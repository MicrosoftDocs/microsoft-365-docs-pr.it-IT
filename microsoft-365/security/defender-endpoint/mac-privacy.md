---
title: Privacy per Microsoft Defender per Endpoint su Mac
description: Controlli sulla privacy, come configurare le impostazioni dei criteri che influiscono sulla privacy e informazioni sui dati di diagnostica raccolti in Microsoft Defender per Endpoint su Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, privacy, diagnostica
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2884ffc695abc1c6b4b5be9bbd7c9ad37ad05439
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651297"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a>Privacy per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Microsoft si impegna a fornire all'utente le informazioni e i controlli necessari per effettuare scelte sulla modalità di raccolta e utilizzo dei dati quando si usa Microsoft Defender for Endpoint in macOS.

In questo argomento vengono descritti i controlli della privacy disponibili all'interno del prodotto, come gestire questi controlli con le impostazioni dei criteri e altri dettagli sugli eventi dati raccolti.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a>Panoramica dei controlli della privacy in Microsoft Defender for Endpoint in macOS

Questa sezione descrive i controlli della privacy per i diversi tipi di dati raccolti da Microsoft Defender per Endpoint in macOS.

### <a name="diagnostic-data"></a>Dati di diagnostica

I dati di diagnostica vengono usati per mantenere Microsoft Defender for Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto.

Alcuni dati di diagnostica sono obbligatori, mentre altri sono facoltativi. Microsoft fornisce la possibilità di scegliere se inviare i dati di diagnostica obbligatori o facoltativi tramite i controlli della privacy, ad esempio le impostazioni dei criteri per le organizzazioni.

Esistono due livelli di dati di diagnostica per il software client Microsoft Defender for Endpoint tra cui è possibile scegliere:

* **Obbligatorio:** i dati minimi necessari per mantenere Microsoft Defender for Endpoint sicuro, aggiornato e le prestazioni come previsto nel dispositivo in cui è installato.

* **Facoltativo:** dati aggiuntivi che consentono a Microsoft di apportare miglioramenti al prodotto e fornisce informazioni avanzate per rilevare, diagnosticare e risolvere i problemi.

Per impostazione predefinita, a Microsoft vengono inviati solo i dati di diagnostica necessari.

### <a name="cloud-delivered-protection-data"></a>Dati di protezione del cloud recapitati

La protezione basata sul cloud viene usata per fornire una protezione maggiore e più veloce con l'accesso ai dati di protezione più recenti nel cloud.

L'abilitazione del servizio di protezione fornita dal cloud è facoltativa, tuttavia è consigliabile perché fornisce una protezione importante contro il malware sugli endpoint e sulla rete.

### <a name="sample-data"></a>Dati di esempio

I dati di esempio vengono usati per migliorare le funzionalità di protezione del prodotto, inviando campioni sospetti Microsoft in modo che possano essere analizzati. L'abilitazione dell'invio automatico di esempi è facoltativa.

Quando questa funzionalità è abilitata e è probabile che l'esempio raccolto contenga informazioni personali, all'utente viene richiesto il consenso.

## <a name="manage-privacy-controls-with-policy-settings"></a>Gestire i controlli della privacy con le impostazioni dei criteri

Gli amministratori IT possono configurare questi controlli a livello aziendale. 

I controlli della privacy per i vari tipi di dati descritti nella sezione precedente sono descritti in dettaglio in Impostare le preferenze per [Microsoft Defender per Endpoint su macOS.](mac-preferences.md)

Come per le nuove impostazioni dei criteri, è consigliabile testarle attentamente in un ambiente limitato e controllato per garantire che le impostazioni configurate siano effettive prima di implementare le impostazioni dei criteri in modo più ampio nell'organizzazione.

## <a name="diagnostic-data-events"></a>Eventi di dati di diagnostica

In questa sezione vengono descritti i dati di diagnostica necessari e i dati di diagnostica facoltativi, insieme a una descrizione degli eventi e dei campi raccolti.

### <a name="data-fields-that-are-common-for-all-events"></a>Campi dati comuni per tutti gli eventi
Alcune informazioni sono comuni a tutti gli eventi, indipendentemente dalla categoria o dal sottotipo di dati. 

I campi seguenti sono considerati comuni per tutti gli eventi:

