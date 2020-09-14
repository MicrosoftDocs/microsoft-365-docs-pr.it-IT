---
title: RGPD per server di Office
description: Informazioni su come gestire i requisiti del GDPR nei server locali di Office.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ee42a12f65ad5eff0a33ef2b61d328ebdc7af3e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547332"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="eefb0-103">RGDP per server locali di Office</span><span class="sxs-lookup"><span data-stu-id="eefb0-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="eefb0-p101">L'RGDP presenta i requisiti delle organizzazioni per proteggere i dati personali e rispondere in modo appropriato alle richieste del soggetto dei dati. Questa serie di articoli fornisce i metodi consigliati per i carichi di lavoro locali:</span><span class="sxs-lookup"><span data-stu-id="eefb0-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

- [<span data-ttu-id="eefb0-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

- [<span data-ttu-id="eefb0-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

- [<span data-ttu-id="eefb0-108">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

- [<span data-ttu-id="eefb0-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-109">Project Server</span></span>](gdpr-for-project-server.md)

- [<span data-ttu-id="eefb0-110">Server Office Web Apps e Office Online Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

- [<span data-ttu-id="eefb0-111">Condivisioni file locali</span><span class="sxs-lookup"><span data-stu-id="eefb0-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="eefb0-112">Per ulteriori informazioni sull'RGDP e su come Microsoft può essere di aiuto, vedere [Centro protezione Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span><span class="sxs-lookup"><span data-stu-id="eefb0-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span></span>

<span data-ttu-id="eefb0-p102">Prima di iniziare una qualsiasi operazione con i dati locali, consultare il team di conformità e il team legale per cercare informazioni sugli schemi di classificazione esistenti e sugli approcci all'utilizzo dei dati personali. Microsoft fornisce suggerimenti per lo sviluppo e per l'estensione degli schemi di classificazione nel Microsoft GDPR Data Discovery Toolkit in [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). Il toolkit descrive anche metodi per trasferire dati locali nel cloud, dove è possibile utilizzare funzionalità di gestione dati più complesse, se necessario. Gli articoli di questa sezione contengono suggerimenti per i dati che devono rimanere in locale.</span><span class="sxs-lookup"><span data-stu-id="eefb0-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="eefb0-p103">Di seguito sono elencate funzionalità consigliate per ognuno di questi carichi di lavoro per individuare, classificare, proteggere e monitorare i dati personali. Vedere gli articoli in questa sezione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="eefb0-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![Diagramma che descrive le funzionalità per individuare, classificare, proteggere e monitorare i dati personali nei carichi di lavoro](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="eefb0-120">Descrizione dell'illustrazione</span><span class="sxs-lookup"><span data-stu-id="eefb0-120">Illustration description</span></span>

<span data-ttu-id="eefb0-121">Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="eefb0-121">For accessibility, the following table provides the same examples in the illustration.</span></span>

****

|<span data-ttu-id="eefb0-122">Azione</span><span class="sxs-lookup"><span data-stu-id="eefb0-122">Action</span></span>|<span data-ttu-id="eefb0-123">Condivisioni file di Windows Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-123">Windows Server file shares</span></span>|<span data-ttu-id="eefb0-124">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-124">SharePoint Server</span></span>|<span data-ttu-id="eefb0-125">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-125">Exchange Server</span></span>|<span data-ttu-id="eefb0-126">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="eefb0-126">Skype for Business</span></span>|<span data-ttu-id="eefb0-127">Project Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-127">Project Server</span></span>|
|---|---|---|---|---|---|
|<span data-ttu-id="eefb0-128">Individuazione</span><span class="sxs-lookup"><span data-stu-id="eefb0-128">Discover</span></span>|<span data-ttu-id="eefb0-129">Scanner di Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eefb0-129">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="eefb0-130">Centro ricerche o eDiscovery (dopo la classificazione dei dati)</span><span class="sxs-lookup"><span data-stu-id="eefb0-130">Search Center or eDiscovery (after data is classified)</span></span> <br/><br/> <span data-ttu-id="eefb0-131">Scanner di Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eefb0-131">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="eefb0-132">Portale eDiscovery di Exchange</span><span class="sxs-lookup"><span data-stu-id="eefb0-132">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="eefb0-133">Portale eDiscovery di Exchange</span><span class="sxs-lookup"><span data-stu-id="eefb0-133">Exchange eDiscovery portal</span></span>|<span data-ttu-id="eefb0-134">Script SQL per l'individuazione e l'esportazione</span><span class="sxs-lookup"><span data-stu-id="eefb0-134">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="eefb0-135">Classificare</span><span class="sxs-lookup"><span data-stu-id="eefb0-135">Classify</span></span>|<span data-ttu-id="eefb0-136">Scanner di Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eefb0-136">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="eefb0-137">Tipi di informazioni riservate di Office 365</span><span class="sxs-lookup"><span data-stu-id="eefb0-137">Office 365 sensitive information types</span></span>|<span data-ttu-id="eefb0-138">Scanner di Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eefb0-138">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="eefb0-139">Tipi di informazioni riservate di Office 365</span><span class="sxs-lookup"><span data-stu-id="eefb0-139">Office 365 sensitive information types</span></span>|<span data-ttu-id="eefb0-140">Tag e criteri di conservazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="eefb0-140">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="eefb0-141">Tag e criteri di conservazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="eefb0-141">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="eefb0-142">Proteggere</span><span class="sxs-lookup"><span data-stu-id="eefb0-142">Protect</span></span>||<span data-ttu-id="eefb0-143">Regole di prevenzione della perdita dei dati di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-143">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="eefb0-144">Autorizzazioni, protezione IRM per librerie</span><span class="sxs-lookup"><span data-stu-id="eefb0-144">Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="eefb0-145">Regole di prevenzione della perdita dei dati di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-145">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="eefb0-146">Integrazione IRM con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="eefb0-146">IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="eefb0-147">Monitorare</span><span class="sxs-lookup"><span data-stu-id="eefb0-147">Monitor</span></span>|<span data-ttu-id="eefb0-148">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="eefb0-148">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="eefb0-149">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="eefb0-149">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="eefb0-150">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="eefb0-150">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="eefb0-151">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="eefb0-151">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="eefb0-152">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="eefb0-152">Integrate logs with SIEM tools</span></span>|
|

<span data-ttu-id="eefb0-153"><sup>\*</sup>Si noti che la protezione crittografa il file.</span><span class="sxs-lookup"><span data-stu-id="eefb0-153"><sup>\*</sup> Note that protection encrypts the file.</span></span> <span data-ttu-id="eefb0-154">Di conseguenza, SharePoint Server non riesce a individuare tipi di informazioni riservate nei file protetti.</span><span class="sxs-lookup"><span data-stu-id="eefb0-154">Consequently, SharePoint Server can't find the sensitive information types in protected files.</span></span>
