---
title: Profilo dispositivo nel portale di sicurezza di Microsoft 365
description: Visualizzare i livelli di rischio e esposizione per un dispositivo nell'organizzazione. Analizzare le minacce passate e presenti e proteggere il dispositivo con gli aggiornamenti più recenti.
keywords: sicurezza, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, centro sicurezza, Microsoft Defender ATP, Office 365 ATP, Azure ATP, pagina del dispositivo, profilo del dispositivo, pagina del computer, profilo computer
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929575"
---
# <a name="device-profile-page"></a>Pagina Profilo dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Il portale di sicurezza di Microsoft 365 fornisce le pagine del profilo del dispositivo, in modo da poter valutare rapidamente l'integrità e lo stato dei dispositivi nella rete.

> [!IMPORTANT]
> La pagina del profilo del dispositivo potrebbe essere leggermente diversa, a seconda che il dispositivo sia registrato in Microsoft Defender per Endpoint, Microsoft Defender per l'identità o entrambi.

Se il dispositivo è registrato in Microsoft Defender per Endpoint, puoi anche usare la pagina del profilo del dispositivo per eseguire alcune attività di sicurezza comuni.

## <a name="navigating-the-device-profile-page"></a>Spostamento nella pagina del profilo del dispositivo

La pagina del profilo è suddivisa in diverse sezioni generali.

![Immagine della pagina del profilo del dispositivo con (1) Area scheda (2) Barra laterale e (3) Azioni evidenziate in rosso](../../media/mtp-device-profile/hybrid-device-overall.png)

La barra laterale (1) elenca i dettagli di base sul dispositivo.

L'area del contenuto principale (2) contiene schede che puoi alternare per visualizzare diversi tipi di informazioni sul dispositivo.

Se il dispositivo è registrato in Microsoft Defender per Endpoint, verrà visualizzato anche un elenco di azioni di risposta (3). Le azioni di risposta consentono di eseguire attività comuni relative alla sicurezza.

## <a name="sidebar"></a>Barra laterale

Accanto all'area del contenuto principale della pagina del profilo del dispositivo è visualizzata la barra laterale.

