```mermaid
flowchart TD
    A[External Data Sources<br/>(NSQA, MISLE, FCC, IMO, ITU, IACS)]
    B[AWS Lambda Functions<br/>(Data Retrieval)]
    C[Amazon S3<br/>(Raw Data Bucket)]
    D[AWS Glue Jobs<br/>(Data Processing)]
    E[Amazon RDS<br/>(PostgreSQL/Structured Data)]
    F[Amazon QuickSight<br/>(Data Visualization)]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
``` 
