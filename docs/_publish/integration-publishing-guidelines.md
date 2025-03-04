---
title: Integration publishing guidelines
order: 3
layout: post-toc
redirect_from: /partners/integration-review-guidelines
---

# Integration publishing guidelines

## Introduction

We are excited you are creating an integration for the [Zapier Platform](https://zapier.com/platform). We are here to help you understand our platform and give you guidelines so you can successfully build your Zapier integration. Thousands of partners have built integrations on the Zapier Platform, so their mutual users can set up Zaps as easily and quickly as possible.

When you follow these guidelines, your Zapier integration can pass our review process quickly and smoothly. Plus, you’re helping us maintain quality and consistency with all integrations listed in our [App Directory](https://zapier.com/integrations). You are responsible for making sure everything in your integration complies with these guidelines, so please review them carefully before submitting for review.

Below you will find our latest guidelines arranged into clear, multiple sections: [General](https://platform.zapier.com/publish/integration-publishing-guidelines#1-general), [Meta](https://platform.zapier.com/publish/integration-publishing-guidelines#2-meta), [Authentication](https://platform.zapier.com/publish/integration-publishing-guidelines#3-authentication), [Triggers](https://platform.zapier.com/publish/integration-publishing-guidelines#4-triggers), [Actions](https://platform.zapier.com/publish/integration-publishing-guideliness#5-actions), [Searches](https://platform.zapier.com/publish/integration-publishing-guidelines#6-searches), [Error Handling](https://platform.zapier.com/publish/integration-publishing-guidelines#7-error-handling), and [Code](https://platform.zapier.com/publish/integration-publishing-guidelines#8-code).

### Key considerations

* Because the Zapier Platform is always changing and improving to keep up with the needs of our customers, this is a living document.
* If you prefer your integration to be accessible to a limited group of users, or if the Zapier integration review guidelines do not align with your requirements, you might want to consider maintaining your integration as private. Learn more about [private vs public integrations](https://platform.zapier.com/quickstart/private-vs-public-integrations).
* We encourage diversity on the Zapier Platform, provided your integration respects users with varying viewpoints and ensures a high-quality user experience. Any integration found to contain or exhibit behaviour deemed inappropriate, discriminatory or crossing acceptable boundaries will be rejected
* We reserve the right to remove users from the Zapier Platform and remove integrations from Zapier if there is evidence of not following these guidelines. This includes attempts to exploit the review process, illicitly acquire user data, or manipulate test users.


## Pre-submission checklist


Before submitting your[ Zapier integration for app review](https://platform.zapier.com/publish/public-integration), familiarize yourself with the criteria the Zapier team uses during app reviews:

* Confirm your integration is fully developed and has undergone thorough testing. This includes creating test Zaps on your end that check for bugs, edge cases, and errors.
* Focus on primary use cases. Review similar integrations in [Zapier’s App Directory](https://zapier.com/integrations/) for inspiration on which features to include in your integration.
* Ensure all integration information and metadata is complete and accurate. Be sure to follow[ Zapier’s standards for integration branding](https://platform.zapier.com/publish/intergration-brand-design-guidelines) to help your integration fit into the Zapier ecosystem well.
* Provide an active demo account and login credentials, plus any other resources that might be needed to review your integration (e.g. login credentials to your product under integration-testing@zapier.com as the username/email and dummy credit card credentials used to test making purchases, if applicable to your integration). We may need to test triggers, actions, or searches in your integration during review, so please provide us with access to the appropriate platforms and resources to do so.
* Test early with real users. Use our[ invite links to beta test](https://platform.zapier.com/manage/share-integration) the integration.
* Enable backend services so they’re live and accessible during review.
* Include detailed explanations of non-obvious features in the publishing request notes, including supporting documentation where appropriate. If we cannot understand aspects of your integration during the review, we may reject it.
* Your developer should review the [integration check reference documentation](https://platform.zapier.com/publish/integration-checks-reference) to make sure all common technical issues are addressed.

## 1. General

### 1.1 Familiarity with Zapier
If you haven’t used Zapier before, [sign up](https://zapier.com/sign-up/) for a free account and try a few popular integrations before building your integration. This will help you understand how Zapier works, how your users will set up Zaps, and how your integration can best fit into Zap workflows.

### 1.2 Key use cases
Your triggers, actions, and searches should focus on the main use cases of your platform. Check similar integrations in [Zapier’s App Directory](https://zapier.com/integrations/) to get some ideas on which items to include in your integration.

### 1.3. Integration testing
Test your integration early and often, both internally and externally during the build stage. This will help you catch bugs and identify any usability issues early on that you otherwise will be asked to address during the review process, which may extend the time to launch.

#### 1.3.1 Internal Testing
* Create test Zaps in your developer account with each of the triggers, actions, and searches in your integration, and run them, so each have some successful runs in the Zap History. This lets you experience firsthand the Zap setup process our mutual users will go through, and lets you validate the triggers, actions, and searches look and work as intended. We may ask you to share your test Zaps with us when you submit your integration for review.

#### 1.3.2 External testing with real users
* Share your integration's [invite link](https://platform.zapier.com/manage/share-integration) before you request a review to give users access to the integration and to gather early feedback. Seeing unique and active users gives us confidence the integration is useful and successfully working for many users.

### 1.4 Consistency in style
The terminology and features in your Zapier integration should be consistent with the terminology and features seen in your product's own UI. We strive to give users a consistent experience throughout Zapier, so your integration should also be consistent with the style used in other popular Zapier integrations. Be sure to follow [Zapier’s integration branding and design guidelines](https://platform.zapier.com/publish/intergration-brand-design-guidelines) to ensure your integration suits the Zapier ecosystem well.

### 1.5 Valid test account
The Zapier team verifies each trigger, action,and search in the integration to verify they function consistently with the platform. To do so, please set up a valid test account on your platform and share the test credentials with our team via the publishing form. Further requirements for the test account are below:

* Create the test account using integration-testing@zapier.com, so we have access to the Forgot Password flow.
* Make sure the account includes all the features enabled needed to test out each Zap step with any special configurations set. All paid/premium features required for testing should be unlocked.
* Ensure the account is non-expiring and not under a trial to avoid any interruption during your review and going forward even after your integration goes live. Our team will need occasional access for troubleshooting and testing while supporting our mutual users
* Provide a demo video or detailed documentation to the Zapier team if testing any features requires an environment that is difficult to replicate or requires specific hardware.
* Supply any other necessary credentials/resources and configure the test account so it’s ready to test. For example,  providing dummy payment data if your integration requires making payments, or configuring your plugin/embed on a test site to send us. Do not give super admin access or enable any features or settings on the test account that are only available to internal employees, and not available to users.

### 1.6 Completeness and platform consistency
Submit your integration for review only when it is complete and ready to be published. Make sure it is thoroughly tested for edge cases, and does not have any bugs when submitting. Both your product and integration need to work consistently without errors. Products not yet fully launched to the public (app is invite-only or for beta users only) and integrations using sandbox/test/dev environments or endpoints will be asked to remain private until they are ready to be publicly available. Once the app is published, it is visible in the Zapier App Directory and it would be expected that any of our mutual users would be able to connect the application to Zapier.

See the following guideline regarding “Repeated Submission” for more information. We will not allow incomplete or error-ridden integrations to become public.

### 1.7 Repeated submission
Submitting multiple integrations that are essentially the same ties up the Zapier process and risks the rejection of all the integrations. Please be thoughtful and consider combining your integrations into one where it makes sense. Also, please do not flood the Zapier team with multiple, consecutive submissions of the same integration while going through the review process. Violating this policy will result in slower review times for your integration or further penalties.

### 1.8 Misleading or malicious functionality
Your integration must perform as advertised and should not give users the impression the integration is something it is not. If your integration appears to promise certain features and functionalities, it needs to deliver. Do not create a Zapier integration that can be used to spam, phish, or send unsolicited messages to users. If you attempt to cheat the system (for example, by trying to trick the review process, steal user data, or fake real users) your integration will be removed from Zapier and you could be expelled from submitting any integrations in the future. False information and features, including inaccurate data or joke functionalities, such as fake phone calls or SMS are prohibited.

### 1.9 Objectionable content
Integrations should not include content that is discriminatory, defamatory, offensive, mean-spirited, or insensitive with regards to gender, religion, sexual orientation, age, race, national/ethnic origin, or other targeted groups.

## 2. Meta

### 2.1 Integration ownership
The Zapier team needs to ensure the account owning the integration has proper access to associated platform and API, either by working for, being associated with, or being contracted by the company whose integration is in review. This is so we can reach out with questions or support issues during the review and after the integration is public. If it’s not obvious to us the owning account is associated with your integration's company (largely by email domain), we will request proof via an email from a matching domain as the platform or confirmation from someone at the company.

Here are some further scenarios of what integrations are permitted on the Zapier platform by status, ownership, and intention:

* Anyone can build a private integration.
* Integrations by developers who work for or third-party developers (preferably a [trusted developer](https://platform.zapier.com/quickstart/trusted-developers)) hired by the company owning the API and intended to go public are permitted to the invite-only status as a stepping stone before going public. 
* Integrations by developers who work for the company owning the API or have been contracted by the API owner can go public.
* Integrations by developers who are building on a private API and have no intension of taking their integration public are permitted to remain invite-only indefinitely.
* Integrations by developers who are building on a public API they do not own and only intend to share with their team (within their company or organization, family and friends, etc.) are permitted to be in invite-only.
* Integrations by developers who are building on a public API they do not own and intend to sell access to the integration are permitted to remain in invite-only.
* Integrations by developers who are building with sandbox/test/dev environments or endpoints are permitted to remain in invite-only.

Here are some further scenarios of what integrations are prohibited from the Zapier Platform by integration status, ownership, and intention:

* Integrations by developers who are building on an API they own but for a competing product with Zapier are prohibited from going public or being invite-only.
* Integrations by developers who are building on a public API they do not own, and routing traffic to their own servers are prohibited from going public or being invite-only. Exceptions apply when building on an approved third-party API.
* Integrations by developers who do not own the API used in the integration or who have not been given explicit permission by the owners of the API cannot be public.

### 2.2 Developer information
Ensure all information provided in the Publishing form is accurate and up-to-date. This helps us reach out to the appropriate contacts when questions or support issues arise. 

#### 2.2.1 Homepage URL
* The Homepage URL submitted via the Publishing form should be the homepage URL of the application's marketing site.

### 2.3 Replacement integration
The integration should not already have an equivalent that is Public in our App Directory. Each integration published within the Zapier App Directory should represent a distinct, independent app - to ensure the best experience for our mutual customers. If you’re trying to replace an existing (Legacy) integration, check out the guide on [versions](https://platform.zapier.com/manage/versions-ui) and how to deploy changes. Creating separate integrations for the same app brand is [not allowed.](https://platform.zapier.com/manage/versions-ui#can-i-start-over) 

### 2.4 Multiple integrations
Do not create separate integrations for functionality that share the same authentication method and interact with the same API. Consolidate the functionality into one, high-level integration.

### 2.5 Name
Use the actual, unique name of your app with the same capitalization your company uses in your core branding. Trademark/copyright identifiers such as a TM suffix aren’t allowed in the app name, though they can be added to the description.

Do not add adjectives or phrases to your app name, and only include your company name if the company and app name are always used together in your branding. Do not include the word "app" unless you always include that in your app’s branding.

### 2.6 Logo
The logo must be a square, transparent PNG at least 256x256px in size. Please use a bigger version if you have one available. If your app has a solid, square background, round the corners 3% of the width and set the background as transparent. If your icon is not square, make a square transparent image and center your icon inside the transparent square. Do not include the app name or other copy in the logo as it will not be legible at small sizes.

### 2.7 Description
Write a short description (up to 140 characters) of your app’s core features and use cases in the form of `<Integration Name> is a...`. The copy should not include links or mentions of Zapier. Do not use flowery or overstated language, or make make it appear your integration is associated with or endorsed by Zapier.

**Example**:

- `Trello is a team collaboration tool to organize anything on a kanban board.`, not `Trello is the best project management tool.`
- `Dropbox lets you store files online, sync them to all your devices, and share them easily.`, not `A file storage app.`

###  2.8 Category and role
Select the category that best fits your app’s core features and use case. If your app includes features from multiple categories, choose the category that best describes your app’s primary use case today.

You may update your app’s category anytime if needed, so do not select a category that fits your future ambitions for the app instead of its features today. Additionally, do not select a category that applies only to a secondary feature in your app or a narrow category that does not cover your app’s broader focus.

Be sure to select the integration owner’s relationship with your integration in the Role field.

### 2.9 Language
We do not have native support for language other than English on the Zapier Platform. The description of your integration, trigger/action/search names, field names, output field labels, help texts, and error messages must be in English. The data returned from your API and passed back to Zapier can be in the native language of your product.

## 3. Authentication

### 3.1 Connecting accounts
Make connecting new accounts on Zapier easy for users. [OAuth v2](https://platform.zapier.com/build/oauth) is the preferred authentication scheme.

* For non-Oauth v2 authentication schemes, users must have the ability to easily generate and retrieve API keys or other required credentials themselves without needing assistance from your support team. 
* Provide help text with guidance on where users can find their credentials if you’re not using Basic Auth. If possible, provide an embedded link in the help text straight to the page in the platform where users can find the credentials. For example, “Go to the [[API details](https://www.example.com/manage/api-details)](https://my.xxxx.com/manage/api-details) screen from your <Integration Name> Dashboard to find your API Key.“

### 3.2. Invalid credentials
When authenticating with invalid credentials, make sure a user-friendly error message is returned containing information a non-technical user can understand. For example, "Your API Key does not appear to be valid." is better than a generic 401 error message.

### 3.3 Connection label
[Connection labels](https://platform.zapier.com/build/auth#how-to-add-a-connection-label-to-authenticated-accounts) for authenticated accounts helps users who connect more than one account to their Zapier account distinguish between accounts. Easily identifiable values such as account name, email address, and name work great as Connection Labels, but avoid using sensitive information or non-easily identifiable values such as API Keys, API Secrets, and lengthy IDs as Connection Labels. 

### 3.4 HTTPS endpoints
For security purposes, all API endpoints used by in integration must use HTTPS versus HTTP. We also require the authentication or login portal to the platform to be hosted on HTTPS.

## 4. Triggers

### 4.1 Important triggers
We allow integrations to set a maximum of three triggers as ‘Important’ via the [Visibility Option](https://platform.zapier.com/build/trigger#how-to-add-a-new-trigger-to-a-zapier-integration) in the Visual Builder or the basic [display schema](https://zapier.github.io/zapier-platform-schema/build/schema.html#basicdisplayschema) via the CLI. If you have three or fewer triggers, generally you should set them all as ‘Important’.

### 4.2 Copy

Any copy associated with a trigger should match the copy, text, and terminology used in your product’s UI. This includes the trigger’s name, description, input fields, help text, output fields, etc. For instance, since Dropbox calls directories "folders" in their product UI, the respective trigger in [their Zapier integration](https://zapier.com/integrations/dropbox/integrations#triggers-and-actions) refers to "folders" instead of "directories". If your API uses different terminology than your product’s UI, match the UI as users are most familiar with this - not the API.

Additionally, each trigger must have:

* a descriptive, titlecased name. For example, ‘New Lead’, instead of ‘New lead’.
* a descriptive key. For example, ‘new_lead’, instead of ‘trigger_1’.
* a descriptive noun that reflects the object that is being returned in the trigger. This typically is one word and should always be in the singular form. The noun is used around the Zapier platform and will be pluralized automatically to complete various messages to users such as ‘No new <noun> found.‘
* a concise description using our standard phrasing ‘Triggers when...“ and no more than a handful of additional words. Always the description with a period/full stop. Do not include the name of your integration nor capitalize the noun in the description such a ‘Triggers when a new Lead is created in Example CRM.’ 

### 4.3 Trigger input fields
[Trigger input fields](http:), if they exist, should be named appropriately and include help text if their purpose is ambiguous.

#### 4.3.1 ID fields
* Users should never be expected to type in an ID as this is error prone. Your integration should not have any trigger fields labeled ‘<Object Name> ID’, such as ‘Customer ID’. Instead, use Zapier’s [dropdown](https://platform.zapier.com/build/input-designer) functionality to provide users with a user-friendly list of options.

#### 4.3.2 Help text
* Don't be redundant with help text, and only include it if you have something different to say from the field name such as  the expected format of the value or additional instructions. Redundant help text teaches users not to read any help text at all, so important information can be missed.

#### 4.3.3 Optional trigger fields

* If a trigger field is optional, confirm the request does not throw an error in a null case where the users does not select an option.

#### 4.3.4 Field types

* Use the most appropriate [input field type](https://platform.zapier.com/build/input-designer#zapier-input-field-types) for each of the input fields to show users what type of data to include — though do note the Zap Editor does not validate the data to ensure users added the correct item for that field type. 

* If the field can accept multiple values, use our built in [‘List’ property](https://github.com/zapier/zapier-platform/blob/main/packages/schema/docs/build/schema.md#fieldschema) or ‘[Allow Multiples’](https://platform.zapier.com/build/input-designer#allows-multiples) functionality rather than asking users to provide a comma-separated value in a text field.

#### 4.2.5 Ordering
* Put required trigger input fields at the top of the form with optional fields towards the bottom by importance.

### 4.4 Static webhooks
                        
Triggers using static webhooks are not allowed in public Zapier integrations. Users can replicate this functionality on Zapier via our built in [Webhooks integration](https://zapier.com/integrations/webhook/integrations). Please consider including authentication and using REST hooks to provide users with a more streamlined experience.

### 4.4 Polling Triggers
Live Zaps with [polling triggers](https://platform.zapier.com/build/trigger#polling-trigger) automatically poll the request URL for new data every 5 to 15 minutes, depending on the user’s [Zapier plan](https://zapier.com/pricing).

* Return results from the polling URL in reverse chronological order by created date, so the most recently created or updated object is returned first. 
* Return a sufficient amount of items from the polling endpoint. Generally, 100 items is plenty for most integrations, but there are be cases where it’s common for users to perform an action that would trigger more than 100+ records at once.
* Use [pagination](https://platform.zapier.com/build/trigger#how-to-use-pagination) on the trigger results if large amounts of data will be returned.
* Each result should contain an explicit ‘id’ field for [deduplication](https://platform.zapier.com/build/dedupe) from the polling endpoint. By default, the field called `id` will be used as the deduplication key if it exists. Otherwise Zapier looks for the shortest field key with `id` in the key name.

### 4.6 REST webhooks
[REST hook-based triggers](https://platform.zapier.com/build/trigger#rest-hook-trigger) are Zapier’s preferred implementation of triggers, since they fire immediately after the triggering action is performed. Here’s a [post](https://zapier.com/engineering/introducing-resthooksorg/) further describing why we and our mutual users prefer REST hook triggers over polling triggers.

#### 4.6.1 Multiple subscriptions

* Hook based triggers must allow multiple subscriptions without overwriting subscriptions. You can test this by setting up 2 Zaps with the same trigger, turning them On, and confirming  both Zaps fire successfully when the triggering action is performed.

#### 4.5.2 Polling URL
* Each REST hook trigger must also have a polling URL defined. This allows users to easily pull in sample resources to set up their Zaps without leaving the Zap Editor. Without a corresponding polling URL, users would have to navigate off of the Zap Editor to the product to create or update a resource each time they setup a Zap.
* Ensure the data returned from the polling URL follows the Polling Trigger guidelines above.
* Data returned from the polling URL should exactly match the data returned in the hook payload. Be particularly wary field keys from the polling URL and in the hook payload match in spelling and casing.

### 4.7 Response content

#### 4.7.1 Names
* Many actions in Zapier require names to be split into two fields - first/last or given/surname. This conflicts with some naming schemes around the world, but without a separated name field, your trigger may not be compatible with certain integrations. Always provide separated name fields, though feel free to return the full name as well if the response already includes this.

#### 4.7.2 Addresses
* Likewise with names, many actions in Zapier require address components in separate fields (street, street2, city, state, zip), instead of requiring the complete address in a single field. Always provide separated address fields, though feel free to return the complete address as well if the response already includes this.

#### 4.7.3 Date-times
* Date-time values are required to be in [ISO 8601 format](http://www.cl.cam.ac.uk/~mgk25/iso-time.html?utm_source=zapier.com&utm_medium=referral&utm_campaign=zapier#date) and should always include a time zone offset (even if it's UTC). This includes date-time values returned from the polling URL, in the hook payload, and in your sample data. Avoid UNIX/Epoch timestamps. Date-time values may be modified in your API call custom code if your API returns dates in different formats. Example acceptable date-time values include:

    * `2018-12-15T01:15:13Z` (or `-0000` instead of `Z`)
    * `2018-12-01T12:32:01-0800`
    * `2018-12-01T12:32:01-08:00`
    * `2018-12-13` (for date-only values)

#### 4.7.4 Booleans
* Set boolean values as `true` or `false`. Do not use `1` and `0` or alternative representations for boolean values.

#### 4.7.5 Important data
* The response data should include important keys in the most usable format. For example, it helps to return both the ID and pretty name of objects, any contact information, and links to the resource (ex: New Card in Trello, link to card).

#### 4.7.6 Unnecessary/excess data
* Remove unnecessary fields that may seem confusing or add noise to users’ Zap setup process. For example, if the response content includes information about the request itself and the input fields provided, please remove those fields from the returned response.

#### 4.7.7 Dropdown fields

* Return both the name and ID of the selected dropdown option to be used in subsequent steps of a Zap. 

### 4.8 Sample Data

Each trigger requires [sample data](https://platform.zapier.com/build/faq#output) for instances where no result is returned during Zap setup. This could be because the API is temporarily down, or because the user has no existing data in their account to return. The sample data must:

* Only represent one item, and not the entire response of the request if there are multiple items returned as a set. For example, {"key": "value"} instead of [{"key": "value"}, {"key": "value2"}, ... ]. 
* Use representative data in the expected format the values will be returned. For example, don’t set a ‘first name’ key to ‘string’ or ‘1234’; set it to something like ‘Bob’.
* Be a reflection of the keys returned in every response for all users of the trigger. This means if there are custom fields that will be returned for some users and not others, please do not include these in the sample data.

### 4.9 Output fields

[Output fields](https://platform.zapier.com/build/faq#output) add user-friendly labels to your API’s response to facilitate mapping fields during Zap setup for users. By default, Zapier will try to make a friendly version of the response by capitalizing words and replacing underscores with spaces, but this can be customized. Add a custom output field label when:

* a field is abbreviated. For example, ‘LTV’ should be labeled ‘Lifetime Value’.
* a field has an ambiguous unit of measure. For example, ‘Duration’ should be labeled ‘Duration (in seconds)’.
* a field is represented by an ID.
* in general, it is not instantly clear what the field or value represents.


### 4.10 Update triggers
Don't offer a generic 'Updated <object name>' trigger, as these are often too general for users to use in their Zaps. Instead, think under what specific scenarios the user needs an update trigger. For example, instead of offering an 'Updated Deal' trigger which triggers when anything changes on the deal, offer a 'New Deal in Stage' or 'Updated Deal Status' trigger that allows the user to specify which stage they want to monitor.

### 4.10 Error Messages
Users should never receive a successful response if there was an error in the request. All error messages should be user-friendly and avoid technical jargon. Be as specific as possible to what caused the error.

## 5. Actions

### 5.1 Important actions
We allow integrations to set a maximum of three actions as ‘Important’ via the [Visibility Option](https://platform.zapier.com/build/action#how-to-add-a-new-action-to-a-zapier-integration) in the Visual Builder or the basic [display schema](https://zapier.github.io/zapier-platform-schema/build/schema.html#basicdisplayschema) via the CLI. If you have three or fewer actions, generally you should set them all as ‘Important’.

### 5.2 Copy

The copy for actions should match your product’s UI. This includes the action’s name, description, input fields, help text, etc. For instance, since Dropbox calls directories "folders" in their product UI, the Zapier integration should refer to "folders" in the respective action. If the API uses different terminology than your product’s UI, match the UI - not the API.

Additionally, each action must have:

* a descriptive, titlecased name. For example, ‘Create Lead’, instead of ‘Create lead’.
* a descriptive key. For example, ‘create_lead’, instead of ‘action_1’.
* a descriptive noun that reflects the object that is being fired in the trigger. This should typically be one word and should always be in the singular form. The noun is used around the Zapier platform and will be pluralized automatically to complete various messages to users such as ‘No new <noun> found.‘
* a concise description starting with a plural form of the action verb, and ending in a period/fullstop. For example, the description for a ‘Create Lead’ action could be ‘Creates a new lead.’ Please do not include the name of the platform nor capitalize the noun such a  ‘Creates a new Lead in XXX CRM.’

### 5.3 Action input fields
All action steps *must* include [input fields](https://platform.zapier.com/build/action#2-build-action-input-form) to gather the data needed to create, update, or perform the intended action.

#### 5.3.1 ID fields

* Users should never be expected to manually type or map an internal ID to an action field. Your integration should not have input fields labeled ‘XXX ID’. Generally, trigger and action steps of other integrations do not return internal IDs for your specific platform to be used in an action field from your Zapier integration. Use Zapier’s [dynamic dropdown](https://platform.zapier.com/build/dynamic-dropdowns) and [Search Connector](https://platform.zapier.com/build/search-create-action)/[search-powered field](https://platform.zapier.com/reference/cli-docs#search-powered-fields) functionalities to provide users with an easier way to select or search for the appropriate resource by a more readily-available value such as ‘name’, ‘email address’, ‘title’, etc.

#### 5.2.2 Ordering
* Order action fields logically. If you are unsure, look at how the respective fields are ordered in your platform and mimic that since users will be familiar with that ordering. 
* Required action fields should generally be listed first at the top of the Zap Editor.
* Place all optional, lesser-used fields towards the bottom.
* Group related fields together. For example, first name and last name fields, as well as individual address component fields should be ordered consecutively. Do NOT use [line-item groups](https://platform.zapier.com/build/input-designer#how-to-add-a-line-item-group) or the [‘children’](https://github.com/zapier/zapier-platform/blob/main/packages/schema/docs/build/schema.md#fieldschema) field schema key to visually group fields; these are solely intended for line-item functionality.

#### 5.3.3 Required fields
* If a field doesn't have to be required, don't make it! Parallel the required fields from your integration as closely as possible. For example, if 'Email Address' is not required to create a lead in the platform, do not make the 'Email Address' field required in the Zapier editor. If the API specifies a non-important field as required, hard-code a default value so the field is not empty if one is not provided by the user.
* If the action step has a case where one field OR another field is required, set both fields as optional, add help text to both fields stating that one or the other is required, and throw a user-friendly error message if neither field is filled.

#### 5.3.4 Help text
* Don't be redundant with help text, and only include it if you have something different to say from the field name such as the expected format of the value or additional instructions. For example, help text for an 'Email Address' field stating 'Contact's email address' is not necessary. Redundant help text teaches users not to read any help text at all, so important information can be missed. You may use [Markdown](https://zapier.com/blog/beginner-ultimate-guide-markdown/) formatting in help text.

#### 5.3.5 Default values

* Set [default values](https://platform.zapier.com/build/input-designer#add-fields) for input fields sparsely, but when:

* the API specifies an unimportant field as required, set a default value in case one is not provided by the user.
* the a field in the platform is set to or shows a default value, set the same default value for the action field in the Zapier integration.

#### 5.3.6 Field types

* Use the most appropriate [input field type](https://platform.zapier.com/build/input-designer#zapier-input-field-types) for each of the input fields to show users what type of data to include — though do note Zapier does not validate the data to ensure users added the correct item for that field type.

* If the field can accept multiple values, use our built in [‘List’ property](https://github.com/zapier/zapier-platform/blob/main/packages/schema/docs/build/schema.md#fieldschema) or ‘[Allow Multiples’](https://platform.zapier.com/build/input-designer#allows-multiples) functionality rather than asking users to provide a comma-separated value in a text field.

### 5.4 [Response content](https://zapier.com/developer/documentation/v2/integration-dev-guide/#action-response-content)

Return information about the resource that was created, updated, or affected by the action, and not just a 'success' message. At a minimum, return an ID, the name or title of the resource (when pertinent), and a link to the newly created, updated, or affected resource in the platform (if available). Additionally, return any other useful data about the resource users may need in subsequent actions of a multi-step Zap.

#### 5.3.1 Date-times
* Date-time values are required to be in standard [ISO 8601 format](http://www.cl.cam.ac.uk/~mgk25/iso-time.html?utm_source=zapier.com&utm_medium=referral&utm_campaign=zapier#date) and should always include a time zone offset (even if it's UTC). This includes date-time values returned from the polling URL, in the hook payload, and in your sample data. Avoid UNIX/Epoch timestamps. Date-time values may be modified in your API call custom code if your API returns dates in different formats. Example acceptable date-time values include:

    * `2018-12-15T01:15:13Z` (or `-0000` instead of `Z`)
    * `2018-12-01T12:32:01-0800`
    * `2018-12-01T12:32:01-08:00`
    * `2018-12-13` (for date-only values)

#### 5.3.2 Booleans
* Set boolean values as `true` or `false`. Do not use `1` and `0` or alternative representations for boolean values.


#### 5.4.3 Important data

* The response data should include important fields in the most usable format. For example, it helps to return both the ID and pretty name of resources, any important information about the resource such as contact information, and a link to the resource in the platform (ex: New Card in Trello, link to card).

* Returning a link of the newly created/updated/affected resource in the action’s response data helps users link to the resource in subsequent steps of a multi-step Zap and confirms the new resource was created. This is also helpful for our support team when debugging issues.

#### 5.4.4 Unnecessary/excess data
* Remove non-necessary fields that may seem confusing or add unnecessary noise to users’ Zap setup process from your API call’s custom code. For example, if the response content includes information about the request itself and the input fields provided, please remove those fields from the returned response.

#### 5.4.5 Dropdown fields

* The response data should include important keys in the most usable format. For example, it helps to return both the ID and pretty name of objects, any contact information, and links to the resource (ex: Find Card in Trello, link to card).

* Return both the name and ID of the selected dropdown option to be used in subsequent steps of the Zap. 

### 5.5 Sample data

The ‘Test this Step’ step on actions sends a real request on behalf of the connected account. Therefore, each action requires [sample data](https://platform.zapier.com/build/faq#output) for instances when the user does not wish to actually run the action in their account to finish setting up the Zap. The sample data must:

* Only represent one record, and not the entire return from the request if there are multiple records returned as a set. For example, {"key": "value"} instead of [{"key": "value"}, {"key": "value2"}, ... ]. 
* Use representative data in the expected format the values will be returned. For example, don’t set a ‘first name’ key to ‘string’ or ‘1234’; set it to something like ‘Bob’.
* Be a reflection of the keys return in every response for all users of the action. This means if there are custom fields that will be returned for some users and not others, please do not include these key:values in the sample data.

### 5.6 Output fields

[Output Fields](https://platform.zapier.com/build/faq#output) add user-friendly labels to your API’s response data to facilitate mapping fields during Zap setup for users. By default, Zapier will try to make friendly version of your API’s response, capitalizing words, and replacing underscores with spaces, but they an also be customized. Add a custom output field label when:

* a field is abbreviated. For example, ‘LTV’ should be labeled ‘Lifetime Value’.
* a field has an ambiguous unit of measure. For example, ‘Duration’ should be labeled ‘Duration (in seconds)’.
* a field is represented by an ID.
* in general, it is not instantly clear what the field or value represents.

### 5.7 Create or update functionality
If your integration must have a ‘Create-or-Update’ functionality, implement a ‘Find-or-Create Search’ with an ‘Update’ action versus a ‘Search’ with a ‘Create-or-Update’ action or a standalone ‘Create-or-Update’ action.

### 5.8 Delete actions
Avoid delete actions which make it easy for users to accidentally delete data they didn’t intend to remove. Instead, offer less permanent actions such as options to deactivate, unsubscribe, or tag a user in a certain way (where users could then easily delete those items from inside your product).

## 6. Searches

### 6.1 Important searches
We allow integrations to set a maximum of three searches as ‘Important’ via the [Visibility Option](https://platform.zapier.com/build/action#how-to-add-a-new-action-to-a-zapier-integration) in the Visual Builder or the basic [display schema](https://zapier.github.io/zapier-platform-schema/build/schema.html#basicdisplayschema) via the CLI. If you have three or less searches, generally you should set them all as ‘Important’.

### 6.2 Find or create

Search actions can optionally create items if nothing is found in the search. If your integration has a ‘Create-or-Update’ action, please implement a ‘Find-or-Create Search’ with an ‘Update’ action versus a ‘Search’ with a ‘Create-or-Update’ action or a standalone ‘Create-or-Update’ action.

### 6.3 Copy
The copy for searches should match your product’s UI. This includes search name, description, input fields, help text, etc. For instance, since Dropbox calls directories "folders" in their product UI, the Zapier integration should refer to "folders" in the respective search. If the API uses different terminology than your integration's UI, match the UI - not the API.

Additionally, each search must have:

* a descriptive, titlecased name. Use ‘Find’ over ‘Get’. For example, ‘Find Lead’, instead of ‘Get lead’.
* a descriptive key. For example, ‘find_lead’, instead of ‘search_1’.
* a descriptive noun that reflects the object that will be returned. This should typically be one word and should always be in the singular form. The noun is used around the Zapier platform and will be pluralized automatically to complete various messages to users such as ‘No new <noun> found.‘
* a concise description starting with a plural form of the verb, which typically is ‘Finds’, and ending in a period/fullstop. For example, a valid description for a ‘Find Lead’ search is ‘Finds a new lead.’ Please do not include the name of the platform nor capitalize the noun such a  ‘Finds a new Lead in XXX CRM.’

### 6.4 Search fields
[Search fields](https://platform.zapier.com/build/action#2-build-action-input-form) should be named appropriately and include help text if their purpose is ambiguous.

#### 6.4.1 ID fields
* Users should never be expected to manually type or map an internal ID to a search field. Your integration should not have search fields labeled ‘XXX ID’. Generally, trigger and action steps of other integrations do not return internal IDs for your specific platform to be used in an action field from your Zapier integration. And if the user *is* using a trigger from your Zapier integration, the trigger should return all necessary information about the resource without the Zap needing a search step to retrieve additional, necessary information. Instead, provide search field options for more general information such as ‘name’, ‘email address’, ‘phone number’, ‘title’, etc. that is more readily-available from all triggers.

#### 6.4.2 Help text
* Don't be redundant with help text, and only include it if you have something different to say from the field name such as the expected format of the value or additional instructions. Redundant help text teaches users not to read any help text at all, so important information can be missed.

#### 6.4.3 Optional search fields
* If a search field is optional, confirm the request does not throw an error in a null case where the users does not select an option.

#### 6.4.4 Field types
* Use the most appropriate [input field type](https://platform.zapier.com/build/input-designer#zapier-input-field-types) for each of the input fields to show users what type of data to include — though do note Zapier does not validate the data to ensure users added the correct item for that field type. 
* If the field can accept multiple values, use our built in [‘List’ property](https://github.com/zapier/zapier-platform/blob/main/packages/schema/docs/build/schema.md#fieldschema) or ‘[Allow Multiples’](https://platform.zapier.com/build/input-designer#allows-multiples) functionality rather than asking users to provide a comma-separated value in a text field.

#### 6.4.5 Ordering
* Put required search fields at the top of the form with optional fields towards the bottom by importance.

### 6.5 Response content
While create actions return a single object to Zapier; searches must return an array of objects. Each search must follow these guideline:

#### 6.5.1 No result

* Do not raise an error if there are no search results to return. If your API returns a 404 for search misses, use custom code to return an empty list.

#### 6.5.2 Names
* Many actions in Zapier require names to be split into two fields - first/last or given/surname. This conflicts with some naming schemes around the world, but without a separated name field, your trigger may not be compatible with certain integrations. Always provide separated name fields, though feel free to return the full name as well if the response already includes this.

#### 6.5.3 Addresses
* Likewise with names, most actions in Zapier require address components in separate fields (street, street2, city, state, zip), instead of requiring the complete address in a single field. Always provide separated address fields, though feel free to return the complete address as well if the response already includes this.

#### 6.5.4 Date-times
* Date-time values are required to be in [ISO 8601 format](http://www.cl.cam.ac.uk/~mgk25/iso-time.html?utm_source=zapier.com&utm_medium=referral&utm_campaign=zapier#date) and should always include a time zone offset (even if it's UTC). This includes date-time values returned from the polling URL, in the hook payload, and in your sample data. Avoid UNIX/Epoch timestamps. Date-time values may be modified in your API call custom code if your API returns dates in different formats. Example acceptable date-time values include:

    * `2018-12-15T01:15:13Z` (or `-0000` instead of `Z`)
    * `2018-12-01T12:32:01-0800`
    * `2018-12-01T12:32:01-08:00`
    * `2018-12-13` (for date-only values)

#### 6.4.5 Booleans
* Set boolean values as `true` or `false`. Do not use `1` and `0` or alternative representations for boolean values.

#### 6.4.6 Important Data
* The response data should include important fields in the most usable format. For example, it helps to return both the ID and pretty name of resources, any important information about the resource such as contact information, and a link to the resource in the platform (ex: New Card in Trello, link to card).

#### 6.4.7 Unnecessary/Excess Data
* Remove unnecessary fields that may seem confusing or add noise to users’ Zap setup process from your API call’s custom code. For example, if the response content includes information about the request itself and the input fields provided, please remove those fields from the returned response.

### 6.5 Sample Data
Each search requires [sample data](https://platform.zapier.com/build/faq#output) for instances where no result is returned during Zap setup. This could be because the API is temporarily down, or because no result is returned for the specific search the user tests. The sample data must:

* Only represent one record, and not the entire return from the request if there are multiple records returned as a set. For example, {"key": "value"} instead of [{"key": "value"}, {"key": "value2"}, ... ]. 
* Use representative data in the expected format the values will be returned. For example, don’t set a ‘first name’ key to ‘string’ or ‘1234’; set it to something like ‘Bob’.
* Be a reflection of the keys return in every response for all users of the search. This means if there are custom fields that will be returned for some users and not others, please do not include these key:values in the sample data.

### 6.7 Output fields
[Output fields](https://platform.zapier.com/docs/build#output) add user-friendly labels to your API’s response data to facilitate mapping fields during Zap setup for users. By default, Zapier will try to make friendly version of your API’s response, capitalizing words, and replacing underscores with spaces, but they an also be customized. Add a custom output field label when:

* a field is abbreviated. For example, ‘LTV’ should be labeled ‘Lifetime Value’.
* a field has an ambiguous unit of measure. For example, ‘Duration’ should be labeled ‘Duration (in seconds)’.
* a field is represented by an ID.
* in general, it is not instantly clear what the field or value represents.

## 7. Error handling
APIs are not always available. Users do not always provide valid data for requests. Build a defensive and resilient integration. Plan for 4xx and 5xx responses. Without proper handling, errors can have incomprehensible messages, technical error codes, or worse, go uncaught.

### 7.1 General errors
Use `ErrorException` in situations where users misconfigure their Zaps and need to take action. Typically, this will be for prettifying `4xx` responses and API’s that return errors as `200` with a payload that describes the error and any guidance on how to correct it, if possible.

* Note if a Zap raises too many error messages it will be automatically turned off, so only throw these if the scenario is truly an error that needs to be fixed.
* Elaborate on terse messages. 'Your API Key is invalid.' is better than 'not_authenticated.' 
* If the error calls out a specific field, surface that information to the user. ‘Title is not valid.’ is better than ‘Invalid Request.’
* If the error provides details about why a field is invalid, surface that information to users. ‘Title is invalid. Please only use alphanumeric characters.’ is better than ‘Title is invalid.‘

### 7.2 Halting errors
Use `HaltedError` in situations where a required pre-condition is not met. For instance, in an action to add an email            address to a list where duplicates are not allowed, throw a `HaltedError` if the Zap attempted to add a duplicate. This          indicates failure, but is treated as a soft failure.

* Note, unlike general errors, a Zap will never by turned off when this error is thrown even if it is raised more often than not.

### 7.3 Stale authentication credentials
* For integrations requiring manual refresh of authorization on a regular basis, Zapier provides `ExpiredAuthError`, so the current operation is interrupted, the Zap is turned off (to prevent additional calls with expired credentials), and a predefined email is sent out informing the user to refresh the credentials.
* For integrations using OAuth2 + refresh requests or Session Auth, use `RefreshAuthError`. This signals Zapier to refresh the credentials and retry the failed operation.

## 8. Code

### 8.1 Environment variables
Do not hard code credentials such as API Keys, Client IDs, Client Secrets, etc. into your integration. Use [environment variables](https://platform.zapier.com/build/advanced-features#environment-variables)instead. 

### 8.2 Structure
If you are using the [Zapier CLI](https://platform.zapier.com/reference/cli-docs) to build the integration, ensure files are logically broken out into respective directories and the code is easy to follow. We suggest putting triggers, actions, and searches each in their own directories.


If you have any questions or concerns about our integration review guidelines, contact Zapier via the [contact form](https://developer.zapier.com/contact).
