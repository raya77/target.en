---
keywords: Profile script;profile script attributes;profile script best practices;debug;debugging;scripts;profile scripts;attributes;attribute;parameter
description: Learn about visitor-specific attributes that are stored in the visitor's profile to provide information about that can be used in your Adobe [!DNL Target] activities.
title: What Are Profile Attributes?
feature: Audiences
exl-id: 6c689629-bbd3-461e-9a68-5b16d4eb4250
---
# Profile attributes

Profile attributes in [!DNL Adobe Target] are parameters that are specific to a visitor. These attributes are stored in the visitor's profile to provide information about the visitor that can be used in your activities.

A user profile contains demographic and behavioral information of a web page visitor. This information can include age, gender, products purchased, last time of visit, and so on, that [!DNL Target] uses to personalize the content it serves to the visitor.

As a visitor browses your website, or when the visitor returns for another session, the saved profile attributes in the profile can be used to target content or log information for segment filtering.

To set up profile attributes:

1. Click **[!UICONTROL Audiences]** > **[!UICONTROL Profile Scripts.]**

   ![Profile Scripts tab](/help/main/c-target/c-visitor-profile/assets/create-script.png)

1. Click **[!UICONTROL Create Script]**.

   ![Create Profile Script dialog box](/help/main/c-target/c-visitor-profile/assets/profile-script.png)

   The following types of profile attributes are available:

   | Parameter Type | Description |
   |--- |--- |
   |mbox|Passed in directly through page code when creating the mbox. See [Pass Parameters to a Global Mbox](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/){target=_blank}.<br>**Note**: [!DNL Target] has a limit of 50 unique profile attributes per mbox call. If you must pass more than 50 profile attributes to [!DNL Target], pass them using the Profile Update API method. For more information, see [Profile Update in the [!DNL Adobe Target] API documentation](https://developers.adobetarget.com/api/#updating-profiles).|
   |Profile|Defined directly with a JavaScript code snippet. These snippets can store running totals like total money spent by consumer and are executed on each mbox request. See Profile Script Attributes below.|

## Profile script attributes {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

Define a profile script attribute with its associated JavaScript code snippet.

You can use profile scripts to capture visitor attributes across multiple visits. Profile scripts are code snippets defined within [!DNL Target] using a form of server-side JavaScript. For example, you might use a profile script to capture how frequently a visitor visits your site, and when that visitor last visited.

Profile scripts are not the same as profile parameters. Profile parameters capture information about visitors using the mbox code implementation of [!DNL Target].

## Create profile scripts {#section_CB02F8B97CAF407DA84F7591A7504810}

Profile scripts are available under the [!UICONTROL Audiences] tab in the [!DNL Target] interface.

To add a profile script, click the **[!UICONTROL Profile Scripts]** tab, **[!UICONTROL Create Script]**, then write your script.

Or

To copy an existing profile script, from the [!UICONTROL Profile Scripts] list, click the ellipsis icon for the desired script, then click **[!UICONTROL Duplicate]**.

You can then edit the audience to create a similar audience.

Profile scripts run profile attribute "catchers" on each location request. When a location request is received, [!DNL Target] determines which activity should run and displays content that is appropriate to that activity and that experience. [!DNL Target] also tracks the success of the activity and runs any relevant profile scripts. This process lets you track information about the visit, such as the visitor's location, time of day, number of times that visitor has been to the site, if they've purchased before, and so on. This information is then added to the visitor's profile so you can better track that visitor's activity on your site.

Profile script attributes have the `user.` tag inserted before the attribute name. For example:

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

Keep the following information in mind:

* Refer to profile script attributes (including itself) in the code with `user.get('parameterName')`. 
* Save variables that can be accessed the next time the script is run (on the next mbox request) with `user.setLocal('variable_name', 'value')`. Reference the variable with `user.getLocal('variable_name')`. This process is useful for situations where you want to reference the date and time of the last request.

  These values persist just like a profile script, but you only have access to them within the script they were set.

* Parameters and values are case-sensitive. Match the case of the parameters and values you receive during the activity or test. 
* See the "JavaScript reference for script profile parameters" section below for more JavaScript syntax.
* The parameter remains in the profile after disabling the script. Users whose profiles already contain a parameter that is used in an activity's audience qualify in that activity.
* Profile scripts cannot be deleted while they're being used in an activity.
* Creating dependent profile scripts that use the result of one profile script in another profile script is not recommended. The order of profile script execution is not guaranteed.

## Viewing profile script information cards {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

You can view profile script information pop-up cards similar to offer information cards. These profile script information cards let you view the list of activities that reference the selected profile script, along with other useful metadata.

For example, the following profile script information card is accessed by clicking the [!UICONTROL Info] icon for the desired profile script from the list ([!UICONTROL Audiences] > [!UICONTROL Profile Scripts]).

The [!UICONTROL Script Info] tab contains the following information: Name, Description, and script code.

![Profile Script info card](assets/profile_script_info_card.png)

Click **[!UICONTROL View full details]** to see the audiences and activities that reference the selected profile script.

![Profile Script info card > Script Usage tab](assets/profile_script_info_card_usage_tab.png)

>[!NOTE]
>
>The [!UICONTROL Script Usage] tab does not display activities that reference the selected profile script in the following situations:
>
> * The activity is in the [!UICONTROL Draft] state.
> * The content or offer used in the activity uses script variables (either an inline offer within the activity or an offer within the Offer library).

## Target disables profile scripts in certain situations {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

[!DNL Target] automatically disables profile scripts in certain situations, such as if they take too long to execute or have too many instructions.

When a profile script is disabled, a yellow alert icon displays next to the profile script in the Target UI, as illustrated below:

![profile_script_invalid image](assets/profile_script_invalid.png)

On hover, details on the error display, as illustrated below:

![profile_script_hover image](assets/profile_script_hover.png)

Typical reasons for the system to disable profile scripts include the following:

* An undefined variable to referenced. 
* An invalid value is referenced. This error is often caused by referencing URL values and other user-inputted data without proper validation. 
* Too many JavaScript instructions are used. [!DNL Target] has limit of 2,000 JavaScript instructions per script, but this limit cannot simply be calculated by manually reading the JavaScript. For example, Rhino treats all function calls and "new" calls as 100 instructions. Any call to any function consumes 100 instructions. Also, the size of any entry data, such as URL values, can impact the instructions count. 
* Not following items highlighted in the [best practices](/help/main/c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0) section below.

## Best practices {#best}

The following guidelines are meant to help write simplified profile scripts that are as error-failing-free as possible by writing code that fails gracefully so the scripts are processed without forcing a system-script-halt. These guidelines are a result of best practices that have been proven to run efficiently. These guidelines are to be applied alongside principles and recommendations drawn by the Rhino development community.

* Set current script value to a local variable in the user script, set a failover to a blank string. 
* Validate the local variable by ensuring it is not a blank string. 
* Use string-based manipulation functions vs. Regular Expressions. 
* Use limited for loops vs. open ended for or while loops. 
* Do not exceed 1,300 characters or 50 loop iterations. 
* Do not exceed 2,000 JavaScript instructions. [!DNL Target] has limit of 2,000 JavaScript instructions per script, but this limit cannot simply be calculated by manually reading the JavaScript. For example, Rhino treats all function calls and "new" calls as 100 instructions. Also, the size of any entry data, such as URL values, can impact the instructions count. 
* Be mindful of not only the script performance, but the combined performance of all scripts. As best practice, [!DNL Adobe] recommends fewer than 5,000 instructions in total. Counting the number of instructions is not obvious, but the important thing to note is that scripts exceeding 2,000 instructions are automatically disabled. The number of active profile scripts should not exceed 300. Each script is executed with every single mbox call. Run only as many scripts as needed.
* In a regex, having dot-star in the beginning (for example: `/.*match/`, `/a|.*b/`) is almost never needed. The regex search starts from all positions in a string (unless bound with `^`), so dot-star is already assumed. The script execution can be interrupted if such a regex is matched to a long enough input data (which can be as low as several hundred characters).
* If all fails, wrap script in a try/catch. 
* The following recommendations can help you limit profile script complexity. Profile scripts can execute a limited number of instructions.

  As best practice:

  * Keep profile scripts small and as simple as possible.
  * Avoid regular expressions or use only simple regular expressions. Even simple expressions can take many instructions to evaluate.
  * Avoid recursion.
  * Profile scripts should be performance-tested before being added to [!DNL Target]. All profile scripts execute on every mbox request. If profile scripts do not execute correctly, mbox requests take longer to execute, which can impact traffic and conversion.
  * If profile scripts become too complex, consider using [response tokens](/help/main/administrating-target/response-tokens.md) instead.

* See the JS Rhino engine documentation for more information.

## Debug profile scripts {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

The following methods can be used to debug profile scripts:

>[!NOTE]
>
>Using [!DNL console.log] within a profile script does not output the profile value, because profile scripts execute server-side.

* **Add profile scripts as response tokens to debug profile scripts:**

  In [!DNL Target], click **[!UICONTROL Administration]**, click **[!UICONTROL Response Tokens]**, then enable the profile script you want to debug.

  Anytime you load a page for your site with [!DNL Target] on it, part of the response from [!DNL Target] contains your value for the given profile script, as shown below:

  ![debug_profile_script_1 image](assets/debug_profile_script_1.png)

* **Use the mboxTrace debugging tool to debug profile scripts.**

  This method requires an authorization token that you can generate by clicking **[!UICONTROL Target]** > **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Generate Authorization Token]** in the [!UICONTROL Debugger tools] section.

  You then add these two parameters to your page URL after the "?": `mboxTrace=window&authorization=YOURTOKEN`.

  Adding these parameters is a little more informative than the response token because you get a before-executed snapshot and an after-snapshot of your profile. It also shows all your available profiles.

  ![debug_profile_script_2 image](assets/debug_profile_script_2.png)

