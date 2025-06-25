---
title: Clean-up Scripts
---

## Clean-up Scripts

Below are the instructions on how to use the clean-up scripts found in the **Recommendations** section.

Note

The script will attempt to delete all resources that are recommended for deletion (based on the downloadable json file) and will not fail on errors. Upon its completion, a summary will be generated containing a list of deleted resources, a list of non-existing (already deleted) resources and a list of resources that could not be deleted due to other reasons.

## Alibaba

### Requirements

1. **Aliyun**. [Installation guide](https://www.alibabacloud.com/help/en/cli/install-cli-on-linux?spm=a2c63.p38356.0.0.540c20e0EjR2dd).
2. **jq** - the package allows executing json scripts with bash. [Download page](https://stedolan.github.io/jq/download/).

### Action plan

1\. Install the requirements on a machine running Linux OS.

2\. Sign in [aliyun](https://www.alibabacloud.com/help/en/cli/configure-credentials?spm=a2c63.p38356.0.0.358b6be5UJWDO2):

```js
aliyun configure --mode AK --profile test
Configuring profile 'test' in 'AK' authenticate mode...
Access Key Id []: 
Access Key Secret []: 
Default Region Id []: ap-southeast-1
Default Output Format [json]: json (Only support json)
Default Language [zh|en] en: en
Saving profile[test] ...Done.
Configure Done!!!
..............888888888888888888888 ........=8888888888888888888D=..............
...........88888888888888888888888 ..........D8888888888888888888888I...........
.........,8888888888888ZI: ...........................=Z88D8888888888D..........
.........+88888888 ..........................................88888888D..........
.........+88888888 .......Welcome to use Alibaba Cloud.......O8888888D..........
.........+88888888 ............. ************* ..............O8888888D..........
.........+88888888 .... Command Line Interface(Reloaded) ....O8888888D..........
.........+88888888...........................................88888888D..........
..........D888888888888DO+. ..........................?ND888888888888D..........
...........O8888888888888888888888...........D8888888888888888888888=...........
............ .:D8888888888888888888.........78888888888888888888O ..............
```

3\. Configure timeouts:

```js
aliyun configure set --read-timeout 20  --connect-timeout 20 --retry-count 3
```

4\. Run script bash `<script_name>` `<path to recommendation json file>`.

5\. Run script on Alibaba shell:

- Open console → [Online Linux Shell](https://shell.alibabacloud.com/?spm=5176.12818093.resource-links.dcli.551c12d2L3gIYR).
- Copy script and recomendation json file via the **Upload/Download files** button.
- Run script as follows: **bash `<script_name>` `<path to recommendation json file>`**. Use absolute paths or perform *cd* before execution.

## AWS Source

### Requirements

1. **AWS cli v2**. [Official Amazon User Guide](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html).
2. **jq** - the package allows executing json scripts with bash. [Download page from the developer](https://stedolan.github.io/jq/download/).

### Action plan

1\. Install the requirements on a machine running Linux OS.

2\. Configure the AWS Command Line Interface. (Run the **aws configure** command. For more info, please refer to the following section of the [AWS User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html))

3\. Download the script from the corresponding subsection of the CloudTuner's **Recommendations** page.

![script_download](https://hystax.com/documentation/optscale/_static/screens/optscales_recommendations/script_download.png)

4\. From the same page, download the json file containing a list of all resources that are recommended for deletion.

5\. Run the script as follows: **bash `<script_name>` `<path to json file>`**

## Azure Source

### Requirements

1. **Azure cli**. [Official Microsoft User Guide](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt).
2. **jq** - the package allows executing json scripts with bash. [Download page](https://stedolan.github.io/jq/download/).

### Action plan

1. Install the requirements on a machine running Linux OS.
2. Sign in with the Azure cli.
3. Download the script from the corresponding subsection of the CloudTuner's **Recommendations** page.
4. From the same page, download the json file containing a list of all resources that are recommended for deletion.
5. Run the script as follows: **bash `<script_name>` `<path to json file>`**.

### Action plan when using Azure Shell

1. Open [Azure shell](https://portal.azure.com/#cloudshell/).
2. Download the script and the json file from the corresponding subsection of the CloudTuner's **Recommendations** page.
3. Copy these files via the **Upload/Download files** button. The files will be placed in **/usr/csuser/clouddrive**.
4. Run the script as follows: **bash `<script_name>` `<path to json file>`** using absolute paths or navigate to the necessary folder before executing.

## GCP Source

### Requirements

1. **Gcloud cli**. [gcloud CLI overview](https://cloud.google.com/sdk/gcloud).
2. **jq** - the package allows executing json scripts with bash. [Download page](https://stedolan.github.io/jq/download/).

### Action plan

1\. Install requirements on a machine running Linux OS.

2\. Configure gcloud: run gcloud init. [See more info](https://cloud.google.com/sdk/docs/initializing).

3\. Run script bash `<script_name>` `<path to recommendation json file>`.

![](https://hystax.com/documentation/optscale/images/snipp4.svg)