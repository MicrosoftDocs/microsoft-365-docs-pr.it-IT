---
title: Monitoraggio dei dispositivi & Reporting-Centro sicurezza
description: Descrive in che modo è possibile mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, dispositivi
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 870d2ce1f70028c917cc8b165e8a1c55b746100a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033999"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Monitoraggio e Reporting dei dispositivi nel centro sicurezza Microsoft 365

Mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nel centro sicurezza Microsoft 365.

## <a name="view-device-alerts"></a>Visualizzare gli avvisi per i dispositivi

Ottenere avvisi aggiornati sull'attività di violazione e altre minacce sui dispositivi da Microsoft Defender ATP (disponibile con una licenza E5). Microsoft 365 Security Center monitora efficacemente gli avvisi a un livello elevato utilizzando il flusso di lavoro preferito.

### <a name="monitor-high-impact-alerts"></a>Monitorare gli avvisi ad impatto elevato

Ogni avviso del trifosfato di adenosina di Microsoft Defender ha un livello di gravità corrispondente (alto, medio, basso o informativo) che indica il suo impatto potenziale sulla rete se non è presente.  

Utilizzare la scheda **gravità avviso dispositivo** per concentrarsi in modo specifico sugli avvisi più gravi e potrebbe richiedere una risposta immediata. Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.

