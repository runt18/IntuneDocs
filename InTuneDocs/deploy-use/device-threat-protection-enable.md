---
# required metadata

title: Enable Lookout MTP in Intune | Microsoft Docs
description: Enable Lookout mobile threat protection in the Intune admin console.
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enable Lookout MTP connection in the Intune admin console

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

To enable the Lookout malicious threat protection (MTP) connection in Intune, you should have already configured the Intune Connector in the Lookout console.  If you have not already done so, you should [Set up your subscription with Lookout mobile threat protection](set-up-your-subscription-with-lookout-mtp.md).

To enable the Lookout MTP connection in Intune, on the **Administration** page in the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Third Party Service Integration**. Choose **Lookout status** and enable **Synchronization with MTP** using the toggle button.

![screenshot of the Lookout synchronization page with the enable toggle button highlighted](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> You **must** configure the Lookout for Work app before creating compliance policy rules and configuring conditional access. This ensures that the app is ready and available for end users to install before they can get access to email or other company resources.

This completes the setup of the Lookout and Intune integration in the Intune administrator console.  The next few steps to implement this solution involve deploying the [Lookout for Work apps](configure-and-deploy-lookout-for-work-apps.md) and setting up the [compliance](enable-device-threat-protection-rule-in-compliance-policy.md) policy.


## Next steps
[Configure Lookout for Work app ](configure-and-deploy-lookout-for-work-apps.md)
