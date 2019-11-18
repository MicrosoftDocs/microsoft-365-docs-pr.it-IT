---
title: Note sulla versione di Microsoft Compliance Manager
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager è uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal. Compliance Manager consente di monitorare, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.
ms.openlocfilehash: 1a490212b2275b9f297e2585e7242f5331d0fe56
ms.sourcegitcommit: 5c6c30ec5541d2fb77e53a1309db1fe7b75fc3e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2019
ms.locfileid: "38686371"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="b9295-104">Note sulla versione per Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b9295-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="b9295-105">L'anteprima pubblica di Compliance Manager fornisce l'accesso tempestivo alle funzionalità e agli aggiornamenti imminenti.</span><span class="sxs-lookup"><span data-stu-id="b9295-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="b9295-106">È possibile utilizzare lo strumento di [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) aggiornato nel [Service Trust Portal](https://servicetrust.microsoft.com) per tenere conto, assegnare e verificare le attività di conformità alle normative relative ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9295-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="b9295-107">Novità di Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b9295-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="b9295-108">**Accesso basato sui ruoli a Compliance Manager:** Il ruolo predefinito di **accesso Guest** è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="b9295-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="b9295-109">Per consentire a un utente di accedere a Compliance Manager, l'amministratore globale deve [assegnare a ciascun utente un'autorizzazione](compliance-manager-overview.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="b9295-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="b9295-110">**Punteggio di conformità aggiornato**: Il Punteggio di conformità include ora i punteggi per le azioni gestite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9295-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="b9295-111">Il punteggio aumenterà di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="b9295-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="b9295-112">**Elementi Actions:** Gli elementi azione sono ora singoli elementi e molti includono la raccolta di telemetria dall'API Microsoft Secure Score Graph.</span><span class="sxs-lookup"><span data-stu-id="b9295-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="b9295-113">Se possibile, le raccomandazioni per l'azione tecnica sono ora collegate alla pagina di configurazione applicabile nel servizio Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9295-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="b9295-114">**Gestione tenant:** Nuova interfaccia per la gestione dei nuovi elementi dati in Compliance Manager (Preview):</span><span class="sxs-lookup"><span data-stu-id="b9295-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="b9295-115">**Dimensioni:** Consente di visualizzare, aggiungere e personalizzare i metadati per i modelli, le valutazioni e gli elementi di azione che consentono di creare pivot personalizzati per i filtri.</span><span class="sxs-lookup"><span data-stu-id="b9295-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="b9295-116">**Proprietari:** Specificare un proprietario per ogni elemento di azione.</span><span class="sxs-lookup"><span data-stu-id="b9295-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="b9295-117">**Azioni dei clienti:** Gestire l'elenco completo degli elementi delle azioni inclusi in Compliance Manager (Preview) e abilitare/disabilitare il monitoraggio del Punteggio sicuro per gli elementi azione integrati con Secure score.</span><span class="sxs-lookup"><span data-stu-id="b9295-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="b9295-118">Problemi noti in Compliance Manager (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b9295-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="b9295-119">Nelle sezioni seguenti vengono illustrati i problemi noti da risolvere nelle prossime versioni di Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="b9295-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="b9295-120">Punteggio di conformità</span><span class="sxs-lookup"><span data-stu-id="b9295-120">Compliance Score</span></span>

- <span data-ttu-id="b9295-121">Per gli elementi azione contrassegnati come **non nell'ambito**, il punteggio assegnato all'elemento azione non è escluso dal calcolo del Punteggio di conformità.</span><span class="sxs-lookup"><span data-stu-id="b9295-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the compliance score calculation.</span></span> <span data-ttu-id="b9295-122">Gli elementi azione contrassegnati **non nell'ambito** non aumentano il Punteggio di conformità.</span><span class="sxs-lookup"><span data-stu-id="b9295-122">Action Items marked **Not in Scope** do not increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="b9295-123">Secure Score</span><span class="sxs-lookup"><span data-stu-id="b9295-123">Secure Score</span></span>

- <span data-ttu-id="b9295-124">I risultati del Punteggio sicuro non sono disponibili per alcuni elementi di azioni in determinate sottoscrizioni di Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9295-124">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="b9295-125">**Non è stato possibile rilevare** il risultato del Punteggio sicuro in questi casi.</span><span class="sxs-lookup"><span data-stu-id="b9295-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="b9295-126">A volte vengono restituiti risultati di Punteggio sicuro per i criteri corrispondenti e gli elementi di azione non completati.</span><span class="sxs-lookup"><span data-stu-id="b9295-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="b9295-127">Per i nuovi tenant, gli aggiornamenti del Punteggio sicuro per tutte le azioni vengono attivati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b9295-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="b9295-128">L'amministratore globale può impostare l'opzione di aggiornamento continuo per il Punteggio sicuro su disattivato, che disattiva gli aggiornamenti per tutte le azioni.</span><span class="sxs-lookup"><span data-stu-id="b9295-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
- <span data-ttu-id="b9295-129">Quando gli aggiornamenti del Punteggio sicuro sono attivati, le azioni vengono monitorate attivamente dal punteggio sicuro, anche se la data di test dell'azione non verrà aggiornata per riflettere il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b9295-129">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date will not be updated to reflect monitoring.</span></span>
- <span data-ttu-id="b9295-130">Quando vengono create nuove valutazioni, i punteggi includono automaticamente i punteggi dei controlli gestiti da Microsoft e l'integrazione del Punteggio sicuro.</span><span class="sxs-lookup"><span data-stu-id="b9295-130">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="b9295-131">Controlli gestiti da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9295-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="b9295-132">La data di test per i controlli gestiti da Microsoft non viene visualizzata nell'interfaccia utente, anche se inclusa nella valutazione.</span><span class="sxs-lookup"><span data-stu-id="b9295-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="b9295-133">Per visualizzare le informazioni relative alla data di test, è necessario esportare la valutazione.</span><span class="sxs-lookup"><span data-stu-id="b9295-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="b9295-134">Personalizzazione</span><span class="sxs-lookup"><span data-stu-id="b9295-134">Customization</span></span>

- <span data-ttu-id="b9295-135">L'aggiunta di controlli personalizzati consente di aggiungere un nuovo controllo a una famiglia di controlli esistente, ma non consente di aggiungere una nuova famiglia di controlli.</span><span class="sxs-lookup"><span data-stu-id="b9295-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="b9295-136">Questa versione non supporta il collegamento di elementi azione o l'aggiunta di elementi o controlli di azioni a una valutazione.</span><span class="sxs-lookup"><span data-stu-id="b9295-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="b9295-137">Se si crea un'azione personalizzata, non è possibile modificarla o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="b9295-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="b9295-138">Famiglie di controllo non visualizzate nelle valutazioni</span><span class="sxs-lookup"><span data-stu-id="b9295-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="b9295-139">Quando si importa un modello, tutte le valutazioni basate su tale modello riflettono tutte le famiglie di controlli facenti parte del modello.</span><span class="sxs-lookup"><span data-stu-id="b9295-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="b9295-140">Tuttavia, se si aggiungono nuove famiglie di controlli al modello, tutte le valutazioni esistenti non riflettono le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b9295-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="b9295-141">Solo le nuove valutazioni create al di fuori del modello aggiornato riflettono le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b9295-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="b9295-142">Modelli</span><span class="sxs-lookup"><span data-stu-id="b9295-142">Templates</span></span>

- <span data-ttu-id="b9295-143">Quando si crea un modello, è necessario includere le dimensioni per il **prodotto** e la **certificazione** per garantire che il modello venga visualizzato nel punteggio di conformità.</span><span class="sxs-lookup"><span data-stu-id="b9295-143">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="b9295-144">I modelli archiviati sono modificabili e non devono essere modificabili.</span><span class="sxs-lookup"><span data-stu-id="b9295-144">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="b9295-145">I modelli bloccati consentono la creazione di una valutazione quando non dovrebbero.</span><span class="sxs-lookup"><span data-stu-id="b9295-145">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="b9295-146">Il blocco di un modello deve impedire che venga utilizzato per creare valutazioni.</span><span class="sxs-lookup"><span data-stu-id="b9295-146">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="b9295-147">Esportazione</span><span class="sxs-lookup"><span data-stu-id="b9295-147">Export</span></span>

- <span data-ttu-id="b9295-148">L'esportazione dei modelli in JSON ha esito negativo quando lo stato del modello è impostato su **importazione** o **in attesa di approvazione**.</span><span class="sxs-lookup"><span data-stu-id="b9295-148">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="b9295-149">Browser supportati</span><span class="sxs-lookup"><span data-stu-id="b9295-149">Supported browsers</span></span>

- <span data-ttu-id="b9295-150">Sono supportate le versioni più recenti di Microsoft Edge, Chrome e Safari.</span><span class="sxs-lookup"><span data-stu-id="b9295-150">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="b9295-151">Possono verificarsi casi in cui i dati aggiornati non vengono visualizzati fino a quando il browser non viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b9295-151">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="b9295-152">La versione di anteprima di Microsoft Edge non è supportata ma non ha problemi noti.</span><span class="sxs-lookup"><span data-stu-id="b9295-152">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="b9295-153">Internet Explorer non è supportato.</span><span class="sxs-lookup"><span data-stu-id="b9295-153">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="b9295-154">Timeout sessione</span><span class="sxs-lookup"><span data-stu-id="b9295-154">Session timeout</span></span>

- <span data-ttu-id="b9295-155">Quando si verifica un timeout di una sessione, potrebbe essere visualizzato un errore "qualcosa è andato storto".</span><span class="sxs-lookup"><span data-stu-id="b9295-155">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="b9295-156">Per risolvere il caso, passare a [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) e accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b9295-156">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="b9295-157">Supporto lingue</span><span class="sxs-lookup"><span data-stu-id="b9295-157">Language support</span></span>

- <span data-ttu-id="b9295-158">Tutte le lingue non sono supportate per tutte le pagine Web.</span><span class="sxs-lookup"><span data-stu-id="b9295-158">All languages are not supported for all webpages.</span></span> <span data-ttu-id="b9295-159">Se la lingua locale non è supportata, visualizzarla in inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="b9295-159">If your local language is unsupported, view in US English.</span></span>