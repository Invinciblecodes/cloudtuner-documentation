---
title: Quotas and Budgets
---

## Quotas and Budgets

Budgets and quotas are two crucial concepts to consider when managing cloud storage. These tools help organizations control costs and manage resources efficiently.

Budgets in cloud storage refer to the financial limits an organization sets to manage the costs associated with cloud storage usage.

Quotas limit the storage resources a user, application, or department can consume.

This option provides a comprehensive approach to cloud storage management. Leveraging this tool to control cloud storage costs while maximizing the efficiency and availability of their cloud resources.

To set budgets and quotas, go to the **Quotas & Budgets** item in the **Policies** section of the menu.

## Page overview

Go to the **Quotas & Budgets** page to get a brief description of created quotas and budgets. Find its status, description, and available actions.

Use the **Add** button to add a quota or budget. A user with the Organization manager role can perform this action.

![page](https://hystax.com/documentation/optscale/_static/screens/quotas_and_budgets/page.png)

- Below the quota/budget **Name**, the time of the last check is shown. An exclamation mark appears if the restriction is violated. Hover over it to see a hint.
- The **Status** field is a progress bar that displays the current resource count or expense value. The quota itself is shown in the **Description** field. The progress bar's fill level indicates how close the current value is to the set threshold. The color of the progress bar depends on the ratio of the current value to the quota or budget:
	- Red: Warning! The value of resource count or expenses exceeds the quota or budget
	- Yellow: Attention! The value of resource count or expenses is approaching the threshold in the range between 90 and 100%
	- Green: Normal situation. The value doesn't exceed the quota or budget.
- A typical **Description** depends on the type of quota or budget.

| Type of budget | Typical description |
| --- | --- |
| Resource quota | Resource count must not exceed 10 |
| Recurring budget | Current month expenses must not exceed $100 |
| Expiring budget | Total expenses from 01/01/2024 must not exceed $100 |

- The **Filters** field displays the criteria used to select resources for the quota or budget.

Observe the resources connected to the quota or budget. There are two ways to do this:

1\. Go to the **Quotas and Budgets** page → open the **Actions** menu in the table → click the **Show resources** button.

2\. Go to the **Quotas and Budgets** page → click in the quota or budget name → click **Show resources** in the top-right hand corner of the page.

To view detailed information about an item, or to edit or delete it, click on its name. The policy violations history can also be found on this page. A user with the Organization manager role can edit or delete a quota or budget.

If an anomaly occurs, the Organization manager receives a notification email. Click the **Go to CloudTuner** button to be automatically redirected to the solution's **Quotas and Budgets** page.

![alert_an_email](https://hystax.com/documentation/optscale/_static/screens/quotas_and_budgets/alert_an_email.png)

## Add new policy

To create a new policy click **Add** on the **Quotas and Budgets** page.

Note

Only a user with the Organization manager role can add a new policy.

![create_quota_or_budget](https://hystax.com/documentation/optscale/_static/screens/quotas_and_budgets/create_quota_or_budget.png)

Enter the name, select the type of the policy:

- **Resource quota**
	- Set a maximum number of resources
	- Triggers if the current number of resources exceeds the limit
	- One trigger per day
- **Recurring budget**
	- Set a monthly budget
	- Triggers if expenses for the current month exceed the limit
	- One trigger per month
- **Expiring budget**
	- Set the total budget and start date
	- Triggers if total expenses from the start date exceed the limit
	- One trigger

Below the Type field, find a list of available filters that can be set. These filters act as additional criteria for the items retrieved based on the selected policy type. Use them if needed.

![](https://hystax.com/documentation/optscale/images/snipp4.svg)