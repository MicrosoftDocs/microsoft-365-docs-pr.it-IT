---
title: Informazioni di base su Esplora minacce e rilevamento in tempo reale in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Usa Explorer o i rilevamenti in tempo reale per analizzare e rispondere alle minacce in modo efficiente.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300156"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="68cbc-103">Nozioni di base su Threat Explorer e rilevamento in tempo reale</span><span class="sxs-lookup"><span data-stu-id="68cbc-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="68cbc-104">Contenuto dell'articolo:</span><span class="sxs-lookup"><span data-stu-id="68cbc-104">In this article:</span></span>

- [<span data-ttu-id="68cbc-105">Differenze tra Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="68cbc-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="68cbc-106">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="68cbc-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="68cbc-107">Questo articolo fa parte di una serie di **3** articoli su **Threat Explorer (Explorer),** sicurezza della posta elettronica e informazioni di base su **Explorer** e sui rilevamenti in tempo reale (ad esempio le differenze tra gli strumenti e le autorizzazioni necessarie per operare). </span><span class="sxs-lookup"><span data-stu-id="68cbc-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="68cbc-108">Gli altri due articoli di questa serie sono Ricerca delle [minacce in Threat Explorer](threat-hunting-in-threat-explorer.md) e Sicurezza della posta elettronica con Threat [Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="68cbc-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="68cbc-109">In questo articolo viene illustrata la differenza tra l'esplorazione delle minacce e la segnalazione dei rilevamenti in tempo reale e le licenze e le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="68cbc-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="68cbc-110">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="68cbc-110">**Applies to**</span></span>
- [<span data-ttu-id="68cbc-111">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="68cbc-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="68cbc-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68cbc-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="68cbc-113">Se l'organizzazione dispone di [Microsoft Defender per Office 365](defender-for-office-365.md)e si dispone delle autorizzazioni  , è possibile utilizzare **Esplora** minacce (denominato **Esplora** risorse) o rilevamenti in tempo reale per rilevare e correggere le minacce. [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="68cbc-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="68cbc-114">Nel **Centro sicurezza & conformità** passare a **Gestione** delle minacce e quindi scegliere **Esplora risorse**  o **Rilevamenti in tempo reale.**</span><span class="sxs-lookup"><span data-stu-id="68cbc-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="68cbc-115">Con Microsoft Defender per Office 365 Piano 2, viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="68cbc-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="68cbc-116">Con Microsoft Defender per Office 365 piano 1, viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="68cbc-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Esplora minacce](../../media/threatmgmt-explorer.png)|![Rilevamenti in tempo reale](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="68cbc-119">Con questi strumenti, è possibile:</span><span class="sxs-lookup"><span data-stu-id="68cbc-119">With these tools, you can:</span></span>

- <span data-ttu-id="68cbc-120">Vedi malware rilevato dalle Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="68cbc-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="68cbc-121">Visualizzare l'URL di phishing e fare clic su Dati verdetto.</span><span class="sxs-lookup"><span data-stu-id="68cbc-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="68cbc-122">Avvia un processo di indagine e risposta automatizzato da una visualizzazione in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="68cbc-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="68cbc-123">Analizzare la posta elettronica dannosa e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="68cbc-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="68cbc-124">Per altre informazioni, vedi [Sicurezza della posta elettronica con Threat Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="68cbc-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="68cbc-125">Differenze tra Esplora minacce e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="68cbc-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="68cbc-126">*I rilevamenti in tempo reale* sono uno strumento di reporting disponibile in Defender per Office 365 Piano 1.</span><span class="sxs-lookup"><span data-stu-id="68cbc-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="68cbc-127">*Threat Explorer* è uno strumento di ricerca e correzione delle minacce disponibile in Defender per Office 365 Piano 2.</span><span class="sxs-lookup"><span data-stu-id="68cbc-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="68cbc-128">Il report Rilevamenti in tempo reale consente di visualizzare i rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="68cbc-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="68cbc-129">Threat Explorer esegue anche questa operazione, ma fornisce ulteriori dettagli per un determinato attacco, ad esempio l'evidenziazione delle campagne di attacco, e offre ai team delle operazioni di sicurezza la possibilità di correggere le minacce (inclusa l'attivazione di un'indagine automatizzata e un'indagine di [risposta).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="68cbc-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="68cbc-130">Una *visualizzazione Tutti i* messaggi di posta elettronica è disponibile in Esplora minacce, ma non è inclusa nel report Rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="68cbc-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="68cbc-131">Le funzionalità di filtro avanzate e le azioni di correzione sono incluse in Esplora minacce.</span><span class="sxs-lookup"><span data-stu-id="68cbc-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="68cbc-132">Per altre informazioni, vedi [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="68cbc-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="68cbc-133">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="68cbc-133">Required licenses and permissions</span></span>

<span data-ttu-id="68cbc-134">Devi disporre di [Microsoft Defender per Office 365](defender-for-office-365.md) usare uno dei rilevamenti di Explorer o in tempo reale:</span><span class="sxs-lookup"><span data-stu-id="68cbc-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="68cbc-135">Ma Explorer è incluso solo in Defender per Office 365 Piano 2.</span><span class="sxs-lookup"><span data-stu-id="68cbc-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="68cbc-136">Il report rilevamenti in tempo reale è incluso in Defender per Office 365 piano 1.</span><span class="sxs-lookup"><span data-stu-id="68cbc-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="68cbc-137">I team delle operazioni di sicurezza devono assegnare licenze a tutti gli utenti che devono essere protetti da Defender per Office 365 e tenere presente che i rilevamenti di Esplora risorse e in tempo reale mostrano i dati di rilevamento per gli utenti con licenza.</span><span class="sxs-lookup"><span data-stu-id="68cbc-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="68cbc-138">Per visualizzare e usare Esplora *risorse o* rilevamenti in tempo reale, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="68cbc-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="68cbc-139">Per il Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="68cbc-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="68cbc-140">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="68cbc-140">Organization Management</span></span>
  - <span data-ttu-id="68cbc-141">Amministratore della sicurezza (può essere assegnato nell'Azure Active Directory di amministrazione ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="68cbc-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="68cbc-142">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="68cbc-142">Security Reader</span></span>

- <span data-ttu-id="68cbc-143">Per Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="68cbc-143">For Exchange Online:</span></span>

  - <span data-ttu-id="68cbc-144">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="68cbc-144">Organization Management</span></span>
  - <span data-ttu-id="68cbc-145">Gestione organizzazione sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="68cbc-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="68cbc-146">Destinatari solo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="68cbc-146">View-Only Recipients</span></span>
  - <span data-ttu-id="68cbc-147">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="68cbc-147">Compliance Management</span></span>

<span data-ttu-id="68cbc-148">Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="68cbc-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="68cbc-149">Autorizzazioni nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="68cbc-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="68cbc-150">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="68cbc-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="68cbc-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="68cbc-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="68cbc-152">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="68cbc-152">More information</span></span>
- [<span data-ttu-id="68cbc-153">Threat Explorer raccoglie i dettagli della posta elettronica nella pagina dell'entità di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="68cbc-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="68cbc-154">Identificare e analizzare i messaggi di posta elettronica dannosi recapitati</span><span class="sxs-lookup"><span data-stu-id="68cbc-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="68cbc-155">Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68cbc-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="68cbc-156">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="68cbc-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="68cbc-157">Indagine e reazione automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="68cbc-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)