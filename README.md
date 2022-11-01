# crop-pest-list

In addition to [browsing through the data in a web browser](https://aubreymoore.github.io/crop-pest-list/), you can build a simple sqlite database from the **crop-pest.csv** file by executing the following code in a terminal window. 

The following code creates a database and imports the csv file.
```bash
sqlite3
.open crop_pest.sqlite
.mode csv
.import crop-pest.csv crop_pest
.schema
```

Here's a simple SQL statement which finds whiteflies attacking citrus.
```sql
SELECT pest_scientific_name, pest_common_name 
FROM crop_pest
WHERE pest_family = 'Aleyrodidae' AND crop LIKE '%Citrus%'
ORDER BY pest_scientific_name, pest_common_name;
```
