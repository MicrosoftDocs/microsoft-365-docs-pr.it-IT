---
title: Tabella EmailPostDeliveryEvents nello schema di ricerca avanzata
description: Informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica di Microsoft 365 nella tabella EmailPostDeliveryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailPostDeliveryEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di phishing, verdetto phishing, numero di allegati, numero di collegamenti, numero di url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6e12ddfc402f1bd420f57369cc6d54f2e670d710
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712379"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="264ab-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="264ab-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="264ab-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="264ab-105">**Applies to:**</span></span>
- <span data-ttu-id="264ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="264ab-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="264ab-107">La tabella nello schema di ricerca avanzata contiene informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica `EmailPostDeliveryEvents` elaborati da Microsoft 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="264ab-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="264ab-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="264ab-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="264ab-109">Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="264ab-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="264ab-110">Per ottenere ulteriori informazioni sui singoli messaggi di posta elettronica, è inoltre possibile utilizzare le tabelle [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) , e [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="264ab-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="264ab-111">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="264ab-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="264ab-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="264ab-112">Column name</span></span> | <span data-ttu-id="264ab-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="264ab-113">Data type</span></span> | <span data-ttu-id="264ab-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="264ab-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="264ab-115">datetime</span><span class="sxs-lookup"><span data-stu-id="264ab-115">datetime</span></span> | <span data-ttu-id="264ab-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="264ab-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="264ab-117">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-117">string</span></span> | <span data-ttu-id="264ab-118">Identificatore univoco del messaggio di posta elettronica, generato da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="264ab-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="264ab-119">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-119">string</span></span> | <span data-ttu-id="264ab-120">Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio</span><span class="sxs-lookup"><span data-stu-id="264ab-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="264ab-121">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-121">string</span></span> | <span data-ttu-id="264ab-122">Azione eseguita sull'entità</span><span class="sxs-lookup"><span data-stu-id="264ab-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="264ab-123">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-123">string</span></span> | <span data-ttu-id="264ab-124">Tipo di attività che ha attivato l'evento: correzione manuale, Phish ZAP, Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="264ab-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="264ab-125">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-125">string</span></span> | <span data-ttu-id="264ab-126">Indica se un'azione è stata attivata da un amministratore (manualmente o tramite l'approvazione di un'azione automatica in sospeso) o da un meccanismo speciale, ad esempio zap o recapito dinamico</span><span class="sxs-lookup"><span data-stu-id="264ab-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="264ab-127">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-127">string</span></span> | <span data-ttu-id="264ab-128">Risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="264ab-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="264ab-129">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-129">string</span></span> | <span data-ttu-id="264ab-130">Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="264ab-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="264ab-131">stringa</span><span class="sxs-lookup"><span data-stu-id="264ab-131">string</span></span> | <span data-ttu-id="264ab-132">Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati</span><span class="sxs-lookup"><span data-stu-id="264ab-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="264ab-133">long</span><span class="sxs-lookup"><span data-stu-id="264ab-133">long</span></span> | <span data-ttu-id="264ab-134">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="264ab-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="264ab-135">Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="264ab-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="264ab-136">Tipi di evento supportati</span><span class="sxs-lookup"><span data-stu-id="264ab-136">Supported event types</span></span>
<span data-ttu-id="264ab-137">Questa tabella acquisisce gli eventi con i valori `ActionType` seguenti:</span><span class="sxs-lookup"><span data-stu-id="264ab-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="264ab-138">**Correzione manuale: un** amministratore ha preso manualmente un'azione su un messaggio di posta elettronica dopo che è stato recapitato alla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="264ab-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="264ab-139">Sono incluse le azioni eseguite manualmente tramite [Esplora](../office-365-security/threat-explorer.md) minacce o l'approvazione di azioni di analisi e risposta [automatizzate (AIR).](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="264ab-139">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="264ab-140">**PHISH ZAP** - [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span><span class="sxs-lookup"><span data-stu-id="264ab-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="264ab-141">**ZAP antimalware:** zap (Zero-Hour Auto Purge) ha preso azione su un messaggio di posta elettronica trovato contenente malware dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="264ab-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="264ab-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="264ab-142">Related topics</span></span>
- [<span data-ttu-id="264ab-143">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="264ab-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="264ab-144">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="264ab-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="264ab-145">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="264ab-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="264ab-146">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="264ab-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="264ab-147">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="264ab-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="264ab-148">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="264ab-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
