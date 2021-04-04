---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: Learn how to filter dynamically in Adobe Target Recommendations by comparing items (entities) against a value in the user's profile.
title: How Do I Filter by Profile Attribute Matching In Recommendations Activities?
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
---
# ![PREMIUM](/help/assets/premium.png) Profile Attribute Matching

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing items (entities) against a value in the user's profile.

Use [!UICONTROL Profile Attribute Matching] when you want to show recommendations that match a value stored in the visitor’s profile, such as size or favorite brand.

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

The following scenarios show how you can use [!UICONTROL Profile Attribute Matching]:

* A company that sells eyeglasses stores a visitor's favorite frame color as “walnut.” For that specific visitor, recommendation are set up to return only eyeglass frames that match “walnut” in color.
* A profile parameter can be defined for the clothing size (e.g., Small, Medium, or Large) of a visitor as they navigate your company’s web site. A recommendation can be set up to match that profile parameter and return products specific only to the user’s preferred clothing size.

## Profile Attribute Matching examples {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] allows you to recommend only the items that match an attribute from the visitor's profile, as in the examples below.

### Recommending items from the user's favorite brand

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. With such a rule, if a visitor is looking at running shorts from a particular brand, only recommendations will display that match that user's favorite brand (the value stored in `profile.favoritebrand` in the visitor's profile).

![Favorite brand](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Matching jobs to job seekers

Suppose that you're trying to match jobs to job seekers. You want to recommend only jobs that are in the same city as the job seeker.

You can use inclusion rules to match a job seeker's location from his or her visitor's profile to a job listing, as in the following example:

![User's city](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recommending items based on size

For a visual example of how profile attribute matching affects recommendations, consider a website that sells electric fans.

When a visitor clicks various images of fans on this website, each page sets the value of the `entity.size` parameter based on whether the size of the fan in the image is small or large.

Assume you created a profile script to track and count the number of times the value of `entity.size` is set to small vs. large.

If the visitor then returns to the Home Page, he or she will see filtered recommendations based on whether more small fans or large fans were clicked.

Recommendations based on viewing more small fans on the website:

![small fans recommendations](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations based on viewing more large fans on the website:

![large fans recommendations](/help/c-recommendations/c-algorithms/assets/large-fans.png)
