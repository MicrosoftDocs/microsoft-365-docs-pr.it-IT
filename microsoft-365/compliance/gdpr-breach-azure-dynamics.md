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
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920261"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Notifica di violazione nell'ambito del GDPR in Azure e Dynamics 365

Microsoft Azure prende in seria considerazione gli obblighi previsti dal Regolamento generale sulla protezione dei dati (GDPR). Microsoft Azure adotta ampie misure di sicurezza per proteggere dalle violazioni dei dati. Queste includono controlli di sicurezza sia fisici che logici, così come interventi di sicurezza automatizzati, criteri completi di sicurezza delle informazioni e privacy, nonché formazione sulla sicurezza e sulla privacy per tutto il personale.

La sicurezza è integrata in Microsoft Azure, a partire dal [Security Development Lifecycle](https://www.microsoft.com/sdl/), un processo di sviluppo obbligatorio che incorpora le metodologie di privacy by design e privacy by default. Il principio guida della strategia di sicurezza di Microsoft consiste nel "presumere la violazione", che è un'estensione della strategia di difesa in profondità. Mettendo costantemente alla prova le funzionalità di sicurezza di Azure, Microsoft può stare al passo con le minacce emergenti. Per altre informazioni sulla sicurezza di Azure, consultare queste [risorse](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft ha un servizio di intervento a un incidente globale disponibile 24 ore su 24, 7 giorni su 7, che opera per mitigare gli effetti degli attacchi contro Microsoft Azure. Attestato da più controlli di sicurezza e conformità (ad es. [ISO/IEC 27018](offering-iso-27018.md)), Microsoft impiega rigorose operazioni e interventi nei suoi data center per prevenire accessi non autorizzati, tra cui monitoraggio video disponibile 24 ore su 24, 7 giorni su 7, personale di sicurezza addestrato, smart card e controlli biometrici.

## <a name="detection-of-potential-breaches"></a>Rilevamento di potenziali violazioni

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure offre anche diversi servizi, ad esempio [Azure Defender](https://azure.microsoft.com/services/security-center/), che i clienti possono usare per sviluppare e gestire gli interventi in caso di incidenti di sicurezza.

Azure risponde a una potenziale violazione dei dati in base al processo di risposta agli incidenti di sicurezza, che è un sottoinsieme del piano di gestione degli incidenti di Microsoft Azure. La risposta agli incidenti di sicurezza di Azure viene implementata tramite un processo costituito da cinque fasi: rilevamento, valutazione, diagnostica, stabilizzazione e chiusura. Il team dedicato può alternare le fasi di diagnosi e stabilizzazione man mano che l'indagine procede. Di seguito è riportata una panoramica del processo di risposta agli incidenti di sicurezza:

|**Fase**|**Descrizione**|
| ------- | ------------- |
| **_1 — Rilevamento_* _ | Prima indicazione di un potenziale incidente. |
| _*_2 — Valutazione_*_ | Un tecnico di turno del team di intervento per gli incidenti valuta l'impatto e la gravità dell'incidente. Secondo le prove raccolte, la valutazione può comportare o meno un'ulteriore escalation al team di intervento della sicurezza. |
| _*_3 — Diagnostica_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — Stabilizzazione e ripristino_*_ | Il team di intervento per gli incidenti crea un piano di ripristino per mitigare il problema. Le misure di contenimento della crisi, come l'applicazione della quarantena ai sistemi colpiti, possono verificarsi immediatamente e parallelamente alla fase di diagnosi. Si possono pianificare misure di mitigazione a lungo termine da implementare dopo che è passato il rischio immediato. |
| _*_5 - Chiusura e relazione finale_*_ | Il team di intervento per gli incidenti crea una relazione finale dettagliata dell'incidente finalizzata alla revisione di criteri, procedure e interventi per prevenire il ripetersi dell'evento. |

Il white paper di [Microsoft Azure Security Response nel cloud](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) fornisce ulteriori dettagli su come Microsoft indaga, gestisce e interviene agli incidenti di sicurezza all'interno di Azure.

I processi di rilevamento utilizzati da Microsoft Azure sono progettati per rilevare eventi che mettono a rischio la riservatezza, l'integrità e la disponibilità dei servizi di Azure. Diversi eventi possono dare il via a un'indagine:

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- Report di prima parte dei servizi Microsoft in esecuzione su Microsoft Azure e Azure per enti pubblici.
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- Report dei clienti tramite il [portale del supporto tecnico](https://www.windowsazure.com/support/contact/) o il portale di Microsoft Azure e Azure per enti pubblici, che descrivono attività sospette attribuite all'infrastruttura di Azure (al contrario delle attività che si verificano nell'ambito di responsabilità del cliente).
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Escalation da parte degli operatori di servizi di Azure. I dipendenti Microsoft sono addestrati per identificare e inoltrare potenziali problemi riguardanti la sicurezza.

## <a name="azures-data-breach-response"></a>Intervento in caso di violazione dei dati di Azure

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

Microsoft Azure classifica l'impatto dell'evento sulle informazioni nelle seguenti categorie di violazione:

| _ *Categoria**             | **Definizione**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Nessuna_* _               | Nessuna informazione è stata estratta, modificata, cancellata o comunque compromessa.                                                      |
| _*_Violazione della privacy_*_     | È stato possibile accedere o estrarre dati personali sensibili riguardanti i contribuenti, i dipendenti, i beneficiari e così via.                                |
| _*_Violazioni di proprietà_*_ | È stato possibile accedere o estrarre informazioni proprietarie non classificate, ad esempio informazioni riguardanti l'infrastruttura critica protetta (PCII). |
| _*_Perdita di integrità_*_     | Sono state modificate o cancellate informazioni sensibili o proprietarie.                                                                     |

Il team di Security Response collabora con Microsoft Azure Security Engineers e SME per classificare l'evento sulla base di dati concreti tratti dalle prove raccolte. Un incidente di sicurezza può essere classificato come:

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **Incidente di sicurezza** : un accesso illecito o non autorizzato ai dati del cliente o ai dati di supporto archiviati nelle apparecchiature o strutture Microsoft che ha provocato la perdita, la divulgazione o l'alterazione dei dati del cliente o dei dati di supporto.
- **Incidente di sicurezza/privacy segnalabile dal cliente (CRSPI)** : un accesso o un utilizzo illecito o non autorizzato dei sistemi, dei dispositivi o delle sedi Microsoft che ha provocato la divulgazione, la modifica o la perdita dei dati del cliente.
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

Durante l'indagine, il team di intervento per la sicurezza lavora a stretto contatto con i consulenti legali globali per contribuire a garantire che le analisi forensi siano eseguite in conformità con gli obblighi legali e gli impegni nei confronti dei clienti. Esistono anche limitazioni significative sulla visualizzazione e gestione dei dati del sistema e del cliente in vari ambienti operativi. I dati sensibili o riservati, così come i dati del cliente, non vengono trasferiti fuori dall'ambiente di produzione senza un'approvazione scritta esplicita da parte del responsabile dell'incidente registrato nel ticket dell'incidente corrispondente.

Microsoft verifica che il rischio per il cliente e per l'azienda sia contenuto e che vengano implementate misure correttive. Se necessario, vengono adottate misure di attenuazione dell'emergenza per risolvere i rischi di sicurezza immediati associati all'evento.

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>Notifica al cliente

Microsoft Azure notifica le violazioni dei dati ai clienti e agli organismi di certificazione, come richiesto. Microsoft si basa su una forte compartimentazione interna nel funzionamento di Azure. Anche i registri del flusso di dati sono solidi. A vantaggio di questa struttura, la maggior parte degli incidenti può essere indirizzata a clienti specifici. L'obiettivo è fornire ai clienti interessati un avviso accurato, attuabile e tempestivo nel momento in cui i dati vengono violati.

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- Altre circostanze insolite o estreme esaminate dall'ufficio legale di Microsoft (CELA) e dall'Executive Incident Manager.
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

Microsoft Azure fornisce ai clienti informazioni dettagliate che consentono loro di svolgere indagini interne e di assisterli nell'adempimento degli impegni assunti con l'utente finale, senza ritardare ingiustificatamente il processo di notifica.

La notifica di una violazione dei dati personali verrà consegnata al cliente con qualsiasi mezzo selezionato da Microsoft, anche via e-mail. La notifica di una violazione dei dati verrà inviata all'elenco dei contatti di sicurezza fornito da Azure Defender, che può essere configurato seguendo le [linee guida per l'implementazione](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se le informazioni di contatto non vengono fornite in Azure Defender, la notifica verrà inviata a uno o più amministratori in una sottoscrizione di Azure. Per garantire che la notifica possa essere consegnata con successo, è responsabilità del cliente assicurarsi che le informazioni di contatto amministrative su ciascun abbonamento e portale di servizi online siano corrette.

Il team di Microsoft Azure o Azure per enti pubblici può anche decidere di informare altri membri del personale Microsoft, ad esempio il servizio clienti (CSS) e l'Account Manager del cliente (AM) o il Technical Account Manager (TAM). Tali figure hanno spesso strette relazioni con il cliente e possono facilitare una correzione più rapida.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Funzionalità di sicurezza integrate in Microsoft Dynamics 365

Microsoft Dynamics 365 si avvale dell'infrastruttura dei servizi del cloud e delle funzionalità di protezione integrate per proteggere i dati attraverso meccanismi e misure di sicurezza. Inoltre, Dynamics 365 fornisce accesso efficiente ai dati e collaborazione con l'integrità dei dati e la privacy nelle aree seguenti: [protezione dell'identità, protezione dei dati, protezione basata sui ruoli e gestione delle minacce](https://www.microsoft.com/trustcenter/security/dynamics365-security).

L'offerta Microsoft Dynamics 365 segue le stesse misure tecniche e organizzative adottate da uno o più team di servizi di Microsoft Azure per garantire la protezione dai processi di violazione dei dati. Di conseguenza, tutte le informazioni riportate nel documento di notifica "Violazioni di dati in Microsoft Azure" sono analoghe a Microsoft Dynamics 365.

## <a name="learn-more"></a>Altre informazioni

[Centro protezione Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
