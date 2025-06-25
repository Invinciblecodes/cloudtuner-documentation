[Skip to content](https://hystax.com/documentation/optscale/#anomaly-detection)

## Anomaly Detection

Anomaly detection in cloud technology is essential to ensuring cloud services’ security, reliability, and performance. Cloud computing environments are complex and often consist of many interconnected components and services, making them vulnerable to various operational and security-related issues. Anomaly detection in this context aims to identify unusual behavior that could indicate a security breach, system malfunction, or other operational challenges.

OptScale keeps up with the times. The OptScale team implemented the anomaly detection algorithms in the solution. This feature is an integral part of a broader cloud security and management strategy, helping our clients preemptively address potential issues before they cause significant damage or disruption. Cloud anomaly detection is crucial for maintaining the integrity and performance of cloud services.

## Page overview

To utilize anomaly detection policies find the **Anomaly Detection** page in the **Policies** section.

![main_page](https://hystax.com/documentation/optscale/_static/screens/anomaly_detection/main_page.png)

The table on this page gives information about all created anomalies under specified policies. Track the dynamic in the status column. On hover, view the average and current values. The description reminds us of the policy. The filters field shows the instances in which this policy is available. “-” in the filter means the policy is available for all cases.

The policy is clickable. Use this feature to get general information, the date of violation, status, average, and actual counts for easy comparison and a quick assessment of the situation. Resources can be accessed through the **Actions** menu. **Edit** and **Delete** buttons are also here. A user with the Organization manager role can edit or delete a policy.

Warning

Pay special attention: deleted policies cannot be restored.

![policy_view](https://hystax.com/documentation/optscale/_static/screens/anomaly_detection/page_overview.png)

If an anomaly occurs, the Organization manager receives a notification email. Click the **Go to OptScale** button to be automatically redirected to the solution’s **Anomaly Detection** page.

![policy_view](https://hystax.com/documentation/optscale/_static/screens/anomaly_detection/alert_in_email.png)

## Add new policy

To create a new policy click **Add** on the **Anomaly Detection** page.

Note

Only a user with the Organization manager role can add a new policy.

Enter a name and select the type of policy. There are two types of policies:

- *resource count*. The rule for the *resource count* is that the daily resource count must not exceed the average amount for the last Evaluation period days on the Threshold percentage.
- *expenses*. The rule for the *expense* type of policy is that OptScale shows red if everyday expenses expand the average sum for the last Evaluation period days on the Threshold percentage.

When the type is selected, the **Evaluation period** and **Threshold** fields appear.

![policy_view](https://hystax.com/documentation/optscale/_static/screens/anomaly_detection/evaluation_period_threshold.png)

Below these fields a list of filters is available. Set if necessary and Save.

![](https://hystax.com/documentation/optscale/images/snipp4.svg)