---
title: Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint
description: Informazioni su come Microsoft Defender for Endpoint gestisce la privacy e i dati raccolti.
keywords: Microsoft Defender for Endpoint, archiviazione e privacy dei dati, archiviazione, privacy, licenze, georilevazione, conservazione dei dati, dati
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0258b2cdbff4a8b20be42e508863985c7402f609
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845511"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Questa sezione illustra alcune delle domande più frequenti sulla privacy e sulla gestione dei dati per Defender per Endpoint.
> [!NOTE]
> In questo documento vengono illustrati i dettagli sull'archiviazione dei dati e sulla privacy relativi a Defender for Endpoint. Per altre informazioni relative a Defender for Endpoint e ad altri prodotti e servizi come Antivirus Microsoft Defender e Windows 10, vedi Informativa [sulla privacy Microsoft.](https://go.microsoft.com/fwlink/?linkid=827576) Vedi anche domande [Windows 10 sulla privacy per](https://go.microsoft.com/fwlink/?linkid=827577) altre informazioni.


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Quali dati vengono raccolti da Microsoft Defender per Endpoint?

Microsoft Defender for Endpoint raccoglierà e archivierà le informazioni dai dispositivi configurati in un tenant dedicato e segregato del cliente specifico per il servizio per scopi di amministrazione, monitoraggio e creazione di report. 

Le informazioni raccolte includono dati di file (ad esempio nomi di file, dimensioni e hash), dati di processo (processi in esecuzione, hash), dati del Registro di sistema, dati di connessione di rete (IP host e porte) e dettagli del dispositivo (ad esempio identificatori di dispositivo, nomi e versione del sistema operativo).

