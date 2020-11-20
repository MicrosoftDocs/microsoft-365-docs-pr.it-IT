---
title: Novità di Microsoft Secure Score
description: In questo articolo vengono descritte le nuove modifiche apportate a Microsoft Secure score nel centro sicurezza Microsoft 365.
keywords: Microsoft Secure score, Secure score, Office 365 Secure score, Microsoft Security score, Microsoft 365 Security Center
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367113"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="27abd-104">Novità di Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="27abd-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="27abd-105">Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza, sono state apportate alcune modifiche.</span><span class="sxs-lookup"><span data-stu-id="27abd-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="27abd-106">Per informazioni sulle modifiche pianificate, vedere [What ' s Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="27abd-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="27abd-107">2020 novembre</span><span class="sxs-lookup"><span data-stu-id="27abd-107">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="27abd-108">Sono state aggiunte 3 azioni di miglioramento correlate ai servizi per Microsoft Defender per endpoint (in precedenza Microsoft Defender ATP):</span><span class="sxs-lookup"><span data-stu-id="27abd-108">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="27abd-109">Risolvere il percorso del servizio non quotato per i servizi Windows</span><span class="sxs-lookup"><span data-stu-id="27abd-109">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="27abd-110">Modificare il percorso eseguibile del servizio in una posizione protetta comune</span><span class="sxs-lookup"><span data-stu-id="27abd-110">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="27abd-111">Cambiare l'account del servizio per evitare la password memorizzata nella cache nel registro di sistema</span><span class="sxs-lookup"><span data-stu-id="27abd-111">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="27abd-112">Ottobre 2020</span><span class="sxs-lookup"><span data-stu-id="27abd-112">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="27abd-113">Rimuovere l'azione di miglioramento relativa a Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="27abd-113">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="27abd-114">Impostare Microsoft Defender SmartScreen app di Windows Store per il controllo del contenuto Web per l'avviso</span><span class="sxs-lookup"><span data-stu-id="27abd-114">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="27abd-115">Agosto 2020</span><span class="sxs-lookup"><span data-stu-id="27abd-115">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="27abd-116">Azione di miglioramento aggiornata per Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="27abd-116">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="27abd-117">Abilitazione del criterio per bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="27abd-117">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="27abd-118">Incompatibilità con il Punteggio identità sicuro e l'API del grafico</span><span class="sxs-lookup"><span data-stu-id="27abd-118">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="27abd-119">Nella versione recente di Microsoft Secure Score è stato rilasciato un modello di Punteggio migliorato.</span><span class="sxs-lookup"><span data-stu-id="27abd-119">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="27abd-120">Tali modifiche consentono una visualizzazione più flessibile e accurata della posizione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="27abd-120">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="27abd-121">Tuttavia, questi aggiornamenti sono stati resi temporaneamente incompatibili con il Punteggio di Microsoft Secure e l'API del grafico.</span><span class="sxs-lookup"><span data-stu-id="27abd-121">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="27abd-122">Nel tempo, il Punteggio di sicurezza dell'identità e l'API del grafico adotteranno il nuovo modello di punteggio.</span><span class="sxs-lookup"><span data-stu-id="27abd-122">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="27abd-123">Fino a quel momento, i clienti vedranno le differenze nei punteggi riportati da Microsoft Secure score, Identity Secure score e l'API del grafico.</span><span class="sxs-lookup"><span data-stu-id="27abd-123">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="27abd-124">Vi chiediamo scusa per qualsiasi inconveniente che questo comporta, e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.</span><span class="sxs-lookup"><span data-stu-id="27abd-124">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="27abd-125">Azioni di miglioramento aggiornate</span><span class="sxs-lookup"><span data-stu-id="27abd-125">Updated improvement actions</span></span>

- <span data-ttu-id="27abd-126">Aggiunta delle azioni di miglioramento di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="27abd-126">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="27abd-127">Aggiunta di Microsoft Defender per azioni di miglioramento dell'identità</span><span class="sxs-lookup"><span data-stu-id="27abd-127">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="27abd-128">Supporto di Microsoft Defender per la [minaccia](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) di endpoint & le indicazioni sulla sicurezza per la gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="27abd-128">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="27abd-129">Tutti i consigli di sicurezza rilasciati forniti da TVM sono ora disponibili</span><span class="sxs-lookup"><span data-stu-id="27abd-129">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="27abd-130">Interfaccia e funzionalità aggiornate</span><span class="sxs-lookup"><span data-stu-id="27abd-130">Updated interface and functionality</span></span>

* <span data-ttu-id="27abd-131">Tutte le nuove visualizzazioni metriche e tendenze per le discussioni su OICOL e Lead Level</span><span class="sxs-lookup"><span data-stu-id="27abd-131">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="27abd-132">Nuove modalità di monitoraggio e benchmark del Punteggio</span><span class="sxs-lookup"><span data-stu-id="27abd-132">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="27abd-133">Migliorare il monitoraggio e la comprensione delle regressioni dei punteggi</span><span class="sxs-lookup"><span data-stu-id="27abd-133">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="27abd-134">Filtrare, contrassegnare, ricercare e raggruppare le azioni di miglioramento</span><span class="sxs-lookup"><span data-stu-id="27abd-134">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="27abd-135">Gestire gli obiettivi futuri utilizzando le proiezioni dei punteggi e le azioni pianificate</span><span class="sxs-lookup"><span data-stu-id="27abd-135">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="27abd-136">E altro ancora!</span><span class="sxs-lookup"><span data-stu-id="27abd-136">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="27abd-137">Si vuole sapere da voi</span><span class="sxs-lookup"><span data-stu-id="27abd-137">We want to hear from you</span></span>

<span data-ttu-id="27abd-138">In caso di problemi, inviaci informazioni scrivendo nella community [sicurezza, Privacy & conformità](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="27abd-138">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="27abd-139">Si sta monitorando la community e viene fornita assistenza.</span><span class="sxs-lookup"><span data-stu-id="27abd-139">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="27abd-140">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="27abd-140">Related resources</span></span>

- [<span data-ttu-id="27abd-141">Valutazione del profilo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="27abd-141">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="27abd-142">Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi</span><span class="sxs-lookup"><span data-stu-id="27abd-142">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="27abd-143">Novità in arrivo</span><span class="sxs-lookup"><span data-stu-id="27abd-143">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
