---
title: Report di monitoraggio & dispositivi - Centro sicurezza
description: Descrive come mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, report, dispositivi
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930499"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Monitoraggio e creazione di report dei dispositivi nel Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nel Centro sicurezza Microsoft 365.

## <a name="view-device-alerts"></a>Visualizzare gli avvisi per i dispositivi

Ricevere avvisi aggiornati sull'attività di violazione e altre minacce nei dispositivi da Microsoft Defender per Endpoint (disponibile con una licenza E5). Il Centro sicurezza Microsoft 365 monitora in modo efficace questi avvisi a un livello elevato usando il flusso di lavoro preferito.

### <a name="monitor-high-impact-alerts"></a>Monitorare gli avvisi ad alto impatto

Ogni avviso di Microsoft Defender per endpoint ha una gravità corrispondente (alta, media, bassa o informativo). Indica un potenziale impatto sulla rete se lasciato automatico.  

Usa la **scheda Gravità avviso dispositivo** per concentrarti in modo specifico sugli avvisi più gravi e che potrebbero richiedere una risposta immediata. Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.

![Scheda di gravità degli avvisi del dispositivo](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Comprendere le origini degli avvisi

Microsoft Defender for Endpoint sfrutta i dati di un'ampia gamma di sensori di sicurezza e origini di intelligence per generare avvisi. Ad esempio, può usare le informazioni di rilevamento di Microsoft Defender Antivirus e antimalware di terze parti. Può anche usare intelligence personalizzata per le minacce fornita tramite l'API del servizio Web.

La **scheda delle origini di rilevamento degli** avvisi del dispositivo mostra la distribuzione degli avvisi in base all'origine. Tenere traccia delle attività correlate a determinate origini, in particolare alle origini personalizzate. Puoi anche usare la scheda per concentrarti sugli avvisi provenienti da sensori non configurati per bloccare automaticamente attività dannose o componenti.

![Scheda delle origini di rilevamento degli avvisi del dispositivo](../../media/device-alert-detection-sources.png)

Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Comprendere i tipi di minacce che attivano gli avvisi

Microsoft Defender per endpoint ordina ogni avviso in una categoria che rappresenta una determinata fase della catena di attacchi o del tipo di componente di minaccia. Ad esempio, un'attività di minaccia rilevata potrebbe essere classificata come "movimento laterale" per indicare che si è tentato di raggiungere altri dispositivi nella rete. È probabile che l'attività si sia verificata dopo che gli utenti malintenzionati hanno acquisito una posizione iniziale. Quando viene rilevato, un componente di minaccia può essere classificato su larga come malware o in modo specifico come tipo di minaccia specifico. Le specifiche includono ransomware, furto di credenziali o altri tipi di software dannoso o indesiderato.

La **scheda categorie di minacce dispositivo** mostra la distribuzione degli avvisi in queste categorie. Utilizzare queste informazioni per identificare le attività relative alle minacce, ad esempio i tentativi di furto di credenziali, che in genere hanno un impatto maggiore rispetto ai tentativi di ingegneria sociale. Puoi anche monitorare le minacce potenzialmente distruttive come il ransomware.

![Scheda categorie di minacce dispositivo](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Monitorare gli avvisi attivi

La **scheda di stato dell'avviso** del dispositivo indica il numero di avvisi che non sono stati risolti e potrebbero richiedere attenzione. Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.

![Scheda stato avviso dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Monitorare la classificazione degli avvisi risolti

Durante la risoluzione di un avviso di Microsoft Defender per endpoint, il personale di sicurezza può specificare se un avviso è stato verificato come:

* Un vero avviso che identifica l'attività effettiva di violazione o i componenti delle minacce
* Un falso avviso che ha rilevato in modo errato attività normale

La **scheda di classificazione degli avvisi** del dispositivo mostra se gli avvisi risolti sono stati classificati come avvisi veri o falsi. Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.

Nota: in alcuni casi, le informazioni di classificazione non sono disponibili per determinati avvisi.

![Scheda di classificazione degli avvisi del dispositivo](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Monitorare la determinazione degli avvisi risolti

Oltre a classificare se un avviso è vero o falso durante la risoluzione, il personale di sicurezza può fornire una determinazione. Una determinazione indica il tipo di attività normale o dannosa trovata durante la convalida dell'avviso.

La **scheda di determinazione dell'avviso** del dispositivo mostra la determinazione fornita per ogni avviso.

* **APT:** minaccia persistente avanzata, che indica che l'attività rilevata o il componente della minaccia fa parte di una violazione sofisticata progettata per ottenere una base nella rete interessata  
* **Malware:** file o codice dannoso
* **Personale di sicurezza:** normale attività eseguita dal personale di sicurezza
* **Test di sicurezza:** attività o componenti progettati per simulare minacce effettive e che dovrebbero attivare sensori di sicurezza e generare avvisi
* **Software indesiderato:** app e altri software non considerati dannosi, ma che violano in altro modo i criteri o gli standard di utilizzo accettabili
* **Altri**: qualsiasi altra determinazione che non rientra nei tipi forniti

Da questa scheda puoi visualizzare altre informazioni in Microsoft Defender Security Center.

![Scheda per la determinazione dell'avviso del dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Comprendere quali dispositivi sono a rischio

**La protezione dei** dispositivi mostra il livello di rischio per i dispositivi. Il livello di rischio si basa su fattori quali il tipo e la gravità degli avvisi nel dispositivo.

![Scheda di protezione del dispositivo](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Monitorare e segnalare lo stato dei dispositivi gestiti da Intune

I report seguenti contengono i dati dei dispositivi registrati in Intune. I dati dei dispositivi non sono inclusi. Solo gli amministratori globali possono visualizzare queste schede.

I dati dei dispositivi registrati in Intune includono:

* Conformità dispositivo
* Dispositivi con malware attivo
* Tipi di malware nei dispositivi
* Malware nei dispositivi
* Dispositivi con rilevamenti di malware
* Utenti con rilevamenti di malware

### <a name="monitor-device-compliance"></a>Monitorare la conformità dei dispositivi

**La conformità dei** dispositivi mostra quanti dispositivi sono registrati in Intune sono conformi ai criteri di configurazione.

![Scheda di conformità del dispositivo](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Individuare i dispositivi con rilevamenti di malware

**I rilevamenti di malware dei** dispositivi forniscono il numero di dispositivi registrati a Intune con malware che non è stato risolto completamente. La mancanza di risoluzione può essere causata da azioni in sospeso, un riavvio, un'analisi completa, azioni manuali dell'utente o se l'azione di correzione non è stata completata correttamente.

![Scheda rilevamenti malware dei dispositivi](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Comprendere i tipi di malware rilevato

**I tipi di malware nei dispositivi** mostrano diversi tipi di malware rilevati nei dispositivi registrati in Intune. È possibile analizzare ogni tipo nel Centro sicurezza Microsoft 365.

![Tipi di malware nella scheda dei dispositivi](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Comprendere il malware specifico rilevato nei dispositivi

**Il malware nei dispositivi** fornisce un elenco del malware specifico rilevato nei dispositivi.

![Scheda Malware nei dispositivi](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Comprendere quali dispositivi hanno il maggior numero di malware

**I dispositivi con rilevamenti di malware** mostrano quali dispositivi hanno il maggior numero di rilevamenti di malware. nel Centro sicurezza Microsoft 365, è possibile verificare se il malware è attivo, chi usa il dispositivo e il relativo stato di gestione in Intune.

![Scheda dispositivi con rilevamento malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Comprendere quali utenti dispongono di dispositivi con il maggior numero di malware

**Gli utenti con rilevamenti di malware** mostrano gli utenti con dispositivi con il maggior numero di rilevamenti di malware. Nel Centro sicurezza Microsoft 365 è possibile vedere quanti dispositivi sono assegnati a ogni utente e ulteriori informazioni su ogni dispositivo e sul tipo di malware.

![Utenti con scheda di rilevamento malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Monitorare e gestire la distribuzione e i rilevamenti delle regole per la riduzione della superficie di attacco

Le regole di riduzione della superficie di attacco [(ASR, Attack Surface Reduction)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) consentono di impedire azioni e app che in genere vengono usate dal malware per la ricerca di exploit per infettare i dispositivi. Queste regole controllano il modo in cui possono essere eseguiti i file eseguibili. Ad esempio, è possibile impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office o bloccare i processi eseguiti da unità USB.

![Scheda riduzione della superficie di attacco](../../media/attack-surface-reduction-rules.png)

La scheda **Regole per la riduzione della superficie di attacco** fornisce una panoramica della distribuzione delle regole in tutti i dispositivi.

La barra superiore della scheda mostra il numero totale di dispositivi che si trovano nelle modalità di distribuzione seguenti:

* **Modalità di blocco:** dispositivi con almeno una regola configurata per bloccare l'attività rilevata
* **Modalità di controllo:** dispositivi senza regole impostate per bloccare l'attività rilevata, ma con almeno una regola impostata per controllare l'attività rilevata  
* **Disattivato:** dispositivi con tutte le regole asR disattivate

La parte inferiore della scheda mostra le impostazioni per ciascuna regola in tutti i dispositivi. Ogni barra indica il numero di dispositivi impostati per bloccare, controllare il rilevamento o disattivare completamente la regola.

### <a name="view-asr-detections"></a>Visualizzare i rilevamenti asr

Per visualizzare informazioni dettagliate sui rilevamenti delle  regole asr nella rete, selezionare Visualizza rilevamenti nella scheda delle regole di riduzione **della superficie di** attacco. Verrà **visualizzata la** scheda Rilevamenti nella pagina dettagliata del report.

![Scheda Rilevamenti](../../media/detections-tab.png)

Il grafico nella parte superiore della pagina mostra i rilevamenti nel corso del tempo di sovrapposizione dei rilevamenti bloccati o controllati. La tabella in basso elenca i rilevamenti più recenti. Utilizzare le informazioni seguenti nella tabella per comprendere la natura dei rilevamenti:

* **File rilevato:** il file, in genere uno script o un documento, il cui contenuto ha attivato l'attività di attacco sospetto
* **Regola**: nome che descrive le attività di attacco che la regola è progettata per intercettare. Informazioni sulle regole ASR esistenti
* **App di origine:** l'applicazione che ha caricato o eseguito il contenuto che attiva l'attività di attacco sospetto. Potrebbe trattarsi di un'applicazione legittima, ad esempio un Web browser, un'applicazione di Office o uno strumento di sistema come PowerShell
* **Autore:** il fornitore che ha rilasciato l'app di origine

### <a name="review-device-asr-rule-settings"></a>Esaminare le impostazioni delle regole di registrazione asr del dispositivo

Nella pagina **del report Sulle regole di riduzione della superficie** di attacco passare alla scheda **Configurazione** per esaminare le impostazioni delle regole per i singoli dispositivi. Seleziona un dispositivo per ottenere informazioni dettagliate sul fatto che ogni regola sia in modalità di blocco, in modalità di controllo o completamente disattivata.

![Scheda Configuration](../../media/configuration-tab.png)

Microsoft Intune offre funzionalità di gestione per le regole ASR. Se si desidera aggiornare le impostazioni, **selezionare** Introduzione in **Configura** dispositivi nella scheda per aprire la gestione dei dispositivi in Intune.

### <a name="exclude-files-from-asr-rules"></a>Escludere i file dalle regole asr

Il Centro sicurezza Microsoft 365 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) raccoglie i nomi dei file che potrebbe essere necessario escludere dai rilevamenti dalle regole di riduzione della superficie di attacco. Escludendo i file, è possibile ridurre i rilevamenti di falsi positivi e distribuire in modo più sicuro le regole di riduzione della superficie di attacco in modalità blocco.

Le esclusioni sono gestite in Microsoft Intune, ma il Centro sicurezza Microsoft 365 offre uno strumento di analisi che consente di comprendere i file. Per iniziare a raccogliere i file per l'esclusione, vai alla **scheda** Aggiungi esclusioni nella pagina del report sulle regole di **riduzione della superficie** di attacco.

>[!NOTE]  
>Lo strumento analizza i rilevamenti in base a tutte le regole di riduzione della superficie di attacco, ma [solo alcune regole supportano le esclusioni.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)

![Scheda Aggiungi esclusioni](../../media/add-exclusions-tab.png)

Nella tabella sono elencati tutti i nomi di file rilevati dalle regole di riduzione della superficie di attacco. È possibile selezionare i file per esaminare l'impatto dell'esclusione:

* Numero di rilevamenti in meno
* Numero di dispositivi in meno che segnalano i rilevamenti

Per ottenere un elenco dei file selezionati con i relativi percorsi completi per l'esclusione, selezionare **Ottieni percorsi di esclusione.**

I log per la regola ASR bloccano il furto delle credenziali dal sottosistema dell'autorità di sicurezza locale **di Windows (lsass.exe)** acquisiscono l'app **di originelsass.exe**. Si tratta di un normale file di sistema, ma acquisito come file rilevato. Di conseguenza, l'elenco generato di percorsi di esclusione includerà questo file. Per escludere il file che ha attivato questa regola **anzichélsass.exe**, usa il percorso dell'app di origine anziché il file rilevato.

Per individuare l'app di origine, eseguire la [query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) di ricerca avanzata seguente per questa regola specifica (identificata dall'ID regola 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Controllare i file per l'esclusione

Prima di escludere un file da ASR, si consiglia di esaminare il file per determinare se non è effettivamente dannoso.

Per esaminare un file, usare la pagina [delle informazioni sul file](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) in Microsoft Defender Security Center. La pagina fornisce informazioni sulla diffusione e il rapporto di rilevamento antivirus VirusTotal. È inoltre possibile utilizzare la pagina per inviare il file per l'analisi approfondita.

Per individuare un file rilevato in Microsoft Defender Security Center, cercare tutti i rilevamenti ASR usando la query di ricerca avanzata seguente:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Usa **SHA1** o **InitiatingProcessSHA1** nei risultati per cercare il file usando la barra di ricerca universale in Microsoft Defender Security Center.
