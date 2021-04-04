---
keywords: css selector;custom code;code editor;Mobile Web Experience Editor
description: Learn how to use the Modifications panel in Adobe Target to view page modifications and to add additional modifications (CSS Selector, Mbox, and Custom Code).
title: What Modifications Can I Make to My Page?
feature: Visual Experience Composer (VEC)
exl-id: 23456a4b-9457-4f05-989e-a7c39ce17cc2
---
# Modifications{#modifications}

Information about the Modifications page in [!DNL Adobe Target] that lets you view modifications to your page and add additional modifications (CSS Selector, Mbox, and Custom Code).

The Modifications page shows all changes that have been made to your page in the Visual Experience Composer (VEC) and lets you make additional changes by clicking each element on the page and [selecting an action](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81). Each change you make appears as a separate action or element in the [!UICONTROL Modifications] list. You can also add modifications, including the following modification types: CSS Selector, Mbox. and Custom Code.

## Modifications Overview {#section_EE27E7572AA74397BBDED563B2B3D509}

The [!UICONTROL Modifications] page shows all changes that have been made to your page in the VEC. Each change you make appears as a separate action or element in the [!UICONTROL Modifications] list.

![](assets/codeeditor_page_mods.png)

Use the Modifications page to make small changes to the selector that Target chooses when you use the VEC to configure how content is delivered. You can change either the content or an HTML attribute. You can also edit the code to create the equivalent of an HTML offer within an mbox.

Use the Modifications page to:

* View an action taken in the visual composer.

  ![](assets/codeeditor_viewchange.png)

* Edit an existing action. Hover over the desired modification, then click the **[!UICONTROL Edit]** icon.

  ![](assets/codeeditor_edit.png)

  Make your changes.

  ![](assets/codeeditor_changechange1.png)

* Delete an existing action. Hover over the desired modification, then click the **[!UICONTROL Delete]** icon.

  ![](assets/codeditor_delete.png)

* Add a new modification. Click **[!UICONTROL Add Modification]** or the + icon, then specify your changes as described below.

  ![](assets/codeeditor_new.png)

  Note that after one modification is created, Target displays a + icon at the top of the Modifications panel instead of the Add Modification button at the bottom of the panel. 

* Dock the Modifications panel vertically along the side of the Target UI or horizontally at the bottom. Click the [!UICONTROL Dock] icon to toggle between the two settings.

  ![](assets/codeditor_dock.png)

  The following illustration shows the Modifications panel docked at the bottom of the screen:

  ![](assets/codeeditor_dock_bottom.png)

## Add Modifications {#section_C7ABCD5731A048CB8F90EDC31A32EDF9}

1. To display the [!UICONTROL Modifications] page for a selected experience, in the VEC, click the **[!UICONTROL Modifications]** </> icon.

   ![](assets/codeeditor_icon_big.png)

   >[!NOTE]
   >
   >To open the Modifications panel in the Form-based Experience Composer, create or edit an HTML offer. For more information, see [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E).

   The [!UICONTROL Modifications] page opens, splitting the screen between the visual mode on the left and the Modifications panel on the right. Click the [!UICONTROL Dock] icon to dock the Modifications panel vertically along the side of the Target UI or horizontally at the bottom. Notice that Experience A in the following illustration has no previous modifications.

   ![](assets/codeeditor_page.png)

   Experience B shows the previous modifications in the [!UICONTROL Modifications] panel on the right.

   ![](assets/codeeditor_page_mods.png)

1. To add a modification:

    * If no previous modifications for the experience have been made, click the **[!UICONTROL Add Modification]** button at the bottom of the [!UICONTROL Modifications] panel on the right side. 
    * If there are previous modifications for the experience, click the + icon at the top of the [!UICONTROL Modifications] panel on the right side.

   The Modifications panel displays:

   ![](assets/codeeditor_page_mods_add.png)

