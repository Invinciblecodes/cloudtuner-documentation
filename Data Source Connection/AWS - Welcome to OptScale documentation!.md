[Skip to content](https://hystax.com/documentation/optscale/e2e_guides/#aws)

## AWS

## Root account – Data Export already configured

OptScale supports the AWS Organizations service that allows linking several Data Sources in order to centrally manage data of multiple users while receiving all billing exports within a single invoice. The Root account (payer) will be the only one having access to collective data related to cloud spendings. When registering this type of profile in OptScale, the user is given an option for Data Exports to be detected automatically.

Warning

When you connect the root account but do not connect the linked accounts, all expenses from the unconnected linked accounts will be ignored, even if they exist in the data export file. To retrieve expenses from both linked and root accounts, connect all AWS accounts (not just the root). OptScale ignores data from unconnected linked accounts.

### Configure policies and user

1\. **Configure Data Exports**. Having Data Exports configured for your cloud account is the main prerequisite in order to proceed with the remaining actions. If Data Export hasn't been configured, refer to the [Root Account – Data Export not configured yet](https://hystax.com/documentation/optscale/e2e_guides/e2e_aws.html#root-account-data-export-not-configured-yet) instruction.

2\. **Update bucket policy**:

- Navigate to the **Permissions** tab of your AWS S3 bucket → select **Bucket Policy**.
- Click **\+ Add new statement** → insert a JSON code snippet:
	```json
	{
	   "Version":"2012-10-17",
	   "Statement":[
	      {
	         "Sid":"EnableAWSDataExportsToWriteToS3AndCheckPolicy",
	         "Effect":"Allow",
	         "Principal":{
	            "Service":[
	               "billingreports.amazonaws.com",
	               "bcm-data-exports.amazonaws.com"
	            ]
	         },
	         "Action":[
	            "s3:PutObject",
	            "s3:GetBucketPolicy"
	         ],
	         "Resource":[
	            "arn:aws:s3:::<bucket_name>/*",
	            "arn:aws:s3:::<bucket_name>"
	         ],
	         "Condition":{
	            "StringLike":{
	               "aws:SourceAccount":"<AWS account ID>",
	               "aws:SourceArn":[
	                  "arn:aws:cur:us-east-1:<AWS account ID>:definition/*",
	                  "arn:aws:bcm-data-exports:us-east-1:<AWS account ID>:export/*"
	               ]
	            }
	         }
	      }
	   ]
	}
	```
- Replace `<bucket_name>` with the name of the bucket.
- Replace `<AWS account ID>` with the AWS Account ID (12 digits without “-”).
- Save.

3\. Create user policies for **Discover Resources** and **ReadOnly access**.

- **ReadOnly access**:
	- Follow [steps 1–5 of the instructions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html#access_policies_create-json-editor).
	- Insert the JSON code in the **Type or paste a JSON policy document** step:
		```json
		{
		   "Version":"2012-10-17",
		   "Statement":[
		      {
		         "Sid":"ReportDefinition",
		         "Effect":"Allow",
		         "Action":[
		            "cur:DescribeReportDefinitions"
		         ],
		         "Resource":"*"
		      },
		      {
		         "Sid":"GetObject",
		         "Effect":"Allow",
		         "Action":[
		            "s3:GetObject"
		         ],
		         "Resource":"arn:aws:s3:::<bucket_name>/*"
		      },
		      {
		         "Sid":"BucketOperations",
		         "Effect":"Allow",
		         "Action":[
		            "s3:ListBucket",
		            "s3:GetBucketLocation"
		         ],
		         "Resource":"arn:aws:s3:::<bucket_name>"
		      }
		   ]
		}
		```
	- Replace `<bucket_name>` with the name of the bucket created on the previous step.
- **Discover Resources**:
	- Include the following policy to allow OptScale to parse EC2 resource data. Follow [steps 1-5 of the instructions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html#access_policies_create-json-editor).
	- Insert the JSON code on the **Type or paste a JSON policy document** step:

4\. **Create user** and **grant policies**:

- Go to **Identity and Access Management (IAM)** → **Users** → create a new user.
- In **Step 2. Set permissions**, select **Attach policies directly** → attach the policies created earlier.
- Confirm the creation of the user.

5\. **Create access key**:

- Go to **Identity and Access Management (IAM)** → **Users** → select the created user → create an access key
- Download the.csv file with **Access key** and **Secret access key**.

### Connect to OptScale

Once the user is configured, add the data source to OptScale.

- Go to **OptScale** → **Data Sources** → click the **Add** button → select **AWS** → choose the **Root** connection type.

![root_account](https://hystax.com/documentation/optscale/_static/screens/onboarding/root_account.png)

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

Wait for the export to be generated by AWS and uploaded to OptScale according to the schedule (which is performed on an hourly basis).

Please contact our Support Team at [support@hystax.com](https://hystax.com/documentation/optscale/e2e_guides/) if you have any questions regarding the described configuration flow.

## Root account – Data Export not configured yet

OptScale supports the AWS Organizations service that allows linking several Data Sources in order to centrally manage data of multiple users while receiving all billing reports within a single invoice. The Root account (payer) will be the only one having access to collective data related to cloud spendings. When registering this type of profile in OptScale, the user is given an option for Data Exports to be created automatically.

Warning

When you connect the root account but do not connect the linked accounts, all expenses from the unconnected linked accounts will be ignored, even if they exist in the data export file. To retrieve expenses from both linked and root accounts, connect all AWS accounts (not just the root). OptScale ignores data from unconnected linked accounts.

### Configure policies and user

1\. **Create user policy** for bucket and export creation access.

- Go to **Identity and Access Management (IAM)** → **Policies**.
- Create a new policy for fully automatic configuration (both bucket and export are created):
	- Follow [steps 1-5 of the instructions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.%20%20%20%20%20html#:~:text=To%20use%20the%20JSON%20policy%20editor%20to%20create%20a%20policy).
	- Insert the JSON code on the **Type or paste a JSON policy document** step:
		```json
		{
		   "Version":"2012-10-17",
		   "Statement":[
		      {
		         "Sid":"ReportDefinition",
		         "Effect":"Allow",
		         "Action":[
		            "cur:DescribeReportDefinitions",
		            "cur:PutReportDefinition"
		         ],
		         "Resource":"*"
		      },
		      {
		         "Sid":"CreateCurExportsInDataExports",
		         "Effect":"Allow",
		         "Action":[
		            "bcm-data-exports:ListExports",
		            "bcm-data-exports:GetExport",
		            "bcm-data-exports:CreateExport"
		         ],
		         "Resource":"*"
		      },
		      {
		         "Sid":"CreateBucket",
		         "Effect":"Allow",
		         "Action":[
		            "s3:CreateBucket"
		         ],
		         "Resource":"*"
		      },
		      {
		         "Sid":"GetObject",
		         "Effect":"Allow",
		         "Action":[
		            "s3:GetObject"
		         ],
		         "Resource":"arn:aws:s3:::<bucket_name>/*"
		      },
		      {
		         "Sid":"BucketOperations",
		         "Effect":"Allow",
		         "Action":[
		            "s3:PutBucketPolicy",
		            "s3:ListBucket",
		            "s3:GetBucketLocation"
		         ],
		         "Resource":"arn:aws:s3:::<bucket_name>"
		      }
		   ]
		}
		```
	- Replace `<bucket_name>` with the name of the bucket.
- **Discover Resources**:
	- Include the following policy to allow OptScale to parse EC2 resource data. Follow [steps 1-5 of the instructions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html#access_policies_create-json-editor).
	- Insert the JSON code on the **Type or paste a JSON policy document** step:

2\. **Create user** and **grant policies**:

- Go to **Identity and Access Management (IAM)** → **Users** → create a new user.
- In **Step 2. Set permissions**, select **Attach policies directly** → attach the policies created earlier.
- Confirm the creation of the user.

3\. **Create access key**:

- Go to **Identity and Access Management (IAM)** → **Users** → select the created user → create an access key
- Download the.csv file with **Access key** and **Secret access key**.

### Connect to OptScale

Once the user is configured, add the data source to OptScale.

- Go to **OptScale** → **Data Sources** → click the **Add** button → select **AWS** → choose the **Root** connection type.

![root_account](https://hystax.com/documentation/optscale/_static/screens/onboarding/root_account.png)

- Fill in the fields:
	- Provide user credentials: **AWS Access key ID** → **Access key**, **AWS Secret access key** → **Access key secret**.
	- Select **Export type** as in the report configured earlier: **AWS Billing and Cost Management** → **Data Exports** → find the report configured earlier → export type.
	- Switch off **Automatically detect existing Data Exports**.
	- Select **Create new Data Export**.
	- Provide Data Export parameters:
		- Export Name: enter a new name for the data export.
		- Export Amazon S3 Bucket Name: **AWS Billing and Cost Management** → **Data Exports** table → **S3 bucket** column.
		- Export path prefix: enter a new export path prefix that you want to prepend to the names of your report files.
		Note
		Specify the bucket in the 'Export S3 Bucket Name' field if it already exists. OptScale will then create the report and store it in the bucket using the specified prefix.
	- Click **Connect** when done.
	- Wait for AWS to generate the export and upload it to OptScale according to the schedule (approximately one day).

Warning

AWS updates or creates a new export file once a day. If the export file is not placed in the specified bucket under the specified prefix, the export will fail with an error.

![status_failed](https://hystax.com/documentation/optscale/_static/screens/onboarding/status_failed.png)

## Root account – Create Standard Data Export / Legacy CUR Export

Note

Creating a data export is only available for the **Root cloud account** (payer), while all its **Linked accounts** will be centrally managed and receive their billing data through the main account's invoice.

In order to utilize automatic / manual billing data import in OptScale, first, create a Data Export in AWS. Please refer to their [official documentation](https://docs.aws.amazon.com/cur/latest/userguide/what-is-data-exports.html) to become acquainted with the guidelines for Data Exports.

- Navigate to **AWS Billing & Cost Management** → **Data Exports**.
- Create a new data export:
	- Standard:
		1\. Select **Standard data export** as the export type.
		2\. Enter the export name.
		3\. Select **CUR 2.0** → select the **Include resource IDs** checkbox → choose the time granularity for how you want the line items in the export to be aggregated.
		4\. Select **Overwrite existing data export file** → choose the compression type.
		5\. Set the data export storage setting:
		- Create a new or use an existing bucket for the export.
		- Enter the **S3 path prefix** that you want prepended to the name of your data export.
		6\. Confirm export creation. Data export is prepared by AWS within 24 hours.
	- Legacy CUR Export:
		1\. Select **Legacy CUR export (CUR)** as the export type.
		2\. Enter the export name.
		3\. Select the **Include resource IDs** and **Refresh automatically** checkboxes.
		4\. Set the data export delivery options:
		- Choose the time granularity for how you want the line items in the export to be aggregated.
		- Sekect **Overwrite existing report**.
		- Choose the compression type.
		5\. Set the data export storage setting:
		- Create a new bucket or use an existing one for the export.
		- Enter the **S3 path prefix** that you want prepended to the name of your data export.
		6\. Confirm export creation. Data export is prepared by AWS within 24 hours

When it's done, follow the steps from the section [Root account – Data Export already configured](https://hystax.com/documentation/optscale/e2e_guides/e2e_aws.html#root-account-data-export-already-configured)

## Linked

OptScale supports the AWS Organizations service that allows linking several Data Sources in order to centrally manage data of multiple users while receiving all billing exports within a single invoice.

Before establishing the connection, include the **Discover Resources** policy to allow OptScale to parse EC2 resource data:

- Follow [steps 1-5 of the instructions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html#access_policies_create-json-editor).
- Insert the JSON code in the **Type or paste a JSON policy document** step:

Now, your AWS Data Source is ready for integration with OptScale!

### Connect to OptScale

Go to **OptScale** → select **AWS** → choose the **Linked** connection type to simplify the registration process. This option removes the need to manually input bucket information for billing purposes, as the data will be received through the root account. The root user can then distribute periodic reports individually if required by company management. In this case, only the **Access Key** and **Secret Access Key** are needed.

![linked_account](https://hystax.com/documentation/optscale/_static/screens/onboarding/linked_account.png)

Note

If you only specify a **AWS Linked account** without providing credentials for the main one, OptScale is not able to import any billing data.

Use **Connect** to create a Data Source in OptScale. If some of the provided values are invalid, an error message indicates a failure to connect.

Please contact our Support Team at [support@hystax.com](https://hystax.com/documentation/optscale/e2e_guides/) if you have any questions regarding the described configuration flow.

## Migrating from CUR to CUR 2.0

The information on this page can be useful if an AWS Data Source (Legacy CUR export schema) has already been connected and you want to configure CUR 2.0 data and update the AWS Data Source.

### A new bucket is required

#### Configure

Create a new Data Export with CUR 2.0 schema:

1\. Navigate to **AWS Billing & Cost Management** → **Data Exports** page → click **Create**.

2\. Select **Standard data export** as an export type, enter **Export name**. This name is required when updating a data source in OptScale.

3\. Fill in the Data table content settings section:

- Select **CUR 2.0**.
- Select the **Include resource IDs** checkbox.
- Choose the time granularity for how you want the line items in the export to be aggregated.

4\. Fill in the Data export delivery options section:

- Choose **Overwrite existing data export file**.
- Select compression type.

5\. Configure a new bucket the Data export storage setting section. Fill in the **S3 path prefix** and **S3 bucket name** fields. They are required when updating a data source in OptScale.

6\. Confirm export creation. Data Export will be prepared by AWS during 24 hours.

#### Connect to OptScale

When the bucket is ready, go to **OptScale** → **Data Sources** → click on the AWS data source.

Click the **UPDATE CREDENTIALS** button to update the Data Source credentials:

- Switch onthe **Update Data Export** parameters to update info about the billing bucket.
- Select **Standard data export (CUR 2.0)** as an export type.
- Enter **Export name** from the first step as **Export name**, **S3 bucket name** as **Export Amazon S3 bucket name**, and **S3 bucket** name as **Export path prefix**.

Save and wait for a new export to import!

### The bucket already exists

Use this case if you have already connected an AWS Data Source (on Legacy CUR export schema) and want to configure CUR 2.0 data into the same bucket.

#### Configure

Create a new Data Export with CUR 2.0 schema:

1\. Navigate to **AWS Billing & Cost Management** → **Data Exports** page → click **Create**.

2\. Select **Standard data export** as an export type, enter **Export name**. This name is required when updating a data source in OptScale.

3\. Fill in the Data table content settings section:

- Select **CUR 2.0**.
- Select the **Include resource IDs** checkbox.
- Choose the time granularity for how you want the line items in the export to be aggregated.

4\. Fill in the Data export delivery options section:

- Choose **Overwrite existing data export file**.
- Select compression type.

5\. Update the Data export storage settings section contents:

- Сlick **Configure** → Select existing bucket → choose an existing S3 bucket → click **Select bucket**.
- Enter a new **S3 path prefix**. This prefix is required when updating a data source in OptScale.

6\. Confirm export update.

#### Connect to OptScale

When the bucket is ready, go to **OptScale** → **Data Sources** → click on the AWS data source.

Click the **UPDATE CREDENTIALS** button to update the data source credentials. Switch on **Update Data Export** parameters to update info about the billing bucket.

![aws_migrate_cur1_cur2_08](https://hystax.com/documentation/optscale/_static/screens/onboarding/aws_migrate_cur1_cur2_08.png)

Select **Standard data export (CUR 2.0)** export type and update **Export name** and **Export path prefix** fields, as in the updated bucket.

Save and wait for a new export to import!

![](https://hystax.com/documentation/optscale/e2e_guides/images/snipp4.svg)