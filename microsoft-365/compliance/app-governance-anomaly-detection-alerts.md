---
title: Analizzare gli avvisi di rilevamento delle anomalie
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Analizzare gli avvisi di rilevamento delle anomalie.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420472"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="79784-103">Analizzare gli avvisi di rilevamento delle anomalie</span><span class="sxs-lookup"><span data-stu-id="79784-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="79784-104">La governance delle app Microsoft fornisce rilevamenti di sicurezza e avvisi per attività dannose.</span><span class="sxs-lookup"><span data-stu-id="79784-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="79784-105">Lo scopo di questa guida è fornire informazioni generali e pratiche su ciascun avviso, in modo da facilitare le attività di indagine e correzione.</span><span class="sxs-lookup"><span data-stu-id="79784-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="79784-106">In questa guida sono incluse informazioni generali sulle condizioni per l'attivazione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="79784-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="79784-107">Poiché i rilevamenti di anomalie non sono prevedibili per natura, vengono attivati solo quando c'è un comportamento che devia dalla norma.</span><span class="sxs-lookup"><span data-stu-id="79784-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="79784-108">Infine, alcuni avvisi potrebbero essere in anteprima, quindi è consigliabile esaminare regolarmente la documentazione ufficiale per informazioni aggiornate sullo stato degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="79784-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="79784-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="79784-109">MITRE ATT&CK</span></span>

<span data-ttu-id="79784-110">Per semplificare la mappatura della relazione tra gli avvisi di governance delle app Microsoft e la matrice familiare MITRE ATT&CK, gli avvisi sono stati classificati in base alla tattica MITRE ATT&CK corrispondente.</span><span class="sxs-lookup"><span data-stu-id="79784-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="79784-111">Questo riferimento aggiuntivo semplifica la comprensione della tecnica di attacchi sospetti in uso, quando viene attivato l'avviso di sicurezza e governance delle applicazioni Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79784-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="79784-112">Questa guida fornisce informazioni sull'analisi e sulla correzione degli avvisi di governance delle app Microsoft nelle categorie seguenti.</span><span class="sxs-lookup"><span data-stu-id="79784-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="79784-113">Accesso iniziale</span><span class="sxs-lookup"><span data-stu-id="79784-113">Initial Access</span></span>
- <span data-ttu-id="79784-114">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="79784-114">Execution</span></span>
- <span data-ttu-id="79784-115">Persistenza</span><span class="sxs-lookup"><span data-stu-id="79784-115">Persistence</span></span>
- <span data-ttu-id="79784-116">Escalation dei privilegi</span><span class="sxs-lookup"><span data-stu-id="79784-116">Privilege Escalation</span></span>
- <span data-ttu-id="79784-117">Evasione delle difese</span><span class="sxs-lookup"><span data-stu-id="79784-117">Defense Evasion</span></span>
- <span data-ttu-id="79784-118">Accesso alle credenziali</span><span class="sxs-lookup"><span data-stu-id="79784-118">Credential Access</span></span>
- <span data-ttu-id="79784-119">Raccolta</span><span class="sxs-lookup"><span data-stu-id="79784-119">Collection</span></span>
- <span data-ttu-id="79784-120">Sottrazione di dati</span><span class="sxs-lookup"><span data-stu-id="79784-120">Exfiltration</span></span>
- <span data-ttu-id="79784-121">Impatto</span><span class="sxs-lookup"><span data-stu-id="79784-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="79784-122">Classificazioni degli avvisi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="79784-122">Security alert classifications</span></span>

<span data-ttu-id="79784-123">Dopo un'adeguata indagine, tutti gli avvisi di governance delle app Microsoft possono essere classificati in base a uno dei seguenti tipi di attività:</span><span class="sxs-lookup"><span data-stu-id="79784-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="79784-124">Vero positivo (TP): un avviso su un'attività dannosa confermata.</span><span class="sxs-lookup"><span data-stu-id="79784-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="79784-125">Vero positivo non dannoso (B-TP): avviso su attività sospette ma non dannose, ad esempio un test di penetrazione o altre azioni sospette autorizzate.</span><span class="sxs-lookup"><span data-stu-id="79784-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="79784-126">Falso positivo (FP): avviso su un'attività non dannosa.</span><span class="sxs-lookup"><span data-stu-id="79784-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="79784-127">Passaggi generali dell'indagine</span><span class="sxs-lookup"><span data-stu-id="79784-127">General investigation steps</span></span>

