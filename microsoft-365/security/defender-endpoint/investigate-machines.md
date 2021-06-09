---
title: Analizzare i dispositivi nell'elenco Defender for Endpoint Devices
description: Analizzare i dispositivi interessati esaminando avvisi, informazioni sulla connessione di rete, aggiungendo tag e gruppi di dispositivi e controllando l'integrità del servizio.
keywords: dispositivi, tag, gruppi, endpoint, coda avvisi, avvisi, nome del dispositivo, dominio, ultimo visto, IP interno, avvisi attivi, categoria di minacce, filtro, ordinamento, esaminare avvisi, rete, connessione, tipo, furto di password, ransomware, exploit, minaccia, bassa gravità, integrità del servizio
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e64f17f2bedea89db1190e6c758c514f14fc3a68
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843579"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a>Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Analizzare i dettagli di un avviso generato su un dispositivo specifico per identificare altri comportamenti o eventi che potrebbero essere correlati all'avviso o all'ambito potenziale della violazione.

> [!NOTE]
> Come parte del processo di indagine o di risposta, puoi raccogliere un pacchetto di indagine da un dispositivo. Ecco come: Raccogliere [il pacchetto di indagine dai dispositivi](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).

Puoi fare clic sui dispositivi interessati ogni volta che li vedi nel portale per aprire un report dettagliato su tale dispositivo. I dispositivi interessati sono identificati nelle aree seguenti:

- [Elenco dispositivi](investigate-machines.md)
- [Coda di avvisi](alerts-queue.md)
- [Dashboard delle operazioni di sicurezza](security-operations-dashboard.md)
- Qualsiasi singolo avviso
- Qualsiasi visualizzazione dei dettagli dei singoli file
- Qualsiasi indirizzo IP o visualizzazione dei dettagli del dominio

Quando indaghi su un dispositivo specifico, vedrai:

- Dettagli dispositivo
- Azioni di risposta
- Schede (panoramica, avvisi, sequenza temporale, suggerimenti per la sicurezza, inventario software, vulnerabilità individuate, INDICATORI KPI mancanti)
- Schede (avvisi attivi, utenti connessi, valutazione della sicurezza)

![Immagine della visualizzazione del dispositivo](images/specific-device.png)

## <a name="device-details"></a>Dettagli dispositivo

La sezione dettagli dispositivo fornisce informazioni quali il dominio, il sistema operativo e lo stato di integrità del dispositivo. Se nel dispositivo è disponibile un pacchetto di analisi, vedrai un collegamento che ti consente di scaricare il pacchetto.

## <a name="response-actions"></a>Azioni di risposta

Le azioni di risposta vengono eseguite nella parte superiore di una pagina specifica del dispositivo e includono:

- Gestire i tag
- Isola dispositivo
- Limitare l'esecuzione dell'app
- Eseguire ricerca del virus
- Raccogliere un pacchetto di indagini
- Avviare la sessione di risposta in tempo reale
- Avviare un'indagine automatizzata
- Consultare un esperto di minacce
- Centro notifiche

Puoi eseguire azioni di risposta nel centro notifiche, in una pagina del dispositivo specifico o in una pagina di file specifica.

Per altre informazioni su come eseguire un'azione su un dispositivo, vedi [Eseguire un'azione di risposta in un dispositivo.](respond-machine-alerts.md)

Per ulteriori informazioni, vedere [Investigate user entities](investigate-user.md).

## <a name="tabs"></a>Schede

Le schede forniscono informazioni rilevanti sulla sicurezza e sulla prevenzione delle minacce relative al dispositivo. In ogni scheda è possibile personalizzare le  colonne visualizzate selezionando Personalizza colonne dalla barra sopra le intestazioni di colonna.

