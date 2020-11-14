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
ms.author: siosulli
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 5d0a5563de2443e5af0f3b7efda0947d4f669cee
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070900"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>Notifica di violazione relativa al servizio di trattamento dei dati per Windows Enterprise ai sensi del GDPR

>[!NOTE]
>This topic is intended for participants in the data processor service for Windows Enterprise preview program and requires acceptance of specific terms of use. To learn more about the program and agree to the terms of use, see [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Microsoft data processor service for Windows Enterprise takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft data processor service for Windows Enterprise takes extensive security measures to protect against data breaches. These include dedicated threat management teams that proactively anticipate, prevent, and mitigate malicious access.  Internal security measures such as port scanning, perimeter vulnerability scanning, and intrusion detection detect and prevent malicious access, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel. 

Security is built into the Microsoft data processor service for Windows Enterprise from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft's security strategy is to 'assume breach', which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of the data processor service for Windows Enterprise, Microsoft can stay ahead of emerging threats. For more information on the data processor service for Windows Enterprise security, please review these [resources](https://www.microsoft.com/TrustCenter/Security/windows10-security) the data processor service for Windows Enterprise responds to a potential data breach according to the security incident response process. The data processor service for Windows Enterprise security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below: 

|**Fase**|**Descrizione**|
| ------- | ------------- |
| **_1 — Rilevamento_* _ | Prima indicazione di un potenziale incidente. |
| _*_2 — Valutazione_*_ | Un tecnico di turno del team di intervento per gli incidenti valuta l'impatto e la gravità dell'incidente. Secondo le prove raccolte, la valutazione può comportare o meno un'ulteriore escalation al team di intervento della sicurezza. |
| _*_3 — Diagnostica_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — Stabilizzazione e ripristino_*_ | Il team di intervento per gli incidenti crea un piano di ripristino per mitigare il problema. Le misure di contenimento della crisi, come l'applicazione della quarantena ai sistemi colpiti, possono verificarsi immediatamente e parallelamente alla fase di diagnosi. Si possono pianificare misure di mitigazione a lungo termine da implementare dopo che è passato il rischio immediato. |
| _*_5 — Chiusura e relazione finale_*_ | Il team di intervento per gli incidenti crea una relazione finale dettagliata dell'incidente finalizzata alla revisione di criteri, procedure e interventi per prevenire il ripetersi dell'evento. |

The detection processes used by Microsoft data processor service for Windows Enterprise are designed to discover events that risk the confidentiality, integrity, and availability of the data processor service for Windows Enterprise. Several events can trigger an investigation: 

 - Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
 - Report di prima parte dei servizi Microsoft in esecuzione su Microsoft Azure e Azure per enti pubblici.
 - Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
 - Report dei clienti tramite il portale del supporto tecnico o il portale di Microsoft Azure e Azure per enti pubblici, che descrivono attività sospette attribuite all'infrastruttura di Azure (al contrario delle attività che si verificano nell'ambito di responsabilità del cliente).
 - Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
 - Escalation da parte degli operatori di servizi di Azure. I dipendenti Microsoft sono addestrati per identificare e inoltrare potenziali problemi riguardanti la sicurezza.

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Risposta alle violazioni dei dati nel servizio di trattamento dei dati per Windows Enterprise 

 Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft data processor service for Windows Enterprise categorizes the information impact of the incident into the following breach categories: 

| _ *Categoria**             | **Definizione**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Nessuna_* _               | Nessuna informazione è stata rimossa, modificata, cancellata o comunque compromessa. |
| _*_Violazione della privacy_*_     | È stato possibile accedere o rimuovere dati personali sensibili riguardanti i contribuenti, i dipendenti, i beneficiari e così via. |
| _*_Violazioni di proprietà_*_ | È stato possibile accedere o rimuovere informazioni proprietarie non classificate, ad esempio informazioni riguardanti l'infrastruttura critica protetta (PCII). |
| _*_Perdita di integrità_*_     | Sono state modificate o cancellate informazioni sensibili o proprietarie. |

