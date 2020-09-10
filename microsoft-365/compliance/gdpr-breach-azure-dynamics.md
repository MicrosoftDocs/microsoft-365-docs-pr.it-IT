---
title: Notifica di violazione nell'ambito del GDPR in Azure e Dynamics 365
description: Informazioni su come Azure e Dynamics 365 proteggono da una violazione dei dati personali e su come Microsoft gestisce un'eventuale violazione e lo comunica agli utenti interessati.
keywords: Azure, Microsoft 365, Dynamics 365, documentazione di Microsoft 365, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 838e2ee09ea80f07c637eeebd1229b63f01ad00b
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415900"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Notifica di violazione nell'ambito del GDPR in Azure e Dynamics 365

Microsoft Azure prende in seria considerazione gli obblighi previsti dal Regolamento generale sulla protezione dei dati (GDPR). Microsoft Azure adotta ampie misure di sicurezza per proteggere dalle violazioni dei dati. Queste includono controlli di sicurezza sia fisici che logici, così come interventi di sicurezza automatizzati, criteri completi di sicurezza delle informazioni e privacy, nonché formazione sulla sicurezza e sulla privacy per tutto il personale.

La sicurezza è integrata in Microsoft Azure, a partire dal [Security Development Lifecycle](https://www.microsoft.com/sdl/), un processo di sviluppo obbligatorio che incorpora le metodologie di privacy by design e privacy by default. Il principio guida della strategia di sicurezza di Microsoft consiste nel "rappresentare la violazione", che è un'estensione della strategia di difesa completa. Mettendo costantemente alla prova le funzionalità di sicurezza di Azure, Microsoft può stare al passo con le minacce emergenti. Per ulteriori informazioni sulla sicurezza di Azure, consultare queste [risorse](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft ha un servizio di intervento a un incidente globale disponibile 24 ore su 24, 7 giorni su 7, che opera per mitigare gli effetti degli attacchi contro Microsoft Azure. Attestato da più controlli di sicurezza e conformità (ad es. [ISO/IEC 27018](offering-iso-27018.md)), Microsoft impiega rigorose operazioni e interventi nei suoi data center per prevenire accessi non autorizzati, tra cui monitoraggio video disponibile 24 ore su 24, 7 giorni su 7, personale di sicurezza addestrato, smart card e controlli biometrici.

## <a name="detection-of-potential-breaches"></a>Rilevamento di potenziali violazioni

Vista la natura del cloud computing moderno, non tutte le violazioni dei dati che si verificano in un ambiente cloud cliente coinvolgono i servizi di Microsoft Azure. Microsoft adotta un modello di responsabilità condivisa per i servizi di Azure per definire le responsabilità operative e di sicurezza. La responsabilità condivisa è un aspetto importante quando si parla di sicurezza di un servizio cloud, poiché sia il fornitore di servizi cloud sia il cliente sono responsabili di diverse parti della sicurezza del cloud.

Microsoft non monitora né risponde agli incidenti di sicurezza nell'ambito di responsabilità del cliente. Un compromesso di sicurezza esclusivo per cliente non verrebbe trattato come un incidente di sicurezza di Azure e richiederebbe al tenant del cliente di gestire l'intervento. L'intervento del cliente in caso di incidente può implicare la collaborazione con il [supporto tecnico](https://azure.microsoft.com/support/options/) di Microsoft Azure, in base ai contratti di servizio appropriati. Microsoft Azure offre inoltre vari servizi (ad es., [Centro sicurezza di Azure](https://azure.microsoft.com/services/security-center/)) che i clienti possono utilizzare per lo sviluppo e la gestione dell'intervento in caso di incidente di sicurezza.

Azure interviene a una potenziale violazione dei dati in base al processo di intervento all'incidente di sicurezza, che è un sottoinsieme del piano di gestione degli incidenti di Microsoft Azure. L'intervento all'incidente di sicurezza di Azure viene implementata utilizzando un intervento a cinque fasi: Rilevamento, Valutazione, Diagnostica, Stabilizzazione e Chiusura. Il team di intervento in caso di incidenti di sicurezza può alternare le fasi di diagnosi e stabilizzazione man mano che l'indagine procede. Di seguito è riportata una panoramica del processo di intervento in caso di incidenti di sicurezza:

|**Fase**|**Descrizione**|
| ------- | ------------- |
| ***1 - Rilevamento*** | Prima indicazione di un potenziale incidente. |
| ***2 - Valutazione*** | Un tecnico di turno del team di intervento per gli incidenti valuta l'impatto e la gravità dell'incidente. Secondo le prove raccolte, la valutazione può comportare o meno un'ulteriore escalation al team di intervento della sicurezza. |
| ***3 - Diagnostica*** | Gli esperti del team di intervento della sicurezza svolgono le indagini tecniche o forensi, identificano le strategie di contenimento, mitigazione e le soluzioni alternative. Se il team della sicurezza ritiene che i dati del cliente potrebbero essere stati esposti a un individuo non autorizzato o a un criminale, il processo di notifica dell'incidente al cliente si svolge in parallelo. |
| ***4 - Stabilizzazione e ripristino*** | Il team di intervento per gli incidenti crea un piano di ripristino per mitigare il problema. Le misure di contenimento della crisi, come l'applicazione della quarantena ai sistemi colpiti, possono verificarsi immediatamente e parallelamente alla fase di diagnosi. Si possono pianificare misure di mitigazione a lungo termine da implementare dopo che è passato il rischio immediato. |
| ***5 - Chiusura e relazione finale*** | Il team di intervento per gli incidenti crea una relazione finale dettagliata dell'incidente finalizzata alla revisione di criteri, procedure e interventi per prevenire il ripetersi dell'evento. |

Il white paper di [Microsoft Azure Security Response nel cloud](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) fornisce ulteriori dettagli su come Microsoft indaga, gestisce e interviene agli incidenti di sicurezza all'interno di Azure.

I processi di rilevamento utilizzati da Microsoft Azure sono progettati per rilevare eventi che mettono a rischio la riservatezza, l'integrità e la disponibilità dei servizi di Azure. Diversi eventi possono dare il via a un'indagine:

- Avvisi di sistema automatici tramite framework di monitoraggio e avviso interni. Questi avvisi potrebbero interferire con avvisi basati su firma come antimalware, rilevamento di intrusioni o tramite algoritmi progettati per tracciare il profilo dell'attività prevista e segnalare anomalie.
- Report di prima parte dei servizi Microsoft in esecuzione su Microsoft Azure e Azure per enti pubblici.
- Le vulnerabilità di sicurezza vengono segnalate a [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) tramite [secure@microsoft.com](mailto:secure@microsoft.com). MSRC collabora con partner e ricercatori di sicurezza di tutto il mondo per prevenire incidenti e migliorare la sicurezza dei prodotti Microsoft.
- Report dei clienti tramite il [Portale di supporto tecnico](https://www.windowsazure.com/support/contact/) o il portale di Microsoft Azure e Azure per enti pubblici, che descrivono attività sospette attribuite all'infrastruttura di Azure (al contrario delle attività che si verificano nell'ambito di responsabilità del cliente).
- Attività di [Red Team e Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) per la sicurezza. Questa strategia utilizza un Red Team altamente qualificato di esperti di sicurezza offensiva di Microsoft per individuare e attaccare potenziali vulnerabilità in Azure. Il Blue Team di intervento per la sicurezza deve rilevare e difendersi dall'attività del Read Team. Le azioni del Red team e del Blue Team vengono usate per verificare che gli interventi per la sicurezza di Azure gestiscano in modo efficace gli incidenti. Le attività di sicurezza del Red Team e del Blue Team vengono gestite secondo regole di ingaggio per garantire la protezione dei dati dei clienti.
- Escalation da parte degli operatori di servizi di Azure. I dipendenti Microsoft sono addestrati per identificare e inoltrare potenziali problemi riguardanti la sicurezza.

## <a name="azures-data-breach-response"></a>Intervento in caso di violazione dei dati di Azure

Microsoft assegna all'indagine adeguati livelli di priorità e gravità determinando l'impatto funzionale, la recuperabilità e l'impatto dell'evento sulle informazioni. La priorità e la gravità possono cambiare nel corso dell'indagine sulla base di nuove scoperte e conclusioni. Gli eventi di sicurezza che comportano rischi imminenti o confermati per i dati del cliente sono considerati di gravità elevata e vengono seguiti 24 ore su 24 fino a quando non vengono risolti. 

Microsoft Azure classifica l'impatto dell'evento sulle informazioni nelle seguenti categorie di violazione:

| **Categoria**             | **Definizione**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***Nessuna***               | Nessuna informazione è stata estratta, modificata, cancellata o comunque compromessa.                                                      |
| ***Violazione della privacy***     | È stato possibile accedere o estrarre dati personali sensibili riguardanti i contribuenti, i dipendenti, i beneficiari e così via.                                |
| ***Violazioni di proprietà*** | È stato possibile accedere o estrarre informazioni proprietarie non classificate, ad esempio informazioni riguardanti l'infrastruttura critica protetta (PCII). |
| ***Perdita di integrità***     | Sono state modificate o cancellate informazioni sensibili o proprietarie.                                                                     |

Il team di Security Response collabora con Microsoft Azure Security Engineers e SME per classificare l'evento sulla base di dati concreti tratti dalle prove raccolte. Un incidente di sicurezza può essere classificato come:

- **Falso positivo**: un evento che soddisfa i criteri di rilevamento ma che risulta essere parte di una normale pratica aziendale e può avere bisogno di essere filtrato. Il team del servizio identifica la causa radice dei falsi positivi e li risolve in modo sistematico usando le fonti di rilevamento e ottimizzandole se necessario.
- **Incidente di sicurezza**: un accesso illecito o non autorizzato ai dati del cliente o ai dati di supporto archiviati nei dispositivi o nelle sedi Microsoft che ha provocato la perdita, la divulgazione o l'alterazione dei dati del cliente o dei dati di supporto.
- **Incidente di sicurezza/privacy segnalabile dal cliente (CRSPI)**: un accesso o un utilizzo illecito o non autorizzato dei sistemi, dei dispositivi o delle sedi Microsoft che ha provocato la divulgazione, la modifica o la perdita dei dati del cliente.
- **Violazione della privacy**: un sottotipo di incidente di sicurezza che coinvolge dati personali. Le procedure di gestione non sono diverse da un incidente di sicurezza.

Per dichiarare un CRSPI, Microsoft deve stabilire che l'accesso non autorizzato ai dati del cliente è effettivamente o probabilmente avvenuto e/o che esiste un impegno legale o contrattuale perché la notifica abbia luogo. È auspicabile, ma non obbligatorio, conoscere lo specifico impatto sul cliente, l'accesso alle risorse e i passaggi di ripristino. Un incidente viene generalmente dichiarato un CRSPI dopo la conclusione della fase diagnostica di un incidente di sicurezza. Tuttavia, la dichiarazione può avvenire in qualsiasi momento, in modo che tutte le informazioni pertinenti siano disponibili. Il responsabile per gli incidenti di sicurezza deve trovare delle prove oltre ogni ragionevole dubbio che si sia verificato un evento segnalabile per avviare l'esecuzione del processo di notifica sull'incidente del cliente.

Durante l'indagine, il team di intervento per la sicurezza lavora a stretto contatto con i consulenti legali globali per contribuire a garantire che le analisi forensi siano eseguite in conformità con gli obblighi legali e gli impegni nei confronti dei clienti. Esistono anche limitazioni significative sulla visualizzazione e gestione dei dati del sistema e del cliente in vari ambienti operativi. I dati sensibili o riservati, così come i dati del cliente, non vengono trasferiti fuori dall'ambiente di produzione senza un'approvazione scritta esplicita da parte del responsabile dell'incidente registrato nel ticket dell'incidente corrispondente.

Microsoft verifica che il rischio per il cliente e per l'azienda sia contenuto e che vengano implementate misure correttive. Se necessario, vengono adottate misure di attenuazione dell'emergenza per risolvere i rischi di sicurezza immediati associati all'evento.

Microsoft completa anche una relazione finale interna per violazioni dei dati. Come parte di questo esercizio, sono state valutate la sufficienza delle procedure di risposta e di funzionamento, e gli eventuali aggiornamenti che potrebbero essere necessari al SOP o ai processi correlati sono identificati e implementati. La relazione finale interna per violazioni dei dati è un registro altamente riservato che non è disponibile per i clienti. Le relazioni finali, tuttavia, possono essere riepilogate e incluse nelle altre notifiche di eventi relative al cliente. Questi report vengono forniti ai revisori esterni per la revisione come parte del ciclo di controllo di routine di Azure.

## <a name="customer-notification"></a>Notifica al cliente

Microsoft Azure notifica le violazioni dei dati ai clienti e agli organismi di certificazione, come richiesto. Microsoft si basa su una forte compartimentazione interna nel funzionamento di Azure. Anche i registri del flusso di dati sono solidi. A vantaggio di questa struttura, la maggior parte degli incidenti può essere indirizzata a clienti specifici. L'obiettivo è fornire ai clienti interessati un avviso accurato, attuabile e tempestivo nel momento in cui i dati vengono violati.

Dopo aver dichiarato un CRSPI, il processo di notifica si verificherà nel modo più rapido possibile, pur considerando i rischi per la sicurezza del passaggio rapido. In generale, il processo di stesura delle notifiche avviene quando l'indagine sull'incidente è in corso. Le notifiche ai cliente vengono recapitate entro 72 ore dall'identificazione di una violazione *tranne* nei casi seguenti:

- Microsoft ritiene che l'esecuzione di una notifica aumenti il rischio per altri clienti. Ad esempio, l'operazione di notifica può allertare un avversario causando l'impossibilità di porvi rimedio.
- Altre circostanze insolite o estreme esaminate dall'ufficio legale di Microsoft (CELA) e dall'Executive Incident Manager.
- La sequenza temporale di 72 ore potrebbe rendere pubblici alcuni dettagli sull'evento. Questi vengono forniti ai clienti e alle autorità di regolamentazione man mano che procedono le indagini.

Microsoft Azure fornisce ai clienti informazioni dettagliate che consentono loro di svolgere indagini interne e di assisterli nell'adempimento degli impegni assunti con l'utente finale, senza ritardare ingiustificatamente il processo di notifica.

La notifica di una violazione dei dati personali verrà recapitata al cliente con qualsiasi mezzo Microsoft selezioni, anche tramite posta elettronica. La notifica di una violazione dei dati verrà inviata all'elenco dei contatti di sicurezza specificato nel Centro sicurezza di Azure, che può essere configurato seguendo le [linee guida per l'implementazione](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se le informazioni sui contatti non sono disponibili nel Centro sicurezza di Azure, la notifica verrà inviata a uno o più amministratori di una sottoscrizione di Azure. Per fare in modo che la notifica possa essere recapitata correttamente, il cliente è tenuto a verificare la correttezza delle informazioni sui contatti amministrativi relative a ogni sottoscrizione e portale dei servizi online applicabile.

Il team di Microsoft Azure o Azure per enti pubblici può anche decidere di notificare ulteriori informazioni al personale Microsoft, ad esempio il servizio clienti (CSS) e l'Account Manager del cliente (AM) o il Technical Account Manager (TAM). Tali figure hanno spesso strette relazioni con il cliente e possono facilitare una correzione più rapida.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Funzionalità di sicurezza integrate in Microsoft Dynamics 365

Microsoft Dynamics 365 si avvale dell'infrastruttura dei servizi del cloud e delle funzionalità di protezione integrate per proteggere i dati attraverso meccanismi e misure di sicurezza. Inoltre, Dynamics 365 fornisce accesso efficiente ai dati e collaborazione con l'integrità dei dati e la privacy nelle aree seguenti: [protezione dell'identità, protezione dei dati, protezione basata sui ruoli e gestione delle minacce](https://www.microsoft.com/trustcenter/security/dynamics365-security).

L'offerta Microsoft Dynamics 365 segue le stesse misure tecniche e organizzative adottate da uno o più team di servizi di Microsoft Azure per garantire la protezione dai processi di violazione dei dati. Di conseguenza, tutte le informazioni riportate nel documento di notifica "Violazioni di dati in Microsoft Azure" sono analoghe a Microsoft Dynamics 365.

## <a name="learn-more"></a>Ulteriori informazioni

[Centro protezione Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
