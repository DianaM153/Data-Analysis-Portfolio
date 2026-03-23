Sql Queries
Regional Development Analysis
Average water access by region

  SELECT region,
  
      ROUND(AVG(Pct_managed_drinking_water_services),2) AS avg_water_access
      
      FROM united_nations.access_to_basic_services
      
      GROUP BY region
      
      ORDER BY avg_water_access DESC;
