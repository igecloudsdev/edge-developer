---
title: Handle links to a PWA
description: How links to your Progressive Web App (PWA) can be handled by your app rather than by the web browser.
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: conceptual
ms.service: microsoft-edge
ms.subservice: pwa
ms.date: 09/15/2022
---
# Handle links to a PWA

A Progressive Web App (PWA) on the device's operating system can handle links, so that when an associated URL is activated, the PWA can request to be launched instead of the web browser, to create a more engaging experience.

This link handling is like how native apps handle links on many operating systems.

<!--
link handling vs. url handling:
Although the present file name is handle-urls.md, this file was repurposed to cover link handling rather than URL handlers.
The PWA URL handlers feature was removed from Chromium.
See also [PWAs as URL Handlers](https://web.dev/pwa-url-handler/).
-->


<!-- ====================================================================== -->
## Automatic link handling

The operating system that your PWA is installed on automatically launches your PWA for any link that refers to content that's within the scope of the PWA, when either of the following conditions are met:

* The PWA was installed from the Microsoft Store on Windows.
* The PWA was installed by using Microsoft Edge, and Microsoft Edge is the default browser on the device.

No code is required for automatic link handling to work, but end users can opt-out of automatic link handling. To opt-out of automatic link handling:

1. In Microsoft Edge, navigate to `edge://apps`.

1. Find the PWA you want to disable automatic link handling for and click **Details**.

1. On the PWA details page, under the **Link handling** section, click the toggle button.

![The edge://apps details page for the PWAmp music player app, showing where the link handling toggle button is](./handle-urls-images/link-handling-opt-out.png)


<!-- ====================================================================== -->
## Handle links from other origins by using scope extensions

Scope extensions make it possible for a PWA to capture navigation to paths, subdomains, or even sites other than its own scope.  This can be useful for PWAs that span multiple domains for localization purposes.  For example, a PWA may span `contoso.com`, `contoso.co.uk`, and `contoso.fr`.

The manifest of a PWA defines which part of the hosting domain the PWA is scoped to.  For example, the `www.contoso.com` domain name may have a PWA defined under `www.contoso.com/app` with its scope set to `/app`.  In this case, all the web pages available within the `www.contoso.com/app` path are part of the PWA scope.  However, the web pages within the `www.contoso.com/foo` path are not part of the PWA scope.  Furthermore, web pages that are available at `bar.contoso.com/app` or `www.contoso.co.uk` are also not part of the PWA scope.


<!-- ------------------------------ -->
#### Origin trial

As of October 17, 2024, the scope extensions feature is an origin trial.  For status, see [Web app scope extensions feature](https://chromestatus.com/feature/5746537956114432) at Chrome Platform Status.

When the feature can be used in Microsoft Edge and is no longer in origin trial, the feature will be documented in the present article.  See [Scope Extensions for Web Apps](https://github.com/WICG/manifest-incubations/blob/gh-pages/scope_extensions-explainer.md), an Explainer in the **manifest-incubations** repo.

See also:
* [Use origin trials in Microsoft Edge](../../origin-trials/index.md)


<!-- ====================================================================== -->
## See also

* [PWAs as URL Handlers](https://web.dev/pwa-url-handler/)
