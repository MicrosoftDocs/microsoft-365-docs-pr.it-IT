---
title: Profile del computer nel portale di sicurezza di Microsoft 365
description: Visualizzare i livelli di rischio e di esposizione per un dispositivo nell'organizzazione. Analizzare le minacce passate e presenti e proteggere il computer con gli aggiornamenti più recenti.
keywords: sicurezza, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Centro sicurezza, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Machine Page, Machine list, Machine profile
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895464"
---
# <a name="machine-profile-page"></a>Pagina del profilo del computer

Il portale di sicurezza di Microsoft 365 fornisce pagine del profilo del computer, in modo da poter valutare l'integrità e lo stato dei dispositivi sulla rete. Ogni pagina del profilo del computer contiene una vasta gamma di informazioni sul dispositivo.

È possibile esaminare informazioni approfondite sul software in esecuzione, sugli eventi o gli avvisi di sicurezza precedenti e presenti e trovare collegamenti a patch software rilevanti.

È inoltre possibile utilizzare il profilo del computer per eseguire attività comuni relative alla sicurezza e esaminare rapidamente i dettagli di base del dispositivo.

## <a name="navigating-the-machine-profile-page"></a>Esplorazione della pagina del profilo del computer

La pagina del profilo del computer è suddivisa in tre sezioni.

