---
title: Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
keywords: integrare, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Usa Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint per ottenere informazioni più dettagliate sulle minacce ai dispositivi e al contenuto di posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904081"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="2c0c4-104">Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c0c4-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2c0c4-105">[Microsoft Defender per Office 365](defender-for-office-365.md) può essere configurato per l'utilizzo con [Microsoft Defender for Endpoint.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="2c0c4-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="2c0c4-106">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint può aiutare il team delle operazioni di sicurezza a monitorare e intervenire rapidamente se i dispositivi degli utenti sono a rischio.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="2c0c4-107">Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente interessati da un messaggio di posta elettronica rilevato e il numero di avvisi recenti generati per tali dispositivi in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="2c0c4-108">L'immagine seguente illustra  l'aspetto della scheda Dispositivi quando è abilitata l'integrazione di Microsoft Defender per endpoint:</span><span class="sxs-lookup"><span data-stu-id="2c0c4-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Quando Microsoft Defender for Endpoint è abilitato, puoi visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="2c0c4-110">In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="2c0c4-111">Facendo clic sul collegamento per un dispositivo viene aperta la pagina [in Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (in precedenza Microsoft Defender Security Center).</span><span class="sxs-lookup"><span data-stu-id="2c0c4-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="2c0c4-112">Il portale Microsoft 365 Defender sostituisce il Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="2c0c4-113">Vedi [Microsoft Defender per Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="2c0c4-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="2c0c4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c0c4-114">Requirements</span></span>

- <span data-ttu-id="2c0c4-115">L'organizzazione deve disporre di Microsoft Defender per Office 365 (o Office 365 E5) e Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="2c0c4-116">È necessario essere un amministratore globale o disporre di un ruolo di amministratore della sicurezza (ad esempio Amministratore della sicurezza) in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="2c0c4-117">(Vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="2c0c4-117">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="2c0c4-118">Devi avere accesso a [Esplora risorse (o ai rilevamenti in tempo reale).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="2c0c4-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="2c0c4-119">Per integrare Microsoft Defender per Office 365 con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c0c4-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="2c0c4-120">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint è impostata sia in Defender per Endpoint che in Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="2c0c4-121">In quanto amministratore globale o amministratore della sicurezza, passare a [https://protection.office.com](https://protection.office.com) e accedere.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-121">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="2c0c4-122">Questa operazione consente di accedere al Centro Office 365 sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-122">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="2c0c4-123">Nel riquadro di spostamento scegliere **Esplora gestione** \> **minacce**.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-123">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Esplora risorse nel menu Gestione minacce](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="2c0c4-125">Nell'angolo in alto a destra dello schermo scegli **Defender per Endpoint Impostazioni (MDE Impostazioni).**</span><span class="sxs-lookup"><span data-stu-id="2c0c4-125">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="2c0c4-126">Nella finestra di dialogo Connessione a Microsoft Defender for Endpoint, attivare Connessione **a Microsoft Defender for Endpoint.**</span><span class="sxs-lookup"><span data-stu-id="2c0c4-126">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Connessione a Microsoft Defender for Endpoint](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="2c0c4-128">Passare al portale Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="2c0c4-128">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="2c0c4-129">Nella barra di spostamento scegliere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-129">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="2c0c4-130">In Generale **scegliere** Quindi **Funzionalità avanzate.**</span><span class="sxs-lookup"><span data-stu-id="2c0c4-130">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="2c0c4-131">Scorri verso il basso **Office 365 threat intelligence e** attiva la connessione.</span><span class="sxs-lookup"><span data-stu-id="2c0c4-131">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 di intelligence sulle minacce](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="2c0c4-133">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="2c0c4-133">Related articles</span></span>

[<span data-ttu-id="2c0c4-134">Funzionalità di indagine e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="2c0c4-134">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="2c0c4-135">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2c0c4-135">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="2c0c4-136">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2c0c4-136">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
