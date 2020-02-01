---
title: Contrastare la posta indesiderata inviata a Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: La Guida di orientamento alla sicurezza della posta elettronica di Microsoft comporta un approccio cross-product senza eguali. La tecnologia di filtraggio della posta indesiderata e anti-phishing di Exchange Online Protection (EOP) è in corso di applicazione nelle piattaforme e-mail di Microsoft per offrire agli utenti gli strumenti e le innovazioni più recenti di protezione da posta indesiderata e anti-phishing in tutta la rete. L'obiettivo di EOP è offrire un servizio di posta elettronica completo e utilizzabile che aiuti a rilevare e proteggere gli utenti dalla posta indesiderata, dalle minacce alla posta elettronica fraudolente (phishing) e da malware.
ms.openlocfilehash: 888df6224007471db46b669ac4ffe33983057115
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599323"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>Contrastare la posta indesiderata inviata a Office 365

La Guida di orientamento alla sicurezza della posta elettronica di Microsoft comporta un approccio cross-product senza eguali. La tecnologia di filtraggio della posta indesiderata e anti-phishing di Exchange Online Protection (EOP) è in corso di applicazione nelle piattaforme e-mail di Microsoft per offrire agli utenti gli strumenti e le innovazioni più recenti di protezione da posta indesiderata e anti-phishing in tutta la rete. L'obiettivo di EOP è offrire un servizio di posta elettronica completo e utilizzabile che aiuti a rilevare e proteggere gli utenti dalla posta indesiderata, dalle minacce alla posta elettronica fraudolente (phishing) e da malware.
  
## <a name="the-challenge"></a>Problema

La posta elettronica è diventata uno strumento di comunicazione importante non solo per i consumatori, ma anche per gli addetti marketing, il personale di supporto, le organizzazioni di vendita e le aziende di tutte le dimensioni. L'utilizzo della posta elettronica è cresciuto, quindi ha un abuso di posta elettronica. La posta indesiderata non monitorata può intasare le cassette postali e le reti, influire sulla soddisfazione degli utenti e ostacolare l'efficacia delle comunicazioni di posta elettronica. Ecco perché Microsoft continua a investire nelle tecnologie di protezione dalla posta indesiderata. In poche parole, viene avviato contenendo e filtrando la posta indesiderata. 
  
## <a name="our-efforts"></a>I nostri sforzi

EOP offre una serie di passaggi per ridurre al minimo l'impatto negativo della posta indesiderata sull'utilizzo della posta elettronica degli utenti.
  
### <a name="exchange-online-protection-technology"></a>Tecnologia Exchange Online Protection

Per contribuire a ridurre la posta indesiderata, EOP include la protezione della posta indesiderata utilizzando tecnologie di filtro EOP proprietarie che schermano la posta elettronica per identificare e separare la posta indesiderata Il filtro contenuto di EOP apprende dalle minacce note e dalla posta indesiderata e dal feedback degli utenti dalla nostra piattaforma consumer, Outlook.com. Questi tipi di dati aiutano il treno EOP Technologies a riconoscere la posta elettronica legittima e la posta indesiderata e sono input chiave nella reputazione mittente. Il feedback in corso da parte degli utenti di EOP nel programma di classificazione della posta indesiderata contribuisce a garantire che le tecnologie EOP siano continuamente addestrate e migliorate.
  
#### <a name="how-does-eop-work"></a>Come funziona EOP?

Quando un utente esterno invia un messaggio di posta elettronica a un utente di EOP, le tecnologie di filtro di EOP valutano il contenuto del messaggio e assegnano una classificazione al messaggio in base alla probabilità che il messaggio sia posta indesiderata. Questa valutazione viene memorizzata come una proprietà del messaggio denominata livello di probabilità di posta indesiderata (SCL) all'interno del messaggio stesso. La valutazione SCL rimane con il messaggio così come viene inviata ad altri livelli di protezione dalla posta indesiderata all'interno di EOP. 
  
Le regole all'interno di EOP sono impostate per gestire i messaggi di posta elettronica con diverse valutazioni SCL. Se un messaggio ha una valutazione SCL superiore a una determinata soglia, viene considerato posta indesiderata. Il messaggio verrà messo in quarantena o recapitato nella cartella posta indesiderata dell'utente a seconda del modo in cui l'amministratore di sistema configura l'opzione di recapito della posta indesiderata
  
#### <a name="eop-filters"></a>Filtri di EOP

Oltre alle tecnologie di filtraggio della protezione da posta indesiderata, EOP fornisce anche all'amministratore di sistema la possibilità di impostare livelli di filtro per personalizzare ulteriormente il recapito della posta elettronica ai propri account utente. Gli amministratori possono facilmente aggiungere un mittente o un nome di dominio all'elenco Mittenti attendibili e domini in modo che la posta elettronica proveniente da quel mittente o dominio non venga mai trattata come posta indesiderata indipendentemente dal contenuto del messaggio. Per informazioni, vedere [elenchi di mittenti attendibili e bloccati in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).
  
