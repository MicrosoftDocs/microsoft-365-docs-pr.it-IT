---
title: Suggerimenti per la sicurezza gestione di minacce e vulnerabilità
description: Ottenere consigli di sicurezza utilizzabili in base alle minacce, alle probabilità di violazione e al valore, in gestione di minacce e vulnerabilità.
keywords: gestione di minacce e vulnerabilità, raccomandazione sulla sicurezza di Microsoft Defender for Endpoint tvm, raccomandazione sulla sicurezza informatica, raccomandazione di sicurezza utilizzabile
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933734"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="efd6f-104">Suggerimenti per la sicurezza - gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="efd6f-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="efd6f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="efd6f-105">**Applies to:**</span></span>

- [<span data-ttu-id="efd6f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="efd6f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="efd6f-107">Minaccia e gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="efd6f-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="efd6f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efd6f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="efd6f-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="efd6f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="efd6f-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="efd6f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="efd6f-111">I punti deboli della cybersecurity identificati nell'organizzazione sono mappati a consigli sulla sicurezza utilizzabili e classificati in ordine di priorità in base al loro impatto.</span><span class="sxs-lookup"><span data-stu-id="efd6f-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="efd6f-112">I consigli con priorità consentono di ridurre il tempo necessario per ridurre o correggere le vulnerabilità e migliorare la conformità.</span><span class="sxs-lookup"><span data-stu-id="efd6f-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="efd6f-113">Ogni suggerimento per la sicurezza include passaggi correttivi utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="efd6f-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="efd6f-114">Per facilitare la gestione delle attività, è inoltre possibile inviare il suggerimento Microsoft Intune e Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="efd6f-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="efd6f-115">Quando cambia il panorama delle minacce, il consiglio cambia anche quando raccoglie continuamente informazioni dall'ambiente.</span><span class="sxs-lookup"><span data-stu-id="efd6f-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="efd6f-116">Per ricevere messaggi di posta elettronica sui nuovi eventi di vulnerabilità, vedere Configurare le notifiche di posta elettronica relative alla vulnerabilità [in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="efd6f-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="efd6f-117">Come funziona</span><span class="sxs-lookup"><span data-stu-id="efd6f-117">How it works</span></span>

<span data-ttu-id="efd6f-118">Ogni dispositivo dell'organizzazione viene ottenuto in base a tre fattori importanti per aiutare i clienti a concentrarsi sulle cose giuste al momento giusto.</span><span class="sxs-lookup"><span data-stu-id="efd6f-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="efd6f-119">**Minaccia:** caratteristiche delle vulnerabilità e degli exploit nei dispositivi dell'organizzazione e cronologia delle violazioni.</span><span class="sxs-lookup"><span data-stu-id="efd6f-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="efd6f-120">In base a questi fattori, i suggerimenti per la sicurezza mostrano i collegamenti corrispondenti agli avvisi attivi, alle campagne di minacce in corso e ai report analitici relativi alle minacce corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="efd6f-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="efd6f-121">**Probabilità di violazione** - La posizione di sicurezza e la resilienza dell'organizzazione contro le minacce</span><span class="sxs-lookup"><span data-stu-id="efd6f-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="efd6f-122">**Valore aziendale** - Asset dell'organizzazione, processi critici e proprietà intellettuali</span><span class="sxs-lookup"><span data-stu-id="efd6f-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="efd6f-123">Passare alla pagina Suggerimenti per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="efd6f-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="efd6f-124">Accedere alla pagina Suggerimenti per la sicurezza in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="efd6f-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="efd6f-125">Minaccia e gestione delle vulnerabilità di spostamento nella [Microsoft Defender Security Center](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="efd6f-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="efd6f-126">Principali suggerimenti per la sicurezza [nel dashboard gestione di minacce e vulnerabilità sicurezza](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="efd6f-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="efd6f-127">Visualizzare i suggerimenti sulla sicurezza correlati nelle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="efd6f-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="efd6f-128">Pagina Software</span><span class="sxs-lookup"><span data-stu-id="efd6f-128">Software page</span></span>
- <span data-ttu-id="efd6f-129">Pagina Dispositivo</span><span class="sxs-lookup"><span data-stu-id="efd6f-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="efd6f-130">Menu di spostamento</span><span class="sxs-lookup"><span data-stu-id="efd6f-130">Navigation menu</span></span>

<span data-ttu-id="efd6f-131">Vai al menu di gestione di minacce e vulnerabilità navigazione e seleziona **Suggerimenti per la sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="efd6f-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="efd6f-132">La pagina contiene un elenco di consigli sulla sicurezza per le minacce e le vulnerabilità presenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="efd6f-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="efd6f-133">Suggerimenti per la sicurezza principali nel dashboard gestione di minacce e vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="efd6f-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="efd6f-134">In un determinato giorno come amministratore della sicurezza, puoi dare un'occhiata [](tvm-exposure-score.md) al [dashboard di gestione di minacce e vulnerabilità](tvm-dashboard-insights.md) per visualizzare il punteggio di esposizione affiancato al punteggio microsoft secure per [i dispositivi](tvm-microsoft-secure-score-devices.md).</span><span class="sxs-lookup"><span data-stu-id="efd6f-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="efd6f-135">L'obiettivo è ridurre **l'esposizione** dell'organizzazione  dalle vulnerabilità e aumentare la sicurezza dei dispositivi dell'organizzazione per essere più resiliente contro gli attacchi di minacce alla cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="efd6f-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="efd6f-136">L'elenco dei principali suggerimenti per la sicurezza consente di raggiungere questo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="efd6f-136">The top security recommendations list can help you achieve that goal.</span></span>

![Esempio di scheda Consigli per la sicurezza principali, con quattro consigli per la sicurezza.](images/top-security-recommendations350.png)

<span data-ttu-id="efd6f-138">I principali suggerimenti per la sicurezza elencano le opportunità di miglioramento con priorità in base ai fattori importanti menzionati nella sezione precedente: minaccia, probabilità di violazione e valore.</span><span class="sxs-lookup"><span data-stu-id="efd6f-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="efd6f-139">La selezione di un suggerimento consente di accedere alla pagina degli elementi consigliati per la sicurezza con ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="efd6f-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="efd6f-140">Panoramica degli elementi consigliati per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="efd6f-140">Security recommendations overview</span></span>

<span data-ttu-id="efd6f-141">Visualizza i suggerimenti, il numero di punti deboli trovati, i componenti correlati, le informazioni dettagliate sulle minacce, il numero di dispositivi esposti, lo stato, il tipo di correzione, le attività di correzione, l'impatto sul punteggio di esposizione e microsoft Secure Score per i dispositivi e i tag associati.</span><span class="sxs-lookup"><span data-stu-id="efd6f-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="efd6f-142">Il colore del grafico **Dei dispositivi esposti** cambia quando cambia la tendenza.</span><span class="sxs-lookup"><span data-stu-id="efd6f-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="efd6f-143">Se il numero di dispositivi esposti è in aumento, il colore viene modificato in rosso.</span><span class="sxs-lookup"><span data-stu-id="efd6f-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="efd6f-144">In caso di diminuzione del numero di dispositivi esposti, il colore del grafico verrà modificato in verde.</span><span class="sxs-lookup"><span data-stu-id="efd6f-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="efd6f-145">Minacce e gestione delle vulnerabilità mostra i dispositivi che erano in uso fino a **30 giorni** fa.</span><span class="sxs-lookup"><span data-stu-id="efd6f-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="efd6f-146">Questo è diverso dal resto di Microsoft Defender per Endpoint, dove se un dispositivo non è in uso da più di 7 giorni ha lo stato "Inattivo".</span><span class="sxs-lookup"><span data-stu-id="efd6f-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![Esempio di pagina di destinazione per suggerimenti sulla sicurezza.](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="efd6f-148">Icone</span><span class="sxs-lookup"><span data-stu-id="efd6f-148">Icons</span></span>

<span data-ttu-id="efd6f-149">Anche le icone utili richiamano rapidamente l'attenzione su:</span><span class="sxs-lookup"><span data-stu-id="efd6f-149">Useful icons also quickly call your attention to:</span></span>
- ![freccia che colpisce una destinazione](images/tvm_alert_icon.png) <span data-ttu-id="efd6f-151">possibili avvisi attivi</span><span class="sxs-lookup"><span data-stu-id="efd6f-151">possible active alerts</span></span>
- ![bug rosso](images/tvm_bug_icon.png) <span data-ttu-id="efd6f-153">exploit pubblici associati</span><span class="sxs-lookup"><span data-stu-id="efd6f-153">associated public exploits</span></span>
- ![lampadina](images/tvm_insight_icon.png) <span data-ttu-id="efd6f-155">informazioni dettagliate sulle raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="efd6f-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="efd6f-156">Esplorare le opzioni di suggerimento per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="efd6f-156">Explore security recommendation options</span></span>

<span data-ttu-id="efd6f-157">Selezionare il suggerimento per la sicurezza che si desidera analizzare o elaborare.</span><span class="sxs-lookup"><span data-stu-id="efd6f-157">Select the security recommendation that you want to investigate or process.</span></span>

![Esempio di pagina a comparsa di suggerimenti per la sicurezza.](images/secrec-flyouteolsw.png)

<span data-ttu-id="efd6f-159">Dal riquadro a comparsa è possibile scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="efd6f-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="efd6f-160">**Pagina Apri software:** aprire la pagina del software per ottenere più contesto sul software e su come viene distribuito.</span><span class="sxs-lookup"><span data-stu-id="efd6f-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="efd6f-161">Le informazioni possono includere il contesto delle minacce, i suggerimenti associati, i punti deboli rilevati, il numero di dispositivi esposti, le vulnerabilità individuate, i nomi e i dettagli dei dispositivi con il software installato e la distribuzione delle versioni.</span><span class="sxs-lookup"><span data-stu-id="efd6f-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="efd6f-162">[**Opzioni di correzione-**](tvm-remediation.md) Inviare una richiesta di correzione per aprire un ticket in Microsoft Intune che l'amministratore IT può prelevare e inviare.</span><span class="sxs-lookup"><span data-stu-id="efd6f-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="efd6f-163">Tenere traccia dell'attività di correzione nella pagina Correzione.</span><span class="sxs-lookup"><span data-stu-id="efd6f-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="efd6f-164">[**Opzioni di eccezione:**](tvm-exception.md) invia un'eccezione, fornisci giustificazione e imposta la durata dell'eccezione se non riesci ancora a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="efd6f-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="efd6f-165">Quando viene apportata una modifica software in un dispositivo, in genere sono necessari 2 ore prima che i dati si riflettano nel portale di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="efd6f-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="efd6f-166">A volte, tuttavia, può essere necessario più tempo.</span><span class="sxs-lookup"><span data-stu-id="efd6f-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="efd6f-167">Le modifiche alla configurazione possono richiedere da 4 a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="efd6f-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="efd6f-168">Analizzare le modifiche nell'esposizione o nell'impatto del dispositivo</span><span class="sxs-lookup"><span data-stu-id="efd6f-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="efd6f-169">Se c'è un notevole aumento del numero di dispositivi esposti o un forte aumento dell'impatto sul punteggio di esposizione dell'organizzazione e microsoft Secure Score per i dispositivi, vale la pena analizzare il suggerimento per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="efd6f-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="efd6f-170">Selezionare la pagina dei suggerimenti **e del software aperto**</span><span class="sxs-lookup"><span data-stu-id="efd6f-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="efd6f-171">Seleziona la **scheda Sequenza temporale** eventi per visualizzare tutti gli eventi di impatto correlati a tale software, ad esempio nuove vulnerabilità o nuovi exploit pubblici.</span><span class="sxs-lookup"><span data-stu-id="efd6f-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="efd6f-172">Altre informazioni sulla sequenza temporale degli eventi</span><span class="sxs-lookup"><span data-stu-id="efd6f-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="efd6f-173">Decidere come affrontare l'aumento o l'esposizione dell'organizzazione, ad esempio l'invio di una richiesta di correzione</span><span class="sxs-lookup"><span data-stu-id="efd6f-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="efd6f-174">Richiesta di correzione</span><span class="sxs-lookup"><span data-stu-id="efd6f-174">Request remediation</span></span>

<span data-ttu-id="efd6f-175">La gestione di minacce e vulnerabilità di correzione consente di colmare il distacco tra gli amministratori IT e la sicurezza attraverso il flusso di lavoro delle richieste di correzione.</span><span class="sxs-lookup"><span data-stu-id="efd6f-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="efd6f-176">Gli amministratori della sicurezza come te possono richiedere all'amministratore IT di correggere una vulnerabilità dalla pagina **Dei** suggerimenti per la sicurezza a Intune.</span><span class="sxs-lookup"><span data-stu-id="efd6f-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="efd6f-177">Ulteriori informazioni sulle opzioni di correzione</span><span class="sxs-lookup"><span data-stu-id="efd6f-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="efd6f-178">Come richiedere la correzione</span><span class="sxs-lookup"><span data-stu-id="efd6f-178">How to request remediation</span></span>

<span data-ttu-id="efd6f-179">Selezionare un suggerimento per la sicurezza per cui si desidera richiedere la correzione e quindi selezionare **Opzioni di correzione.**</span><span class="sxs-lookup"><span data-stu-id="efd6f-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="efd6f-180">Compila il modulo e seleziona **Invia richiesta.**</span><span class="sxs-lookup"><span data-stu-id="efd6f-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="efd6f-181">Passare alla [**pagina Correzione**](tvm-remediation.md) per visualizzare lo stato della richiesta di correzione.</span><span class="sxs-lookup"><span data-stu-id="efd6f-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="efd6f-182">Ulteriori informazioni su come richiedere la correzione</span><span class="sxs-lookup"><span data-stu-id="efd6f-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="efd6f-183">File per l'eccezione</span><span class="sxs-lookup"><span data-stu-id="efd6f-183">File for exception</span></span>

<span data-ttu-id="efd6f-184">In alternativa a una richiesta di correzione quando al momento un suggerimento non è rilevante, è possibile creare eccezioni per i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="efd6f-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="efd6f-185">Ulteriori informazioni sulle eccezioni</span><span class="sxs-lookup"><span data-stu-id="efd6f-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="efd6f-186">Solo gli utenti con autorizzazioni di "gestione delle eccezioni" possono aggiungere un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="efd6f-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="efd6f-187">[Ulteriori informazioni sui ruoli RBAC.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="efd6f-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="efd6f-188">Quando viene creata un'eccezione per un suggerimento, il suggerimento non è più attivo.</span><span class="sxs-lookup"><span data-stu-id="efd6f-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="efd6f-189">Lo stato del suggerimento verrà modificato in **Eccezione completa** o **Eccezione parziale** (per gruppo di dispositivi).</span><span class="sxs-lookup"><span data-stu-id="efd6f-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="efd6f-190">Come creare un'eccezione</span><span class="sxs-lookup"><span data-stu-id="efd6f-190">How to create an exception</span></span>

<span data-ttu-id="efd6f-191">Selezionare un suggerimento per la sicurezza per cui si desidera creare un'eccezione e quindi selezionare **Opzioni eccezione.**</span><span class="sxs-lookup"><span data-stu-id="efd6f-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![Visualizzazione del punto in cui si trova il pulsante per le "opzioni di eccezione" in un riquadro a comparsa dei suggerimenti per la sicurezza.](images/tvm-exception-options.png)

<span data-ttu-id="efd6f-193">Compilare il modulo e inviarlo.</span><span class="sxs-lookup"><span data-stu-id="efd6f-193">Fill out the form and submit.</span></span> <span data-ttu-id="efd6f-194">Per visualizzare tutte le eccezioni (correnti [](tvm-remediation.md) e passate), passare alla pagina Correzione nel menu  Gestione vulnerabilità di **Threat &** e selezionare la scheda Eccezioni. Ulteriori informazioni su come creare un'eccezione [](tvm-exception.md#create-an-exception)</span><span class="sxs-lookup"><span data-stu-id="efd6f-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="efd6f-195">Imprecisione dei report</span><span class="sxs-lookup"><span data-stu-id="efd6f-195">Report inaccuracy</span></span>

<span data-ttu-id="efd6f-196">È possibile segnalare un falso positivo quando vengono visualizzate informazioni di suggerimento sulla sicurezza vaghe, imprecise, incomplete o già corretti.</span><span class="sxs-lookup"><span data-stu-id="efd6f-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="efd6f-197">Aprire il suggerimento Sicurezza.</span><span class="sxs-lookup"><span data-stu-id="efd6f-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="efd6f-198">Selezionare i tre punti accanto al suggerimento di sicurezza che si desidera segnalare, quindi selezionare **Segnala imprecisione.**</span><span class="sxs-lookup"><span data-stu-id="efd6f-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![Visualizzazione della posizione del pulsante "Segnala imprecisione" in un riquadro a comparsa per i suggerimenti per la sicurezza.](images/report-inaccuracy500.png)

3. <span data-ttu-id="efd6f-200">Nel riquadro a comparsa selezionare la categoria di imprecisione dal menu a discesa, immettere l'indirizzo di posta elettronica e i dettagli relativi all'imprecisione.</span><span class="sxs-lookup"><span data-stu-id="efd6f-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="efd6f-201">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="efd6f-201">Select **Submit**.</span></span> <span data-ttu-id="efd6f-202">Il feedback viene inviato immediatamente agli gestione di minacce e vulnerabilità esperti.</span><span class="sxs-lookup"><span data-stu-id="efd6f-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="efd6f-203">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="efd6f-203">Related articles</span></span>

- [<span data-ttu-id="efd6f-204">Panoramica delle minacce gestione delle vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="efd6f-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="efd6f-205">Dashboard</span><span class="sxs-lookup"><span data-stu-id="efd6f-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="efd6f-206">Punteggio di esposizione.</span><span class="sxs-lookup"><span data-stu-id="efd6f-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="efd6f-207">Punteggio di sicurezza Microsoft per dispositivi</span><span class="sxs-lookup"><span data-stu-id="efd6f-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="efd6f-208">Correggere le vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="efd6f-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="efd6f-209">Creare e visualizzare le eccezioni per i suggerimenti sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="efd6f-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="efd6f-210">Sequenza temporale eventi</span><span class="sxs-lookup"><span data-stu-id="efd6f-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
