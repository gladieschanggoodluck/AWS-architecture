```mermaid
flowchart TD
    EXTERNAL["External Data Sources\n(NSQA, MISLE, FCC, IMO, ITU, IACS)"]
    LAMBDA1["AWS Lambda Functions"]
    S3["Amazon S3\n(Raw Data Bucket)\nFolders: raw/, processed/"]
    GLUE1["AWS Glue Jobs"]
    RDS["Amazon RDS\n(PostgreSQL)\nSchemas: fcc, iacs, imo, itu, misle, nsqa"]
    GLUE2["AWS Glue Jobs"]
    LAMBDA2["AWS Lambda Functions"]
    QUICKSIGHT["Amazon QuickSight"]
    IAM["AWS IAM\n(Ac```mermaid
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
