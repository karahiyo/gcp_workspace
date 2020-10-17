# BigQuery

https://cloud.google.com/bigquery

## Quickstart

https://cloud.google.com/bigquery/docs/quickstarts/quickstart-command-line?hl=ja

```
wget https://www.ssa.gov/OACT/babynames/names.zip
```

create dataset
```
bq mk babynames
```

list tables
```
bq ls
```

upload
```
bq load babynames.names2010 babynames/yob2010.txt name:string,gender:string,count:integer
```

check scheme
```
bq show babynames.names2010
```

run query
```
bq query "SELECT name,count FROM babynames.names2010 WHERE gender = 'F' ORDER BY count DESC LIMIT 5"

+----------+-------+
|   name   | count |
+----------+-------+
| Isabella | 22921 |
| Sophia   | 20646 |
| Emma     | 17348 |
| Olivia   | 17029 |
| Ava      | 15435 |
+----------+-------+
```
