---
summary: Manage QUERY_ALL_PACKAGES permission in Android apps using AppShield on OutSystems Developer Cloud (ODC) for Google Play compliance.
tags: android development, google play compliance, app security, mobile app security
locale: en-us
guid: c8e9533c-1f33-407f-b3f6-523ac67ad126
app_type: mobile apps
platform-version: odc
figma:
audience:
  - mobile developers
outsystems-tools:
  - appshield
  - odc studio
content-type:
  - procedure
  - conceptual
---

# Query All Packages permission in Android apps using AppShield

<div class="info" markdown="1">

Applies only to Mobile Apps.

</div>

This article applies to Mobile Apps generated for Android that use AppShield. This article is for developers responsible for securing Mobile Apps from tampering and are familiar with mobile development and AppShield.

Android 11 (Android R) introduces the **QUERY_ALL_PACKAGES** permission. This permission enables an app to query the full list of apps installed on an Android device. AppShield uses the **QUERY_ALL_PACKAGES** permission for some security checks. To learn more about it, refer [QUERY_ALL_PACKAGES](https://support.google.com/googleplay/android-developer/answer/10158779).

## Ensure your apps are compliant

Starting 20th July 2022, apps targeting Android 11 or above must include a declaration to use the QUERY_ALL_PACKAGES permission. This has implications for your apps and you must take action.
After this date, you won’t be able to submit app updates if your app uses the **QUERY_ALL_PACKAGES** permission and the declaration is missing. Furthermore, your app may be removed from Google Play.

To ensure your apps are complaint, follow one of these options for each app:

* If your app needs PCI (Payment Card Industry) compliance, fill in a Permissions Declaration Form requesting the use of **QUERY_ALL_PACKAGES**. Check how to [keep using the permission and provide a declaration](#query).

* Otherwise, remove the **QUERY_ALL_PACKAGES** permission from your app. Check how to [remove the permission request from your app](#no-query)

## Keep the QUERY_ALL_PACKAGES permission and provide a declaration { #query }

If your application requires PCI compliance, continue to use the QUERY_ALL_PACKAGES permission and ask Google for permission to use the permission. Do the following:

1. Ensure you are using AppShield Plugin version 1.0 or higher.

1. Add the following preference to your app's **Extensibility Options**:

        "RemoveQueryAllPackagesPermission":"false"

1. Generate a new Android package for your app and submit your updated app to Google Play.

1. Then, fill in a Permissions Declaration Form requesting the use of **QUERY_ALL_PACKAGES** permission. Check [how to do this in Google's documentation](https://support.google.com/googleplay/android-developer/answer/9214102). If your app needs to be PCI compliant, we suggest you provide the following information in your Google Play application:

        This application requires using the QUERY_ALL_PACKAGES for Payment Card Industry compliance (PCI) purposes. This software implements a required mechanism to determine whether or not the device contains one or more apps originating from non-trusted sources. Such sources can be third-party app stores, or locally side-loaded apps. The information is only processed inside the app for this purpose.

## Remove the QUERY_ALL_PACKAGES permission from your app { #no-query }

If your app doesn't require PCI compliance, remove the QUERY_ALL_PACKAGES permission from your app by doing the following:

1. Ensure you are using AppShield Plugin version 1.0 or higher.

1. Add the following preference to your app's **Extensibility Options**:

        "RemoveQueryAllPackagesPermission":"true"

1. Generate a new Android package for your app and submit your updated app to Google Play.

