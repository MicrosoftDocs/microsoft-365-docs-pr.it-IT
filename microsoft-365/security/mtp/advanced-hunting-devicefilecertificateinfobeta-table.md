---
title: Tabella DeviceFileCertificateInfoBeta nello schema di caccia avanzato
description: Informazioni sulla firma dei file nella tabella DeviceFileCertificateInfoBeta dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, firma digitale, certificato, firma dei file, DeviceFileCertificateInfoBeta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d51fc812ffb82d9af1f706e513498da7611a1a6b
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210468"
---
# <a name="devicefilecertificateinfobeta"></a><span data-ttu-id="29a35-104">DeviceFileCertificateInfoBeta</span><span class="sxs-lookup"><span data-stu-id="29a35-104">DeviceFileCertificateInfoBeta</span></span>

<span data-ttu-id="29a35-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="29a35-105">**Applies to:**</span></span>
- <span data-ttu-id="29a35-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="29a35-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="29a35-107">La `DeviceFileCertificateInfoBeta` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sui certificati di firma dei file.</span><span class="sxs-lookup"><span data-stu-id="29a35-107">The `DeviceFileCertificateInfoBeta` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="29a35-108">In questa tabella vengono utilizzati i dati ottenuti dalle attività di verifica dei certificati eseguite regolarmente sui file negli endpoint.</span><span class="sxs-lookup"><span data-stu-id="29a35-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="29a35-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="29a35-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="29a35-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="29a35-110">Column name</span></span> | <span data-ttu-id="29a35-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="29a35-111">Data type</span></span> | <span data-ttu-id="29a35-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29a35-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="29a35-113">datetime</span><span class="sxs-lookup"><span data-stu-id="29a35-113">datetime</span></span> | <span data-ttu-id="29a35-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="29a35-114">Date and time when the event was recorded</span></span>
| `DeviceId` | <span data-ttu-id="29a35-115">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-115">string</span></span> | <span data-ttu-id="29a35-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="29a35-116">Unique identifier for the machine in the service</span></span>
| `DeviceName` | <span data-ttu-id="29a35-117">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-117">string</span></span> | <span data-ttu-id="29a35-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="29a35-118">Fully qualified domain name (FQDN) of the machine</span></span>
| `SHA1` | <span data-ttu-id="29a35-119">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-119">string</span></span> | <span data-ttu-id="29a35-120">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="29a35-120">SHA-1 of the file that the recorded action was applied to</span></span>
| `IsSigned` | <span data-ttu-id="29a35-121">boolean</span><span class="sxs-lookup"><span data-stu-id="29a35-121">boolean</span></span> | <span data-ttu-id="29a35-122">Indica se il file è firmato</span><span class="sxs-lookup"><span data-stu-id="29a35-122">Indicates whether the file is signed</span></span>
| `SignatureType` | <span data-ttu-id="29a35-123">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-123">string</span></span> | <span data-ttu-id="29a35-124">Indica se le informazioni sulla firma sono state lette come contenuto incorporato nel file stesso o lette da un file di catalogo esterno.</span><span class="sxs-lookup"><span data-stu-id="29a35-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span>
| `Signer` | <span data-ttu-id="29a35-125">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-125">string</span></span> | <span data-ttu-id="29a35-126">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="29a35-126">Information about the signer of the file</span></span>
| `SignerHash` | <span data-ttu-id="29a35-127">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-127">string</span></span> | <span data-ttu-id="29a35-128">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="29a35-128">Unique hash value identifying the signer</span></span>
| `Issuer` | <span data-ttu-id="29a35-129">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-129">string</span></span> | <span data-ttu-id="29a35-130">Informazioni sull'autorità di certificazione (CA) di emissione</span><span class="sxs-lookup"><span data-stu-id="29a35-130">Information about the issuing certificate authority (CA)</span></span>
| `IssuerHash` | <span data-ttu-id="29a35-131">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-131">string</span></span> | <span data-ttu-id="29a35-132">Valore hash univoco che identifica l'autorità di certificazione (CA) di emissione</span><span class="sxs-lookup"><span data-stu-id="29a35-132">Unique hash value identifying issuing certificate authority (CA)</span></span>
| `CrlDistributionPointUrls` | <span data-ttu-id="29a35-133">stringa</span><span class="sxs-lookup"><span data-stu-id="29a35-133">string</span></span> |  <span data-ttu-id="29a35-134">URL della condivisione di rete che contiene i certificati e l'elenco di revoche di certificati (CRL)</span><span class="sxs-lookup"><span data-stu-id="29a35-134">URL of the network share that contains certificates and the certificate revocation list (CRL)</span></span>
| `CertificateCreationTime` | <span data-ttu-id="29a35-135">datetime</span><span class="sxs-lookup"><span data-stu-id="29a35-135">datetime</span></span> | <span data-ttu-id="29a35-136">Data e ora in cui è stato creato il certificato</span><span class="sxs-lookup"><span data-stu-id="29a35-136">Date and time the certificate was created</span></span>
| `CertificateExpirationTime` | <span data-ttu-id="29a35-137">datetime</span><span class="sxs-lookup"><span data-stu-id="29a35-137">datetime</span></span> | <span data-ttu-id="29a35-138">Data e ora in cui il certificato è impostato per scadere</span><span class="sxs-lookup"><span data-stu-id="29a35-138">Date and time the certificate is set to expire</span></span>
| `CertificateCountersignatureTime` | <span data-ttu-id="29a35-139">datetime</span><span class="sxs-lookup"><span data-stu-id="29a35-139">datetime</span></span> | <span data-ttu-id="29a35-140">Data e ora in cui il certificato è stato controfirmato</span><span class="sxs-lookup"><span data-stu-id="29a35-140">Date and time the certificate was countersigned</span></span>
| `IsTrusted` | <span data-ttu-id="29a35-141">boolean</span><span class="sxs-lookup"><span data-stu-id="29a35-141">boolean</span></span> | <span data-ttu-id="29a35-142">Indica se il file è attendibile in base ai risultati della funzione WinVerifyTrust, che consente di verificare la presenza di informazioni sul certificato radice sconosciute, firme non valide, certificati revocati e altri attributi discutibili.</span><span class="sxs-lookup"><span data-stu-id="29a35-142">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span>
| `IsRootSignerMicrosoft` | <span data-ttu-id="29a35-143">boolean</span><span class="sxs-lookup"><span data-stu-id="29a35-143">boolean</span></span> | <span data-ttu-id="29a35-144">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="29a35-144">Indicates whether the signer of the root certificate is Microsoft</span></span>
| `ReportId` | <span data-ttu-id="29a35-145">long</span><span class="sxs-lookup"><span data-stu-id="29a35-145">long</span></span> | <span data-ttu-id="29a35-146">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="29a35-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="29a35-147">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp.</span><span class="sxs-lookup"><span data-stu-id="29a35-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span>

## <a name="related-topics"></a><span data-ttu-id="29a35-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="29a35-148">Related topics</span></span>
- [<span data-ttu-id="29a35-149">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="29a35-149">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="29a35-150">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="29a35-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="29a35-151">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="29a35-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="29a35-152">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="29a35-152">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="29a35-153">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="29a35-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="29a35-154">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="29a35-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)