![Immagine della scheda della barra laterale per il profilo del dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

La barra laterale elenca il nome completo e il livello di esposizione del dispositivo. Vengono inoltre fornite alcune importanti informazioni di base nelle sottosezioni di piccole dimensioni che possono essere attivate o chiuse, ad esempio:

* **Tag:** qualsiasi microsoft defender per endpoint, Microsoft Defender per l'identità o tag personalizzati associati al dispositivo. I tag di Microsoft Defender for Identity non sono modificabili.
* **Info di sicurezza:** eventi imprevisti aperti e avvisi attivi. Anche i dispositivi registrati in Microsoft Defender per Endpoint visualizzano il livello di esposizione e il livello di rischio.

> [!TIP]
> Il livello di esposizione si riferisce a quanto il dispositivo è conforme alle raccomandazioni per la sicurezza, mentre il livello di rischio viene calcolato in base a una serie di fattori, inclusi i tipi e la gravità degli avvisi attivi.

* **Dettagli dispositivo:** dominio, sistema operativo, timestamp della prima visualizzazione del dispositivo, indirizzi IP, risorse. Anche i dispositivi registrati in Microsoft Defender per Endpoint visualizzano lo stato di integrità. I dispositivi registrati in Microsoft Defender per l'identità visualizzano il nome SAM e un timestamp per la prima creazione del dispositivo.
* **Attività di** rete: timestamp per la prima volta e l'ultima volta in cui il dispositivo è stato visualizzato in rete.
* **Dati della directory** *(solo per i dispositivi registrati in Microsoft Defender per* l'identità): flag [di](https://docs.microsoft.com/windows/win32/ad/service-principal-names)Controllo dell'account utente, nomi SPN e appartenenze a gruppi. [](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview)

## <a name="response-actions"></a>Azioni di risposta

Le azioni di risposta offrono un modo rapido per difendersi dalle minacce e analizzarne le minacce.

![Immagine della barra delle azioni per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Le azioni](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) di risposta sono disponibili solo se il dispositivo è registrato in Microsoft Defender per Endpoint.
> * I dispositivi registrati in Microsoft Defender per Endpoint potrebbero visualizzare un numero diverso di azioni di risposta, in base al sistema operativo e al numero di versione del dispositivo.

Le azioni disponibili nella pagina del profilo del dispositivo includono:

* **Gestisci tag:** aggiorna i tag personalizzati applicati a questo dispositivo.
* **Isola dispositivo:** isola il dispositivo dalla rete dell'organizzazione mantenendolo connesso a Microsoft Defender per Endpoint. È possibile scegliere di consentire l'esecuzione di Outlook, Teams e Skype for Business mentre il dispositivo è isolato, a scopo di comunicazione.
* **Centro notifiche:** consente di visualizzare lo stato delle azioni inviate. Disponibile solo se è già stata selezionata un'altra azione.
* **Limitare l'esecuzione delle** app: impedisce l'esecuzione di applicazioni non firmate da Microsoft.
* **Eseguire l'analisi antivirus:** Windows Defender definizioni antivirus ed esegue immediatamente un'analisi antivirus. Scegliere tra Analisi rapida o Analisi completa.
* **Raccogliere il pacchetto di** analisi: raccoglie informazioni sul dispositivo. Al termine dell'indagine, è possibile scaricarla.
* **Avvia sessione di risposta in tempo** reale: carica una shell remota nel dispositivo per indagini [approfondite sulla sicurezza.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* **Avviare un'indagine automatizzata:** consente di [analizzare e correggere automaticamente le minacce.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Sebbene sia possibile attivare manualmente l'esecuzione di indagini automatizzate da questa [pagina,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) alcuni criteri di avviso attivano automaticamente le indagini.
* **Centro notifiche:** visualizza informazioni sulle azioni di risposta attualmente in esecuzione.

## <a name="tabs-section"></a>Sezione Tabs

Le schede del profilo del dispositivo consentono di passare da una panoramica dei dettagli di sicurezza sul dispositivo e delle tabelle contenenti un elenco di avvisi.

I dispositivi registrati in Microsoft Defender per Endpoint visualizzano anche schede che presentano una sequenza temporale, un elenco di suggerimenti sulla sicurezza, un inventario software, un elenco di vulnerabilità individuate e gli indicatori KPI mancanti (aggiornamenti della sicurezza).

### <a name="overview-tab"></a>Scheda Panoramica

La scheda predefinita è **Panoramica.** Fornisce un rapido sguardo al fatto di sicurezza più importante sul dispositivo.

![Immagine della scheda Panoramica per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Qui puoi visualizzare rapidamente gli avvisi attivi del dispositivo e gli utenti attualmente connessi.

Se il dispositivo è registrato in Microsoft Defender per Endpoint, verranno visualizzati anche il livello di rischio del dispositivo e i dati disponibili sulle valutazioni della sicurezza. Le valutazioni della sicurezza descrivono il livello di esposizione del dispositivo, forniscono consigli sulla sicurezza ed elencano il software interessato e le vulnerabilità individuate.

### <a name="alerts-tab"></a>Scheda Avvisi

La **scheda Avvisi** contiene un elenco di avvisi generati nel dispositivo, sia da Microsoft Defender per l'identità che da Microsoft Defender per endpoint.

![Immagine della scheda avvisi per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

È possibile personalizzare il numero di elementi visualizzati, nonché le colonne visualizzate per ogni elemento. Il comportamento predefinito è elencare trenta elementi per pagina.

Le colonne in questa scheda includono informazioni sulla gravità della minaccia che ha attivato l'avviso, nonché lo stato, lo stato dell'indagine e l'utente a cui è stato assegnato l'avviso.

La *colonna delle entità interessate* fa riferimento al dispositivo (entità) di cui si sta visualizzando il profilo, oltre a tutti gli altri dispositivi della rete interessati.

Se si seleziona un elemento dall'elenco, verrà aperto un riquadro a comparsa contenente ulteriori informazioni sull'avviso selezionato.

Questo elenco può essere filtrato in base alla gravità, allo stato o all'utente a cui è stato assegnato l'avviso.

### <a name="timeline-tab"></a>Scheda Sequenza temporale

La **scheda Sequenza** temporale include un grafico cronologico interattivo di tutti gli eventi generati nel dispositivo. Spostando l'area evidenziata del grafico a sinistra o a destra, è possibile visualizzare gli eventi in periodi di tempo diversi. Puoi anche scegliere un intervallo personalizzato di date dal menu a discesa tra il grafico interattivo e l'elenco degli eventi.

Sotto il grafico è riportato un elenco di eventi per l'intervallo di date selezionato.

![Immagine della scheda sequenza temporale per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

Il numero di elementi visualizzati e le colonne dell'elenco possono essere entrambi personalizzati. Le colonne predefinite elencano l'ora dell'evento, l'utente attivo, il tipo di azione, le entità (processi) e informazioni aggiuntive sull'evento.

Se si seleziona un elemento da questo elenco, verrà visualizzato un riquadro a comparsa con un grafico delle entità evento che mostra i processi padre e figlio coinvolti nell'evento.

L'elenco può essere filtrato in base al tipo specifico di evento; ad esempio eventi del Registro di sistema o eventi smart screen.

L'elenco può anche essere esportato in un file CSV, per il download. Anche se il file non è limitato dal numero di eventi, l'intervallo di tempo massimo che è possibile scegliere di esportare è di sette giorni.

### <a name="security-recommendations-tab"></a>Scheda Suggerimenti per la sicurezza

Nella **scheda Suggerimenti per la** sicurezza sono elencate le azioni che è possibile eseguire per proteggere il dispositivo. La selezione di un elemento in questo elenco consente di aprire un riquadro a comparsa in cui è possibile ottenere istruzioni su come applicare il suggerimento.

![Immagine della scheda degli elementi consigliati per la sicurezza per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati per pagina, nonché le colonne visibili.

La visualizzazione predefinita include colonne che dettagliano i punti deboli della sicurezza, la minaccia associata, il componente o il software correlato interessato dalla minaccia e altro ancora. Gli elementi possono essere filtrati in base allo stato del suggerimento.

### <a name="software-inventory"></a>Inventario software

La **scheda Inventario software** elenca il software installato nel dispositivo.

![Immagine della scheda inventario software per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

Nella visualizzazione predefinita vengono visualizzati il fornitore del software, il numero di versione installato, il numero di punti deboli noti del software, informazioni dettagliate sulle minacce, codice prodotto e tag. Il numero di elementi visualizzati e le colonne visualizzate possono essere entrambi personalizzati.

Selezionando un elemento da questo elenco si apre un riquadro a comparsa contenente ulteriori dettagli sul software selezionato, nonché il percorso e il timestamp dell'ultima volta che il software è stato trovato.

Questo elenco può essere filtrato in base al codice prodotto.

### <a name="discovered-vulnerabilities-tab"></a>Scheda Vulnerabilità individuate

Nella **scheda Vulnerabilità individuate** sono elencate tutte le vulnerabilità e gli exploit comuni che possono influire sul dispositivo.

![Immagine della scheda delle vulnerabilità individuate per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

Nella visualizzazione predefinita sono elencati la gravità del CVE, il punteggio di vulnerabilità comune (CVS), il software correlato al CVE, la data di pubblicazione del CVE, l'ultimo aggiornamento del CVE e le minacce associate al CVE.

Come per le schede precedenti, è possibile personalizzare il numero di elementi visualizzati e le colonne visibili.

Se si seleziona un elemento dall'elenco, verrà aperto un riquadro a comparsa che descrive il punto di controllo.

### <a name="missing-kbs"></a>Indicatori KPI mancanti

Nella **scheda Kpi** mancanti sono elencati gli eventuali aggiornamenti Microsoft che devono ancora essere applicati al dispositivo. I "Kb" in questione sono articoli [della Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) che descrivono questi aggiornamenti; ad esempio [KB4551762.](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)

![Immagine della scheda kb mancante per il profilo del dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

Nella visualizzazione predefinita sono elencati i bollettini contenenti gli aggiornamenti, la versione del sistema operativo, i prodotti interessati, i CVE indirizzati, il numero KB e i tag.

Il numero di elementi visualizzati per pagina e le colonne visualizzate possono essere personalizzati.

Se si seleziona un elemento, verrà aperto un riquadro a comparsa che collega all'aggiornamento.

## <a name="related-topics"></a>Argomenti correlati

* [Panoramica di Microsoft 365 Defender](microsoft-threat-protection.md)
* [Attivare Microsoft 365 Defender](mtp-enable.md)
* [Analizzare le entità nei dispositivi, usando la risposta in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Analisi e risposta automatizzate (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
