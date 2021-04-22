---
title: Tabella AADSpnSignInEventsBeta nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate all'entità servizio di Azure Active Directory e alla tabella degli eventi di accesso delle identità gestite dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AlertInfo, avviso, entità, prova, file, indirizzo IP, dispositivo, computer, utente, account, identità, AAD
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
ms.openlocfilehash: 984e945107b6e0b41459659a7f2e9f649981e4b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932596"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="e535f-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="e535f-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="e535f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e535f-105">**Applies to:**</span></span>

- <span data-ttu-id="e535f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e535f-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e535f-107">La tabella è attualmente in versione beta e viene offerta a breve termine per consentire la ricerca tramite l'entità servizio `AADSpnSignInEventsBeta` di Azure Active Directory (AAD) e gli eventi di accesso delle identità gestite.</span><span class="sxs-lookup"><span data-stu-id="e535f-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="e535f-108">Alla fine verranno spostate tutte le informazioni sullo schema di accesso nella `IdentityLogonEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="e535f-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="e535f-109">I clienti che possono accedere a Microsoft 365 Defender tramite la soluzione Microsoft Defender for Endpoint integrata di Azure Defender, ma non dispongono di licenze per Microsoft Defender per Office, Microsoft Defender for Identity o Microsoft Cloud App Security, non potranno visualizzare questo schema.</span><span class="sxs-lookup"><span data-stu-id="e535f-109">Customers who can access Microsoft 365 Defender through the Azure Defender’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="e535f-110">La tabella nello schema di ricerca avanzata contiene informazioni sull'entità servizio di Azure Active Directory e sugli account `AADSpnSignInEventsBeta` di accesso delle identità gestite. Ulteriori informazioni sui diversi tipi di accesso sono disponibili nei report attività di accesso di [Azure Active Directory - anteprima.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="e535f-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="e535f-111">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="e535f-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e535f-112">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="e535f-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="e535f-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="e535f-113">Column name</span></span>     | <span data-ttu-id="e535f-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e535f-114">Data type</span></span> | <span data-ttu-id="e535f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e535f-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="e535f-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e535f-116">datetime</span></span>      | <span data-ttu-id="e535f-117">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="e535f-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="e535f-118">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-118">string</span></span>        | <span data-ttu-id="e535f-119">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="e535f-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="e535f-120">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-120">string</span></span>        | <span data-ttu-id="e535f-121">Identificatore univoco dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="e535f-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="e535f-122">boolean</span><span class="sxs-lookup"><span data-stu-id="e535f-122">boolean</span></span>       | <span data-ttu-id="e535f-123">Indica se l'accesso è stato avviato da un'identità gestita</span><span class="sxs-lookup"><span data-stu-id="e535f-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="e535f-124">int</span><span class="sxs-lookup"><span data-stu-id="e535f-124">int</span></span>        | <span data-ttu-id="e535f-125">Contiene il codice di errore se si verifica un errore di accesso.</span><span class="sxs-lookup"><span data-stu-id="e535f-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="e535f-126">Per trovare una descrizione di un codice di errore specifico, visitare <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="e535f-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="e535f-127">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-127">string</span></span>        | <span data-ttu-id="e535f-128">Identificatore univoco dell'evento di accesso</span><span class="sxs-lookup"><span data-stu-id="e535f-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="e535f-129">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-129">string</span></span>        | <span data-ttu-id="e535f-130">Nome dell'entità servizio che ha avviato l'accesso</span><span class="sxs-lookup"><span data-stu-id="e535f-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="e535f-131">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-131">string</span></span>        | <span data-ttu-id="e535f-132">Identificatore univoco dell'entità servizio che ha avviato l'accesso</span><span class="sxs-lookup"><span data-stu-id="e535f-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="e535f-133">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-133">string</span></span>        | <span data-ttu-id="e535f-134">Nome visualizzato della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="e535f-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="e535f-135">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-135">string</span></span>        | <span data-ttu-id="e535f-136">Identificatore univoco della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="e535f-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="e535f-137">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-137">string</span></span>        | <span data-ttu-id="e535f-138">Identificatore univoco del tenant della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="e535f-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="e535f-139">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-139">string</span></span>        | <span data-ttu-id="e535f-140">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="e535f-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="e535f-141">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-141">string</span></span>        | <span data-ttu-id="e535f-142">Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocale</span><span class="sxs-lookup"><span data-stu-id="e535f-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="e535f-143">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-143">string</span></span>        | <span data-ttu-id="e535f-144">Stato in cui si è verificato l'accesso, se disponibile</span><span class="sxs-lookup"><span data-stu-id="e535f-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="e535f-145">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-145">string</span></span>        | <span data-ttu-id="e535f-146">Città in cui si trova l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="e535f-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="e535f-147">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-147">string</span></span>        | <span data-ttu-id="e535f-148">Coordinate da nord a sud della posizione di accesso</span><span class="sxs-lookup"><span data-stu-id="e535f-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="e535f-149">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-149">string</span></span>        | <span data-ttu-id="e535f-150">Coordinate da est a ovest della posizione di accesso</span><span class="sxs-lookup"><span data-stu-id="e535f-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="e535f-151">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-151">string</span></span>        | <span data-ttu-id="e535f-152">Identificatore univoco della richiesta</span><span class="sxs-lookup"><span data-stu-id="e535f-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="e535f-153">stringa</span><span class="sxs-lookup"><span data-stu-id="e535f-153">string</span></span> | <span data-ttu-id="e535f-154">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="e535f-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="e535f-155">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="e535f-155">Related articles</span></span>

-   [<span data-ttu-id="e535f-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="e535f-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="e535f-157">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="e535f-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="e535f-158">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="e535f-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="e535f-159">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="e535f-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)