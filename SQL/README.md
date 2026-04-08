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
```