| Campo                   | Descrizione |
| ----------------------- | ----------- |
| piattaforma                | Classificazione generale della piattaforma in cui è in esecuzione l'app. Consente a Microsoft di identificare su quali piattaforme potrebbe verificarsi un problema in modo che possa essere assegnata correttamente la priorità. |
| machine_guid            | Identificatore univoco associato al dispositivo. Consente a Microsoft di identificare se i problemi influiscono su un set selezionato di installazioni e sul numero di utenti che ne sono influenzati. |
| sense_guid              | Identificatore univoco associato al dispositivo. Consente a Microsoft di identificare se i problemi influiscono su un set selezionato di installazioni e sul numero di utenti che ne sono influenzati. |
| org_id                  | Identificatore univoco associato all'organizzazione a cui appartiene il dispositivo. Consente a Microsoft di identificare se i problemi influiscono su un set selezionato di aziende e su quante aziende sono influenzate. |
| hostname                | Nome del dispositivo locale (senza suffisso DNS). Consente a Microsoft di identificare se i problemi influiscono su un set selezionato di installazioni e sul numero di utenti che ne sono influenzati. |
| product_guid            | Identificatore univoco del prodotto. Consente a Microsoft di distinguere i problemi che influiscono sulle diverse versioni del prodotto. |
| app_version             | Versione di Microsoft Defender per Endpoint in un'applicazione macOS. Consente a Microsoft di identificare le versioni del prodotto che mostrano un problema in modo che possa essere correttamente classificata in ordine di priorità.|
| sig_version             | Versione del database di intelligence per la sicurezza. Consente a Microsoft di identificare le versioni dell'intelligence per la sicurezza che mostrano un problema in modo che possa essere assegnata correttamente la priorità. |
| supported_compressions  | Elenco degli algoritmi di compressione supportati dall'applicazione, ad esempio `['gzip']` . Consente a Microsoft di comprendere quali tipi di compressione possono essere utilizzati quando comunica con l'applicazione. |
| release_ring            | Anello a cui è associato il dispositivo (ad esempio Insider Fast, Insider Slow, Production). Consente a Microsoft di identificare in quale anello di rilascio potrebbe verificarsi un problema in modo che possa essere assegnata correttamente la priorità. |


### <a name="required-diagnostic-data"></a>Dati di diagnostica obbligatori

**I dati di diagnostica** necessari sono i dati minimi necessari per mantenere Microsoft Defender for Endpoint sicuro, aggiornato ed eseguire come previsto nel dispositivo in cui è installato.

I dati di diagnostica necessari consentono di identificare i problemi di Microsoft Defender per Endpoint che potrebbero essere correlati a una configurazione di dispositivo o software. Ad esempio, può aiutare a determinare se una funzionalità di Microsoft Defender for Endpoint si arresta più frequentemente in una determinata versione del sistema operativo, con le nuove funzionalità introdotte o quando alcune funzionalità di Microsoft Defender for Endpoint sono disabilitate. I dati di diagnostica necessari consentono a Microsoft di rilevare, diagnosticare e risolvere questi problemi più rapidamente, in modo da ridurre l'impatto sugli utenti o sulle organizzazioni.

#### <a name="software-setup-and-inventory-data-events"></a>Eventi dati Configurazione e inventario software

**Installazione/disinstallazione di Microsoft Defender for Endpoint**

Vengono raccolti i campi seguenti:

| Campo            | Descrizione |
| ---------------- | ----------- |
| correlation_id   | Identificatore univoco associato all'installazione. |
| Versione          | Versione del pacchetto. |
| gravità         | Gravità del messaggio (ad esempio Informativo). |
| code             | Codice che descrive l'operazione. |
| text             | Informazioni aggiuntive associate all'installazione del prodotto. |

**Configurazione di Microsoft Defender per endpoint**

Vengono raccolti i campi seguenti:

| Campo                                               | Descrizione |
| --------------------------------------------------- | ----------- |
| antivirus_engine.enable_real_time_protection        | Indica se la protezione in tempo reale è abilitata o meno nel dispositivo. |
| antivirus_engine.passive_mode                       | Indica se la modalità passiva è abilitata o meno nel dispositivo. |
| cloud_service.enabled                               | Indica se la protezione basata sul cloud è abilitata o meno nel dispositivo. |
| cloud_service.timeout                               | Timeout quando l'applicazione comunica con il cloud Microsoft Defender for Endpoint. |
| cloud_service.heartbeat_interval                    | Intervallo tra heartbeat consecutivi inviati dal prodotto al cloud. |
| cloud_service.service_uri                           | URI usato per comunicare con il cloud. |
| cloud_service.diagnostic_level                      | Livello di diagnostica del dispositivo (obbligatorio, facoltativo). |
| cloud_service.automatic_sample_submission           | Indica se l'invio automatico di esempio è attivato o meno. |
| cloud_service.automatic_definition_update_enabled   | Indica se l'aggiornamento automatico delle definizioni è attivato o meno. |
| edr.early_preview                                   | Indica se il dispositivo deve essere eseguito EDR funzionalità di anteprima anticipata. |
| edr.group_id                                        | Identificatore di gruppo utilizzato dal componente di rilevamento e risposta. |
| edr.tags                                            | Tag definiti dall'utente. |
| funzionalità. \[ nome funzionalità facoltativo\]                  | Elenco delle funzionalità di anteprima, insieme al fatto che siano abilitate o meno. |

