---
title: Risolvere le vulnerabilità con gestione di minacce e vulnerabilità
description: Correggere i punti deboli della sicurezza individuati tramite suggerimenti per la sicurezza e creare eccezioni, se necessario, in gestione di minacce e vulnerabilità.
keywords: Microsoft Defender for Endpoint tvm remediation, Microsoft Defender for Endpoint tvm, gestione di minacce e vulnerabilità, threat & gestione delle vulnerabilità, threat & gestione delle vulnerabilità remediation, tvm remediation intune, tvm remediation sccm
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
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840912"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>Risolvere le vulnerabilità con gestione di minacce e vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Minaccia e gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>Richiesta di correzione

La gestione di minacce e vulnerabilità in Microsoft Defender for Endpoint colma il divario tra gli amministratori IT e della sicurezza attraverso il flusso di lavoro delle richieste di correzione. Gli amministratori della sicurezza come te possono richiedere all'amministratore IT di correggere una vulnerabilità dalle pagine **dei** suggerimenti per la sicurezza a Intune.

### <a name="enable-microsoft-intune-connection"></a>Abilitare Microsoft Intune connessione

Per usare questa funzionalità, abilitare le connessioni Microsoft Intune rete. Nella finestra Microsoft Defender Security Center, passare a **Impostazioni**  >  **Funzionalità avanzate**  >  **generali.** Scorrere verso il basso e cercare Microsoft Intune **connessione**. Per impostazione predefinita, l'interruttore è disattivato. Attivare la connessione Microsoft Intune **attiva.** 

**Nota:** se la connessione intune è abilitata, si ottiene un'opzione per creare un'attività di sicurezza di Intune durante la creazione di una richiesta di correzione. Questa opzione non viene visualizzata se la connessione non è impostata.

Per informazioni dettagliate, vedere Usare Intune per correggere [le vulnerabilità identificate da Microsoft Defender for Endpoint.](/intune/atp-manage-vulnerabilities)

### <a name="remediation-request-steps"></a>Passaggi della richiesta di correzione

1. Vai al menu gestione di minacce e vulnerabilità navigazione nella Microsoft Defender Security Center e seleziona [**Suggerimenti per la sicurezza.**](tvm-security-recommendation.md)

2. Selezionare un suggerimento per la sicurezza per cui si desidera richiedere la correzione e quindi selezionare **Opzioni di correzione.**

3. Compila il modulo, inclusi gli elementi per cui stai richiedendo la correzione, i gruppi di dispositivi applicabili, la priorità, la data di scadenza e le note facoltative.
    1. Se si sceglie l'opzione di correzione "attenzione necessaria", la selezione di una data di scadenza non sarà disponibile perché non è disponibile alcuna azione specifica.

4. Selezionare **Invia richiesta**. L'invio di una richiesta di correzione crea un elemento attività di correzione all'interno di gestione di minacce e vulnerabilità, che può essere usato per monitorare lo stato di avanzamento della correzione per questo suggerimento. In questo modo non verrà attivata una correzione o non verranno applicate modifiche ai dispositivi.

5. Informare l'amministratore IT della nuova richiesta e chiedere loro di accedere a Intune per approvare o rifiutare la richiesta e avviare la distribuzione di un pacchetto.

6. Passare alla [**pagina Correzione**](tvm-remediation.md) per visualizzare lo stato della richiesta di correzione.

Se vuoi controllare come viene visualizzato il ticket in Intune, vedi Usare Intune per correggere le vulnerabilità identificate [da Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) per informazioni dettagliate.

>[!NOTE]
>Se la richiesta prevede la correzione di più di 10.000 dispositivi, possiamo inviare solo 10.000 dispositivi per la correzione a Intune.

Dopo che i punti deboli della sicurezza informatica [](tvm-security-recommendation.md)dell'organizzazione sono stati identificati e mappati a consigli sulla sicurezza utilizzabili, iniziare a creare attività di sicurezza. È possibile creare attività tramite l'integrazione con Microsoft Intune in cui vengono creati i ticket di correzione.

Ridurre l'esposizione dell'organizzazione dalle vulnerabilità e aumentare la configurazione della sicurezza corredando i suggerimenti per la sicurezza.

## <a name="view-your-remediation-activities"></a>Visualizzare le attività di correzione

Quando invii una richiesta di correzione dalla pagina Suggerimenti per la sicurezza, avvia un'attività di correzione. Viene creata un'attività di sicurezza di cui  è possibile tenere traccia nella pagina di correzione gestione di minacce e vulnerabilità e viene creato un ticket di correzione in Microsoft Intune.

Se hai scelto l'opzione di correzione "attenzione necessaria", non ci saranno barre di avanzamento, stato del ticket o data di scadenza poiché non è possibile monitorare alcuna azione effettiva.

Una volta visualizzata la pagina Correzione, selezionare l'attività di correzione che si desidera visualizzare. È possibile seguire i passaggi di correzione, tenere traccia dello stato, visualizzare il suggerimento correlato, esportare in CSV o contrassegnare come completato.
![Esempio della pagina Correzione, con un'attività di correzione selezionata e il riquadro a comparsa dell'attività che elenca la descrizione, gli strumenti di gestione dei dispositivi e dei servizi IT e lo stato di avanzamento della correzione dei dispositivi.](images/remediation_flyouteolsw.png)

>[!NOTE]
> Esiste un periodo di conservazione di 180 giorni per le attività di correzione completate. Per mantenere le prestazioni ottimali della pagina di correzione, l'attività di correzione verrà rimossa 6 mesi dopo il completamento.

### <a name="completed-by-column"></a>Completato per colonna

Tenere traccia di chi ha chiuso l'attività di correzione con la colonna "Completato da" nella pagina Correzione.

- **Indirizzo di posta** elettronica : Il messaggio di posta elettronica della persona che ha completato manualmente l'attività
- **Conferma del sistema:** l'attività è stata completata automaticamente (tutti i dispositivi corretti)
- **N/D:** le informazioni non sono disponibili perché non si sa come è stata completata questa attività precedente

![Creato da e completato da colonne con due righe. Una riga completata da ha un esempio di un messaggio di posta elettronica, l'altra riga indica la conferma del sistema.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a>Principali attività di correzione nel dashboard

Visualizzare **le principali attività di correzione** nel dashboard di [gestione di minacce e vulnerabilità.](tvm-dashboard-insights.md) Selezionare una delle voci per passare alla **pagina Correzione.** È possibile contrassegnare l'attività di correzione come completata dopo la correzione dell'attività da parte del team di amministrazione IT.

![Esempio di scheda Attività di correzione principali con una tabella in cui sono elencate le attività principali generate dai suggerimenti per la sicurezza.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle minacce gestione delle vulnerabilità sicurezza](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)