---
keywords: Targeting;target categories;target conditions;audience manager;custom profile parameters;visitor profile;custom user parameters;target rules
description: Learn how to use categories (such as Browser, Geo, Network, Operating System, Visitor Profile) to target content.
title: What Are the Categories for Audiences?
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
---
# Categories for audiences

You can target on any of several category attributes using [!DNL Adobe Target]. To create targeting rules (or groups) for each attribute, drag and drop the desired attributes into the Audience Builder pane.

![Attributes for audiences](/help/main/c-target/c-audiences/assets/attributes.png)

When a particular category is selected, you can apply one or more targeting conditions. For example, in the Geo category, define a rule like City=San Francisco. Adding multiple values creates an OR condition. The visitor has to match only one of the values to meet the targeting condition. For AND conditions on the same parameter, create a custom expression target.

After you have created a rule, click **[!UICONTROL Done]**. A summary of the rule displays next to the targeting link for the level you are targeting.

You can further refine a rule by adding more conditions or by creating additional rules in other categories. For example, you can target only Firefox users from San Francisco who access your site from Google. Set the [!UICONTROL Geo] category to target users from San Francisco, the [!UICONTROL Browser] category to target users using Firefox, and the [!UICONTROL Traffic Sources] category to target users coming from [!UICONTROL From Google]. The rules created across categories are combined with the AND operator. 

To create complex targeting rules that include OR operations across categories, create an expression target.

You can also target custom profile parameters and `user.` parameters. When adding an audience, drag and drop **[!UICONTROL Visitor Profile]**, then choose the parameter you use want to use to target your activity. If the desired parameter does not display, the parameter has not been fired by an mbox.

Use the search box to search your [!UICONTROL Audiences] list. You can search for any part of an audience name, or you can enclose a specific string in quotes.

You can sort the [!UICONTROL Audience] list by audience name or by the date when it was last modified. To sort by name or date, click the column header, then select to display audiences in ascending or descending order.

## Training video: Creating Audiences ![Tutorial badge](/help/main/assets/tutorial.png)

This video includes information about using audience categories.

* Create audiences 
* Define audience categories

>[!VIDEO](https://video.tv.adobe.com/v/17392)