![Immagine della pagina del profilo del computer con (1) area della scheda (2) barra laterale e (3) azioni evidenziate in rosso](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

L'area di contenuto principale (1) contiene sette schede che è possibile passare per visualizzare diversi tipi di informazioni sul computer.

La barra laterale (2) elenca i dettagli di base del computer.

Esistono anche azioni di risposta disponibili in un'intestazione (3) prima della barra laterale e delle sezioni principali del contenuto. È possibile utilizzare le azioni in questa intestazione per eseguire attività comuni relative alla sicurezza.

## <a name="tabs-section"></a>Sezione tabulazioni

Le schede del profilo del computer consentono di alternare una panoramica dei dettagli sulla sicurezza del computer e delle tabelle che contengono un elenco di avvisi, una sequenza temporale, un elenco di suggerimenti per la sicurezza, un inventario software, un elenco di vulnerabilità individuate e mancanti KBs (aggiornamenti della sicurezza).

### <a name="overview-tab"></a>Scheda Panoramica

La scheda predefinita è **Overview**. In questo modo viene fornita una rapida occhiata ai fatti di sicurezza più importanti per il dispositivo.

![Immagine della scheda Panoramica per il profilo del computer](../../media/mtp-machine-profile/overview.png)

In questo articolo è possibile trovare un grafico del livello di rischio del dispositivo e gli avvisi attivi, tutti gli utenti attualmente connessi, un breve elenco di utenti più e meno frequenti e le valutazioni di sicurezza che illustrano il livello di esposizione del dispositivo, le raccomandazioni per la sicurezza, il software influenzato e vulnerabilità individuate.

### <a name="alerts-tab"></a>Scheda avvisi

La scheda **avvisi** contiene un elenco di avvisi che sono stati segnalati nel dispositivo.

![Immagine della scheda avvisi per il profilo del computer](../../media/mtp-machine-profile/alerts.png)

È possibile personalizzare il numero di elementi visualizzati, nonché le colonne visualizzate per ogni elemento. Il comportamento predefinito consiste nell'elencare 30 elementi per ogni pagina e con 11 colonne attivate per la visualizzazione.

Nelle colonne di questa scheda sono incluse informazioni sulla gravità del pericolo che ha attivato l'avviso, nonché lo stato, lo stato di indagine e l'utente a cui è stato assegnato l'avviso.

La colonna *entità* interessate si riferisce al computer (entità) di cui è in corso la visualizzazione, oltre a qualsiasi altro computer della rete interessato.

Se si seleziona un elemento da questo elenco, verrà aperto un collegamento all'avviso selezionato.

Questo elenco può essere filtrato in base a gravità, stato o assegnatario.

### <a name="timeline-tab"></a>Scheda sequenza temporale

Nella scheda **sequenza temporale** è incluso un grafico cronologico interattivo degli eventi generati nel dispositivo. Spostando l'area evidenziata del grafico, è possibile visualizzare gli eventi su intervalli diversi di tempo. È inoltre possibile digitare un intervallo di date personalizzato.

Di seguito è riportato un elenco di eventi per l'intervallo di date selezionato.

![Immagine della scheda sequenza temporale per il profilo del computer](../../media/mtp-machine-profile/timeline.png)

È possibile personalizzare il numero di elementi visualizzati e le colonne dell'elenco. Le colonne predefinite elencano l'ora dell'evento, l'utente attivo, il tipo di azione, le entità (processi) e altre informazioni sull'evento.

Se si seleziona un elemento dall'elenco, verrà aperto un riquadro a comparsa che visualizza un grafico entità eventi, mostrando i processi padre e figlio che hanno attivato l'evento.

Questo elenco può essere filtrato in base al tipo di evento specifico. ad esempio, eventi del registro di sistema o eventi dello Smart Screen.

### <a name="security-recommendations-tab"></a>Scheda suggerimenti per la sicurezza

La scheda consigli per la **sicurezza** elenca le operazioni che è possibile eseguire per proteggere il dispositivo. Se si seleziona un elemento di questo elenco, verrà aperto un riquadro a comparsa in cui è possibile ottenere istruzioni su come applicare il suggerimento.

![Immagine della scheda consigli per la sicurezza per il profilo del computer](../../media/mtp-machine-profile/security-recs.png)

Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati per pagina e le colonne visibili.

La visualizzazione predefinita include colonne che illustrano in dettaglio le debolezze della sicurezza affrontate, la minaccia associata, il componente o il software correlato e altro. Gli elementi possono essere filtrati in base allo stato della raccomandazione.

### <a name="software-inventory"></a>Inventario software

Nella scheda **inventario software** sono elencati i software installati nel dispositivo.

![Immagine della scheda inventario software per il profilo del computer](../../media/mtp-machine-profile/software-inventory.png)

La visualizzazione predefinita Visualizza il fornitore del software, il numero di versione installata, il numero di debolezze del software note, le informazioni sulle minacce, il codice prodotto e i tag. È possibile personalizzare il numero di elementi visualizzati e le colonne visualizzate.

Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa contenente ulteriori informazioni sul software selezionato, nonché il percorso e il timestamp per l'ultima volta che il software è stato trovato.

Questo elenco può essere filtrato in base al codice prodotto.

### <a name="discovered-vulnerabilities-tab"></a>Scheda vulnerabilità individuate

La scheda **vulnerabilità individuata** elenca le vulnerabilità e gli exploit comuni (CVE) che possono influire sul dispositivo.

![Immagine della scheda vulnerabilità individuate per il profilo del computer](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

La visualizzazione predefinita elenca la gravità di CVE, il Punteggio di vulnerabilità comune (CVS), il software relativo a CVE, quando è stato pubblicato CVE, quando è stato aggiornato l'ultimo CVE e le minacce associate a CVE.

Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati e le colonne visibili.

Se si seleziona un elemento da questo elenco, verrà aperto un riquadro a comparsa che descrive CVE.

### <a name="missing-kbs"></a>KBs mancante

La scheda **KBS mancante** elenca gli aggiornamenti di Microsoft che devono essere ancora applicati al computer. La "KBs" in questione sono [articoli della Knowledge base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) che descrivono questi aggiornamenti; ad esempio, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Immagine della scheda KBS mancante per il profilo del computer](../../media/mtp-machine-profile/missing-kbs.PNG)

La visualizzazione predefinita elenca il Bollettino contenente gli aggiornamenti, la versione del sistema operativo, i prodotti coinvolti, la CVE indirizzata, il numero di KB e i tag.

Il numero di elementi visualizzati per pagina e quali colonne vengono visualizzate può essere personalizzato.

Se si seleziona un elemento, verrà aperto un riquadro a comparsa che si collega all'aggiornamento.

## <a name="sidebar"></a>Barra laterale

Accanto all'area di contenuto principale della pagina del profilo del computer è presente la barra laterale.

![Immagine della scheda barra laterale per il profilo del computer](../../media/mtp-machine-profile/sidebar.png)

La barra laterale fornisce alcune importanti informazioni di base in piccole sottosezioni che possono essere attivate in modo aperto o chiuso:

* **Tag** : tutti i tag associati al dispositivo
* **Informazioni di sicurezza** : eventi di apertura, avvisi attivi, livello di esposizione e livello di rischio
* **Dettagli del dispositivo** : dominio, sistema operativo, gruppo di risorse, stato di integrità, sensibilità ai dati e indirizzi IP
* **Attività di rete** -timestamp per la prima volta e l'ultima volta che il dispositivo è stato visualizzato sulla rete

Questa sezione include anche il nome e il livello di esposizione del dispositivo e un'icona per indicare se è attualmente attiva sulla rete.

## <a name="response-actions"></a>Azioni di risposta

Le azioni di risposta offrono una soluzione rapida per la difesa e l'analisi delle minacce.

![Immagine della scheda barra laterale per il profilo del computer](../../media/mtp-machine-profile/actions.PNG)

Le azioni di risposta disponibili includono:

* **Gestione tag** : consente di aggiornare i tag personalizzati applicati al dispositivo.
* **Isolate Machine** -consente di isolare il computer dalla rete dell'organizzazione mantenendo la connessione a Microsoft Defender Advanced Threat Protection. È possibile scegliere di consentire l'esecuzione di Outlook, teams e Skype for business mentre il computer è isolato, a scopo di comunicazione.
* **Limitare l'esecuzione delle app** -impedisce l'esecuzione di applicazioni non firmate da Microsoft
* **Run Antivirus Scan** -aggiorna le definizioni di Windows Defender antivirus ed esegue immediatamente un'analisi antivirus. Scegliere tra analisi rapida o analisi completa.
* **Raccolta del pacchetto di analisi** : raccoglie informazioni sul computer. Al termine dell'analisi, è possibile scaricarlo.
* **Avvio di Live Response Session** -carica una shell remota sul computer per [indagini di sicurezza approfondite](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).
* **Avviare l'analisi automatizzata** : consente [di analizzare e correggere automaticamente le minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Anche se è possibile attivare manualmente le indagini automatizzate per l'esecuzione da questa pagina, [alcuni criteri di avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) attivano le indagini automatiche in modo autonomo.
* **Centro azioni** : visualizzare lo stato delle azioni inviate. Disponibile solo se è già stata selezionata un'altra azione.

## <a name="related-topics"></a>Argomenti correlati

* [Panoramica su Microsoft Threat Protection](microsoft-threat-protection.md)
* [Attivare Microsoft Threat Protection](mtp-enable.md)
* [Esaminare le entità nei computer che utilizzano Live Response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Indagine automatizzata e risposta (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
