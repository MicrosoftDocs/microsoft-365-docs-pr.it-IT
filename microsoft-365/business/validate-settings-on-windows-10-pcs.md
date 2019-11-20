---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informazioni su come convalidare le impostazioni di protezione delle app di Microsoft 365 nei dispositivi Windows 10.
ms.openlocfilehash: b8793ab7f77bbc7f608f237e2455f6fd12c3bb26
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721801"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="ee619-103">Verificare le impostazioni di protezione nei PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="ee619-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="ee619-104">Verificare che siano impostati i criteri per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="ee619-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="ee619-105">Dopo aver [configurato i criteri per i dispositivi](protection-settings-for-windows-10-pcs.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ee619-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="ee619-106">Per verificare che i criteri siano stati applicati, esaminare le diverse schermate delle impostazioni di Windows sui dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ee619-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="ee619-107">Poiché gli utenti non saranno in grado di modificare le impostazioni di Windows Update e Windows Defender antivirus nei dispositivi Windows 10, molte opzioni saranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="ee619-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="ee619-108">Passare a **Impostazioni** \> \*\*aggiornare &amp; \*\* le opzioni di sicurezza \> di **Windows Update** \> **Restart** e verificare che tutte le impostazioni siano disabilitate.</span><span class="sxs-lookup"><span data-stu-id="ee619-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Tutte le opzioni di riavvio sono disattivate.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="ee619-110">Andare a **Impostazioni** \> \*\*aggiornare &amp; \*\* le opzioni di sicurezza \> di **Windows Update** \> **Advanced** e verificare che tutte le impostazioni siano disabilitate.</span><span class="sxs-lookup"><span data-stu-id="ee619-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Le opzioni di Windows Advanced Updates sono tutte disabilitate.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="ee619-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="ee619-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="ee619-113">Confermare che è possibile visualizzare il messaggio (in rosso) che alcune impostazioni sono nascoste o gestite dall'organizzazione e tutte le opzioni sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="ee619-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="ee619-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="ee619-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="ee619-116">Verificare che tutte le opzioni siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="ee619-116">Verify that all options are grayed out.</span></span> 
    
    ![Le impostazioni relative a virus e protezione dalle minacce sono disattivate.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="ee619-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ee619-118">Related Topics</span></span>

[<span data-ttu-id="ee619-119">Documentazione e risorse su Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ee619-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="ee619-120">Introduzione a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ee619-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="ee619-121">Gestire Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ee619-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="ee619-122">Impostare le configurazioni dei dispositivi per PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="ee619-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

