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
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198014"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="b842a-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="b842a-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b842a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b842a-105">**Applies to:**</span></span>
- <span data-ttu-id="b842a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b842a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b842a-107">La `EmailPostDeliveryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle azioni successive al recapito eseguite nei messaggi di posta elettronica elaborati da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b842a-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="b842a-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="b842a-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="b842a-109">Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b842a-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="b842a-110">Per ottenere ulteriori informazioni sui singoli messaggi di posta elettronica, è anche possibile utilizzare le [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabelle, e [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="b842a-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="b842a-111">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b842a-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b842a-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b842a-112">Column name</span></span> | <span data-ttu-id="b842a-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b842a-113">Data type</span></span> | <span data-ttu-id="b842a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b842a-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b842a-115">datetime</span><span class="sxs-lookup"><span data-stu-id="b842a-115">datetime</span></span> | <span data-ttu-id="b842a-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="b842a-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="b842a-117">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-117">string</span></span> | <span data-ttu-id="b842a-118">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="b842a-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="b842a-119">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-119">string</span></span> | <span data-ttu-id="b842a-120">Identificatore univoco per il messaggio di posta elettronica, generato da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b842a-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="b842a-121">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-121">string</span></span> | <span data-ttu-id="b842a-122">Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio</span><span class="sxs-lookup"><span data-stu-id="b842a-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="b842a-123">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-123">string</span></span> | <span data-ttu-id="b842a-124">Azione intrapresa nell'entità</span><span class="sxs-lookup"><span data-stu-id="b842a-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="b842a-125">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-125">string</span></span> | <span data-ttu-id="b842a-126">Tipo di attività che ha attivato l'evento: correzione manuale, phishing ZAP, malware ZAP</span><span class="sxs-lookup"><span data-stu-id="b842a-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="b842a-127">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-127">string</span></span> | <span data-ttu-id="b842a-128">Indica se un'azione è stata attivata da un amministratore (manualmente o tramite approvazione di un'azione automatizzata in sospeso) o da un meccanismo speciale, ad esempio uno ZAP o un recapito dinamico.</span><span class="sxs-lookup"><span data-stu-id="b842a-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="b842a-129">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-129">string</span></span> | <span data-ttu-id="b842a-130">Risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="b842a-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="b842a-131">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-131">string</span></span> | <span data-ttu-id="b842a-132">Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="b842a-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="b842a-133">stringa</span><span class="sxs-lookup"><span data-stu-id="b842a-133">string</span></span> | <span data-ttu-id="b842a-134">Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati</span><span class="sxs-lookup"><span data-stu-id="b842a-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="b842a-135">Tipi di evento supportati</span><span class="sxs-lookup"><span data-stu-id="b842a-135">Supported event types</span></span>
<span data-ttu-id="b842a-136">In questa tabella vengono acquisiti gli eventi con i `ActionType` valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b842a-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="b842a-137">**Correzione manuale** : un amministratore ha eseguito manualmente un'azione su un messaggio di posta elettronica dopo che è stato recapitato alla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b842a-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="b842a-138">Sono incluse le azioni eseguite manualmente tramite [Esplora minacce](../office-365-security/threat-explorer.md) o le approvazioni delle [azioni automatiche di analisi e risposta (Air)](mtp-autoir-actions.md).</span><span class="sxs-lookup"><span data-stu-id="b842a-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="b842a-139">**Phishing zap** – [zero-hour auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) ha eseguito un'azione su un messaggio di posta elettronica di phishing dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="b842a-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="b842a-140">**Malware zap** – zero-hour auto Purge (ZAP) ha eseguito un'azione su un messaggio di posta elettronica contenente malware dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="b842a-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b842a-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b842a-141">Related topics</span></span>
- [<span data-ttu-id="b842a-142">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="b842a-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b842a-143">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="b842a-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b842a-144">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="b842a-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b842a-145">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="b842a-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b842a-146">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="b842a-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b842a-147">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="b842a-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
