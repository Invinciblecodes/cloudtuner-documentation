<!-- ---
title: Carbon Emission
--- -->

# Carbon Emission Monitoring - User Guide

## Overview

The Carbon Emission feature helps you track and monitor the environmental impact of your cloud infrastructure. By measuring CO₂ emissions from your cloud resources, you can make informed decisions to reduce your carbon footprint and contribute to sustainability goals.

![Carbon Emission Dashboard](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/carbonemissiondashboard.png)

---

## Key Features

### 1. **Total Emissions Overview**

View your total carbon emissions across all cloud resources in a single glance. The dashboard displays:

- **Total Emissions**: Measured in kilograms of CO₂ equivalent (kgCO2e)
- **Trees Saved**: Number of trees needed to offset your emissions
- **Smartphones Charged**: Equivalent number of smartphone charges
- **Flights Saved**: Equivalent flights (Delhi-Mumbai route)

![Summary Cards](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/totalemission.png)

### 2. **Visual Emission Trends**

Track your carbon emissions over time with an interactive bar chart that shows daily emission patterns. This helps you:

- Identify emission spikes
- Monitor reduction efforts
- Understand usage patterns

![Emission Trends Chart](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/visualtrends.png)

### 3. **Detailed Resource Breakdown**

Get granular insights into which resources are contributing most to your carbon footprint. The table shows:

- Resource name and ID
- CO₂ emissions per resource
- Power consumption in watts
- Cloud provider
- Resource type

![Resource Breakdown Table](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/resourcebreakdowntable.png)

---

## Getting Started

### Accessing the Carbon Emission Dashboard

1. Navigate to the Carbon Emission section from the main menu
2. The dashboard will load with data for the current month by default

![Navigation Menu](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/cotwosidebar.png)

---

## Using the Dashboard

### Filtering by Date Range

To view emissions for a specific time period:

1. Click on the **Date Range Picker** in the top-right corner
2. Select your desired start and end dates
3. Click **Apply** to update the dashboard

![Date Range Picker](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/daterange.png)

**Tip**: Use predefined ranges like "Last 7 Days", "Last 30 Days", or "This Month" for quick filtering.

---

### Filtering by Cloud Account

To view emissions for a specific cloud account:

1. Click on the **Cloud Account** dropdown
2. Select a specific account or choose "Overall" to view all accounts
3. The dashboard will automatically update

![Cloud Account Filter](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/cloudaccounts.png)

---

### Viewing by Summary Type

You can view emissions grouped by different resource types:

1. Click on the **Summary by** dropdown
2. Select your preferred grouping:
   - **Instance**: View emissions by compute instances
   - **Storage**: View emissions by storage resources (coming soon)

![Summary Type Filter](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/summaryby.png)

---

## Understanding the Metrics

### Total Emissions (kgCO2e)

This represents the total carbon dioxide equivalent emitted by your cloud resources during the selected period. Lower values indicate better environmental performance.

### Trees Saved

**Calculation**: Total CO₂ (kg) ÷ 21 kg absorbed per tree annually

This metric shows how many trees would be needed to absorb the CO₂ emissions from your cloud infrastructure over one year.

### Smartphones Charged

**Calculation**: Total CO₂ (kg) ÷ 0.005 kg per smartphone charge

This relatable metric helps you understand your emissions in terms of everyday activities.

### Flights Saved (Delhi-Mumbai)

**Calculation**: Total CO₂ (kg) ÷ 135 kg per Delhi-Mumbai flight

This shows the equivalent number of domestic flights your emissions represent.

---

## Resource Details

### Viewing Individual Resource Emissions

To see detailed information about a specific resource:

1. Locate the resource in the summary table
2. Click on the **resource name** (underlined)
3. You'll be taken to a detailed view showing:
   - Historical emission trends for that resource
   - Power consumption patterns
   - Resource specifications

![Resource Detail View](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/resourcemanagementbreakdown.png)

---

## Carbon Calculator

The Carbon Calculator helps you estimate potential emissions for planned infrastructure changes.

### Using the Carbon Calculator

1. Click the **Carbon Calculator** button in the top-right corner
2. Enter your resource specifications:
   - Cloud provider
   - Resource type
   - Region
   - Usage hours
3. View the estimated CO₂ emissions
4. Use this information to make informed decisions about resource provisioning

![Carbon Calculator](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/carboncalculator.png)

---

## Table Features

### Pagination

Navigate through large datasets using the pagination controls at the bottom of the table:

- **Rows per page**: Choose to display 20, 50, or 100 rows
- **Page navigation**: Use arrow buttons to move between pages
- **Total records**: View the total number of resources

![Pagination Controls](https://cloudtuner-email-templates-image.s3.eu-north-1.amazonaws.com/documentation/pagination.png)

### Sorting and Filtering

The table displays the following information for each resource:

- **Name**: Resource identifier
- **Resource ID**: Unique cloud resource ID
- **CO₂ Emission**: Total emissions in grams of CO₂ equivalent (gCO2e)
- **Power Consumed**: Power usage in watts
- **Cloud Provider**: AWS, GCP, or Azure (shown with icons)
- **Resource Type**: Service category (e.g., Elasticsearch, EC2, etc.)

---

## Best Practices

### 1. Regular Monitoring

- Check your emissions dashboard weekly to identify trends
- Set up alerts for unusual emission spikes (coming soon)

### 2. Identify High-Impact Resources

- Sort resources by CO₂ emission to find the biggest contributors
- Focus optimization efforts on high-emission resources

### 3. Compare Time Periods

- Use the date range picker to compare emissions across different periods
- Track the impact of optimization efforts

### 4. Use the Carbon Calculator

- Estimate emissions before provisioning new resources
- Choose regions and resource types with lower carbon intensity

### 5. Account-Level Analysis

- Filter by cloud account to understand emissions per project or team
- Allocate carbon budgets to different accounts

---

## Tips for Reducing Carbon Emissions

1. **Right-size your resources**: Avoid over-provisioning compute and storage
2. **Use auto-scaling**: Scale resources based on actual demand
3. **Choose green regions**: Select cloud regions powered by renewable energy
4. **Optimize workloads**: Improve application efficiency to reduce resource usage
5. **Schedule non-critical workloads**: Run batch jobs during off-peak hours
6. **Implement resource lifecycle policies**: Automatically shut down unused resources

---

## Frequently Asked Questions

### How is CO₂ emission calculated?

Emissions are calculated based on:

- Resource power consumption
- Cloud provider's energy mix
- Region-specific carbon intensity
- Usage duration

### Why do emissions vary by region?

Different regions have different energy sources. Regions powered by renewable energy have lower carbon intensity than those using fossil fuels.

### Can I export emission data?

Export functionality is coming soon. You can currently view and analyze data within the dashboard.

### How often is data updated?

Emission data is updated daily and reflects resource usage from the previous day.

### What cloud providers are supported?

Currently supported:

- Amazon Web Services (AWS)
- Google Cloud Platform (GCP)
- Microsoft Azure

---

## Support

If you have questions or need assistance with the Carbon Emission feature:

- Contact support at: [contact@cloudtuner.ai](mailto:contact@cloudtuner.ai)
- Schedule a demo: [dashboard.cloudtuner.ai](https://dashboard.cloudtuner.ai)

---

## What's Coming Next

We're continuously improving the Carbon Emission feature. Upcoming enhancements include:

- Storage resource emissions tracking
- Custom emission alerts and notifications
- Emission reduction recommendations
- Carbon budget management
- Detailed emission reports and exports
- Integration with sustainability reporting frameworks

---