## Profile script FAQ {#section_1389497BB6D84FC38958AE43AAA6E712}

**Is it possible to use profile scripts to capture information from a page that resides in a data layer?**

Profile scripts are unable to read the page directly because they are executed server side. The data must be passed in through an mbox request or through other [methods of getting data into Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}. After the data is in [!DNL Target], profile scripts can read the data as an mbox parameter or profile parameter. 

## JavaScript reference for script profile parameters

Simple Javascript knowledge is required to effectively use script profile
parameters. This section serves as a quick reference to make you productive with this functionality in just a few minutes.

Script Profile Parameters are found under the mboxes/profiles tab. You can write Javascript programs that return any Javascript type (string, integer, array, and so forth).

### Script profile parameter examples {#examples}

**Name:** *user.recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

Creates a variable for day as measured in milliseconds. If the mbox name is `orderThankyouPage`, set a local (invisible) user profile attribute named `lastPurchaseTime` to show the value of the current date and time. The value of last purchase time is read, and if defined, [!DNL Target] returns the time that has passed since the last purchase time, divided by the number of milliseconds in a day (which results in the number of days since the last purchase).

**Name:** *user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

Creates a variable called `frequency`, initializing it to either the previous value or 0, if there was no previous value. If the mbox name is `orderThankyouPage`, the incremented value is returned.

