---
title: Notifica relativa al servizio di trattamento dei dati per Windows Enterprise ai sensi del GDPR
description: Informazioni su come il servizio di trattamento dei dati per Windows Enterprise tutela da una violazione dei dati personali e su come Microsoft gestisce un'eventuale violazione e lo comunica agli interessati.
keywords: Servizio di trattamento dei dati per Windows Enterprise, Microsoft 365, documentazione di Microsoft 365, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 30fefe49dbbe1bffa0447d66695431d30342b843
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843140"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>Notifica di violazione relativa al servizio di trattamento dei dati per Windows Enterprise ai sensi del GDPR

>[!NOTE]
>Questo argomento è rivolto ai partecipanti al servizio di trattamento dei dati per il programma di anteprima di Windows Enterprise e richiede l'accettazione di specifiche condizioni d'uso. Per maggiori informazioni sul programma e per l'accettazione delle condizioni d'uso, vedere [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Per il servizio di trattamento dei dati per Windows Enterprise di Microsoft, il rispetto degli obblighi derivanti dal Regolamento generale sulla protezione dei dati (GDPR) è importante. Il servizio di trattamento dei dati per Windows Enterprise di Microsoft adotta ampie misure di sicurezza per proteggere gli utenti dalle violazioni dei dati. Queste includono team dedicati alla gestione delle minacce che prevedono, prevengono e riducono proattivamente il rischio di accessi dannosi.Le misure di sicurezza interne quali scansione porte, analisi delle vulnerabilità dei perimetri e rilevamento delle intrusioni rilevano e prevengono gli accessi dannosi, così come i processi di sicurezza automatizzati, criteri completi di sicurezza e privacy delle informazioni e formazione sulla sicurezza e sulla privacy per tutto il personale. 

La sicurezza è integrata nel servizio di trattamento dei dati per Windows Enterprise di Microsoft, a partire dal [Security Development Lifecycle](https://www.microsoft.com/sdl/), un processo di sviluppo obbligatorio che incorpora le metodologie di privacy by design e privacy by default. Il principio guida della strategia di sicurezza di Microsoft consiste nel "presumere la violazione", configurandosi come un'estensione della strategia di difesa completa. Mettendo costantemente alla prova le funzionalità di sicurezza del servizio di trattamento dei dati per Windows Enterprise, Microsoft può stare al passo con le minacce emergenti. Per ulteriori informazioni sulla sicurezza del servizio di trattamento dei dati per Windows Enterprise, consultare queste [risorse](https://www.microsoft.com/TrustCenter/Security/windows10-security). Il servizio di trattamento dei dati per Windows Enterprise risponde a una potenziale violazione dei dati in base al processo di risposta agli incidenti di sicurezza. La risposta agli incidenti di sicurezza del servizio di trattamento dei dati per Windows Enterprise viene implementata tramite un processo costituito da cinque fasi: rilevamento, valutazione, diagnostica, stabilizzazione e chiusura. Il team di risposta in caso di incidenti di sicurezza può alternare le fasi di diagnosi e stabilizzazione man mano che l'indagine procede. Di seguito è riportata una panoramica del processo di risposta in caso di incidenti di sicurezza: 

|**Fase**|**Descrizione**|
| ------- | ------------- |
| **_1 — Rilevamento_* _ | Prima indicazione di un potenziale incidente. |
| _*_2 — Valutazione_*_ | Un tecnico di turno del team di intervento per gli incidenti valuta l'impatto e la gravità dell'incidente. Secondo le prove raccolte, la valutazione può comportare o meno un'ulteriore escalation al team di intervento della sicurezza. |
| _*_3 — Diagnostica_*_ | Gli esperti del team di intervento della sicurezza svolgono le indagini tecniche o forensi, identificano le strategie di contenimento, mitigazione e le soluzioni alternative. Se il team della sicurezza ritiene che i dati del cliente potrebbero essere stati esposti a un individuo non autorizzato o a un criminale, il processo di notifica dell'incidente al cliente si svolge in parallelo. |
| _*_4 — Stabilizzazione e ripristino_*_ | Il team di intervento per gli incidenti crea un piano di ripristino per mitigare il problema. Le misure di contenimento della crisi, come l'applicazione della quarantena ai sistemi colpiti, possono verificarsi immediatamente e parallelamente alla fase di diagnosi. Si possono pianificare misure di mitigazione a lungo termine da implementare dopo che è passato il rischio immediato. |
| _*_5 — Chiusura e relazione finale_*_ | Il team di intervento per gli incidenti crea una relazione finale dettagliata dell'incidente finalizzata alla revisione di criteri, procedure e interventi per prevenire il ripetersi dell'evento. |

I processi di rilevamento utilizzati dal servizio di trattamento dei dati per Windows Enterprise di Microsoft sono progettati per rilevare eventi che mettono a rischio la riservatezza, l'integrità e la disponibilità dei servizi del servizio di trattamento dei dati per Windows Enterprise. Diversi eventi possono dare il via a un'indagine: 

 - Avvisi di sistema automatici tramite framework di monitoraggio e avviso interni. Questi avvisi potrebbero interferire con avvisi basati su firma come antimalware, rilevamento di intrusioni o tramite algoritmi progettati per tracciare il profilo dell'attività prevista e segnalare anomalie.
 - Report di prima parte dei servizi Microsoft in esecuzione su Microsoft Azure e Azure per enti pubblici.
 - Le vulnerabilità di sicurezza vengono segnalate a [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) tramite [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC collabora con partner e ricercatori di sicurezza di tutto il mondo per prevenire gli incidenti e migliorare la sicurezza dei prodotti Microsoft.
 - Report dei clienti tramite il portale del supporto tecnico o il portale di Microsoft Azure e Azure per enti pubblici, che descrivono attività sospette attribuite all'infrastruttura di Azure (al contrario delle attività che si verificano nell'ambito di responsabilità del cliente).
 - Attività di [Red Team e Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) per la sicurezza. Questa strategia utilizza un Red Team altamente qualificato di esperti di sicurezza offensiva di Microsoft per individuare e attaccare potenziali vulnerabilità in Azure. Il Blue Team di intervento per la sicurezza deve rilevare e difendersi dall'attività del Read Team. Le azioni del Red team e del Blue Team vengono usate per verificare che gli interventi per la sicurezza di Azure gestiscano in modo efficace gli incidenti. Le attività di sicurezza del Red Team e del Blue Team vengono gestite secondo regole di ingaggio per garantire la protezione dei dati dei clienti.
 - Escalation da parte degli operatori di servizi di Azure. I dipendenti Microsoft sono addestrati per identificare e inoltrare potenziali problemi riguardanti la sicurezza.

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Risposta alle violazioni dei dati nel servizio di trattamento dei dati per Windows Enterprise 

 Microsoft assegna all'indagine adeguati livelli di priorità e gravità determinando l'impatto funzionale, la recuperabilità e l'impatto dell'evento sulle informazioni. La priorità e la gravità possono cambiare nel corso dell'indagine sulla base di nuove scoperte e conclusioni. Gli eventi di sicurezza che comportano rischi imminenti o confermati per i dati del cliente sono considerati di gravità elevata e vengono seguiti 24 ore su 24 fino a quando non vengono risolti. Il servizio di trattamento dei dati per Windows Enterprise di Microsoft classifica l'impatto dell'incidente sulle informazioni nelle seguenti categorie di violazione: 

| _ *Categoria**             | **Definizione**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Nessuna_* _               | Nessuna informazione è stata rimossa, modificata, cancellata o comunque compromessa. |
| _*_Violazione della privacy_*_     | È stato possibile accedere o rimuovere dati personali sensibili riguardanti i contribuenti, i dipendenti, i beneficiari e così via. |
| _*_Violazioni di proprietà_*_ | È stato possibile accedere o rimuovere informazioni proprietarie non classificate, ad esempio informazioni riguardanti l'infrastruttura critica protetta (PCII). |
| _*_Perdita di integrità_*_     | Sono state modificate o cancellate informazioni sensibili o proprietarie. |

Il team di Security Response collabora con il servizio di trattamento dei dati di Microsoft per Windows Enterprise Security Engineers e SME al fine di classificare l'evento sulla base di dati concreti tratti dalle prove raccolte. Un evento di sicurezza può essere classificato come: 

 - *Falso positivo**: un evento che soddisfa i criteri di rilevamento ma che risulta essere parte di una normale pratica aziendale e può avere bisogno di essere filtrato. Il team del servizio identificherà la causa principale dei falsi positivi e li risolverà in modo sistematico sfruttando le fonti di rilevamento e ottimizzandole se necessario. 
 - **Incidente di sicurezza** : un accesso illecito o non autorizzato ai dati del cliente o ai dati di supporto archiviati nelle apparecchiature o strutture Microsoft che ha provocato la perdita, la divulgazione o l'alterazione dei dati del cliente o dei dati di supporto. 
 - **Incidente di sicurezza segnalabile dal cliente (CRSI)** : un accesso o un utilizzo illecito o non autorizzato dei sistemi, delle apparecchiature o strutture Microsoft che ha provocato la divulgazione, la modifica o la perdita dei dati del cliente. 
 - **Violazione della privacy** : un sottotipo di incidente di sicurezza che coinvolge dati personali. Le procedure di gestione non sono diverse da un incidente di sicurezza. 

 Affinché un incidente di sicurezza segnalabile dal cliente possa essere dichiarato, Microsoft deve stabilire che l'accesso non autorizzato ai dati del cliente è avvenuto o molto probabilmente si è verificato e/o che esiste un impegno legale o contrattuale perché si verifichi la notifica. È auspicabile, ma non è necessario, conoscere lo specifico impatto sul cliente, l'accesso alle risorse e i passaggi di ripristino. Un incidente di sicurezza è generalmente dichiarato incidente di sicurezza segnalabile dal cliente dopo la conclusione della fase di diagnosi; tuttavia, la dichiarazione può avvenire in qualsiasi momento in cui tutte le informazioni pertinenti siano disponibili. Il responsabile dell'incidente deve stabilire oltre ogni ragionevole dubbio che si è verificato un evento da segnalare per iniziare l'esecuzione del Processo di notifica dell'incidente del cliente. 

Durante l'indagine, il team di intervento per la sicurezza lavora a stretto contatto con i consulenti legali globali per contribuire a garantire che le analisi forensi siano eseguite in conformità con gli obblighi legali e gli impegni nei confronti dei clienti. Esistono anche limitazioni significative sulla visualizzazione e gestione dei dati del sistema e del cliente in vari ambienti operativi. I dati sensibili o riservati, così come i dati del cliente, non vengono trasferiti fuori dall'ambiente di produzione senza un'approvazione scritta esplicita da parte del responsabile dell'incidente registrato nel ticket dell'incidente corrispondente. 

Microsoft verifica che il rischio per il cliente e per l'azienda sia contenuto e che vengano implementate misure correttive. Se necessario, vengono adottate misure di attenuazione dell'emergenza per risolvere i rischi di sicurezza immediati associati all'evento. 

Microsoft completa anche una relazione finale interna per violazioni dei dati. Come parte di questo esercizio, sono state valutate la sufficienza delle procedure di risposta e di funzionamento, e gli eventuali aggiornamenti che potrebbero essere necessari al SOP o ai processi correlati sono identificati e implementati. La relazione finale interna per violazioni dei dati è un registro altamente riservato che non è disponibile per i clienti. Le relazioni finali, tuttavia, possono essere riepilogate e incluse nelle altre notifiche di eventi relative al cliente. Questi report vengono forniti ai revisori esterni per la revisione come parte del ciclo di controllo di routine del servizio di trattamento dei dati per Windows Enterprise. 

## <a name="customer-notice"></a>Comunicazione ai clienti

Il servizio di trattamento dei dati per Windows Enterprise di Microsoft informa i clienti e le autorità competenti delle violazioni dei dati come richiesto. Microsoft si basa su una forte compartimentazione interna nel funzionamento del servizio di trattamento dei dati per Windows Enterprise. Anche i registri del flusso di dati sono solidi. Un vantaggio di questa struttura è che la maggior parte degli incidenti può essere ricondotta a clienti specifici. L'obiettivo è fornire ai clienti interessati una comunicazione accurata, attuabile e tempestiva nel momento in cui i dati vengono violati. 

Dopo aver dichiarato un CRSI, il processo di notifica si verificherà nel modo più rapido possibile, pur considerando i rischi per la sicurezza di tale rapidità. In generale, il processo di stesura delle notifiche avviene quando è in corso l'indagine sull'incidente. Le notifiche ai clienti vengono recapitate entro 72 ore dall’identificazione di una violazione tranne nei casi seguenti: 

 - Microsoft ritiene che l'atto di esecuzione di una notifica aumenti il rischio per gli altri clienti. Ad esempio, l'atto di notifica può allertare un avversario causando l'impossibilità di porvi rimedio. 
 - Altre circostanze insolite o estreme esaminate dall'ufficio legale di Microsoft (CELA) e dall'Executive Incident Manager. 

 Il servizio di trattamento dei dati per Windows Enterprise di Microsoft fornisce ai clienti informazioni dettagliate che consentono loro di svolgere indagini interne e di assisterli nell'adempimento degli impegni assunti con l'utente finale, senza ritardare ingiustificatamente il processo di notifica. 

La notifica di una violazione dei dati personali verrà recapitata al cliente con qualsiasi mezzo Microsoft selezioni, anche tramite posta elettronica. La notifica di una violazione dei dati verrà recapitata all'elenco dei contatti di sicurezza disponibili nell' *di Azure Defender, che può essere configurata seguendo le indicazioni di [implementazione](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se le informazioni sui contatti non sono disponibili in Azure Defender* , la notifica viene inviata a uno o più amministratori di un abbonamento ad Azure. Per fare in modo che la notifica possa essere recapitata correttamente, il cliente è tenuto a verificare la correttezza delle informazioni sui contatti amministrativi relative a ogni sottoscrizione e portale dei servizi online applicabile.

Il team del Servizio di trattamento dei dati aziendali per Windows può anche decidere di informare altri membri del personale Microsoft, ad esempio il Supporto tecnico (CSS), e l'Account Manager (AM) o il Technical Account Manager (TAM) del cliente. Tali figure hanno spesso strette relazioni con il cliente e possono facilitare una correzione più rapida. 

Per ulteriori informazioni su come Microsoft rileva e interviene a un caso di violazione dei dati personali, vedere [Notifica di violazione dei dati secondo il GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) nel Service Trust Portal.
