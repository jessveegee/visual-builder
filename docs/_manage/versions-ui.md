---
title: Manage versions integration in Platform UI
order: 7
layout: post-toc
redirect_from: /docs/versions
---

# Manage versions integration in Platform UI

Your Zapier integration should be ready to use when first launched—minimal, perhaps, but with the basics covered. The app authentication will let users connect to your API, and the triggers and actions should get data to and from your API.

Over time, though, things will change. Users will request new triggers and actions, or want to send and receive more data with your existing ones. You’ll add new features to your app and want to add them to your Zapier integration, too. And eventually, your API may change, and your Zapier integration’s authentication or API calls may need to be changed as well.

That’s where versions come in. Zapier lets you create multiple versions of your integration to test and build new features without interrupting existing users. You can then release the new version to some users, ensure everything is working, and eventually migrate all of your users to the new version. After that, you can deprecate and remove the old version.

This guide will cover the steps for _Cloning_, _Promoting_, _Migrating_, and _Deprecating_ integration versions in more detail. Put briefly, the process of creating a new version of your integration takes three steps in either the Developer Platform [UI](https://developer.zapier.com/) or [Zapier Command Line Interface](https://platform.zapier.com/quickstart/platform-cli-tutorial) (CLI).

In the Visual Builder:

1. In the sidebar on the left, navigate to **Manage**, then **Versions**
2. Select the gear icon next to the version you’d like to update, then select **Clone**
3. Select a new version number, then **Clone** and **Edit** to create the new version and begin editing it

Using the Zapier CLI:

1. Increment the version number in your app’s `package.json` file
2. Make the necessary updates to the rest of the app’s resources
3. Run [`zapier push`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#push) to build and upload the new version to Zapier

This guide is intended to cover version management in the Visual Builder. If you're using the CLI, we recommend reading the [CLI version tutorial](https://platform.zapier.com/manage/versions-cli).

## Which Version Can Users Access?

A Zapier integration can be either _Private_, _Beta_, or _Public_. Private integrations require an [invitation](https://platform.zapier.com/manage/share-integration) for users to access it. Public and Beta integrations can be seen by Zapier users on [the public Apps page](https://zapier.com/apps). Each integration can have many versions, but only one version can be public at a time, while the rest remain private. 

Newly published integrations will feature a _Beta_ tag when first published. While your [integration is in Beta](https://platform.zapier.com/publish/public-integration#5-beta-phase), we’ll monitor how it’s performing. When your integration reaches 50 users, our team will get in touch to invite you to start the [official partner program](https://zapier.com/platform/partner-program) launch process.

To review your integration’s versions, open it in the Visual Builder and navigate to Manage then Versions. This page shows a list of all versions of the integration, along with status and the number of users of each.

![The Versions page in the Zapier Developer Platform](https://cdn.zappy.app/b443129368e61bdaa86c6f5a741fbe8a.png)

> **Note:** In the Zapier CLI, you can also run [`zapier versions`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#versions) to see the information in your terminal.

For Public apps, which are searchable in the Zap Editor/App Directory, a user that selects your integration in the Zap Editor will be using the current Public version by default. Optionally, you can use the **Sharing** page to [send users an invitation](https://platform.zapier.com/manage/share-integration) to a specific private version, which will allow them to select it in the Zap Editor. This is also how all users of Private integrations are added.

## Making Changes

To make edits to a version of your integration in the Developer Platform Visual Builder, select it in the Version dropdown menu in the top right, or select **Edit** from the options menu on the Versions page.

![Highlighting the Version dropdown menu](https://cdn.zappy.app/61956b1f6879fc95f6cd421d02ec45ef.png)
![Edit option on the Versions page](https://cdn.zappy.app/dcad96f8ee8e2751829cbf42504aa974.png)

Clicking **Edit** will direct you to the page of that version. You can then make changes to any of the sections: _Authentication_, _Triggers_, _Actions_, and _Advanced_. Saving those changes will automatically apply them to the version (and by extension, any Zaps using it). 

While using the Zapier CLI, you can change which version you are editing by updating the version number in your `package.json` file. When you run [`zapier push`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#push) your code will overwrite the specified version. While optional, we also recommend using version control software, such as GitHub or GitLab, to keep track of previous versions of your code.

## Why Can’t I Edit a Particular Version?

To make sure that existing Zaps can continue to work consistently, the Zapier Developer Platform only allows you to edit versions that are Private and have fewer than 5 users. Versions that are Public or have more than 5 users will show a warning message prompting you to Clone the version instead.

!['You can't edit this version'](https://cdn.zappy.app/8b5cbf5a37ce60ba89eb555c0429eca6.png)

## Cloning

_Cloning_ is a process in the Zapier Developer Platform Visual Builder that allows you to create a new version of your integration, based on a previous one. 

> **Note:** While the term “cloning” doesn’t appear in the Zapier CLI, this is equivalent to updating the version number in `package.json` and running [`zapier push`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#push) to create a new version. 

To clone a version of your integration, navigate to **Manage** then **Versions** in the Visual Builder, and select the **gear icon** next to the version you’d like to duplicate. 

![Selecting the 'Clone' option](https://cdn.zappy.app/46ff6be376f18abc74cbf3ed3836b28e.png)

That will open a window that prompts you to select a number for the new version, to help represent the kinds of changes you plan on making.

![The 'Clone Version' window, showing the options for a new version number](https://cdn.zappy.app/b4b841aa1dccab5a87854ae815418de5.png)

Zapier uses semantic versioning numbers, which gives you three options to choose from:

* **Patch** (e.g. 1.0.0 to 1.0.1) can be used for changes that are still compatible with the previous version, such as fixing a bug or updating help text.
* **Minor** (e.g. 1.0.0 to 1.1.0) is recommended for changes that add new functionality without changing what’s already there, such as creating a new trigger or action.
* **Major** (e.g. 1.0.0 to 2.0.0) is used when making changes that are likely to break existing Zaps, such as removing triggers or actions, changing authentication methods, or starting over from scratch.

Select the version that feels correct based on your plans, then click **Clone** to create the new version and start editing it.

## Promoting a Version

After your integration has entered the _Beta_ or _Public_ status, one of its versions also becomes _Public_, meaning users see and use it by default. The process of changing which version is Public is called _Promotion_, and can be done from either the CLI or the Versions page. 

In the CLI, running [`zapier promote [version]`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#promote) will make the specified version number the new Public version. [Read more about that here](https://platform.zapier.com/reference/cli-docs#promoting-an-app-version).

In the Visual Builder, head to **Manage** then **Versions**, and select the **gear icon** next to the version you’d like to make public. In the menu that appears, select **Promote**.

![Selecting 'Promote' on the Versions page](https://cdn.zappy.app/bb69d022902a74466427d24a67c6a8a3.png)

If you’re working with an integration that’s currently private, the _Promote_ option won’t appear. Instead, make sure users you’d like to test or move to the new integration version are invited to that version, and encourage them to try it out.

### What Happens When a Version Is Promoted?

* [Zap templates](https://platform.zapier.com/publish/zap-templates) are updated to use the new Public version of your app if there are no breaking changes
* Any new triggers or actions will appear on your integration’s public app page
* When a user selects your integration in a new Zap, they’ll use the promoted version by default

## Migrating Users

Once you’ve added all the changes needed to your integration, you can start rolling it out to users to update their existing Zaps and let users make new Zaps with your new integration features.

If you made a new version with only minor, non-breaking changes ([read more about breaking changes here](#what-is-a-breaking-change)), you can migrate existing users and Zaps to your new integration version. On the **Versions** page, select the **Migrate** option on your new integration version.

![Selecting the 'Migrate' option on the Versions page](https://cdn.zappy.app/90f865924add0a028c8300d33dba09e6.png)

That will reveal a screen that will allow you to move users between two versions. Select the _From_ and _To_ versions, then select **Migrate** to begin moving users to the selected version.

![After selecting 'Migrate', the Migration window allows you to select 'From' and 'To' versions](https://cdn.zappy.app/39081a9504f64333e48bd9d84e6c758e.png)

When migrating users, you are also migrating their Zaps. This means that any active Zaps using the _From_ version will begin using the _To_ version as soon as the migration is complete. This makes it a great solution for Patch and Minor updates, but _not_ a recommended option for Major updates. For Major updates, review our section on [Deprecation](#deprecating-versions) instead.

In some cases, it may be more useful to migrate only a portion of the current users, to ensure that the minor change did not accidentally introduce any unforeseen issues. You can do that using the **Percentage** option in the Migration window, or select **Email** to migrate only one user at a time.

![Using the Percentage slider to migrate only 55% of users](https://cdn.zappy.app/68a6701f418dbda95771258703cc609a.png)

> **Warning:** By default, migrating a single user with the "migrate by email" option will only migrate Zaps that are *private to that user*—owned by the user, are not shared, and whose integration auths are not shared.

You can then repeat the Migration process later on, and migrate the rest of the users once you are comfortable with how the new version is running in production.

> **Note:** It is also possible to migrate a portion of users with the CLI using the [`zapier migrate`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#migrate) command. [Read more about that here](https://platform.zapier.com/reference/cli-docs#deploying-an-app-version). 

### What Is a “Breaking Change”?

Before performing a migration, it is important to consider all Zaps which are currently running on previous versions of your integration. The configuration of these Zaps will not be modified during the migration, so they will need to be capable of functioning correctly on both the old and new versions.

Because of that, a “breaking change” can be defined as any modification to the integration which renders existing Zaps incompatible with the new version. Examples include:

* Changing the Authentication scheme
* Adding a new "required" input field or making a previously optional input field “required”
* Removing a trigger/action
* Changing the key of a trigger/action or any input field
* Removing an input or output field on a trigger/action

## Deprecating Versions

_Deprecation_ is an optional process that allows you to set a date from which a non-Public version of your integration will no longer be supported. This is only applicable after promoting a major update which cannot support automatic migration of users due to breaking changes **and** when the older version will no longer function.

Setting a deprecation date needs to be between 2 weeks and 1 year in the future.

Upon deprecation, two automatic communications are sent by Zapier. We recommend also announcing the changes/new integration version to your general user base via in-app or email marketing. For privacy reasons, Zapier is unable to provide an email list of your app’s Zapier integration users.

Please note that deprecating a version is significantly more disruptive to our mutual users than migrating to the latest promoted version, or than leaving users on an older (now) private version if migration is not possible.

Users with Zaps on any older Private versions will still have access to those older Private versions in the Zap Editor after a new version has been promoted. However, users who have no Zaps on older versions will only see the current Public (promoted) version. [This help page](https://help.zapier.com/hc/en-us/articles/8496295729421-What-are-legacy-and-deprecated-apps-#1-optional-duplicate-your-zap-0-0) provides users with information about this.

To deprecate a Private version, select the **gear icon** next to the version number on the Versions page, then select **Deprecate**.

![The window that opens when selecting 'Deprecate'](https://cdn.zappy.app/948f09e34a01aca849952b71474a522b.png)

> **Note:** You can also set a deprecation date using the CLI, with the [`zapier deprecate`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#deprecate) command. [More about that here](https://platform.zapier.com/reference/cli-docs#promoting-an-app-version).

Once a deprecation date is set, Zapier sends [email notification #1](https://cdn.zappy.app/147e8ce1de24c6f799afac516112bbd0.png) to that version’s users, to notify them that a new Public version is available, and that action is required on their part to manually update their Zaps and ensure that the new version fits their workflows.

Once the deprecation date is reached, if the Zaps weren’t updated, they’ll automatically be paused and [email notification #2](https://cdn.zappy.app/f6920ad2c38bc8e52cc09420ed47e73e.png) is sent to any remaining users - with the subject line "X Zaps paused over deprecated apps!". It is not possible to customize that email to include a change log to let users know what the differences are.

Once the deprecation date is reached, they’ll also start seeing it as “Deprecated” in the Zap Editor along with the [prompt to update to the latest version.](https://cdn.zappy.app/551bc24447db12241e1b0bf2452b7c15.png)

After the deprecation date has passed, the version will still be available in the [Versions page of your integration](https://cdn.zappy.app/7015fc0393d6e687b3eb4d1070977c93.png) for future reference. You can (but should not) even invite users to it with the options in the Sharing page, like you would with any Private version.

### Should I Deprecate or Delete?

It’s also possible to _Delete_ versions from the Versions page. That option will fully remove the version from your Zapier integration, meaning that neither you nor users will be able to access it from that time — so use it with caution! 

In most cases, either deprecation or leaving a private version untouched are recommended, and deletion should only be used when you're absolutely sure that the version will never be used again.

## Can I Start Over?

In some cases, it may make sense to rebuild your integration from scratch. For example, if your company has introduced a new product, or if the API that was originally used with the integration is now considered “Legacy”. There’s also a chance that it’s just been a while since you’ve used Zapier, and you wish to refresh your knowledge of the Developer Platform.

Because our mutual users see your Zapier integration as an extension of your brand, we do not allow creating separate integrations in these cases. Even if the new integration is clearly labelled as “New App!” or “App V2”, having two separate versions of your brand available often causes confusion amongst users, so we have this restriction in place to prevent them selecting the wrong version by mistake.

Instead, we recommend cloning the latest version of your integration, and picking the **Major** version number change. The triggers, actions, and even authentication of the new version can be changed entirely, so that the update looks and feels like a brand new app, but maintains the brand consistency for our end users.

> **Note:** With the Zapier CLI, you can start a brand new project and "link" the new code to your existing integration with the [`zapier link`](https://github.com/zapier/zapier-platform/blob/master/packages/cli/docs/cli.md#link) command.

It is also possible to change which development environment your integration is built in, to help make the experience of building the new version easier for your team:

If your integration was built with our [Visual Builder](https://developer.zapier.com), you can export and convert it to the Zapier CLI using [the steps provided here](https://platform.zapier.com/manage/export-integration). The CLI gives full control over your integration’s code, and is a great fit for teams of developers who are used to sharing code via tools like GitHub or GitLab.

Alternatively, if your integration was built with the Zapier CLI, and your team would prefer to use our Visual Builder moving forward, please [contact our Support team](https://developer.zapier.com/contact) to let us know. In some cases, we can create a new version of your integration that can be edited on the Visual Builder, while allowing the existing CLI integration to continue running.
