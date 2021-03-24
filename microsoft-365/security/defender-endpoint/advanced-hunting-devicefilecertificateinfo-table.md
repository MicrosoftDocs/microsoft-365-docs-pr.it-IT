---
title: Tabella DeviceFileCertificateInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla firma dei file nella tabella DeviceFileCertificateInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, firma digitale, certificato, firma file, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064381"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="8a1e0-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="8a1e0-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a1e0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8a1e0-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a1e0-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8a1e0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="8a1e0-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8a1e0-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8a1e0-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="8a1e0-109">La `DeviceFileCertificateInfo` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sui certificati di firma dei file.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="8a1e0-110">Questa tabella usa i dati ottenuti dalle attività di verifica dei certificati eseguite regolarmente sui file sugli endpoint.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="8a1e0-111">Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="8a1e0-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="8a1e0-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="8a1e0-112">Column name</span></span> | <span data-ttu-id="8a1e0-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8a1e0-113">Data type</span></span> | <span data-ttu-id="8a1e0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a1e0-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8a1e0-115">datetime</span><span class="sxs-lookup"><span data-stu-id="8a1e0-115">datetime</span></span> | <span data-ttu-id="8a1e0-116">Data e ora di registrazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="8a1e0-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8a1e0-117">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-117">string</span></span> | <span data-ttu-id="8a1e0-118">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="8a1e0-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8a1e0-119">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-119">string</span></span> | <span data-ttu-id="8a1e0-120">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="8a1e0-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="8a1e0-121">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-121">string</span></span> | <span data-ttu-id="8a1e0-122">SHA-1 del file a cui è stata applicata l'azione registrata</span><span class="sxs-lookup"><span data-stu-id="8a1e0-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="8a1e0-123">boolean</span><span class="sxs-lookup"><span data-stu-id="8a1e0-123">boolean</span></span> | <span data-ttu-id="8a1e0-124">Indica se il file è firmato</span><span class="sxs-lookup"><span data-stu-id="8a1e0-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="8a1e0-125">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-125">string</span></span> | <span data-ttu-id="8a1e0-126">Indica se le informazioni sulla firma sono stati letti come contenuto incorporato nel file stesso o letti da un file di catalogo esterno</span><span class="sxs-lookup"><span data-stu-id="8a1e0-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="8a1e0-127">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-127">string</span></span> | <span data-ttu-id="8a1e0-128">Informazioni sul firmatario del file</span><span class="sxs-lookup"><span data-stu-id="8a1e0-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="8a1e0-129">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-129">string</span></span> | <span data-ttu-id="8a1e0-130">Valore hash univoco che identifica il firmatario</span><span class="sxs-lookup"><span data-stu-id="8a1e0-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="8a1e0-131">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-131">string</span></span> | <span data-ttu-id="8a1e0-132">Informazioni sull'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="8a1e0-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="8a1e0-133">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-133">string</span></span> | <span data-ttu-id="8a1e0-134">Valore hash univoco che identifica l'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="8a1e0-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="8a1e0-135">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-135">string</span></span> | <span data-ttu-id="8a1e0-136">Identificatore del certificato univoco dell'autorità di certificazione (CA) emittente</span><span class="sxs-lookup"><span data-stu-id="8a1e0-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="8a1e0-137">stringa</span><span class="sxs-lookup"><span data-stu-id="8a1e0-137">string</span></span> |  <span data-ttu-id="8a1e0-138">Array JSON che elenca gli URL delle condivisioni di rete che contengono certificati ed elenchi di revoche di certificati (CRL)</span><span class="sxs-lookup"><span data-stu-id="8a1e0-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="8a1e0-139">datetime</span><span class="sxs-lookup"><span data-stu-id="8a1e0-139">datetime</span></span> | <span data-ttu-id="8a1e0-140">Data e ora di creazione del certificato</span><span class="sxs-lookup"><span data-stu-id="8a1e0-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="8a1e0-141">datetime</span><span class="sxs-lookup"><span data-stu-id="8a1e0-141">datetime</span></span> | <span data-ttu-id="8a1e0-142">Data e ora di scadenza del certificato</span><span class="sxs-lookup"><span data-stu-id="8a1e0-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="8a1e0-143">datetime</span><span class="sxs-lookup"><span data-stu-id="8a1e0-143">datetime</span></span> | <span data-ttu-id="8a1e0-144">Data e ora in cui il certificato è stato controfirmato</span><span class="sxs-lookup"><span data-stu-id="8a1e0-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="8a1e0-145">boolean</span><span class="sxs-lookup"><span data-stu-id="8a1e0-145">boolean</span></span> | <span data-ttu-id="8a1e0-146">Indica se il file è attendibile in base ai risultati della funzione WinVerifyTrust, che verifica la presenza di informazioni sconosciute sul certificato radice, firme non valide, certificati revocati e altri attributi discutibile</span><span class="sxs-lookup"><span data-stu-id="8a1e0-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="8a1e0-147">boolean</span><span class="sxs-lookup"><span data-stu-id="8a1e0-147">boolean</span></span> | <span data-ttu-id="8a1e0-148">Indica se il firmatario del certificato radice è Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a1e0-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="8a1e0-149">long</span><span class="sxs-lookup"><span data-stu-id="8a1e0-149">long</span></span> | <span data-ttu-id="8a1e0-150">Identificatore di evento basato su un contatore ripetuto.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8a1e0-151">Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="8a1e0-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="8a1e0-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8a1e0-152">Related topics</span></span>
- [<span data-ttu-id="8a1e0-153">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="8a1e0-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a1e0-154">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="8a1e0-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a1e0-155">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="8a1e0-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
