# ELT Pipeline in Datalake

## ELT - Extract Load Transform pipeline ingestion from Database into a single datalake location to do transform processing.


# Diagram
<img src="https://github.com/Jira-saki/AWS-ELT-S3-Athena/blob/main/diagram.png" width="700">

## Introduction & Goals
- Ingest Data from RDBMS to a Data lake bucket. 
- Process transaction files to a single location
  - Data set of customer list of sales person
  - We use [AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html") 
  - Create Data Catalog, transform, load to Data lake
  - Data will be transform from CSV to [Parquet file](https://databricks.com/glossary/what-is-parquet")
  - Parquet stores the file schema in the file metadata. It is easier to work with because they are supported by so many different projects.
  - Transformed data will be ready for query in Data Warehouse


## The Data Set
- We use transaction data set [customer.csv](https://github.com/Jira-saki/AWS-ELT-S3-Athena/blob/main/customer.csv").
- Data set of sales person's customer list
- appropiate size 197 KB for Glue ETL demo


## Used Tools
- **Amazon RDS postgreSQL, AWS Glue, Glue crawler, [Athena](https://aws.amazon.com/athena/?nc=sn&loc=1&whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc")**
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