### <a name="overview"></a>Panoramica
Nella **scheda Panoramica** vengono visualizzate le [schede](#cards) per gli avvisi attivi, gli utenti connessi e la valutazione della sicurezza.

![Immagine della scheda Panoramica nella pagina del dispositivo](images/overview-device.png)

### <a name="alerts"></a>Avvisi

La **scheda** Avvisi fornisce un elenco di avvisi associati al dispositivo. Questo elenco è una versione [](alerts-queue.md)filtrata della coda avvisi e mostra una breve descrizione dell'avviso, della gravità (alto, medio, basso, informativo), dello stato nella coda (nuovo, in corso, risolto), classificazione (non impostato, falso avviso, avviso vero), stato dell'indagine, categoria dell'avviso, destinatario dell'avviso e ultima attività. È inoltre possibile filtrare gli avvisi.

![Immagine degli avvisi correlati al dispositivo](images/alerts-device.png)

Quando l'icona del cerchio a sinistra di un avviso è selezionata, viene visualizzato un riquadro a comparsa. Da questo pannello puoi gestire l'avviso e visualizzare altri dettagli, ad esempio il numero di incidente e i dispositivi correlati. È possibile selezionare più avvisi alla volta.

Per visualizzare una visualizzazione a pagina intera di un avviso, incluso il grafico degli eventi imprevisti e l'albero dei processi, selezionare il titolo dell'avviso.

### <a name="timeline"></a>Sequenza temporale

La **scheda** Sequenza temporale fornisce una visualizzazione cronologica degli eventi e degli avvisi associati che sono stati osservati nel dispositivo. In questo modo puoi correlare eventi, file e indirizzi IP in relazione al dispositivo.

La sequenza temporale consente inoltre di eseguire il drill-down in modo selettivo negli eventi che si sono verificati in un determinato periodo di tempo. Puoi visualizzare la sequenza temporale degli eventi che si sono verificati in un dispositivo in un periodo di tempo selezionato. Per controllare ulteriormente la visualizzazione, è possibile filtrare in base ai gruppi di eventi o personalizzare le colonne.

>[!NOTE]
> Per visualizzare gli eventi del firewall, è necessario abilitare il criterio di controllo, vedere [Audit Filtering Platform connection.](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
>Il firewall copre gli eventi seguenti
>
>- [5025](/windows/security/threat-protection/auditing/event-5025) - Servizio firewall arrestato
>- [5031](/windows/security/threat-protection/auditing/event-5031) - Applicazione bloccata dall'accettazione delle connessioni in ingresso sulla rete
>- [5157](/windows/security/threat-protection/auditing/event-5157) - Connessione bloccata

![Immagine della sequenza temporale del dispositivo con eventi](images/timeline-device.png)

Alcune delle funzionalità includono:

- Cercare eventi specifici
  - Usa la barra di ricerca per cercare eventi sequenza temporale specifici.
- Filtrare gli eventi da una data specifica
  - Selezionare l'icona del calendario in alto a sinistra della tabella per visualizzare gli eventi dell'ultimo giorno, settimana, 30 giorni o intervallo personalizzato. Per impostazione predefinita, la sequenza temporale del dispositivo è impostata per visualizzare gli eventi degli ultimi 30 giorni.
  - Usa la sequenza temporale per passare a un momento specifico evidenziando la sezione. Le frecce sulla sequenza temporale consentono di individuare indagini automatizzate
- Esportare eventi dettagliati della sequenza temporale del dispositivo
  - Esporta la sequenza temporale del dispositivo per la data corrente o un intervallo di date specificato fino a sette giorni.

Ulteriori dettagli su determinati eventi sono disponibili nella **sezione Informazioni** aggiuntive. Questi dettagli variano a seconda del tipo di evento, ad esempio: 

- Contenuto di Application Guard: l'evento del Web browser è stato limitato da un contenitore isolato
- Minaccia attiva rilevata: il rilevamento delle minacce si è verificato durante l'esecuzione della minaccia
- Correzione non riuscita: un tentativo di correzione della minaccia rilevata è stato richiamato ma non è riuscito
- Correzione riuscita: la minaccia rilevata è stata arrestata e pulita
- Avviso ignorato dall'utente: l'Windows Defender SmartScreen è stato ignorato e sostituito da un utente
- Rilevato script sospetto: è stato rilevato uno script potenzialmente dannoso in esecuzione
- Categoria di avviso: se l'evento ha generato un avviso, viene fornita la categoria di avviso ("Movimento laterale", ad esempio)

#### <a name="event-details"></a>Dettagli evento
Seleziona un evento per visualizzare i dettagli pertinenti su tale evento. Viene visualizzato un pannello per visualizzare informazioni generali sull'evento. Se applicabile e i dati sono disponibili, viene visualizzato anche un grafico che mostra le entità correlate e le relative relazioni.

Per esaminare ulteriormente l'evento e gli eventi correlati, è possibile eseguire rapidamente una [query](advanced-hunting-overview.md) di ricerca avanzata selezionando Cerca **eventi correlati.** La query restituirà l'evento selezionato e l'elenco di altri eventi che si sono verificati nello stesso momento nello stesso endpoint.

![Immagine del pannello dei dettagli dell'evento](images/event-details.png)

### <a name="security-recommendations"></a>Consigli sulla sicurezza

**I suggerimenti per** la sicurezza vengono generati da Microsoft Defender per la funzionalità di gestione delle [& delle](tvm-dashboard-insights.md) vulnerabilità di Microsoft Defender for Endpoint. La selezione di un suggerimento mostrerà un pannello in cui è possibile visualizzare dettagli pertinenti, ad esempio la descrizione del suggerimento e i potenziali rischi associati alla sua non applicazione. Per [informazioni dettagliate, vedere](tvm-security-recommendation.md) Consigli per la sicurezza.

![Immagine della scheda Suggerimenti per la sicurezza](images/security-recommendations-device.png)

### <a name="software-inventory"></a>Inventario software

La **scheda Inventario** software consente di visualizzare il software nel dispositivo, insieme a eventuali punti deboli o minacce. Se si seleziona il nome del software, verrà visualizzata la pagina dei dettagli del software in cui è possibile visualizzare i suggerimenti per la sicurezza, le vulnerabilità individuate, i dispositivi installati e la distribuzione delle versioni. Per [informazioni dettagliate, vedere Inventario](tvm-software-inventory.md) software

![Immagine della scheda inventario software](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a>Vulnerabilità individuate

La **scheda Vulnerabilità individuate** mostra il nome, la gravità e le informazioni dettagliate sulle minacce delle vulnerabilità individuate nel dispositivo. La selezione di vulnerabilità specifiche mostrerà una descrizione e dettagli.

![Immagine della scheda vulnerabilità individuate](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a>Indicatori KPI mancanti
Nella **scheda Blob** mancanti sono elencati gli aggiornamenti di sicurezza mancanti per il dispositivo.

![Immagine della scheda kb mancanti](images/missing-kbs-device.png)

## <a name="cards"></a>Schede

### <a name="active-alerts"></a>Avvisi attivi

La **scheda Azure Advanced Threat Protection** visualizza una panoramica generale degli avvisi relativi al dispositivo e al relativo livello di rischio, se è stata abilitata la funzionalità Microsoft Defender for Identity e sono presenti avvisi attivi. Ulteriori informazioni sono disponibili nel drill-down "Avvisi".

![Immagine della scheda avvisi attivi](images/risk-level-small.png)

>[!NOTE]
>Dovrai abilitare l'integrazione sia in Microsoft Defender for Identity che in Defender for Endpoint per usare questa funzionalità. In Defender for Endpoint puoi abilitare questa funzionalità nelle funzionalità avanzate. Per ulteriori informazioni su come abilitare le funzionalità avanzate, vedere [Attivare le funzionalità avanzate.](advanced-features.md)

### <a name="logged-on-users"></a>Utenti connessi

La **scheda Utenti connessi** mostra quanti utenti hanno effettuato l'accesso negli ultimi 30 giorni, insieme agli utenti più e meno frequenti. Se si seleziona il collegamento "Visualizza tutti gli utenti", verrà aperto il riquadro dei dettagli, in cui vengono visualizzate informazioni quali il tipo di utente, il tipo di accesso e la data e l'ultima visualizzazione dell'utente. Per ulteriori informazioni, vedere [Investigate user entities](investigate-user.md).

![Immagine del riquadro dei dettagli utente](images/logged-on-users.png)

### <a name="security-assessments"></a>Valutazioni sulla sicurezza

La **scheda Valutazioni della sicurezza** mostra il livello complessivo di esposizione, i consigli per la sicurezza, il software installato e le vulnerabilità individuate. Il livello di esposizione di un dispositivo è determinato dall'impatto cumulativo dei consigli di sicurezza in sospeso.

![Immagine della scheda di valutazione della sicurezza](images/security-assessments.png)

## <a name="related-topics"></a>Argomenti correlati

- [Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts](alerts-queue.md)
- [Gestire gli avvisi di Microsoft Defender for Endpoint](manage-alerts.md)
- [Analizzare gli avvisi di Microsoft Defender for Endpoint](investigate-alerts.md)
- [Analizzare un file associato a un avviso di Defender for Endpoint](investigate-files.md)
- [Analizzare un indirizzo IP associato a un avviso Defender for Endpoint](investigate-ip.md)
- [Analizzare un dominio associato a un avviso Defender for Endpoint](investigate-domain.md)
- [Analizzare un account utente in Defender for Endpoint](investigate-user.md)
- [Suggerimenti per la sicurezza](tvm-security-recommendation.md)
- [Inventario software](tvm-software-inventory.md)