#### <a name="product-and-service-usage-data-events"></a>Eventi dati di Utilizzo di prodotti e servizi

**Report sull'aggiornamento delle funzionalità di intelligence per la sicurezza**

Vengono raccolti i campi seguenti:

| Campo            | Descrizione |
| ---------------- | ----------- |
| from_version     | Versione originale di security intelligence. |
| to_version       | Nuova versione di security intelligence. |
| status           | Stato dell'aggiornamento che indica l'esito positivo o negativo. |
| using_proxy      | Indica se l'aggiornamento è stato eseguito su un proxy. |
| error            | Codice di errore se l'aggiornamento non è riuscito. |
| motivo           | Messaggio di errore se l'aggiornamento è stato aggiornato. |

#### <a name="product-and-service-performance-data-events"></a>Eventi dati di Prestazioni di prodotti e servizi

**Chiusura imprevista (arresto anomalo) dell'applicazione**

Raccoglie informazioni di sistema e lo stato di un'applicazione quando un'applicazione viene chiusa in modo imprevisto.

Vengono raccolti i campi seguenti:

| Campo                          | Descrizione |
| ------------------------------ | ----------- |
| v1_crash_count                 | Numero di arresti anomalo del processo del motore V1 ogni ora nel computer client  |
| v2_crash_count                 | Numero di arresti anomalo del processo del motore V2 ogni ora nel computer client  |
| EDR_crash_count                | Numero di arresti EDR arresto anomalo del processo ogni ora nel computer client        |

**Statistiche dell'estensione kernel**

Vengono raccolti i campi seguenti:

| Campo            | Descrizione |
| ---------------- | ----------- |
| Versione          | Versione di Microsoft Defender per Endpoint in macOS. |
| instance_id      | Identificatore univoco generato all'avvio dell'estensione del kernel. |
| trace_level      | Livello di traccia dell'estensione del kernel. |
| sottosistema        | Sottosistema sottostante utilizzato per la protezione in tempo reale. |
| ipc.connects     | Numero di richieste di connessione ricevute dall'estensione del kernel. |
| ipc.rejects      | Numero di richieste di connessione rifiutate dall'estensione del kernel. |
| ipc.connected    | Indica se esiste una connessione attiva all'estensione del kernel. |

#### <a name="support-data"></a>Dati di supporto

**Registri diagnostici**

I log di diagnostica vengono raccolti solo con il consenso dell'utente come parte della funzionalità di invio del feedback. I file seguenti vengono raccolti come parte dei registri di supporto:

- Tutti i file in */Library/Logs/Microsoft/mdatp/*
- Sottoinsieme di file in */Library/Application Support/Microsoft/Defender/* creati e usati da Microsoft Defender per Endpoint in macOS
- Sottoinsieme di file in */Library/Managed Preferences* usati da Microsoft Defender per Endpoint in macOS
- /Library/Logs/Microsoft/autoupdate.log
- $HOME/Library/Preferences/com.microsoft.autoupdate2.plist

### <a name="optional-diagnostic-data"></a>Dati di diagnostica facoltativi

**I dati di diagnostica facoltativi** sono dati aggiuntivi che consentono a Microsoft di apportare miglioramenti al prodotto e fornisce informazioni avanzate per rilevare, diagnosticare e risolvere i problemi.

Se si sceglie di inviare i dati di diagnostica facoltativi, saranno inclusi anche i dati indispensabili.

Esempi di dati di diagnostica facoltativi includono i dati raccolti da Microsoft sulla configurazione del prodotto (ad esempio il numero di esclusioni impostate nel dispositivo) e sulle prestazioni del prodotto (misure aggregate sulle prestazioni dei componenti del prodotto).

#### <a name="software-setup-and-inventory-data-events"></a>Eventi dati Configurazione e inventario software

**Configurazione di Microsoft Defender per endpoint**

Vengono raccolti i campi seguenti:

