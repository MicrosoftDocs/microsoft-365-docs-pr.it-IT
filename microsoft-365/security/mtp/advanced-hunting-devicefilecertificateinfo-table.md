---
title: Tabella DeviceFileCertificateInfo nello schema di caccia avanzato
description: Informazioni sulla firma dei file nella tabella DeviceFileCertificateInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, firma digitale, certificato, firma dei file, DeviceFileCertificateInfo
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
ms.openlocfilehash: cba27b5b43141c8c90f9a8bc7f70c55aabc1979d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899316"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="53df0-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="53df0-104">DeviceFileCertificateInfo</span></span>

<span data-ttu-id="53df0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="53df0-105">**Applies to:**</span></span>
- <span data-ttu-id="53df0-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="53df0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="53df0-107">La `DeviceFileCertificateInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sui certificati di firma dei file.</span><span class="sxs-lookup"><span data-stu-id="53df0-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="53df0-108">In questa tabella vengono utilizzati i dati ottenuti dalle attività di verifica dei certificati eseguite regolarmente sui file negli endpoint.</span><span class="sxs-lookup"><span data-stu-id="53df0-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="53df0-109">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="53df0-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="53df0-110">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="53df0-110">Column name</span></span> | <span data-ttu-id="53df0-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="53df0-111">Data type</span></span> | <span data-ttu-id="53df0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53df0-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="53df0-113">datetime</span><span class="sxs-lookup"><span data-stu-id="53df0-113">datetime</span></span> | <span data-ttu-id="53df0-114">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="53df0-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="53df0-115">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-115">string</span></span> | <span data-ttu-id="53df0-116">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="53df0-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="53df0-117">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-117">string</span></span> | <span data-ttu-id="53df0-118">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="53df0-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="53df0-119">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-119">string</span></span> | <span data-ttu-id="53df0-120">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="53df0-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="53df0-121">boolean</span><span class="sxs-lookup"><span data-stu-id="53df0-121">boolean</span></span> | <span data-ttu-id="53df0-122">Indica se il file è firmato</span><span class="sxs-lookup"><span data-stu-id="53df0-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="53df0-123">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-123">string</span></span> | <span data-ttu-id="53df0-124">Indica se le informazioni sulla firma sono state lette come contenuto incorporato nel file stesso o lette da un file di catalogo esterno.</span><span class="sxs-lookup"><span data-stu-id="53df0-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="53df0-125">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-125">string</span></span> | <span data-ttu-id="53df0-126">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="53df0-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="53df0-127">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-127">string</span></span> | <span data-ttu-id="53df0-128">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="53df0-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="53df0-129">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-129">string</span></span> | <span data-ttu-id="53df0-130">Informazioni sull'autorità di certificazione (CA) di emissione</span><span class="sxs-lookup"><span data-stu-id="53df0-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="53df0-131">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-131">string</span></span> | <span data-ttu-id="53df0-132">Valore hash univoco che identifica l'autorità di certificazione (CA) di emissione</span><span class="sxs-lookup"><span data-stu-id="53df0-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="53df0-133">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-133">string</span></span> | <span data-ttu-id="53df0-134">Identificatore del certificato univoco per l'autorità di certificazione (CA) di emissione</span><span class="sxs-lookup"><span data-stu-id="53df0-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="53df0-135">stringa</span><span class="sxs-lookup"><span data-stu-id="53df0-135">string</span></span> |  <span data-ttu-id="53df0-136">Array JSON che elenca gli URL delle condivisioni di rete che contengono certificati e elenchi di revoche di certificati (CRL)</span><span class="sxs-lookup"><span data-stu-id="53df0-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="53df0-137">datetime</span><span class="sxs-lookup"><span data-stu-id="53df0-137">datetime</span></span> | <span data-ttu-id="53df0-138">Data e ora in cui è stato creato il certificato</span><span class="sxs-lookup"><span data-stu-id="53df0-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="53df0-139">datetime</span><span class="sxs-lookup"><span data-stu-id="53df0-139">datetime</span></span> | <span data-ttu-id="53df0-140">Data e ora in cui il certificato è impostato per scadere</span><span class="sxs-lookup"><span data-stu-id="53df0-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="53df0-141">datetime</span><span class="sxs-lookup"><span data-stu-id="53df0-141">datetime</span></span> | <span data-ttu-id="53df0-142">Data e ora in cui il certificato è stato controfirmato</span><span class="sxs-lookup"><span data-stu-id="53df0-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="53df0-143">boolean</span><span class="sxs-lookup"><span data-stu-id="53df0-143">boolean</span></span> | <span data-ttu-id="53df0-144">Indica se il file è attendibile in base ai risultati della funzione WinVerifyTrust, che consente di verificare la presenza di informazioni sul certificato radice sconosciute, firme non valide, certificati revocati e altri attributi discutibili.</span><span class="sxs-lookup"><span data-stu-id="53df0-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="53df0-145">boolean</span><span class="sxs-lookup"><span data-stu-id="53df0-145">boolean</span></span> | <span data-ttu-id="53df0-146">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="53df0-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="53df0-147">long</span><span class="sxs-lookup"><span data-stu-id="53df0-147">long</span></span> | <span data-ttu-id="53df0-148">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="53df0-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="53df0-149">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp.</span><span class="sxs-lookup"><span data-stu-id="53df0-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="53df0-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="53df0-150">Related topics</span></span>
- [<span data-ttu-id="53df0-151">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="53df0-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="53df0-152">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="53df0-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="53df0-153">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="53df0-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="53df0-154">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="53df0-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="53df0-155">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="53df0-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="53df0-156">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="53df0-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
