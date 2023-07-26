---
title: Preparing for API Outages
order: 9
layout: post-toc
---

# Preparing for API Outages

Zapier recognises that temporary unavailability is sometimes inevitable for your API. To accommodate these situations, we recommend configuring [custom error response handling](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md#general-errors) to:
- Present a meaningful, user-friendly message to users
- Refrain from disabling Zaps due to error-ratio
- Potentially reattempt the action after a given delay window

## Default Behaviour

Zap Runs that encounter a 5xx error will throw an exception and receive the “Stopped / Errored” status. This will [display an error message to the user](https://help.zapier.com/hc/en-us/articles/8496291148685#stopped-0-1); allowing them to replay the Run.
 
If the user has [Autoreplay](https://help.zapier.com/hc/en-us/articles/8496241726989-Replay-failed-Zap-runs#how-autoreplay-works-0-4) enabled, then the errored steps will be retried on [a defined schedule](https://help.zapier.com/hc/en-us/articles/8496241726989-Replay-failed-Zap-runs#how-autoreplay-works-0-4). Only when all Autoreplay attempts have also failed will the Zap Run be assigned the “Stopped / Errored” status.
 
If [95% of a Zap’s Runs in the last 7 days are assigned the “Stopped / Errored” status](https://help.zapier.com/hc/en-us/articles/8496037690637-Troubleshoot-errors-in-Zapier#500-series-error-codes-0-3), the Zap will be paused automatically. The Zap will not run again until the user manually enables it.

## Avoiding automatic Zap disablement

**If you use [the Zapier Platform CLI](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md)**, you'll be able to [make use of HTTP middleware](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md#using-http-middleware) to implement [custom error response handling](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md#error-handling). This will allow you to write a single script that applies across the entire integration to detect a specific error from the API, and act accordingly.
For example, if the API’s outage duration is known, you could catch HTTP503 responses during the afterResponse middleware and throw a [`ThrottledError`](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md#handling-throttled-requests) like this:

```js
const yourAfterResponse = (resp) => {
  if (resp.status === 503) {
    throw new z.errors.ThrottledError('Service is temporarily unavailable. Retrying in 60 seconds.', 60);  // Zapier will retry in 60 seconds
  }
  return resp;
};
```
> **Note:** Don’t forget to set [`skipThrowForStatus`](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md#http-response-object) to `true` when invoking `z.request()`!

**If you use the [Zapier Platform UI](https://developer.zapier.com/)**, you can also implement custom error handling, although it needs to be added to each individual element of the integration (triggers, actions, authentication).
To do this, you will need to ensure that:
each request made by your integration is [configured using Code Mode](https://platform.zapier.com/build/action#how-to-use-custom-code-in-zapier-actions),
the script checks for the HTTP status expected during downtime, and
throws [a custom error](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md#error-handling) instead of returning data back to the Zap.

For example:

![custom_error_UI](https://cdn.zappy.app/f9f04386f19f0e9f7f107ea8d0d6e3b7.png)

> **Note:** Integrations built with the Zapier Platform UI can enable the skipThrowForStatus toggle to On to use [`skipThrowForStatus:true`](https://cdn.zappy.app/8ac6af91f6b27c4a473d566f1534b27e.png) on every request

> **Note:** Integrations built with the Zapier Platform UI can easily [switch to Zapier CLI](https://platform.zapier.com/manage/export-integration) at any time.

## Specifying how long Zapier should wait before retrying

The `ThrottledError(message,delay)` method accepts two input parameters; a custom error message (string) and a delay expressed in seconds (integer). By including a Retry-After header with responses provided during downtime, an API can specify the amount of time until the service is expected to be back online and Zapier should retry the request.
Your [custom error handling script](https://github.com/zapier/zapier-platform/blob/main/packages/cli/README.md#error-response-handling) can read this header and pass it to the delay parameter for `ThrottledError()`, like this:

```js
if(response.status === 503){
    const delay = response.getHeader('retry-after');
    const message = `Service is temporarily unavailable. Retrying in ${delay} seconds.`;
    throw new z.errors.ThrottledError(message,delay);
}
```
## Scheduled API Maintenance

For periods of scheduled maintenance, a status of an app (API) as "unhealthy" can be set between a specific start and end time. A "Scheduled Maintenance" message will then be posted to our [status page](https://status.zapier.com) for [example](https://status.zapier.com/incidents/njgw7lrhn5hs).

![scheduled_maintenance](https://cdn.zappy.app/2ae85a1cd6d00981ed30af8eede5938b.png)

The app will also have a status of "unhealthy" on the [_App Status_ tab.](https://status.zapier.com/#app-status)

During a set maintenance window, Zaps impacted by the downtime will be affected as follows:

**Actions/Searches:** Zap Runs with affected actions/searches will have the status of “Playing” in the Zap History page. The action/search will be delayed until the incident resolves, or up to five times. On the fifth time, Zapier will attempt it regardless of the app status. If it fails, Zap Runs will error and [normal manual replay mechanisms](https://help.zapier.com/hc/en-us/articles/8496241726989-Replay-failed-Zap-runs) can be used to try to replay any affected Zap Runs.

**Triggers:** _most_ Zaps with affected (polling) triggers won't run and so (for the most part) there will be no Zap Runs in [Zap History](https://help.zapier.com/hc/en-us/articles/8496291148685-View-and-manage-your-Zap-history). 

In more detail, Zapier will "skip" 90% of polls, allowing 10% through, so typically _some_ runs will occur for _some_ Zaps. After 15 minutes, all polling is re-enabled to check if the API is healthy again. If not, Zapier will again "skip" 90% of polls. This will be repeated until the API is healthy.
Once the API is healthy, Zaps will be triggered and "catch up" on missed data, subject to normal polling limitations such as [pagination](https://platform.zapier.com/build/trigger#how-to-use-pagination).
 
If Zap Runs error users will be notified via email based on their [notification settings](https://help.zapier.com/hc/en-us/articles/8496289225229-Manage-notifications-when-errors-occur-in-Zaps). 
 
If you would like to schedule a maintenance window for your app, please send across the following information to [Developer Support](https://developer.zapier.com/contact) 

1. Start date and time (in UTC)
2. End date and time (in UTC)
3. Further details about how the API will respond during the downtime if called; eg. will it return an [HTTP 503](https://www.webfx.com/web-development/glossary/http-status-codes/what-is-a-503-status-code/) "Service Unavailable" status code or not respond at all.
