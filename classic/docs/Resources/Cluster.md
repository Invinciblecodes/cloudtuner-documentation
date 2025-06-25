---
title: Clusters
---
## Clusters

Oftentimes a set of cloud resources that serve a common purpose can be viewed as a single entity from the user perspective. In many cases, resources are not intended to run independently and are created/terminated simultaneously while sharing an attribute like tag value that connects them together. Such groups of resources can be merged into **clusters** making them stand-alone virtual resources in CloudTuner for better management options.

Sub-resources are added into clusters automatically based on **cluster type** definitions that are created by the user with the Organization Manager role.

To set up a new cluster, go to the **Configure cluster types** on the right-hand corner of the **Resources** page and click the **Add** button on the **Cluster Types** page.

![main_cluster](https://hystax.com/documentation/optscale/_static/screens/clusters/main_cluster.png)

Please define new cluster type name (will be used as the type of created cluster resources) and clusterization tag key. Once created, this cluster type will be applied to newly discovered resources. Existing resources can be clusterized using the **Re-apply cluster types** action.

A definition consists of the following two parameters:

- **cluster type name** - must be unique within the organization.
- **tag key** - a common parameter to be used for consolidating sub-resources.

![add_cluster](https://hystax.com/documentation/optscale/_static/screens/clusters/add_cluster.png)

Cluster type definitions are automatically applied to resources upon their discovery in CloudTuner (through billing or direct discovery) for consolidation even before any existing assignment rules take effect.

The list of cluster types is prioritized to avoid any conflicts. A new cluster type is placed at the bottom of the list so it does not affect existing clusters and can be prioritized manually later on.

Clicking on the **Re-apply cluster types** button triggers a new resource allocation sequence that uses the current order of cluster types as a rule.

A cluster type can be deleted from the same page. Upon deletion, all clusters of this type are disassembled as well.

In the Resources section, items that are part of a cluster are marked with thesymbol to distinguish them among usual resources.

![cluster_icon](https://hystax.com/documentation/optscale/_static/screens/clusters/cluster_icon.png)

Clicking on their names will bring up the **Cluster Details** page that lists all included sub-resources, their total expenses, and constraints that are applied throughout the cluster.

Note

When a resource becomes part of a cluster, it can no longer be reassigned separately or receive an individual constraint in CloudTuner.

