```mermaid
flowchart TD
    A[External Data Sources\n(NSQA, MISLE, FCC, IMO, ITU, IACS)]
    B[AWS Lambda Functions\n(Data Retrieval)]
    C[Amazon S3\n(Raw Data Bucket)]
    D[AWS Glue Jobs\n(Data Processing)]
    E[Amazon RDS\n(PostgreSQL/Structured Data)]
    F[Amazon QuickSight\n(Data Visualization)]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
```
