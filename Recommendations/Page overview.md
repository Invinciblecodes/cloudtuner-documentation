[Skip to content](https://hystax.com/documentation/optscale/#optscales-recommendations)

OptScale features a set of automated tools for ongoing optimization of registered Data Sources. The section is intended to help maintain awareness of the less apparent deficiencies of the infrastructure like configuration flaws and security risks.

## Filter

There are two types of recommendations that are featured in OptScale: savings, security. Additionally, there is an option to view critical, non-empty, and all recommendations. Refine the recommendations using the Categories filter if necessary. By default, all recommendations are displayed.

![categories](https://hystax.com/documentation/optscale/_static/screens/optscales_recommendations/categories.png)

In addition to filtering by categories, the page allows selection of Data Sources and Applicable services.

## Summary cards

### Description

Use Summary Cards to get an at-a-glance overview of important details, such as total expenses, check time, savings, duplicates found, etc.

This icon shows that you can click on the Summary Card to get detailed information.

![summary_cards](https://hystax.com/documentation/optscale/_static/screens/optscales_recommendations/summary_cards.png)

### Color schema

Pay special attention to the color schema of the page.

A color indicates a critical situation, signaling that you should focus on the card and its information.

A color signifies that there are no recommendations or that potential savings are zero.

A color appears when there are items requiring attention.

In all other situations, the card is white.

Detailed instructions on [how to use recommendation cards](https://hystax.com/how-to-use-recommendation-cards-in-optscale/) find on our web-site.

All cards have the same structure. Let’s look at the structure of the card using ‘Obsolete Images’ as an example:

![card_structure](https://hystax.com/documentation/optscale/_static/screens/optscales_recommendations/card_structure.png)

Name, applicable services, description, and total possible savings (or total count of items) are to inform you. A list of items with maximum savings, a list of all items, and actions are clickable.

Click the item in the list with maximum savings to view detailed information. To view all items, click the See all items link.

The ‘Actions’ menu differs depending on the card. Download a cleanup script or a JSON/XLSX file with a list of recommendations. Each recommendation can be pinned to the top of the list (max is 5). Recommendations are configurable. Open a menu by clicking the ellipsis. Each menu item has a tooltip; use it to get detailed information.

### Download script

Use to download the script for a specific data source and run it against a downloaded JSON file with the recommendation data.

The option is not available for all cards.

### Download JSON/XLSX file

Use to download the list of items in the json/xlsx format.

The option is not available for all cards.

### Settings

Adjusting parameters is beneficial as it allows for fine-tuning and optimizing results to better meet specific goals or conditions. The set of parameters varies depending on the card, so set the values according to your needs.

Note

New settings will be applied on the next recommendations check.

![settings](https://hystax.com/documentation/optscale/_static/screens/optscales_recommendations/settings.png)

![](https://hystax.com/documentation/optscale/images/snipp4.svg)