**Name:** *user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

Creates a variable called `monetaryValue`, looking up the current value for a given visitor (or set to 0 if there was no previous value). If the mbox name is `orderThankyouPage`, new monetary value is returned by adding the previous one and the value of the `orderTotal` parameter passed to the mbox.

**Name:** adobeQA

```
if (page.param("adobeQA"))
     return page.param("adobeQA");
else if (page.param("adobeqa"))
     return page.param("adobeqa");
else if (mbox.param("adobeQA"))
     return mbox.param("adobeQA");
```

Creates a variable called `adobeQA` to track a user for [Activity QA](/help/main/c-activities/c-activity-qa/activity-qa.md).

### Objects and methods {#objects}

The following objects and methods can be referenced by script profile parameters:

|Object or Method|Details|
| --- | --- |
|`page.url`|The current URL.|
|`page.protocol`|The protocol used for the page (http or https).|
|`page.domain`|The current URL domain (everything before the first slash). For example, `www.acme.com` in `http://www.acme.com/categories/men_jeans?color=blue&size=small`.|
|`page.query`|The query string for the current page. Everything after the ‘?’. For example, `blue&size=small` in `http://www.acme.com/categories/mens_jeans?color=blue&size=small`.|
|`page.param(‘<par_name>’)`|The value of the parameter indicated by `<par_name>`. If your current URL is Google’s search page and you had inputted `page.param('hl')`, you would get “en” for the URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`.|
|`page.referrer`|The same set of operations as above apply for referrer and landing (i.e. referrer.url is the url address of the referrer).|
|`landing.url`, `landing.protocol`, `landing.query`, and `landing.param`|Similar to that of page, but for the landing page.|
|`mbox.name`|The active mbox's name.|
|`mbox.param(‘<par_name>’)`|An mbox parameter by the given name in the active mbox.|
|`profile.get(‘<par_name>’)`|The client-created user profile parameter by the name `<par_name>`. For example, if the user sets a profile parameter named “gender”, the value can be extracted using “profile.gender”. Returns the value of the “`profile.<par_name>`” set for the current visitor; returns null if no value has been set. Note that `profile.get(<par_name>)` is qualified as a function call.|
|`user.get(‘<par_name>’)`|Returns the value of the “`user.<par_name>`” set for the current visitor; returns null if no value has been set.|
|`user.categoryAffinity`|Returns the name of the best category.|
|`user.categoryAffinities`|Returns an array with the best categories.|
|`user.isFirstSession`|Returns true if it's the visitor's first session.|
|`user.browser`|Returns the user-agent in the HTTP header. As an example, you can create an expression target to target Safari users only: `if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }`|

### Common operators


All standard JavaScript operators are present and usable. JavaScript operators can be used on strings and numbers (and other data types). A quick briefing:

|Operator|Description|
| --- | --- |
|`==`|Indicates equality. Holds true when operands on either side are equal.|
|`!=`|Indicates inequality. Holds true when operands on either side are not equal.|
|`<`|Indicates that the variable on the left is less than the variable on the right. Evaluates to false if the variables are equal.|
|`>`|Indicates that the variable on the left is greater than the variable on the right. Evaluates to false if the variables are equal.|
|`<=`|Same as `<` except if the variables are equal then it evaluates to true.|
|`>=`|Same as `>` except if the variables are equal then it evaluates to true.|
|`&&`|Logically “ANDs” the expressions to the left and right of it – is only true when both sides are true (false otherwise).|
|`||`|Logically “ORs” the expressions to the left and right of it – is only true if one of the sides is true (false otherwise).|
|`//`|Checks if source contains all elements from target boolean contains (Array source, Array target).<br>`//` extracts substring from target (corresponding to regexp) and decodes it `Array/*String*/ decode(String encoding, String regexp, String target)`.<br>The feature also supports the use of constant string values, grouping (`condition1 || condition2) && condition3`, and regular expressions (`/[^a-z]$/.test(landing.referring.url)`.|

## Training video: Profile Scripts ![Tutorial badge](/help/main/assets/tutorial.png)

This video includes information about using and creating profile scripts.

* Explain what a profile script is 
* Explain how a profile script is different from a profile parameter 
* Create a simple profile script 
* Use the Available Token menu to access available options 
* Enable and disable profile scripts

>[!VIDEO](https://video.tv.adobe.com/v/17394)
