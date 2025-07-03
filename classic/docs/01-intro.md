---
title: Welcome to CloudTuner
slug: /
---

# Welcome to CloudTuner

## About CloudTuner

CloudTuner is a platform that optimizes cloud costs and performance for any workload, providing effective cloud cost management for all types of organizations.

![main](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/dashboard.png)

## CloudTuner primary capabilities

- **Pool Transparency**
	Pool breakdown and transparency across all business units, users, projects and individual cloud services. The customer sets soft and hard limits.
- **Simple multicloud asset provisioning workflow via dashboard or API**
	A single CloudTuner dashboard is used to manage hybrid clouds along with the virtual machines, volumes and network settings. Custom and mandatory tagging is supported. Custom TTL rules can be created to clear out workloads according to customer's policies.
- **Flexible alerts and notifications**
	Custom notifications about all related events, e.g. immediate workload volume increase, pool forecast overdraft or unusual behavior.
- **Swift user creation and business units distribution**
	Step-by-step guides for configuring user settings, organization subdivisions, pools and quotas assignments.
- **VM Power Schedules**
	The Power Schedule feature for cloud instances enables users to automate the management of virtual machine (VM) states by scheduling their start and stop times.
- **Optimal utilization of Reserved Instances, Savings Plans, and Spot Instances**
	A visualization of your compute usage covered by RIs and SPs versus your uncovered usage. By analyzing this data, you can identify potential savings by increasing your RI/SP coverage where beneficial.
- **S3 duplicate object finder**
	The S3 Duplicate Finder is designed to help optimize your AWS S3 storage usage by identifying and managing duplicate objects across your buckets.

More features are just around the corner and will be introduced shortly!

## How it works

CloudTuner is dedicated to improve cloud usage experience but does not actively interfere with processes in your environment since it only requires **Read-Only** rights for the connected cloud account which is used as the main Data Source for all recommendations.

The following data is used:

1. Billing info - all details related to cloud expenses.
2. State of resources (for actively discoverable types) in the cloud - necessary for applying **Constraints** like TTL and Expense limit as well as for CloudTuner's **Recommendation Engine**.
3. Monitoring data from the cloud used for identifying underutilized instances.

Naturally, every cloud platform differs in the way the above data is obtained.

### Alibaba

1\. Billing information is acquired via **Billing API**:

