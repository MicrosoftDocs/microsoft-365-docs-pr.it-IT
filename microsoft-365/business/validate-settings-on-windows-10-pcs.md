---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informazioni su come verificare le impostazioni di protezione di applicazioni Microsoft 365 Business nei dispositivi Windows 10.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868446"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="82121-103">Verificare le impostazioni di protezione nei PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="82121-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="82121-104">Verificare che siano impostati i criteri per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="82121-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="82121-p101">Dopo aver [configurato i criteri per i dispositivi](protection-settings-for-windows-10-pcs.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti. Per verificare che i criteri siano stati applicati, esaminare le diverse schermate delle impostazioni di Windows sui dispositivi degli utenti. Gli utenti non possono modificare le impostazioni di Windows Update e Windows Defender Antivirus nei dispositivi Windows 10, quindi molte di queste opzioni saranno disattivate.</span><span class="sxs-lookup"><span data-stu-id="82121-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="82121-108">Passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Update** \> **riavviare le opzioni** e verificare che tutte le impostazioni sono in grigio.</span><span class="sxs-lookup"><span data-stu-id="82121-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="82121-110">Passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Update** \> **Opzioni avanzate** e verificare che tutte le impostazioni sono in grigio.</span><span class="sxs-lookup"><span data-stu-id="82121-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="82121-112">Passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Update** \> **Opzioni avanzate** \> **scegliere la modalità di recapito degli aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="82121-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="82121-113">Verificare che il messaggio che indica che alcune impostazioni sono nascoste o gestite dall'organizzazione sia visibile (in rosso) e che tutte le opzioni siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="82121-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="82121-115">Per aprire il Centro protezione di Windows Defender, passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Defender** \> fare clic su **Centro protezione di Apri Windows Defender** \> **Virus &amp; thread protezione** \> **Virus &amp; le impostazioni di protezione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="82121-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="82121-116">Verificare che tutte le opzioni siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="82121-116">Verify that all options are greyed out.</span></span> 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="82121-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="82121-118">Related Topics</span></span>

[<span data-ttu-id="82121-119">Documentazione e risorse su Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="82121-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="82121-120">Introduzione a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="82121-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="82121-121">Gestire Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="82121-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="82121-122">Impostare le configurazioni dei dispositivi per PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="82121-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

