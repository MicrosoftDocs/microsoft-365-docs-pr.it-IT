---
title: Procedure consigliate per la configurazione di EOP e Office 365 ATP Security, Best Practices, Settings, consigli, Sender Policy Framework, domain-based Message Reporting and Conformity, DomainKeys Identified Mail, Steps, how it work,
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Quali sono le procedure consigliate per le impostazioni di sicurezza di Exchange Online Protection (EOP) e Advanced Threat Protection (ATP)? Cosa è consigliato? Che cosa dovrebbe essere usato in modo aggressivo? Quali sono gli extra che si ottengono se si utilizza anche Advanced Threat Protection (ATP)?
ms.openlocfilehash: b40b4189ed996e1b2f671b77602630f2a98966a5
ms.sourcegitcommit: ffdf576fbc62c4c316f6d8061d2bd973e7df9f56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2019
ms.locfileid: "37598300"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>Procedure consigliate per la configurazione di EOP e Office 365 ATP Security

Exchange Online Protection (EOP) è il fulcro della sicurezza per gli abbonamenti all'E3 di Office 365. È facoltativo e persino consigliato ai clienti E3 di acquistare un abbonamento a Office 365 Advanced Threat Protection (ATP), ex. ATP piano 1 o ATP piano 2, per sfruttare la sicurezza aggiunta disponibile in E5 Office 365 abbonamenti.

Verranno descritti due livelli di sicurezza, denominati consigliati e aggressivi in EOP, in cui vengono illustrati i commenti su come utilizzare le funzionalità a entrambi i livelli di sicurezza. Le sezioni iniziano con la convalida e l'autenticazione della posta elettronica, che richiede alcuni ritocchi all'esterno di Office 365, in DNS e protegge la posta in uscita, rendendo i tenant buoni cittadini alle risorse che inviano. Queste impostazioni migliorano la protezione dell'abbonamento.


## <a name="email-authentication"></a>Autenticazione della posta elettronica

SPF, DKIM e DMARC sono acronimi di Sender Policy Framework, DomainKeys ha identificato la posta elettronica e l'autenticazione dei messaggi basata sul dominio, la creazione di report e la conformità (un bel boccone) e rappresentano la base per l'autenticazione e la convalida della posta elettronica.

Questi metodi gestiscono la posta elettronica in uscita da Office 365 e aiutano i sistemi di destinazione a considerare che la posta elettronica del dominio è valida. Sono le uniche procedure consigliate che verranno riportate che coinvolgono le configurazioni da effettuare *all'esterno* di Office 365, nel DNS. Per i passaggi di configurazione specifici, vedere la sezione [convalida e autenticazione della posta elettronica](https://docs.microsoft.com/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing) nel sommario di sicurezza e conformità.


|Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|[Creare record SPF](https://docs.microsoft.com/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | Sì        |    Sì     |   -      |
|[Configurare la firma di DKIM per i domini](https://docs.microsoft.com/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  Sì       |    Sì     |  -       |
|[Implementare DMARC con l'azione rifiuta o quarantena](https://docs.microsoft.com/office365/securitycompliance/use-dmarc-to-validate-email)     |   Sì      |     Sì    |   Use Action = None for recommended e Action = Reject for aggressive.     |

> [!IMPORTANT]
> Per utilizzare i ruoli e le autorizzazioni di sicurezza, assicurarsi di avere il ruolo o i ruoli giusti in Office 365 o il Centro sicurezza e conformità. Se si è un *amministratore della sicurezza* in Azure Active Directory, un *amministratore globale* di Office 365 o un *responsabile dell'organizzazione di Exchange Online* in Exchange Online/Exchange Online PowerShell, si è pronti a partire.

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>Protezione da posta indesiderata, anti-malware e anti-phishing

Entrambe le funzionalità di protezione da posta indesiderata e anti-malware sono caratteristiche di EOP. Filtro posta indesiderata, attiva per impostazione predefinita in Office 365, analizza tutti i messaggi di posta elettronica e assegna un valore di numero di probabilità di posta indesiderata (SCL) a ciascun messaggio. Solo per chiarire, il suo scopo è quello di enumerare la fiducia che il filtro è che la posta è (o non) posta indesiderata. I valori bassi, come-1, non sono messaggi di posta indesiderata provenienti da mittenti attendibili e terreni in una cartella posta in arrivo. Gli alti punteggi, come 7, 8 o 9, sono altamente sospetti o noti come spammer e intestazioni per la posta indesiderata di un utente o per la quarantena accessibile dall'amministratore.

Anche il filtro antimalware è attivato per impostazione predefinita in Office 365. Come il filtro anti-spam, i filtri antimalware funzionano sia in ingresso che in uscita. In entrambi i casi, questa protezione può essere configurata per una migliore adattabilità da parte degli amministratori.

I filtri di phishing sono attivati per impostazione predefinita in Office 365, ma devono essere configurati per una migliore adattamento. Di seguito è indicato ciò che si consiglia per il filtro anti-phishing in EOP.

### <a name="anti-spam"></a>Protezione da posta indesiderata

|Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|Periodo di conservazione della quarantena    |   Sì      |     Sì    |   30 giorni   |
|Frequenza della notifica di posta indesiderata dell'utente finale   |   Sì      |     Sì    |   3 giorni   |
|AutoPurge zero hour deve essere abilitata   |   Sì      |     Sì    |   True  |
|L'azione di rilevamento della posta indesiderata deve essere inviata | JMF | Quarantena | - |
|È consigliabile inviare un'azione di rilevamento della posta indesiderata ad alta sicurezza | Quarantena | Quarantena| - |
|L'azione di rilevamento in blocco deve essere impostata su | JMF | Quarantena | - |
|Impostare la soglia di posta elettronica in blocco su | 6 | 4 | - |
|I suggerimenti per la sicurezza devono essere abilitati| True | True | - |
|Abilitare la notifica di posta indesiderata dell'utente finale| True | False | - |
|Mittenti consentiti | Nessuna | Nessuna | - |
|Domini di mittenti consentiti | Nessuna | Nessuna | - |
|Mittenti bloccati | Nessuna | Nessuna | - |
|Domini mittenti bloccati | Nessuna | Nessuna | - |
|Criteri di posta indesiderata in uscita RRL | 500 | 500 | - |

Consigliata per la **disattivazione** sia nei livelli consigliati che in quelli aggressivi:

|Nome della funzionalità di sicurezza  |
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|

Consigliata **per i** livelli consigliati e aggressivi:

|Nome della funzionalità di sicurezza  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>Anti-malware

|Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|Configurare le notifiche di malware per le origini interne |Sì |Sì |- |
|Disabilitare la notifica ai mittenti esterni del rilevamento di malware |Sì |Sì |- |
|Utilizzo del "filtro tipo di allegato comune" per il blocco dei tipi di file sospetti | Sì |Sì |- |
|Malware ZAP |True |True |- |
|Azione antimalware |Blocco |Blocco |- |

### <a name="anti-phishing"></a>Anti-phishing

|Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|AutoPurge zero hour deve essere abilitato-phishing| True | True | - | 
|L'azione di rilevamento di phishing deve essere impostata su | Quarantena-richiesta | Quarantena-amministratore | - |
|È consigliabile impostare l'azione di rilevamento phishing ad alta sicurezza su | Quarantena-amministratore | Quarantena-amministratore | - |
|EnableMailboxIntelligence | True | True | - |
|EnableSimilarUsersSafetyTips | True | True | - |
|EnableSimilarDomainsSafetyTips | True | True | - |
|EnableUnusualCharactersSafetyTips | True | True | - |
|TargetedUserProtectionAction |NoAction |Blocco | - |
|MailboxIntelligenceProtectionAction |NoAction |Blocco | - |
|TargetedDomainProtectionAction |NoAction |Blocco | - |
|AuthenticationFailAction |MoveToJmf |Quarantena | - |
|AntiSpoofEnforcementType |Alta |Alta | - |
|EnableAuthenticationSafetyTip |False |True | - |
|EnableAntiSpoofEnforcement |True |True | - |
|EnableUnauthenticatedSender |True |True | - |
|EnableAuthenticationSoftPassSafetyTip |False |True | - |
|TreatSoftPassAsAuthenticated |True |False | - |
|EnableSuspiciousSafetyTip |True |True | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Sicurezza di Office 365 Advanced Threat Protection (ATP)

In precedenza, ho affermato che è stato consigliato agli abbonamenti E3 di aggiungere un Office 365 ATP Plan 1 o il più completo progetto ATP piano 2. L'anti-phishing avanzato è uno dei motivi per cui. Abilitata per impostazione predefinita, l'anti-phishing ***deve*** essere configurato con i criteri per l'utilizzo. Se si dimentica di configurare i criteri di anti-phishing, gli utenti possono rischiare, assicurarsi che sia Step-2 dopo l'aggiunta di una sottoscrizione ATP.

> [!IMPORTANT]
>  Se si dispone di un abbonamento E5, è attualmente disponibile il [piano ATP 2](https://products.office.com/exchange/advance-threat-protection). Controllare questo collegamento quando si desidera sapere cosa c' [è di nuovo in ATP](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff).

### <a name="advanced-anti-phishing"></a>Anti-phishing avanzato

Il phishing è un tentativo di mascheramento come società o persona rispettabile allo scopo di rubare informazioni personali come i numeri di carta di credito, o pin del computer o dispositivo o password. Il phishing può coinvolgere:

- **Spoofing**, in cui gli spoofing tentano di inviare messaggi di posta elettronica per conto di una destinazione specifica in un dominio (ad esempio, ellar@2020contoso.com tentando di inviare messaggi di posta elettronica per ellar@2020litware.com (un metodo di autenticazione della posta elettronica dello scenario può contribuire a contrastare). 

- **Rappresentazione**, in cui viene ricevuta la posta elettronica il cui mittente è visivamente simile (o sosia) a un dominio di destinazione o a un nome utente. L'attore cattivo qui simula un nome utente specifico o finge di inviare posta da un dominio di destinazione. Di seguito viene indicato un dominio di pretesa: ellar @ 2020 | itware. com ed ecco un utente pretense: ellαr @ 2020litware. com (esaminare attentamente i nomi di dominio e utente in questi esempi per rilevare il dominio e la rappresentazione degli utenti).

Se è stata aggiunta una sottoscrizione di Office 365 ATP all'EOP, assicurarsi di impostare le configurazioni seguenti.

|Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|Impostare una soglia di phishing avanzata su | 2 | 4 | - |
|Abilitare la protezione contro la rappresentazione | Sì | Sì | - |
|Abilitare l'intelligence delle cassette postali nei criteri di anti-rappresentazione | Sì | Sì | - |
|Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali | Sì | Sì | - |
|L'azione di rappresentazione del dominio deve essere | JMF | Quarantena | - |
|L'azione di rappresentazione dell'utente deve essere | JMF | Qurantine | - |
|L'azione di protezione della rappresentazione basata sull'Intelligence delle cassette postali dovrebbe essere |Punta  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>Collegamenti sicuri e allegati sicuri

 ATP include i criteri per i collegamenti sicuri e gli allegati sicuri per evitare che la posta elettronica con allegati potenzialmente dannosi venga recapitata e per impedire agli utenti di fare clic e viaggiare in URL potenzialmente non sicuri.

#### <a name="safe-links"></a>Collegamenti sicuri

|Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|I collegamenti sicuri di ATP devono tenere conto dei clic degli utenti ai fini della risposta |Sì |Sì |- |
|I collegamenti sicuri ATP devono essere abilitati per le applicazioni di Office |Sì |Sì |- |
|I collegamenti sicuri ATP devono essere abilitati per il dominio intra |Sì |Sì |- |
|I collegamenti sicuri di ATP devono applicare l'analisi degli URL in tempo reale per collegamenti sospetti e collegamenti che puntano a file. |Sì |Sì |- |
|I collegamenti sicuri di ATP devono attendere il completamento dell'analisi degli URL prima di recapitare il messaggio. |Sì |Sì |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>Allegati sicuri

|Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|Azione per i criteri degli allegati sicuri ATP dovrebbe essere |Quarantena |Quarantena |- |
|La protezione ATP dovrebbe essere abilitata per OneDrive, SharePoint e teams |Sì |Sì |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>Miscellaneous settings (Impostazioni varie)

Queste impostazioni riguardano una serie di caratteristiche che non si adattano necessariamente alle categorie specifiche sopra riportate. È possibile trovare anche alcune impostazioni di 1-off.

Nome della funzionalità di sicurezza  |Consigliato |Aggressivo  |Commento  |
|---------|---------|---------|---------|
|Creare record SPF |Sì |Sì |- |
|Configurare la firma di DKIM per i domini |Sì |Sì |- |
|Implementare la segnalazione e la conformità dei messaggi basati sul dominio (DMARC) con l'azione Reject o Quarantine |azione = none |azione = rifiuto | |
|Distribuire il componente aggiuntivo dei messaggi di report per migliorare la segnalazione degli utenti finali di messaggi di posta elettronica sospetti |Sì |Sì |- |
|Pianificare i report di malware e posta indesiderata |Sì |Sì |- |
|L'auto-fowarding ai domini esterni deve essere non consentita o monitorata |- |Sì |- |
|Il controllo unificato dovrebbe essere abilitato |Sì |Sì |- |
|IMAP deve essere disabilitato se non necessario |- |disabili |- |
|POP dovrebbe essere disabilitato se non necessario |- |disabili |- |
|L'invio autenticato SMTP deve essere disattivato se non richiesto dalle applicazioni |- |disabili |- |
|EWS devono essere disattivati |- |disabili |- |
|PowerShell |- |disabili |- |
|Configurare il Framework del criterio mittente in modo che non venga eseguito correttamente |-all |-all |- |
|Utilizzare l'intelligence spoof per i mittenti whitelist quando possibile |Sì |Sì |- |
|Blocco Edge basato su directory (DBEB) |Abilitato |Abilitato |Tipo di dominio = autorevole |