- [https://www.alibabacloud.com/help/en/boa/latest/api-bssopenapi-2017-12-14-describeinstancebill](https://www.alibabacloud.com/help/en/boa/latest/api-bssopenapi-2017-12-14-describeinstancebill)
- [https://www.alibabacloud.com/help/en/boa/latest/api-bssopenapi-2017-12-14-queryuseromsdata](https://www.alibabacloud.com/help/en/boa/latest/api-bssopenapi-2017-12-14-queryuseromsdata)
- [https://www.alibabacloud.com/help/en/boa/latest/api-bssopenapi-2017-12-14-querybilloverview](https://www.alibabacloud.com/help/en/boa/latest/api-bssopenapi-2017-12-14-querybilloverview)

2\. Cloud's **Monitor** service is used as the source of all monitoring data.

3\. Resource discovery is performed via **Discovery API**:

- [https://www.alibabacloud.com/help/en/ecs/developer-reference/api-ecs-2014-05-26-describeinstances](https://www.alibabacloud.com/help/en/ecs/developer-reference/api-ecs-2014-05-26-describeinstances)
- [https://www.alibabacloud.com/help/en/ecs/developer-reference/api-ecs-2014-05-26-describedisks](https://www.alibabacloud.com/help/en/ecs/developer-reference/api-ecs-2014-05-26-describedisks)
- [https://www.alibabacloud.com/help/en/rds/developer-reference/api-rds-2014-08-15-describedbinstances](https://www.alibabacloud.com/help/en/rds/developer-reference/api-rds-2014-08-15-describedbinstances)
- [https://www.alibabacloud.com/help/en/eip/developer-reference/api-vpc-2016-04-28-describeeipaddresses-eips](https://www.alibabacloud.com/help/en/eip/developer-reference/api-vpc-2016-04-28-describeeipaddresses-eips)

<!-- Refer to [this guide](https://hystax.com/documentation/optscale/e2e_guides/e2e_alibaba.html#connecting-an-alibaba-account-to-optscale) for more details. -->

### Amazon Web Services (AWS)

1\. Billing information is retrieved from the Data Exports located in a designated S3 bucket in the cloud:

- [https://docs.aws.amazon.com/AmazonS3/latest/API/API_GetObject.html](https://docs.aws.amazon.com/AmazonS3/latest/API/API_GetObject.html)

2\. Resource discovery is performed via **Discovery API**:

- [https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeInstances.html](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeInstances.html)
- [https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeVolumes.html](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeVolumes.html)
- [https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeSnapshots.html](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeSnapshots.html)
- [https://docs.aws.amazon.com/AmazonS3/latest/API/API_ListBuckets.html](https://docs.aws.amazon.com/AmazonS3/latest/API/API_ListBuckets.html)

3\. **Amazon Cloud Watch** is used as the source of monitoring data.

Refer to [this guide](https://docs.cloudtuner.ai/Data%20Source%20Connections/Amazon-AWS#configure-policies-and-user) for more details.

### Azure

1\. Billing information is acquired via **Billing API**:

- [https://docs.microsoft.com/en-us/rest/api/consumption/usage-details/list](https://docs.microsoft.com/en-us/rest/api/consumption/usage-details/list)

2\. Resource discovery is performed via **Discovery API**:

- [https://docs.microsoft.com/en-us/rest/api/compute/virtual-machines/list-all](https://docs.microsoft.com/en-us/rest/api/compute/virtual-machines/list-all)
- [https://docs.microsoft.com/en-us/rest/api/compute/disks/list](https://docs.microsoft.com/en-us/rest/api/compute/disks/list)
- [https://docs.microsoft.com/en-us/rest/api/compute/snapshots/list](https://docs.microsoft.com/en-us/rest/api/compute/snapshots/list)
- [https://docs.microsoft.com/en-us/rest/api/storagerp/storage-accounts/list](https://docs.microsoft.com/en-us/rest/api/storagerp/storage-accounts/list)

3\. Cloud's **Monitoring service** is used as the source of all monitoring data.

Refer to [this guide](https://docs.cloudtuner.ai/Data%20Source%20Connections/Microsoft-Azure/#connect-to-cloudtuner) for more details.

### GCP

1\. Billing information is retrieved from the **BigQuery** service.

2\. Cloud's **Monitoring** service is used as the source of all monitoring data.

3\. Resource discovery is performed via **Discovery API**:

- [https://cloud.google.com/compute/docs/reference/rest/v1/instances/list](https://cloud.google.com/compute/docs/reference/rest/v1/instances/list)
- [https://cloud.google.com/compute/docs/reference/rest/v1/disks/list](https://cloud.google.com/compute/docs/reference/rest/v1/disks/list)
- [https://cloud.google.com/compute/docs/reference/rest/v1/snapshots/list](https://cloud.google.com/compute/docs/reference/rest/v1/snapshots/list)
- [https://cloud.google.com/storage/docs/json_api/v1/buckets/list](https://cloud.google.com/storage/docs/json_api/v1/buckets/list)
- [https://cloud.google.com/compute/docs/reference/rest/v1/addresses/list](https://cloud.google.com/compute/docs/reference/rest/v1/addresses/list)

Refer to [this guide](https://docs.cloudtuner.ai/Data%20Source%20Connections/Google-GCP) for more details.

### Kubernetes

To enable cost management and FinOps capabilities for your Kubernetes cluster, you need to deploy a software component that collects information about running pods and converts it into cost metrics. Refer to [this guide](https://docs.cloudtuner.ai/Data%20Source%20Connections/Kubernetes) for more details.

This software is open-source, free of malware, and requires read-only access to Kubernetes metadata and performance metrics. 

<!-- Please review the code and find a detailed description on [GitHub](https://github.com/hystax/helm-charts/tree/main/charts/kube-cost-metrics-collector). -->

![menu](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/sidebar.png)

- **Home**. Find your organization's current spending and projected expenses for the upcoming month. Details about [Home page](https://docs.cloudtuner.ai/Home%20Page).
- **Recommendations**. Get practical information about suggesting services and features available in CloudTuner. Find a brief description and other pertinent information in the cards to help you assess the situation quickly. [How to use recommendations](https://docs.cloudtuner.ai/Recommendations/Page-overview).
- **Resources**. Observe the expenses for all resources across all connected clouds within the organization for the selected period. Organize and categorize resources based on your specific requirements.
- **Pools**. View pools with limits or projected expenses that require your attention. Manage pools using the available features on this page.
- **Shared Environments**. This feature enables you to focus more on application logic rather than infrastructure management. Use this page to book cloud environments for specific periods to allow multiple users or applications to access and use the same underlying infrastructure.

![menu_therest](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/sidebartabs.png)

- **FinOps**. View a breakdown chart that visualizes your expenses over time, get a visual or analytical representation of costs, and become familiar with the concepts of FinOps.
- **Policies**. Identify and respond to unusual patterns or deviations from normal behavior, control costs and manage resources efficiently, implement robust tagging policies, and manage the resource lifecycle and automated power on/off schedules effectively.
- **Sandbox**. Evaluate CPU and memory usage by k8s resources, view applied recommendations, and compare instance pricing across different clouds.
- **System**. Assign roles to users for resource management, integrate with various services, view events, and manage [email notifications](https://docs.cloudtuner.ai/System-Settings/Settings).

## Organization selector

![organization_field](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/dashboard.png)

In case there are several organizations registered in CloudTuner that the user is considered to be a part of, clicking on the **Organization** field → **Organization overview** in the top right corner of the page will redirected to a new view containing a matrix of key information on each organization.

Organizations that require attention and optimization are marked in red.

![organization_overview](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/organizationsoverview.png)

On the right of the Organization selector find the **Documentation**, and **Product tour**