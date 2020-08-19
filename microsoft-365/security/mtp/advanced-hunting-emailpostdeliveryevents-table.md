---
title: Tabella EmailPostDeliveryEvents nello schema di caccia avanzato
description: Informazioni sulle azioni di post-recapito eseguite nei messaggi di posta elettronica di Microsoft 365 nella tabella EmailPostDeliveryEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailPostDeliveryEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di malware, verdetto di phishing, conteggio degli allegati
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 88074de8792124557c65b5be074e3b02bfec2511
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797887"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="9dc13-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="9dc13-104">EmailPostDeliveryEvents</span></span>

<span data-ttu-id="9dc13-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9dc13-105">**Applies to:**</span></span>
- <span data-ttu-id="9dc13-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9dc13-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9dc13-107">La `EmailPostDeliveryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle azioni successive al recapito eseguite nei messaggi di posta elettronica elaborati da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9dc13-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="9dc13-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="9dc13-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9dc13-109">Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9dc13-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9dc13-110">Per ottenere ulteriori informazioni sui singoli messaggi di posta elettronica, è anche possibile utilizzare le [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabelle, e [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="9dc13-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="9dc13-111">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9dc13-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9dc13-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9dc13-112">Column name</span></span> | <span data-ttu-id="9dc13-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9dc13-113">Data type</span></span> | <span data-ttu-id="9dc13-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9dc13-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9dc13-115">datetime</span><span class="sxs-lookup"><span data-stu-id="9dc13-115">datetime</span></span> | <span data-ttu-id="9dc13-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="9dc13-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="9dc13-117">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-117">string</span></span> | <span data-ttu-id="9dc13-118">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="9dc13-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="9dc13-119">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-119">string</span></span> | <span data-ttu-id="9dc13-120">Identificatore univoco per il messaggio di posta elettronica, generato da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9dc13-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="9dc13-121">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-121">string</span></span> | <span data-ttu-id="9dc13-122">Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio</span><span class="sxs-lookup"><span data-stu-id="9dc13-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="9dc13-123">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-123">string</span></span> | <span data-ttu-id="9dc13-124">Azione intrapresa nell'entità</span><span class="sxs-lookup"><span data-stu-id="9dc13-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="9dc13-125">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-125">string</span></span> | <span data-ttu-id="9dc13-126">Tipo di attività che ha attivato l'evento: correzione manuale, phishing ZAP, malware ZAP</span><span class="sxs-lookup"><span data-stu-id="9dc13-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="9dc13-127">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-127">string</span></span> | <span data-ttu-id="9dc13-128">Indica se un'azione è stata attivata da un amministratore (manualmente o tramite approvazione di un'azione automatizzata in sospeso) o da un meccanismo speciale, ad esempio uno ZAP o un recapito dinamico.</span><span class="sxs-lookup"><span data-stu-id="9dc13-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="9dc13-129">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-129">string</span></span> | <span data-ttu-id="9dc13-130">Risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="9dc13-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="9dc13-131">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-131">string</span></span> | <span data-ttu-id="9dc13-132">Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="9dc13-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="9dc13-133">stringa</span><span class="sxs-lookup"><span data-stu-id="9dc13-133">string</span></span> | <span data-ttu-id="9dc13-134">Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati</span><span class="sxs-lookup"><span data-stu-id="9dc13-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="9dc13-135">Tipi di evento supportati</span><span class="sxs-lookup"><span data-stu-id="9dc13-135">Supported event types</span></span>
<span data-ttu-id="9dc13-136">In questa tabella vengono acquisiti gli eventi con i `ActionType` valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dc13-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="9dc13-137">**Correzione manuale** : un amministratore ha eseguito manualmente un'azione su un messaggio di posta elettronica dopo che è stato recapitato alla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9dc13-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="9dc13-138">Sono incluse le azioni eseguite manualmente tramite [Esplora minacce](../office-365-security/threat-explorer.md) o le approvazioni delle [azioni automatiche di analisi e risposta (Air)](mtp-autoir-actions.md).</span><span class="sxs-lookup"><span data-stu-id="9dc13-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="9dc13-139">**Phishing zap** – [zero-hour auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) ha eseguito un'azione su un messaggio di posta elettronica di phishing dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="9dc13-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="9dc13-140">**Malware zap** – zero-hour auto Purge (ZAP) ha eseguito un'azione su un messaggio di posta elettronica contenente malware dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="9dc13-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9dc13-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9dc13-141">Related topics</span></span>
- [<span data-ttu-id="9dc13-142">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9dc13-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9dc13-143">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="9dc13-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9dc13-144">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="9dc13-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9dc13-145">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="9dc13-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9dc13-146">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="9dc13-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9dc13-147">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="9dc13-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)