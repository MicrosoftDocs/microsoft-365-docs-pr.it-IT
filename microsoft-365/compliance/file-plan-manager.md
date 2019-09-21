---
title: Panoramica della gestione del piano file
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri di etichette di conservazione ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083750"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="4063b-103">Panoramica della gestione del piano file</span><span class="sxs-lookup"><span data-stu-id="4063b-103">Overview of file plan manager</span></span>

<span data-ttu-id="4063b-104">La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri di etichette di conservazione ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.</span><span class="sxs-lookup"><span data-stu-id="4063b-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Pagina del piano file](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="4063b-106">Accesso alla gestione del piano file</span><span class="sxs-lookup"><span data-stu-id="4063b-106">Accessing file plan manager</span></span>

<span data-ttu-id="4063b-107">I requisiti per accedere al piano file sono due:</span><span class="sxs-lookup"><span data-stu-id="4063b-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="4063b-108">Un abbonamento a Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="4063b-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="4063b-109">L’utente dispone di uno dei ruoli seguenti nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="4063b-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="4063b-110">Responsabile della conservazione</span><span class="sxs-lookup"><span data-stu-id="4063b-110">Retention Manager</span></span>
    - <span data-ttu-id="4063b-111">Responsabile della conservazione solo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="4063b-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="4063b-112">Etichette di conservazione e criteri di etichetta predefiniti</span><span class="sxs-lookup"><span data-stu-id="4063b-112">Default retention labels and label policy</span></span>

<span data-ttu-id="4063b-113">Se non sono presenti etichette conservazione nel Centro Sicurezza e Conformità, la prima volta in cui scegli **Piano file** nel riquadro di spostamento a sinistra, verrà creato un criterio di etichetta denominato **Criterio di pubblicazione di governance dei dati predefinito**.</span><span class="sxs-lookup"><span data-stu-id="4063b-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="4063b-114">Questo criterio di etichetta contiene tre etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="4063b-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="4063b-115">**Procedura operativa**</span><span class="sxs-lookup"><span data-stu-id="4063b-115">**Operational procedure**</span></span>
- <span data-ttu-id="4063b-116">**Business general**</span><span class="sxs-lookup"><span data-stu-id="4063b-116">**Business general**</span></span>
- <span data-ttu-id="4063b-117">**Accordo contrattuale**</span><span class="sxs-lookup"><span data-stu-id="4063b-117">**Contract agreement**</span></span>

<span data-ttu-id="4063b-118">Queste etichette di conservazione vengono configurate solo per conservare il contenuto, non per eliminare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4063b-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="4063b-119">Questo criterio di etichetta verrà pubblicato per l'intera organizzazione e può essere disattivato o rimosso.</span><span class="sxs-lookup"><span data-stu-id="4063b-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="4063b-120">È possibile stabilire chi ha aperto la gestione del piano file e avviato la first-run experience esaminando il log di controllo per le attività **Criteri di conservazione creati** e **Configurazione di conservazione creata per un criterio di conservazione**.</span><span class="sxs-lookup"><span data-stu-id="4063b-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="4063b-121">A causa di feedback di alcuni clienti, è stata rimossa la funzionalità che consente di creare le etichette di conservazione predefinite e i criteri di etichetta di conservazione indicati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4063b-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="4063b-122">Le etichette di conservazione e i criteri per le etichette di conservazione sono visibili solo se è stato aperta la gestione del piano file prima dell'11 aprile 2019.</span><span class="sxs-lookup"><span data-stu-id="4063b-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="4063b-123">Esplorare il piano file</span><span class="sxs-lookup"><span data-stu-id="4063b-123">Navigating your file plan</span></span>

<span data-ttu-id="4063b-124">La gestione del piano file semplifica la visualizzazione unica delle impostazioni di tutti i criteri e le etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="4063b-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="4063b-125">Si noti che le etichette di conservazione create all'esterno del piano file saranno disponibili nel piano file e viceversa.</span><span class="sxs-lookup"><span data-stu-id="4063b-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="4063b-126">Nella tabella **etichette piano file** sono disponibili le seguenti informazioni e funzionalità aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="4063b-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="4063b-127">Colonne impostazioni etichetta</span><span class="sxs-lookup"><span data-stu-id="4063b-127">Label settings columns</span></span>