<span data-ttu-id="79784-128">È consigliabile usare le seguenti linee guida generali durante l'analisi dei tipi di avviso per avere una maggiore comprensione della potenziale minaccia prima di applicare l'azione consigliata.</span><span class="sxs-lookup"><span data-stu-id="79784-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="79784-129">Esaminare il livello di gravità dell'app e confrontarlo con il resto delle app nel tenant.</span><span class="sxs-lookup"><span data-stu-id="79784-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="79784-130">Questa revisione consentirà di identificare quali app nel tenant rappresentano il rischio maggiore.</span><span class="sxs-lookup"><span data-stu-id="79784-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="79784-131">Se viene identificato un TP, esaminare tutte le attività dell'app per comprendere l'impatto.</span><span class="sxs-lookup"><span data-stu-id="79784-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="79784-132">Ad esempio, esaminare le informazioni seguenti sull'app:</span><span class="sxs-lookup"><span data-stu-id="79784-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="79784-133">Ambiti a cui è stato concesso l'accesso</span><span class="sxs-lookup"><span data-stu-id="79784-133">Scopes granted access</span></span>
  - <span data-ttu-id="79784-134">Comportamento insolito</span><span class="sxs-lookup"><span data-stu-id="79784-134">Unusual behavior</span></span>  
  - <span data-ttu-id="79784-135">Indirizzo IP e posizione</span><span class="sxs-lookup"><span data-stu-id="79784-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="79784-136">Avvisi di accesso iniziale</span><span class="sxs-lookup"><span data-stu-id="79784-136">Initial access alerts</span></span>

<span data-ttu-id="79784-137">Questa sezione descrive gli avvisi che indicano che un'app dannosa potrebbe tentare di mantenere il controllo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79784-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="79784-138">Nome dell'app codificata con ambiti di consenso sospetti</span><span class="sxs-lookup"><span data-stu-id="79784-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="79784-139">**Gravità:** media</span><span class="sxs-lookup"><span data-stu-id="79784-139">**Severity:** Medium</span></span>

<span data-ttu-id="79784-140">**Descrizione**: questo rilevamento identifica le app OAuth con caratteri, ad esempio caratteri Unicode o codificati, richiesti per gli ambiti di consenso sospetti e che hanno eseguito l'accesso alle cartelle di posta elettronica degli utenti tramite l'API Graph.</span><span class="sxs-lookup"><span data-stu-id="79784-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="79784-141">Questo avviso può indicare un tentativo di mimetizzare un'app dannosa come app nota e attendibile, in modo che gli antagonisti possano indurre gli utenti a fornire il consenso all'app dannosa.</span><span class="sxs-lookup"><span data-stu-id="79784-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="79784-142">**TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="79784-142">**TP or FP?**</span></span>

- <span data-ttu-id="79784-143">**TP**: se è possibile confermare che l'app OAuth ha codificato il nome visualizzato con gli ambiti sospetti recapitati da un'origine sconosciuta, viene indicato un vero positivo.</span><span class="sxs-lookup"><span data-stu-id="79784-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="79784-144">**Azione consigliata**: esaminare il livello di autorizzazione richiesto dall'app e quali utenti hanno concesso l'accesso.</span><span class="sxs-lookup"><span data-stu-id="79784-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="79784-145">In base all'indagine, è possibile scegliere di escludere l'accesso a questa app.</span><span class="sxs-lookup"><span data-stu-id="79784-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="79784-146">Per escludere l'accesso all'app, nella pagina delle app OAuth, nella riga in cui viene visualizzata l'app da escludere, selezionare l'icona di esclusione.</span><span class="sxs-lookup"><span data-stu-id="79784-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="79784-147">È possibile scegliere di indicare agli utenti che l'app che hanno installato e autorizzato è stata esclusa.</span><span class="sxs-lookup"><span data-stu-id="79784-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="79784-148">La notifica informa gli utenti che l'app verrà disabilitata e che non avranno accesso all'app connessa.</span><span class="sxs-lookup"><span data-stu-id="79784-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="79784-149">Se non si vuole informare gli utenti, deselezionare "Invia una notifica agli utenti che hanno concesso l'accesso a questa app vietata" nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79784-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="79784-150">È consigliabile informare gli utenti che l'app verrà presto bloccata e non sarà più possibile usarla.</span><span class="sxs-lookup"><span data-stu-id="79784-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="79784-151">**FP**: se si vuole confermare che l'app ha un nome codificato ma ha un uso aziendale legittimo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79784-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="79784-152">**Azione consigliata**: ignorare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="79784-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="79784-153">Comprendere l'ambito della violazione</span><span class="sxs-lookup"><span data-stu-id="79784-153">Understand the scope of the breach</span></span>

<span data-ttu-id="79784-154">Seguire l'esercitazione [Analizzare le app OAuth rischiose](/cloud-app-security/investigate-risky-oauth).</span><span class="sxs-lookup"><span data-stu-id="79784-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="79784-155">L'app OAuth con ambiti di lettura ha un URL di risposta sospetto</span><span class="sxs-lookup"><span data-stu-id="79784-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="79784-156">**Gravità**: media</span><span class="sxs-lookup"><span data-stu-id="79784-156">**Severity**: Medium</span></span>

