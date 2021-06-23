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
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083381"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="64f5f-104">Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="64f5f-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="64f5f-105">[Microsoft Defender per Office 365](defender-for-office-365.md) può essere configurato per l'utilizzo con [Microsoft Defender for Endpoint.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="64f5f-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="64f5f-106">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint può aiutare il team delle operazioni di sicurezza a monitorare e intervenire rapidamente se i dispositivi degli utenti sono a rischio.</span><span class="sxs-lookup"><span data-stu-id="64f5f-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="64f5f-107">Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente interessati da un messaggio di posta elettronica rilevato e il numero di avvisi recenti generati per tali dispositivi in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="64f5f-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="64f5f-108">L'immagine seguente illustra  l'aspetto della scheda Dispositivi quando è abilitata l'integrazione di Microsoft Defender per endpoint:</span><span class="sxs-lookup"><span data-stu-id="64f5f-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Quando Microsoft Defender for Endpoint è abilitato, puoi visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="64f5f-110">In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso.</span><span class="sxs-lookup"><span data-stu-id="64f5f-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="64f5f-111">Facendo clic sul collegamento per un dispositivo viene aperta la pagina [nel portale Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (in precedenza il Centro sicurezza Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="64f5f-111">Clicking the link for a device opens its page in [the Microsoft 365 Defender portal](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender security center).</span></span>

> [!TIP]
> <span data-ttu-id="64f5f-112">Il Microsoft 365 Defender portale sostituisce il Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="64f5f-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="64f5f-113">Vedi [Microsoft Defender per Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="64f5f-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="64f5f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64f5f-114">Requirements</span></span>

- <span data-ttu-id="64f5f-115">L'organizzazione deve disporre di Microsoft Defender per Office 365 (o Office 365 E5) e Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="64f5f-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="64f5f-116">È necessario essere un amministratore globale o disporre di un ruolo di amministratore della sicurezza (ad esempio Amministratore della sicurezza) in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="64f5f-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="64f5f-117">Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="64f5f-117">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="64f5f-118">Devi avere accesso a [Esplora risorse (o ai rilevamenti in tempo reale).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="64f5f-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="64f5f-119">Per integrare Microsoft Defender per Office 365 con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="64f5f-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="64f5f-120">L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint è impostata sia in Defender per Endpoint che in Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="64f5f-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="64f5f-121">In quanto amministratore globale o amministratore della sicurezza, aprire il portale di Microsoft 365 Defender ( ) e passare a <https://security.microsoft.com> **E-mail &** \> **collaborazione Explorer**.</span><span class="sxs-lookup"><span data-stu-id="64f5f-121">As a global administrator or a security administrator, open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Email & collaboration** \> **Explorer**.</span></span> <span data-ttu-id="64f5f-122">Per passare direttamente alla **pagina Esplora** risorse, utilizzare <https://security.microsoft.com/threatexplorer> .</span><span class="sxs-lookup"><span data-stu-id="64f5f-122">To go directly to the **Explorer** page, use <https://security.microsoft.com/threatexplorer>.</span></span>

2. <span data-ttu-id="64f5f-123">**Nell'angolo** superiore destro della pagina Esplora risorse fare clic su **MDE Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="64f5f-123">On the **Explorer** page, in the upper right corner of the screen, click **MDE Settings**.</span></span>

3. <span data-ttu-id="64f5f-124">Nel riquadro a comparsa di connessione **di Microsoft Defender for Endpoint** visualizzato, attivare Connessione a Microsoft Defender per **Endpoint** ( Attiva/Disattiva ) e quindi fare clic su Chiudi ![ icona ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="64f5f-124">In the **Microsoft Defender for Endpoint connection** flyout that appears, turn on **Connect to Microsoft Defender for Endpoint** (![Toggle on](../../media/scc-toggle-on.png)) and then click ![Close icon](../../media/m365-cc-sc-close-icon.png) **Close**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Connessione MDE":::

4. <span data-ttu-id="64f5f-126">Nel riquadro di spostamento scegliere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="64f5f-126">Back in the navigation pane, choose **Settings**.</span></span> <span data-ttu-id="64f5f-127">Nella pagina **Impostazioni** scegliere **Endpoint**</span><span class="sxs-lookup"><span data-stu-id="64f5f-127">On the **Settings** page, choose **Endpoints**</span></span>

5. <span data-ttu-id="64f5f-128">Nella pagina **Endpoint visualizzata** scegliere **Funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="64f5f-128">On the **Endpoints** page that opens, choose **Advanced features**.</span></span>

6. <span data-ttu-id="64f5f-129">Scorrere verso il **basso Office 365 di Threat Intelligence** e attivarla ( Toggle on ![ ](../../media/scc-toggle-on.png) ).</span><span class="sxs-lookup"><span data-stu-id="64f5f-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn it on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="64f5f-130">Al termine, fare clic su **Salva preferenze.**</span><span class="sxs-lookup"><span data-stu-id="64f5f-130">When you're finished, click **Save preferences**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="64f5f-131">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="64f5f-131">Related articles</span></span>

[<span data-ttu-id="64f5f-132">Funzionalità di indagine e risposta alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="64f5f-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="64f5f-133">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="64f5f-133">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="64f5f-134">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="64f5f-134">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
