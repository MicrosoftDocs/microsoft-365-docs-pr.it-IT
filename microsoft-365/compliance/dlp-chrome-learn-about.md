---
title: Informazioni sull'estensione per Conformità Microsoft
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: L'estensione per Conformità Microsoft estende il monitoraggio e il controllo delle attività sui file e sulle azioni di protezione nel browser Google Chrome
ms.openlocfilehash: b8d9be88f42cce736cdbf66a97f4363106fa5820
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730487"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="91026-103">Informazioni sull'estensione per Conformità Microsoft</span><span class="sxs-lookup"><span data-stu-id="91026-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="91026-104">[Prevenzione della perdita di dati degli endpoint (Endpoint DLP)](endpoint-dlp-learn-about.md) estende le funzionalità di monitoraggio e protezione delle attività della [Prevenzione della perdita di dati di Microsoft 365 (DPL)](dlp-learn-about-dlp.md) agli elementi sensibili presenti nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="91026-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="91026-105">Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="91026-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="91026-106">Dopo l'installazione dell'estensione per la conformità Microsoft in un dispositivo Windows 10, le organizzazioni possono monitorare quando un utente prova ad accedere o caricare un elemento sensibile in un servizio cloud tramite Google Chrome e applicare azioni di protezione tramite DLP.</span><span class="sxs-lookup"><span data-stu-id="91026-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="91026-107">Attività che è possibile monitorare e su cui è possibile intervenire</span><span class="sxs-lookup"><span data-stu-id="91026-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="91026-108">L'estensione per la conformità Microsoft consente di controllare e gestire i tipi di attività seguenti che gli utenti possono eseguire su elementi sensibili nei dispositivi che eseguono Windows 10.</span><span class="sxs-lookup"><span data-stu-id="91026-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="91026-109">attività</span><span class="sxs-lookup"><span data-stu-id="91026-109">activity</span></span> |<span data-ttu-id="91026-110">descrizione</span><span class="sxs-lookup"><span data-stu-id="91026-110">description</span></span>  | <span data-ttu-id="91026-111">azioni dei criteri supportate</span><span class="sxs-lookup"><span data-stu-id="91026-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="91026-112">file copiato nel cloud</span><span class="sxs-lookup"><span data-stu-id="91026-112">file copied to cloud</span></span>  | <span data-ttu-id="91026-113">Rileva quando un utente tenta di caricare un elemento sensibile in un dominio di servizio con restrizioni tramite il browser Chrome</span><span class="sxs-lookup"><span data-stu-id="91026-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="91026-114">audit, blocco</span><span class="sxs-lookup"><span data-stu-id="91026-114">audit, block</span></span>|
|<span data-ttu-id="91026-115">file stampato</span><span class="sxs-lookup"><span data-stu-id="91026-115">file printed</span></span>  |<span data-ttu-id="91026-116">Rileva quando un utente cerca di stampare un elemento sensibile aperto nel browser Chrome in una stampante locale o di rete</span><span class="sxs-lookup"><span data-stu-id="91026-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="91026-117">audit, blocco con override, blocco</span><span class="sxs-lookup"><span data-stu-id="91026-117">audit, block with override, block</span></span>|
|<span data-ttu-id="91026-118">file copiato negli Appunti</span><span class="sxs-lookup"><span data-stu-id="91026-118">file copied to clipboard</span></span> |<span data-ttu-id="91026-119">Rileva quando un utente tenta di copiare le informazioni da un elemento sensibile visualizzato nel browser Chrome per incollarle in un'altra applicazione, processo o elemento.</span><span class="sxs-lookup"><span data-stu-id="91026-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="91026-120">audit, blocco con override, blocco</span><span class="sxs-lookup"><span data-stu-id="91026-120">audit, block with override, block</span></span>|
|<span data-ttu-id="91026-121">file copiato su archivio rimovibile</span><span class="sxs-lookup"><span data-stu-id="91026-121">file copied to removable storage</span></span>    | <span data-ttu-id="91026-122">Rileva quando un utente prova a copiare elementi o informazioni sensibili da un elemento sensibile aperto nel browser Chrome in un supporto rimovibile o un dispositivo USB</span><span class="sxs-lookup"><span data-stu-id="91026-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="91026-123">audit, blocco con override, blocco</span><span class="sxs-lookup"><span data-stu-id="91026-123">audit, block with override, block</span></span>|
|<span data-ttu-id="91026-124">file copiato in una condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="91026-124">file copied to network share</span></span>  |<span data-ttu-id="91026-125">Rileva quando un utente prova a copiare elementi o informazioni sensibili da un elemento sensibile aperto nel browser Chrome in una condivisione di rete o un'unità di rete mappata.</span><span class="sxs-lookup"><span data-stu-id="91026-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="91026-126">audit, blocco con override, blocco</span><span class="sxs-lookup"><span data-stu-id="91026-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="91026-127">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="91026-127">Deployment process</span></span>
1. [<span data-ttu-id="91026-128">Introduzione alla prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="91026-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="91026-129">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="91026-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="91026-130">Installare l'estensione nei dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="91026-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="91026-131">[Creare o modificare criteri DLP](create-test-tune-dlp-policy.md) che limitano il caricamento nel servizio cloud o l'accesso da azioni del browser non consentite e l'applicazione ai dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="91026-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="91026-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="91026-132">Next steps</span></span>

<span data-ttu-id="91026-133">Per le procedure e gli scenari di distribuzione completi, vedere [Introduzione all'estensione per la conformità Microsoft](dlp-chrome-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="91026-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="91026-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91026-134">See also</span></span>

- [<span data-ttu-id="91026-135">Introduzione all'estensione per la conformità Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="91026-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="91026-136">Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91026-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="91026-137">Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="91026-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="91026-138">Uso della prevenzione della perdita di dati degli endpoint Microsoft</span><span class="sxs-lookup"><span data-stu-id="91026-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="91026-139">Informazioni sulla prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="91026-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="91026-140">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="91026-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="91026-141">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="91026-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="91026-142">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="91026-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="91026-143">Gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="91026-143">Insider Risk management</span></span>](insider-risk-management.md)
