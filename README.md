# crop-pest-list

```bash
sqlite3
.open crop_pest.sqlite
.mode csv
.import crop-pest.csv crop_pest
.schema
```

```sql
SELECT * 
FROM crop_pest
WHERE crop LIKE '%Citrus%' AND pest_family = 'Aleyrodidae';
```
