---
title: Tabella AADSpnSignInEventsBeta nello schema di caccia avanzato
description: Informazioni sui dati associati alla tabella eventi di accesso di Azure Active Directory Service Principal e Managed Identity per lo schema di ricerca avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, evidenza, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784300"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="a6668-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="a6668-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="a6668-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a6668-105">**Applies to:**</span></span>

- <span data-ttu-id="a6668-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6668-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="a6668-107">La `AADSpnSignInEventsBeta` tabella è attualmente in fase di beta e viene offerta a breve termine per consentire la caccia tramite gli eventi di accesso all'entità del servizio di Azure Active Directory (AAD) e dell'identità gestita.</span><span class="sxs-lookup"><span data-stu-id="a6668-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="a6668-108">Alla fine, verranno spostate tutte le informazioni dello schema di accesso alla `IdentityLogonEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="a6668-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="a6668-109">I clienti che possono accedere a Microsoft 365 Defender tramite la soluzione integrata Microsoft Defender for endpoint di Azure Security Center, ma non dispongono di licenze per Microsoft Defender per Office, Microsoft Defender for Identity o Microsoft cloud app Security, non saranno in grado di visualizzare questo schema.</span><span class="sxs-lookup"><span data-stu-id="a6668-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="a6668-110">La `AADSpnSignInEventsBeta` tabella nello schema di ricerca avanzata contiene informazioni sull'accesso all'entità servizio di Azure Active Directory e sugli accessi all'identità gestita. Per ulteriori informazioni sui diversi tipi di accesso ai report di attività di [accesso di Azure Active Directory, vedere Preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="a6668-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="a6668-111">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="a6668-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a6668-112">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="a6668-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="a6668-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="a6668-113">Column name</span></span>     | <span data-ttu-id="a6668-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a6668-114">Data type</span></span> | <span data-ttu-id="a6668-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6668-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="a6668-116">datetime</span><span class="sxs-lookup"><span data-stu-id="a6668-116">datetime</span></span>      | <span data-ttu-id="a6668-117">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="a6668-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="a6668-118">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-118">string</span></span>        | <span data-ttu-id="a6668-119">Applicazione in cui è stata eseguita l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="a6668-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="a6668-120">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-120">string</span></span>        | <span data-ttu-id="a6668-121">Identificatore univoco per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="a6668-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="a6668-122">boolean</span><span class="sxs-lookup"><span data-stu-id="a6668-122">boolean</span></span>       | <span data-ttu-id="a6668-123">Indica se l'accesso è stato avviato da un'identità gestita</span><span class="sxs-lookup"><span data-stu-id="a6668-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="a6668-124">int</span><span class="sxs-lookup"><span data-stu-id="a6668-124">int</span></span>        | <span data-ttu-id="a6668-125">Contiene il codice di errore nel caso in cui si verifichi un errore di accesso.</span><span class="sxs-lookup"><span data-stu-id="a6668-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="a6668-126">Per trovare una descrizione di un codice di errore specifico, visitare <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="a6668-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="a6668-127">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-127">string</span></span>        | <span data-ttu-id="a6668-128">Identificatore univoco dell'evento di accesso</span><span class="sxs-lookup"><span data-stu-id="a6668-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="a6668-129">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-129">string</span></span>        | <span data-ttu-id="a6668-130">Nome dell'entità servizio che ha avviato l'accesso</span><span class="sxs-lookup"><span data-stu-id="a6668-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="a6668-131">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-131">string</span></span>        | <span data-ttu-id="a6668-132">Identificatore univoco dell'entità servizio che ha avviato l'accesso</span><span class="sxs-lookup"><span data-stu-id="a6668-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="a6668-133">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-133">string</span></span>        | <span data-ttu-id="a6668-134">Nome visualizzato della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="a6668-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="a6668-135">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-135">string</span></span>        | <span data-ttu-id="a6668-136">Identificatore univoco della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="a6668-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="a6668-137">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-137">string</span></span>        | <span data-ttu-id="a6668-138">Identificatore univoco del tenant della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="a6668-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="a6668-139">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-139">string</span></span>        | <span data-ttu-id="a6668-140">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="a6668-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="a6668-141">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-141">string</span></span>        | <span data-ttu-id="a6668-142">Codice di due lettere che indica il paese in cui l'indirizzo IP del client è Geolocated</span><span class="sxs-lookup"><span data-stu-id="a6668-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="a6668-143">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-143">string</span></span>        | <span data-ttu-id="a6668-144">Stato in cui si è verificato l'accesso, se disponibile</span><span class="sxs-lookup"><span data-stu-id="a6668-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="a6668-145">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-145">string</span></span>        | <span data-ttu-id="a6668-146">Città in cui si trova l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="a6668-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="a6668-147">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-147">string</span></span>        | <span data-ttu-id="a6668-148">Le coordinate nord-sud del percorso di accesso</span><span class="sxs-lookup"><span data-stu-id="a6668-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="a6668-149">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-149">string</span></span>        | <span data-ttu-id="a6668-150">Le coordinate da est a ovest del percorso di accesso</span><span class="sxs-lookup"><span data-stu-id="a6668-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="a6668-151">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-151">string</span></span>        | <span data-ttu-id="a6668-152">Identificatore univoco della richiesta</span><span class="sxs-lookup"><span data-stu-id="a6668-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="a6668-153">stringa</span><span class="sxs-lookup"><span data-stu-id="a6668-153">string</span></span> | <span data-ttu-id="a6668-154">Identificatore univoco per l'evento</span><span class="sxs-lookup"><span data-stu-id="a6668-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="a6668-155">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="a6668-155">Related articles</span></span>

-   [<span data-ttu-id="a6668-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="a6668-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="a6668-157">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="a6668-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="a6668-158">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="a6668-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="a6668-159">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="a6668-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

