---
title: Zapier integration tips
order: 6
layout: post-toc
redirect_from: /partners/faq
---

# Zapier integration tips

Before developing your Zapier integration, it’s important to be familiar with the criteria Zapier uses to review all new integrations. Follow our [Integration Branding and Design Guidelines](https://platform.zapier.com/publish/intergration-brand-design-guidelines) when building your integration.

The following tips are based on the most common issues we encounter and will help you successfully launch your integration. Check out [Common Migration Errors](https://platform.zapier.com/manage/troubleshoot-versions) for tips if you're ready to deploy a new version of your integration.

## Get familiar with Zapier

If you haven't used Zapier before, [sign up](https://zapier.com/sign-up/) for a free account and try a few popular integrations before building your own. This helps you understand how Zapier works, how your users will set up Zaps, and how your integration can best fit into Zap workflows.

## Focus on key use cases

Your initial Triggers, Actions, and Searches should cover the main functionality users perform on your platform to maximize utility. Check similar integrations in [Zapier's App Directory](https://zapier.com/apps/) to get ideas on which items to include in your integration. Consistently monitor feature requests from users to fill in any gaps in functionality.

## Test early with real users

Hopefully, you have a bunch of keen users waiting to get their hands on your Zapier integration; don't be afraid to reach out to them for early testing. Active usage gives us confidence your integration is useable and functionally valuable for numerous users. Make sure to test the integration early and often in the Zap Editor yourself!

## Maintain consistency in your integration style

Users should be familiar with the terminology used in your Zapier integration. The input and output field labels, and trigger/action/search names must be consistent with the terminology used in your platform's own UI. It should also be consistent with the style used in other popular Zapier integrations.

We strive to give users a consistent experience throughout Zapier. Be sure to follow [Zapier's standards for app branding](https://platform.zapier.com/publish/intergration-brand-design-guidelines#how-to-brand-your-zapier-integration) so your integration fits well into the Zapier ecosystem.

## Make connecting new accounts easy

Connecting to Zapier must be easy for the user. OAuth v2 is the preferred authentication scheme; otherwise, users must be able to easily retrieve or generate an API Key or other credentials themselves without needing support. Both authentication and test authentication requests should return actionable, user-friendly error messages to guide users in successfully connecting their accounts.

## Ensure your integration is complete and platform consistent

Only submit your integration for review when it is complete and ready to be published. Make sure to thoroughly test your integration for edge cases, fix all bugs, and address [integration checks](https://platform.zapier.com/publish/integration-checks-reference) before submitting. Confirm your integration adheres to our [Integration Review Guidelines](https://platform.zapier.com/publish/integration-publishing-guidelines thoroughly. Please ensure both your platform and integration work consistently without errors.

## Use Zapier Issue Manager

Use Zapier Issue Manager to sync and manage issues for your Zapier integration from your own issue-tracking tools (such as Jira or Trello). [Learn more and request access to Zapier Issue Manager here.](https://platform.zapier.com/publish/zapier-issue-manager)

## Provide a valid test account

When submitting your integration for review, we require a valid, non-expiring test account under `integration-testing@zapier.com`. During the review and going forward after launch, our team may need occasional access for troubleshooting support issues. Please ensure the account is not under a trial and all necessary paid/premium features are unlocked.

## Avoid misleading or malicious functionality

Your integration must perform as advertised and must not give users a false impression. If it appears to promise certain features and functionalities, it needs to deliver. Do not create a Zapier integration that can be used to spam, phish, or send unsolicited messages to users.

Violations of the review process or guidelines can have your integration removed from Zapier, and you could be banned from submitting more in the future.

## Add collaborators to your team

Bring your team onboard by inviting other team members to your integration as Collaborators. Collaborators can log into your Zapier dashboard and gain valuable insights into your integration—including what your customers are saying about it. They can view performance data, see feature requests and bugs, and access tools to embed Zapier integrations inside your UI to rack up user adoption. 

### Find a Zapier integration partner

We're excited to help you with your Zapier integration, but we can't build it for you. If you're looking for someone to take over the technical reins, check our list of [Zapier trusted app developers
](/partners/trusted-developers) to find someone who can help develop a Zapier integration for you.

### Our pledge to Zapier Platform partners

At Zapier, our mission is to make automation work for everyone, so every person and business can move forward at growth speed. Our Zapier Platform partners and ecosystem are essential to achieving this mission. [Read more about how we support and grow our ecosystem of Platform partners](https://zapier.com/l/partner-pledge).
