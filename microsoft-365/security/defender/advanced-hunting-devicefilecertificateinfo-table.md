---
title: Tabella DeviceFileCertificateInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla firma dei file nella tabella DeviceFileCertificateInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, firma digitale, certificato, firma file, DeviceFileCertificateInfo
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
ms.openlocfilehash: 272896c745386f13fc0e36301c5c16f5f24dbb42
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933674"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="a97b4-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="a97b4-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a97b4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a97b4-105">**Applies to:**</span></span>
- <span data-ttu-id="a97b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a97b4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a97b4-107">La `DeviceFileCertificateInfo` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sui certificati di firma dei file.</span><span class="sxs-lookup"><span data-stu-id="a97b4-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="a97b4-108">Questa tabella usa i dati ottenuti dalle attività di verifica dei certificati eseguite regolarmente sui file sugli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a97b4-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="a97b4-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a97b4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a97b4-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="a97b4-110">Column name</span></span> | <span data-ttu-id="a97b4-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a97b4-111">Data type</span></span> | <span data-ttu-id="a97b4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a97b4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a97b4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a97b4-113">datetime</span></span> | <span data-ttu-id="a97b4-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a97b4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a97b4-115">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-115">string</span></span> | <span data-ttu-id="a97b4-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="a97b4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a97b4-117">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-117">string</span></span> | <span data-ttu-id="a97b4-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="a97b4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="a97b4-119">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-119">string</span></span> | <span data-ttu-id="a97b4-120">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="a97b4-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="a97b4-121">boolean</span><span class="sxs-lookup"><span data-stu-id="a97b4-121">boolean</span></span> | <span data-ttu-id="a97b4-122">Indica se il file è firmato</span><span class="sxs-lookup"><span data-stu-id="a97b4-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="a97b4-123">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-123">string</span></span> | <span data-ttu-id="a97b4-124">Indica se le informazioni sulla firma sono stati letti come contenuto incorporato nel file stesso o letti da un file di catalogo esterno</span><span class="sxs-lookup"><span data-stu-id="a97b4-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="a97b4-125">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-125">string</span></span> | <span data-ttu-id="a97b4-126">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="a97b4-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="a97b4-127">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-127">string</span></span> | <span data-ttu-id="a97b4-128">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="a97b4-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="a97b4-129">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-129">string</span></span> | <span data-ttu-id="a97b4-130">Informazioni sull'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="a97b4-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="a97b4-131">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-131">string</span></span> | <span data-ttu-id="a97b4-132">Valore hash univoco che identifica l'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="a97b4-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="a97b4-133">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-133">string</span></span> | <span data-ttu-id="a97b4-134">Identificatore del certificato univoco dell'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="a97b4-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="a97b4-135">stringa</span><span class="sxs-lookup"><span data-stu-id="a97b4-135">string</span></span> |  <span data-ttu-id="a97b4-136">Array JSON che elenca gli URL delle condivisioni di rete che contengono certificati ed elenchi di revoche di certificati (CRL)</span><span class="sxs-lookup"><span data-stu-id="a97b4-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="a97b4-137">datetime</span><span class="sxs-lookup"><span data-stu-id="a97b4-137">datetime</span></span> | <span data-ttu-id="a97b4-138">Data e ora di creazione del certificato</span><span class="sxs-lookup"><span data-stu-id="a97b4-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="a97b4-139">datetime</span><span class="sxs-lookup"><span data-stu-id="a97b4-139">datetime</span></span> | <span data-ttu-id="a97b4-140">Data e ora di scadenza del certificato</span><span class="sxs-lookup"><span data-stu-id="a97b4-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="a97b4-141">datetime</span><span class="sxs-lookup"><span data-stu-id="a97b4-141">datetime</span></span> | <span data-ttu-id="a97b4-142">Data e ora in cui il certificato è stato controfirmato</span><span class="sxs-lookup"><span data-stu-id="a97b4-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="a97b4-143">boolean</span><span class="sxs-lookup"><span data-stu-id="a97b4-143">boolean</span></span> | <span data-ttu-id="a97b4-144">Indica se il file è attendibile in base ai risultati della funzione WinVerifyTrust, che verifica la presenza di informazioni sconosciute sul certificato radice, firme non valide, certificati revocati e altri attributi discutibile</span><span class="sxs-lookup"><span data-stu-id="a97b4-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="a97b4-145">boolean</span><span class="sxs-lookup"><span data-stu-id="a97b4-145">boolean</span></span> | <span data-ttu-id="a97b4-146">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="a97b4-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="a97b4-147">long</span><span class="sxs-lookup"><span data-stu-id="a97b4-147">long</span></span> | <span data-ttu-id="a97b4-148">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="a97b4-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a97b4-149">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="a97b4-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="a97b4-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a97b4-150">Related topics</span></span>
- [<span data-ttu-id="a97b4-151">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="a97b4-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a97b4-152">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="a97b4-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a97b4-153">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="a97b4-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a97b4-154">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="a97b4-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a97b4-155">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="a97b4-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a97b4-156">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="a97b4-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