- <span data-ttu-id="4063b-p103">**In base a** identifica il tipo di trigger che avvierà il periodo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4063b-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="4063b-130">Evento</span><span class="sxs-lookup"><span data-stu-id="4063b-130">Event</span></span>
    - <span data-ttu-id="4063b-131">Momento della creazione</span><span class="sxs-lookup"><span data-stu-id="4063b-131">When created</span></span>
    - <span data-ttu-id="4063b-132">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="4063b-132">When last modified</span></span>
    - <span data-ttu-id="4063b-133">Data etichettatura</span><span class="sxs-lookup"><span data-stu-id="4063b-133">When labeled</span></span>
- <span data-ttu-id="4063b-p104">**Record** indica se l'elemento diventa un record dichiarato dopo l'applicazione dell'etichetta. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4063b-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="4063b-136">No</span><span class="sxs-lookup"><span data-stu-id="4063b-136">No</span></span>
    - <span data-ttu-id="4063b-137">Sì</span><span class="sxs-lookup"><span data-stu-id="4063b-137">Yes</span></span>
    - <span data-ttu-id="4063b-138">Sì (normativo)</span><span class="sxs-lookup"><span data-stu-id="4063b-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="4063b-p105">**Conservazione** identifica il tipo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4063b-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="4063b-141">Conservare</span><span class="sxs-lookup"><span data-stu-id="4063b-141">Keep</span></span>
    - <span data-ttu-id="4063b-142">Conservare ed eliminare</span><span class="sxs-lookup"><span data-stu-id="4063b-142">Keep and delete</span></span>
    - <span data-ttu-id="4063b-143">Eliminare</span><span class="sxs-lookup"><span data-stu-id="4063b-143">Delete</span></span>
- <span data-ttu-id="4063b-p106">**Disposizione** identifica cosa succederà al contenuto alla fine del periodo di conservazione. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4063b-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="4063b-146">null</span><span class="sxs-lookup"><span data-stu-id="4063b-146">null</span></span>
    - <span data-ttu-id="4063b-147">Nessuna azione</span><span class="sxs-lookup"><span data-stu-id="4063b-147">No action</span></span>
    - <span data-ttu-id="4063b-148">Eliminazione automatica</span><span class="sxs-lookup"><span data-stu-id="4063b-148">Auto-delete</span></span>
    - <span data-ttu-id="4063b-149">Revisione obbligatoria (ovvero revisione della disposizione)</span><span class="sxs-lookup"><span data-stu-id="4063b-149">Review required (aka Disposition review)</span></span>

![Impostazioni delle etichette nel piano file](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="4063b-151">Colonne dei descrittori del piano file delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="4063b-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="4063b-p107">È ora possibile includere altre informazioni nella configurazione delle etichette di conservazione. L’inserimento di descrittori del piano file nelle etichette di conservazione migliora la gestibilità e l'organizzazione del piano file.</span><span class="sxs-lookup"><span data-stu-id="4063b-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="4063b-p108">Per iniziare, la gestione del piano file fornisce alcuni valori predefiniti per: funzione/reparto, categoria, tipo di autorità e disposizione/citazione. È possibile aggiungere nuovi valori al descrittore del piano file quando si crea o si modifica un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="4063b-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="4063b-156">Ecco una visualizzazione del passaggio dei descrittori del piano file quando si crea o modifica un'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="4063b-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Descrittori del piano file](media/file-plan-descriptors.png)

<span data-ttu-id="4063b-158">Ecco una visualizzazione delle colonne dei descrittori del piano file nella scheda etichette della gestione del piano file.</span><span class="sxs-lookup"><span data-stu-id="4063b-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="4063b-160">Esportare tutte le etichette di conservazione esistenti per analizzare e/o eseguire le revisioni offline</span><span class="sxs-lookup"><span data-stu-id="4063b-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="4063b-161">Dalla gestione del piano file, è possibile esportare i dettagli di tutte le etichette di conservazione in un file CSV per agevolare le analisi di conformità periodiche con le parti interessate responsabili della governance dei dati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4063b-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="4063b-162">Per esportare tutte le etichette di conservazione, passare a **gestione del piano file** \> **azioni del piano file** \> **esporta etichette**.</span><span class="sxs-lookup"><span data-stu-id="4063b-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Opzione per esportare il piano file](media/file-plan-export-labels-option.png)

