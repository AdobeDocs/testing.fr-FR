---
description: Experience URLs can be generated for Target Automated Personalization
  activities to see experience content directly on your site before the activity is
  live for preview and QA purposes. Experience URLs bypass targeting to force viewing
  of a particular experience.
keywords: experience preview;experience urls;generate urls;view experience urls
seo-description: Experience URLs can be generated for Target Automated Personalization
  activities to see experience content directly on your site before the activity is
  live for preview and QA purposes. Experience URLs bypass targeting to force viewing
  of a particular experience.
seo-title: Share experience URLs to preview Automated Personalization outside of Target
solution: Target
title: Share experience URLs to preview Automated Personalization outside of Target
title-outputclass: premium
topic: Standard
uuid: 2ef07b6c-086d-43ac-bf02-efe217652a3a
badge: premium
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Share experience URLs to preview Automated Personalization outside of Target{#share-experience-urls-to-preview-automated-personalization-outside-of-target}

Experience URLs can be generated for Target Automated Personalization activities to see experience content directly on your site before the activity is live for preview and QA purposes. Experience URLs bypass targeting to force viewing of a particular experience.

>[!NOTE]
>
>The Activity QA mode lets you create Activity URLs for other types of activities. For more information, see [Activity QA](../../c-activities/c-activity-qa/c-activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)

.

To use experience URLs, you have to share the links generated from Target, not the final URL you land on when viewing the experience. Also, if the content changes, new URLs must be generated. If you generates new URLs, old ones may not work.

Use experience URLs to share experiences with team members and to QA experiences across browsers and environments, without creating a separate QA activity. This feature is particularly useful if a site is complex, or if your security policies do not allow the site to be viewed in a simulator.

1. Create an [Automated Personalization activity](../../c-activities/t-automated-personalization/t-create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) or click the activity to open it.

   The activity does not have to be live to preview an experience.
1. On the activity summary page, click on the three vertical dots, then click **[!UICONTROL View Experience URLs]**.
1. Review and/or specify your URLs.

   * If you are using the Visual Experience Composer, the default URL you specified for the activity is entered automatically and a link is generated for each experience in your activity. You can change this URL and add others, if desired.
   * If you are using the Form-Based Experience Composer, no default URL is entered automatically. If you haven't previously created Experience URLs, click **Add New URL**. You must specify all URLs you want to preview as well as a name for each URL.
   You can add multiple URLs, which is useful when running a multi-page test or a template test and you want to preview the activity on more than one page.

   A modal window displays links to your experiences on your site to get a "true preview" of the experiences outside of Target's Visual Experience Composer. You must share the links from the message to share the preview. Clicking a link and then copying the resulting URL from the page won't work because the URL contains a parameter that only displays the page correctly when you access the page from the link in the message. Instead, copy the text in the modal window and email the whole text to your team.
1. Click **[!UICONTROL Generate All]**, then click each experience to preview it.

   If you then make changes to the experience, make sure to generate new preview links for your team by returning to the modal window and clicking **Generate all** to get new links.

   **Note:** The preview links open in new tabs and require that the pop-up blocker on your browser is disabled.

1. Click each experience name to preview the activity.

   The page opens, displaying the activity.
1. Click **[!UICONTROL Done]** to return to the activity summary.

## Considerations {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Generating Experience URLs**

* The experience URL is not impacted by traffic division between experiences.
* Audience-level targeting does not affect the preview.
* You can automatically generate a maximum of 300 experience URLs per activity. After that, you must generate the URLs manually.
* You can automatically generate a maximum of 300 experience URLs per activity. After that, you must generate the URLs manually.
* Depending on the number of experiences, it can take up to five minutes to generate the URLs. Do not close the dialog or the generated URLs will be lost.
* The preview links generated are valid for two months. After this time, you must regenerate your preview URLs.
* You must regenerate any time an experience is changed.

**Sharing Experience URLs**

* You can preview an experience even if you are not part of the targeted audience.
* You can share Experience URLs with colleagues who don't have access to Adobe Target.

**Viewing Experiences with Experience URLs**

* The preview functions for any saved activity, as long as the page hasn't changed.
* The experience URL is available whether the activity is active or inactive.
* You cannot preview an experience that has the Draft status
* Reporting is not impacted by previewing Experience URLs.

**Troubleshooting Experience URLs**

* If you are not able to see the preview in the new tab (due to browser cache), try refreshing two or three times or copy the link and open it in new browser, new session, or in a private-browser mode.
* Whether you are running your own QA for your activity or whether you forward links to another team, you can easily preview specific experiences without setting up separate tests.

