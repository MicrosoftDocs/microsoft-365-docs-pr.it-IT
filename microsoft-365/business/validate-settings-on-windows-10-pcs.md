---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informazioni su come verificare che le impostazioni di protezione delle app di Microsoft 365 for business siano state applicate nei dispositivi Windows 10 degli utenti.
ms.openlocfilehash: b63681f040b0fe49127693e9cb7aac7ba6c41af6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635705"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="05bc9-103">Verificare le impostazioni di protezione nei PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="05bc9-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="05bc9-104">Verificare che siano impostati i criteri per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="05bc9-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="05bc9-105">Dopo aver [configurato i criteri per i dispositivi](protection-settings-for-windows-10-pcs.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="05bc9-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="05bc9-106">Per verificare che i criteri siano stati applicati, esaminare le diverse schermate delle impostazioni di Windows sui dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="05bc9-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="05bc9-107">Poiché gli utenti non saranno in grado di modificare le impostazioni di Windows Update e Windows Defender antivirus nei dispositivi Windows 10, molte opzioni saranno disabilitate.</span><span class="sxs-lookup"><span data-stu-id="05bc9-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="05bc9-108">Passare a **Impostazioni** \> \*\*aggiornare &amp; \*\* le opzioni di sicurezza \> di **Windows Update** \> **Restart** e verificare che tutte le impostazioni siano disabilitate.</span><span class="sxs-lookup"><span data-stu-id="05bc9-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Tutte le opzioni di riavvio sono disattivate.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="05bc9-110">Andare a **Impostazioni** \> \*\*aggiornare &amp; \*\* le opzioni di sicurezza \> di **Windows Update** \> **Advanced** e verificare che tutte le impostazioni siano disabilitate.</span><span class="sxs-lookup"><span data-stu-id="05bc9-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Le opzioni di Windows Advanced Updates sono tutte disabilitate.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="05bc9-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="05bc9-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="05bc9-113">Confermare che è possibile visualizzare il messaggio (in rosso) che alcune impostazioni sono nascoste o gestite dall'organizzazione e tutte le opzioni sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="05bc9-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="05bc9-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="05bc9-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="05bc9-116">Verificare che tutte le opzioni siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="05bc9-116">Verify that all options are grayed out.</span></span> 
    
    ![Le impostazioni relative a virus e protezione dalle minacce sono disattivate.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="05bc9-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="05bc9-118">Related Topics</span></span>

[<span data-ttu-id="05bc9-119">Documentazione e risorse su Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="05bc9-119">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="05bc9-120">Introduzione a Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="05bc9-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="05bc9-121">Gestire Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="05bc9-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="05bc9-122">Impostare le configurazioni dei dispositivi per PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="05bc9-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

