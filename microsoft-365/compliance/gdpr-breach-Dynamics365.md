---
title: Dynamics 365 e notifica di violazione secondo l'RGPD
description: Informazioni su come Dynamics 365 protegge da una violazione dei dati personali e su come Microsoft gestisce un'eventuale violazione e lo comunica agli utenti interessati.
keywords: Dynamics 365, Microsoft 365, Microsoft 365 Education, Documentazione Microsoft 365, RGPD
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 3ee90c2fbe2684cebbd19376f44fc97d743515db
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286386"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a>Dynamics 365 e notifica di violazione secondo l'RGPD

Per Dynamics 365 gli obblighi previsti dal Regolamento generale sulla protezione dei dati (GDPR) sono una priorità.

Uno degli obiettivi di Microsoft è offrire servizi estremamente sicuri ai clienti di Dynamics 365. Le informazioni contenute in questa sezione forniscono un riepilogo su come Microsoft Dynamics 365 protegge da eventi imprevisti per la sicurezza/violazione dei dati e sul processo seguito per rispondere a tali situazioni e informare i clienti.

#### <a name="microsoft-dynamics-365-built-in-security-features"></a>Funzionalità di sicurezza integrate in Microsoft Dynamics 365

Microsoft Dynamics 365 si avvale dell’infrastruttura dei servizi del cloud e delle funzionalità di protezione integrate per proteggere i dati attraverso meccanismi e misure di sicurezza. Inoltre, Dynamics 365 fornisce accesso efficiente ai dati e collaborazione con l'integrità dei dati e la privacy nelle aree seguenti: [protezione dell’identità, protezione dei dati, protezione basata sui ruoli e gestione delle minacce](https://www.microsoft.com/trustcenter/security/dynamics365-security).

#### <a name="incident-response-training"></a>Formazione su come intervenire in caso di incidenti

A tutti i dipendenti che usano Microsoft Dynamics 365 viene offerto un corso di formazione relativo agli incidenti di sicurezza e alle procedure di intervento adatto al proprio ruolo. Tutti i dipendenti di Microsoft Dynamics 365 completano la formazione al momento dell’assunzione e successivamente partecipano a corsi di aggiornamento annuali. Il corso di formazione fornisce al dipendente le nozioni di base sull'approccio di Microsoft alla sicurezza. Al termine della formazione tutti i dipendenti hanno conoscono:

-   la definizione di un incidente di sicurezza;

-   la responsabilità di tutti i dipendenti di segnalare gli incidenti di sicurezza;

-   come fare l'escalation di un potenziale incidente di sicurezza al team dedicato di Dynamics 365;

-   come il team di intervento di Dynamics 365 opera in caso di incidenti di sicurezza;

-   le problematiche particolari della privacy, in particolare della privacy dei clienti;

-   dove trovare ulteriori informazioni su sicurezza e privacy e contatti di escalation.

#### <a name="how-does-microsoft-dynamics-365-define-security-incident-potential-breaches"></a>Definizione di incidente di sicurezza e violazione dei dati secondo Microsoft Dynamics 365

