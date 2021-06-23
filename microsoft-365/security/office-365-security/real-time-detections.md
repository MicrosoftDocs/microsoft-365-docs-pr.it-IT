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
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083189"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="6be22-103">Nozioni di base su Esplora risorse e rilevamento in tempo reale</span><span class="sxs-lookup"><span data-stu-id="6be22-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="6be22-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="6be22-104">**Applies to**</span></span>
- [<span data-ttu-id="6be22-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="6be22-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6be22-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6be22-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6be22-107">Contenuto dell'articolo:</span><span class="sxs-lookup"><span data-stu-id="6be22-107">In this article:</span></span>

- [<span data-ttu-id="6be22-108">Differenze tra Esplora risorse e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="6be22-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="6be22-109">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="6be22-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="6be22-110">Questo articolo fa parte di una serie di **3** articoli su Explorer (noto anche come **Threat Explorer),** sicurezza della posta elettronica e informazioni di base su **Esplora** risorse e rilevamenti in tempo reale (ad esempio differenze tra gli strumenti e autorizzazioni necessarie per operare).</span><span class="sxs-lookup"><span data-stu-id="6be22-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="6be22-111">Gli altri due articoli di questa serie sono Ricerca delle [minacce in Esplora](threat-hunting-in-threat-explorer.md) risorse e Sicurezza della posta elettronica con Esplora [risorse.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="6be22-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="6be22-112">In questo articolo viene illustrata la differenza tra Explorer e la segnalazione dei rilevamenti in tempo reale e le licenze e le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="6be22-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="6be22-113">Se l'organizzazione dispone di [Microsoft Defender per Office 365](defender-for-office-365.md)e si dispone delle autorizzazioni ,  è possibile utilizzare **Esplora** risorse (noto anche come **Esplora** minacce) o rilevamenti in tempo reale per rilevare e correggere le minacce. [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="6be22-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="6be22-114">Nel portale Microsoft 365 Defender ( ), passare a Posta elettronica & collaborazione e quindi scegliere Esplora risorse o <https://security.microsoft.com>   **Rilevamenti in tempo reale**. </span><span class="sxs-lookup"><span data-stu-id="6be22-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="6be22-115">Con questi strumenti è possibile:</span><span class="sxs-lookup"><span data-stu-id="6be22-115">With these tools, you can:</span></span>

- <span data-ttu-id="6be22-116">Vedi malware rilevato dalle Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6be22-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="6be22-117">Visualizzare l'URL di phishing e fare clic su Dati verdetto.</span><span class="sxs-lookup"><span data-stu-id="6be22-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="6be22-118">Avvia un processo di indagine e risposta automatizzato da una visualizzazione in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="6be22-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="6be22-119">Analizzare la posta elettronica dannosa e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="6be22-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="6be22-120">Per altre informazioni, vedi [Sicurezza della posta elettronica con Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="6be22-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="6be22-121">Differenze tra Esplora risorse e rilevamenti in tempo reale</span><span class="sxs-lookup"><span data-stu-id="6be22-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="6be22-122">*I rilevamenti in tempo reale* sono uno strumento di reporting disponibile in Defender per Office 365 Piano 1.</span><span class="sxs-lookup"><span data-stu-id="6be22-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="6be22-123">*Threat Explorer* è uno strumento di ricerca e correzione delle minacce disponibile in Defender per Office 365 Piano 2.</span><span class="sxs-lookup"><span data-stu-id="6be22-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="6be22-124">Il report Rilevamenti in tempo reale consente di visualizzare i rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6be22-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="6be22-125">Threat Explorer esegue anche questa operazione, ma fornisce ulteriori dettagli per un determinato attacco, ad esempio l'evidenziazione delle campagne di attacco, e offre ai team delle operazioni di sicurezza la possibilità di correggere le minacce (inclusa l'attivazione di un'indagine automatizzata e un'indagine di [risposta).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="6be22-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="6be22-126">Una *visualizzazione Tutti i* messaggi di posta elettronica è disponibile in Esplora minacce, ma non è inclusa nel report Rilevamenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6be22-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="6be22-127">Le funzionalità di filtro avanzate e le azioni di correzione sono incluse in Esplora minacce.</span><span class="sxs-lookup"><span data-stu-id="6be22-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="6be22-128">Per altre informazioni, vedi [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="6be22-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="6be22-129">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="6be22-129">Required licenses and permissions</span></span>

<span data-ttu-id="6be22-130">Devi disporre di [Microsoft Defender per Office 365](defender-for-office-365.md) usare uno dei rilevamenti di Explorer o in tempo reale:</span><span class="sxs-lookup"><span data-stu-id="6be22-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="6be22-131">Explorer è incluso solo in Defender per Office 365 Piano 2.</span><span class="sxs-lookup"><span data-stu-id="6be22-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="6be22-132">Il report rilevamenti in tempo reale è incluso in Defender per Office 365 piano 1.</span><span class="sxs-lookup"><span data-stu-id="6be22-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="6be22-133">I team delle operazioni di sicurezza devono assegnare licenze a tutti gli utenti che devono essere protetti da Defender per Office 365 e tenere presente che i rilevamenti di Esplora risorse e in tempo reale mostrano i dati di rilevamento per gli utenti con licenza.</span><span class="sxs-lookup"><span data-stu-id="6be22-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="6be22-134">Per visualizzare e usare Esplora *risorse o* rilevamenti in tempo reale, sono necessarie le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6be22-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="6be22-135">In Defender per Office 365:</span><span class="sxs-lookup"><span data-stu-id="6be22-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="6be22-136">Gestione dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6be22-136">Organization Management</span></span>
  - <span data-ttu-id="6be22-137">Amministratore della sicurezza (può essere assegnato nell'Azure Active Directory di amministrazione ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="6be22-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="6be22-138">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="6be22-138">Security Reader</span></span>
- <span data-ttu-id="6be22-139">In Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="6be22-139">In Exchange Online:</span></span>
  - <span data-ttu-id="6be22-140">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="6be22-140">Organization Management</span></span>
  - <span data-ttu-id="6be22-141">Gestione organizzazione sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="6be22-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="6be22-142">Destinatari solo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="6be22-142">View-Only Recipients</span></span>
  - <span data-ttu-id="6be22-143">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="6be22-143">Compliance Management</span></span>

<span data-ttu-id="6be22-144">Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6be22-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="6be22-145">Autorizzazioni nel portale di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6be22-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="6be22-146">Autorizzazioni in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6be22-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="6be22-147">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="6be22-147">More information</span></span>

- [<span data-ttu-id="6be22-148">Threat Explorer raccoglie i dettagli della posta elettronica nella pagina dell'entità di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6be22-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="6be22-149">Identificare e analizzare i messaggi di posta elettronica dannosi recapitati</span><span class="sxs-lookup"><span data-stu-id="6be22-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="6be22-150">Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6be22-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="6be22-151">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="6be22-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="6be22-152">Indagine e reazione automatizzate in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6be22-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
