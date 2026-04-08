```sql
-- =========================================
-- ADVANCED SQL ANALYSIS
-- Project: Global Access To Basic Services
-- =========================================

-- 1. Regional developmental analysis
   
SELECT region,
ROUND(AVG(Pct_managed_drinking_water_services),2) AS avg_water_access
FROM united_nations.access_to_basic_services
GROUP BY region
ORDER BY avg_water_access DESC;

-----------------------------------------
-- Trend Analysis

SELECT country_name,
time_period,
Pct_managed_drinking_water_services,
LAG(Pct_managed_drinking_water_services) OVER (PARTITION BY country_name ORDER BY time_period) AS previous_year,
ROUND(Pct_managed_drinking_water_services - LAG(Pct_managed_drinking_water_services) 
OVER (PARTITION BY country_name ORDER BY time_period),2) AS yearly_change
FROM united_nations.access_to_basic_services;

-----------------------------------------
-- Ranking Countries by Sanitation Access

SELECT country_name,
ROUND(AVG(Pct_managed_sanitation_services),2) AS avg_sanitation,
RANK() OVER (ORDER BY AVG(Pct_managed_sanitation_services) DESC) AS sanitation_rank
FROM united_nations.access_to_basic_services
GROUP BY country_name;

-----------------------------------------
-- GDP VS Water Access

SELECT 
  (avg_xy - avg_x * avg_y) /
  SQRT((avg_x2 - POW(avg_x,2)) * (avg_y2 - POW(avg_y,2))) AS water_gdp_corr
FROM (
  SELECT 
    AVG(Est_gdp_in_billions * Pct_managed_drinking_water_services) AS avg_xy,
    AVG(Est_gdp_in_billions) AS avg_x,
    AVG(Pct_managed_drinking_water_services) AS avg_y,
    AVG(POW(Est_gdp_in_billions,2)) AS avg_x2,
    AVG(POW(Pct_managed_drinking_water_services,2)) AS avg_y2
  FROM united_nations.access_to_basic_services
) stats;
```
