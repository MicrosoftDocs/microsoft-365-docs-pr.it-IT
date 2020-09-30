---
title: Utilizzare Microsoft Defender per Office 365 insieme a Microsoft Defender per endpoint
f1.keywords:
- NOCSH
keywords: integrazione, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Utilizzare Microsoft Defender per Office 365 insieme a Microsoft Defender Advanced Threat Protection per ottenere informazioni più dettagliate sulle minacce nei confronti dei dispositivi e del contenuto della posta elettronica.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c95e15c3cf16547843f9d2976dbf9df0d5747c0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309238"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="30e73-104">Utilizzare Microsoft Defender per Office 365 insieme a Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="30e73-104">Use Microsoft Defender for Office 365 together with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="30e73-105">[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) può essere configurato per l'utilizzo con [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="30e73-105">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="30e73-106">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender per endpoint può essere di aiuto per il monitoraggio del team delle operazioni di sicurezza e per intervenire rapidamente se i dispositivi degli utenti sono a rischio.</span><span class="sxs-lookup"><span data-stu-id="30e73-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="30e73-107">Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente interessati da un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti generati per i dispositivi in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="30e73-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="30e73-108">Nell'immagine seguente viene illustrato l'aspetto della scheda **dispositivi** con Microsoft Defender for endpoint Integration abilitato:</span><span class="sxs-lookup"><span data-stu-id="30e73-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![Quando Microsoft Defender per endpoint è abilitato, è possibile visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="30e73-110">In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso.</span><span class="sxs-lookup"><span data-stu-id="30e73-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="30e73-111">Se si fa clic sul collegamento di un dispositivo, viene aperta la relativa pagina nel centro protezione Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="30e73-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="30e73-112">Per **[ulteriori informazioni, vedere Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (denominato anche Microsoft Defender ATP Portal).</span><span class="sxs-lookup"><span data-stu-id="30e73-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="30e73-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30e73-113">Requirements</span></span>

- <span data-ttu-id="30e73-114">L'organizzazione deve disporre di Microsoft Defender per Office 365 (o Office 365 E5) e Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="30e73-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="30e73-115">È necessario essere un amministratore globale o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato [nel &amp; centro conformità sicurezza](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="30e73-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="30e73-116">(Vedere [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="30e73-116">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="30e73-117">È necessario disporre dell'accesso sia all' [esploratore (o ai rilevamenti in tempo reale)](threat-explorer.md) nel centro sicurezza & compliance e al Centro protezione Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="30e73-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="30e73-118">Per integrare Microsoft Defender per Office 365 con Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="30e73-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="30e73-119">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender per endpoint è configurata utilizzando il Centro sicurezza & compliance e il Centro sicurezza Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="30e73-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="30e73-120">Come amministratore globale o amministratore della sicurezza, accedere a [https://protection.office.com](https://protection.office.com) e accedere.</span><span class="sxs-lookup"><span data-stu-id="30e73-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="30e73-121">(Questo porta al centro sicurezza & conformità di Office 365).</span><span class="sxs-lookup"><span data-stu-id="30e73-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="30e73-122">Nel riquadro di spostamento, scegliere **gestione minacce**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="30e73-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="30e73-123">![Explorer nel menu Gestione minacce](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="30e73-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="30e73-124">Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.</span><span class="sxs-lookup"><span data-stu-id="30e73-124">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="30e73-125">Nella finestra di dialogo Microsoft Defender for endpoint Connection, abilitare la **connessione a Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="30e73-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="30e73-126">![Microsoft Defender per la connessione dell'endpoint](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="30e73-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="30e73-127">Accedere a Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="30e73-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="30e73-128">Nella barra di spostamento, scegliere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="30e73-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="30e73-129">Quindi, in **generale**, scegliere **funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="30e73-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="30e73-130">Scorrere verso il basso fino a **Office 365 Threat Intelligence Connection**e quindi accendere la connessione.</span><span class="sxs-lookup"><span data-stu-id="30e73-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="30e73-131">![Connessione di Microsoft Threat Intelligence di Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="30e73-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="30e73-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="30e73-132">Related articles</span></span>

[<span data-ttu-id="30e73-133">Analisi delle minacce e funzionalità di risposta in Office 365</span><span class="sxs-lookup"><span data-stu-id="30e73-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="30e73-134">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="30e73-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="30e73-135">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="30e73-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
