---
title: Resource constraints and Pool constraints

---

## Resource Assignment

Strong resource assignment improves efficiency, reduces costs, enhances accountability, and helps projects stay on track, all of which contribute to higher overall success rates in organizational and project management contexts.

Newly created resources are distributed among pools based on assignment rules. If they have certain tags, they will immediately be assigned to the appropriate pool as soon as they are first discovered. If they do not belong to any pool, they will be assigned to the Data Source pool. The Data Source pool is created when the Data Source is connected.

CloudTuner allows you to manage assignment rules by viewing, creating, editing, and changing their priority.

## Assignment Rules Table

Go to the **Pools** page and click on the **Configure Assignment Rules** button.

![poolspage](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/resourceassignmentpools.png)

**Assignment Rules** is a centralized interface for viewing and managing all existing assignment rules in the system. This page provides a list of rules displayed in a tabular format for easy navigation and interaction. Users can view the status of each rule and take appropriate actions directly from this page.

![assignment_rules](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/resourceassignmentrules.png)

All assignment rules are displayed in a table, allowing easy browsing and management. The general actions **Add** and **Re-apply Ruleset** are placed above the table. Search functionality is available based on criteria such as *Name*, *Assigned to*, *Conditions*, and *Priority*. For ease of navigation, the page supports pagination, allowing to view assignment rules in manageable chunks. All data columns are sortable.

Each row represents a specific rule and includes details such as:

- a descriptive **name** for the rule,
- the pool and owner to whom the resource is **assigned**,
- a summary of the **conditions** that trigger the rule,
- the **priority** used to apply assignment rules to resources,
- **actions**.

Use the **Actions** column buttons to manage rules:

\- *prioritize* - sets the rule priority to the highest. The priority of the other rules will be decreased by one

![promote](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/promote.png)  - *promote* - increases rule priority by 1. The rule will be swapped with the previous rule.

![demote](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/demote.png) - *demote* - decreases rule priority by 1. The rule will be swapped with the rule behind it.

![deprioritize](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/deprioritize.png) - *deprioritize* - assigns a rule with the lowest priority across the given organization. All other affected rules will be updated.

![edit](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/edit.png) - *edit* - allows modification of an existing rule. Adjust conditions and assignment details, ensuring that the rule remains accurate and up to date with changing requirements. A rule can be enabled/disabled by ticking the **Active** checkbox. Active rules are marked with green dots next to their names, inactive ones are marked with grey dots.

![delete](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/delete.png) - *delete* - removes the rule from the list.

Note

CloudTuner will assign newly detected resources automatically according to the rules listed above. Rules are evaluated according to the priority. You can also force re-apply them for the whole organization or a specific pool if you need to reflect allocation policies changes immediately.

## Add Assignment Rule

There are two ways to add an Assignment Rule: through the **Assignment Rules** page or the **Resource** page. On the **Resource** page, you get a specialized version of the **Add Automatic Resource Assignment Rule Form** with pre-filled fields based on your resource information.

### Assignment Rules page

The **Add Automatic Resource Assignment Rule Form** is used to define new assignment rules for automatic resource allocation based on specified conditions. The form is divided into sections to collect relevant information for creating an assignment rule, including the rule's name, status, conditions, and assignment targets.

![add_rule](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/resourceassignmentaddnew.png)

The list of available **Conditions**:

| Type | Key/Value | Description |
| --- | --- | --- |
| Name/ID starts with | string value | Matches resources where the name or ID begins with the specified value. |
| Name/ID ends with | string value | Matches resources where the name or ID ends with the specified value. |
| Name/ID is | string value | Matches resources with an exact name or ID match. |
| Name/ID contains | string value | Matches resources where the name or ID contains the specified substring. |
| Tag is | key-value pair | Matches resources with a tag that matches both the specified key and value. |
| Tag exists | key-value pair | Matches resources that have a tag with the specified key. |
| Tag value starts with | key-value pair | Matches resources with a tag value starting with the specified value for the given key. |
| Source is | selected row | Matches resources from a selected data source. Options are presented in a dropdown for selecting the source. |
| Resource type is | string value | Matches resources where the resource type contains the specified value. |
| Region is | string value | Matches resources where the region contains the specified value. |

Input a **Name** for the new automatic resource assignment rule as well as the **Conditions** that have to be fulfilled in order for the rule to become applicable. Add and remove conditions to suit your needs. As the result, a matching resource will be included into the selected **Target Pool** and assigned to an **Owner**.

A newly created rule is always prioritized across the organization and is put at the top of the list for the discovered resources to be checked against its conditions first. If these are not satisfied, a resource will be checked against the remaining rules in descending order until one is found applicable.

### Resources page

