---
title: Risolvere le vulnerabilità con la gestione delle minacce e delle vulnerabilità
description: Correggere i punti deboli della sicurezza individuati tramite suggerimenti sulla sicurezza e creare eccezioni, se necessario, nella gestione delle minacce e delle vulnerabilità.
keywords: microsoft defender atp tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0a0f70d81c3060f14f917cac49851af2e9dae210
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068685"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="aecda-104">Risolvere le vulnerabilità con la gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="aecda-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aecda-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="aecda-105">**Applies to:**</span></span>
- [<span data-ttu-id="aecda-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="aecda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="aecda-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="aecda-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="aecda-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aecda-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aecda-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aecda-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aecda-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="aecda-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="aecda-111">Richiesta di correzione</span><span class="sxs-lookup"><span data-stu-id="aecda-111">Request remediation</span></span>

<span data-ttu-id="aecda-112">La funzionalità di gestione delle minacce e delle vulnerabilità in Microsoft Defender for Endpoint colma il divario tra amministratori IT e sicurezza attraverso il flusso di lavoro delle richieste di correzione.</span><span class="sxs-lookup"><span data-stu-id="aecda-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="aecda-113">Gli amministratori della sicurezza come te possono richiedere all'amministratore IT di correggere una vulnerabilità dalle pagine **dei** suggerimenti per la sicurezza a Intune.</span><span class="sxs-lookup"><span data-stu-id="aecda-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="aecda-114">Abilitare la connessione a Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="aecda-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="aecda-115">Per usare questa funzionalità, abilitare le connessioni di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="aecda-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="aecda-116">In Microsoft Defender Security Center, passare a **Impostazioni**  >  **Generali**  >  **Funzionalità avanzate.**</span><span class="sxs-lookup"><span data-stu-id="aecda-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="aecda-117">Scorrere verso il basso e cercare **La connessione a Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="aecda-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="aecda-118">Per impostazione predefinita, l'interruttore è disattivato.</span><span class="sxs-lookup"><span data-stu-id="aecda-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="aecda-119">Attivare la connessione  **di Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="aecda-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="aecda-120">**Nota:** se la connessione intune è abilitata, si ottiene un'opzione per creare un'attività di sicurezza di Intune durante la creazione di una richiesta di correzione.</span><span class="sxs-lookup"><span data-stu-id="aecda-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="aecda-121">Questa opzione non viene visualizzata se la connessione non è impostata.</span><span class="sxs-lookup"><span data-stu-id="aecda-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="aecda-122">Per informazioni dettagliate, vedere Usare Intune per correggere [le vulnerabilità identificate da Microsoft Defender for Endpoint.](https://docs.microsoft.com/intune/atp-manage-vulnerabilities)</span><span class="sxs-lookup"><span data-stu-id="aecda-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="aecda-123">Passaggi della richiesta di correzione</span><span class="sxs-lookup"><span data-stu-id="aecda-123">Remediation request steps</span></span>

1. <span data-ttu-id="aecda-124">Vai al menu di spostamento per la gestione delle minacce e delle vulnerabilità in Microsoft Defender Security Center e seleziona [**Suggerimenti per la sicurezza.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="aecda-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="aecda-125">Selezionare un suggerimento per la sicurezza per cui si desidera richiedere la correzione e quindi selezionare **Opzioni di correzione.**</span><span class="sxs-lookup"><span data-stu-id="aecda-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="aecda-126">Compila il modulo, inclusi gli elementi per cui stai richiedendo la correzione, i gruppi di dispositivi applicabili, la priorità, la data di scadenza e le note facoltative.</span><span class="sxs-lookup"><span data-stu-id="aecda-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="aecda-127">Se si sceglie l'opzione di correzione "attenzione necessaria", la selezione di una data di scadenza non sarà disponibile perché non è disponibile alcuna azione specifica.</span><span class="sxs-lookup"><span data-stu-id="aecda-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="aecda-128">Selezionare **Invia richiesta**.</span><span class="sxs-lookup"><span data-stu-id="aecda-128">Select **Submit request**.</span></span> <span data-ttu-id="aecda-129">L'invio di una richiesta di correzione crea un elemento dell'attività di correzione all'interno della gestione delle minacce e delle vulnerabilità, che può essere utilizzato per monitorare lo stato di avanzamento della correzione per questo suggerimento.</span><span class="sxs-lookup"><span data-stu-id="aecda-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="aecda-130">In questo modo non verrà attivata una correzione o non verranno applicate modifiche ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="aecda-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="aecda-131">Informare l'amministratore IT della nuova richiesta e chiedere loro di accedere a Intune per approvare o rifiutare la richiesta e avviare la distribuzione di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aecda-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="aecda-132">Passare alla [**pagina Correzione**](tvm-remediation.md) per visualizzare lo stato della richiesta di correzione.</span><span class="sxs-lookup"><span data-stu-id="aecda-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="aecda-133">Se vuoi controllare come viene visualizzato il ticket in Intune, vedi Usare Intune per correggere le vulnerabilità identificate [da Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="aecda-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="aecda-134">Se la richiesta prevede la correzione di più di 10.000 dispositivi, possiamo inviare solo 10.000 dispositivi per la correzione a Intune.</span><span class="sxs-lookup"><span data-stu-id="aecda-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="aecda-135">Dopo che i punti deboli della sicurezza informatica [](tvm-security-recommendation.md)dell'organizzazione sono stati identificati e mappati a consigli sulla sicurezza utilizzabili, iniziare a creare attività di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="aecda-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="aecda-136">È possibile creare attività tramite l'integrazione con Microsoft Intune in cui vengono creati i ticket di correzione.</span><span class="sxs-lookup"><span data-stu-id="aecda-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="aecda-137">Ridurre l'esposizione dell'organizzazione dalle vulnerabilità e aumentare la configurazione della sicurezza corredando i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="aecda-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="aecda-138">Visualizzare le attività di correzione</span><span class="sxs-lookup"><span data-stu-id="aecda-138">View your remediation activities</span></span>

<span data-ttu-id="aecda-139">Quando invii una richiesta di correzione dalla pagina Suggerimenti per la sicurezza, avvia un'attività di correzione.</span><span class="sxs-lookup"><span data-stu-id="aecda-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="aecda-140">Viene creata un'attività di sicurezza che può essere  monitorata nella pagina di correzione della gestione delle minacce e delle vulnerabilità e viene creato un ticket di correzione in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="aecda-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="aecda-141">Se hai scelto l'opzione di correzione "attenzione necessaria", non ci saranno barre di avanzamento, stato del ticket o data di scadenza poiché non è possibile monitorare alcuna azione effettiva.</span><span class="sxs-lookup"><span data-stu-id="aecda-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="aecda-142">Una volta visualizzata la pagina Correzione, selezionare l'attività di correzione che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="aecda-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="aecda-143">È possibile seguire i passaggi di correzione, tenere traccia dello stato, visualizzare il suggerimento correlato, esportare in CSV o contrassegnare come completato.</span><span class="sxs-lookup"><span data-stu-id="aecda-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="aecda-144">![Esempio della pagina Correzione, con un'attività di correzione selezionata e il riquadro a comparsa dell'attività che elenca la descrizione, gli strumenti di gestione dei dispositivi e dei servizi IT e lo stato di avanzamento della correzione dei dispositivi.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="aecda-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="aecda-145">Esiste un periodo di conservazione di 180 giorni per le attività di correzione completate.</span><span class="sxs-lookup"><span data-stu-id="aecda-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="aecda-146">Per mantenere le prestazioni ottimali della pagina di correzione, l'attività di correzione verrà rimossa 6 mesi dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="aecda-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="aecda-147">Completato per colonna</span><span class="sxs-lookup"><span data-stu-id="aecda-147">Completed by column</span></span>

<span data-ttu-id="aecda-148">Tenere traccia di chi ha chiuso l'attività di correzione con la colonna "Completato da" nella pagina Correzione.</span><span class="sxs-lookup"><span data-stu-id="aecda-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="aecda-149">**Indirizzo di posta** elettronica : Il messaggio di posta elettronica della persona che ha completato manualmente l'attività</span><span class="sxs-lookup"><span data-stu-id="aecda-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="aecda-150">**Conferma del sistema:** l'attività è stata completata automaticamente (tutti i dispositivi corretti)</span><span class="sxs-lookup"><span data-stu-id="aecda-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="aecda-151">**N/D:** le informazioni non sono disponibili perché non si sa come è stata completata questa attività precedente</span><span class="sxs-lookup"><span data-stu-id="aecda-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Creato da e completato da colonne con due righe.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="aecda-154">Principali attività di correzione nel dashboard</span><span class="sxs-lookup"><span data-stu-id="aecda-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="aecda-155">Visualizzare **le principali attività di correzione** nel dashboard di gestione delle minacce e delle [vulnerabilità.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="aecda-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="aecda-156">Selezionare una delle voci per passare alla **pagina Correzione.**</span><span class="sxs-lookup"><span data-stu-id="aecda-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="aecda-157">È possibile contrassegnare l'attività di correzione come completata dopo la correzione dell'attività da parte del team di amministrazione IT.</span><span class="sxs-lookup"><span data-stu-id="aecda-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Esempio di scheda Attività di correzione principali con una tabella in cui sono elencate le attività principali generate dai suggerimenti per la sicurezza.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="aecda-159">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="aecda-159">Related articles</span></span>

- [<span data-ttu-id="aecda-160">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="aecda-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="aecda-161">Dashboard</span><span class="sxs-lookup"><span data-stu-id="aecda-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="aecda-162">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="aecda-162">Security recommendations</span></span>](tvm-security-recommendation.md)