# crop-pest-list

In addition to [examining the data in a web browser](https://aubreymoore.github.io/crop-pest-list/), you can build a simple sqlite database from the **crop-pest.csv** file by executing the following code in a terminal window. 
```bash
wget https://github.com/aubreymoore/crop-pest-list/raw/gh-pages/crop-pest.csv
sqlite3
.open crop_pest.sqlite
.mode csv
.headers on
.import crop-pest.csv crop_pest
.schema
```

The following code finds whiteflies attacking citrus. 
(Tip: If you want to see the result in a spreadsheet, execute the **.excel** command just before running the SQL query.)
```sql
SELECT pest_scientific_name, pest_common_name 
FROM crop_pest
WHERE pest_family = 'Aleyrodidae' AND crop LIKE '%Citrus%'
ORDER BY pest_scientific_name, pest_common_name;
```
Result:
```
pest_scientific_name,pest_common_name
"Aleurocanthus spiniferus (Quaintance)","orange spiny whitefly"
"Aleurodicus dispersus Russell","spiralling whitefly"
"Aleurothrixus floccosus (Maskell)","woolly whitefly"
"Dialeurodes citrifolii (Morgan)","cloudywinged whitefly"
```
## Notes

### URL for Google search

[Google search](https://www.google.com/search?q=Bactocera+cucurbitae)

### URL for Google image search

[Google images](https://www.google.com/search?q=Bactocera+cucurbitae&tbm=isch)

