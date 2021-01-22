---
title: Tabella IdentityDirectoryEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi del controller di dominio e di Active Directory nella tabella IdentityDirectoryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityDirectoryEvents, controller di dominio, Active Directory, Azure ATP, identità
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
ms.openlocfilehash: 95090b0f4abe0b0f0552c81495936f4f2261cf8e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929935"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="9e3f8-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="9e3f8-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e3f8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9e3f8-105">**Applies to:**</span></span>
- <span data-ttu-id="9e3f8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e3f8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9e3f8-107">La tabella nello schema di ricerca avanzata contiene gli eventi che coinvolgono un controller di dominio locale che `IdentityDirectoryEvents` esegue Active Directory (AD). [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9e3f8-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9e3f8-108">Questa tabella acquisisce vari eventi correlati all'identità, come le modifiche delle password, la scadenza delle password e le modifiche al nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="9e3f8-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="9e3f8-109">Acquisisce inoltre gli eventi di sistema nel controller di dominio, ad esempio la pianificazione delle attività e l'attività di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e3f8-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="9e3f8-110">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="9e3f8-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9e3f8-111">Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="9e3f8-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9e3f8-112">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9e3f8-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9e3f8-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9e3f8-113">Column name</span></span> | <span data-ttu-id="9e3f8-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9e3f8-114">Data type</span></span> | <span data-ttu-id="9e3f8-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e3f8-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9e3f8-116">datetime</span><span class="sxs-lookup"><span data-stu-id="9e3f8-116">datetime</span></span> | <span data-ttu-id="9e3f8-117">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="9e3f8-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9e3f8-118">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-118">string</span></span> | <span data-ttu-id="9e3f8-119">Tipo di attività che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="9e3f8-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="9e3f8-120">Per informazioni [dettagliate, vedere le informazioni di riferimento](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) sullo schema nel portale</span><span class="sxs-lookup"><span data-stu-id="9e3f8-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="9e3f8-121">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-121">string</span></span> | <span data-ttu-id="9e3f8-122">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="9e3f8-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="9e3f8-123">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-123">string</span></span> | <span data-ttu-id="9e3f8-124">Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="9e3f8-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="9e3f8-125">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-125">string</span></span> | <span data-ttu-id="9e3f8-126">Nome visualizzato dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="9e3f8-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="9e3f8-127">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-127">string</span></span> | <span data-ttu-id="9e3f8-128">Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="9e3f8-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="9e3f8-129">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-129">string</span></span> | <span data-ttu-id="9e3f8-130">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="9e3f8-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="9e3f8-131">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-131">string</span></span> | <span data-ttu-id="9e3f8-132">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="9e3f8-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="9e3f8-133">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-133">string</span></span> | <span data-ttu-id="9e3f8-134">Porta di destinazione dell'attività</span><span class="sxs-lookup"><span data-stu-id="9e3f8-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="9e3f8-135">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-135">string</span></span> | <span data-ttu-id="9e3f8-136">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="9e3f8-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="9e3f8-137">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-137">string</span></span> | <span data-ttu-id="9e3f8-138">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="9e3f8-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9e3f8-139">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-139">string</span></span> | <span data-ttu-id="9e3f8-140">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="9e3f8-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9e3f8-141">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-141">string</span></span> | <span data-ttu-id="9e3f8-142">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="9e3f8-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9e3f8-143">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-143">string</span></span> | <span data-ttu-id="9e3f8-144">Identificatore di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="9e3f8-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9e3f8-145">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-145">string</span></span> | <span data-ttu-id="9e3f8-146">Identificatore univoco per l'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9e3f8-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9e3f8-147">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-147">string</span></span> | <span data-ttu-id="9e3f8-148">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="9e3f8-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9e3f8-149">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="9e3f8-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9e3f8-150">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-150">string</span></span> | <span data-ttu-id="9e3f8-151">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="9e3f8-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="9e3f8-152">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-152">string</span></span> | <span data-ttu-id="9e3f8-153">Indirizzo IP assegnato al dispositivo durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="9e3f8-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="9e3f8-154">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-154">string</span></span> | <span data-ttu-id="9e3f8-155">Porta TCP utilizzata durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="9e3f8-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="9e3f8-156">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-156">string</span></span> | <span data-ttu-id="9e3f8-157">Città, paese o altra posizione geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="9e3f8-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="9e3f8-158">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-158">string</span></span> | <span data-ttu-id="9e3f8-159">Provider di servizi Internet associato all'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="9e3f8-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="9e3f8-160">long</span><span class="sxs-lookup"><span data-stu-id="9e3f8-160">long</span></span> | <span data-ttu-id="9e3f8-161">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="9e3f8-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="9e3f8-162">stringa</span><span class="sxs-lookup"><span data-stu-id="9e3f8-162">string</span></span> | <span data-ttu-id="9e3f8-163">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="9e3f8-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9e3f8-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9e3f8-164">Related topics</span></span>
- [<span data-ttu-id="9e3f8-165">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9e3f8-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e3f8-166">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="9e3f8-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9e3f8-167">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="9e3f8-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9e3f8-168">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="9e3f8-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9e3f8-169">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="9e3f8-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9e3f8-170">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="9e3f8-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