<span data-ttu-id="4063b-164">Verrà aperto un file CSV che contiene tutte le etichette di conservazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="4063b-164">A \*.csv file containing all existing retention labels will open.</span></span>

![File CSV con tutte le etichette di conservazione](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="4063b-166">Importare le etichette di conservazione nel piano file</span><span class="sxs-lookup"><span data-stu-id="4063b-166">Import labels into your file plan</span></span>

<span data-ttu-id="4063b-167">Dalla gestione del piano file, è possibile importare in blocco nuove etichette di conservazione nonché modificare le etichette di conservazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="4063b-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="4063b-168">Per importare nuove etichette di conservazione e aggiornare le etichette di conservazione esistenti, passare a **gestione del piano file** \> **azioni del piano file** \> **importa etichette**.</span><span class="sxs-lookup"><span data-stu-id="4063b-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Opzione per importare il piano file](media/file-plan-import-labels-option.png)

![Opzione per scaricare un modello di piano file vuoto](media/file-plan-blank-template-option.png)

<span data-ttu-id="4063b-171">Scaricare un modello vuoto (o creare a partire da un'esportazione del piano file corrente).</span><span class="sxs-lookup"><span data-stu-id="4063b-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Modello di piano file vuoto aperto in Excel](media/file-plan-blank-template.png)

<span data-ttu-id="4063b-173">Compilare il modello.</span><span class="sxs-lookup"><span data-stu-id="4063b-173">Fill-out the template.</span></span> <span data-ttu-id="4063b-174">Questa tabella fornisce valori validi.</span><span class="sxs-lookup"><span data-stu-id="4063b-174">This table provides valid values.</span></span>

|<span data-ttu-id="4063b-175">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="4063b-175">**Property**</span></span>|<span data-ttu-id="4063b-176">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4063b-176">**Type**</span></span>|<span data-ttu-id="4063b-177">**Valori validi**</span><span class="sxs-lookup"><span data-stu-id="4063b-177">**Valid values**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4063b-178">LabelName</span><span class="sxs-lookup"><span data-stu-id="4063b-178">LabelName</span></span>|<span data-ttu-id="4063b-179">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-179">String</span></span>|<span data-ttu-id="4063b-180">Se il valore contiene degli spazi, è necessario racchiuderlo tra virgolette (").</span><span class="sxs-lookup"><span data-stu-id="4063b-180">If the value contains spaces, enclose the value in quotation marks (").</span></span>|
|<span data-ttu-id="4063b-181">Commento</span><span class="sxs-lookup"><span data-stu-id="4063b-181">Comment</span></span>|<span data-ttu-id="4063b-182">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-182">String</span></span>|<span data-ttu-id="4063b-183">Se il valore contiene degli spazi, è necessario racchiuderlo tra virgolette (").</span><span class="sxs-lookup"><span data-stu-id="4063b-183">If the value contains spaces, enclose the value in quotation marks (").</span></span> |
|<span data-ttu-id="4063b-184">Note</span><span class="sxs-lookup"><span data-stu-id="4063b-184">Notes</span></span>|<span data-ttu-id="4063b-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-185">String</span></span>|<span data-ttu-id="4063b-186">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-186">Custom</span></span>|
|<span data-ttu-id="4063b-187">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="4063b-187">IsRecordLabel</span></span>|<span data-ttu-id="4063b-188">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-188">String</span></span>|<span data-ttu-id="4063b-189">$true: L'etichetta è un'etichetta record.</span><span class="sxs-lookup"><span data-stu-id="4063b-189">The label is a record label.</span></span></br><span data-ttu-id="4063b-190">$false: L'etichetta non è un'etichetta record.</span><span class="sxs-lookup"><span data-stu-id="4063b-190">The label isn't a record label.</span></span> <span data-ttu-id="4063b-191">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4063b-191">This is the default value.</span></span>|
|<span data-ttu-id="4063b-192">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="4063b-192">RetentionAction</span></span>|<span data-ttu-id="4063b-193">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-193">String</span></span>|<span data-ttu-id="4063b-194">Elimina</span><span class="sxs-lookup"><span data-stu-id="4063b-194">Delete</span></span></br><span data-ttu-id="4063b-195">Conserva</span><span class="sxs-lookup"><span data-stu-id="4063b-195">Keep</span></span></br><span data-ttu-id="4063b-196">KeepAndDelete</span><span class="sxs-lookup"><span data-stu-id="4063b-196">KeepAndDelete</span></span> |
|<span data-ttu-id="4063b-197">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="4063b-197">RetentionDuration</span></span>|<span data-ttu-id="4063b-198">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-198">String</span></span>|<span data-ttu-id="4063b-199">La proprietà specifica per quanti giorni mantenere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="4063b-199">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="4063b-200">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4063b-200">Valid values are:</span></span></br><span data-ttu-id="4063b-201">Un numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="4063b-201">A positive integer.</span></span></br><span data-ttu-id="4063b-202">Il valore è illimitato.</span><span class="sxs-lookup"><span data-stu-id="4063b-202">The default value is unlimited.</span></span>|
|<span data-ttu-id="4063b-203">RetentionType</span><span class="sxs-lookup"><span data-stu-id="4063b-203">RetentionType</span></span>|<span data-ttu-id="4063b-204">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-204">String</span></span>|<span data-ttu-id="4063b-205">La proprietà specifica se la durata del periodo di conservazione è stata calcolata a partire dalla data di creazione del contenuto, dalla data etichettata (contrassegnata) o dalla data dell'ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="4063b-205">The RetentionType parameter specifies whether the retention duration is calculated  from the content creation date, tagged date, or last modification date.</span></span> <span data-ttu-id="4063b-206">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4063b-206">Valid values are:</span></span></br><span data-ttu-id="4063b-207">CreationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="4063b-207">CreationAgeInDays</span></span></br><span data-ttu-id="4063b-208">EventAgeInDays</span><span class="sxs-lookup"><span data-stu-id="4063b-208">EventAgeInDays</span></span></br><span data-ttu-id="4063b-209">ModificationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="4063b-209">ModificationAgeInDays</span></span></br><span data-ttu-id="4063b-210">TaggedAgeInDays</span><span class="sxs-lookup"><span data-stu-id="4063b-210">TaggedAgeInDays</span></span> |
|<span data-ttu-id="4063b-211">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="4063b-211">ReviewerEmail</span></span>|<span data-ttu-id="4063b-212">SmtpAddress[]</span><span class="sxs-lookup"><span data-stu-id="4063b-212">PARAMVALUE: SmtpAddress[]</span></span>|<span data-ttu-id="4063b-213">Questa proprietà consente di specificare l'indirizzo di posta elettronica del revisore per le azioni di conservazione Delete e KeepAndDelete.</span><span class="sxs-lookup"><span data-stu-id="4063b-213">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="4063b-214">È possibile indicare più indirizzi di posta elettronica separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="4063b-214">You can specify multiple email addresses separated by commas.</span></span>|
|<span data-ttu-id="4063b-215">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="4063b-215">ReferenceId</span></span>|<span data-ttu-id="4063b-216">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-216">String</span></span>|<span data-ttu-id="4063b-217">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-217">Custom</span></span>|
|<span data-ttu-id="4063b-218">Departmentname</span><span class="sxs-lookup"><span data-stu-id="4063b-218">DepartmentName</span></span>|<span data-ttu-id="4063b-219">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-219">String</span></span>|<span data-ttu-id="4063b-220">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-220">Custom</span></span>|
|<span data-ttu-id="4063b-221">Categoria</span><span class="sxs-lookup"><span data-stu-id="4063b-221">Category</span></span>|<span data-ttu-id="4063b-222">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-222">String</span></span>|<span data-ttu-id="4063b-223">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-223">Custom</span></span>|
|<span data-ttu-id="4063b-224">Sottocategoria</span><span class="sxs-lookup"><span data-stu-id="4063b-224">SubCategory</span></span>|<span data-ttu-id="4063b-225">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-225">String</span></span>|<span data-ttu-id="4063b-226">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-226">Custom</span></span>|
|<span data-ttu-id="4063b-227">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="4063b-227">AuthorityType</span></span>|<span data-ttu-id="4063b-228">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-228">String</span></span>|<span data-ttu-id="4063b-229">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-229">Custom</span></span>|
|<span data-ttu-id="4063b-230">CitationName</span><span class="sxs-lookup"><span data-stu-id="4063b-230">CitationName</span></span>|<span data-ttu-id="4063b-231">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-231">String</span></span>|<span data-ttu-id="4063b-232">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-232">Custom</span></span>|
|<span data-ttu-id="4063b-233">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="4063b-233">CitationUrl</span></span>|<span data-ttu-id="4063b-234">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-234">String</span></span>|<span data-ttu-id="4063b-235">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-235">Custom</span></span>|
|<span data-ttu-id="4063b-236">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="4063b-236">CitationJurisdiction</span></span>|<span data-ttu-id="4063b-237">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-237">String</span></span>|<span data-ttu-id="4063b-238">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-238">Custom</span></span>|
|<span data-ttu-id="4063b-239">Normativa</span><span class="sxs-lookup"><span data-stu-id="4063b-239">Regulatory</span></span>|<span data-ttu-id="4063b-240">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-240">String</span></span>|<span data-ttu-id="4063b-241">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="4063b-241">Custom</span></span>|
|<span data-ttu-id="4063b-242">EventType</span><span class="sxs-lookup"><span data-stu-id="4063b-242">EventType</span></span>|<span data-ttu-id="4063b-243">Stringa</span><span class="sxs-lookup"><span data-stu-id="4063b-243">String</span></span>|<span data-ttu-id="4063b-244">Questa proprietà specifica la regola di conservazione associata all'etichetta.</span><span class="sxs-lookup"><span data-stu-id="4063b-244">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="4063b-245">È possibile utilizzare qualsiasi valore che identifichi la regola in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="4063b-245">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="4063b-246">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4063b-246">For example:</span></span></br><span data-ttu-id="4063b-247">Nome</span><span class="sxs-lookup"><span data-stu-id="4063b-247">Name</span></span></br><span data-ttu-id="4063b-248">Nome distinto (DN)</span><span class="sxs-lookup"><span data-stu-id="4063b-248">Distinguished name (DN)</span></span></br><span data-ttu-id="4063b-249">GUID</span><span class="sxs-lookup"><span data-stu-id="4063b-249">GUID</span></span> </br><span data-ttu-id="4063b-250">È possibile usare il cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/it-IT/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) per visualizzare le regole di conservazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="4063b-250">You can use the [Get-DataEncryptionPolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available policies.</span></span>|

![Modello del piano file compilato con le informazioni](media/file-plan-filled-out-template.png)

<span data-ttu-id="4063b-252">Caricare il modello compilato e la gestione del piano file convaliderà le voci e visualizzerà le statistiche di importazione.</span><span class="sxs-lookup"><span data-stu-id="4063b-252">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Statistiche di importazione del piano file](media/file-plan-import-statistics.png)

<span data-ttu-id="4063b-254">Se è presente un errore di convalida, l'importazione del piano file continuerà a convalidare ogni voce nel file di importazione e visualizzerà tutti gli errori che fanno riferimento a numeri di linea o riga nel file di importazione, copierà i risultati degli errori visualizzati in modo che sia possibile facilmente tornare al file di importazione e correggere gli errori.</span><span class="sxs-lookup"><span data-stu-id="4063b-254">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="4063b-255">Al termine dell'importazione, tornare alla gestione del piano file per associare le nuove etichette di conservazione ai criteri nuovi o esistenti delle etichette di conservazione.</span><span class="sxs-lookup"><span data-stu-id="4063b-255">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Opzione per pubblicare le etichette](media/file-plan-publish-labels-option.png)

