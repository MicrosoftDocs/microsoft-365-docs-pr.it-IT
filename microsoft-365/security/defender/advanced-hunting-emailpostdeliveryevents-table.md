---
title: Tabella EmailPostDeliveryEvents nello schema di ricerca avanzata
description: Informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica di Microsoft 365 nella tabella EmailPostDeliveryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailPostDeliveryEvents, ID messaggio di rete, mittente, destinatario, ID allegato, nome allegato, verdetto di phishing, conteggio degli allegati, conteggio dei collegamenti, conteggio url
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 25f1a177571862e92c502b584bbd51801141069a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068661"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="e9c9e-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="e9c9e-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e9c9e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e9c9e-105">**Applies to:**</span></span>
- <span data-ttu-id="e9c9e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9c9e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e9c9e-107">La tabella nello schema di ricerca avanzata contiene informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica `EmailPostDeliveryEvents` elaborati da Microsoft 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e9c9e-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="e9c9e-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="e9c9e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="e9c9e-109">Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e9c9e-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="e9c9e-110">Per ottenere ulteriori informazioni sui singoli messaggi di posta elettronica, è inoltre possibile utilizzare le tabelle [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) , e [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="e9c9e-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="e9c9e-111">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e9c9e-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e9c9e-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="e9c9e-112">Column name</span></span> | <span data-ttu-id="e9c9e-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e9c9e-113">Data type</span></span> | <span data-ttu-id="e9c9e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9c9e-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e9c9e-115">datetime</span><span class="sxs-lookup"><span data-stu-id="e9c9e-115">datetime</span></span> | <span data-ttu-id="e9c9e-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="e9c9e-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="e9c9e-117">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-117">string</span></span> | <span data-ttu-id="e9c9e-118">Identificatore univoco del messaggio di posta elettronica, generato da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9c9e-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="e9c9e-119">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-119">string</span></span> | <span data-ttu-id="e9c9e-120">Identificatore pubblico per il messaggio di posta elettronica impostato dal sistema di invio</span><span class="sxs-lookup"><span data-stu-id="e9c9e-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="e9c9e-121">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-121">string</span></span> | <span data-ttu-id="e9c9e-122">Azione eseguita sull'entità</span><span class="sxs-lookup"><span data-stu-id="e9c9e-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="e9c9e-123">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-123">string</span></span> | <span data-ttu-id="e9c9e-124">Tipo di attività che ha attivato l'evento: correzione manuale, Phish ZAP, Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="e9c9e-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="e9c9e-125">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-125">string</span></span> | <span data-ttu-id="e9c9e-126">Indica se un'azione è stata attivata da un amministratore (manualmente o tramite l'approvazione di un'azione automatica in sospeso) o da un meccanismo speciale, ad esempio zap o recapito dinamico</span><span class="sxs-lookup"><span data-stu-id="e9c9e-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="e9c9e-127">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-127">string</span></span> | <span data-ttu-id="e9c9e-128">Risultato dell'azione</span><span class="sxs-lookup"><span data-stu-id="e9c9e-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="e9c9e-129">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-129">string</span></span> | <span data-ttu-id="e9c9e-130">Indirizzo di posta elettronica del destinatario o indirizzo di posta elettronica del destinatario dopo l'espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e9c9e-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="e9c9e-131">stringa</span><span class="sxs-lookup"><span data-stu-id="e9c9e-131">string</span></span> | <span data-ttu-id="e9c9e-132">Posizione di recapito del messaggio di posta elettronica: cartella Posta in arrivo, locale/esterno, Posta indesiderata, Quarantena, invio non riuscito, non elaborato, Elementi eliminati</span><span class="sxs-lookup"><span data-stu-id="e9c9e-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="e9c9e-133">long</span><span class="sxs-lookup"><span data-stu-id="e9c9e-133">long</span></span> | <span data-ttu-id="e9c9e-134">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="e9c9e-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e9c9e-135">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="e9c9e-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="e9c9e-136">Tipi di evento supportati</span><span class="sxs-lookup"><span data-stu-id="e9c9e-136">Supported event types</span></span>
<span data-ttu-id="e9c9e-137">Questa tabella acquisisce gli eventi con i valori `ActionType` seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9c9e-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="e9c9e-138">**Correzione manuale: un** amministratore ha preso manualmente un'azione su un messaggio di posta elettronica dopo che è stato recapitato alla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e9c9e-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="e9c9e-139">Sono incluse le azioni eseguite manualmente tramite [Threat Explorer](../defender-365-security/threat-explorer.md) o le approvazioni di azioni di indagine e [risposta automatizzate (AIR).](m365d-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="e9c9e-139">This includes actions taken manually through [Threat Explorer](../defender-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](m365d-autoir-actions.md).</span></span>
- <span data-ttu-id="e9c9e-140">**Phish ZAP-** [Zero-hour auto purge (ZAP)](../defender-365-security/zero-hour-auto-purge.md) ha preso azione su un messaggio di posta elettronica di phishing dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="e9c9e-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../defender-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="e9c9e-141">**MALWARE ZAP** : l'eliminazione automatica di zero ore (ZAP) ha preso azione su un messaggio di posta elettronica trovato contenente malware dopo il recapito.</span><span class="sxs-lookup"><span data-stu-id="e9c9e-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9c9e-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e9c9e-142">Related topics</span></span>
- [<span data-ttu-id="e9c9e-143">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="e9c9e-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9c9e-144">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="e9c9e-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e9c9e-145">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="e9c9e-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e9c9e-146">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="e9c9e-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e9c9e-147">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="e9c9e-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e9c9e-148">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="e9c9e-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
