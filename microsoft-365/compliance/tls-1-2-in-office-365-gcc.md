---
title: Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD
description: Viene descritto in che modo Microsoft trasferisce la data in avanti per interrompere il supporto per TLS 1,1 e 1,0 negli ambienti GCC High e DoD in Office 365 e prepararsi per l'utilizzo di TLS 1,2.
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158881"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="53cd2-103">Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="53cd2-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="53cd2-104">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="53cd2-104">Summary</span></span>

<span data-ttu-id="53cd2-105">Per essere conformi agli standard di conformità più recenti per il programma di gestione delle autorizzazioni e dei rischi federali (FedRAMP), sono deprecati i modelli TLS (Transport Layer Security) 1,1 e 1,0 in Microsoft Office 365 per ambienti GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="53cd2-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are deprecating Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="53cd2-106">Questa modifica è stata precedentemente annunciata tramite il supporto tecnico Microsoft [per la preparazione all'uso obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="53cd2-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="53cd2-107">La sicurezza dei dati è importante e siamo impegnati nella trasparenza sulle modifiche che potrebbero influire sull'utilizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="53cd2-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="53cd2-108">Anche se l' [implementazione di Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) non ha vulnerabilità di sicurezza note, è necessario rimanere impegnati negli standard di conformità di FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="53cd2-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="53cd2-109">Di conseguenza, gli ambienti TLS 1,1 e 1,0 in Office 365 sono obsoleti nell'ambiente GCC High e DoD, a partire dal 15 gennaio 2020.</span><span class="sxs-lookup"><span data-stu-id="53cd2-109">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="53cd2-110">Per informazioni su come rimuovere le dipendenze TLS 1,1 e 1,0, vedere il white paper seguente:</span><span class="sxs-lookup"><span data-stu-id="53cd2-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="53cd2-111">Risoluzione del problema di TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="53cd2-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="53cd2-112">Durante la preparazione di questa modifica per TLS 1,1 e 1,0, è consigliabile utilizzare TLS versione 1,2.</span><span class="sxs-lookup"><span data-stu-id="53cd2-112">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="53cd2-113">Per ulteriori informazioni, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="53cd2-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="53cd2-114">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="53cd2-114">More information</span></span>

<span data-ttu-id="53cd2-115">A partire da gennaio 15, 2020, Office 365 nell'ambiente GCC High e DoD diventeranno obsoleti TLS 1,1 e 1,0.</span><span class="sxs-lookup"><span data-stu-id="53cd2-115">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="53cd2-116">Entro il 15 gennaio 2020, tutte le combinazioni di server client e server browser devono utilizzare TLS versione 1,2 (o versione successiva) per assicurarsi che tutte le connessioni possano essere eseguite senza problemi per i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="53cd2-116">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="53cd2-117">Questo potrebbe richiedere aggiornamenti a determinate combinazioni di server client e server browser.</span><span class="sxs-lookup"><span data-stu-id="53cd2-117">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="53cd2-118">Se non si esegue l'aggiornamento a TLS versione 1,2 (o versione successiva) entro il 15 gennaio 2020, si verificheranno problemi quando si tenta di connettersi a Office 365.</span><span class="sxs-lookup"><span data-stu-id="53cd2-118">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="53cd2-119">Sarà inoltre necessario eseguire l'aggiornamento a TLS 1,2 (o versione successiva) come parte della risoluzione.</span><span class="sxs-lookup"><span data-stu-id="53cd2-119">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="53cd2-120">Sappiamo che i client seguenti non possono utilizzare TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="53cd2-120">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="53cd2-121">Android 4.3 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="53cd2-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="53cd2-122">Firefox versione 5.0 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="53cd2-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="53cd2-123">Internet Explorer 8 – 10 in Windows 7 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="53cd2-123">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="53cd2-124">Internet Explorer 10 su Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="53cd2-124">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="53cd2-125">Safari 6.0.4/OS X 10.8.4 e versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="53cd2-125">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="53cd2-126">Si consiglia di aggiornare i client per assicurarsi di mantenere l'accesso ininterrotto a Office 365 GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="53cd2-126">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="53cd2-127">Anche se l'analisi corrente delle connessioni ai servizi Microsoft online dimostra che la maggior parte dei servizi e degli endpoint Visualizza pochissimo utilizzo di TLS 1,1 e 1,0, viene fornito un avviso di questa modifica, in modo da poter aggiornare i client o i server coinvolti come necessario prima che il supporto per TLS 1,1 e 1,0 termini.</span><span class="sxs-lookup"><span data-stu-id="53cd2-127">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="53cd2-128">Se si utilizza un'infrastruttura locale per gli scenari ibridi o Active Directory Federation Services (AD FS), verificare che l'infrastruttura sia in grado di supportare le connessioni in ingresso e in uscita che utilizzano TLS 1,2 (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="53cd2-128">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="53cd2-129">Oltre alle interruzioni che è possibile riscontrare se si utilizzano i client elencati che non possono utilizzare TLS 1,2, la rimozione di TLS 1,1 e 1,0 impedirà l'utilizzo del prodotto Microsoft seguente:</span><span class="sxs-lookup"><span data-stu-id="53cd2-129">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="53cd2-130">Lync Phone</span><span class="sxs-lookup"><span data-stu-id="53cd2-130">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="53cd2-131">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="53cd2-131">References</span></span>

<span data-ttu-id="53cd2-132">L'articolo di supporto seguente descrive le linee guida e i riferimenti per assicurarsi che i client utilizzino TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="53cd2-132">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="53cd2-133">Preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365</span><span class="sxs-lookup"><span data-stu-id="53cd2-133">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
