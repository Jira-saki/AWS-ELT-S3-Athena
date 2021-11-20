# ELT Pipeline in Datalake

## ELT - Extract Load Transform pipeline into a single datalake location on AWS platform.


# Diagram
<img src="https://github.com/Jira-saki/AWS-ELT-S3-Athena/blob/main/diagram.png" width="700">

## Introduction & Goals
- Process transaction files to a single location
- Load Data from RDBMS to Data lake
  - Data set of customer list of sales person
  - We use AWS Glue 
  - Create Data Catalog, transform, load to Data lake
  - Data will be transform from csv to parquet.


## The Data Set
- We use transaction data set "customer.csv" 
- Data set of customer list of sales person
- appropiate size 197 KB for Glue ETL demo


## Used Tools
- **Amazon RDS postgreSQL, AWS Glue, Glue crawler, Athena**
  - Load .csv file RDS into *input folder* inside a bucket.
	  - Create *output folder* as target inside the same bucket.
  - Add Glue crawler to craw Data catalog of  .csv file ( in *input folder*)
	  - run Glue job to transform to parquet file  
	  - Set target to load into *output folder* 
  - In Athena, check view or query of transformed file. 
  - Add Glue crawler to craw Data catalog of .parquet file in (output folder).

# Pipelines
- Batch processing pipeline for bulk import.
- Use source code of AWS Glue

## Conclusion
- Data set has transform inside a single datalake bucket
- File can be loading to Data Warehouse.
- Glue job can be assign for aggregate , join, filter tables


## Follow Me On
https://www.linkedin.com/in/jirasak-pakdeeto-900665214/
