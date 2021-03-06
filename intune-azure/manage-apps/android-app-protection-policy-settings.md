---
# required metadata

title: Android app protection policy settings | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: This topic describes the app protection policy settings for Android devices."
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Android app protection policy settings
The policy settings that are described in this topic can be [configured](app-protection-policies.md) for an app protection policy on the **Settings** blade in the Azure portal.
There are two categories of policy settings: data relocation settings and access settings. In this topic, the term *policy-managed apps* refers to apps that are configured with app protection policies.

##  Data relocation settings

| Setting | How to use | Default value(s) |
|------|------|------|
| **Prevent Android backups** | Choose **Yes** to prevent this app from backing up work or school data to the [Android Backup Service](https://developer.android.com/google/backup/index.html) Choose **No** to allow this app to back up work or school data.| Yes |
| **Allow app to transfer data to other apps** | Specify what apps can receive data from this app: <ul><li> **Policy managed apps**: Allow transfer only to other policy-managed apps.</li> <li>**All apps**: Allow transfer to any app. </li> <li>**None**: Do not allow data transfer to any app, including other policy-managed apps.</li></ul> | All apps |
| **Allow app to receive data from other apps** | Specify what apps can transfer data to this app: <ul><li>**Policy managed apps**: Allow transfer only from other policy-managed apps.</li><li>**All apps**: Allow data transfer from any app.</li><li>**None**: Do not allow data transfer from any app, including other policy-managed apps. | All apps |
| **Prevent "Save As"** | Choose **Yes** to disable the use of the Save As option in this app. Choose **No** if you want to allow the use of Save As. | No |
| **Restrict cut, copy and paste with other apps** | Specify when cut, copy, and paste actions can be used with this app. Choose from: <ul><li>**Blocked**:  Do not allow cut, copy, and paste actions between this app and any other app.</li><li>**Policy managed apps**: Allow cut, copy, and paste actions between this app and other policy-managed apps.</li><li>**Policy managed with paste in**: Allow cut or copy between this app and other policy-managed apps. Allow data from any app to be pasted into this app.</li><li>**Any app**: No restrictions for cut, copy, and paste to and from this app. | Any app |
|**Restrict web content to display in the Managed Browser** | Choose **Yes** to enforce web links in the app to be opened in the Managed Browser app. <br><br> For devices not enrolled in Intune, the web links in policy-managed apps can open only in the Managed Browser app. <br><br> If you are using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-internet-access-using-managed-browser-policies). | No |
| **Encrypt app data** | Choose **Yes** to enable encryption of work or school data in this app. Intune uses an OpenSSL encryption scheme along with the Android Keystore system to securely encrypt app data. Data is encrypted synchronously during file I/O tasks. Content on the device storage is always encrypted. <br><br> The encryption method is **not** FIPS 140-2 certified.  | Yes |
| **Disable contact sync** | Choose **Yes** to prevent the app from saving data to the native Contacts app on the device. If you choose **No**, the app can save data to the native Contacts app on the device. <br><br>When you perform a selective wipe to remove work or school data from the app, contacts synced directly from the app to the native Contacts app are removed. Any contacts synced from the native address book to another external source cannot be wiped. Currently this applies only to the Microsoft Outlook app. | No |
| **Disable printing** | Choose **Yes** to prevent the app from printing work or school data. | No |


  >[!NOTE]
  >The encryption method for the **Encrypt app data** setting is **not** FIPS 140-2 certified.




##  Access settings

| Setting | How to use | Default value(s) |
|------|------|------|
| **Require PIN for access** | Choose **Yes** to require a PIN to use this app. The user is prompted to set up this PIN the first time they run the app in a work or school context. Default value = **Yes**.<br><br> Configure the following settings for PIN strength: <ul><li>**Number of attempts before PIN reset**: Specify the number of tries the user has to successfully enter their PIN before they must reset it. Default value = **5**.</li><li> **Allow simple PIN**: Choose **Yes** to allow users to use simple PIN sequences like 1234 or 1111. Choose **No** to prevent them from using simple sequences. Default value = **Yes**. </li><li> **PIN length**: Specify the minimum number of digits in a PIN sequence. Default value = **4**. </li><li> **Allow fingerprint instead of PIN (Android 6.0+)**: Choose **Yes** to allow the user to use [fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) instead of a PIN for app access. Default value = **Yes**.<br><br> On Android devices, you can let the user prove their identity by using [Android fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) instead of a PIN. When the user tries use this app with their work or school account, they are prompted to provide their fingerprint identity instead of entering a PIN. </li></ul>| Require PIN: Yes <br><br> PIN reset attempts: 5 <br><br> Allow simple PIN: Yes <br><br> PIN length: 4 <br><br> Allow fingerprint: Yes |
| **Require corporate credentials for access** | Choose **Yes** to require the user to sign in with their work or school account instead of entering a PIN for app access. If you set this to **Yes**, this overrides the requirements for PIN or Touch ID.  | No |
| **Block managed apps from running on jailbroken or rooted devices** |  Choose **Yes** to prevent this app from running on jailbroken or rooted devices. The user will continue to be able to use this app for personal tasks, but will have to use a different device to access work or school data in this app. | Yes |
| **Recheck the access requirements after (minutes)** | Configure the following settings: <ul><li>**Timeout**: Specify the time (in minutes) before the access requirements for the app are rechecked. Default value = **30** minutes.</li><li>**Offline grace period**: If the device is offline, specify the time (in minutes) before the access requirements for the app are rechecked. Default value = **720** minutes (12 hours).</li></ul>| Timeout: 30 <br><br> Offline: 720 |
| **Offline interval before app data is wiped (days)** | Work or school data in this app can be wiped if a device has been offline for more than a certain period. Specify the number of days a device can be offline before the work or school data is removed from the device. <br><br> | 90 days |
| **Block screen capture and Android Assistant (Android 6.0+)** | Choose **Yes** to block screen capture and the **Android Assistant** capabilities of the device when using this app. Choosing **Yes** will also blur the App-switcher preview image when using this app with a work or school account. | No |
