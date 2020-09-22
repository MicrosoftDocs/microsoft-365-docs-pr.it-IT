---
title: Integrare Office 365 ATP con Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrazione di Office 365 Advanced Threat Protection con Microsoft Defender Advanced Threat Protection per visualizzare informazioni più dettagliate sulla gestione delle minacce.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201972"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="1b180-103">Integrazione di Office 365 Advanced Threat Protection con Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1b180-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1b180-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) può essere configurato per l'utilizzo con [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span><span class="sxs-lookup"><span data-stu-id="1b180-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="1b180-105">L'integrazione di Office 365 ATP con Microsoft Defender ATP può aiutare le operazioni di sicurezza del team monitor e intervenire rapidamente se i dispositivi degli utenti sono a rischio.</span><span class="sxs-lookup"><span data-stu-id="1b180-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="1b180-106">Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente coinvolti da un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti di tali dispositivi in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="1b180-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="1b180-107">Nell'immagine seguente viene illustrato l'aspetto della scheda **dispositivi** con l'integrazione ATP di Microsoft Defender abilitata:</span><span class="sxs-lookup"><span data-stu-id="1b180-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Quando Microsoft Defender ATP è abilitato, è possibile visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="1b180-109">In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso.</span><span class="sxs-lookup"><span data-stu-id="1b180-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="1b180-110">Se si fa clic sul collegamento di un dispositivo, viene aperta la relativa pagina nel centro protezione Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="1b180-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="1b180-111">Per **[ulteriori informazioni, vedere Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (denominato anche Microsoft Defender ATP Portal).</span><span class="sxs-lookup"><span data-stu-id="1b180-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1b180-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b180-112">Requirements</span></span>

- <span data-ttu-id="1b180-113">L'organizzazione deve disporre di Office 365 ATP piano 2 (o Office 365 E5) e Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="1b180-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="1b180-114">È necessario essere un amministratore globale o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato [nel &amp; centro conformità sicurezza](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="1b180-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="1b180-115">(Vedere [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="1b180-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="1b180-116">È necessario disporre dell'accesso sia all' [esploratore (o ai rilevamenti in tempo reale)](threat-explorer.md) nel centro sicurezza & compliance e al Centro protezione Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1b180-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="1b180-117">Per integrare Office 365 ATP con Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1b180-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="1b180-118">L'integrazione di Office 365 ATP con Microsoft Defender ATP è configurata utilizzando il Centro sicurezza & compliance e il Centro protezione Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1b180-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="1b180-119">Come amministratore globale o amministratore della sicurezza, accedere a [https://protection.office.com](https://protection.office.com) e accedere.</span><span class="sxs-lookup"><span data-stu-id="1b180-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="1b180-120">(Questo porta al centro sicurezza & conformità di Office 365).</span><span class="sxs-lookup"><span data-stu-id="1b180-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="1b180-121">Nel riquadro di spostamento, scegliere **gestione minacce**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="1b180-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="1b180-122">![Explorer nel menu Gestione minacce](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="1b180-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="1b180-123">Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.</span><span class="sxs-lookup"><span data-stu-id="1b180-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="1b180-124">Nella finestra di dialogo Microsoft Defender ATP Connection, abilitare **Connect to Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="1b180-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="1b180-125">![Connessione ATP Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="1b180-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="1b180-126">Accedere a Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="1b180-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="1b180-127">Nella barra di spostamento, scegliere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="1b180-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="1b180-128">Quindi, in **generale**, scegliere **funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="1b180-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="1b180-129">Scorrere verso il basso fino a **Office 365 Threat Intelligence Connection**e quindi accendere la connessione.</span><span class="sxs-lookup"><span data-stu-id="1b180-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="1b180-130">![Connessione di Microsoft Threat Intelligence di Office 365](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="1b180-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="1b180-131">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="1b180-131">Related articles</span></span>

[<span data-ttu-id="1b180-132">Analisi delle minacce e funzionalità di risposta in Office 365</span><span class="sxs-lookup"><span data-stu-id="1b180-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="1b180-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1b180-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1b180-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1b180-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