1. From the **[!UICONTROL Modifications Type]** drop-down list, choose the desired type:

    | Modifications Type | Details |
    |--- |--- |
    |CSS Selector|In the CSS Element Selector box, specify the desired CSS element that you want to modify, select an action type ( Set Content or Set Attribute), then fill in the required information and the desired content.|
    |Mbox|Specify the Mbox name and the desired content.|
    |Custom Code|Specify an optional name, select or deselect the [!UICONTROL Add Code in the `<HEAD>` Section] check box, as desired, then add your custom code.<br>If you select [!UICONTROL Add Code in the `<HEAD>` Section], custom code is added to the  `<head>`  section and its execution does not wait for body or page-load events. Add only `<script>` and  `<style>` elements. Adding  `<div>`  tags and other elements might cause remaining  `<head>`  elements to pop into the  `<body>`. If you are using mbox.js version 60 or later or any version of at.js, all offers will deliver asynchronously.<br> If you deselect [!UICONTROL Add Code in the `<HEAD>` Section], custom code executes immediately following the `<body>` tag. Wrap all code in a single `<div>` to preserve DOM structure. If you are using mbox.js version 60 or later or any version of at.js, all offers will deliver asynchronously.<br>**Note**: Scripts are run asynchronously. This means that you cannot, for example, use `document.write`  or similar script methods.<br>Custom code provides a non-visual interface to view, edit, and add new actions within the VEC, the Form-based Experience Composer, and the HTML offers editor. The panel provides a code view of an experience to help you build more complex experiences, fine tune existing experiences, and troubleshoot issues.<br>Custom code is intended for advanced users who are comfortable with HTML, JavaScript, and CSS. The code view can help you tweak or fine-tune changes, or fix selector issues. It can also be used to add new custom code and actions. You can add more than one custom code and optionally name each custom code.<br>**Note**: Custom code is currently available for A/B and Experience Targeting (XT) activities only. Custom code is disabled for overlay and if a redirect offer is applied.<br>Custom code supports the following use cases:<ul><li>Add custom JavaScript, HTML, or CSS to be executed at top of the page</li><li>View or edit the code generated by VEC after making modifications</li><li>Set HTML content for a selector (CSS selectors only)</li><li>Set an attribute on an HTML element</li><li>Add offer content to be delivered in a regional mbox</li><li>Swap on DOM-ready, using jQuery</li><li>Swap on DOM-ready, no jquery (Does not support Internet Explorer 8)</li><li>Swap with DOM-polling via "elementOnLoad" plugin</li><li>Custom redirect</li></ul>Custom code provides:<ul><li>Line numbers for better usability.</li><li>Syntax highlighting to help you avoid incorrect syntax for HTML offers.</li><li>The ability to create multiple custom codes and provide an optional name for each. Creating multiple custom codes makes future debugging easier. For example, instead of creating a single custom code to accomplish several modifications, you can create a separate custom code for each modification with a descriptive name. Having separate custom codes makes your modifications more modular and manageable. Note that the execution of multiple custom codes in an activity is not guaranteed to happen in the sequence in which they were created.</li></ul>The Modifications panel splits the screen between the visual mode and the code mode. Both modes remain in sync. Every modification made visually has a corresponding row in the code view. Similarly, every change that is committed in the code view displays in the visual experience. Clicking on any row in the code view selects the corresponding element on the visual page.<br>Custom code supports HTML, scripts, and styles. Any valid HTML code or script can be added or edited.|

1. Add additional modifications as necessary.

## Custom Code Use Cases {#section_26CB3360097D400FB02E20AE5FDBA352}

The **[!UICONTROL Custom Code]** panel contains code that is executed at the beginning of the page load.

You can execute the JavaScript code in the `<head>` tag. Execution of code does not wait for the `<body>` tag to be present in the DOM.

Selectors for subsequent visual actions depend on the HTML elements added in this tab.

The Custom Code panel is commonly used to add JavaScript or CSS to the top of the page.

![](assets/codeeditor_custom.png)

Use the **[!UICONTROL Custom Code]** tab to:

* Use JavaScript inline or link to an external JavaScript file

  For example, to change an element's color:

  ```javascript
  <script type="text/javascript"> 
  document.getElementById("element_id").style.color = "blue"; 
  </script> 
  ```

* Configure a style inline or link to an external stylesheet

  For example, to define a class for an overlay element:

  ```html
  <style> 
  .overlay 
  { position: absolute; top:0; left: 0; right: 0; bottom: 0; background: red; } 
  </style> 
  ```

* Add HTML snippets to define new elements

  For example, use the following HTML snippet to create an overlay `<div>` using the CSS class defined above:

  ```html
  <div class="overlay"></div>
  ```

* Swap on DOM-ready, using jQuery

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  jQuery( document ).ready(function() { 
      jQuery("#default_content").html( "<span style='color:red'>Hello <strong>Again</strong></span>" ); 
      jQuery("#default_content").css("visibility","visible"); 
  }); 
  </script> 
  ```

* Swap on DOM-ready, no jQuery (does not support Internet Explorer 8)

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  document.addEventListener("DOMContentLoaded", function(event) {  
      document.getElementById("default_content").innerHTML = "<span style='color:red'>Hello <strong>Again</strong></span>"; 
      document.getElementById("default_content").style.visibility="visible"; 
  }); 
  </script> 
  ```

