---
title: Requisiti per le app di Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 01c580cd671a84ef68c18b114e133f046a3e5b3b
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "42328068"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="0fd03-103">Requisiti per le app di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0fd03-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="0fd03-104">Per garantire le prestazioni, l'affidabilità e la funzionalità dei dispositivi Microsoft Managed Desktop, le app di una linea del cliente non devono influire sul serio sull'esperienza dell'utente finale o modificare la posizione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0fd03-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="0fd03-105">Di conseguenza, le applicazioni line-of-business che si desidera distribuire ai dispositivi Microsoft Managed Desktop devono soddisfare i requisiti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0fd03-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="0fd03-106">Condizione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0fd03-106">Application condition</span></span>

<span data-ttu-id="0fd03-107">È importante che le applicazioni non influiscano negativamente sull'ambiente Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0fd03-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="0fd03-108">Di seguito sono indicati i requisiti che un'applicazione deve soddisfare per la distribuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0fd03-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="0fd03-109">Per qualsiasi applicazione o driver specificata, Microsoft può rinunciare a qualsiasi requisito fornito nel presente documento.</span><span class="sxs-lookup"><span data-stu-id="0fd03-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="0fd03-110">Microsoft può decidere di rimuovere qualsiasi applicazione o driver che influisce negativamente sulle prestazioni e l'affidabilità dei dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0fd03-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="0fd03-111">App gestite centralmente</span><span class="sxs-lookup"><span data-stu-id="0fd03-111">Centrally managed apps</span></span>

<span data-ttu-id="0fd03-112">Tutte le applicazioni e i driver installati nei dispositivi gestiti Microsoft devono essere distribuiti tramite Microsoft Intune, Microsoft Store o Microsoft Store for business. Se disponibile, i driver verranno distribuiti anche tramite il servizio Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0fd03-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="0fd03-113">Classi app non consentite</span><span class="sxs-lookup"><span data-stu-id="0fd03-113">Prohibited app classes</span></span>

<span data-ttu-id="0fd03-114">Alcuni tipi di applicazioni non sono consentiti sui dispositivi Microsoft Managed Desktop:</span><span class="sxs-lookup"><span data-stu-id="0fd03-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="0fd03-115">software di terze parti antivirus, di sicurezza o di controllo</span><span class="sxs-lookup"><span data-stu-id="0fd03-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="0fd03-116">Versioni di Microsoft Office precedenti a Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="0fd03-116">Versions of Microsoft Office prior to Office 365 ProPlus</span></span>
- <span data-ttu-id="0fd03-117">Applicazioni che installino o bundle altri software di terze parti</span><span class="sxs-lookup"><span data-stu-id="0fd03-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="0fd03-118">Comportamenti delle app con limitazioni</span><span class="sxs-lookup"><span data-stu-id="0fd03-118">Restricted app behaviors</span></span>

<span data-ttu-id="0fd03-119">Alcuni comportamenti delle app possono influire negativamente sull'esperienza dell'utente o possono presentare un rischio per la sicurezza per i dispositivi desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="0fd03-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="0fd03-120">Le app con i comportamenti seguenti non sono autorizzate a essere eseguite nell'ambiente Microsoft Managed Desktop senza una specifica di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0fd03-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="0fd03-121">Esperienza utente:</span><span class="sxs-lookup"><span data-stu-id="0fd03-121">User Experience:</span></span>
- <span data-ttu-id="0fd03-122">Installare servizi in background</span><span class="sxs-lookup"><span data-stu-id="0fd03-122">Install background services</span></span>
- <span data-ttu-id="0fd03-123">Aggiungersi al percorso di avvio di Windows</span><span class="sxs-lookup"><span data-stu-id="0fd03-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="0fd03-124">Le applicazioni dipendono dai driver</span><span class="sxs-lookup"><span data-stu-id="0fd03-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="0fd03-125">Web browser di terze parti</span><span class="sxs-lookup"><span data-stu-id="0fd03-125">3rd party web browsers</span></span>

<span data-ttu-id="0fd03-126">Sicurezza:</span><span class="sxs-lookup"><span data-stu-id="0fd03-126">Security:</span></span>
- <span data-ttu-id="0fd03-127">Elevare i privilegi dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="0fd03-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="0fd03-128">Agire come App Store o avere un gestore di estensioni incorporato</span><span class="sxs-lookup"><span data-stu-id="0fd03-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="0fd03-129">Sono note vulnerabilità relative alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="0fd03-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="0fd03-130">Crittografare o limitare l'accesso ai dati degli utenti finali</span><span class="sxs-lookup"><span data-stu-id="0fd03-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="0fd03-131">È senza segno o viene firmato utilizzando un certificato che non viene eseguito fino a una radice attendibile</span><span class="sxs-lookup"><span data-stu-id="0fd03-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="0fd03-132">Distribuzione del driver</span><span class="sxs-lookup"><span data-stu-id="0fd03-132">Driver deployment</span></span>

<span data-ttu-id="0fd03-133">Microsoft Managed Desktop supporta solo i driver di dispositivo disponibili tramite Windows Update o la posta in arrivo installata con il dispositivo gestito Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0fd03-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="0fd03-134">Se un'applicazione richiede un driver specifico per l'esecuzione, è considerata un'applicazione limitata e richiede un'eccezione prima di essere distribuita in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0fd03-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exception before being deployed to Microsoft Managed Desktop.</span></span> 

