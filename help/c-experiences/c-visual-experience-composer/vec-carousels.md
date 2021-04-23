---
keywords: Visual Experience Composer;VEC;carousel
description: Learn how to create a carousel that can be edited in the Adobe [!DNL Target] Visual Experience Composer (VEC).
title: How Do I Create Carousels in the Visual Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
---
# Creating Carousels that Work in the Visual Experience Composer

This topic shows how to create a carousel that can be edited in the [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).

When you use the steps below, [!DNL Target] always knows that the selected slide will have the 'selector' for the correct slide, even if it is changed in the Visual Experience Composer after a few seconds. 

1. Create static HTML placeholders.

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Add CSS to design the look and feel.

   Don't use JavaScript for this.

   >[!NOTE]
   >
   >The [!UICONTROL Render Using JavaScript] option is currently not supported if it is used along with custom code in the Visual Experience Composer.

1. Only update the classNames to hide others and show the next with timer/animation.

   Never update the DOM structure using JavaScript.