The Security Response Team works with Microsoft data processor service for Windows Enterprise Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as: 

 - _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-tuning them as needed. 
 - **Incidente di sicurezza** : un accesso illecito o non autorizzato ai dati del cliente o ai dati di supporto archiviati nelle apparecchiature o strutture Microsoft che ha provocato la perdita, la divulgazione o l'alterazione dei dati del cliente o dei dati di supporto. 
 - **Incidente di sicurezza segnalabile dal cliente (CRSI)** : un accesso o un utilizzo illecito o non autorizzato dei sistemi, delle apparecchiature o strutture Microsoft che ha provocato la divulgazione, la modifica o la perdita dei dati del cliente. 
 - **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident. 

 Affinché un incidente di sicurezza segnalabile dal cliente possa essere dichiarato, Microsoft deve stabilire che l'accesso non autorizzato ai dati del cliente è avvenuto o molto probabilmente si è verificato e/o che esiste un impegno legale o contrattuale perché si verifichi la notifica. È auspicabile, ma non è necessario, conoscere lo specifico impatto sul cliente, l'accesso alle risorse e i passaggi di ripristino. Un incidente di sicurezza è generalmente dichiarato incidente di sicurezza segnalabile dal cliente dopo la conclusione della fase di diagnosi; tuttavia, la dichiarazione può avvenire in qualsiasi momento in cui tutte le informazioni pertinenti siano disponibili. Il responsabile dell'incidente deve stabilire oltre ogni ragionevole dubbio che si è verificato un evento da segnalare per iniziare l'esecuzione del Processo di notifica dell'incidente del cliente. 

Durante l'indagine, il team di intervento per la sicurezza lavora a stretto contatto con i consulenti legali globali per contribuire a garantire che le analisi forensi siano eseguite in conformità con gli obblighi legali e gli impegni nei confronti dei clienti. Esistono anche limitazioni significative sulla visualizzazione e gestione dei dati del sistema e del cliente in vari ambienti operativi. I dati sensibili o riservati, così come i dati del cliente, non vengono trasferiti fuori dall'ambiente di produzione senza un'approvazione scritta esplicita da parte del responsabile dell'incidente registrato nel ticket dell'incidente corrispondente. 

Microsoft verifica che il rischio per il cliente e per l'azienda sia contenuto e che vengano implementate misure correttive. Se necessario, vengono adottate misure di attenuazione dell'emergenza per risolvere i rischi di sicurezza immediati associati all'evento. 

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of the data processor service for Windows Enterprise routine audit cycle. 

## <a name="customer-notice"></a>Comunicazione ai clienti

Microsoft data processor service for Windows Enterprise notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of the data processor service for Windows Enterprise. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached. 

After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances: 

 - Microsoft ritiene che l'atto di esecuzione di una notifica aumenti il rischio per gli altri clienti. Ad esempio, l'atto di notifica può allertare un avversario causando l'impossibilità di porvi rimedio. 
 - Altre circostanze insolite o estreme esaminate dall'ufficio legale di Microsoft (CELA) e dall'Executive Incident Manager. 

 Il servizio di trattamento dei dati per Windows Enterprise di Microsoft fornisce ai clienti informazioni dettagliate che consentono loro di svolgere indagini interne e di assisterli nell'adempimento degli impegni assunti con l'utente finale, senza ritardare ingiustificatamente il processo di notifica. 

La notifica di una violazione dei dati personali verrà consegnata al cliente con qualsiasi mezzo selezionato da Microsoft, anche via e-mail. La notifica di una violazione dei dati verrà inviata all'elenco dei contatti di sicurezza fornito in Azure Defender, che può essere configurato seguendo le [linee guida per l'implementazione](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se le informazioni di contatto non vengono fornite in Azure Defender, la notifica verrà inviata a uno o più amministratori in una sottoscrizione di Azure. Per garantire che la notifica possa essere consegnata con successo, è responsabilità del cliente assicurarsi che le informazioni di contatto amministrative su ciascun abbonamento e portale di servizi online siano corrette.

Il team del Servizio di trattamento dei dati aziendali per Windows può anche decidere di informare altri membri del personale Microsoft, ad esempio il Supporto tecnico (CSS), e l'Account Manager (AM) o il Technical Account Manager (TAM) del cliente. Tali figure hanno spesso strette relazioni con il cliente e possono facilitare una correzione più rapida. 

Per ulteriori informazioni su come Microsoft rileva e interviene a un caso di violazione dei dati personali, vedere [Notifica di violazione dei dati secondo il GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) nel Service Trust Portal.
