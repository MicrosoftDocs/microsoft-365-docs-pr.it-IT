---
title: Criteri, procedure e linee guida di riferimento
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure consigliate per aiutare a proteggere gli utenti da messaggi di posta elettronica abusivi, indesiderati o dannosi.
ms.openlocfilehash: 4a9c38822c4d0f3e06e209acf021618864540c83
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082812"
---
# <a name="reference-policies-practices-and-guidelines"></a>Informazioni di riferimento: criteri, procedure e linee guida
  
Microsoft è dedicato all'assistenza per fornire l'esperienza utente più affidabile sul Web. Pertanto, Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure consigliate per aiutare a proteggere gli utenti da messaggi di posta elettronica abusivi, indesiderati o dannosi. I mittenti che tentano di inviare messaggi di posta elettronica agli utenti di Office 365 devono accertarsi di comprendere e seguire le indicazioni contenute in questo articolo per facilitare questo sforzo e per evitare potenziali problemi di recapito.
  
Se non si è in conformità con questi criteri e linee guida, potrebbe non essere possibile per il team di supporto aiutarla. Se si rispettano le linee guida, le procedure e i criteri illustrati in questo articolo e si verificano ancora problemi di recapito in base all'indirizzo IP di invio, attenersi alla procedura seguente per inviare una richiesta di delisting. Per istruzioni, vedere [use the delist Portal to Remove from the Office 365 Blocked Senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).
  
## <a name="general-microsoft-policies"></a>Criteri generali di Microsoft
<a name="GenMsftPolicies"> </a>

I messaggi di posta elettronica inviati a Office 365 gli utenti devono essere conformi a tutti i criteri Microsoft che regolano la trasmissione e l'utilizzo di Office 365.
  
- Termini di servizi applicabili a Office 365; in particolare, il divieto di utilizzare il servizio per la posta indesiderata o la distribuzione di malware
    
- [Accordo sui servizi Microsoft](https://www.microsoft.com/servicesagreement/)
    
## <a name="governmental-regulations"></a>Regolamenti governativi
<a name="GovtRegulations"> </a>

I messaggi di posta elettronica inviati a Office 365 gli utenti devono rispettare tutte le leggi e i regolamenti applicabili che disciplinano le comunicazioni di posta elettronica nella giurisdizione applicabile.
  
- [CAN-SPAM Act: una guida alla conformità per le aziende](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)
    
- ["Rimuovi" risposte e responsabilità: i marketer della posta elettronica devono onorare le attestazioni di "annullamento della sottoscrizione"](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)
    
## <a name="technical-guidelines"></a>Linee guida tecniche
<a name="TechGuidelines"> </a>

I messaggi di posta elettronica inviati a Office 365 devono essere conformi alle raccomandazioni applicabili elencate nei documenti riportati di seguito (alcuni collegamenti sono disponibili solo in inglese).
  
- [RFC 2505: suggerimenti per la protezione da posta indesiderata per MTA SMTP](https://www.ietf.org/rfc/rfc2505.txt)
    
- [RFC 2920: estensione del servizio SMTP per il pipelining dei comandi](https://www.ietf.org/rfc/rfc2920.txt)
    
Inoltre, i server di posta elettronica che si connettono a Office 365 devono attenersi ai requisiti seguenti:
  
- Il mittente deve essere conforme a tutti gli standard tecnici per la trasmissione della posta elettronica Internet, come pubblicato dall'IETF (Internet Engineering Task Force), tra cui RFC 5321, RFC 5322 e altri. 
    
- Dopo aver specificato un codice di risposta di errore SMTP numerico compreso tra 500 e 599 (noto anche come risposta di mancato recapito permanente o NDR), il mittente non deve tentare di ritrasmettere tale messaggio al destinatario.
    
- Dopo più risposte di mancato recapito, il mittente deve interrompere ulteriori tentativi di inviare messaggi di posta elettronica al destinatario.
    
- I messaggi non devono essere trasmessi tramite l'inoltro di posta elettronica insicuro o i server proxy.
    
- Il meccanismo di annullamento della sottoscrizione, sia da singoli elenchi che da tutti gli elenchi ospitati dal mittente, deve essere chiaramente documentato e facile da trovare e utilizzare per i destinatari.
    
- Non è possibile accettare le connessioni dallo spazio IP dinamico.
    
- I server di posta elettronica devono disporre di record DNS inversi validi.
    
## <a name="reputation-management"></a>Gestione della reputazione
<a name="RepManagement"> </a>

I mittenti, gli ISP e gli altri provider di servizi dovrebbero gestire attivamente la reputazione degli indirizzi IP in uscita.
  
## <a name="office-365-limits"></a>Limiti relativi a Office 365
<a name="sectionSection4"> </a>

I mittenti devono attenersi ai limiti di Office 365 elencati nei [limiti di Exchange Online Protection](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx).
  
## <a name="email-delivery-resources-and-organizations"></a>Risorse e organizzazioni per il recapito della posta elettronica
<a name="sectionSection5"> </a>

Microsoft collabora attivamente con gli enti del settore e i provider di servizi per migliorare Internet e l'ecosistema di posta elettronica. Queste organizzazioni hanno pubblicato documenti di Best practice che supportano e consiglia ai mittenti di aderire. Questo consente di migliorare la possibilità di inviare posta elettronica tra diversi provider di servizi di posta elettronica in tutto il mondo.
  
- [Gruppo di lavoro anti-abuso mobile per la messaggistica](https://www.m3aawg.org/)
    
- [Alleanza Fiduciaria online](https://www.otalliance.org/resources)
    
- [Coalizione &amp; provider di mittenti di posta elettronica](http://www.espcoalition.org/)
    
## <a name="abuse-and-spam-reporting"></a>Segnalazione di abusi e posta indesiderata
<a name="AbuseSpamReports"> </a>

Per segnalare messaggi di posta elettronica illeciti, abusivi, indesiderati o dannosi, [segnalare la posta indesiderata e i tentativi di phishing in Outlook sul Web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). L'invio di questi tipi di comunicazioni è una violazione dei criteri di Microsoft e le azioni appropriate verranno eseguite nei rapporti confermati.
  
## <a name="law-enforcement"></a>Applicazione della legge
<a name="sectionSection7"> </a>

Se si è membri di Law Enforcement e si desidera servire Microsoft Corporation con documentazione legale relativa a Office 365 o se si dispone di domande relative alla documentazione legale inviata a Microsoft, chiamare il (1) (425) 722-1299.
  