Un incidente di sicurezza/violazione dei dati si riferisce ad eventi quali, ad esempio, l'accesso illecito ai dati dei clienti archiviati in attrezzature Microsoft o l'accesso non autorizzato a tali attrezzature che è in grado di causare perdita, divulgazione o alterazione dei dati dei clienti. L'obiettivo di Microsoft durante l'intervento in caso di incidenti di sicurezza/violazione dei dati consiste nel proteggere i dati dei clienti e i servizi di Dynamics 365. L’approccio di Microsoft per la gestione di un incidente di sicurezza è conforme al [National Institute of Standards and Technology](https://www.nist.gov/) Special Publication (NIST) (SP) [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf).

Microsoft non monitora gli incidenti che sono di responsabilità del cliente, né internviene in tali casi. Una compromissione che si verifica esclusivamente presso il cliente non viene considerata un incidente di sicurezza di Dynamics 365 e pertanto il tenant del cliente deve gestire l'intervento in tali casi. L'intervento del cliente può necessitare della collaborazione del supporto tecnico di Microsoft Dynamics 365, secondo quanto previsto dai relativi contratti di servizio.

#### <a name="detection-of-potential-breaches"></a>Rilevamento di potenziali violazioni

In caso di una violazione dei dati, Dynamics 365 interviene secondo il processo di intervento per gli incidenti di sicurezza, che rientra nel piano di gestione degli incidenti di Microsoft Dynamics 365. Il processo di intervento per gli incidenti di sicurezza di Dynamics 365 comprende cinque fasi: Rilevamento, Valutazione, Diagnostica, Stabilizzazione e Chiusura. Nel corso dell'indagine il team di intervento può passare dalla fase di diagnostica a quella di stabilizzazione e viceversa. Ecco una panoramica del processo di intervento per gli incidenti di sicurezza:

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Fase</th>
<th align="left">Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Rilevamento</td>
<td align="left">Prima indicazione della necessità di indagare un evento.</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Valutazione</td>
<td align="left">Un tecnico di turno del team di intervento per gli incidenti valuta l'impatto e la gravità dell'incidente. Secondo le prove raccolte, la valutazione può comportare o meno un'ulteriore escalation al team di intervento della sicurezza.</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Diagnostica/Indagine</td>
<td align="left"><p>Gli esperti del team di intervento della sicurezza svolgono le indagini tecniche o forensi, identificano le strategie di contenimento, mitigazione e le soluzioni alternative.</p>
<p>Se il team della sicurezza ritiene che i dati del cliente potrebbero essere stati esposti a un individuo non autorizzato o a un criminale, il processo di notifica dell'incidente al cliente si svolge in parallelo.</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Stabilizzazione e ripristino</td>
<td align="left">Il team di intervento per gli incidenti crea un piano di ripristino per mitigare il problema. Le misure di contenimento della crisi, come l'applicazione della quarantena ai sistemi colpiti, possono verificarsi immediatamente e parallelamente alla fase di diagnosi. Si possono pianificare misure di mitigazione a lungo termine da implementare dopo che è passato il rischio immediato.</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Chiusura e relazione finale</td>
<td align="left">Il team di intervento per gli incidenti crea una relazione finale dettagliata dell'incidente finalizzata alla revisione di criteri, procedure e interventi per prevenire il ripetersi dell'evento.</td>
</tr>
</tbody>
</table>

Il white paper di [Dynamics Security Incident Management](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) fornisce ulteriori informazioni su come Microsoft indaga, gestisce e interviene in caso di incidenti di sicurezza nell'ambito di Dynamics 365.

I processi di rilevamento utilizzati da Microsoft Dynamics 365 sono progettati per rilevare eventi che mettono a rischio la riservatezza, l'integrità e la disponibilità dei servizi di Dynamics 365. Diversi eventi possono dare il via a un'indagine:

-   Avvisi di sistema automatici tramite framework di monitoraggio e avviso interni. Questi avvisi potrebbero interferire con avvisi basati su firma come antimalware, rilevamento di intrusioni o tramite algoritmi progettati per tracciare il profilo dell'attività prevista e segnalare anomalie.

-   Report generati con i servizi di Microsoft Dynamics 365 distribuiti nel cloud pubblico e con i servizi Microsoft Dynamics 365 distribuiti nel cloud sovrano.

-   Le vulnerabilità di sicurezza vengono segnalate a [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) tramite <secure@microsoft.com>. MSRC collabora con partner e ricercatori di sicurezza di tutto il mondo per prevenire incidenti e migliorare la sicurezza dei prodotti Microsoft.

-   Report dei clienti che descrivono le attività sospette attribuite a servizi Microsoft Dynamics 365 (in contrasto con l'attività che si svolge nell'ambito di responsabilità del cliente).

-   Attività di [Red Team e Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) della sicurezza. Questa strategia utilizza un Red Team altamente qualificato di esperti di sicurezza offensiva per scoprire e attaccare potenziali punti deboli nei servizi di Microsoft Dynamics 365. Il Blue Team di intervento per la sicurezza deve rilevare e difendersi dall'attività del Read Team. Le azioni del Red e Blue Team vengono utilizzate per verificare che gli interventi per la sicurezza di Microsoft Dynamics 365 gestiscano in modo efficace gli incidenti. Le attività di sicurezza Red Team e Blue Team sono gestite secondo requisiti di responsabilità per garantire la protezione dei dati del cliente.

-   Escalation da parte degli operatori di servizi di Microsoft Dynamics 365. I dipendenti Microsoft sono addestrati per identificare e intensificare potenziali incidenti riguardanti la sicurezza.

#### <a name="microsoft-dynamics-365-data-breach-response"></a>Interventi di Microsoft Dynamics 365 in caso di violazione dei dati 

Microsoft assegna all'indagine adeguati livelli di priorità e gravità determinando l'impatto funzionale, la recuperabilità e l'impatto delle informazioni dell'incidente. Sia la priorità che la gravità possono cambiare nel corso dell'indagine, sulla base di nuove scoperte e conclusioni. Gli eventi di sicurezza che comportano rischi imminenti o confermati per i dati del cliente sono considerati di gravità elevata e vengono seguiti 24 ore su 24 fino a quando non vengono risolti. Microsoft Dynamics 365 definisce la violazione della privacy come violazione di ''dati personali degli utenti finali di un servizio online o di dipendenti Microsoft''.

Il team di Security Response collabora con Microsoft Dynamics 365 Security Engineers e Subject Matter Experts (SME) per classificare l'evento sulla base di dati concreti tratti dalle prove raccolte. Un incidente di sicurezza può essere classificato come:

-   **Falso positivo:** un evento che soddisfa i criteri di rilevamento ma che risulta essere parte di una normale pratica aziendale e può aver bisogno di essere filtrato. Il team del servizio identificherà la causa principale dei falsi positivi e li risolverà in modo sistematico sfruttando le fonti di rilevamento e <span id="_Toc350859432" class="anchor"></span>ottimizzandole se necessario.

-   **Incidente di sicurezza:** un accesso illecito o non autorizzati ai dati del cliente o ai dati di supporto conservati nei dispositivi o nelle sedi Microsoft che ha provocato la perdita, la divulgazione o l'alterazione dei dati del cliente o dei dati di supporto.

-   **Incidenti di sicurezza segnalabili dal cliente (CRSI):** un accesso o un utilizzo illecito o non autorizzato dei sistemi, dei dispositivi o delle sedi Microsoft che ha provocato la divulgazione, la modifica o la perdita dei dati del cliente.

-   **Incidente di privacy:** un tipo di incidente di sicurezza che coinvolge i dati personali. Le procedure di gestione non sono diverse da altri incidenti di sicurezza.

Affinché un incidente di sicurezza segnalabile dal cliente possa essere dichiarato, Microsoft deve stabilire che l'accesso non autorizzato ai dati del cliente è avvenuto o molto probabilmente si è verificato e/o che esiste un impegno legale o contrattuale perché si verifichi la notifica. È auspicabile, ma non è necessario, conoscere lo specifico impatto sul cliente, l'accesso alle risorse e i passaggi di ripristino. Un incidente di sicurezza è generalmente dichiarato incidente di sicurezza segnalabile dal cliente dopo la conclusione della fase di diagnosi; tuttavia, la dichiarazione può accadere in qualsiasi momento in cui tutte le informazioni pertinenti siano disponibili. Il responsabile dell'incidente deve stabilire prove raccolte oltre ogni ragionevole dubbio che si è verificato un evento da segnalare per iniziare l'esecuzione del Processo di notifica dell'incidente del cliente.

Durante l'indagine, il team di intervento per la sicurezza lavora a stretto contatto con i consulenti legali globali per contribuire a garantire che le analisi forensi siano eseguite in conformità con gli obblighi legali e gli impegni nei confronti dei clienti. Esistono anche limitazioni significative sulla visualizzazione e gestione dei dati del sistema e del cliente in vari ambienti operativi. I dati sensibili o riservati, così come i dati del cliente, non vengono trasferiti fuori dall'ambiente di produzione senza un'approvazione scritta esplicita da parte del responsabile dell'incidente registrato nel ticket dell'incidente corrispondente.

Microsoft verifica che il rischio per il cliente e per l'azienda sia contenuto e che vengano implementate misure correttive. Se necessario, vengono adottate misure di attenuazione dell'emergenza per risolvere i rischi di sicurezza immediati associati all'evento.

Microsoft completa inoltre una relazione finale interna per le violazioni dei dati. Come parte di questo esercizio, vengono valutate l'adeguatezza dell'intervento, le procedure operative e tutti gli aggiornamenti che possono essere necessari secondo i criteri di sicurezza interni di Microsoft o che i processi correlati siano identificati e implementati. Le relazioni finali interne per le violazioni dei dati sono registrazioni altamente riservate non disponibili per i clienti. Le relazioni finali possono, tuttavia, essere riassunte e incluse in altre notifiche di eventi al cliente. Questi report vengono forniti ai revisori esterni per essere esaminati come parte del ciclo di controllo di routine di Dynamics 365.

#### <a name="customer-notification"></a>Notifica al cliente

Microsoft Dynamics 365 notifica le violazioni dei dati ai clienti e agli organismi di certificazione, come richiesto. Microsoft si basa su una forte compartimentazione interna nel funzionamento di Dynamics 365. Anche i registri del flusso di dati sono solidi. A vantaggio di questa struttura, la maggior parte degli incidenti può essere indirizzata a clienti specifici. L'obiettivo è fornire ai clienti interessati un avviso accurato, attuabile e tempestivo nel momento in cui i dati vengono violati.

Dopo la dichiarazione di un incidente di sicurezza segnalabile dal cliente, il processo di notifica viene eseguito il più rapidamente possibile, tenendo in considerazione i rischi che ciò comporta alla sicurezza. Generalmente, il processo di progettazione delle notifiche avviene mentre è in corso l'indagine sull'incidente. Le notifiche al cliente sono consegnate con tempestività dal momento in cui viene dichiarata una violazione, *salvo* nelle seguenti circostanze:

-   Microsoft ritiene che l'atto di esecuzione di una notifica aumenti il rischio per gli altri clienti. Ad esempio, l'atto di notifica può allertare un avversario causando l'impossibilità di porvi rimedio.

-   Altre circostanze insolite o estreme esaminate dall'ufficio legale di Microsoft e dall'Executive Incident Manager.

Microsoft Dynamics 365 fornisce ai clienti informazioni dettagliate che consentono loro di svolgere indagini interne e di assisterli nell'adempimento degli impegni assunti con l'utente finale, senza ritardare ingiustificatamente il processo di notifica.

La notifica di una violazione dei dati personali verrà consegnata al cliente con qualsiasi mezzo selezionato da Microsoft, anche via email. La notifica di una violazione dei dati verrà inviata all'elenco dei contatti del cliente/amministratori (solo i tenant interessati) fornito nel Centro sicurezza di Office e configurabile dal cliente/amministratore del tenant. Per garantire che la notifica possa essere consegnata con successo, è responsabilità del cliente assicurarsi che le informazioni di contatto amministrative su ciascun abbonamento e portale di servizi online siano corrette.

Il team di Microsoft Dynamics 365 per enti pubblici può anche decidere di notificare ulteriori informazioni al personale Microsoft, ad esempio il servizio clienti (CSS) e l'Account Manager del cliente (AM) o il Technical Account Manager (TAM). Tali figure hanno spesso strette relazioni con il cliente e possono facilitare una correzione più rapida.<span id="_Appendix_A" class="anchor"></span>

#### <a name="learn-more"></a>Altre informazioni
[Centro protezione Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)