![Scheda di gravità avvisi dispositivo](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Informazioni sulle origini degli avvisi

Microsoft Defender ATP utilizza i dati provenienti da una vasta gamma di sensori di sicurezza e fonti di intelligence per generare avvisi. Ad esempio, è possibile utilizzare le informazioni di rilevamento di Windows Defender Antivirus e antimalware di terze parti, nonché la propria Intelligence di minacce personalizzata fornita tramite l'API del servizio Web.

La scheda fonti di **rilevamento avvisi dispositivo** Visualizza la distribuzione degli avvisi per origine. Questa scheda può essere utile per monitorare le attività relative a determinate origini, in particolare le origini personalizzate. È inoltre possibile utilizzare questa pagina per concentrarsi sugli avvisi provenienti da sensori che non sono configurati per bloccare automaticamente le attività o i componenti dannosi.

![Scheda fonti di rilevamento avvisi dispositivo](../../media/device-alert-detection-sources.png)

Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Comprendere i tipi di minacce che attivano gli avvisi

Microsoft Defender ATP Ordina ogni avviso in una categoria che rappresenta una determinata fase della catena di attacco o un tipo di componente di minaccia. Ad esempio, un'attività di minacce rilevata potrebbe essere categorizzata come "movimento laterale" per indicare che si è verificato un tentativo di raggiungere altri dispositivi sulla rete. L'attività è probabile che si è verificato anche dopo che gli aggressori hanno acquisito un appiglio iniziale. Una volta rilevato, un componente di minacce potrebbe essere classificato come malware, o più specificamente come ransomware, furto di credenziali o altri tipi di software dannoso o indesiderato.

La scheda **categorie minacce dispositivo** Visualizza la distribuzione degli avvisi in queste categorie. È possibile utilizzare queste informazioni per identificare le attività di minacce, ad esempio i tentativi di furto delle credenziali, che possono avere un impatto maggiore rispetto ai tentativi di social engineering. È inoltre possibile utilizzare queste informazioni per eseguire il monitoraggio di minacce potenzialmente distruttive come ransomware.

![Scheda categorie di minacce per dispositivi](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Monitorare gli avvisi attivi

La scheda **stato avviso dispositivo** indica il numero di avvisi che non sono stati risolti e che potrebbero richiedere attenzione. Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.

![Scheda stato avviso dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Monitorare la classificazione degli avvisi risolti

Durante la risoluzione di un avviso di Microsoft Defender ATP, il personale di sicurezza può specificare se un avviso è stato verificato come:

* Un avviso vero che identifica le attività di violazione effettive o i componenti di minaccia
* Un falso avviso che ha rilevato erroneamente attività normale

La scheda di **classificazione avviso dispositivo** indica se gli avvisi risolti sono stati classificati come avvisi veri o falsi. Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.

Nota: in alcuni casi, le informazioni di classificazione non sono disponibili per determinati avvisi.

![Scheda di classificazione degli avvisi dei dispositivi](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Monitorare la determinazione degli avvisi risolti

Oltre a classificare se un avviso è vero o falso durante la risoluzione, il personale della sicurezza può fornire una determinazione, indicando il tipo di attività normale o dannosa individuata durante la convalida dell'avviso.

La scheda di **determinazione dell'avviso del dispositivo** Visualizza la determinazione fornita per ogni avviso.

* **Apt**: Advanced Persistent Threat, che indica che l'attività rilevata o il componente di minaccia è parte di una sofisticata violazione progettata per ottenere un punto di appoggio nella rete in questione  
* **Malware**: file o codice dannoso
* **Personale di sicurezza**: attività normale eseguita dal personale della sicurezza
* **Test di sicurezza**: attività o componenti studiati per simulare le minacce effettive e prevedere l'attivazione di sensori di sicurezza e generare avvisi
* **Software indesiderato**: app e altri software che non sono considerati dannosi, ma violano in altro modo i criteri o gli standard di utilizzo accettabili
* **Altri**: eventuali altre determinazioni che non rientrano nei tipi forniti

Da questa scheda, è possibile visualizzare altre informazioni in Microsoft Defender Security Center.

![Scheda di determinazione dell'avviso del dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Comprendere quali dispositivi sono a rischio

La **protezione del dispositivo** Visualizza il livello di rischio per i dispositivi. Il livello di rischio si basa su fattori quali il tipo e la gravità degli avvisi nel dispositivo.

![Scheda di protezione del dispositivo](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Monitorare e segnalare lo stato dei dispositivi gestiti da Intune

Nei rapporti seguenti sono contenuti dati provenienti da dispositivi registrati in Intune. I dati dei dispositivi non registrati non sono inclusi. Solo gli amministratori globali possono visualizzare queste schede.

I dati dei dispositivi registrati di Intune includono:

* Conformità dispositivo
* Dispositivi con malware attivo
* Tipi di malware nei dispositivi
* Malware nei dispositivi
* Dispositivi con rilevamenti di malware
* Utenti con rilevamenti di malware

### <a name="monitor-device-compliance"></a>Monitorare la conformità del dispositivo

La **conformità del dispositivo** indica il numero di dispositivi registrati in Intune conformi ai criteri di configurazione.

![Scheda conformità dispositivo](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Individuare i dispositivi con rilevamenti di malware

I **rilevamenti di malware** per i dispositivi forniscono il numero di dispositivi registrati di Intune con malware che non sono stati completamente risolti. Questo può essere dovuto a azioni in sospeso, a un riavvio, a un'analisi completa, azioni utente manuali o se l'azione di correzione non è stata completata correttamente.

![Scheda rilevamenti malware dispositivo](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Informazioni sui tipi di malware rilevati

I **tipi di malware nei dispositivi** mostrano diversi tipi di malware che sono stati rilevati nei dispositivi registrati in Intune. È possibile esaminare ogni tipo nel centro sicurezza Microsoft 365.

![Tipi di malware sulla scheda dispositivi](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Comprendere il malware specifico rilevato nei dispositivi

Il **malware nei dispositivi** fornisce un elenco di malware specifici rilevati nei dispositivi.

![Scheda malware su dispositivi](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Informazioni sui dispositivi con la maggior parte dei malware

I **dispositivi con rilevamenti di malware** mostrano quali dispositivi presentano la maggior parte dei rilevamenti di malware. nel centro sicurezza Microsoft 365, è possibile verificare se il malware è attivo, chi usa il dispositivo e lo stato di gestione in Intune.

![Scheda dispositivi con rilevamento malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Comprendere quali utenti dispongono di dispositivi con la maggior parte dei malware

**Gli utenti che dispongono di rilevamenti di malware** mostrano agli utenti i dispositivi con più rilevamenti di malware. Nel centro sicurezza Microsoft 365, è possibile visualizzare il numero di dispositivi assegnati a ciascun utente e ulteriori informazioni su ogni dispositivo e sul tipo di malware.

![Utenti con scheda di rilevamento antimalware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>Monitorare e gestire la distribuzione e i rilevamenti delle regole ASR

[Le regole di riduzione dell'attacco superficiale (ASR, Attack Surface Reduction)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) consentono di prevenire azioni e app che in genere vengono utilizzate da malware in grado di sfruttare i dispositivi. Queste regole controllano il modo in cui possono essere eseguiti i file eseguibili. Ad esempio, è possibile impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office o bloccare i processi eseguiti da unità USB.

![Scheda riduzioni superficie attacco](../../media/attack-surface-reduction-rules.png)

La scheda **Regole per la riduzione della superficie di attacco** fornisce una panoramica della distribuzione delle regole in tutti i dispositivi.

La barra superiore della scheda mostra il numero totale di dispositivi che si trovano nelle modalità di distribuzione seguenti:

* **Modalità di blocco**: dispositivi con almeno una regola configurata per bloccare l'attività rilevata
* **Modalità di controllo**: i dispositivi con nessuna regola impostata per bloccare l'attività rilevata, ma hanno almeno un set di regole per il controllo dell'attività rilevata  
* **Disattivato**: i dispositivi con tutte le regole di ASR sono disattivati

La parte inferiore della scheda mostra le impostazioni per ciascuna regola in tutti i dispositivi. Ogni barra indica il numero di dispositivi bloccati o da controllare oppure con la regola completamente disattivata.

### <a name="view-asr-detections"></a>Visualizzazione dei rilevamenti ASR

Per visualizzare informazioni dettagliate sui rilevamenti delle regole di ASR nella rete, selezionare **Visualizza rilevamenti** nella scheda **regole di riduzione della superficie di attacco** . Verrà aperta la scheda **rilevamenti** nella pagina rapporto dettagliato.

![Scheda rilevamenti](../../media/detections-tab.png)

Il grafico nella parte superiore della pagina Visualizza rilevamenti nel tempo di rilevamenti di sovrapposizione che sono stati bloccati o controllati. La tabella in basso elenca i rilevamenti più recenti. Utilizzare le informazioni seguenti nella tabella per comprendere la natura dei rilevamenti:

* **File rilevato**: il file, in genere uno script o un documento, il cui contenuto ha attivato l'attività di attacco sospetta
* **Regola**: nome che descrive le attività di attacco la regola è progettata per essere intercettata. Leggere le regole ASR esistenti
* **App di origine**: l'applicazione che ha caricato o eseguito contenuto che attiva l'attività di attacco sospetta. Potrebbe trattarsi di un'applicazione legittima, ad esempio il Web browser, un'applicazione di Office o uno strumento di sistema come PowerShell.
* **Publisher**: il fornitore che ha rilasciato l'app di origine

### <a name="review-device-asr-rule-settings"></a>Esaminare le impostazioni della regola di ASR del dispositivo

Nella pagina rapporto **regole di riduzione della superficie di attacco** passare alla scheda **configurazione** per esaminare le impostazioni delle regole per i singoli dispositivi. Selezionare un dispositivo per ottenere informazioni dettagliate sul fatto che ogni regola sia in modalità di blocco, modalità di controllo o disattivata completamente.

![Scheda configurazione](../../media/configuration-tab.png)

Microsoft Intune offre funzionalità di gestione per le regole di ASR. Se si desidera aggiornare le impostazioni, selezionare **Get Started** in **Configure Devices** nella scheda per aprire Gestione dispositivi su Intune.

### <a name="exclude-files-from-asr-rules"></a>Escludi file dalle regole di ASR

Microsoft 365 Security Center raccoglie i nomi dei [file che potrebbe essere necessario escludere](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) dai rilevamenti tramite le regole di riduzione della superficie di attacco. Escludendo i file, è possibile ridurre i rilevamenti falsi positivi e distribuire in modo più sicuro le regole di riduzione della superficie di attacco in modalità di blocco.

Le esclusioni sono gestite su Microsoft Intune, ma Microsoft 365 Security Center fornisce uno strumento di analisi per facilitare la comprensione dei file. Per avviare la raccolta dei file per l'esclusione, passare alla scheda **Aggiungi esclusioni** nella pagina rapporto **regole di riduzione della superficie di attacco** .

>[!NOTE]  
>Lo strumento analizza i rilevamenti per tutte le regole di riduzione della superficie di attacco, ma [solo alcune regole supportano le esclusioni](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).

![Scheda Aggiungi esclusioni](../../media/add-exclusions-tab.png)

Nella tabella sono elencati tutti i nomi di file rilevati dalle regole di riduzione della superficie di attacco. È possibile selezionare i file per esaminare l'impatto dell'esclusione:

* Quanti meno rilevamenti
* Quanti meno dispositivi segnalano i rilevamenti

Per ottenere un elenco dei file selezionati con i percorsi completi per l'esclusione, selezionare **Ottieni percorsi di esclusione**.

Registri per la regola di ASR **Block Credential Stealing from the Windows Local Security Authority Subsystem (Lsass. exe)** acquisire l'app di origine **Lsass. exe**, un file di sistema normale, come file rilevato. Di conseguenza, l'elenco generato dei percorsi di esclusione includerà questo file. Per escludere il file che ha attivato questa regola anziché **Lsass. exe**, utilizzare il percorso dell'applicazione di origine anziché il file rilevato.

Per individuare l'app di origine, eseguire la [query di ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) seguente per questa regola specifica (identificata dalla regola ID 9e6c4e1f-7d60-472F-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Controllare i file per l'esclusione

Prima di escludere un file dal riconoscimento vocale automatico, è consigliabile ispezionare il file per determinare se non è effettivamente dannoso.

Per esaminare un file, utilizzare la [pagina informazioni sui file](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) in Microsoft Defender Security Center. La pagina fornisce informazioni sulla prevalenza così come il rapporto di rilevamento antivirus di VirusTotal. È inoltre possibile utilizzare la pagina per inviare il file per un'analisi approfondita.

Per individuare un file rilevato in Microsoft Defender Security Center, cercare tutti i rilevamenti ASR utilizzando la query di caccia avanzata seguente:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Utilizzare l'interfaccia **SHA1** o la **InitiatingProcessSHA1** nei risultati per cercare il file utilizzando la barra di ricerca universale in Microsoft Defender Security Center.
