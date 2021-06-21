---
keywords: Profile script;profile script attributes;mutually exclusive activities
description: Learn how to use profile attributes to set up tests in Adobe [!DNL Target] that compare multiple activities but do not let the same visitors participate in each activity.
title: Can I Use Profile Scripts to Test Mutually Exclusive Activities?
feature: Audiences
exl-id: b0b23887-3339-411e-9f5c-64f9d1ba778c
---
# Use profile scripts to test mutually exclusive activities 

You can use profile attributes in [!DNL Adobe Target] to set up tests that compare two or more activities but do not let the same visitors participate in each activity.

Testing mutually exclusive activities prevents a visitor in one activity from affecting the test results for the other activities. When a visitor participates in multiple activities, it can be difficult to determine whether positive or negative lift resulted from the visitor's experience with one activity, or if interactions between multiple activities affected the results of one or more of the activities.

For example, you can test two areas of your ecommerce system. You might want to test making your "Add to Cart" button red instead of blue. You might also test a new checkout process that reduces the number of steps from five to two. If both activities have the same success event (a completed purchase), it can be difficult to determine whether the red button improves conversions, or whether those same conversions were also increased because of the improved checkout process. By separating the tests into mutually exclusive activities, you can independently test each change.

Be aware of the following information when using one of the following profile scripts:

* The profile script must run before the activity launches and the script must remain unchanged for the duration of the activity. 
* This technique reduces the amount of traffic in the activity, which might require the activity to run longer. You must account for this fact when you estimate the duration of the activity.

## Setting up two activities

To sort visitors into groups that each see a different activity, you must create a profile attribute. A profile attribute can sort a visitor into one of two or more groups. To set up a profile attribute called "twogroups," create the following script:

```javascript
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 99); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` determines whether the *twogroups* profile attribute is set for the current visitor. If they do, no further action is required.

* `var ran_number=Math.floor(Math.random() *99)` declares a new variable called ran_number, sets its value to a random decimal between 0 and 1, then multiplies it by 99 and rounds it down to create a range of 100 (0-99), useful for specifying a percentage of visitors who see the activity.

* `if (ran_number <= 49)` begins a routine that determines which group the visitor belongs to. If the number returned is 0-49, the visitor is assigned to GroupA. If the number is 50-99, the visitor is assigned to GroupB. The group determines which activity the visitor sees.

After you create the profile attribute, set up the first activity to target the desired population by requiring that the user profile parameter `user.twogroups` matches the value specified for GroupA.

>[!NOTE]
>
>Choose an mbox early on the page. This code determines whether a visitor experiences the activity. As long as an mbox is encountered first by the browser, it can be used to set this value.

Set up the second campaign so the user profile parameter `user.twogroups` matches the value specified for GroupB.

## Setting up three or more activities

Setting up three or more mutually exclusive activities is similar to setting up two, but you must change the profile attribute JavaScript to create a separate group for each activity and determine who sees each one. The random number generation is different, depending on whether you create an odd or even number of groups.

For example, to create four groups, use the following JavaScript:

```javascript
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 99); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

In this example, the math used to generate the random number that assigns a visitor to a group is the same as it is with only two groups. A random decimal is generated, then rounded down to create an integer.

If you create an odd number of groups, or any number that 100 does not divide evenly into, you should not round the decimal down to an integer. Not rounding the decimal enables you to specify non-integer ranges. You do this by changing this line:

`var ran_number=Math.floor(Math.random()*99);`

to:

`var ran_number=Math.random()*99;`

For example, to place visitors in three equal groups, use the following code:

```javascript
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 99; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
