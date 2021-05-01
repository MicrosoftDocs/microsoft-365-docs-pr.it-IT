---
title: Esempio di attacco tramite posta elettronica di phishing
description: Eseguire un'analisi di esempio di un attacco di phishing.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114790"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="66e5e-104">Esempio di attacco tramite posta elettronica di phishing</span><span class="sxs-lookup"><span data-stu-id="66e5e-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="66e5e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="66e5e-105">**Applies to:**</span></span>
- <span data-ttu-id="66e5e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66e5e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="66e5e-107">Microsoft 365 Defender può aiutare a rilevare gli allegati dannosi recapitati tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="66e5e-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="66e5e-108">Poiché il Centro sicurezza e conformità di [Office 365](https://protection.office.com/) si integra con Microsoft 365 Defender, gli analisti della sicurezza possono avere visibilità sulle minacce provenienti da Office 365, ad esempio tramite allegati di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="66e5e-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="66e5e-109">Ad esempio, a un analista è stato assegnato un incidente in più fasi.</span><span class="sxs-lookup"><span data-stu-id="66e5e-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Esempio di incidente in più fasi"::: 

<span data-ttu-id="66e5e-111">Nella scheda **Avvisi** dell'evento imprevisto vengono visualizzati gli avvisi di Defender Office 365 e Microsoft Cloud App Security messaggi.</span><span class="sxs-lookup"><span data-stu-id="66e5e-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="66e5e-112">L'analista può eseguire il drill-down in Defender per Office 365 avvisi selezionando gli avvisi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="66e5e-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="66e5e-113">I dettagli dell'avviso vengono visualizzati nel riquadro laterale.</span><span class="sxs-lookup"><span data-stu-id="66e5e-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Esempio di avviso tramite posta elettronica":::
 
<span data-ttu-id="66e5e-115">Scorrendo ulteriormente verso il basso, vengono visualizzate ulteriori informazioni, che mostrano i file dannosi e l'utente che è stato tolto.</span><span class="sxs-lookup"><span data-stu-id="66e5e-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Esempio di impatto su utenti e file di un avviso di posta elettronica":::
  
<span data-ttu-id="66e5e-117">Selezionando **La pagina Apri avviso** si visualizza l'avviso specifico in cui è possibile visualizzare più informazioni in modo più dettagliato selezionando il collegamento.</span><span class="sxs-lookup"><span data-stu-id="66e5e-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="66e5e-118">Il messaggio di posta elettronica effettivo può essere visualizzato selezionando **Visualizza messaggi in Esplora** risorse verso la parte inferiore del pannello.</span><span class="sxs-lookup"><span data-stu-id="66e5e-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Esempio dei dettagli di un avviso"::: 

<span data-ttu-id="66e5e-120">In questo modo l'analista viene visualizzato nella pagina Gestione minacce in cui vengono visualizzati l'oggetto, il destinatario, il mittente e altre informazioni di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="66e5e-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="66e5e-121">**ZAP** in **Azioni speciali indica** all'analista che è stata implementata la funzionalità di eliminazione automatica a zero ore.</span><span class="sxs-lookup"><span data-stu-id="66e5e-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="66e5e-122">ZAP rileva e rimuove automaticamente i messaggi dannosi e di posta indesiderata dalle cassette postali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="66e5e-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="66e5e-123">Per ulteriori informazioni, vedere [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="66e5e-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="66e5e-124">È possibile eseguire altre azioni su messaggi specifici selezionando **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="66e5e-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Esempio di altre azioni che possono essere eseguite sui messaggi di posta elettronica"::: 

## <a name="next-step"></a><span data-ttu-id="66e5e-126">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="66e5e-126">Next step</span></span>

<span data-ttu-id="66e5e-127">Vedi il percorso [di analisi degli attacchi basati sull'identità.](first-incident-path-identity.md)</span><span class="sxs-lookup"><span data-stu-id="66e5e-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="66e5e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e5e-128">See also</span></span>

- [<span data-ttu-id="66e5e-129">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="66e5e-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="66e5e-130">Analizzare gli incidenti</span><span class="sxs-lookup"><span data-stu-id="66e5e-130">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="66e5e-131">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="66e5e-131">Manage incidents</span></span>](manage-incidents.md)
