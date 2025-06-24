[Skip to content](https://hystax.com/documentation/optscale/#resources-constraints-pool-constraint-policies)

## Resources constraints & Pool constraint policies

To address the ever-dynamic cloud infrastructure where resources are being created and deleted continuously, OptScale introduces a set of tools to help limit the related expenses and the lifetime of individual assets. The following feature is implemented in form of *constraints* that User can set for a specific resource or generally for a Pool.

There are two constraint types that can be set:

- **TTL** - time to live, a resource should not live more than the specified period. For a resource, specify a date and time. For a pool, input an integer between 1 and 720 hours.
- **Daily expenses limit** - resource spendings should not exceed the specified amount in dollars. Input as integer, min $ 1, 0 - unlimited.

When OptScale discovers active resources in the connected source, it checks that they don't violate any existing Pool constraints that were applied as policies before.

When a resource hits a constraint, both manager and owner of the resource are alerted via email. If a resource is unassigned - alerts are sent to the organization managers. On the **Pools** page an exclamation mark will appear next to the pool name.

Note

As of now, OptScale provides solely notifications about violated constraints and does not interact with the connected source itself to perform any constraint-related adjustments.

## Resources constraints

Navigate to the desired asset by selecting the appropriate resource on the **Resources** page.

![resources](https://hystax.com/documentation/optscale/_static/screens/resource_constraints/resources.png)

To assign constraints to resources, go to the **Constraints** tab on the selected resource's page.

On the **Constraints** tab, use the slider to enable/disable the current setting. Click on the image below the constraint's name and fill in the values for **TTL** or the **Daily expense limit** in the fields.

![constraint_resources](https://hystax.com/documentation/optscale/_static/screens/resource_constraints/constraint_resources.png)

If a resource doesn't have a specific constraint set, it inherits the policies from its Pool. However, resource owner or manager can override an existing Pool constraint policy for an individual resource by issuing a custom constraint for any given asset.

## Pool constraint policies

This is a more high-level setting that facilitates the flow in a way that allows implementing policies for entire Pools instead of a single resource. Thus, a manager can enforce all resources in the Pool to share constraints so that they are applied to all resources in this Pool, while custom resource-specific constraints can still exist and yet override the general policy.

Click on **Pools** in the left sidebar and choose a Pool group or its sub Pool.

![constraint_budget](https://hystax.com/documentation/optscale/_static/screens/resource_constraints/constraint_budget.png)

Click on the image next to a constraint's name and fill in the values for **TTL** or the **Daily expense limit** in the empty fields. Use the slider to enable/disable the current setting.

Note

A constraint will not be visible if the related resource has already been deleted from OptScale or if a resource has been tracked only by imported billing data.

## Pool deletion

The Pool structure can be changed by deleting unnecessary Pools via the dedicated section of the main page. This option is not available for Pools that have *sub-Pools* - latter have to be deleted first.

Note

An employee should have the Manager role in the parent of the Pool that they want to delete.

Use button from the *Actions* menu to delete a Pool.

![budget_actions](https://hystax.com/documentation/optscale/_static/screens/resource_constraints/budget_actions.png)

Warning

This action is irreversible. The solution will ask for confirmation before deletion.

![delete_budget](https://hystax.com/documentation/optscale/_static/screens/resource_constraints/delete_budget.png)

When a Pool is deleted:

- all resources are reassigned to its parent Pool;
- all rules that used to point to this Pool are redirected to its root.

![](https://hystax.com/documentation/optscale/images/snipp4.svg)