---
title: Convalidare le impostazioni di protezione delle app Windows 10 PC
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Scopri come verificare che le impostazioni di Microsoft 365 per le app aziendali siano applicate ai dispositivi Windows 10 degli utenti.
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925260"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="59001-103">Convalidare le impostazioni di protezione dei Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="59001-103">Validate device protection settings for Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="59001-104">Verificare che siano impostati i criteri per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="59001-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="59001-105">Dopo aver [configurato i criteri per i dispositivi](protection-settings-for-windows-10-pcs.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="59001-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="59001-106">Per verificare che i criteri siano stati applicati, esaminare le diverse schermate delle impostazioni di Windows sui dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="59001-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="59001-107">Poiché gli utenti non saranno in grado di modificare le impostazioni di Windows Update e Windows Defender Antivirus nei dispositivi Windows 10, molte opzioni saranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="59001-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="59001-108">Vai **a** Impostazioni aggiorna la sicurezza Windows opzioni di riavvio dell'aggiornamento e verifica che tutte le impostazioni \> **&amp;** \>  \>  siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="59001-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Tutte le opzioni di riavvio sono disattivate.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="59001-110">Vai a **Impostazioni** aggiornamento della sicurezza Windows Opzioni avanzate di aggiornamento e verifica che tutte le impostazioni \> **&amp;** \>  \>  siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="59001-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows Le opzioni degli aggiornamenti avanzati sono tutte disattivate.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="59001-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="59001-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="59001-113">Verificare che sia possibile visualizzare il messaggio (in rosso) che alcune impostazioni sono nascoste o gestite dall'organizzazione e che tutte le opzioni sono in grigio.</span><span class="sxs-lookup"><span data-stu-id="59001-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="59001-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="59001-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="59001-116">Verificare che tutte le opzioni siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="59001-116">Verify that all options are grayed out.</span></span> 
    
    ![Le impostazioni di Protezione da virus e minacce sono disattivate.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="59001-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="59001-118">Related Topics</span></span>

[<span data-ttu-id="59001-119">Microsoft 365 documentazione e risorse per le aziende</span><span class="sxs-lookup"><span data-stu-id="59001-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="59001-120">Introduzione a Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="59001-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="59001-121">Gestire Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="59001-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="59001-122">Impostare le configurazioni dei dispositivi per PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="59001-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
