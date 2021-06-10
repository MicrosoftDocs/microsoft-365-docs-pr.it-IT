---
title: Tabella IdentityDirectoryEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi del controller di dominio e di Active Directory nella tabella IdentityDirectoryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityDirectoryEvents, controller di dominio, Active Directory, Microsoft Defender per l'identità, identità
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b42ff09f1e363f115ecc06c361c8386b328b0bcb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933002"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="88569-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="88569-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="88569-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="88569-105">**Applies to:**</span></span>
- <span data-ttu-id="88569-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88569-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="88569-107">La tabella nello schema di ricerca avanzata contiene eventi che coinvolgono un controller di dominio locale che `IdentityDirectoryEvents` esegue Active Directory (AD). [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="88569-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="88569-108">Questa tabella acquisisce vari eventi correlati all'identità, come le modifiche delle password, la scadenza della password e le modifiche del nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="88569-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="88569-109">Acquisisce anche gli eventi di sistema nel controller di dominio, ad esempio la pianificazione delle attività e l'attività di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88569-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="88569-110">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="88569-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="88569-111">Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="88569-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="88569-112">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="88569-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="88569-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="88569-113">Column name</span></span> | <span data-ttu-id="88569-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="88569-114">Data type</span></span> | <span data-ttu-id="88569-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88569-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="88569-116">datetime</span><span class="sxs-lookup"><span data-stu-id="88569-116">datetime</span></span> | <span data-ttu-id="88569-117">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="88569-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="88569-118">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-118">string</span></span> | <span data-ttu-id="88569-119">Tipo di attività che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="88569-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="88569-120">Per informazioni [dettagliate, vedere](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) informazioni di riferimento sullo schema nel portale</span><span class="sxs-lookup"><span data-stu-id="88569-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="88569-121">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-121">string</span></span> | <span data-ttu-id="88569-122">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="88569-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="88569-123">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-123">string</span></span> | <span data-ttu-id="88569-124">Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="88569-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="88569-125">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-125">string</span></span> | <span data-ttu-id="88569-126">Nome visualizzato dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="88569-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="88569-127">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-127">string</span></span> | <span data-ttu-id="88569-128">Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="88569-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="88569-129">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-129">string</span></span> | <span data-ttu-id="88569-130">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="88569-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="88569-131">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-131">string</span></span> | <span data-ttu-id="88569-132">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="88569-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="88569-133">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-133">string</span></span> | <span data-ttu-id="88569-134">Porta di destinazione dell'attività</span><span class="sxs-lookup"><span data-stu-id="88569-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="88569-135">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-135">string</span></span> | <span data-ttu-id="88569-136">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="88569-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="88569-137">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-137">string</span></span> | <span data-ttu-id="88569-138">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="88569-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="88569-139">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-139">string</span></span> | <span data-ttu-id="88569-140">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="88569-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="88569-141">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-141">string</span></span> | <span data-ttu-id="88569-142">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="88569-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="88569-143">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-143">string</span></span> | <span data-ttu-id="88569-144">Identificatore di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="88569-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="88569-145">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-145">string</span></span> | <span data-ttu-id="88569-146">Identificatore univoco dell'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="88569-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="88569-147">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-147">string</span></span> | <span data-ttu-id="88569-148">Nome dell'utente dell'account visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="88569-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="88569-149">In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome.</span><span class="sxs-lookup"><span data-stu-id="88569-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="88569-150">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-150">string</span></span> | <span data-ttu-id="88569-151">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="88569-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="88569-152">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-152">string</span></span> | <span data-ttu-id="88569-153">Indirizzo IP assegnato al dispositivo durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="88569-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="88569-154">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-154">string</span></span> | <span data-ttu-id="88569-155">Porta TCP utilizzata durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="88569-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="88569-156">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-156">string</span></span> | <span data-ttu-id="88569-157">Città, paese o altra posizione geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="88569-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="88569-158">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-158">string</span></span> | <span data-ttu-id="88569-159">Provider di servizi Internet associato all'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="88569-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="88569-160">long</span><span class="sxs-lookup"><span data-stu-id="88569-160">long</span></span> | <span data-ttu-id="88569-161">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="88569-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="88569-162">stringa</span><span class="sxs-lookup"><span data-stu-id="88569-162">string</span></span> | <span data-ttu-id="88569-163">Informazioni aggiuntive sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="88569-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="88569-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="88569-164">Related topics</span></span>
- [<span data-ttu-id="88569-165">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="88569-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="88569-166">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="88569-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="88569-167">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="88569-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="88569-168">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="88569-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="88569-169">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="88569-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="88569-170">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="88569-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
