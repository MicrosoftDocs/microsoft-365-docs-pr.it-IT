---
title: Tabella IdentityDirectoryEvents nello schema di caccia avanzato
description: Informazioni sui controller di dominio e sugli eventi di Active Directory nella tabella IdentityDirectoryEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, IdentityDirectoryEvents, controller di dominio, Active Directory, Azure ATP, identità
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 41b429e32122d6cc58a746649c8a0428f0a90b0f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847429"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="921cf-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="921cf-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="921cf-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="921cf-105">**Applies to:**</span></span>
- <span data-ttu-id="921cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="921cf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="921cf-107">La `IdentityDirectoryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene gli eventi che coinvolgono un controller di dominio locale che esegue Active Directory (ad).</span><span class="sxs-lookup"><span data-stu-id="921cf-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="921cf-108">In questa tabella vengono acquisiti vari eventi relativi all'identità, come le modifiche alle password, la scadenza della password e le modifiche del nome dell'entità utente (UPN, User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="921cf-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="921cf-109">Acquisisce inoltre gli eventi di sistema nel controller di dominio, ad esempio la pianificazione delle attività e l'attività di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="921cf-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="921cf-110">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="921cf-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="921cf-111">Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="921cf-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="921cf-112">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="921cf-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="921cf-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="921cf-113">Column name</span></span> | <span data-ttu-id="921cf-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="921cf-114">Data type</span></span> | <span data-ttu-id="921cf-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="921cf-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="921cf-116">datetime</span><span class="sxs-lookup"><span data-stu-id="921cf-116">datetime</span></span> | <span data-ttu-id="921cf-117">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="921cf-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="921cf-118">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-118">string</span></span> | <span data-ttu-id="921cf-119">Tipo di attività che ha attivato l'evento.</span><span class="sxs-lookup"><span data-stu-id="921cf-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="921cf-120">Per informazioni dettagliate, vedere la Guida [di riferimento allo schema in-Portal.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="921cf-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="921cf-121">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-121">string</span></span> | <span data-ttu-id="921cf-122">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="921cf-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="921cf-123">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-123">string</span></span> | <span data-ttu-id="921cf-124">Nome dell'entità utente (UPN) dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="921cf-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="921cf-125">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-125">string</span></span> | <span data-ttu-id="921cf-126">Nome visualizzato dell'account a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="921cf-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="921cf-127">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-127">string</span></span> | <span data-ttu-id="921cf-128">Nome di dominio completo (FQDN) del dispositivo a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="921cf-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="921cf-129">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-129">string</span></span> | <span data-ttu-id="921cf-130">Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="921cf-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="921cf-131">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-131">string</span></span> | <span data-ttu-id="921cf-132">Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="921cf-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="921cf-133">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-133">string</span></span> | <span data-ttu-id="921cf-134">Porta di destinazione dell'attività</span><span class="sxs-lookup"><span data-stu-id="921cf-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="921cf-135">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-135">string</span></span> | <span data-ttu-id="921cf-136">Protocollo utilizzato durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="921cf-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="921cf-137">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-137">string</span></span> | <span data-ttu-id="921cf-138">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="921cf-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="921cf-139">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-139">string</span></span> | <span data-ttu-id="921cf-140">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="921cf-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="921cf-141">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-141">string</span></span> | <span data-ttu-id="921cf-142">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="921cf-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="921cf-143">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-143">string</span></span> | <span data-ttu-id="921cf-144">ID di sicurezza (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="921cf-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="921cf-145">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-145">string</span></span> | <span data-ttu-id="921cf-146">Identificatore univoco per l'account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="921cf-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="921cf-147">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-147">string</span></span> | <span data-ttu-id="921cf-148">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="921cf-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="921cf-149">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="921cf-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="921cf-150">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-150">string</span></span> | <span data-ttu-id="921cf-151">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="921cf-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="921cf-152">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-152">string</span></span> | <span data-ttu-id="921cf-153">Indirizzo IP assegnato al dispositivo durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="921cf-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="921cf-154">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-154">string</span></span> | <span data-ttu-id="921cf-155">Porta TCP utilizzata durante la comunicazione</span><span class="sxs-lookup"><span data-stu-id="921cf-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="921cf-156">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-156">string</span></span> | <span data-ttu-id="921cf-157">Città, paese o altra località geografica associata all'evento</span><span class="sxs-lookup"><span data-stu-id="921cf-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="921cf-158">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-158">string</span></span> | <span data-ttu-id="921cf-159">Provider di servizi Internet associato all'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="921cf-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="921cf-160">long</span><span class="sxs-lookup"><span data-stu-id="921cf-160">long</span></span> | <span data-ttu-id="921cf-161">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="921cf-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="921cf-162">stringa</span><span class="sxs-lookup"><span data-stu-id="921cf-162">string</span></span> | <span data-ttu-id="921cf-163">Ulteriori informazioni sull'entità o sull'evento</span><span class="sxs-lookup"><span data-stu-id="921cf-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="921cf-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="921cf-164">Related topics</span></span>
- [<span data-ttu-id="921cf-165">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="921cf-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="921cf-166">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="921cf-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="921cf-167">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="921cf-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="921cf-168">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="921cf-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="921cf-169">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="921cf-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="921cf-170">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="921cf-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
