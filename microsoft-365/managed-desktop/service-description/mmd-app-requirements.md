---
title: Requisiti di app Desktop gestiti Microsoft
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868263"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="1d010-103">Requisiti di app Desktop gestiti Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d010-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="1d010-104">Le applicazioni line-of-business che si desidera distribuire ai dispositivi Desktop gestiti Microsoft devono soddisfare i requisiti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1d010-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="1d010-105">Condizione di applicazione</span><span class="sxs-lookup"><span data-stu-id="1d010-105">Application condition</span></span>

<span data-ttu-id="1d010-p101">È importante che le applicazioni non negativamente dell'ambiente Desktop gestito Microsoft. Di seguito sono i requisiti di un'applicazione deve essere soddisfatti per Microsoft per la distribuzione. Per un'applicazione specificata o driver, Microsoft può rinunciare qualsiasi requisito contenuta nel presente documento. Microsoft può decidere di rimuovere un'applicazione o driver che impatta negativamente sulle prestazioni e affidabilità dei dispositivi Desktop gestiti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1d010-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="1d010-110">Deployable utilizzando le tecnologie Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d010-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="1d010-p102">Desktop gestiti Microsoft utilizza Intune, Microsoft Store e Microsoft Store for Business per distribuire le applicazioni. Di conseguenza, è necessario essere un pacchetto applicazioni in modo possono essere distribuiti con la versione vigore di tali servizi.</span><span class="sxs-lookup"><span data-stu-id="1d010-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="1d010-113">Classi proibito app</span><span class="sxs-lookup"><span data-stu-id="1d010-113">Prohibited app classes</span></span>

<span data-ttu-id="1d010-114">Alcuni tipi di applicazioni non sono consentite per i dispositivi Desktop gestiti Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1d010-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="1d010-115">antivirus parti 3, sicurezza o software di controllo</span><span class="sxs-lookup"><span data-stu-id="1d010-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="1d010-116">Versioni di Microsoft Office prima di Office 365 Professional Plus</span><span class="sxs-lookup"><span data-stu-id="1d010-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="1d010-117">Applicazioni di installare o aggregano altri software di terze parti 3</span><span class="sxs-lookup"><span data-stu-id="1d010-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="1d010-118">Comportamenti di app con restrizioni</span><span class="sxs-lookup"><span data-stu-id="1d010-118">Restricted app behaviors</span></span>

<span data-ttu-id="1d010-p103">Alcuni comportamenti applicazione possono essere essere genere pregiudizievole per l'esperienza utente o costituiscano un rischio di protezione per i dispositivi Desktop gestiti Microsoft. Le applicazioni non devono presentare comportamenti o le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d010-p103">Certain application behaviors can be either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 
- <span data-ttu-id="1d010-121">Installare i servizi in background o generano processi in background di lunga durata</span><span class="sxs-lookup"><span data-stu-id="1d010-121">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="1d010-122">Aggiungersi al percorso di avvio di Windows</span><span class="sxs-lookup"><span data-stu-id="1d010-122">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="1d010-123">Chiamata non documentate Windows o le API di Office o prendere dipendenze sulle strutture di dati interne Windows o di Office</span><span class="sxs-lookup"><span data-stu-id="1d010-123">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="1d010-124">Agire come archivio dell'app o hanno estensione incorporata manager</span><span class="sxs-lookup"><span data-stu-id="1d010-124">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="1d010-125">Aumentare i privilegi dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="1d010-125">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="1d010-126">Sono noti vulnerabilità di protezione</span><span class="sxs-lookup"><span data-stu-id="1d010-126">Have known security vulnerabilities</span></span>
- <span data-ttu-id="1d010-127">Effettuato l'accesso utilizzando un certificato di riporto non viene applicato a un'autorità attendibile</span><span class="sxs-lookup"><span data-stu-id="1d010-127">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="1d010-128">Crittografare o limitare l'accesso ai dati dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="1d010-128">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="1d010-129">Modificare il codice del sistema operativo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="1d010-129">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="1d010-130">Distribuzione di driver</span><span class="sxs-lookup"><span data-stu-id="1d010-130">Driver deployment</span></span>

<span data-ttu-id="1d010-131">A meno che un driver è disponibile in Windows Update o separatamente è firmato da Windows Hardware Quality Lab (WHQL), Microsoft è necessario approvare un driver prima che Microsoft verrà distribuito il driver di dispositivi Desktop gestiti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1d010-131">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>