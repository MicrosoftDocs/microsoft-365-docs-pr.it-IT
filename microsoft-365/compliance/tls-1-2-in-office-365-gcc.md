---
title: Disabilitazione di TLS 1.0 e 1.1 in Office 365 GCC High e DoD
description: Illustra in che modo Microsoft disabilita il supporto per TLS 1.1 e 1.0 negli ambienti GCC High e DoD in Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166441"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="e33f8-103">Disabilitazione di TLS 1.0 e 1.1 in Office 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="e33f8-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="e33f8-104">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e33f8-104">Summary</span></span>

<span data-ttu-id="e33f8-105">Per rispettare gli standard di conformità più recenti per il Federal Risk and Authorization Management Program (FedRAMP), stiamo disabilitando Transport Layer Security (TLS) versioni 1.1 e 1.0 in Microsoft 365 per ambienti GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="e33f8-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="e33f8-106">Questa modifica è stata annunciata in precedenza tramite il supporto tecnico Microsoft nella preparazione per l'uso obbligatorio di [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="e33f8-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="e33f8-107">La sicurezza dei dati è importante e ci impegniamo a trasparenza sulle modifiche che potrebbero influire sull'uso del servizio.</span><span class="sxs-lookup"><span data-stu-id="e33f8-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="e33f8-108">Anche se [l'implementazione di Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) non presenta vulnerabilità di sicurezza note, microsoft si impegna a mantenere gli standard di conformità FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="e33f8-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="e33f8-109">Pertanto, TLS 1.1 e 1.0 sono stati disabilitati in Office 365 in ambienti GCC High e DoD il 15 gennaio 2020.</span><span class="sxs-lookup"><span data-stu-id="e33f8-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="e33f8-110">Per informazioni su come rimuovere le dipendenze tls 1.1 e 1.0, vedere il white paper seguente:</span><span class="sxs-lookup"><span data-stu-id="e33f8-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="e33f8-111">Risoluzione del problema di TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="e33f8-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="e33f8-112">È invece necessario utilizzare TLS versione 1.2.</span><span class="sxs-lookup"><span data-stu-id="e33f8-112">You must use TLS version 1.2 instead.</span></span> <span data-ttu-id="e33f8-113">Per ulteriori informazioni, vedere [Preparazione per l'uso obbligatorio di TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="e33f8-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="e33f8-114">Per SharePoint e OneDrive, è necessario aggiornare e configurare .NET per supportare TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="e33f8-114">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="e33f8-115">Per informazioni, vedere [Come abilitare TLS 1.2 nei client.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="e33f8-115">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="e33f8-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="e33f8-116">More information</span></span>

<span data-ttu-id="e33f8-117">A partire dal 15 gennaio 2020, Office 365 negli ambienti GCC High e DoD deprecerà TLS 1.1 e 1.0.</span><span class="sxs-lookup"><span data-stu-id="e33f8-117">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="e33f8-118">Entro il 15 gennaio 2020, tutte le combinazioni di server client e server browser devono utilizzare TLS versione 1.2 (o versione successiva) per assicurarsi che tutte le connessioni possano essere effettuate senza problemi con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e33f8-118">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="e33f8-119">Questa operazione potrebbe richiedere aggiornamenti a determinate combinazioni di server client e server browser.</span><span class="sxs-lookup"><span data-stu-id="e33f8-119">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="e33f8-120">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span><span class="sxs-lookup"><span data-stu-id="e33f8-120">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="e33f8-121">Inoltre, sarà necessario eseguire l'aggiornamento a TLS 1.2 (o versione successiva) come parte della risoluzione.</span><span class="sxs-lookup"><span data-stu-id="e33f8-121">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="e33f8-122">I client seguenti non possono utilizzare TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="e33f8-122">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="e33f8-123">Android 4.3 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="e33f8-123">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="e33f8-124">Firefox versione 5.0 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="e33f8-124">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="e33f8-125">Internet Explorer 8-10 in Windows 7 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="e33f8-125">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="e33f8-126">Internet Explorer 10 in Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="e33f8-126">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="e33f8-127">Safari 6.0.4/OS X 10.8.4 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="e33f8-127">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="e33f8-128">È consigliabile aggiornare i client per assicurarsi di mantenere l'accesso senza interruzioni a Office 365 GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="e33f8-128">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="e33f8-129">Anche se l'analisi corrente delle connessioni ai servizi online Microsoft mostra che la maggior parte dei servizi e degli endpoint vede un utilizzo molto scarso di TLS 1.1 e 1.0, microsoft fornisce notifica di questa modifica in modo da poter aggiornare i client o i server interessati in base alle esigenze prima che il supporto per TLS 1.1 e 1.0 termini.</span><span class="sxs-lookup"><span data-stu-id="e33f8-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="e33f8-130">Se si utilizza un'infrastruttura locale per scenari ibridi o Active Directory Federation Services (AD FS), assicurarsi che l'infrastruttura sia in grado di supportare connessioni in ingresso e in uscita che utilizzano TLS 1.2 (o una versione successiva).</span><span class="sxs-lookup"><span data-stu-id="e33f8-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="e33f8-131">Oltre alle interruzioni che potrebbero verificarsi se si utilizzano i client elencati che non possono utilizzare TLS 1.2, la rimozione di TLS 1.1 e 1.0 impedisce di utilizzare il prodotto Microsoft seguente:</span><span class="sxs-lookup"><span data-stu-id="e33f8-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="e33f8-132">Telefono Lync</span><span class="sxs-lookup"><span data-stu-id="e33f8-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="e33f8-133">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="e33f8-133">References</span></span>

<span data-ttu-id="e33f8-134">L'articolo di supporto seguente descrive le linee guida e i riferimenti per assicurarsi che i client utilizzino TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="e33f8-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="e33f8-135">Preparazione per l'uso obbligatorio di TLS 1.2 in Office 365</span><span class="sxs-lookup"><span data-stu-id="e33f8-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
