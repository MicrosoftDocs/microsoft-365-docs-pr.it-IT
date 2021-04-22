---
title: Punteggio di sicurezza Microsoft per dispositivi
description: Il punteggio per i dispositivi mostra lo stato di configurazione della sicurezza collettiva dei dispositivi tra applicazioni, sistema operativo, rete, account e controlli di sicurezza.
keywords: Microsoft Secure Score for Devices, Microsoft Defender for Endpoint Microsoft Secure Score for Devices, secure score, configuration score, threat and vulnerability management, security controls, improvement opportunities, security configuration score over time, security posture, baseline
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
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934082"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="f1c83-104">Punteggio di sicurezza Microsoft per dispositivi</span><span class="sxs-lookup"><span data-stu-id="f1c83-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1c83-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f1c83-105">**Applies to:**</span></span>

- [<span data-ttu-id="f1c83-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f1c83-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f1c83-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="f1c83-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f1c83-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1c83-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f1c83-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f1c83-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f1c83-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f1c83-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="f1c83-111">Il punteggio di configurazione fa ora parte della gestione delle minacce e delle vulnerabilità come Punteggio sicuro Microsoft per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f1c83-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="f1c83-112">Il punteggio per i dispositivi è visibile nel [dashboard di gestione](tvm-dashboard-insights.md) delle minacce e delle vulnerabilità di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="f1c83-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="f1c83-113">Un punteggio microsoft sicuro più alto per i dispositivi significa che gli endpoint sono più resilienti dagli attacchi di minacce alla cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="f1c83-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="f1c83-114">Riflette lo stato di configurazione della sicurezza collettiva dei dispositivi nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1c83-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="f1c83-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="f1c83-115">Application</span></span>
- <span data-ttu-id="f1c83-116">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="f1c83-116">Operating system</span></span>
- <span data-ttu-id="f1c83-117">Rete</span><span class="sxs-lookup"><span data-stu-id="f1c83-117">Network</span></span>
- <span data-ttu-id="f1c83-118">Account</span><span class="sxs-lookup"><span data-stu-id="f1c83-118">Accounts</span></span>
- <span data-ttu-id="f1c83-119">Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1c83-119">Security controls</span></span>

<span data-ttu-id="f1c83-120">Selezionare una categoria per passare alla pagina [**Suggerimenti per**](tvm-security-recommendation.md) la sicurezza e visualizzare i suggerimenti pertinenti.</span><span class="sxs-lookup"><span data-stu-id="f1c83-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="f1c83-121">Attivare il connettore Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="f1c83-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="f1c83-122">Inoltra i segnali di Microsoft Defender for Endpoint, offrendo a Microsoft Secure Score visibilità sulla posizione di sicurezza del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1c83-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="f1c83-123">I dati inoltrati vengono archiviati ed elaborati nella stessa posizione dei dati di Microsoft Secure Score.</span><span class="sxs-lookup"><span data-stu-id="f1c83-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="f1c83-124">Le modifiche potrebbero richiedere fino a poche ore per riflettere nel dashboard.</span><span class="sxs-lookup"><span data-stu-id="f1c83-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="f1c83-125">Nel riquadro di spostamento passare a **Impostazioni**  >  **Caratteristiche avanzate**</span><span class="sxs-lookup"><span data-stu-id="f1c83-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="f1c83-126">Scorrere verso il basso **fino a Microsoft Secure Score** e attivare o disattivare l'impostazione su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="f1c83-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="f1c83-127">Selezionare **Salva preferenze.**</span><span class="sxs-lookup"><span data-stu-id="f1c83-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="f1c83-128">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="f1c83-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="f1c83-129">Microsoft Secure Score per i dispositivi attualmente supporta le configurazioni impostate tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f1c83-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="f1c83-130">A causa dell'attuale supporto parziale di Intune, le configurazioni che potrebbero essere state impostate tramite Intune potrebbero risultare non configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="f1c83-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="f1c83-131">Contattare l'amministratore IT per verificare lo stato di configurazione effettivo nel caso in cui l'organizzazione utilizzi Intune per la gestione sicura della configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1c83-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="f1c83-132">I dati nella scheda Microsoft Secure Score for Devices sono il prodotto di un processo di individuazione delle vulnerabilità meticoloso e continuo.</span><span class="sxs-lookup"><span data-stu-id="f1c83-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="f1c83-133">Viene aggregato con valutazioni di individuazione della configurazione che continuamente:</span><span class="sxs-lookup"><span data-stu-id="f1c83-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="f1c83-134">Confrontare le configurazioni raccolte con i benchmark raccolti per individuare asset non configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="f1c83-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="f1c83-135">Mappare le configurazioni a vulnerabilità che possono essere corretti o parzialmente corretti (riduzione dei rischi)</span><span class="sxs-lookup"><span data-stu-id="f1c83-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="f1c83-136">Raccogliere e gestire benchmark di configurazione delle procedure consigliate (fornitori, feed di sicurezza, team di ricerca interni)</span><span class="sxs-lookup"><span data-stu-id="f1c83-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="f1c83-137">Raccogliere e monitorare le modifiche dello stato di configurazione del controllo di sicurezza da tutti gli asset</span><span class="sxs-lookup"><span data-stu-id="f1c83-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="f1c83-138">Migliorare la configurazione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1c83-138">Improve your security configuration</span></span>

<span data-ttu-id="f1c83-139">Migliorare la configurazione della sicurezza corredando i problemi dall'elenco dei suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f1c83-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="f1c83-140">In questo modo, microsoft Secure Score for Devices migliora e l'organizzazione diventa più resiliente alle minacce e alle vulnerabilità di cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="f1c83-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="f1c83-141">Nella scheda Microsoft Secure Score for Devices nel dashboard di gestione delle minacce e delle vulnerabilità seleziona una delle categorie.</span><span class="sxs-lookup"><span data-stu-id="f1c83-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="f1c83-142">Verrà visualizzato l'elenco dei suggerimenti relativi a tale categoria.</span><span class="sxs-lookup"><span data-stu-id="f1c83-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="f1c83-143">Verrà visualizzata la pagina [**Suggerimenti per la**](tvm-security-recommendation.md) sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f1c83-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="f1c83-144">Se si desidera visualizzare tutti i suggerimenti per la sicurezza, una volta visualizzata la pagina Suggerimenti per la sicurezza, deselezionare il campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f1c83-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="f1c83-145">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1c83-145">Select an item on the list.</span></span> <span data-ttu-id="f1c83-146">Il riquadro a comparsa si aprirà con i dettagli relativi al suggerimento.</span><span class="sxs-lookup"><span data-stu-id="f1c83-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="f1c83-147">Selezionare **Opzioni di correzione.**</span><span class="sxs-lookup"><span data-stu-id="f1c83-147">Select **Remediation options**.</span></span>

   ![Suggerimenti sulla sicurezza correlati ai controlli di sicurezza](images/tvm_security_controls.png)

3. <span data-ttu-id="f1c83-149">Leggere la descrizione per comprendere il contesto del problema e le operazioni da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f1c83-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="f1c83-150">Selezionare una data di scadenza, aggiungere note e selezionare Esporta tutti i dati **dell'attività** di correzione in CSV in modo da poterli allegare a un messaggio di posta elettronica per il follow-up.</span><span class="sxs-lookup"><span data-stu-id="f1c83-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="f1c83-151">**Invia richiesta**.</span><span class="sxs-lookup"><span data-stu-id="f1c83-151">**Submit request**.</span></span> <span data-ttu-id="f1c83-152">Verrà visualizzato un messaggio di conferma che l'attività di correzione è stata creata.</span><span class="sxs-lookup"><span data-stu-id="f1c83-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="f1c83-153">![Conferma creazione attività di correzione](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="f1c83-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="f1c83-154">Salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="f1c83-154">Save your CSV file.</span></span>
   <span data-ttu-id="f1c83-155">![Salvare il file csv](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="f1c83-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="f1c83-156">Inviare un messaggio di posta elettronica di follow-up all'amministratore IT e consentire la propagazione nel sistema del tempo assegnato per la correzione.</span><span class="sxs-lookup"><span data-stu-id="f1c83-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="f1c83-157">Rivedere di **nuovo la scheda Microsoft Secure Score for Devices** nel dashboard.</span><span class="sxs-lookup"><span data-stu-id="f1c83-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="f1c83-158">Il numero di elementi consigliati per i controlli di sicurezza diminuisce.</span><span class="sxs-lookup"><span data-stu-id="f1c83-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="f1c83-159">Quando si seleziona **Controlli** di  sicurezza per tornare alla pagina Suggerimenti per la sicurezza, l'elemento che è stato indirizzato non sarà più presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1c83-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="f1c83-160">Il punteggio microsoft secure per i dispositivi dovrebbe aumentare.</span><span class="sxs-lookup"><span data-stu-id="f1c83-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f1c83-161">Per aumentare la frequenza di rilevamento della valutazione delle vulnerabilità, scaricare i seguenti aggiornamenti obbligatori per la sicurezza e distribuirli nella rete:</span><span class="sxs-lookup"><span data-stu-id="f1c83-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="f1c83-162">19H1 clienti | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="f1c83-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="f1c83-163">Clienti RS5 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="f1c83-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="f1c83-164">Clienti RS4 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="f1c83-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="f1c83-165">Clienti RS3 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="f1c83-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="f1c83-166">Per scaricare gli aggiornamenti della sicurezza:</span><span class="sxs-lookup"><span data-stu-id="f1c83-166">To download the security updates:</span></span>
>1. <span data-ttu-id="f1c83-167">Passare a [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span><span class="sxs-lookup"><span data-stu-id="f1c83-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="f1c83-168">Immettere il numero KB dell'aggiornamento della sicurezza da scaricare, quindi fare clic su **Cerca.**</span><span class="sxs-lookup"><span data-stu-id="f1c83-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="f1c83-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1c83-169">Related topics</span></span>

- [<span data-ttu-id="f1c83-170">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="f1c83-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f1c83-171">Dashboard</span><span class="sxs-lookup"><span data-stu-id="f1c83-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="f1c83-172">Punteggio di esposizione.</span><span class="sxs-lookup"><span data-stu-id="f1c83-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="f1c83-173">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1c83-173">Security recommendations</span></span>](tvm-security-recommendation.md)
