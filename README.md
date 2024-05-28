# Data Engineering project with Medallion Architecture using DBT, Databricks, Spark and Azure Cloud

**Steps Involved**

**Azure Cloud**
1.In azure cloud create a sql database called medallion-db-dev with the sample database of Adventure Works using SalesLT schema
2.	An azure data lake gen2 called adlspromedallion with the medallion architecture containing bronze, silver and gold layers.
3.	Used Azure Data Factory with activities
a) Lookup - to fetch the list of schema name and base tables 
b) for each enumerator, copy data activity and databricks notebook to load data within these tables and mount to a bronze layer in adls gen 2 as parquet files

**DBT**
1)	Create snapshots of address, customer, customeraddress, product, productmodel, salesorderdetail, salesorderheader tables and mount to silver layer using the delta file format
2)	Perform transformations on address, customeraddress, customer snapshots to produce dim_customer table
3)	Perform transformations on product, product_model to produce dim_product table
4)	Perform transformations on sales_orderdetail, salesorderheader, to produce dim_sales table

**Commands**
1)	dbt run # for running models
2)	dbt test # for tests
3)	dbt snapshot # for snapshotting and slowly changing dimensions
4)	dbt docs # for documentation
5)	dbt docs serve # for documentation preview

**Azure Data Factory pipeline**
![image](https://github.com/annvin/ADF_spark_dbt/assets/42974141/b816a094-7ebc-48d9-8db4-e16cabfdfa7b)

**DBT Documentation**
![image](https://github.com/annvin/ADF_spark_dbt/assets/42974141/d350eb97-0b82-4d2d-bad5-9c1e88b8e6cf)
![image](https://github.com/annvin/ADF_spark_dbt/assets/42974141/3e6b3a46-2b04-4cbd-83a0-d99c59e84242)
![image](https://github.com/annvin/ADF_spark_dbt/assets/42974141/cfa706b0-a3ba-48d7-9331-b4ae54865ecf)




