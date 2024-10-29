# Table of contents
## Project Overview

### Data Sources
#### Tools
##### Analysis
```sql
SELECT country, 
       SUM(CASE WHEN import_export = 'export' THEN value ELSE 0 END) AS total_exports, 
       SUM(CASE WHEN import_export = 'import' THEN value ELSE 0 END) AS total_imports,
       (SUM(CASE WHEN import_export = 'export' THEN value ELSE 0 END) - 
        SUM(CASE WHEN import_export = 'import' THEN value ELSE 0 END)) AS trade_balance
FROM portal
GROUP BY country
order by trade_balance desc;
```
###### Results
###### Recommendations
######  Limitations
