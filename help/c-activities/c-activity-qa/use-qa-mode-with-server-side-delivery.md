---
keywords: qa;server side;server-side;preview;preview links
description: Learn how to use Adobe [!DNL Target] QA URLs with server-side delivery to perform easy end-to-end activity QA with preview links that never change, optional audience targeting, and QA reporting that stays segmented from live activity data.
title: Use Can I Perform Activity QA with Server-Side Delivery?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
---
# Use Activity QA with server-side delivery

Use QA URLs with server-side delivery in [!DNL Adobe Target] to perform easy end-to-end activity QA with preview links that never change, optional audience targeting, and QA reporting that stays segmented from live activity data.

The standard implementation of Activity QA supports passing `qa_mode` parameters via `pageUrl` parameters. This approach is convenient for standard/ajax [!DNL Target] calls. However, for server-to-server calls, this is not the best approach for a Mobile SDK case when `pageUrl` is not available.

The following code sample shows Activity QA in a server-side call:

```json
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

The following table explains a server-side request's details:

| Parameter | Type | Default Value | Description |
|--- |--- |--- |--- |
|token|Encrypted token|None.<br>It cannot be empty.|An encrypted entity that contains the list of activity IDs that are allowed to be executed in Activity QA.<br>Validation rules: Should be an encrypted token belonging to the client specified in the [!DNL Target] request. All activities specified in the token should belong to the client.|
|bypassEntryAudience|Boolean|False|Specifies whether entry step targets for QA activities should be evaluated or if they should be considered as matching.|
|listedActivitiesOnly|Boolean|False|Specifies whether QA activities should be executed in isolation or if they should be evaluated as active activities for the current environment.|
|evaluateAsTrueAudienceIds|List of IDs|Empty list.|List of audience IDs that should always be evaluated as true in the scope of the [!DNL Target] request.|
|evaluateAsFalseAudienceIds|List of IDs|Empty list.|List of audience IDs that should always be evaluated as false in the scope of the [!DNL Target] request.|
|activityIndex|Integer|Null.<br>It cannot be empty.|Activity index in the encrypted token. If  activityIndex is out of boundaries of the activity in the token or if null, it will be ignored. Index starts with 1.<br>Validation rules: Should be at least one activity index, and should reference an activity specified in the token.|
|experienceIndex|Integer|Null.|When specified, selects an experience by index in the activity definition. If not specified or out of boundaries, it will fall-back to the activity's experience selector strategy. Index starts with 1  Validation rules: Can be null, or should reference an experience in the activity.|
