---
title: Tabella AADSpnSignInEventsBeta nello schema di ricerca avanzata
description: Informazioni sulle informazioni associate all'entità Azure Active Directory e agli eventi di accesso dell'identità gestita della tabella degli eventi di ricerca avanzata
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347908"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="6d86d-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="6d86d-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="6d86d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6d86d-105">**Applies to:**</span></span>

- <span data-ttu-id="6d86d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d86d-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6d86d-107">La tabella è attualmente in versione beta e viene offerta a breve termine per consentire la ricerca tramite l'entità servizio Azure Active Directory (AAD) e gli eventi di accesso delle identità `AADSpnSignInEventsBeta` gestite.</span><span class="sxs-lookup"><span data-stu-id="6d86d-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="6d86d-108">Alla fine verranno spostate tutte le informazioni sullo schema di accesso nella `IdentityLogonEvents` tabella.</span><span class="sxs-lookup"><span data-stu-id="6d86d-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="6d86d-109">La `AADSpnSignInEventsBeta` tabella nello schema di ricerca avanzata contiene informazioni sull Azure Active Directory'entità servizio e sugli account di accesso delle identità gestite. Ulteriori informazioni sui diversi tipi di accesso in Azure Active Directory attività di [accesso - anteprima.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="6d86d-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="6d86d-110">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="6d86d-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6d86d-111">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="6d86d-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="6d86d-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="6d86d-112">Column name</span></span> | <span data-ttu-id="6d86d-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6d86d-113">Data type</span></span> | <span data-ttu-id="6d86d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d86d-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="6d86d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="6d86d-115">datetime</span></span> | <span data-ttu-id="6d86d-116">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="6d86d-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="6d86d-117">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-117">string</span></span> | <span data-ttu-id="6d86d-118">Applicazione che ha eseguito l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="6d86d-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="6d86d-119">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-119">string</span></span> | <span data-ttu-id="6d86d-120">Identificatore univoco dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6d86d-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="6d86d-121">boolean</span><span class="sxs-lookup"><span data-stu-id="6d86d-121">boolean</span></span>       | <span data-ttu-id="6d86d-122">Indica se l'accesso è stato avviato da un'identità gestita</span><span class="sxs-lookup"><span data-stu-id="6d86d-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="6d86d-123">int</span><span class="sxs-lookup"><span data-stu-id="6d86d-123">int</span></span> | <span data-ttu-id="6d86d-124">Contiene il codice di errore se si verifica un errore di accesso.</span><span class="sxs-lookup"><span data-stu-id="6d86d-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="6d86d-125">Per trovare una descrizione di un codice di errore specifico, visitare <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="6d86d-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="6d86d-126">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-126">string</span></span>        | <span data-ttu-id="6d86d-127">Identificatore univoco dell'evento di accesso</span><span class="sxs-lookup"><span data-stu-id="6d86d-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="6d86d-128">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-128">string</span></span>        | <span data-ttu-id="6d86d-129">Nome dell'entità servizio che ha avviato l'accesso</span><span class="sxs-lookup"><span data-stu-id="6d86d-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="6d86d-130">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-130">string</span></span>        | <span data-ttu-id="6d86d-131">Identificatore univoco dell'entità servizio che ha avviato l'accesso</span><span class="sxs-lookup"><span data-stu-id="6d86d-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="6d86d-132">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-132">string</span></span>        | <span data-ttu-id="6d86d-133">Nome visualizzato della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="6d86d-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="6d86d-134">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-134">string</span></span>        | <span data-ttu-id="6d86d-135">Identificatore univoco della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="6d86d-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="6d86d-136">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-136">string</span></span>        | <span data-ttu-id="6d86d-137">Identificatore univoco del tenant della risorsa a cui si accede</span><span class="sxs-lookup"><span data-stu-id="6d86d-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="6d86d-138">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-138">string</span></span>        | <span data-ttu-id="6d86d-139">Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate</span><span class="sxs-lookup"><span data-stu-id="6d86d-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="6d86d-140">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-140">string</span></span>        | <span data-ttu-id="6d86d-141">Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocale</span><span class="sxs-lookup"><span data-stu-id="6d86d-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="6d86d-142">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-142">string</span></span>        | <span data-ttu-id="6d86d-143">Stato in cui si è verificato l'accesso, se disponibile</span><span class="sxs-lookup"><span data-stu-id="6d86d-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="6d86d-144">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-144">string</span></span>        | <span data-ttu-id="6d86d-145">Città in cui si trova l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="6d86d-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="6d86d-146">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-146">string</span></span>        | <span data-ttu-id="6d86d-147">Coordinate da nord a sud della posizione di accesso</span><span class="sxs-lookup"><span data-stu-id="6d86d-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="6d86d-148">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-148">string</span></span>        | <span data-ttu-id="6d86d-149">Coordinate da est a ovest della posizione di accesso</span><span class="sxs-lookup"><span data-stu-id="6d86d-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="6d86d-150">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-150">string</span></span>        | <span data-ttu-id="6d86d-151">Identificatore univoco della richiesta</span><span class="sxs-lookup"><span data-stu-id="6d86d-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="6d86d-152">stringa</span><span class="sxs-lookup"><span data-stu-id="6d86d-152">string</span></span> | <span data-ttu-id="6d86d-153">Identificatore univoco dell'evento</span><span class="sxs-lookup"><span data-stu-id="6d86d-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="6d86d-154">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="6d86d-154">Related articles</span></span>

-   [<span data-ttu-id="6d86d-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="6d86d-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="6d86d-156">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="6d86d-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="6d86d-157">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="6d86d-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="6d86d-158">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="6d86d-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
