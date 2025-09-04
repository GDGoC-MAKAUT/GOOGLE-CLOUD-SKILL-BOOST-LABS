### 


```bash

bq load --source_format=CSV --skip_leading_rows=1 --autodetect products.products_information gs://[PROJECT_ID]-bucket/products.csv
```
```
bq query --use_legacy_sql=false 'CREATE SEARCH INDEX product_search_index ON products.products_information(ALL COLUMNS)'
```
```
bq query --use_legacy_sql=false 'SELECT * FROM products.products_information WHERE SEARCH(products_information, "22 oz Water Bottle")'
```




