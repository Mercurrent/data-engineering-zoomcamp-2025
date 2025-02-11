**Queries:**

2.
```
SELECT COUNT(DISTINCT PULocationID) AS distinct_pulocation_count
FROM `datazoomcamp-450522.TaxiDataset.TaxiTable`;

SELECT COUNT(DISTINCT PULocationID) AS distinct_pulocation_count
FROM `datazoomcamp-450522.TaxiDataset.RegularTaxiTable`;
```

3.
```
SELECT PULocationID
FROM `datazoomcamp-450522.TaxiDataset.RegularTaxiTable`;

SELECT PULocationID, DOLocationID
FROM `datazoomcamp-450522.TaxiDataset.RegularTaxiTable`;
```

4.
```
SELECT COUNT(*) AS zero_fare_count
FROM `datazoomcamp-450522.TaxiDataset.RegularTaxiTable`
WHERE fare_amount = 0;
```
5.
```
CREATE TABLE `datazoomcamp-450522.TaxiDataset.OptimizedTaxiTable`
PARTITION BY DATE(tpep_dropoff_datetime)
CLUSTER BY VendorID AS
SELECT *
FROM `datazoomcamp-450522.TaxiDataset.RegularTaxiTable`;
```

6.
```
SELECT DISTINCT VendorID
FROM `datazoomcamp-450522.TaxiDataset.OptimizedTaxiTable`
WHERE tpep_dropoff_datetime BETWEEN '2024-03-01' AND '2024-03-15';
```