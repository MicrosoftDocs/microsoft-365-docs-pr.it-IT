---
title: Usare le utilità di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: Informazioni sulle utilità in Advanced eDiscovery, tra cui log del caso, dati di cancellazione, errori di processo, modifica della pertinenza e analisi della trasparenza.
ms.openlocfilehash: 4283bc7bea509c8a01fb45c433964230a5256f8a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936619"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a><span data-ttu-id="0094c-103">Usare le utilità di Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="0094c-103">Use Advanced eDiscovery (classic) utilities</span></span>

> [!NOTE]
> <span data-ttu-id="0094c-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="0094c-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="0094c-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="0094c-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="0094c-106">Le utilità visualizzate e disponibili in Advanced eDiscovery dipendono dai ruoli contesto e utente.</span><span class="sxs-lookup"><span data-stu-id="0094c-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="0094c-107">Registro case</span><span class="sxs-lookup"><span data-stu-id="0094c-107">Case log</span></span>

<span data-ttu-id="0094c-108">Il registro dei casi fornisce un elenco dettagliato delle attività di elaborazione delle applicazioni, che possono essere utilizzate per la verifica, la risoluzione dei problemi e per l'indirizzamento di errori e avvisi.</span><span class="sxs-lookup"><span data-stu-id="0094c-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="0094c-109">Il registro può essere generato e archiviato localmente nell'host o nel server oppure inviato direttamente a un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0094c-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="0094c-110">Il file di registro può essere scaricato anche nel computer del client.</span><span class="sxs-lookup"><span data-stu-id="0094c-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="0094c-111">L'opzione download client può essere abilitata o disabilitata in base alla configurazione e al ruolo utente.</span><span class="sxs-lookup"><span data-stu-id="0094c-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="0094c-112">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="0094c-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="0094c-113">Nella scheda \*\* \> utilità di impostazioni e utilità\*\* Selezionare \*\* \> installazione log dei casi\*\*.</span><span class="sxs-lookup"><span data-stu-id="0094c-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="0094c-114">Selezionare il **livello di registrazione** come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0094c-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="0094c-115">**Standard**: include i dati di log di base.</span><span class="sxs-lookup"><span data-stu-id="0094c-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="0094c-116">Questa opzione è in genere necessaria per il monitoraggio e deve essere utilizzata se non diversamente consigliato.</span><span class="sxs-lookup"><span data-stu-id="0094c-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="0094c-117">**Minimal**: utilizzato per casi molto grandi e restituisce solo i dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="0094c-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="0094c-118">Fare clic su **Run case log**.</span><span class="sxs-lookup"><span data-stu-id="0094c-118">Click **Run Case log**.</span></span> <span data-ttu-id="0094c-119">Il log viene generato e viene visualizzato il percorso.</span><span class="sxs-lookup"><span data-stu-id="0094c-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="0094c-120">Le informazioni sull'avanzamento delle attività per l'attività corrente e ultima vengono visualizzate nel riquadro Stato attività.</span><span class="sxs-lookup"><span data-stu-id="0094c-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="0094c-121">Cancellare i dati</span><span class="sxs-lookup"><span data-stu-id="0094c-121">Clear data</span></span>

<span data-ttu-id="0094c-122">Se è necessario eliminare o reinizializzare i dati del caso, è necessario inizializzare l'istanza del database.</span><span class="sxs-lookup"><span data-stu-id="0094c-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="0094c-123">L'utilità Cancella dati consente di eliminare tutte le voci specificate dal database del caso, dai file di testo, dalla cartella del caso e dai risultati accumulati.</span><span class="sxs-lookup"><span data-stu-id="0094c-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="0094c-124">La funzione può essere eseguita solo da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="0094c-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0094c-125">Questa azione non è reversibile e cancellerà tutti i tag di pertinenza e l'analisi eseguiti dall'esperto.</span><span class="sxs-lookup"><span data-stu-id="0094c-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="0094c-126">Salvare un backup dei dati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0094c-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="0094c-127">Utilizzare questa opzione con estrema attenzione.</span><span class="sxs-lookup"><span data-stu-id="0094c-127">Use this option with extreme care.</span></span> <span data-ttu-id="0094c-128">L'eliminazione dei file contrassegnati e classificati può influire sui risultati della pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0094c-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="0094c-129">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="0094c-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="0094c-130">Nella scheda \*\* \> utilità di impostazioni e utilità\*\* selezionare **Annulla \> installazione dati**.</span><span class="sxs-lookup"><span data-stu-id="0094c-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="0094c-131">Selezionare un'opzione per l'inizializzazione delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="0094c-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="0094c-132">**Pertinenza**: Elimina tutti i lavori in pertinenza, tra cui la definizione dei carichi e l'associazione dei file ai carichi.</span><span class="sxs-lookup"><span data-stu-id="0094c-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="0094c-133">Elimina tutti gli esempi e il tagging.</span><span class="sxs-lookup"><span data-stu-id="0094c-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="0094c-134">**Quasi duplicati e thread di posta elettronica**: consente di eliminare tutte le informazioni di analisi di quasi duplicati e thread di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0094c-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="0094c-135">**Temi**: Elimina i dati correlati ai temi.</span><span class="sxs-lookup"><span data-stu-id="0094c-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="0094c-136">**Esporta cronologia**: Elimina le informazioni sulla cronologia dei batch di esportazione.</span><span class="sxs-lookup"><span data-stu-id="0094c-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="0094c-137">Fare clic su **Pulisci dati**.</span><span class="sxs-lookup"><span data-stu-id="0094c-137">Click **Clear data**.</span></span> <span data-ttu-id="0094c-138">I dati del caso sono deselezionati.</span><span class="sxs-lookup"><span data-stu-id="0094c-138">The case data is cleared.</span></span> <span data-ttu-id="0094c-139">Le informazioni sull'avanzamento delle attività per l'attività corrente e ultima vengono visualizzate nel riquadro **stato attività** .</span><span class="sxs-lookup"><span data-stu-id="0094c-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="0094c-140">Modifica pertinenza</span><span class="sxs-lookup"><span data-stu-id="0094c-140">Modify Relevance</span></span>

