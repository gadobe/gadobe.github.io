---
title:  "Adobe 2020 Checklist"
excerpt: "3-item checklist to consider to comply and future proof your Adobe implementations in 2020"
search: true
categories:
  - technical
  - dmp
  - data
  - analytics
  - implementation

tags:
  - adobe-analytics
  - adobe-audience-manager  
  - adobe-target
  - adobe-launch
  - adobe-dtm
  - ecid-experience-cloud-id-service
  - cookies
  - itp

last_modified_at: 2020-01-05T08:05:34-05:00
---
# Adobe 2020 Checklist
This post contains a 3-item checklist to consider to comply and ideas to future-proof your Adobe implementations in 2020.

## 1. DTM Update to Adobe Launch
DTM sunset is on-going and the first milestone "new properties disabled" has passed. There are multiple guides floating around to facilitate the planning.

Key Dates (already been extended by 6 months):

|Milestone|Deadline|
|--|--|
|Option to create new DTM properties no longer available|July 9, 2019|
|All DTM properties become read-only|July 14, 2020|
|DTM servers go to sleep|January 12, 2021|

DTM has been around for years, this means that there might be redundant or legacy code/methods. The level of effort for a migration will depend on the implementation "style", tracked events and third-party tags.

### Bookmarks:
* [Upgrade Preparation Guide (official documentation)](https://docs.adobe.com/content/help/en/launch/using/reference/upgrade/upgrade-preparation-guide.html)
* [Migrating from DTM to Launch blog post by Adobe](https://medium.com/launch-by-adobe/migrating-from-dtm-to-launch-57548251a86d)
* [The Migration Process from Adobe DTM to Adobe Launch by Adobe](https://theblog.adobe.com/the-migration-process-from-adobe-dtm-to-adobe-launch/)
* [Migration considerations by 33 Sticks](https://33sticks.com/dtm-launch-migration-series-1-options-considerations/#options)
* [Key Differences between DTM and Adobe Launch by 33 Sticks](https://33sticks.com/differences-dtm-launch-aware/)

## 2. CName Tracking Server Implementation
With all the changes to cross-domain tracking in the last 12 months by browsers such as Safari (ITP), CName tracking server implementations are a must.
This is required to ensure that:
* attribution are not affected
* visitor metrics are persisted and not inflated
* segmentation and personalisation is maintained

|Solution|Method|
|--|--|
|Adobe Analytics (AA) | CName Tracking server must be implemented as part of ECID library and AA (Appmeasurement) code<sup>1</sup>.|
|Adobe Audience Manager (AAM) |If AA is not present, must be implemented as part of ECID library<sup>1</sup>.|
|Adobe Target (AT)|Request and implement first-party certificate for AT requests<sup>2</sup>.|

### Bookmarks:
<sup>1</sup> [Use ECID library and CNAME tracking to extend visitor ID expiration (official documentation)](https://docs.adobe.com/content/help/en/id-service/using/reference/ecid-library-methods.html)\
<sup>2</sup> [CNAME and Adobe Target (official documentation)](https://docs.adobe.com/content/help/en/target/using/implement-target/before-implement/implement-cname-support-in-target.html)

## 3. Consent Management
[GDPR](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation), [CCPA](https://en.wikipedia.org/wiki/California_Consumer_Privacy_Act), the data regulation in your region is when rather than an if. The common trend of to collect consent and allow users to opt-out<sup>3</sup>.

Adobe Launch can facilitate the implementation of three Consent Management extensions: Evidon, TrustArc, OneTrust.

My recommendation is to start the discussion with your legal teams to identify a potential consent and opt-out framework.

### Bookmarks:
<sup>3</sup> [Adobe Audience Manager Opt-out Options (official documentation)](https://docs.adobe.com/content/help/en/audience-manager/user-guide/overview/data-privacy/data-privacy-requests.html)\
<sup>3</sup> [Adobe Analytics Opt-out Options (official documentation)](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/data-collection/opt-out.html)

Please let me know your questions or feedback for this and future posts in the comments.
