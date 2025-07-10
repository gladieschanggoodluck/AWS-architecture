```mermaid
flowchart TD
    subgraph Security_and_Monitoring [Security and Monitoring]
        IAM[AWS IAM<br/>Access Control]
        KMS[AWS KMS<br/>Encryption]
        CW[AWS CloudWatch<br/>Monitoring & Alerts]
    end

    EXTERNAL[External Data Sources (NSQA, MISLE, FCC, IMO, ITU, IACS)]
    LAMBDA[AWS Lambda Functions<br/>Data Retrieval & Automation]
    S3[Amazon S3<br/>Raw Data Bucket (raw/, processed/)]
    GLUE[AWS Glue Jobs<br/>Data Processing]
    RDS[Amazon RDS (PostgreSQL)<br/>Structured Data]
    QUICKSIGHT[Amazon QuickSight<br/>Data Visualization]

    EXTERNAL --> LAMBDA
    LAMBDA --> S3
    S3 --> GLUE
    GLUE --> RDS
    RDS --> QUICKSIGHT

    %% Security and Monitoring applies to all major services
    IAM -.-> LAMBDA
    IAM -.-> S3
    IAM -.-> GLUE
    IAM -.-> RDS
    IAM -.-> QUICKSIGHT

    KMS -.-> S3
    KMS -.-> RDS

    CW -.-> LAMBDA
    CW -.-> S3
    CW -.-> GLUE
    CW -.-> RDS
    CW -.-> QUICKSIGHT
```
