-- =========================================
-- ADVANCED SQL ANALYSIS
-- Project: Global Water & Sanitation
-- =========================================

-- 1. Regional developmental analysis
   
   SELECT region,
   ROUND(AVG(Pct_managed_drinking_water_services),2) AS avg_water_access
   FROM united_nations.access_to_basic_services
   GROUP BY region
   ORDER BY avg_water_access DESC;
 -----------------------------------------
--Trend Analysis

SELECT country_name,
time_period,
Pct_managed_drinking_water_services,
LAG(Pct_managed_drinking_water_services) OVER (PARTITION BY country_name ORDER BY time_period) AS previous_year,
ROUND(Pct_managed_drinking_water_services - LAG(Pct_managed_drinking_water_services) 
OVER (PARTITION BY country_name ORDER BY time_period),2) AS yearly_change
FROM united_nations.access_to_basic_services;
