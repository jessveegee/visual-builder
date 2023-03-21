---
title: Zap Editor
order: 4
layout: post-toc
redirect_from:
  - /embed/
  - /partner_api/
  - /partner_api/introduction
---

# Embedding the Zap Editor

By embedding our Zap Editor in your product, your users can create and edit their Zaps without leaving your product.

## Creating Zaps from Zap Templates

Use the Partner API to query the public Zap templates featuring your integration (using the [`GET /v1/zap-templates`](./partner-api#get-v1zap-templates) endpoint) and feature them in your product. When a user chooses a Zap template they’d like to try, use the `create_url` value as the source to load in an embedded frame such as:

```html
<iframe src="https://api.zapier.com/v1/embed/trello/create/113"></iframe>
```

Where `https://api.zapier.com/v1/embed/trello/create/113` is the `create_url` value of the Zap template.

Optionally, you can add additional parameters to the `create_url` to prefill the user’s Zap with custom values (e.g., specifying a workspace for the trigger to filter by).

## Creating Zaps without Zap Templates

You can also facilitate a user's Zap creation via URL parameters instead of an existing Zap Template. This provides flexibility to redirect users to a pre-populated Zap Editor with known context from your app without publishing a Zap Template for each specific use case. Use this URL schema for your embedded editor experience or as lightweight entry point into the Zap Editor from your app. Similar to the [prefill](https://platform.zapier.com/embed/zap-editor#prefill-options) options for automatically defining field values for users, you can prefill apps, events, and input field values in the Zap Editor with the following URL schema:

Base URL: `https://zapier.com/webintent/create-zap?`

URL parameters (with example values):

- Trigger app (required): `steps[0][app]=MailchimpCLIAPI@latest` 
- Trigger event: `steps[0][action]=new_member`
- Trigger field prefills: `steps[0][params][list_id]=123`
- Action app: `steps[1][app]=GoogleAdsCLIAPI@latest`
- Action event: `steps[1][action]=add_to_customer_list_v2`
- Action field prefills: `steps[1][params][list_id]=234`

Requirements:

- A trigger app is required. The `steps` index for a trigger is always `0`.
- An app is defined by `SelectedAPI@version` where SelectedAPI generally equals a titleized string of the app name + `CLIAPI` (e.g., MailchimpCLIAPI, GoogleAdsCLIAPI, FacebookLeadAdsCLIAPI). This value is case-sensitive.
- The version for the app can be specified or set to `latest` (highly suggested) to automatically point to the current production version (e.g., MailchimpCLIAPI@latest, MailchimpCLIAPI@1.0.0).
- You can define 0 to many subsequent action steps. The `steps` index for actions will be `1` or greater. Please note, only users on a paid Zapier plan have access to multi-step Zaps.
- Events are defined by the `key` of the trigger, action, or search.
- Field prefills are defined by the `key` of the input field. See the below [Prefill Options](https://platform.zapier.com/embed/zap-editor#prefill-options) for more details on prefilling fields.

Examples:

Defining a trigger and action app
> `https://zapier.com/webintent/create-zap?steps[0][app]=MailchimpCLIAPI@latest&steps[1][app]=GoogleAdsCLIAPI@latest`

Defining a trigger and trigger event with no action:
> `https://zapier.com/webintent/create-zap?steps[0][app]=MailchimpCLIAPI@latest&steps[0][action]=new_member`

Defining a trigger and trigger event with a prefilled value for the "Audience" input field:
> `https://zapier.com/webintent/create-zap?steps[0][app]=MailchimpCLIAPI@latest&steps[0][action]=new_member&steps[0][params][list_id]=123`

Defining a trigger, trigger event, action, and action event with prefilled values for "Audience" and "Customer List" input fields:
> `https://zapier.com/webintent/create-zap?steps[0][app]=MailchimpCLIAPI@latest&steps[0][action]=new_member&steps[0][params][list_id]=123&steps[1][app]=GoogleAdsCLIAPI@latest&steps[1][action]=add_to_customer_list_v2&steps[1][params][customer_list_id]=234`

Defining a trigger and two actions:
> `https://zapier.com/webintent/create-zap?steps[0][app]=MailchimpCLIAPI@latest&steps[1][app]=GoogleAdsCLIAPI@latest&steps[2][app]=FacebookLeadAdsCLIAPI@latest`

## Editing a Zap

Use the Partner API to load a user’s Zaps (using the [`GET /v1/zaps`](./partner-api#get-v1zaps) endpoint). When the user chooses to open or edit a Zap use the the `url` value of the Zap as the source of an embedded frame such as:

```html
<iframe src="https://zapier.com/app/editor/123456"></iframe>
```

Where `https://zapier.com/app/editor/123456` is the `url` of the Zap to be edited.

Additionally, if you’d prefer, you can open these URLs in a separate window, new tab, or popup just as well.

## Prefill Options

Prefills allow you to define the fields on behalf of the user, thus simplying the experience of setting up their Zap.

You'll use the `create_url` (available in a [Zap template object](/partner_api/endpoints#zap-template)) in order to create the Zap. Next, you will add parameters to the `create_url` so that the user's Zap is prefilled with the provided custom values.

> Note: You will need to know the fields that your app requires per step. You can find the fields as defined in your Zapier integration.

**Example**

You can prefill the name of a Trello card (field: `name`) in the second step of the Zap template:

> `https://api.zapier.com/v1/embed/trello/create/113?steps[1][params][name]=hello`

- `template=113`
- `steps[1][params][name]=hello`


Here's what it would look like in the editor:

![Zap Editor showing "hello" pre-filled into the name field of a new Zap titled Create Card in Trello](https://cdn.zappy.app/5db273249f668a1520e1632cf331a141.png)

You can prefill multiple values for the user. In this example `name` and `desc` are prefilled

> `https://api.zapier.com/v1/embed/trello/create/113?steps[1][params][name]=yoyoyo&steps[1][params][desc]=yeehaw`

- `template=113`
- `steps[1][params][name]=yoyoyo`
- `steps[1][params][desc]=yeehaw`

![Zap Editor showing "yoyoyo" pre-filled into the name field, and "yeehaw" pre-filled into the description field of a new Zap titled Create Card in Trello](https://cdn.zappy.app/35882f8b86dade9e41c13cdbd0baf03c.png)

You can provide a label for prefill dropdowns as we won't fetch all of the pages of choices until the user opens the dropdown:

> `https://api.zapier.com/v1/embed/trello/create/113?steps[1][params][board]=1234&steps[1][meta][parammap][board]=Test`

- `template=113`
- `steps[1][params][board]=1234`
- `steps[1][meta][parammap][board]=Test`


![Zap Editor showing "Test" pre-filled into the board field of a new Zap titled Create Card in Trello](https://cdn.zappy.app/fd9fd4872773018bfd15dfebea0795a4.png)

## `postMessage` events

If you decide to embed the Zapier Editor within your product you can listen to [message events from `postMessage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/message_event) which can help you improve the interactivity with the iframe (e.g. automatically close the iframe modal.)

The messages available include:

- `zap:unpause` = Zap turned on / published
- `zap:unpause:done` = Zap turned on / published (success)
- `zap:unpause:fail` = Zap turned on / published (failure)
- `zap:pause` = Zap turned off
- `zap:pause:done` = Zap turned off (success)
- `zap:pause:fail` = Zap turned off (failure)

## Turning off a Zap

The API does not currently have an endpoint to turn off/on a user's Zaps. If your Zapier app uses Webhook Subscriptions, you can send a `DELETE` to the webhook subscription URL and that will then pause/turn off a Zap.
