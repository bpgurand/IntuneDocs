---
# required metadata

title: Company portal enrollment abandonment in Intune
titlesuffix: "Microsoft Intune"
description: Learn about the company portal abandonment report.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started

---

# Company portal abandonment report

This report tells you where in the Company Portal enrollment users are abandoning the enrollment process.

To see the report, choose **Intune** > **Device enrollment** > **Company portal abandonment**.

Using this abandonment information, you can update your onboarding documents to help users complete enrollment. For example, if many users are quitting at the Terms of Use, you might investigate that area and make it more intuitive for users.

## What is abandonment?

Abandonment is when a user does any of the following:

-	Explicitly chooses an action to halt enrollment
-	Closes the Company Portal during enrollment
-	Spends more than 30 minutes between enrollment sections

If a user chooses to stop enrollment and restart multiple times, it shows up as multiple attempts and multiple abandonments. If a user waits for 30 minutes between different enrollment screens, it is considered multiple abandonments.

## What does the report show?

The enrollment reports include data for iOS and Android devices.

The reports show data for the past two weeks, but you can filter the report to show any period up to 30 days in the past.

You can filter the date range, operating system, and enrollment section by choosing **Filter**.

### Number and percentage tiles

At the top of the report, you can see the number and percentage of abandoned reports in relation to all enrollments.

-	Initiated enrollments: The number of enrollments attempted.
-	Abandoned enrollments: The number of attempted enrollments that didn’t result in a fully enrolled and compliant device.
-	Abandonment rate: The percentage of enrollment attempts that were abandoned (Abandoned enrollments / Initiated enrollments).

### Line graph

The line graph shows the daily abandonments for each of the four core enrollment sections:

-	Setup checklist
-	Platform screens
-	Terms of use
-	Compliance/Activation

### User abandonment actions

The following tables show the list of user actions that qualify as abandonment. To see examples of enrollment screens, you can watch the [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) and [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment) enrollment videos. 


#### Setup checklist section

| Abandonment name | Screen or flow | Platform | Action |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Prompt to open page in Company Portal | iOS/Android | **Cancel** |
| EnrollmentWrapUp | Enrolling device screen until finish of **Loading company resources** | iOS/Android | Took > 30 minutes |
| DeviceCategory | Device Category selection (if admin configured) until click **Done** | iOS/Android | Took > 30 minutes |
| PreEnrollmentWizard | Set up access screen when having started enrollment but returned to Set up access | iOS/Android| **Postpone** |
| PreEnrollmentWizard | Set up access screen until clicking **Next** on the **What’s Next** screen | iOS/Android | Took > 30 minutes |

#### Platform screens section

| Abandonment name | Screen or flow | Platform | Action |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Prompt to show a configuration profile | iOS | **Ignore** |
| iOSProfileLaunch | Installing profile screen | iOS | **Cancel** |
| iOSProfileLaunch | Prompt to trust the profile’s source to enroll the device | iOS | **Cancel** |
| iOSProfileLaunch | Install profile screen until profile is installed | iOS | Took > 30 minutes |
| AndroidPermissions | Device administrator activation screen | Android | **Cancel** |
| AndroidPermissions | From prompt for approval to make and manage phone calls until device administrator **Activate** | Android | Took > 30 minutes |
| KnoxActivation | KLMS agent activation (Samsung only) | Android| **Cancel** |
| KnoxActivation | KLMS agent activation until **Confirm** | Android | Took > 30 minutes|

#### Terms of use section

| Abandonment name | Screen or flow | Platform | Action |
| ---- |---- |---- |---- |
| TermsofUse | Terms of use (if admin configured) | iOS/Android | **Decline All** |
| TermsofUse | Terms of use until **Accept all** | iOS/Android | Took > 30 minutes |

#### Compliance/Activation section

| Abandonment name | Screen or flow | Platform | Action |
| ---- |---- |---- |---- |
| Compliance | Device compliance (if admin configured) shows as non-green on access setup post enrollment| iOS/Android | **Postpone** |
| Compliance | Device compliance shows as non-green until updated to show green | iOS/Android | Took > 30 minutes |
| Activation | Enrollment activation  (if admin configured) shows as non-green on access setup | iOS/Android | **Postpone** |
| Compliance | Device activation shows as non-green until updated to show green | iOS/Android | Took > 30 minutes |

## Next steps

After checking on your abandonment rates, you can review the [enrollment options](enrollment-options.md) to see if you can make any changes to improve enrollment.