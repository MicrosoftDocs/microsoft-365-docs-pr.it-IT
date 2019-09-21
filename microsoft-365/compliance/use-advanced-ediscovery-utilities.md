---
title: Utilizzare le utilità avanzate di eDiscovery di Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Informazioni sulle utilità in Office 365 Advanced eDiscovery, tra cui log di caso, dati di cancellazione, errori di processo, modifica della pertinenza e analisi della trasparenza.  '
ms.openlocfilehash: df769ddddd37284da50bc715444f2bf928307706
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084057"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="ab355-103">Utilizzare le utilità avanzate di eDiscovery di Office 365</span><span class="sxs-lookup"><span data-stu-id="ab355-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="ab355-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ab355-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ab355-106">Le utilità visualizzate e disponibili in Advanced eDiscovery dipendono dai ruoli contesto e utente.</span><span class="sxs-lookup"><span data-stu-id="ab355-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="ab355-107">Registro case</span><span class="sxs-lookup"><span data-stu-id="ab355-107">Case log</span></span>

<span data-ttu-id="ab355-108">Il registro dei casi fornisce un elenco dettagliato delle attività di elaborazione delle applicazioni, che possono essere utilizzate per la verifica, la risoluzione dei problemi e per l'indirizzamento di errori e avvisi.</span><span class="sxs-lookup"><span data-stu-id="ab355-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="ab355-109">Il registro può essere generato e archiviato localmente nell'host o nel server oppure inviato direttamente a un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ab355-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="ab355-110">Il file di registro può essere scaricato anche nel computer del client.</span><span class="sxs-lookup"><span data-stu-id="ab355-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="ab355-111">L'opzione download client può essere abilitata o disabilitata in base alla configurazione e al ruolo utente.</span><span class="sxs-lookup"><span data-stu-id="ab355-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="ab355-112">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="ab355-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ab355-113">Nella scheda **utilità di impostazioni \> e utilità** Selezionare \*\* \> installazione log dei casi\*\*.</span><span class="sxs-lookup"><span data-stu-id="ab355-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="ab355-114">Selezionare il **livello di registrazione** come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ab355-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="ab355-115">**Standard**: include i dati di log di base.</span><span class="sxs-lookup"><span data-stu-id="ab355-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="ab355-116">Questa opzione è in genere necessaria per il monitoraggio e deve essere utilizzata se non diversamente consigliato.</span><span class="sxs-lookup"><span data-stu-id="ab355-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="ab355-117">**Minimal**: utilizzato per casi molto grandi e restituisce solo i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="ab355-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="ab355-118">Fare clic su **Run case log**.</span><span class="sxs-lookup"><span data-stu-id="ab355-118">Click **Run Case log**.</span></span> <span data-ttu-id="ab355-119">Il log viene generato e viene visualizzato il percorso.</span><span class="sxs-lookup"><span data-stu-id="ab355-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="ab355-120">Le informazioni sull'avanzamento delle attività per l'attività corrente e ultima vengono visualizzate nel riquadro Stato attività.</span><span class="sxs-lookup"><span data-stu-id="ab355-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="ab355-121">Cancellare i dati</span><span class="sxs-lookup"><span data-stu-id="ab355-121">Clear data</span></span>

<span data-ttu-id="ab355-122">Se è necessario eliminare o reinizializzare i dati del caso, è necessario inizializzare l'istanza del database.</span><span class="sxs-lookup"><span data-stu-id="ab355-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="ab355-123">L'utilità Cancella dati consente di eliminare tutte le voci specificate dal database del caso, dai file di testo, dalla cartella del caso e dai risultati accumulati.</span><span class="sxs-lookup"><span data-stu-id="ab355-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="ab355-124">La funzione può essere eseguita solo da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="ab355-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ab355-125">Questa azione non è reversibile e cancellerà tutti i tag di pertinenza e l'analisi eseguiti dall'esperto.</span><span class="sxs-lookup"><span data-stu-id="ab355-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="ab355-126">Salvare un backup dei dati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ab355-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="ab355-127">Utilizzare questa opzione con estrema attenzione.</span><span class="sxs-lookup"><span data-stu-id="ab355-127">Use this option with extreme care.</span></span> <span data-ttu-id="ab355-128">L'eliminazione dei file contrassegnati e classificati può influire sui risultati della pertinenza.</span><span class="sxs-lookup"><span data-stu-id="ab355-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="ab355-129">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="ab355-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ab355-130">Nella scheda **utilità di impostazioni \> e utilità** Selezionare \*\*Annulla installazione dati \> \*\*.</span><span class="sxs-lookup"><span data-stu-id="ab355-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="ab355-131">Selezionare un'opzione per l'inizializzazione delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="ab355-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="ab355-132">**Pertinenza**: Elimina tutti i lavori in pertinenza, tra cui la definizione dei carichi e l'associazione dei file ai carichi.</span><span class="sxs-lookup"><span data-stu-id="ab355-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="ab355-133">Elimina tutti gli esempi e il tagging.</span><span class="sxs-lookup"><span data-stu-id="ab355-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="ab355-134">**Quasi duplicati e thread di posta elettronica**: consente di eliminare tutte le informazioni di analisi di quasi duplicati e thread di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ab355-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="ab355-135">**Temi**: Elimina i dati correlati ai temi.</span><span class="sxs-lookup"><span data-stu-id="ab355-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="ab355-136">**Esporta cronologia**: Elimina le informazioni sulla cronologia dei batch di esportazione.</span><span class="sxs-lookup"><span data-stu-id="ab355-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="ab355-137">Fare clic su **Pulisci dati**.</span><span class="sxs-lookup"><span data-stu-id="ab355-137">Click **Clear data**.</span></span> <span data-ttu-id="ab355-138">I dati del caso sono deselezionati.</span><span class="sxs-lookup"><span data-stu-id="ab355-138">The case data is cleared.</span></span> <span data-ttu-id="ab355-139">Le informazioni sull'avanzamento delle attività per l'attività corrente e ultima vengono visualizzate nel riquadro **stato attività** .</span><span class="sxs-lookup"><span data-stu-id="ab355-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="ab355-140">Modifica pertinenza</span><span class="sxs-lookup"><span data-stu-id="ab355-140">Modify Relevance</span></span>

