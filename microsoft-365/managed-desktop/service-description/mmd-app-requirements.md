---
title: Requisiti per le app di Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278336"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="5d4e9-103">Requisiti per le app di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5d4e9-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="5d4e9-104">Le applicazioni line-of-business che si desidera distribuire ai dispositivi Microsoft Managed Desktop devono soddisfare i requisiti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="5d4e9-105">Condizione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5d4e9-105">Application condition</span></span>

<span data-ttu-id="5d4e9-106">È importante che le applicazioni non influiscano negativamente sull'ambiente Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="5d4e9-107">Di seguito sono indicati i requisiti che un'applicazione deve soddisfare affinché Microsoft la implementi.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="5d4e9-108">Per qualsiasi applicazione o driver specificata, Microsoft può rinunciare a qualsiasi requisito fornito nel presente documento.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="5d4e9-109">Microsoft può decidere di rimuovere qualsiasi applicazione o driver che influisce negativamente sulle prestazioni e l'affidabilità dei dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="5d4e9-110">Deployable using Microsoft Technologies</span><span class="sxs-lookup"><span data-stu-id="5d4e9-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="5d4e9-111">Microsoft Managed Desktop utilizza Intune, Microsoft Store e Microsoft Store for business per la distribuzione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="5d4e9-112">Di conseguenza, le applicazioni devono essere impacchettate in modo da poter essere distribuite dalla versione corrente di tali servizi.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="5d4e9-113">Classi app non consentite</span><span class="sxs-lookup"><span data-stu-id="5d4e9-113">Prohibited app classes</span></span>

<span data-ttu-id="5d4e9-114">Alcuni tipi di applicazioni non sono consentiti sui dispositivi Microsoft Managed Desktop:</span><span class="sxs-lookup"><span data-stu-id="5d4e9-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="5d4e9-115">software di terze parti antivirus, di sicurezza o di controllo</span><span class="sxs-lookup"><span data-stu-id="5d4e9-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="5d4e9-116">Web browser di terze parti</span><span class="sxs-lookup"><span data-stu-id="5d4e9-116">3rd party web browsers</span></span>
- <span data-ttu-id="5d4e9-117">Versioni di Microsoft Office precedenti a Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="5d4e9-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="5d4e9-118">Applicazioni che installino o bundle altri software di terze parti</span><span class="sxs-lookup"><span data-stu-id="5d4e9-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="5d4e9-119">Comportamenti delle app con limitazioni</span><span class="sxs-lookup"><span data-stu-id="5d4e9-119">Restricted app behaviors</span></span>

<span data-ttu-id="5d4e9-120">Alcuni comportamenti dell'applicazione possono essere pregiudizievoli per l'esperienza degli utenti o per presentare un rischio per la sicurezza per i dispositivi desktop Microsoft gestiti.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="5d4e9-121">Le applicazioni non devono presentare i comportamenti o le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d4e9-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="5d4e9-122">Esperienza utente:</span><span class="sxs-lookup"><span data-stu-id="5d4e9-122">User Experience:</span></span>
- <span data-ttu-id="5d4e9-123">Installare servizi in background o generare processi in background di lunga durata</span><span class="sxs-lookup"><span data-stu-id="5d4e9-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="5d4e9-124">Aggiungersi al percorso di avvio di Windows</span><span class="sxs-lookup"><span data-stu-id="5d4e9-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="5d4e9-125">Sicurezza:</span><span class="sxs-lookup"><span data-stu-id="5d4e9-125">Security:</span></span>
- <span data-ttu-id="5d4e9-126">Chiamare le finestre non documentate o le API di Office o le dipendenze nelle strutture di dati interne di Windows o di Office</span><span class="sxs-lookup"><span data-stu-id="5d4e9-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="5d4e9-127">Agire come App Store o avere un gestore di estensioni incorporato</span><span class="sxs-lookup"><span data-stu-id="5d4e9-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="5d4e9-128">Elevare i privilegi dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="5d4e9-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="5d4e9-129">Sono note vulnerabilità relative alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="5d4e9-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="5d4e9-130">Firmato utilizzando un certificato che non viene eseguito su una radice attendibile</span><span class="sxs-lookup"><span data-stu-id="5d4e9-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="5d4e9-131">Crittografare o limitare l'accesso ai dati degli utenti finali</span><span class="sxs-lookup"><span data-stu-id="5d4e9-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="5d4e9-132">Modificare il codice del sistema operativo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5d4e9-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="5d4e9-133">Distribuzione del driver</span><span class="sxs-lookup"><span data-stu-id="5d4e9-133">Driver deployment</span></span>

<span data-ttu-id="5d4e9-134">Se un driver non è disponibile in Windows Update o è firmato separatamente da Windows Hardware Quality Lab (WHQL), Microsoft deve approvare un driver prima che Microsoft implementi il driver per i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5d4e9-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