* Swap with DOM-polling via `elementOnLoad` plugin

  The advantage of this is the swap occurs earlier than on DOM-ready. The plugin handles pre-hiding and reveal, and requires an id on the element.

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  /*elementOnLoad DOM Swizzling v3 ==>Mbox.js Extra Javascript*/window.elementOnLoad=function(e,l){var m=document.getElementById(e);if(m){setTimeout(function(){l(m);setTimeout(function(){m.style.visibility='visible';m.style.display='block'},20)},20)}else{setTimeout(function(){elementOnLoad(e,l)},20)}},addEvent=function(a){var d=document,w=window,wa=w.addEventListener,da=d.addEventListener,e='load',o='on'+e;if(wa){wa(e,a,false)}else if(da){da(e,a,false)}else if(d.attachEvent){w.attachEvent(o,a)}};addEvent(function(){setTimeout("elementOnLoad=function(){}",500)}); 
  elementOnLoad('default_content',function(e){ 
      e.innerHTML = "<span style='color:red'>Hello <strong>Again</strong></span>"; 
  }); 
  </script> 
  ```

* Custom redirect passing existing params, `s_tnt` param (for legacy integration to Analytics), referrer param, and mbox session

  ```javascript
  <style type="text/css">body{display:none!important;}</style> 
  <script type="text/javascript"> 
   var qs='';window.location.search?qs=window.location.search+'&':qs='?'; 
   window.location.replace('//www.mywebsite.com/'+qs+'s_tnt=${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}&s_tntref='+encodeURIComponent(document.referrer)+'&mboxSession='+mboxFactoryDefault.getSessionId().getId()+''+window.location.hash+''); 
  </script> 
  ```

* Add Adobe Target Experience Templates for use in custom code. Target Experience Templates are pre-coded samples with configurable inputs to be used to execute common marketer use-cases. These Experience Templates are provided free to developers and marketers as a starting point to execute common use-cases, either via the VEC or the Form-based Experience Composer. Use-cases include lightboxes, carousels, countdowns, and more.

  For more information, see [Experience Templates](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/experience-templates.md#concept_109BBD7EABC04DD39E6B7B1687786652).

## Custom Code Best Practices {#section_10DFFD9FB92A43C1BB444A45E0272B28}

**Always wrap the custom code in one element.**

For Example:

```html
<div id="custom-code"> 
// My Code goes here 
</div>
```

In the case that any modifications are needed, make changes inside this container.

If you do not need the custom code anymore, just leave this container empty, but do not remove it. This ensures other experience modifications are not affected.

**Do not use the element ID "CDQID" for modifications to the page made in the Code Editor.**

Target applies a new element ID with the value "CDQID" to any element on the page that's modified by Target. Because this ID is applied by Target, it should not be used for any further modifications or adjustments in the Code Editor.

**Do not perform document.write actions in custom code scripts.**

Scripts are executed asynchronously. This often causes `document.write` actions to appear in the wrong place on your page. Using `document.write` in scripts created in custom code is not recommended.

**If you create an element and then modify it, do not delete the original element.**

Each change creates a new element in the Modifications panel. Because the second action modifies Element 1, if you delete Element 1, that action no longer has anything to modify, so the change no longer works. See "Troubleshooting," below, for more information.

**Be careful if you use the custom code feature for two activities that target the same URL.**

If you use the custom code feature for two activities that target the same URL, the JavaScript is injected into the page from both activities. Target automatically determines the order of delivered content. Make sure the code does not depend on placement. It is up to you to make sure there are no conflicts in the code.

## Troubleshooting Custom Code {#section_6C965CBC31C348D7AA5B57B63DAB9E7F}

**I received a warning that an action cannot be applied due to structural changes in a page. What does this mean?**

This message indicates that the structure of your page has changed since the activity was last saved.

The missing selectors might be reached using Browse mode. We recommend that you delete and then re-create each experience to ensure that your content looks as you expect, as indicated in the warning message.

![](assets/code_editor_2.png)

***When I delete an element, I see a warning tells me that says "Deleting this action may impact subsequent actions." What does this mean?***

For example, if you have taken two actions:

* Added a class to Element 1 
* Edited the HTML for Element 1

Each change creates a new element in the Modifications panel. Because the second action modifies Element 1, if you delete Element 1, the second action no longer has anything to modify, so the change no longer works.

In other words, if you add an element with text, then in a separate action you edit that element with different text, the Modifications panel shows both actions as separate elements. When you edited the element, you created a new element that modifies the original one you created, containing the edited text. If you then delete the original element, the edited text won't be able to find the element that was edited, and will not display. The second element remains in the list of elements, but it does not affect the page because the element it changes no longer exists.

***An element I created using `document.write` in a script does not appear where I expect it to.***

Scripts are executed asynchronously. This often causes `document.write` actions to appear in the wrong place on your page. Adobe does not recommend using `document.write` in scripts created in the custom code.

***My JavaScript displays errors in the custom code.***

Any inline JavaScript which is not a valid JavaScript shows errors in the custom code.

***I cannot undo a change in my custom code.***

Currently, undo is not supported for edit and delete actions from the Modifications panel and in custom code. Undoing one of these operations could cause the experience in the VEC to appear inconsistent with the actual actions visible in the custom code. However, the actions in the custom code are in the correct state and there is no impact on delivery. This is a UI issue. To refresh the experience, save it and open it again, or go to the next step and come back. Either of these actions reloads the experience and so it appears as expected and is consistent with the actions in the Modifications panel.

**Custom code does not produce the expected results in Internet Explorer 8.**

Target no longer supports IE8.