<span data-ttu-id="ab355-141">In questa sezione viene descritto come ignorare o eseguire il rollback di un esempio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="ab355-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="ab355-142">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="ab355-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ab355-143">Nella scheda **utilità di impostazioni \> e utilità** Selezionare **modifica pertinenza**.</span><span class="sxs-lookup"><span data-stu-id="ab355-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="ab355-144">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab355-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="ab355-145">**Ignora il campione corrente-per l'utente corrente**: questo tag, come **Ignora**, tutti i file senza tag nell'esempio Open case dell'utente che esegue l'utilità.</span><span class="sxs-lookup"><span data-stu-id="ab355-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="ab355-146">L'elaborazione della pertinenza non verrà eseguita nei file contrassegnati come **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="ab355-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="ab355-147">**Ignora campione corrente-tutti gli esempi aperti**: questo tag, come **Ignora**, tutti i file senza tag in tutti gli esempi aperti per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ab355-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="ab355-148">Questa opzione non è consigliata se gli utenti sono attualmente tagging campioni.</span><span class="sxs-lookup"><span data-stu-id="ab355-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="ab355-149">**Rollback ultimo esempio**: viene eseguito il rollback dell'ultimo esempio di Training relativo alla pertinenza completata, indipendentemente dal fatto che sia prima o dopo il processo di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ab355-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="ab355-150">Il rollback di un esempio di catch-up non è consentito.</span><span class="sxs-lookup"><span data-stu-id="ab355-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="ab355-151">Fare clic su **Esegui** per eseguire.</span><span class="sxs-lookup"><span data-stu-id="ab355-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="ab355-152">Analisi della trasparenza</span><span class="sxs-lookup"><span data-stu-id="ab355-152">Transparency analysis</span></span>

<span data-ttu-id="ab355-153">L'utilità di analisi della trasparenza attiva una visualizzazione dettagliata dei file e il relativo punteggio di pertinenza assegnato.</span><span class="sxs-lookup"><span data-stu-id="ab355-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="ab355-154">Il rapporto può essere utilizzato come verifica di integrità o per confrontare la pertinenza di un file definito da un revisore umano rispetto alla pertinenza assegnata da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ab355-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="ab355-155">Oltre ai punteggi di pertinenza, Advanced eDiscovery calcola e assegna i pesi delle parole chiave che considerano il contesto di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="ab355-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="ab355-156">La stessa parola di un file può essere assegnata a pesi diversi, in base al contesto e alla posizione.</span><span class="sxs-lookup"><span data-stu-id="ab355-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="ab355-157">Ogni parola chiave è contrassegnata usando una scala crescente di colore che spazia dal giallo all'arancio scuro e dalle diverse sfumature di grigio.</span><span class="sxs-lookup"><span data-stu-id="ab355-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="ab355-158">La codifica a colori viene utilizzata per indicare visivamente il contributo positivo o negativo relativo alla parola al Punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="ab355-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="ab355-159">In uno scenario con più problemi, è possibile generare un report di analisi della trasparenza per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="ab355-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="ab355-160">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="ab355-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ab355-161">Nella scheda **Utilità impostazioni e \> utilità** selezionare **installazione analisi \> trasparenza**.</span><span class="sxs-lookup"><span data-stu-id="ab355-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="ab355-162">In \* \* file ID \* \*, immettere l'ID file del file da elaborare.</span><span class="sxs-lookup"><span data-stu-id="ab355-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="ab355-163">Nell'elenco **problema** selezionare il problema pertinente.</span><span class="sxs-lookup"><span data-stu-id="ab355-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="ab355-164">Fare clic su **analisi trasparenza**.</span><span class="sxs-lookup"><span data-stu-id="ab355-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="ab355-165">Al termine, viene visualizzato il rapporto analisi trasparenza per il file, che Mostra come i colori delle parole chiave contrassegnate sono correlati al Punteggio di pertinenza generale.</span><span class="sxs-lookup"><span data-stu-id="ab355-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ab355-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab355-166">See also</span></span>

[<span data-ttu-id="ab355-167">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ab355-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ab355-168">Definizione delle impostazioni del case e del tenant</span><span class="sxs-lookup"><span data-stu-id="ab355-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

