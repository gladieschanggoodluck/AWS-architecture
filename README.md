# AWS-architecture
```mermaid
flowchart TD
    EXTERNAL[External Data Sources<br/>(NSQA, MISLE, FCC, IMO, ITU, IACS)]
    LAMBDA1[AWS Lambda Functions]
    S3[Amazon S3<br/>(Raw Data Bucket)<br/>Folders: raw/, processed/]
    GLUE1[AWS Glue Jobs]
    RDS[Amazon RDS<br/>(PostgreSQL)<br/>Schemas: fcc, iacs, imo, itu, misle, nsqa]
    GLUE2[AWS Glue Jobs]
    LAMBDA2[AWS Lambda Functions]
    QUICKSIGHT[Amazon QuickSight]
    IAM[AWS IAM<br/>(Access Control)]
    KMS[AWS KMS<br/>(Encryption)]
    CLOUDWATCH[AWS CloudWatch<br/>(Monitoring)]

    EXTERNAL --> S3
    LAMBDA1 --> GLUE1
    GLUE1 --> S3
    S3 --> GLUE1
    GLUE1 --> RDS
    RDS --> GLUE2
    GLUE2 --> LAMBDA2
    RDS --> QUICKSIGHT
    QUICKSIGHT --> IAM
    LAMBDA2 --> KMS
    GLUE2 --> KMS
    LAMBDA1 --> CLOUDWATCH
    GLUE1 --> CLOUDWATCH
    RDS --> CLOUDWATCH
```
