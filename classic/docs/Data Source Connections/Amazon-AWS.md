---

title: Amazon Web Services (AWS)

---
## Quick Setup Overview

CloudTuner supports AWS Organizations for centralized cost management across multiple accounts. The root account (payer) accesses collective billing data while linked accounts are managed centrally.

⚠️ **Important**: Connect ALL AWS accounts (root + linked) to retrieve complete expense data. Unconnected linked accounts will be ignored.

## Setup Options

### Option 1: Root Account (Existing Data Export)

**Prerequisites**: [AWS Data Exports](https://console.aws.amazon.com/billing/home#/dataexports) already configured

#### Step 1: Update S3 Bucket Policy

1. Go to [S3 Console](https://console.aws.amazon.com/s3) → Your bucket → **Permissions** → **Bucket Policy**
2. Add this policy (replace `<bucket_name>` and `<AWS_account_ID>`):

```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Sid": "EnableAWSDataExportsToWriteToS3AndCheckPolicy",
    "Effect": "Allow",
    "Principal": {
      "Service": ["billingreports.amazonaws.com", "bcm-data-exports.amazonaws.com"]
    },
    "Action": ["s3:PutObject", "s3:GetBucketPolicy"],
    "Resource": ["arn:aws:s3:::<bucket_name>/*", "arn:aws:s3:::<bucket_name>"],
    "Condition": {
      "StringLike": {
        "aws:SourceAccount": "<AWS_account_ID>",
        "aws:SourceArn": [
          "arn:aws:cur:us-east-1:<AWS_account_ID>:definition/*",
          "arn:aws:bcm-data-exports:us-east-1:<AWS_account_ID>:export/*"
        ]
      }
    }
  }]
}
```

#### Step 2: Create IAM Policies

1. Go to [IAM Policies](https://console.aws.amazon.com/iam/home#/policies) → **Create Policy** → **JSON**

**ReadOnly Policy:**
*[enhanced-policy]*
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "cur:DescribeReportDefinitions"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": "arn:aws:s3:::<bucket_name>/*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:GetBucketLocation"
            ],
            "Resource": "arn:aws:s3:::<bucket_name>"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetBucket*",
                "iam:GetAccessKeyLastUsed",
                "cloudwatch:GetMetricStatistics",
                "ec2:Describe*",
                "s3:ListAllMyBuckets",
                "iam:ListUsers",
                "s3:GetBucketLocation",
                "iam:GetLoginProfile",
                "cur:DescribeReportDefinitions",
                "iam:ListAccessKeys",
                "elasticloadbalancing:Describe*"
            ],
            "Resource": "*"
        }
    ]
}
```

#### Step 3: Create IAM User

1. Go to [IAM Users](https://console.aws.amazon.com/iam/home#/users) → **Create User**
2. **Set permissions** → **Attach policies directly** → Select both policies above
3. **Create access key** → Download CSV with credentials

#### Step 4: Connect to CloudTuner

1. Go to **CloudTuner** → **Data Sources** → **Add** → **AWS** → **Root**
2. Enter:
    - **Access Key ID** and **Secret Key** from CSV
    - **Export Name**: From [Data Exports table](https://console.aws.amazon.com/billing/home#/dataexports)
    - **S3 Bucket Name**: From Data Exports table
    - **Export Path Prefix**: Last folder from S3 destination path

---

### Option 2: Root Account (Auto-Create Export)

**Use when**: No existing AWS Data Exports

#### Step 1: Create Enhanced IAM Policy

1. Go to [IAM Policies](https://console.aws.amazon.com/iam/home#/policies) → **Create Policy** → **JSON**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "cur:DescribeReportDefinitions", "cur:PutReportDefinition",
        "bcm-data-exports:ListExports", "bcm-data-exports:GetExport", "bcm-data-exports:CreateExport",
        "s3:CreateBucket", "s3:GetObject", "s3:PutBucketPolicy", "s3:ListBucket", "s3:GetBucketLocation"
      ],
      "Resource": "*"
    }
  ]
}
```

2. Also create the **Resource Discovery Policy** from Option 1

#### Step 2: Create User & Connect

1. Follow Step 3 from Option 1 for user creation
2. In CloudTuner:
    - Select **Create new Data Export**
    - Enter desired **Export Name** and **S3 Bucket Name**
    - Wait 24 hours for AWS to generate export

---

### Option 3: Linked Account

**Use for**: Secondary accounts under AWS Organizations

#### Setup

1. Create only the **Resource Discovery Policy** from Option 1
2. Go to [IAM Users](https://console.aws.amazon.com/iam/home#/users) → Create user with this policy
3. Generate access key
4. In CloudTuner:
    - Select **AWS** → **Linked** connection type
    - Enter only **Access Key ID** and **Secret Key**

> [!NOTE]
> 📝 **Note**: Billing data comes through root account automatically
> 

---

### Option 4: Manual Data Export Setup

#### Create Standard Data Export (CUR 2.0)

1. Go to [AWS Billing & Cost Management](https://console.aws.amazon.com/billing/home#/dataexports) → **Create**
2. Configure:
    - **Export Type**: Standard data export
    - **Data Table**: CUR 2.0 + Include resource IDs
    - **Storage**: Choose/create S3 bucket + path prefix
    - **Delivery**: Overwrite existing files
3. Wait 24 hours for AWS preparation
4. Follow Option 1 steps for connection

---
## Connect to [CloudTuner](https://dashboard.cloudtuner.ai/cloud-accounts)

  

Once the user is configured, add the data source to CloudTuner.

  

- Go to **CloudTuner** → **Cloud Accounts** → click the **Add** button → select **AWS** → choose the **Root** connection type.

  

![root_account](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/cloudaccounts.png)

  

- Fill in the fields:

- Provide user credentials: **AWS Access key ID** → **Access key**, **AWS Secret access key** → **Access key secret**.

- Select **Export type** as in the report configured earlier: **AWS Billing and Cost Management** → **Data Exports** → find the report configured earlier → export type.

- Switch off **Automatically detect existing Data Exports**.

- Select **Connect only to data in bucket**.

- Provide Data Export parameters:

- Export Name: **AWS Billing and Cost Management** → **Data Exports** table → **Export name** column.

- Export Amazon S3 Bucket Name: **AWS Billing and Cost Management** → **Data Exports** table → **S3 bucket** column.

- Export path prefix: **AWS Billing and Cost Management** → **Data Exports** table → click on Export name → Edit → Data export storage settings → S3 destination → last folder name(without “/”). Example, S3 destination: *s3://aqa-bill-bucket/report-cur2*, enter *report-cur2* into the field.

  

Attention

  

Wait for the export to be generated by AWS and uploaded to CloudTuner according to the schedule (which is performed on an hourly basis).

> 
> Please contact our Support Team at [contact@cloudtuner.ai](mailto:contact@cloudtuner.ai) if you have any questions regarding the described configuration flow.
> 
> 

---

## Migration: CUR to CUR 2.0

### Quick Migration Steps

1. Go to [Data Exports](https://console.aws.amazon.com/billing/home#/dataexports) → **Create**
2. Select **Standard data export** → **CUR 2.0**
3. Choose existing bucket or create new one with different prefix
4. In CloudTuner → **Data Sources** → Your AWS connection → **UPDATE CREDENTIALS**
5. Switch on **Update Data Export parameters**
6. Update export type to **Standard data export (CUR 2.0)** and new prefix

---

## Quick Links

- [AWS S3 Console](https://console.aws.amazon.com/s3)
- [IAM Policies](https://console.aws.amazon.com/iam/home#/policies)
- [IAM Users](https://console.aws.amazon.com/iam/home#/users)
- [AWS Data Exports](https://console.aws.amazon.com/billing/home#/dataexports)
- [Billing & Cost Management](https://console.aws.amazon.com/billing/home)

## Troubleshooting

**Export not found**: Wait 24 hours after creation, verify bucket name/prefix **Access denied**: Check IAM policies and access key validity **No data**: Ensure all linked accounts are connected to CloudTuner


> 
> When you connect the root account but do not connect the linked accounts, all expenses from the unconnected linked accounts will be ignored, even if they exist in the data export file. To retrieve expenses from both linked and root accounts, connect all AWS accounts (not just the root). CloudTuner ignores data from unconnected linked accounts.
> 