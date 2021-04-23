---
keywords: troubleshooting;frequently asked questions;FAQ;FAQs;targets;audiences
description: View frequently asked questions (FAQs) about experience targeting and audiences used in Adobe [!DNL Target] activities.
title: Where Can I Find Questions and Answers about Targets and Audiences?
feature: Audiences
exl-id: f829bd4a-852a-4eb1-85d1-89e74c14b37e
---
# Targets and audiences FAQ

List of frequently asked questions (FAQs) about experience targeting and audiences.

## How does [!DNL Target] evaluate URLs in targeting? {#url}

Target evaluates URLs differently depending on whether you use audience URL targeting while creating an activity or whether you use URL targeting while creating an audience.

Consider the following URL:

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### Audience URL targeting

To apply audience URL targeting, while creating an activity, on the Experiences page (step one of the three-step guided workflow), click the gear icon, click Page Delivery, then specify the desired URL.

![Page Delivery URL](/help/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

Audience URL targeting looks for an exact URL match. If the URL matches, Target does not consider further logic. In the above URL, if the activity is set to fire on `www.example.com`, the URL matches for the following URLs because audience URL targeting is query agnostic:

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

Beyond audience targeting on the URL, you can also specify specific values that can be in the query.

### URL targeting

To apply URL targeting, while creating an audience, click Add Rule, click Site Pages, select an option from the first drop-down list (Current Page, Previous Page, or Landing Page), select URL from the second drop-down list, specify an evaluator, then specify the desired URL.

![Site Pages > Current Page > URL](/help/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

URL targeting transforms the URL into a set of rules to evaluate:

* URL domain = `example.com`
* Path = path1/path2/path3
* queryStringParam1 =  test123
* queryStringParam2 =  test7

## When creating complex URL strings, does [!DNL Target] evaluate the entire URL?

If you use the same parameter name more than once in a URL string, HTTP considers the first parameter name and ignores subsequent parameters with the same name.

For example, in the following URL string:

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

the first instance of the `Category` parameter is evaluated and the second `Category` parameter is ignored.

Best practice is to have multiple values associated with a single category, as shown below:

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## When building audiences, why are pre-built audiences under [!DNL Target] Library found under other categories? {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

The pre-built audiences in the Target Library category are legacy audiences and exist in other categories. As an example, the legacy Target Library > New Visitors audience has an updated counterpart: Visitor Profile > New Visitor.

Best practice is to use the newer audiences because they have improved performance. Some customers might be using legacy, pre-built audiences, so they have not been removed from the Target interface.

## How do I know how traffic will be split between audiences? {#section_067EEFB956E7465CBF77EC86834470AB}

By default, traffic is split evenly between experiences. However, you can specify percentage targets for each experience. In this case, a random number is generated and that number is used to choose the experience to display. The resulting percentages might not exactly match the specified targets, but more traffic means that the experiences should be split closer to the target goals.

## Which experience displays if a user qualifies for an activity that contains multiple experiences with multiple qualifying audiences? {#section_94A60B11212D48FD8AB0803C6C7E7253}

The user qualifies for the first experience/audience that displays on the activity's [!UICONTROL Target] page.

For example, in the following illustration, a user from California using a Windows device qualifies for both Experience A (Windows audience) and Experience C (California audience). This user would be shown Experience A because it displays in the list above Experience C on the Targets page.

![](assets/audiences_order.png)

## Why do names for the same audience in [!DNL Target] , Adobe Audience Manager (AAM), and the Audience Library in core services differ? {#section_F67E61A607B6444C8DAA4F99C3E95AED}

Audience names in [!DNL Target] are unique; however, in [!DNL AAM] and the [!DNL Audience Library], you can have the same name for multiple audiences (if they are in different folders).When [!DNL Target] encounters an audience name that corresponds to an [!DNL AAM] or [!DNL Audience Library] audience, [!DNL Target] appends "#&lt;number&gt;" to the name.

For example, you might see the following audiences: "PC Users" (in [!DNL AAM]) and "PC Users #1" (in [!DNL Target]).

## Why can't I rename an audience? {#section_54E420556F534D20836E261E253D8B97}

Some Target audiences are predefined, such as "New Visitors" and "Returning Visitors." These predefined audiences cannot be renamed by users.

## Why are all profile parameters not showing in the [!DNL Target] user interface? {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] has a limit of 50 unique profile attributes per mbox call. If you need to pass more than 50 profile attributes to [!DNL Target], you can pass them using the [!UICONTROL Profile Update] API method. For more information, see [Profile Update](https://developers.adobetarget.com/api/#authentication-tokens) in the Adobe Target API documentation.

## Why are visitors seeing experiences for an AP activity that they shouldn't see? {#section_41CECEAE0881446A8D9F3B016857914B}

Automated Personalization activities are evaluated once per session. If there were active sessions that have qualified for a particular experience and now new offers have been added to it, users will see the new content along with the previously shown offers. Because they have previously qualified for those experiences, they would still see them for the duration of the session. If there's a desire to evaluate this at every single page visit, you should change to the Experience Targeting (XT) activity type.

## Why are changes made to audiences created via API not reflected in the [!DNL Target] UI? {#section_6BEB237CAC004A06A290F9644E5BF0FB}

Unlike offers and profile scripts, changes made by API to audiences created via Target Standard are not currently synced back to the Target UI.

## Strings that represent numbers (floating point numbers are supported as well) are compared as numbers.{#strings-that-represent-numbers}

If the left and the right part of the equals expressions can be parsed to a number, the two parts are compared as numbers, not as strings.

For example:

|Value|Targeting Criteria|Result|
| --- | --- | --- |
|1.0|equals 1|true|
|1|equalsIgnoreCase 1.0|true|
|1.230|equals 1|true|
|1.500|equals 1.5|true|
|1.200|is less than 2|true|
|2|is greater than 3.0|false|
|045|equals 45|true|

Numbers written in scientific notation will always be compared as strings.

For example,

"4e-2" will only equal "4e-2". It will *not* equal "0.04".
