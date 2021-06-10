---
title: Gestire gli avvisi di Microsoft Defender for Endpoint
description: Modificare lo stato degli avvisi, creare regole di eliminazione per nascondere gli avvisi, inviare commenti ed esaminare la cronologia delle modifiche per i singoli avvisi con il menu Gestisci avviso.
keywords: gestire avvisi, gestire, avvisi, stato, nuovo, in corso, risolto, risolvere avvisi, eliminare, sopprimere, regole, contesto, cronologia, commenti, modifiche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187002"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="7b923-104">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7b923-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7b923-105">**Applies to:**</span></span>
- [<span data-ttu-id="7b923-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7b923-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b923-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="7b923-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7b923-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7b923-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7b923-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="7b923-110">Defender for Endpoint ti informa di possibili eventi dannosi, attributi e informazioni contestuali tramite avvisi.</span><span class="sxs-lookup"><span data-stu-id="7b923-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="7b923-111">Un riepilogo dei nuovi avvisi viene visualizzato nel **dashboard Operazioni** di sicurezza ed è possibile accedere a tutti gli avvisi nella **coda avvisi.**</span><span class="sxs-lookup"><span data-stu-id="7b923-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="7b923-112">Puoi gestire gli avvisi selezionando un avviso nella coda **avvisi** o nella scheda **Avvisi** della pagina Dispositivo per un singolo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b923-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="7b923-113">Se si seleziona un avviso in una di queste posizioni, verrà visualizzato il **riquadro Gestione avvisi.**</span><span class="sxs-lookup"><span data-stu-id="7b923-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![Immagine del riquadro di gestione degli avvisi e della coda degli avvisi](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="7b923-115">Collegamento a un altro evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="7b923-115">Link to another incident</span></span>
<span data-ttu-id="7b923-116">È possibile creare un nuovo evento imprevisto dall'avviso o dal collegamento a un evento imprevisto esistente.</span><span class="sxs-lookup"><span data-stu-id="7b923-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="7b923-117">Assegnare avvisi</span><span class="sxs-lookup"><span data-stu-id="7b923-117">Assign alerts</span></span>
<span data-ttu-id="7b923-118">Se non è ancora stato assegnato un avviso, è possibile selezionare Assegna a **me** per assegnare l'avviso a se stessi.</span><span class="sxs-lookup"><span data-stu-id="7b923-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="7b923-119">Eliminare gli avvisi</span><span class="sxs-lookup"><span data-stu-id="7b923-119">Suppress alerts</span></span>
<span data-ttu-id="7b923-120">Potrebbero essere presenti scenari in cui è necessario eliminare la visualizzazione degli avvisi in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="7b923-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="7b923-121">Defender for Endpoint consente di creare regole di eliminazione per avvisi specifici noti come innocui, ad esempio strumenti o processi noti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b923-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="7b923-122">Le regole di eliminazione possono essere create da un avviso esistente.</span><span class="sxs-lookup"><span data-stu-id="7b923-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="7b923-123">Possono essere disabilitati e rienabledati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7b923-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="7b923-124">Quando viene creata, una regola di eliminazione avrà effetto dal momento in cui viene creata la regola.</span><span class="sxs-lookup"><span data-stu-id="7b923-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="7b923-125">La regola non influirà sugli avvisi esistenti già presenti nella coda, prima della creazione della regola.</span><span class="sxs-lookup"><span data-stu-id="7b923-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="7b923-126">La regola verrà applicata solo agli avvisi che soddisfano le condizioni impostate dopo la creazione della regola.</span><span class="sxs-lookup"><span data-stu-id="7b923-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="7b923-127">Per una regola di eliminazione è possibile scegliere tra due contesti:</span><span class="sxs-lookup"><span data-stu-id="7b923-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="7b923-128">**Elimina avviso in questo dispositivo**</span><span class="sxs-lookup"><span data-stu-id="7b923-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="7b923-129">**Eliminare l'avviso nell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="7b923-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="7b923-130">Il contesto della regola consente di personalizzare gli elementi che vengono visualizzati nel portale e di verificare che nel portale siano visualizzati solo avvisi di sicurezza reali.</span><span class="sxs-lookup"><span data-stu-id="7b923-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="7b923-131">È possibile utilizzare gli esempi riportati nella tabella seguente per scegliere il contesto per una regola di eliminazione:</span><span class="sxs-lookup"><span data-stu-id="7b923-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="7b923-132">**Contesto**</span><span class="sxs-lookup"><span data-stu-id="7b923-132">**Context**</span></span>                           | <span data-ttu-id="7b923-133">**Definizione**</span><span class="sxs-lookup"><span data-stu-id="7b923-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="7b923-134">**Scenari di esempio**</span><span class="sxs-lookup"><span data-stu-id="7b923-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7b923-135">**Elimina avviso in questo dispositivo**</span><span class="sxs-lookup"><span data-stu-id="7b923-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="7b923-136">Gli avvisi con lo stesso titolo di avviso e solo su quel dispositivo specifico verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="7b923-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="7b923-137">Tutti gli altri avvisi sul dispositivo non verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="7b923-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="7b923-138">Un ricercatore di sicurezza sta analizzando uno script dannoso usato per attaccare altri dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b923-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="7b923-139">Uno sviluppatore crea regolarmente script di PowerShell per il proprio team.</span><span class="sxs-lookup"><span data-stu-id="7b923-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="7b923-140">**Eliminare l'avviso nell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="7b923-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="7b923-141">Gli avvisi con lo stesso titolo di avviso su qualsiasi dispositivo verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="7b923-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="7b923-142">Uno strumento di amministrazione benigno viene utilizzato da tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b923-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="7b923-143">Eliminare un avviso e creare una nuova regola di eliminazione:</span><span class="sxs-lookup"><span data-stu-id="7b923-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="7b923-144">Creare regole personalizzate per controllare quando gli avvisi vengono eliminati o risolti.</span><span class="sxs-lookup"><span data-stu-id="7b923-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="7b923-145">È possibile controllare il contesto per l'eliminazione di un avviso specificando il titolo dell'avviso, l'indicatore di compromissione e le condizioni.</span><span class="sxs-lookup"><span data-stu-id="7b923-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="7b923-146">Dopo aver specificato il contesto, sarà possibile configurare l'azione e l'ambito dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="7b923-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="7b923-147">Seleziona l'avviso che vuoi eliminare.</span><span class="sxs-lookup"><span data-stu-id="7b923-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="7b923-148">Verrà visualizzato il **riquadro Gestione** avvisi.</span><span class="sxs-lookup"><span data-stu-id="7b923-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="7b923-149">Selezionare **Crea una regola di eliminazione.**</span><span class="sxs-lookup"><span data-stu-id="7b923-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="7b923-150">Puoi creare una condizione di eliminazione usando questi attributi.</span><span class="sxs-lookup"><span data-stu-id="7b923-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="7b923-151">Un operatore AND viene applicato tra ogni condizione, pertanto l'eliminazione viene eseguita solo se vengono soddisfatte tutte le condizioni.</span><span class="sxs-lookup"><span data-stu-id="7b923-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="7b923-152">File SHA1</span><span class="sxs-lookup"><span data-stu-id="7b923-152">File SHA1</span></span>
    * <span data-ttu-id="7b923-153">Nome file - Caratteri jolly supportati</span><span class="sxs-lookup"><span data-stu-id="7b923-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="7b923-154">Percorso cartella - Caratteri jolly supportati</span><span class="sxs-lookup"><span data-stu-id="7b923-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="7b923-155">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="7b923-155">IP address</span></span>
    * <span data-ttu-id="7b923-156">URL - Caratteri jolly supportati</span><span class="sxs-lookup"><span data-stu-id="7b923-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="7b923-157">Riga di comando - Caratteri jolly supportati</span><span class="sxs-lookup"><span data-stu-id="7b923-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="7b923-158">Selezionare **l'attivazione di IOC**.</span><span class="sxs-lookup"><span data-stu-id="7b923-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="7b923-159">Specificare l'azione e l'ambito dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="7b923-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="7b923-160">È possibile risolvere automaticamente un avviso o nasconderlo dal portale.</span><span class="sxs-lookup"><span data-stu-id="7b923-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="7b923-161">Gli avvisi risolti automaticamente verranno visualizzati nella sezione risolta della coda degli avvisi, della pagina di avviso e della sequenza temporale del dispositivo e verranno visualizzati come risolti nelle API defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b923-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="7b923-162">Gli avvisi contrassegnati come nascosti verranno eliminati dall'intero sistema, sia dagli avvisi associati al dispositivo che dal dashboard e non verranno trasmessi tra le API di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b923-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="7b923-163">Immettere un nome di regola e un commento.</span><span class="sxs-lookup"><span data-stu-id="7b923-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="7b923-164">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7b923-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="7b923-165">Visualizzare l'elenco delle regole di eliminazione</span><span class="sxs-lookup"><span data-stu-id="7b923-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="7b923-166">Nel riquadro di spostamento selezionare **Impostazioni**  >  **avviso.**</span><span class="sxs-lookup"><span data-stu-id="7b923-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="7b923-167">L'elenco delle regole di eliminazione mostra tutte le regole create dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b923-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="7b923-168">Per ulteriori informazioni sulla gestione delle regole di eliminazione, vedere [Manage suppression rules](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="7b923-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="7b923-169">Modificare lo stato di un avviso</span><span class="sxs-lookup"><span data-stu-id="7b923-169">Change the status of an alert</span></span>

<span data-ttu-id="7b923-170">È possibile categorizzare gli avvisi (come **Nuovo,** **In corso** o **Risolto)** modificandone lo stato durante l'avanzamento dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="7b923-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="7b923-171">Ciò consente di organizzare e gestire il modo in cui il team può rispondere agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="7b923-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="7b923-172">Ad esempio, un responsabile del team può esaminare tutti **i nuovi** avvisi e decidere di assegnarli alla **coda In** corso per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="7b923-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="7b923-173">In alternativa, il responsabile del team  potrebbe assegnare l'avviso alla coda Risolta se sa che l'avviso è benigno, proveniente da un dispositivo irrilevante (ad esempio un utente appartenente a un amministratore della sicurezza) o gestito tramite un avviso precedente.</span><span class="sxs-lookup"><span data-stu-id="7b923-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="7b923-174">Classificazione degli avvisi</span><span class="sxs-lookup"><span data-stu-id="7b923-174">Alert classification</span></span>
<span data-ttu-id="7b923-175">È possibile scegliere di non impostare una classificazione o di specificare se un avviso è un avviso vero o falso.</span><span class="sxs-lookup"><span data-stu-id="7b923-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="7b923-176">È importante fornire la classificazione del vero positivo/falso positivo.</span><span class="sxs-lookup"><span data-stu-id="7b923-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="7b923-177">Questa classificazione viene utilizzata per monitorare la qualità degli avvisi e rendere gli avvisi più accurati.</span><span class="sxs-lookup"><span data-stu-id="7b923-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="7b923-178">Il campo "determinazione" definisce una fedeltà aggiuntiva per una classificazione "vero positivo".</span><span class="sxs-lookup"><span data-stu-id="7b923-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="7b923-179">Aggiungere commenti e visualizzare la cronologia di un avviso</span><span class="sxs-lookup"><span data-stu-id="7b923-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="7b923-180">È possibile aggiungere commenti e visualizzare eventi cronologici relativi a un avviso per visualizzare le modifiche precedenti apportate all'avviso.</span><span class="sxs-lookup"><span data-stu-id="7b923-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="7b923-181">Ogni volta che viene apportata una modifica o un commento a un avviso, questa viene registrata nella sezione Commenti **e** cronologia.</span><span class="sxs-lookup"><span data-stu-id="7b923-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="7b923-182">I commenti aggiunti vengono visualizzati istantaneamente nel pannello.</span><span class="sxs-lookup"><span data-stu-id="7b923-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7b923-183">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7b923-183">Related topics</span></span>
- [<span data-ttu-id="7b923-184">Gestire le regole di eliminazione</span><span class="sxs-lookup"><span data-stu-id="7b923-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="7b923-185">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts</span><span class="sxs-lookup"><span data-stu-id="7b923-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="7b923-186">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="7b923-187">Analizzare un file associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="7b923-188">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="7b923-189">Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="7b923-190">Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="7b923-191">Analizzare un account utente in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b923-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