<span data-ttu-id="0094c-141">In questa sezione viene descritto come ignorare o eseguire il rollback di un esempio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0094c-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="0094c-142">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="0094c-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="0094c-143">Nella scheda \*\* \> utilità di impostazioni e utilità\*\* Selezionare **modifica pertinenza**.</span><span class="sxs-lookup"><span data-stu-id="0094c-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="0094c-144">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0094c-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="0094c-145">**Ignora il campione corrente-per l'utente corrente**: questo tag, come **Ignora**, tutti i file senza tag nell'esempio Open case dell'utente che esegue l'utilità.</span><span class="sxs-lookup"><span data-stu-id="0094c-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="0094c-146">L'elaborazione della pertinenza non verrà eseguita nei file contrassegnati come **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="0094c-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="0094c-147">**Ignora campione corrente-tutti gli esempi aperti**: questo tag, come **Ignora**, tutti i file senza tag in tutti gli esempi aperti per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0094c-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="0094c-148">Questa opzione non è consigliata se gli utenti sono attualmente tagging campioni.</span><span class="sxs-lookup"><span data-stu-id="0094c-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="0094c-149">**Rollback ultimo esempio**: viene eseguito il rollback dell'ultimo esempio di Training relativo alla pertinenza completata, indipendentemente dal fatto che sia prima o dopo il processo di calcolo.</span><span class="sxs-lookup"><span data-stu-id="0094c-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="0094c-150">Il rollback di un esempio di catch-up non è consentito.</span><span class="sxs-lookup"><span data-stu-id="0094c-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="0094c-151">Fare clic su **Esegui** per eseguire.</span><span class="sxs-lookup"><span data-stu-id="0094c-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="0094c-152">Analisi della trasparenza</span><span class="sxs-lookup"><span data-stu-id="0094c-152">Transparency analysis</span></span>

<span data-ttu-id="0094c-153">L'utilità di analisi della trasparenza attiva una visualizzazione dettagliata dei file e il relativo punteggio di pertinenza assegnato.</span><span class="sxs-lookup"><span data-stu-id="0094c-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="0094c-154">Il rapporto può essere utilizzato come verifica di integrità o per confrontare la pertinenza di un file definito da un revisore umano rispetto alla pertinenza assegnata da Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0094c-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="0094c-155">Oltre ai punteggi di pertinenza, Advanced eDiscovery calcola e assegna i pesi delle parole chiave che considerano il contesto di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="0094c-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="0094c-156">La stessa parola di un file può essere assegnata a pesi diversi, in base al contesto e alla posizione.</span><span class="sxs-lookup"><span data-stu-id="0094c-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="0094c-157">Ogni parola chiave è contrassegnata usando una scala crescente di colore che spazia dal giallo all'arancio scuro e dalle diverse sfumature di grigio.</span><span class="sxs-lookup"><span data-stu-id="0094c-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="0094c-158">La codifica a colori viene utilizzata per indicare visivamente il contributo positivo o negativo relativo alla parola al Punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="0094c-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="0094c-159">In uno scenario con più problemi, è possibile generare un report di analisi della trasparenza per ogni problema.</span><span class="sxs-lookup"><span data-stu-id="0094c-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="0094c-160">Sulla barra dei menu, fare clic sull'icona **cremagliera** .</span><span class="sxs-lookup"><span data-stu-id="0094c-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="0094c-161">Nella scheda \*\* \> Utilità impostazioni e utilità\*\* Selezionare \*\* \> installazione analisi trasparenza\*\*.</span><span class="sxs-lookup"><span data-stu-id="0094c-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="0094c-162">In \* \* file ID \* \*, immettere l'ID file del file da elaborare.</span><span class="sxs-lookup"><span data-stu-id="0094c-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="0094c-163">Nell'elenco **problema** selezionare il problema pertinente.</span><span class="sxs-lookup"><span data-stu-id="0094c-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="0094c-164">Fare clic su **analisi trasparenza**.</span><span class="sxs-lookup"><span data-stu-id="0094c-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="0094c-165">Al termine, viene visualizzato il rapporto analisi trasparenza per il file, che Mostra come i colori delle parole chiave contrassegnate sono correlati al Punteggio di pertinenza generale.</span><span class="sxs-lookup"><span data-stu-id="0094c-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0094c-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0094c-166">See also</span></span>

[<span data-ttu-id="0094c-167">Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="0094c-167">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="0094c-168">Definizione delle impostazioni del case e del tenant</span><span class="sxs-lookup"><span data-stu-id="0094c-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

