---
title: Tagging Policies
---

## Tagging Policies

To create, manage and monitor tagging policies go to the **Tagging** item in the **Policies** section of the menu. The search box helps to quickly locate specific policies. Ensure that all resources are tagged correctly to enable cost tracking by team, project, or department. Poorly tagged or untagged resources are harder to manage and optimize financially.

## Page overview

Go to the **Tagging Policies** page to get a brief description of existing policies. Find its status, description, filters, and available actions.

Use the **Add** button to add a new policy. Only a user with the Organization manager role can perform this action.

![page](https://hystax.com/documentation/optscale/_static/screens/tagging_policies/page.png)

- Below the policy **Name**, the time of the last check is shown. An exclamation mark appears if the restriction is violated. Hover over it to see a hint.
- The **Status** field displays the current state of the policy:
	- Indicates that resources violating the tagging rules have been identified.
	- Shows that all resources covered by the policy currently meet its tagging rules.
	- No status information yet means that the policy is newly created and hasn't run an evaluation cycle, or the filters may exclude all current resources, resulting in no data to check.
- A **Description** field informs about the rule's scope, type, and enforcement timeline.
- A **Filter** fiels indicates which specific resources the rule targets.
- An **Actions** column gives quick access to manage policies directly from the table.

If a policy violates, the Organization manager receives a notification email. Click the **Go to CloudTuner** button to be automatically redirected to the solution's **Tagging Policies** page.

![alert_an_email](https://hystax.com/documentation/optscale/_static/screens/tagging_policies/alert_an_email.png)

## Add new policy

To create a new policy click **Add** on the **Tagging Policies** page.

Note

Only a user with the Organization manager role can add a new policy.

![create_tagging_policy](https://hystax.com/documentation/optscale/_static/screens/tagging_policies/create_tagging_policy.png)

Enter the name, specify start date. Use the tagging rules tabs to enforce that certain tags must be present on selected resources. Select one of the following:

- **Required tag** (default) and specify tags that must be present.
- **Prohibited tag** and specify tags that should not be present.
- **Tags correlation** and enforce logical relationships between tags: specify primary and correlated tag.

Use filters to apply stricter tagging rules to specific data sources, pools, owners, etc.

![](https://hystax.com/documentation/optscale/images/snipp4.svg)