Microsoft archivia questi dati in modo sicuro Microsoft Azure e li mantiene in conformità alle procedure di privacy microsoft e ai criteri del Centro protezione [Microsoft.](https://go.microsoft.com/fwlink/?linkid=827578)

Questi dati consentono a Defender for Endpoint di:
- Identificare in modo proattivo gli indicatori di attacco (IOA) nell'organizzazione
- Generare avvisi se è stato rilevato un possibile attacco
- Fornire alle operazioni di sicurezza una visualizzazione di dispositivi, file e URL correlati ai segnali di minaccia provenienti dalla rete, consentendo di analizzare ed esplorare la presenza di minacce alla sicurezza nella rete.

Microsoft non usa i dati per la pubblicità.

## <a name="data-protection-and-encryption"></a>Protezione e crittografia dei dati
Il servizio Defender for Endpoint utilizza tecnologie di protezione dei dati all'avanguardia basate sull'Microsoft Azure aziendale. 

Esistono diversi aspetti rilevanti per la protezione dei dati di cui si occupa il nostro servizio. La crittografia è una delle più critiche e include la crittografia dei dati in fase di pausa, la crittografia in fase di fuga e la gestione delle chiavi con Key Vault. Per altre informazioni sulle altre tecnologie usate dal servizio Defender for Endpoint, vedi Panoramica [della crittografia di Azure.](/azure/security/security-azure-encryption-overview) 

In tutti gli scenari, i dati vengono crittografati utilizzando almeno la crittografia [AES a](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 256 bit.


## <a name="data-storage-location"></a>Posizione di archiviazione dei dati

Defender for Endpoint opera nei Microsoft Azure datacenter nell'Unione Europea, nel Regno Unito o negli Stati Uniti. I dati dei clienti raccolti dal servizio possono essere archiviati in: (a) la posizione geografica del tenant identificata durante il provisioning o (b) se Defender for Endpoint usa un altro servizio online Microsoft per elaborare tali dati, la georilevazione come definita dalle regole di archiviazione dei dati di quell'altro servizio online.

I dati dei clienti in formato pseudonimo possono essere archiviati anche nei sistemi di archiviazione e trattamento centrali negli Stati Uniti.

Dopo la configurazione, non è possibile modificare la posizione in cui sono archiviati i dati. In questo modo è possibile ridurre al minimo i rischi di conformità selezionando attivamente le posizioni geografiche in cui risiederanno i dati. 

## <a name="is-my-data-isolated-from-other-customer-data"></a>I dati sono isolati da altri dati dei clienti?
Sì, i dati vengono isolati tramite l'autenticazione di accesso e la separazione logica in base all'identificatore del cliente. Ogni cliente può accedere solo ai dati raccolti dalla propria organizzazione e ai dati generici forniti da Microsoft.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>In che modo Microsoft impedisce attività insider dannose e l'abuso di ruoli con privilegi elevati?

Per progettazione, agli sviluppatori e agli amministratori Microsoft sono stati assegnati privilegi sufficienti per svolgere i compiti assegnati per operare ed evolvere il servizio. Microsoft distribuisce combinazioni di controlli preventivi, detective e reattivi, inclusi i meccanismi seguenti per proteggere da attività amministrative e/o di sviluppo non autorizzate:

- Controllo dell'accesso limitato ai dati sensibili
- Combinazioni di controlli che migliorano notevolmente il rilevamento indipendente di attività dannose
- Più livelli di monitoraggio, registrazione e creazione di report

Inoltre, Microsoft esegue controlli di verifica in background di determinati membri del personale operativo e limita l'accesso ad applicazioni, sistemi e infrastrutture di rete in proporzione al livello di verifica in background. Il personale operativo segue un processo formale quando è richiesto di accedere all'account di un cliente o alle informazioni correlate nell'esecuzione dei propri compiti.

L'accesso ai dati per i servizi distribuiti nei data center di Microsoft Azure Government è concesso solo al personale operativo che è stato sottoposto a controllo e approvato per gestire i dati soggetti a determinate normative e requisiti governativi, come FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 e CJIS.


## <a name="is-data-shared-with-other-customers"></a>I dati vengono condivisi con altri clienti?
No. I dati dei clienti sono isolati da altri clienti e non vengono condivisi. Tuttavia, le informazioni dettagliate sui dati risultanti dall'elaborazione Microsoft e che non contengono dati specifici del cliente potrebbero essere condivise con altri clienti. Ogni cliente può accedere solo ai dati raccolti dalla propria organizzazione e ai dati generici forniti da Microsoft.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Per quanto tempo Microsoft archivierà i miei dati? Qual è il criterio di conservazione dei dati di Microsoft?
**Onboarding del servizio**<br>
Per impostazione predefinita, i dati vengono conservati per 180 giorni. tuttavia, è possibile specificare i criteri di conservazione dei dati per i dati. Questo determina per quanto tempo Window Defender for Endpoint archivierà i dati. È possibile scegliere tra un mese e sei mesi per soddisfare le esigenze di conformità normativa dell'azienda.

**Alla scadenza o alla risoluzione del contratto**<br>
I dati verranno mantenuti e saranno disponibili mentre la licenza è in modalità di tolleranza o sospesa. Al termine di questo periodo, tali dati verranno cancellati dai sistemi Microsoft per renderli irrecuperabili, non oltre 180 giorni dalla scadenza o dalla risoluzione del contratto.

**Dati di ricerca avanzata**<br>
La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni.


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Microsoft può aiutarci a mantenere la conformità normativa?

Microsoft fornisce ai clienti informazioni dettagliate sui programmi di sicurezza e conformità di Microsoft, inclusi report di controllo e pacchetti di conformità, per aiutare i clienti a valutare Defender per i servizi endpoint in base ai propri requisiti legali e normativi. Defender for Endpoint ha ottenuto una serie di certificazioni tra cui ISO, SOC, FedRAMP High e PCI e continua a perseguire ulteriori certificazioni nazionali, regionali e specifiche del settore.

Fornendo ai clienti servizi conformi e verificati in modo indipendente, Microsoft agevola il raggiungimento della conformità per l'infrastruttura e le applicazioni eseguite.

Per altre informazioni sui report sulla certificazione Defender for Endpoint, vedi [Centro protezione Microsoft.](https://servicetrust.microsoft.com/) 

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
