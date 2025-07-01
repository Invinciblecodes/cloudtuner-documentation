---
title: Kubernetes
---

## Kubernetes

To track a new **Kubernetes** cluster Data Source in your CloudTuner account, please select the Kubernetes tab on the **Data Source Connection** page.

![connect_kubernetes](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/kubernetesdataconnection.png)

| Field | Description |
| --- | --- |
| Name | Specify any preferred name to be used for this data source in CloudTuner. |
| User | Specify a user for the cost metrics collector to use when pushing data to this data source. |
| Password | Specify a password for the cost metrics collector to use when pushing data to this data source. |

Use **Connect** to create a Data Source in CloudTuner.

Click on the newly created Data Source on the **Data Sources** page. The page with detailed information appears.

![kubernetes_clickon](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/kubernetescloudaccounts.png)

Use **KUBERNETES INTEGRATION** or **instructions** to get the instructions to install the software that collects information about running pods and converts them into cost metrics.

![kubernetes_instuctions](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/kubernetescloudaccountdetails.png)

## Software installation on a cluster

To get cost metrics download and install helm chart on the Kubernetes cluster. Helm chart is created to collect Kubernetes resources information and share it with CloudTuner FinOps project. Install one release per cluster.

<!-- ### 1\. Download Hystax repo

Use this command to download repo:

```js
helm repo add hystax https://hystax.github.io/helm-charts
``` -->

###  Install Helm Chart

There is a difference in instructions when a Kubernetes Data Source is connected on cloudtuner.ai or on CloudTuner deployed from open source. In both cases, instructions given are adapted for a selected Data Source and deployed CloudTuner. All you need is just to copy-paste it and replace the < **password\_specified\_during\_data\_source\_connection** > phrase with a user's password.

#### cloudtuner.ai

![kubernetes_chart_installation_prod](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/instructionskubernetes.png)

![kubernetes_chart_installation_prod](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/commandkubernets.png)

 **Note:**  
 Specify the user's password in place of `<password_specified_during_data_source_connection>`.
 
 **⚠️ Warning:**  
 Please wait for the metric generation process to complete. This typically takes **approximately one hour**.


![](https://hystax.com/documentation/optscale/e2e_guides/images/snipp4.svg)