<span data-ttu-id="79784-157">**Descrizione**: questo rilevamento identifica un'app OAuth con solo ambiti di lettura, ad esempio User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared e reindirizza all'URL di risposta sospetto tramite l'API Graph.</span><span class="sxs-lookup"><span data-stu-id="79784-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="79784-158">Questa attività tenta di indicare che l'app dannosa con autorizzazioni con privilegi inferiori (come gli ambiti di lettura) potrebbe essere sfruttata per condurre una ricognizione degli account utente.</span><span class="sxs-lookup"><span data-stu-id="79784-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="79784-159">**TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="79784-159">**TP or FP?**</span></span>

- <span data-ttu-id="79784-160">**TP**: se è possibile confermare che l'app OAuth con ambito di lettura viene recapitata da un'origine sconosciuta e reindirizza a un URL sospetto, viene indicato un vero positivo.</span><span class="sxs-lookup"><span data-stu-id="79784-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="79784-161">**Azione consigliata**: esaminare l'URL di risposta e gli ambiti richiesti dall'app.</span><span class="sxs-lookup"><span data-stu-id="79784-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="79784-162">In base all'indagine, è possibile scegliere di escludere l'accesso a questa app.</span><span class="sxs-lookup"><span data-stu-id="79784-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="79784-163">Esaminare il livello di autorizzazione richiesto dall'app e quali utenti hanno concesso l'accesso.</span><span class="sxs-lookup"><span data-stu-id="79784-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="79784-164">Per escludere l'accesso all'app, nella pagina delle app OAuth, nella riga in cui viene visualizzata l'app da escludere, selezionare l'icona di esclusione.</span><span class="sxs-lookup"><span data-stu-id="79784-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="79784-165">È possibile scegliere di indicare agli utenti che l'app che hanno installato e autorizzato è stata esclusa.</span><span class="sxs-lookup"><span data-stu-id="79784-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="79784-166">La notifica informa gli utenti che l'app verrà disabilitata e che non avranno accesso all'app connessa.</span><span class="sxs-lookup"><span data-stu-id="79784-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="79784-167">Se non si vuole informare gli utenti, deselezionare "Invia una notifica agli utenti che hanno concesso l'accesso a questa app vietata" nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79784-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="79784-168">È consigliabile informare gli utenti che l'app verrà presto bloccata e non sarà più possibile usarla.</span><span class="sxs-lookup"><span data-stu-id="79784-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="79784-169">**B-TP**: se dopo un'indagine, è possibile verificare che l'app abbia un uso aziendale legittimo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79784-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="79784-170">**Azione consigliata**: ignorare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="79784-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="79784-171">Comprendere l'ambito della violazione</span><span class="sxs-lookup"><span data-stu-id="79784-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="79784-172">Esaminare tutte le attività eseguite dall'app.</span><span class="sxs-lookup"><span data-stu-id="79784-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="79784-173">Se si hanno dubbi che un'app sia sospetta, è consigliabile analizzare il nome e l'URL di risposta dell'app in diversi app store.</span><span class="sxs-lookup"><span data-stu-id="79784-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="79784-174">Quando si controllano gli app store, concentrarsi sui tipi di app seguenti:</span><span class="sxs-lookup"><span data-stu-id="79784-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="79784-175">App create di recente.</span><span class="sxs-lookup"><span data-stu-id="79784-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="79784-176">App con un URL di risposta sospetto</span><span class="sxs-lookup"><span data-stu-id="79784-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="79784-177">App che non sono state aggiornate di recente.</span><span class="sxs-lookup"><span data-stu-id="79784-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="79784-178">La mancanza di aggiornamenti potrebbe indicare che l'app non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="79784-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="79784-179">Se si hanno dubbi che un'app sia sospetta, è possibile cercare il nome dell'app, il nome dell'editore e l'URL di risposta online</span><span class="sxs-lookup"><span data-stu-id="79784-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="79784-180">Avvisi di persistenza</span><span class="sxs-lookup"><span data-stu-id="79784-180">Persistence alerts</span></span>

<span data-ttu-id="79784-181">Questa sezione descrive gli avvisi che indicano che un antagonista potrebbe tentare di mantenere il controllo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79784-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="79784-182">L'app con ambito OAuth sospetto crea una regola Posta in arrivo</span><span class="sxs-lookup"><span data-stu-id="79784-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="79784-183">**Gravità**: media</span><span class="sxs-lookup"><span data-stu-id="79784-183">**Severity**: Medium</span></span>

