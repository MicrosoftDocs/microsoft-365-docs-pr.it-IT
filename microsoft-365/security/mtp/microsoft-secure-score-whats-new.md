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
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373996"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="2f04d-104">Novità di Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="2f04d-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2f04d-105">Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza, sono state apportate alcune modifiche.</span><span class="sxs-lookup"><span data-stu-id="2f04d-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="2f04d-106">Per informazioni sulle modifiche pianificate, vedere [What ' s Coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="2f04d-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

<span data-ttu-id="2f04d-107">Microsoft Secure Score può essere trovato https://security.microsoft.com/securescore nel [Centro sicurezza Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="2f04d-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="2f04d-108">2020 novembre</span><span class="sxs-lookup"><span data-stu-id="2f04d-108">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="2f04d-109">Sono state aggiunte 3 azioni di miglioramento correlate ai servizi per Microsoft Defender per endpoint (in precedenza Microsoft Defender ATP):</span><span class="sxs-lookup"><span data-stu-id="2f04d-109">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="2f04d-110">Risolvere il percorso del servizio non quotato per i servizi Windows</span><span class="sxs-lookup"><span data-stu-id="2f04d-110">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="2f04d-111">Modificare il percorso eseguibile del servizio in una posizione protetta comune</span><span class="sxs-lookup"><span data-stu-id="2f04d-111">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="2f04d-112">Cambiare l'account del servizio per evitare la password memorizzata nella cache nel registro di sistema</span><span class="sxs-lookup"><span data-stu-id="2f04d-112">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="2f04d-113">Ottobre 2020</span><span class="sxs-lookup"><span data-stu-id="2f04d-113">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="2f04d-114">Rimuovere l'azione di miglioramento relativa a Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2f04d-114">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="2f04d-115">Impostare Microsoft Defender SmartScreen app di Windows Store per il controllo del contenuto Web per l'avviso</span><span class="sxs-lookup"><span data-stu-id="2f04d-115">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="2f04d-116">Agosto 2020</span><span class="sxs-lookup"><span data-stu-id="2f04d-116">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="2f04d-117">Azione di miglioramento aggiornata per Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2f04d-117">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="2f04d-118">Abilitazione del criterio per bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="2f04d-118">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="2f04d-119">Incompatibilità con il Punteggio identità sicuro e l'API del grafico</span><span class="sxs-lookup"><span data-stu-id="2f04d-119">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="2f04d-120">Nella versione recente di Microsoft Secure Score è stato rilasciato un modello di Punteggio migliorato.</span><span class="sxs-lookup"><span data-stu-id="2f04d-120">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="2f04d-121">Tali modifiche consentono una visualizzazione più flessibile e accurata della posizione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2f04d-121">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="2f04d-122">Tuttavia, questi aggiornamenti sono stati resi temporaneamente incompatibili con il Punteggio di Microsoft Secure e l'API del grafico.</span><span class="sxs-lookup"><span data-stu-id="2f04d-122">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="2f04d-123">Nel tempo, il Punteggio di sicurezza dell'identità e l'API del grafico adotteranno il nuovo modello di punteggio.</span><span class="sxs-lookup"><span data-stu-id="2f04d-123">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="2f04d-124">Fino a quel momento, i clienti vedranno le differenze nei punteggi riportati da Microsoft Secure score, Identity Secure score e l'API del grafico.</span><span class="sxs-lookup"><span data-stu-id="2f04d-124">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="2f04d-125">Vi chiediamo scusa per qualsiasi inconveniente che questo comporta, e stiamo lavorando per garantire che queste esperienze siano più compatibili in futuro.</span><span class="sxs-lookup"><span data-stu-id="2f04d-125">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="2f04d-126">Azioni di miglioramento aggiornate</span><span class="sxs-lookup"><span data-stu-id="2f04d-126">Updated improvement actions</span></span>

- <span data-ttu-id="2f04d-127">Aggiunta delle azioni di miglioramento di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2f04d-127">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="2f04d-128">Aggiunta di Microsoft Defender per azioni di miglioramento dell'identità</span><span class="sxs-lookup"><span data-stu-id="2f04d-128">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="2f04d-129">Supporto di Microsoft Defender per la [minaccia](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) di endpoint & le indicazioni sulla sicurezza per la gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="2f04d-129">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="2f04d-130">Tutti i consigli di sicurezza rilasciati forniti da TVM sono ora disponibili</span><span class="sxs-lookup"><span data-stu-id="2f04d-130">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="2f04d-131">Interfaccia e funzionalità aggiornate</span><span class="sxs-lookup"><span data-stu-id="2f04d-131">Updated interface and functionality</span></span>

* <span data-ttu-id="2f04d-132">Tutte le nuove visualizzazioni metriche e tendenze per le discussioni su OICOL e Lead Level</span><span class="sxs-lookup"><span data-stu-id="2f04d-132">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="2f04d-133">Nuove modalità di monitoraggio e benchmark del Punteggio</span><span class="sxs-lookup"><span data-stu-id="2f04d-133">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="2f04d-134">Migliorare il monitoraggio e la comprensione delle regressioni dei punteggi</span><span class="sxs-lookup"><span data-stu-id="2f04d-134">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="2f04d-135">Filtrare, contrassegnare, ricercare e raggruppare le azioni di miglioramento</span><span class="sxs-lookup"><span data-stu-id="2f04d-135">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="2f04d-136">Gestire gli obiettivi futuri utilizzando le proiezioni dei punteggi e le azioni pianificate</span><span class="sxs-lookup"><span data-stu-id="2f04d-136">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="2f04d-137">E altro ancora!</span><span class="sxs-lookup"><span data-stu-id="2f04d-137">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="2f04d-138">Si vuole sapere da voi</span><span class="sxs-lookup"><span data-stu-id="2f04d-138">We want to hear from you</span></span>

<span data-ttu-id="2f04d-139">In caso di problemi, inviaci informazioni scrivendo nella community [sicurezza, Privacy & conformità](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="2f04d-139">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="2f04d-140">Si sta monitorando la community e viene fornita assistenza.</span><span class="sxs-lookup"><span data-stu-id="2f04d-140">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="2f04d-141">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="2f04d-141">Related resources</span></span>

- [<span data-ttu-id="2f04d-142">Valutazione del profilo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f04d-142">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="2f04d-143">Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi</span><span class="sxs-lookup"><span data-stu-id="2f04d-143">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="2f04d-144">Novità in arrivo</span><span class="sxs-lookup"><span data-stu-id="2f04d-144">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