This form is a specialized version of the **Add Automatic Resource Assignment Rule Form** from the [**Assignment Rules** page](https://docs.cloudtuner.ai/Resources/Resource%20Assignment#assignment-rules-page). The page is accessible by clicking the **Add Assignment Rule** button directly from a specific resource's details page.

![add_rule_resources](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/resourceassignmentresourcepage.png)

Its purpose is to simplify the creation of assignment rules for a particular resource by pre-filling relevant fields with the resource's existing data.

![add_rule_resources](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/addassignmentrules.png)

Add **Conditions** according your needs, specify a *Name*, *Target Pool*, and *Owner*.

## Re-apply Ruleset

\- **Re-apply Ruleset** - initiates a new check of the already assigned resources against the current ruleset. Resources will be reorganized accordingly even if they were explicitly assigned otherwise before. This feature helps manage assignments, especially when rules are edited, new ones are added, or the priority of existing rules is changed.

Note

The re-check process takes some time.

To start the process, click the **Re-apply Rules** button. A side modal opens.

![reapply_ruleset](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/reapplyruleset.png)

Select whether you want to re-apply to the entire organization or a specific pool. In the second selection, specify a pool and, if necessary, enable the **With sub-pools** checkbox. The **Run** button starts the process and closes the modal, while the request continues to run in the background. The **Cancel** button simply closes the modal without performing any actions.

Note

Re-apply options are available if the user has Organization Manager or Root Pool Manager permissions.

This feature provides quick access to the assignment rules that apply specifically to a given pool. It helps users understand how resources are being assigned and managed within the pool, ensuring transparency and simplifying rule verification and modification by centralizing relevant rules in one place.

To find a list of assignment rules associated with the selected pool, open the detailed page of the desired pool from the **Pools** page.

![reapply_ruleset](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/poolrelatedassignmentrules.png)

Each rule entry includes the *Name*, *Owner*, and *Conditions* of the rule, providing a clear overview of the rule configurations.

The *Conditions* column offers a detailed summary of the conditions defined for each rule, including condition types such as *Name/ID contains*, *Tag is*, or *Source is*.

Click the **See all assignment rules** link at the bottom of the section to navigate to the main assignment rules listing page, where all rules across different pools can be managed.

## Resources constraints & Pool constraint policies

To address the ever-dynamic cloud infrastructure where resources are being created and deleted continuously, CloudTuner introduces a set of tools to help limit the related expenses and the lifetime of individual assets. The following feature is implemented in form of *constraints* that User can set for a specific resource or generally for a Pool.

There are two constraint types that can be set:

- **TTL** - time to live, a resource should not live more than the specified period. For a resource, specify a date and time. For a pool, input an integer between 1 and 720 hours.
- **Daily expenses limit** - resource spendings should not exceed the specified amount in dollars. Input as integer, min $ 1, 0 - unlimited.

When CloudTuner discovers active resources in the connected source, it checks that they don't violate any existing Pool constraints that were applied as policies before.

When a resource hits a constraint, both manager and owner of the resource are alerted via email. If a resource is unassigned - alerts are sent to the organization managers. On the **Pools** page an exclamation mark will appear next to the pool name.

Note

As of now, CloudTuner provides solely notifications about violated constraints and does not interact with the connected source itself to perform any constraint-related adjustments.

## Resources constraints

Navigate to the desired asset by selecting the appropriate resource on the **Resources** page.

![resources](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/resources.png)

To assign constraints to resources, go to the **Constraints** tab on the selected resource's page.

On the **Constraints** tab, use the slider to enable/disable the current setting. Click on the image below the constraint's name and fill in the values for **TTL** or the **Daily expense limit** in the fields.

![constraint_resources](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/constraints.png)

If a resource doesn't have a specific constraint set, it inherits the policies from its Pool. However, resource owner or manager can override an existing Pool constraint policy for an individual resource by issuing a custom constraint for any given asset.

## Pool constraint policies

This is a more high-level setting that facilitates the flow in a way that allows implementing policies for entire Pools instead of a single resource. Thus, a manager can enforce all resources in the Pool to share constraints so that they are applied to all resources in this Pool, while custom resource-specific constraints can still exist and yet override the general policy.

Click on **Pools** in the left sidebar and choose a Pool group or its sub Pool.

![constraint_budget](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/constraints.png)
Click on the image next to a constraint's name and fill in the values for **TTL** or the **Daily expense limit** in the empty fields. Use the slider to enable/disable the current setting.

Note

A constraint will not be visible if the related resource has already been deleted from CloudTuner or if a resource has been tracked only by imported billing data.

## Pool deletion

The Pool structure can be changed by deleting unnecessary Pools via the dedicated section of the main page. This option is not available for Pools that have *sub-Pools* - latter have to be deleted first.

Note

An employee should have the Manager role in the parent of the Pool that they want to delete.

Use button from the *Actions* menu to delete a Pool.

![budget_actions](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/deletepools.png)

Warning

This action is irreversible. The solution will ask for confirmation before deletion.

![delete_budget](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/deletepool.png)

When a Pool is deleted:

- all resources are reassigned to its parent Pool;
- all rules that used to point to this Pool are redirected to its root.