<span data-ttu-id="79784-184">**ID MITRE**: T1137.005, T1114</span><span class="sxs-lookup"><span data-stu-id="79784-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="79784-185">Questo rilevamento identifica un'app OAuth che ha acconsentito a ambiti sospetti, crea una regola Posta in arrivo sospetta e accede alle cartelle di posta e ai messaggi degli utenti tramite l'API Graph.</span><span class="sxs-lookup"><span data-stu-id="79784-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="79784-186">Le regole Posta in arrivo, ad esempio l'inoltro di tutte o specifiche e-mail a un altro account di posta elettronica, e le chiamate Graph per accedere alle e-mail e inviarle a un altro account di posta elettronica, possono essere un tentativo di esfiltrare le informazioni dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79784-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="79784-187">**TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="79784-187">**TP or FP?**</span></span>

- <span data-ttu-id="79784-188">**TP**: se è possibile confermare che la regola Posta in arrivo è stata creata da un'app di terze parti OAuth con ambiti sospetti recapitati da un'origine sconosciuta, viene indicato un vero positivo.</span><span class="sxs-lookup"><span data-stu-id="79784-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="79784-189">**Azione consigliata**: disabilitare e rimuovere l'app, reimpostare la password e rimuovere la regola Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="79784-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="79784-190">Seguire l'esercitazione su come reimpostare una password usando Azure Active Directory e l'esercitazione su come rimuovere la regola Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="79784-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="79784-191">**FP**: se è possibile confermare che l'app ha creato una regola di posta in arrivo per un account di posta elettronica esterno nuovo o personale per motivi legittimi.</span><span class="sxs-lookup"><span data-stu-id="79784-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="79784-192">**Azione consigliata**: ignorare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="79784-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="79784-193">Comprendere l'ambito della violazione</span><span class="sxs-lookup"><span data-stu-id="79784-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="79784-194">Esaminare tutte le attività eseguite dall'app.</span><span class="sxs-lookup"><span data-stu-id="79784-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="79784-195">Esaminare gli ambiti concessi dall'app.</span><span class="sxs-lookup"><span data-stu-id="79784-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="79784-196">Esaminare l'azione e la condizione della regola Posta in arrivo creata dall'app.</span><span class="sxs-lookup"><span data-stu-id="79784-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="79784-197">Avvisi di raccolta</span><span class="sxs-lookup"><span data-stu-id="79784-197">Collection alerts</span></span>

<span data-ttu-id="79784-198">Questa sezione descrive gli avvisi che indicano che un antagonista potrebbe tentare di raccogliere dati di interesse dall'organizzazione per i propri obiettivi.</span><span class="sxs-lookup"><span data-stu-id="79784-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="79784-199">L'app ha effettuato chiamate anomale a Graph per leggere le e-mail.</span><span class="sxs-lookup"><span data-stu-id="79784-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="79784-200">**Gravità**: media</span><span class="sxs-lookup"><span data-stu-id="79784-200">**Severity**: Medium</span></span>

<span data-ttu-id="79784-201">**ID MITRE**: T1114</span><span class="sxs-lookup"><span data-stu-id="79784-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="79784-202">Questo rilevamento identifica quando l'app OAuth Line of Business (LOB) accede a un volume insolito e elevato di cartelle ed e-mail dell'utente tramite l'API Graph, che può indicare un tentativo di violazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="79784-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="79784-203">**TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="79784-203">**TP or FP?**</span></span>

- <span data-ttu-id="79784-204">**TP**: se è possibile confermare che l'attività insolita del grafico è stata eseguita dall'app OAuth Line of Business (LOB), viene indicato un vero positivo.</span><span class="sxs-lookup"><span data-stu-id="79784-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="79784-205">**Azioni consigliate**: disabilitare temporaneamente l'app, reimpostare la password e riabilitare l'app.</span><span class="sxs-lookup"><span data-stu-id="79784-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="79784-206">Seguire l'esercitazione su come reimpostare una password usando Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79784-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="79784-207">**FP**: se è possibile confermare che l'app ha lo scopo di eseguire un volume elevato di chiamate Graph.</span><span class="sxs-lookup"><span data-stu-id="79784-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="79784-208">**Azione consigliata**: ignorare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="79784-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="79784-209">Comprendere l'ambito della violazione</span><span class="sxs-lookup"><span data-stu-id="79784-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="79784-210">Esaminare il log attività per gli eventi eseguiti da questa app in modo comprendere meglio le altre attività di Graph per leggere le e-mail e tentare di raccogliere informazioni riservate sugli utenti.</span><span class="sxs-lookup"><span data-stu-id="79784-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="79784-211">Monitorare l'aggiunta di credenziali impreviste all'app.</span><span class="sxs-lookup"><span data-stu-id="79784-211">Monitor for unexpected credential being added to the app.</span></span>
