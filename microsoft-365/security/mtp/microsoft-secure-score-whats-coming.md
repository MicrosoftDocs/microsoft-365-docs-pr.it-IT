---
title: Cosa viene a Microsoft Secure Score
description: In questo articolo vengono descritte le nuove modifiche apportate a Microsoft Secure score nel centro sicurezza Microsoft 365.
keywords: Microsoft Secure score, Secure score, Office 365 Secure score, Microsoft Security score, Microsoft 365 Security Center, azioni di miglioramento
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779249"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="fbfc4-104">Cosa viene a Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="fbfc4-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fbfc4-105">Sono state apportate alcune modifiche nel prossimo futuro per rendere [Microsoft Secure Score](microsoft-secure-score.md) un migliore rappresentante della propria posizione di sicurezza e migliorare l'usabilità.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="fbfc4-106">Il Punteggio e il punteggio massimo possibile possono variare.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="fbfc4-107">Modifiche proposte</span><span class="sxs-lookup"><span data-stu-id="fbfc4-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="fbfc4-108">2020 novembre</span><span class="sxs-lookup"><span data-stu-id="fbfc4-108">November 2020</span></span>

<span data-ttu-id="fbfc4-109">La rimozione della possibilità di creare i ticket di ServiceNow tramite il Punteggio sicuro è in grado di **condividere > ServiceNow** .</span><span class="sxs-lookup"><span data-stu-id="fbfc4-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="fbfc4-110">Il periodo di anteprima per il connettore ServiceNow termina.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="fbfc4-111">Questa funzionalità non sarà più disponibile entro la fine di 2020.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="fbfc4-112">La ringrazio per i commenti e il supporto continuo, mentre si determinano i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="fbfc4-113">Aggiunta di 18 azioni di miglioramento relative a Microsoft Defender per endpoint (in precedenza Microsoft Defender ATP):</span><span class="sxs-lookup"><span data-stu-id="fbfc4-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="fbfc4-114">Suggerimenti correlati alla riduzione della superficie di attacco (ASR):</span><span class="sxs-lookup"><span data-stu-id="fbfc4-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="fbfc4-115">Bloccare i contenuti eseguibili dal client di posta elettronica e webmail</span><span class="sxs-lookup"><span data-stu-id="fbfc4-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="fbfc4-116">Blocca tutte le applicazioni di Office dalla creazione dei processi figlio</span><span class="sxs-lookup"><span data-stu-id="fbfc4-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="fbfc4-117">Bloccare le applicazioni di Office dalla creazione di contenuto eseguibile</span><span class="sxs-lookup"><span data-stu-id="fbfc4-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="fbfc4-118">Blocca le applicazioni di Office dall'inserimento di codice in altri processi</span><span class="sxs-lookup"><span data-stu-id="fbfc4-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="fbfc4-119">Blocca JavaScript o VBScript dall'avvio del contenuto eseguibile scaricato</span><span class="sxs-lookup"><span data-stu-id="fbfc4-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="fbfc4-120">Bloccare l'esecuzione di script potenzialmente offuscati</span><span class="sxs-lookup"><span data-stu-id="fbfc4-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="fbfc4-121">Bloccare le chiamate API Win32 dalle macro di Office</span><span class="sxs-lookup"><span data-stu-id="fbfc4-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="fbfc4-122">Bloccare l'esecuzione di file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile</span><span class="sxs-lookup"><span data-stu-id="fbfc4-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="fbfc4-123">Utilizzare Advanced Protection against ransomware</span><span class="sxs-lookup"><span data-stu-id="fbfc4-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="fbfc4-124">Bloccare la sottrazione di credenziali dal sottosistema di autorità di sicurezza locale di Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="fbfc4-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="fbfc4-125">Bloccare le creazioni dei processi originati da comandi di PSExec e WMI</span><span class="sxs-lookup"><span data-stu-id="fbfc4-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="fbfc4-126">Blocca processi non attendibili e non firmati che vengono eseguiti da USB</span><span class="sxs-lookup"><span data-stu-id="fbfc4-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="fbfc4-127">Bloccare l'applicazione di comunicazione di Office dalla creazione dei processi figlio</span><span class="sxs-lookup"><span data-stu-id="fbfc4-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="fbfc4-128">Impedire a Adobe Reader di creare processi figlio</span><span class="sxs-lookup"><span data-stu-id="fbfc4-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="fbfc4-129">Blocca la persistenza tramite la sottoscrizione di eventi WMI</span><span class="sxs-lookup"><span data-stu-id="fbfc4-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="fbfc4-130">Suggerimenti relativi ai servizi:</span><span class="sxs-lookup"><span data-stu-id="fbfc4-130">Services related recommendations:</span></span>
- <span data-ttu-id="fbfc4-131">Risolvere il percorso del servizio non quotato per i servizi Windows</span><span class="sxs-lookup"><span data-stu-id="fbfc4-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="fbfc4-132">Modificare il percorso eseguibile del servizio in una posizione protetta comune</span><span class="sxs-lookup"><span data-stu-id="fbfc4-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="fbfc4-133">Cambiare l'account del servizio per evitare la password memorizzata nella cache nel registro di sistema</span><span class="sxs-lookup"><span data-stu-id="fbfc4-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="fbfc4-134">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="fbfc4-134">Related resources</span></span>

- [<span data-ttu-id="fbfc4-135">Panoramica del Punteggio Microsoft Secure</span><span class="sxs-lookup"><span data-stu-id="fbfc4-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="fbfc4-136">Valutazione del profilo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="fbfc4-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="fbfc4-137">Monitorare la cronologia dei punteggi di Microsoft Secure e raggiungere gli obiettivi</span><span class="sxs-lookup"><span data-stu-id="fbfc4-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="fbfc4-138">Novità</span><span class="sxs-lookup"><span data-stu-id="fbfc4-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