| Campo                                              | Descrizione |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | Timeout del tentativo di connessione durante la comunicazione con il cloud. |
| file_hash_cache_maximum                            | Dimensioni della cache del prodotto. |
| crash_upload_daily_limit                           | Limite dei log di arresto anomalo caricati ogni giorno. |
| antivirus_engine.exclusions[].is_directory         | Indica se l'esclusione dall'analisi è una directory o meno. |
| antivirus_engine.exclusions[].path                 | Percorso escluso dall'analisi. |
| antivirus_engine.exclusions[].extension            | Estensione esclusa dalla scansione. |
| antivirus_engine.exclusions[].name                 | Nome del file escluso dall'analisi. |
| antivirus_engine.scan_cache_maximum                | Dimensioni della cache del prodotto. |
| antivirus_engine.maximum_scan_threads              | Numero massimo di thread utilizzati per l'analisi. |
| antivirus_engine.threat_restoration_exclusion_time | Timeout prima che un file ripristinato dalla quarantena possa essere rilevato di nuovo. |
| antivirus_engine.threat_type_settings              | Configurazione per la modalità di gestione dei diversi tipi di minacce da parte del prodotto. |
| filesystem_scanner.full_scan_directory             | Directory di analisi completa. |
| filesystem_scanner.quick_scan_directories          | Elenco delle directory utilizzate per l'analisi rapida. |
| edr.latency_mode                                   | Modalità di latenza utilizzata dal componente di rilevamento e risposta. |
| edr.proxy_address                                  | Indirizzo proxy utilizzato dal componente di rilevamento e risposta. |

**Configurazione di Aggiornamento automatico Microsoft**

Vengono raccolti i campi seguenti:

| Campo                       | Descrizione |
| --------------------------- | ----------- |
| how_to_check                | Determina la modalità di controllo degli aggiornamenti dei prodotti, ad esempio automatici o manuali. |
| channel_name                | Canale di aggiornamento associato al dispositivo. |
| manifest_server             | Server utilizzato per il download degli aggiornamenti. |
| update_cache                | Percorso della cache utilizzata per archiviare gli aggiornamenti. |

### <a name="product-and-service-usage"></a>Uso di prodotti e servizi

#### <a name="diagnostic-log-upload-started-report"></a>Rapporto di caricamento del log di diagnostica avviato

Vengono raccolti i campi seguenti:

| Campo            | Descrizione |
| ---------------- | ----------- |
| sha256           | Identificatore SHA256 del registro di supporto. |
| size             | Dimensioni del registro di supporto. |
| original_path    | Percorso del registro di supporto (sempre in */Library/Application Support/Microsoft/Defender/wdavdiag/*). |
| format           | Formato del registro di supporto. |

#### <a name="diagnostic-log-upload-completed-report"></a>Rapporto caricamento log diagnostica completato

Vengono raccolti i campi seguenti:

| Campo            | Descrizione |
| ---------------- | ----------- |
| request_id       | ID di correlazione per la richiesta di caricamento del log di supporto. |
| sha256           | Identificatore SHA256 del registro di supporto. |
| blob_sas_uri     | URI utilizzato dall'applicazione per caricare il log di supporto. |

#### <a name="product-and-service-performance-data-events"></a>Eventi dati di Prestazioni di prodotti e servizi

**Chiusura imprevista (arresto anomalo) dell'applicazione**

Chiusure impreviste dell'applicazione e stato dell'applicazione al momento dell'evento.

**Statistiche dell'estensione kernel**

Vengono raccolti i campi seguenti:

| Campo                          | Descrizione |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | Le proprietà seguenti sono valori numerici aggregati, che rappresentano il numero di eventi che si sono verificati dopo l'avvio dell'estensione del kernel. |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc.ack.timeout                  | |
| ipc.ack.ackd_fast                | |
| ipc.ack.ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| ipc.kauth.vnode.mask             | |
| ipc.kauth.vnode.read             | |
| ipc.kauth.vnode.write            | |
| ipc.kauth.vnode.exec             | |
| ipc.kauth.vnode.del              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| ipc.kauth.vnode.create           | |
| ipc.kauth.vnode.move             | |
| ipc.kauth.vnode.mount            | |
| ipc.kauth.vnode.denied           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op.mask           | |
| ipc.kauth_file_op.open           | |
| ipc.kauth.file_op.close          | |
| ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op.move           | |
| ipc.kauth.file_op.link           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op.remove         | |
| ipc.kauth.file_op.unmount        | |
| ipc.kauth.file_op.fork           | |
| ipc.kauth.file_op.create         | |

## <a name="resources"></a>Risorse

- [Privacy di Microsoft](https://privacy.microsoft.com/)
