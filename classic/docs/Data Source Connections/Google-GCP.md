---
title: Google Cloud - GCP
---
## Google Cloud project

Before connecting, enable billing export, prepare a role for CloudTuner, create service account, and generate API key. If this has not been completed, refer to the [Configure the project](https://hystax.com/documentation/optscale/e2e_guides/e2e_gcp.html#configure-the-project) section before proceeding to [Connect to CloudTuner](https://hystax.com/documentation/optscale/e2e_guides/e2e_gcp.html#connect-to-optscale).

### Configure the project

Make some preparations steps before connect a new GCP data source in CloudTuner, go to the **GCP** cloud.

1\. **Enable Billing export**. Official documentation - [Set up Cloud Billing data export to BigQuery | Google Cloud](https://cloud.google.com/billing/docs/how-to/export-data-bigquery-setup).

As the result you have a new table in your BigQuery project. Note the names of the dataset and the table.

2\. **Prepare a role for CloudTuner**. There are two ways, select one:

- Run the following command in GCP CLI:
	```js
	gcloud iam roles create
	optscale_connection_role \--project=hystaxcom
	\--permissions=bigquery.jobs.create, bigquery.tables.getData, compute.addresses.list, 
	compute.addresses.setLabels, compute.disks.list, compute.disks.setLabels, compute.firewalls.list, 
	compute.globalAddresses.list, compute.instances.list, compute.instances.setLabels, compute.images.list, 
	compute.images.setLabels, compute.machineTypes.get, compute.machineTypes.list, compute.networks.list, 
	compute.regions.list, compute.snapshots.list, compute.snapshots.setLabels, compute.zones.list, 
	iam.serviceAccounts.list, monitoring.timeSeries.list, storage.buckets.get, storage.buckets.getIamPolicy, 
	storage.buckets.list, storage.buckets.update
	```
- Via Google Cloud console
	1\. Go to [Roles page](https://console.cloud.google.com/iam-admin/roles) and click **Create Role**.
	2\. Give the role any name and description.
	3\. Add the following permissions:
	- bigquery.jobs.create
	- bigquery.tables.getData
	- compute.addresses.list
	- compute.addresses.setLabels
	- compute.disks.list
	- compute.disks.setLabels
	- compute.firewalls.list
	- compute.globalAddresses.list
	- compute.instances.list
	- compute.instances.setLabels
	- compute.images.list
	- compute.images.setLabels
	- compute.machineTypes.get
	- compute.machineTypes.list
	- compute.networks.list
	- compute.regions.list
	- compute.snapshots.list
	- compute.snapshots.setLabels
	- compute.zones.list
	- iam.serviceAccounts.list
	- monitoring.timeSeries.list
	- storage.buckets.get
	- storage.buckets.getIamPolicy
	- storage.buckets.list
	- storage.buckets.update

4\. **Create service account**. Official documentation - [Service accounts | IAM Documentation | Google Cloud](https://cloud.google.com/iam/docs/service-accounts). Specify the role that you've created earlier and click **Continue** and then **Done**

5\. **Generate API key** for your service account. Official documentation - [Create a service account key | IAM Documentation | Google Cloud](https://cloud.google.com/iam/docs/keys-create-delete#creating). Download it as a.json file. It is required on the stage of connection to CloudTuner.

### Connect to CloudTuner

Go to **CloudTuner** → **Data Sources** → click the **Add** button → select **GCP** → choose the **Project** connection type.

![gcp_connection_form](https://hystax.com/documentation/optscale/_static/screens/onboarding/gcp/gcp_connection_form.png)

Fill in the fields, download a API key file. Click the **Connect** button.

Please contact our Support Team at [support@hystax.com](https://hystax.com/documentation/optscale/e2e_guides/) if you have any questions regarding the described configuration flow.

## Google Cloud tenant

Before connecting, prepare a role for CloudTuner, create service account, and generate API key. If this has not been completed, refer to the [Configure the project](https://hystax.com/documentation/optscale/e2e_guides/e2e_gcp.html#configure-the-tenant) section before proceeding to [Connect to CloudTuner](https://hystax.com/documentation/optscale/e2e_guides/e2e_gcp.html#connect-to-optscale_1).

### Configure the tenant

Make some preparations steps before connect a new GCP data source in CloudTuner, go to the **GCP** cloud.

1\. **Prepare a role for CloudTuner**. There are two ways, select one:

- Run the following command in GCP CLI:
	```js
	gcloud iam roles create
	optscale_connection_role \--project=hystaxcom
	\--permissions=bigquery.jobs.create, bigquery.tables.getData, compute.addresses.list, 
	compute.addresses.setLabels, compute.disks.list, compute.disks.setLabels, compute.firewalls.list, 
	compute.globalAddresses.list, compute.instances.list, compute.instances.setLabels, compute.images.list, 
	compute.images.setLabels, compute.machineTypes.get, compute.machineTypes.list, compute.networks.list, 
	compute.regions.list, compute.snapshots.list, compute.snapshots.setLabels, compute.zones.list, 
	iam.serviceAccounts.list, monitoring.timeSeries.list, storage.buckets.get, storage.buckets.getIamPolicy, 
	storage.buckets.list, storage.buckets.update
	```
- Via Google Cloud console
	1\. Go to [Roles page](https://console.cloud.google.com/iam-admin/roles) and click **Create Role**.
	2\. Give the role any name and description.
	3\. Add the following permissions:
	- bigquery.jobs.create
	- bigquery.tables.getData
	- compute.addresses.list
	- compute.addresses.setLabels
	- compute.disks.list
	- compute.disks.setLabels
	- compute.firewalls.list
	- compute.globalAddresses.list
	- compute.instances.list
	- compute.instances.setLabels
	- compute.images.list
	- compute.images.setLabels
	- compute.machineTypes.get
	- compute.machineTypes.list
	- compute.networks.list
	- compute.regions.list
	- compute.snapshots.list
	- compute.snapshots.setLabels
	- compute.zones.list
	- iam.serviceAccounts.list
	- monitoring.timeSeries.list
	- storage.buckets.get
	- storage.buckets.getIamPolicy
	- storage.buckets.list
	- storage.buckets.update

2\. **Create service account**. Official documentation - [Service accounts | IAM Documentation | Google Cloud](https://cloud.google.com/iam/docs/service-accounts). Specify the role that you've created earlier and click **Continue** and then **Done**.

3\. **Grant access**. For each project that needs to be added to the tenant, go to the **IAM & Admin** section in the Google Cloud Console, select **IAM**, and press the **GRANT ACCESS** button. Add the created service account and assign the created role to it.

4\. **Generate API key** for your service account. Official documentation - [Create a service account key | IAM Documentation | Google Cloud](https://cloud.google.com/iam/docs/keys-create-delete#creating). Download it as a.json file. It is required on the stage of connection to CloudTuner.

### Connect to CloudTuner

Go to **CloudTuner** → **Data Sources** → click the **Add** button → select **GCP** → choose the **Tenant** connection type.

![connect_gcp_tenant](https://hystax.com/documentation/optscale/_static/screens/onboarding/connect_gcp_tenant.png)

Fill in the fields, upload a API key file. Click the **Connect** button.

Please contact our Support Team at [support@hystax.com](https://hystax.com/documentation/optscale/e2e_guides/) if you have any questions regarding the described configuration flow.

