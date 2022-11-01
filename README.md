# crop-pest-list

In addition to browsing through the data in a web browser, you can build a simple sqlite database from the crop-pest.csv file. 

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
SELECT * 
FROM crop_pest
WHERE crop LIKE '%Citrus%' AND pest_family = 'Aleyrodidae';
```