### <a name="phishing-protection"></a>Protezione dal phishing

Il phishing (pronunciato "Fishing") è una forma di furto di identità e una delle minacce in più rapida crescita su Internet. È spesso possibile identificare un messaggio di phishing quando richiede informazioni personali o finanziarie o include un collegamento a un sito Web che richiede tali informazioni. EOP offre la protezione anti-phishing come parte delle tecnologie di filtraggio EOP proprietarie. Le tecnologie di filtro di EOP analizzano la posta elettronica per individuare i collegamenti fraudolenti o i domini contraffatti per proteggere gli utenti da questi tipi di truffe online.
  
#### <a name="how-does-phishing-protection-work"></a>Come funziona la protezione anti-phishing?

Spesso un messaggio di posta elettronica di phishing verrà inviato contenente un collegamento, una volta che si è fatto clic sul collegamento reindirizza gli utenti a un sito Web fraudolento che sembra valido (come l'istituto finanziario o il servizio online). In genere, questo sito di phishing richiede agli utenti di immettere informazioni personali come nomi utente, password e numeri di previdenza sociale. Tutte le informazioni immesse nel sito di phishing consentono all'truffatore di rubare la propria identità. Utilizzando i marchi e i loghi attendibili noti, phisher è in grado di essere legittimo. La tecnologia dei filtri antiphishing offerti in EOP verifica la possibilità di potenziali caratteristiche di phishing nella posta elettronica. Se trovato, il messaggio di posta elettronica viene spostato nella cartella di posta indesiderata.
  
Microsoft sta concentrando gli sforzi della tecnologia anti-phishing su due fronti: innanzitutto, contribuendo a impedire ai messaggi di posta elettronica di phishing di raggiungere gli utenti e in secondo luogo, contribuendo ad eliminare la possibilità per gli utenti di essere ingannati da messaggi di posta elettronica contraffatti e siti Web. 
  
> [!TIP]
> Internet Explorer versione 7 e versioni successive bloccano o avvisano gli utenti quando visitano siti di phishing noti o potenziali, in modo che non vengano indotti a fornire informazioni personali. Verificare [di disporre della versione più recente di Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx). 
  
#### <a name="authentication"></a>Autenticazione

Lo spoofing del dominio è un modo per imitare un indirizzo di posta elettronica legittimo per rendere legittima la posta elettronica fraudolenta. Lo spoofing viene utilizzato da utenti malintenzionati o organizzazioni nelle truffe di phishing per attirare le persone a divulgare informazioni personali sensibili. La divulgazione di tali informazioni può comportare l'identificazione dei furti e di altri tipi di frodi.
  
EOP utilizza sender Protection Framework (SPF), DomainKeys identificò la posta (DKIM) e l'autenticazione dei messaggi basata sul dominio, la creazione di report e la conformità (DMARC) e altre autenticazioni implicite per verificare che i messaggi provengono dal dominio da cui predicono di provenire . È consigliabile che tutti i mittenti utilizzino SPF e DKIM per proteggere i destinatari dalla posta indesiderata e dalle truffe di phishing. È consigliabile che i mittenti ritengano di pubblicare un DMARC per rifiutare o mettere in quarantena la posta inviata da mittenti non autorizzati.
  
- Per ulteriori informazioni su SPF, vedere [RFC 7208](https://tools.ietf.org/html/rfc7208) and [Sender Policy Framework](https://www.openspf.org/).
    
- Per ulteriori informazioni su DKIM, vedere [RFC 6376](https://tools.ietf.org/html/rfc6376) e [DKIM.org](https://dkim.org/).
    
- Per ulteriori informazioni su DMARC, vedere [DMARC.org](https://dmarc.org/).
    
### <a name="legislation"></a>Legislazione

Microsoft, riteniamo che lo sviluppo di nuove tecnologie e autoregolamentazione richieda il supporto di politiche governative effettive e di quadri giuridici. La proliferazione di posta indesiderata a livello mondiale ha spinto numerose organizzazioni legislative a regolare la posta elettronica commerciale. Molti paesi/aree geografiche dispongono ora di leggi sulla lotta contro la posta indesiderata. Gli Stati Uniti dispongono di leggi federali e statali che disciplinano lo spam e questo approccio complementare contribuisce a limitare la posta indesiderata, consentendo al commercio elettronico legittimo di prosperare. L'Act CAN-SPAM espande gli strumenti disponibili per limitare i messaggi di posta elettronica fraudolenti e ingannevoli.
  

