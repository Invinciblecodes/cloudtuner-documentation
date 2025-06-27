---
title: Microsoft Azure
---

## Subscription

To use data from a specific export, follow the [Subscription - With Billing Export](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#subscription) instructions. Otherwise, follow the instructions below.

Before connecting, ensure that **Subscription ID**, **Directory (tenant) ID**, **Application (client) ID**, and a **Secret** are available. Also, verify that the **Reader** permission is set. If it is not, go to the [Collect the required data](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#collect-the-required-data) section before proceeding to [Connect to CloudTuner](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#connect-to-cloudtuner).

### Collect the required data

1\. [Copy **Subscription ID**](https://learn.microsoft.com/en-us/azure/azure-portal/get-subscription-tenant-id#find-your-azure-subscription).

2\. Generate and copy **Application (client) ID**:

- **Azure Active Directory** → **App registrations**.
- Click **\+ New registration**, provide a name (e.g. *CloudTuner*), and click **Register** at the bottom of the page.
- The newly created **Application (client) ID** is available in the table under the **Owned applications** tab.
- Copy the **Application (client) ID** and store it in a safe place.

3\. **Grand permissions**:

- **Azure Home** page → **Subscriptions** → select the subscription provisioned to be linked to CloudTuner.
- Click **Access control (IAM)** in the left navigation bar → **Role assignments** tab → click **+Add** → **Add role assignment**.
- Go to the **Roles** tab → Fill in the field:
	- Selected role → *Reader*
- Go to the **Members** tab → Fill in the fields:
	- **Assign access** to → *User, group, or service principal*
	- **Members** → Select the name of a registered application from the previous steps (e.g., *CloudTuner*).
- **Save** to add the role assignment.

4\. Copy **Directory (tenant) ID**. Go to **Home** → **App registrations** → find registration name (e.g. *CloudTuner*) → **Overview** → copy **Directory (tenant) ID**.

5\. Create and copy **Secret**. Go to **Home** → **App registrations** → find registration name (e.g. *CloudTuner*) → **Certificates & Secrets** → click **\+ New client secret**.

Attention

Secret's value is hidden shortly after its creation. Make sure to copy it in a safe place.

### Connect to CloudTuner

Go to **CloudTuner** → **Data Sources** → click the **Add** button → select **Azure** → choose the **Subscription** connection type.

![connect_azure](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/azurecloudconnect.png)

To successfully connect an Azure data source to CloudTuner it is needed to pass a **Subscription ID**, **Directory (tenant) ID**, and **Application (client) ID** along with a **Secret**.

When the fields are filled in, click the **Connect** button.

Please contact our Support Team at [contact@cloudtuner.ai](mailto:contact@cloudtuner.ai) if you have any questions regarding the described configuration flow.

To use data from a specific export, follow the instructions below. Otherwise, follow the [Subscription setup instructions](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#subscription).

Before connecting, ensure that **Subscription ID**, **Directory (tenant) ID**, **Application (client) ID**, and a **Secret** are available. If they are not, go to the [Collect the required data](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#collect-the-required-data-2) section before proceeding to [Connect to CloudTuner](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#connect-to-cloudtuner-2).

### Collect the required data

1\. [Copy **Subscription ID**](https://learn.microsoft.com/en-us/azure/azure-portal/get-subscription-tenant-id#find-your-azure-subscription).

2\. Generate and copy **Application (client) ID**:

- **Azure Active Directory** → **App registrations**.
- Click **\+ New registration**, provide a name (e.g. *CloudTuner*), and click **Register** at the bottom of the page.
- The newly created **Application (client) ID** is available in the table under the **Owned applications** tab.
- Copy the **Application (client) ID** and store it in a safe place.

3\. **Grand permissions**:

- **Azure Home** page → **Subscriptions** → select the subscription provisioned to be linked to CloudTuner.
- Click **Access control (IAM)** in the left navigation bar → **Role assignments** tab → click **+Add** → **Add role assignment**.
- Go to the **Roles** tab → Fill in the field:
	- Selected role → *Reader*
- Go to the **Members** tab → Fill in the fields:
	- **Assign access** to → *User, group, or service principal*
	- **Members** → Select the name of a registered application from the previous steps (e.g., *CloudTuner*).
- **Save** to add the role assignment.

4\. Copy **Directory (tenant) ID**. Go to **Home** → **App registrations** → find registration name (e.g. *CloudTuner*) → **Overview** → copy **Directory (tenant) ID**.

5\. Create and copy **Secret**. Go to **Home** → **App registrations** → find registration name (e.g. *CloudTuner*) → **Certificates & Secrets** → click **\+ New client secret**.

Attention

Secret's value is hidden shortly after its creation. Make sure to copy it in a safe place.

6\. Use the [Create and manage Cost Management exports](https://docs.azure.cn/en-us/cost-management-billing/costs/tutorial-improved-exports) tutorial to create export. Set the following parameters:

- Scope: Subscription
- Frequency: Daily export of month-to-date costs.
- Type of data: Cost and usage details (or usage only).
- Overwrite data: On.

### Connect to CloudTuner

Go to **CloudTuner** → **Data Sources** → click the **Add** button → select **Azure** → choose the **Subscription** connection type.

![connect_azure](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/azurecloudconnect.png)

To successfully connect an Azure data source to CloudTuner it is needed to

1\. Pass a **Subscription ID**, **Directory (tenant) ID**, and **Application (client) ID** along with a **Secret**.

2\. Switch on **Use billing export**.

3\. Enter the name of the cost management export as **Export name** (usually consist of prefix + export name),

4\. Use the connection string to connect to storage account where report files are stored as **Storage account connection string**, to get it:

- Navigate to storage account’s page → **Security + Networking** → **Access Keys**,
- Copy connection string value, it should be: `DefaultEndpointsProtocol=https;AccountName=<storage account name>;AccountKey=<secret>;EndpointSuffix=<core.windows.net or sovereign cloud suffix>`.

5\. Enter the storage container as **Storage container**. Copy it from the **Essentials** section of the export parameters.

6\. Enter the storage directory as **Storage directory**. Copy it from the **Essentials** section of the export parameters.

When the fields are filled in, click the **Connect** button.

Please contact our Support Team at [contact@cloudtuner.ai](mailto:contact@cloudtuner.ai) if you have any questions regarding the described configuration flow.

## Tenant

Before connecting, ensure that **Subscription ID**, **Directory (tenant) ID**, **Application (client) ID**, and a **Secret** are available. If they are not, go to the [Collect the required data](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#collect-the-required-data-2) section before proceeding to [Connect to CloudTuner](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#connect-to-cloudtuner-2).

### Collect the required data

1\. Generate and copy **Application (client) ID**:

- **Azure Active Directory** → **App registrations**.
- Click **\+ New registration**, provide a name (e.g. *CloudTuner*), and click **Register** at the bottom of the page.
- The newly created **Application (client) ID** is available in the table under the **Owned applications** tab.
- Copy the **Application (client) ID** and store it in a safe place.

2\. **Grand permissions**:

- **Azure Home** page → **Subscriptions** → select the ones you have provisioned to be linked to CloudTuner.
- Click **Access control (IAM)** in the left navigation bar → **Role assignments** tab → click **+Add** → **Add role assignment**.
- Go to the **Roles** tab → Fill in the field:
	- Selected role → *Reader*
- Go to the **Members** tab → Fill in the fields:
	- **Assign access** to → *User, group, or service principal*
	- **Members** → Select the name of a registered application from the previous steps (e.g., *CloudTuner*).
- **Save** to add the role assignment.

3\. Copy **Directory (tenant) ID**. Go to **Home** → **App registrations** → find registration name (*CloudTuner*) → **Overview** → copy **Directory (tenant) ID**.

4\. Create and copy **Secret**. Go to **Home** → **App registrations** → find registration name (e.g. *CloudTuner*) → **Certificates & Secrets** → click **\+ New client secret**.

Attention

Secret's value is hidden shortly after its creation. Make sure to copy it in a safe place.

### Connect to CloudTuner

Go to **CloudTuner** → **Data Sources** → click the **Add** button → select **Azure** → choose the **Tenant** connection type.

![connect_azure_tenant](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/azuretenantcloud.png)

Fill in the **Application (client) ID**, **Directory (tenant) ID**, and **Secret** fields with the data saved on the [Collect the required data](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure#collect-the-required-data-2) step. Click the **Connect** button.

Please contact our Support Team at [contact@cloudtuner.ai](mailto:contact@cloudtuner.ai) if you have any questions regarding the described configuration flow.