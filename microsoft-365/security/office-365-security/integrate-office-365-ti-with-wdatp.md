---
title: Usare Microsoft Defender per Office 365 insieme a Microsoft Defender per Endpoint
f1.keywords:
- NOCSH
keywords: integrare, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint per ottenere informazioni più dettagliate sulle minacce contro i dispositivi e sul contenuto della posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166088"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="78265-104">Usare Microsoft Defender per Office 365 insieme a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="78265-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="78265-105">[Microsoft Defender per Office 365](office-365-atp.md) può essere configurato per l'utilizzo [con Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="78265-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="78265-106">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint può aiutare il team delle operazioni di sicurezza a monitorare e intervenire rapidamente se i dispositivi degli utenti sono a rischio.</span><span class="sxs-lookup"><span data-stu-id="78265-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="78265-107">Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente interessati da un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti generati per tali dispositivi in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="78265-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="78265-108">L'immagine seguente illustra  l'aspetto della scheda Dispositivi quando è abilitata l'integrazione di Microsoft Defender per endpoint:</span><span class="sxs-lookup"><span data-stu-id="78265-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Quando Microsoft Defender for Endpoint è abilitato, puoi visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="78265-110">In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso.</span><span class="sxs-lookup"><span data-stu-id="78265-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="78265-111">Facendo clic sul collegamento per un dispositivo viene aperta la relativa pagina in Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="78265-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="78265-112">**[Altre informazioni su Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (noto anche come portale di Microsoft Defender per endpoint).</span><span class="sxs-lookup"><span data-stu-id="78265-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="78265-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78265-113">Requirements</span></span>

- <span data-ttu-id="78265-114">L'organizzazione deve disporre di Microsoft Defender per Office 365 (o Office 365 E5) e Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="78265-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="78265-115">È necessario essere un amministratore globale o disporre di un ruolo di amministratore della sicurezza (ad esempio amministratore della sicurezza) assegnato nel Centro [sicurezza & conformità.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="78265-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="78265-116">(Vedere [Autorizzazioni nel Centro sicurezza & conformità)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="78265-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="78265-117">Devi avere accesso a [Esplora risorse (o](threat-explorer.md) ai rilevamenti in tempo reale) nel Centro sicurezza & conformità e in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="78265-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="78265-118">Per integrare Microsoft Defender per Office 365 con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="78265-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="78265-119">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint viene impostata tramite il Centro sicurezza & conformità e Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="78265-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="78265-120">In quanto amministratore globale o amministratore della sicurezza, accedere <https://protection.office.com> a e accedere.</span><span class="sxs-lookup"><span data-stu-id="78265-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="78265-121">In questo modo si viene al Centro sicurezza & conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="78265-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="78265-122">Nel riquadro di spostamento scegliere **Esplora gestione** \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="78265-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Esplora risorse nel menu Gestione minacce](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="78265-124">Nell'angolo in alto a destra dello schermo scegliere **Defender per Impostazioni endpoint (impostazioni MDE).**</span><span class="sxs-lookup"><span data-stu-id="78265-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="78265-125">Nella finestra di dialogo di connessione di Microsoft Defender for Endpoint, attivare **Connetti a Microsoft Defender per Endpoint.**</span><span class="sxs-lookup"><span data-stu-id="78265-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Connessione Microsoft Defender for Endpoint](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="78265-127">Passare a Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="78265-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="78265-128">Nella barra di spostamento scegliere **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="78265-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="78265-129">In Generale **scegliere** Quindi **Funzionalità avanzate.**</span><span class="sxs-lookup"><span data-stu-id="78265-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="78265-130">Scorrere verso il basso fino alla connessione di **Office 365 Threat Intelligence** e attivare la connessione.</span><span class="sxs-lookup"><span data-stu-id="78265-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Connessione intelligence per le minacce di Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="78265-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="78265-132">Related articles</span></span>

[<span data-ttu-id="78265-133">Funzionalità di analisi e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="78265-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="78265-134">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="78265-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="78265-135">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="78265-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
