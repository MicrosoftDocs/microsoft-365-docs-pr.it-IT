---
title: Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD
description: Viene descritto in che modo Microsoft trasferisce la data in avanti per interrompere il supporto per TLS 1,1 e 1,0 negli ambienti GCC High e DoD in Office 365 e prepararsi per l'utilizzo di TLS 1,2.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024826"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="5c415-103">Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="5c415-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c415-104">Il mondo è nel bel mezzo di una pandemia e in Microsoft siamo consapevoli dell'impatto che questa pandemia ha sui nostri clienti e sui nostri partner.</span><span class="sxs-lookup"><span data-stu-id="5c415-104">The world is in the middle of a pandemic, and we at Microsoft are aware of the impact on our customers and partners.</span></span> <span data-ttu-id="5c415-105">Per alleggerire la pressione sui nostri clienti commerciali, abbiamo temporaneamente interrotto qualsiasi deprecazione di TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="5c415-105">To lighten the burden on our commercial customers, we have temporarily halted any deprecation enforcement of TLS 1.0 and 1.1.</span></span> <span data-ttu-id="5c415-106">Dopo che la crisi attuale si sarà stabilizzata, invieremo un aggiornamento sulla nuova tempistica.</span><span class="sxs-lookup"><span data-stu-id="5c415-106">An update will be sent on a revised timeline after the current crisis stabilizes.</span></span> <span data-ttu-id="5c415-107">(Questo articolo è stato modificato per includere tale modifica.)</span><span class="sxs-lookup"><span data-stu-id="5c415-107">(This article is revised to reflect the change.)</span></span>

## <a name="summary"></a><span data-ttu-id="5c415-108">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5c415-108">Summary</span></span>

<span data-ttu-id="5c415-109">Per essere conformi agli standard di conformità più recenti per il programma di gestione delle autorizzazioni e dei rischi federali (FedRAMP), è possibile procedere con le versioni 1,1 e 1,0 di Microsoft Office 365 per gli ambienti GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="5c415-109">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are moving to deprecate Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="5c415-110">Questa modifica è stata precedentemente annunciata tramite il supporto tecnico Microsoft [per la preparazione all'uso obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="5c415-110">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="5c415-111">Si capisce che la sicurezza dei dati è importante e si è impegnati per la trasparenza in merito alle modifiche che potrebbero influire sull'utilizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="5c415-111">We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="5c415-112">Anche se l' [implementazione di Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) non ha vulnerabilità di sicurezza note, è necessario rimanere impegnati negli standard di conformità di FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="5c415-112">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="5c415-113">Di conseguenza, gli ambienti TLS 1,1 e 1,0 in Office 365 sono obsoleti nell'ambiente GCC High e DoD, a partire dal 15 gennaio 2020.</span><span class="sxs-lookup"><span data-stu-id="5c415-113">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="5c415-114">Per informazioni su come rimuovere le dipendenze TLS 1,1 e 1,0, vedere il white paper seguente:</span><span class="sxs-lookup"><span data-stu-id="5c415-114">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="5c415-115">Risoluzione del problema di TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="5c415-115">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="5c415-116">Durante la preparazione di questa modifica per TLS 1,1 e 1,0, è consigliabile utilizzare TLS versione 1,2.</span><span class="sxs-lookup"><span data-stu-id="5c415-116">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="5c415-117">Per ulteriori informazioni, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="5c415-117">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="5c415-118">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="5c415-118">More information</span></span>

<span data-ttu-id="5c415-119">A partire da gennaio 15, 2020, Office 365 nell'ambiente GCC High e DoD diventeranno obsoleti TLS 1,1 e 1,0.</span><span class="sxs-lookup"><span data-stu-id="5c415-119">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="5c415-120">Entro il 15 gennaio 2020, tutte le combinazioni di server client e server browser devono utilizzare TLS versione 1,2 (o versione successiva) per assicurarsi che tutte le connessioni possano essere eseguite senza problemi per i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c415-120">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="5c415-121">Questo potrebbe richiedere aggiornamenti a determinate combinazioni di server client e server browser.</span><span class="sxs-lookup"><span data-stu-id="5c415-121">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="5c415-122">Se non si esegue l'aggiornamento a TLS versione 1,2 (o versione successiva) entro il 15 gennaio 2020, si verificheranno problemi quando si tenta di connettersi a Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c415-122">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="5c415-123">Sarà inoltre necessario eseguire l'aggiornamento a TLS 1,2 (o versione successiva) come parte della risoluzione.</span><span class="sxs-lookup"><span data-stu-id="5c415-123">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="5c415-124">Sappiamo che i client seguenti non possono utilizzare TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="5c415-124">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="5c415-125">Android 4.3 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="5c415-125">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="5c415-126">Firefox versione 5.0 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="5c415-126">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="5c415-127">Internet Explorer 8 – 10 in Windows 7 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="5c415-127">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="5c415-128">Internet Explorer 10 su Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="5c415-128">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="5c415-129">Safari 6.0.4/OS X 10.8.4 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="5c415-129">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="5c415-130">Si consiglia di aggiornare i client per assicurarsi di mantenere l'accesso ininterrotto a Office 365 GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="5c415-130">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="5c415-131">Anche se l'analisi corrente delle connessioni ai servizi Microsoft online dimostra che la maggior parte dei servizi e degli endpoint Visualizza pochissimo utilizzo di TLS 1,1 e 1,0, viene fornito un avviso di questa modifica, in modo da poter aggiornare i client o i server coinvolti come necessario prima che il supporto per TLS 1,1 e 1,0 termini.</span><span class="sxs-lookup"><span data-stu-id="5c415-131">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="5c415-132">Se si utilizza un'infrastruttura locale per gli scenari ibridi o Active Directory Federation Services (AD FS), verificare che l'infrastruttura sia in grado di supportare le connessioni in ingresso e in uscita che utilizzano TLS 1,2 (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="5c415-132">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="5c415-133">Oltre alle interruzioni che è possibile riscontrare se si utilizzano i client elencati che non possono utilizzare TLS 1,2, la rimozione di TLS 1,1 e 1,0 impedirà l'utilizzo del prodotto Microsoft seguente:</span><span class="sxs-lookup"><span data-stu-id="5c415-133">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="5c415-134">Lync Phone</span><span class="sxs-lookup"><span data-stu-id="5c415-134">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="5c415-135">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5c415-135">References</span></span>

<span data-ttu-id="5c415-136">L'articolo di supporto seguente descrive le linee guida e i riferimenti per assicurarsi che i client utilizzino TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="5c415-136">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="5c415-137">Preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365</span><span class="sxs-lookup"><span data-stu-id="5c415-137">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
