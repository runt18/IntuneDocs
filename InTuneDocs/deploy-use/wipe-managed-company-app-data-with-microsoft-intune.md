---
# required metadata

title: Wipe managed company app data | Microsoft Docs
description: Learn how you can selectively remove company data from devices remotely.
keywords:
author: stabarms.author: staciebarkermanager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wipe managed company app data with Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

When a device is lost or stolen, or if the employee leaves your company, you want to make sure company app data is removed from the device. But you might not want to remove personal data on the device, especially if this is an employee-owned device.

To selectively remove company app data, create a wipe request by using the steps in this topic. After the request is finished, the next time the app runs on the device, company data is removed from the app.
>[!NOTE]
> Contacts synced directly from the app to the native address book are removed. Any contacts synced from the native address book to another external source cannot be wiped. Currently, this applies only to the Microsoft Outlook app.



## Create a wipe request

1.  Sign in to the Azure portal, and choose **More Services** > **Other** > **Intune**.

2.  On the Intune blade, choose **Manage apps** > **App Selective Wipe**.

3.  Choose  **New wipe request**. The **New wipe request** blade opens.

    ![Screenshot of the New wipe request blade](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Choose **User** to open the **User** blade, and select the user whose app data you want to wipe.

5.  Choose **Device**.  This opens the **Device** blade that lists all the devices associated with the selected user.  Select the device you want to wipe.

6.  You are now back on the **New wipe request** blade. Choose **Ok** to make a wipe request. The service creates and tracks a separate wipe request for each protected app on the device.

![Screenshot of the Wipe requests tile ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## Monitor your wipe requests

On the **Wipe request** tile, there is a summarized report that shows the overall status of the wipe request, and includes the number of pending requests and failures. To get more details, follow these steps:

1.  On the Intune blade, choose **Manage apps**.

2.  On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.

3.  On the **Wipe request** blade, you can see the list of your requests grouped by users. Because the system creates a wipe request for each protected app running on the device, you might see multiple requests for a user. The status indicates whether a wipe request is **pending**, **failed**, or **successful**.

The user must open the app for the wipe to occur, and the wipe may take up to 30 minutes after the request was made.

Wipes with pending status are displayed until you manually delete them.  To manually delete a wipe request, right-click and choose delete.

### See also
[Protect app data using mobile app management policies ](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Using the Azure portal](azure-portal-for-microsoft-intune-mam-policies.md)
