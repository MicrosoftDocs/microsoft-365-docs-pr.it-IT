---
title: Configurare le funzionalità di analisi e correzione automatizzate
description: Configurare le funzionalità di analisi e correzione automatizzate in Microsoft Defender per Endpoint.
keywords: configurare, configurare, automatizzato, indagine, rilevamento, avvisi, correzione, risposta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841333"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="183d6-104">Configurare le funzionalità di analisi e correzione automatizzate in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="183d6-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="183d6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="183d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="183d6-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="183d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="183d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="183d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="183d6-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="183d6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="183d6-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="183d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="183d6-110">Se l'organizzazione usa [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), le funzionalità di analisi e correzione automatizzate possono risparmiare tempo e fatica per il team delle operazioni di sicurezza. [](/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="183d6-110">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="183d6-111">Come descritto in questo [post di blog,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)queste funzionalità simulano i passaggi ideali che un analista della sicurezza adotta per analizzare e correggere le minacce.</span><span class="sxs-lookup"><span data-stu-id="183d6-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="183d6-112">[Ulteriori informazioni sull'analisi e la correzione automatizzate.](/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="183d6-112">[Learn more about automated investigation and remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="183d6-113">Per configurare l'analisi e la correzione automatizzate,</span><span class="sxs-lookup"><span data-stu-id="183d6-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="183d6-114">[Attivare le funzionalità](#turn-on-automated-investigation-and-remediation); e</span><span class="sxs-lookup"><span data-stu-id="183d6-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="183d6-115">[Configurare i gruppi di dispositivi](#set-up-device-groups).</span><span class="sxs-lookup"><span data-stu-id="183d6-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="183d6-116">Attivare l'analisi e la correzione automatizzate</span><span class="sxs-lookup"><span data-stu-id="183d6-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="183d6-117">Come amministratore globale o amministratore della sicurezza, passare alla Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="183d6-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="183d6-118">Nel riquadro di spostamento scegliere **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="183d6-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="183d6-119">Nella sezione **Generale** selezionare **Funzionalità avanzate**.</span><span class="sxs-lookup"><span data-stu-id="183d6-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="183d6-120">Attivare sia **Analisi automatizzata che** Risolvi **automaticamente gli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="183d6-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="183d6-121">Configurare gruppi di dispositivi</span><span class="sxs-lookup"><span data-stu-id="183d6-121">Set up device groups</span></span>

1. <span data-ttu-id="183d6-122">Nella Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), nella pagina **Impostazioni,** in **Autorizzazioni,** selezionare **Gruppi di dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="183d6-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="183d6-123">Seleziona **+ Aggiungi gruppo di dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="183d6-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="183d6-124">Creare almeno un gruppo di dispositivi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="183d6-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="183d6-125">Specificare un nome e una descrizione per il gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="183d6-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="183d6-126">**Nell'elenco Livello di automazione** selezionare un livello, ad esempio **Completo, per correggere automaticamente le minacce.**</span><span class="sxs-lookup"><span data-stu-id="183d6-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="183d6-127">Il livello di automazione determina se le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="183d6-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="183d6-128">Per ulteriori informazioni, vedere Livelli di automazione in analisi e [correzione automatizzate.](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="183d6-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="183d6-129">Nella sezione **Membri** usa una o più condizioni per identificare e includere i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="183d6-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="183d6-130">Nella scheda **Accesso utente** [](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) seleziona i gruppi Azure Active Directory che devono avere accesso al gruppo di dispositivi che stai creando.</span><span class="sxs-lookup"><span data-stu-id="183d6-130">On the **User access** tab, select the [Azure Active Directory groups](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="183d6-131">Seleziona **Fatto** al termine della configurazione del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="183d6-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="183d6-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="183d6-132">Next steps</span></span>

- [<span data-ttu-id="183d6-133">Visitare il Centro notifiche per visualizzare le azioni di correzione in sospeso e completate</span><span class="sxs-lookup"><span data-stu-id="183d6-133">Visit the Action Center to view pending and completed remediation actions</span></span>](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="183d6-134">Rivedere e approvare le azioni in sospeso</span><span class="sxs-lookup"><span data-stu-id="183d6-134">Review and approve pending actions</span></span>](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="183d6-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="183d6-135">See also</span></span>

- [<span data-ttu-id="183d6-136">Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="183d6-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
