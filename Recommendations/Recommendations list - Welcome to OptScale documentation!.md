[Skip to content](https://hystax.com/documentation/optscale/#recommendations-list)

### IAM users with unused console access

The following active IAM users have console access turned on but have not been using it for more than **90 days**. Consider revoking console access to increase security.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Inactive IAM users

The following IAM users are inactive for more than **90 days**. Consider their deletion.

The number of days is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Instances with insecure Security Groups settings

Some active instances have attached Security Groups with inbound ports that considered insecure. Consider changing Security Groups, restricting these ports only to a specific IP range to increase security.

Insecure ports and permissions:

- port tcp/22
- port tcp/3389
- all inbound traffic

with one of:

- CidrIp: 0.0.0.0/0
- CidrIpv6:::/0

**AWS**

- Describe regions: *ec2.describe\_regions()*
- Describe instances: *ec2.describe\_instances()*
- Describe security groups: *ec2.describe\_security\_groups()*

**Azure**

- Describe instances: *compute.virtual\_machines.list\_all()*
- Describe security groups: *network.network\_security\_groups.list\_all()*

**GCP**

- Describe instance tags, find firewalls applied to each instance, and save firewall IDs to `meta->security_groups` (tags are used to apply firewalls to instances):  
	`compute_service.list(compute.ListInstancesRequest, zone_id)`
- Describe firewalls:  
	`firewall_service.list(compute.ListFirewallsRequest, project_id)`

Note

- Firewalls in GCP are equivalent to **security groups**.
- Firewalls are associated with **networks**.
- A firewall can be applied to **all VMs** in a network or to **VMs with specific tags** in the network.
- **Disabled firewalls** are excluded from recommendations.
- Firewalls that use **service accounts** or **tags** as sources are excluded from recommendations because these limit the number of allowed IPs.
- The **default firewall rules** include a rule that denies all ingress traffic. Therefore, resource recommendations only consider firewalls with **'allow'** rules.

Note

Network interfaces without associated security groups are skipped.

The list of insecure SGs can be downloaded in the json format for subsequent automated processing.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Public S3 buckets

The S3 buckets in the list are public. Please ensure that the buckets use the correct policies and are not publicly accessible unless explicitly required.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Abandoned Amazon S3 buckets

Some of your active Amazon S3 buckets have been detected as abandoned (average data size has been less than **1024** megabytes, Tier1 requests quantity has been less than **100**, and GET requests quantity has been less than **2000** for the last **7 days**). Consider their deletion to reduce expenses.

The parameters in **bold** are custom parameters. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change them.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Abandoned Images

Some images have not been used for volume creation for the last **7 days**. Consider their deletion to reduce expenses.

The parameters in **bold** are custom parameters. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change them.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Abandoned Instances

Some of your active instances have been detected as abandoned (average CPU consumption is less than **5%** and network traffic below **1000** bytes/s for the last **7 days**). Consider their termination to reduce expenses.

The parameters in **bold** are custom parameters. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change them.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Abandoned Kinesis Streams

The following Kinesis Streams have provisioned Shard capacity but have not performed data operations for the last **7 days**. Consider their removal to reduce expenses.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Abandoned Load Balancers

Some of your active load balancers have been detected as abandoned (average bytes sent is less than **0**, average packets sent is less than **0**, and average requests is less than **0** for the last **7 days**). Consider their termination to reduce expenses.

The parameters in **bold** are custom parameters. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change them.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Instances eligible for generation upgrade

Instances with old generation are eligible for upgrade to the newest generation of the same family.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Instances for shutdown

Some of your instances have an inactivity pattern which allows you to set up an on/off power schedule (average CPU consumption is less than **5%** and network traffic below **1000** bytes/s for the last **14 days**). Consider creating a power schedule to reduce expenses.

The parameters in **bold** are custom parameters. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change them.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Instances with migration opportunities

Some of your active instances can cost less with the same size in another geographically closer region. Consider their migration to the recommended region to reduce expenses.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Instances with Spot (Preemptible) opportunities

Some of the instances you have been running for the last **3 days** have existed for less than **6 hours** and were not created as Spot (or Preemptible) Instances. Consider using Spot (Preemptible) Instances.

The parameters in **bold** are custom parameters. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change them.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

Some of your active instances have been detected as sustainable (for more than **90 days**) compute consumers but have not been covered with Subscription or Saving Plans. Consider purchasing Subscriptions to save on compute usage.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources with detailed information in JSON or XLSX formats](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file).

### Not attached volumes

Some of the detached volumes have not been attached for more than **1 day**. Consider their deletion to reduce expenses.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

[Download the script](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-script) for subsequent automated processing using the [Cleanup Scripts](https://hystax.com/documentation/optscale/cleanupscripts.html).

### Not deallocated Instances

Some of your stopped but not deallocated instances have not been running for more than **1 day**. Such instances are still billed by the cloud. Please consider their deletion or deallocation.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

[Download the script](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-script) for subsequent automated processing using the [Cleanup Scripts](https://hystax.com/documentation/optscale/cleanupscripts.html).

### Obsolete Images

Some AMIs have not been used for instance creation for the last **7 days**. Consider their deletion to unlock underlying snapshots.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

[Download the script](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-script) for subsequent automated processing using the [Cleanup Scripts](https://hystax.com/documentation/optscale/cleanupscripts.html).

### Obsolete IPs

Some IPs have not been used the last **7 days**. Consider their deletion to reduce expenses.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Obsolete Snapshot Chains

Some snapshot chains do not have source volumes, images created from their snapshots and have not been used for volume creation for the last **3 days**. Consider their deletion to save on snapshot storage expenses.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

[Download the script](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-script) for subsequent automated processing using the [Cleanup Scripts](https://hystax.com/documentation/optscale/cleanupscripts.html).

### Obsolete Snapshots

Some snapshots have not been used for the last **3 days**. Consider their deletion to save on snapshot storage expenses.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

[Download the script](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-script) for subsequent automated processing using the [Cleanup Scripts](https://hystax.com/documentation/optscale/cleanupscripts.html).

### Reserved Instances opportunities

Some of your active instances have been detected as sustainable (for more than **90 days**) compute consumers but have not been covered with Reserved Instances or Saving Plans. Consider purchasing Reserved Instances to save on compute usage. Check **RI/SP Coverage** to see the detailed breakdown of current reservations.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

### Underutilized instances

Some of your active instances are detected as underutilized and can be downsized to reach your rightsizing strategy goal (have **99% quantile** CPU consumption less than **80%** for the last **3 days**). Consider switching to the recommended size from the same family to reduce expenses.

The parameter in **bold** is a custom parameter. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change it.

[Download the list of resources](https://hystax.com/documentation/optscale/optscales_recommendations.html#download-jsonxlsx-file) with detailed information in JSON or XLSX formats.

### Underutilized RDS Instances

Some of your active RDS instances are detected as underutilized and can be downsized to reach your rightsizing strategy goal (have **99% quantile** CPU consumption less than **80%** for the last **3 days**). Consider switching to the recommended size from the same family to reduce expenses.

The parameters in **bold** are custom parameters. Use [settings](https://hystax.com/documentation/optscale/optscales_recommendations.html#settings) to change them.

![](https://hystax.com/documentation/optscale/images/snipp4.svg)