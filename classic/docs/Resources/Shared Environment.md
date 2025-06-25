---
title: Shared Environments
---

## Shared Environments

CloudTuner Shared Environments provide a signle point to manage your production and test environments. These resources are meant to be acquired for exclusive utilization by an organization member or a team member only temporarily and then released making them available again. The common use cases are release stands and demo environments where the availability of a range of components (e.g. for deploying some software version) has to be controlled in order to eliminate accidental breaking or loss of interconnections.

Depending on your cloud platform, there are two ways to create a Shared Environment in the product:

- if you have a connected Cloud Account, you can easily mark the resources as Shared Environments
- or you can simply add new Shared Environment, not related to any connected Cloud Account, from the **Shared Environments** page.

## Mark existing cloud resources as Shared Environments

At first, when an Organization is added into CloudTuner, the section is empty and new Shared Environments have to be created manually by a user with the Organization Manager role from the scope of *shareable* resources that can only include **Instances** or **CloudTuner clusters**.

To be able to manage your cloud resource as environment, select the resource on the **Resources** page and click **Mark as Shared Environment**.

![mark_environment](https://hystax.com/documentation/optscale/_static/screens/environments/mark_environment.png)

The marked environment will appear on the **Shared Environments** page. The resource is now available for booking, and you can proceed with using webhooks and integrating with your CI/CD.

## Create new Shared Environment

To create a new Environment in CloudTuner select **Shared Environments** at the left sidebar of the main page and click **Add**.

![add_environment](https://hystax.com/documentation/optscale/_static/screens/environments/add_environment.png)

You will be prompted to input a **Name** and a **Resource type**, set if SSH access is required, specify additional properties for a new Shared Environment. Dy defauls, the solution requests to add the Description, IP, and Software. Use the **Add Property** button in case if you want to add extra properties.

![create_env](https://hystax.com/documentation/optscale/_static/screens/environments/create_env.png)

A newly created entity will be added to this section and listed in a table providing information about a **Pool** that it belongs to, its **Status** which can be *In use*, *Available*, or *Unavailable*, **Upcoming bookings**, related **Software** and **Jira tickets** (optional).

![list_env](https://hystax.com/documentation/optscale/_static/screens/environments/list_env.png)

## Action buttons

The following action buttons allow to control an existing environment:

\- a Shared Environment can be booked for a selected period of time.

![book_menu](https://hystax.com/documentation/optscale/_static/screens/environments/book_menu.png)

\- a booked Shared Environment can be released to make it available again. A notification will be sent to the corresponding tenant user.

\- a scope of resources can be deactivated temporarily to prohibit it from being booked.

\- deletion of the Shared Environment.

Detailed instructions on [how to organize access to shared resources using CloudTuner](https://hystax.com/how-to-organize-access-to-shared-resources-using-optscale/) find on our website.
