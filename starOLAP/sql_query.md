 OLAP Queries
 
 Query 1:
 ```
  SELECT sum(cost), location.city FROM fact_table
  INNER JOIN location ON fact_table.idlocation = location.idlocation
  GROUP BY location.city;
```
Query 2:
```
  SELECT sum(cost), location.city, rating.avg_rating FROM fact_table
  INNER JOIN location ON fact_table.idlocation = location.idlocation
  INNER JOIN rating ON fact_table.idrating = rating.idrating
  where rating.avg_rating > 3
  GROUP BY location.city;
```
Query 3:
```
  SELECT sum(cost), location.city, rating.avg_rating FROM fact_table
  INNER JOIN location ON fact_table.idlocation = location.idlocation
  INNER JOIN rating ON fact_table.idrating = rating.idrating
  where rating.avg_rating > 3 AND rating.votes > 80
  GROUP BY location.city;
```
Query 4:
```
  SELECT sum(cost), location.city, rating.avg_rating FROM fact_table
  INNER JOIN location ON fact_table.idlocation = location.idlocation
  INNER JOIN rating ON fact_table.idrating = rating.idrating
  where rating.avg_rating > 3 AND rating.votes > 80
  GROUP BY location.city, rating.avg_rating;
```

