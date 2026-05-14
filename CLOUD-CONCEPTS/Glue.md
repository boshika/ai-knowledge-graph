1. Serverless system handles discovery and definitions. Is a central metadata repository for the data lakes. Extracts structure from unstructured data
2. Used for custom ETL jobs, fully managed. Uses Apache Spark under the hood, since it is fully managed no need to manage the Spark cluster.

Components
1. Glue Crawler/Catalog: Can scan S3 buckets for unstructured data, infer the metadata, this allows Redshift/Athena/Quicksight to query unstrucutred data as structured data. Partitioning in S3 determines how Glue extracts the metadata
2. Glue Data Quality: Rules can be created manually or automatically. Uses Data Qulaity Definition Language(DQDL)
