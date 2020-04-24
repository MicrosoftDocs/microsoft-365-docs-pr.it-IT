---
title: Protezione anti-spoofing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: ''
ms.openlocfilehash: 3a306cb8bda0f5f07660f8a2af60e29a3c4d0776
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636035"
---
# <a name="anti-spoofing-protection"></a>Protezione anti-spoofing

Per i clienti di Microsoft 365 con cassette postali in Exchange Online o di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, EOP include funzionalità per la protezione dell'organizzazione dai mittenti di spoofing (falsificati).

Quando si tratta di proteggere gli utenti, Microsoft prende seriamente in considerazione il rischio di phishing. Lo spoofing è una tecnica comune usata dagli utenti malintenzionati. **I messaggi oggetto di spoofing sembrano provenire da una persona o una posizione diversa da quella reale**. Questa tecnica viene spesso usata in campagne di phishing progettate per ottenere le credenziali dell'utente. La tecnologia anti-spoofing in EOP esamina specificamente la contraffazione dell'intestazione From nel corpo del messaggio, usata per mostrare il mittente dei messaggi nei client di posta elettronica. Se EOP rileva con alta probabilità che l'intestazione From è contraffatta, il messaggio viene identificato come falsificato.

In EOP sono disponibili le tecnologie anti-spoofing seguenti:

- **Spoof Intelligence**: per esaminare i messaggi falsificati inviati da mittenti in domini interni ed esterni e consentire o bloccare tali mittenti. Per altre informazioni, vedere [Configurare spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- **Criteri anti-phishing**: in EOP il criterio anti-phishing predefinito consente di attivare o disattivare spoof intelligence, attivare o disattivare l'identificazione dei mittenti non autenticati in Outlook e specificare l'azione per i mittenti di spoofing bloccati (spostare nella cartella Posta indesiderata o mettere in quarantena). I criteri anti-phishing avanzati disponibili in Office 365 Advanced Threat Protection (ATP) includono anche impostazioni anti-imitazione (mittenti e domini protetti), impostazioni di intelligence sulle cassette postali e soglie di phishing avanzate. Per altre informazioni, vedere [Criteri anti-phishing in Microsoft 365](set-up-anti-phishing-policies.md).

- **Autenticazione e-mail**: parte integrante di qualsiasi iniziativa anti-spoofing è l'uso dell'autenticazione e-mail, nota anche come convalida della posta elettronica, tramite i record SPF, DKIM e DMARC nel DNS. È possibile configurare questi record per un dominio in modo che i sistemi di posta elettronica di destinazione possano controllare la validità dei messaggi che dichiarano di provenire da mittenti in tale dominio. Per i messaggi in ingresso, Microsoft 365 richiede l'autenticazione di posta elettronica per i domini dei mittenti. Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).

In origine, la tecnologia anti-spoofing di Microsoft è stata distribuita solo alle organizzazioni con Office 365 Advanced Threat Protection (ATP). Nell'ottobre 2018, la protezione anti-spoofing è stata aggiunta a EOP.

EOP analizza e blocca i messaggi che non è possibile autenticare con una combinazione di metodi standard di autenticazione della posta elettronica e tecniche basate sulla reputazione del mittente.

![Controlli anti-spoofing di EOP](../../media/eop-anti-spoofing-protection.png)

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Come viene usato lo spoofing negli attacchi di phishing

I messaggi oggetto di spoofing, ovvero falsificati, hanno le implicazioni negative seguenti per gli utenti:

- **I messaggi falsificati ingannano gli utenti**: un messaggio oggetto di spoofing potrebbe indurre un utente a fare clic su un collegamento e fornire le proprie credenziali, a scaricare malware o a rispondere a un messaggio con contenuti sensibili. Quest'ultimo attacco è noto come Business Email Compromise (BEC), compromissione dell'e-mail aziendale.

  Il messaggio seguente è un esempio di phishing che usa il mittente contraffatto msoutlook94@service.outlook.com:

  ![Messaggio di phishing che imita service.outlook.com](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  Il messaggio non proviene da service.outlook.com, ma l'utente malintenzionato ha falsificato il campo di intestazione **From** intestazione per far sembrare che sia così. Si tratta di un tentativo di indurre il destinatario a fare clic sul collegamento per **modificare la password** e inserire le sue credenziali.

  Il messaggio seguente è un esempio di BEC che usa il dominio di posta elettronica contraffatto contoso.com:

  ![Messaggio di phishing - compromissione dell'e-mail aziendale](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  Il messaggio sembra legittimo ma il mittente è contraffatto.

- **Gli utenti confondono i messaggi autentici con quelli contraffatti**: anche gli utenti che conoscono il phishing potrebbero avere difficoltà a distinguere tra messaggi reali e falsificati.

  Il messaggio di seguito è un esempio di messaggio reale di reimpostazione della password inviato dal team per la sicurezza degli account Microsoft:

  ![Messaggio legittimo di reimpostazione della password di Microsoft](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  Il messaggio proveniva davvero da Microsoft, ma gli utenti sono diventati sospettosi. Poiché è difficile capire la differenza tra un messaggio di reimpostazione della password autentico e uno contraffatto, molti utenti potrebbero ignorare il messaggio, segnalarlo come posta indesiderata o segnalarlo inutilmente a Microsoft come phishing.

## <a name="different-types-of-spoofing"></a>Tipi diversi di spoofing

Microsoft distingue tra due diversi tipi di spoofing dei messaggi:

- **Spoofing intra-organizzazione**: anche noto come spoofing _self-to-self_. Ad esempio:

  - Il mittente e il destinatario si trovano nello stesso dominio:
    > Da: chris@contoso.com <br/> A: michelle@contoso.com

  - Il mittente e il destinatario si trovano in sottodomini nello stesso dominio:
    > Da: laura@marketing.fabrikam.com <br/> A: julia@engineering.fabrikam.com

  - Il mittente e il destinatario si trovano in domini diversi che appartengono alla stessa organizzazione, vale a dire che entrambi i domini sono configurati come [domini accettati](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nella stessa organizzazione:
    > Da: mittente @ microsoft.com <br/> A: destinatario @ bing.com

    Negli indirizzi di posta elettronica vengono usati spazi per impedire la raccolta da parte di spambot.

  I messaggi che non superano l'[autenticazione composita](email-validation-and-authentication.md#composite-authentication) per spoofing intra-organizzazione contengono i valori di intestazione seguenti:

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11`

  - `reason=6xx` indica lo spoofing intra-organizzazione.

  - CAT è la categoria del messaggio. In genere è SPM (posta indesiderata), ma occasionalmente può essere HSPM (posta indesiderata con alta confidenza) o PHISH (phishing) a seconda degli altri tipi di schema rilevati nel messaggio.

  - SFTY è il livello di sicurezza del messaggio. 9 indica il phishing, .11 indica lo spoofing intra-organizzazione.

- **Spoofing tra domini**: i domini del mittente e del destinatario sono diversi e non hanno relazioni gli uni con gli altri (si parla anche di domini esterni). Ad esempio:
    > Da: chris@contoso.com <br/> A: michelle@tailspintoys.com

  I messaggi che non superano l'[autenticazione composita](email-validation-and-authentication.md#composite-authentication) a causa dello spoofing tra domini contengono i valori di intestazione seguenti:

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - Il valore `reason=000` indica che il messaggio non ha superato l'autenticazione e-mail esplicita. `reason=001` indica che il messaggio non ha superato l'autenticazione e-mail implicita.

  - SFTY è il livello di sicurezza del messaggio. 9 indica il phishing, .22 indica lo spoofing tra domini.

Per altre informazioni sui valori di categoria e autenticazione composita (CompAuth) correlati allo spoofing, vedere [Intestazioni messaggi della protezione da posta indesiderata in Microsoft 365](anti-spam-message-headers.md).

Per altre informazioni su DMARC, vedere [Usare DMARC per convalidare la posta elettronica in Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="reports-of-how-many-messages-were-marked-as-spoofed"></a>Report relativi al numero di messaggi contrassegnati come spoofing

Le organizzazioni di EOP possono usare il report **Rilevamenti spoof** nel dashboard dei report del Centro sicurezza e conformità. Per altre informazioni, vedere [Report Rilevamenti spoof](view-email-security-reports.md#spoof-detections-report).

Un 'organizzazione di Office 365 ATP può usare Esplora minacce nel Centro sicurezza e conformità per visualizzare informazioni sui tentativi di phishing. Per altre informazioni, vedere [Analisi e risposta alle minacce di Microsoft 365](office-365-ti.md).

## <a name="problems-with-anti-spoofing-protection"></a>Problemi correlati alla protezione anti-spoofing

È noto che le liste di distribuzione, dette anche elenchi di discussione, hanno problemi con l'anti-spoofing a causa del modo in cui inoltrano e modificano i messaggi.

Ad esempio, Gabriela Laureano (glaureano@contoso.com) è interessata al birdwatching, aderisce alla lista di distribuzione birdwatchers@fabrikam.com e invia il messaggio seguente alla lista:

> **Da:** "Gabriela Laureano" \<glaureano@contoso.com\> <br/> **A:** Elenco di discussione Birdwatchers \<birdwatchers@fabrikam.com\> <br/> 
**Oggetto:** ottimo avvistamento dei Jays blu sula cima del Monte. Rainier questa settimana <br/><br/>Qualche utente desidera vedere la visualizzazione di questa settimana dal monte Rainier?

Il server della lista di distribuzione riceve il messaggio, ne modifica il contenuto e lo riproduce ai membri della lista. Il messaggio riprodotto ha lo stesso indirizzo del mittente (glaureano@contoso.com), ma è stato modificato aggiungendo un tag alla riga dell'oggetto e un piè di pagina in fondo. Questo tipo di modifica è comune nelle liste di distribuzione e può generare falsi positivi.

> **Da:** "Gabriela Laureano" \<glaureano@contoso.com\> <br/> **A:** Elenco di discussione Birdwatchers \<birdwatchers@fabrikam.com\> <br/> **Oggetto:** [BIRDWATCHING] ottimo avvistamento dei Jays blu sula cima del Monte Rainier questa settimana <br/><br/> Qualche utente desidera vedere la visualizzazione di questa settimana dal monte Rainier? <br/><br/> Questo messaggio è stato inviato all'elenco di discussione degli amanti del birdwatching. È possibile annullare l’iscrizione in qualsiasi momento.

Per consentire ai messaggi delle liste di distribuzione di superare i controlli anti-spoofing, eseguire le operazioni seguenti in base al fatto che si controlli o meno la lista di distribuzione:

- L'organizzazione è proprietaria della lista di distribuzione:

  - Consultare le domande frequenti su DMARC.org e leggere la domanda: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F) (Gestisco una lista di distribuzione e desidero interagire con DMARC, cosa devo fare?).

  - Leggere le istruzioni in questo post di blog: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/) (Un suggerimento per gli operatori delle liste di distribuzione che interagiscono con DMARC per evitare errori).

  - Prendere in considerazione l'installazione degli aggiornamenti nel server delle liste di distribuzione per supportare ARC, vedere[https://arc-spec.org](https://arc-spec.org/)

- L'organizzazione non è proprietaria della lista di distribuzione:

  - Chiedere al gestore della lista di distribuzione di configurare l'autenticazione e-mail per il dominio da cui la lista di distribuzione esegue l'inoltro.

    Quando un numero sufficiente di mittenti risponde ai proprietari dei domini che dovrebbero impostare i record di autenticazione della posta elettronica, li sprona a intervenire. Anche se Microsoft è compatibile con i proprietari di dominio per pubblicare i record necessari, è ancora più utile quando i singoli utenti lo richiedono.

  - Creare regole di posta in arrivo nel client di posta elettronica per spostare i messaggi nella cartella Posta in arrivo. È anche possibile chiedere agli amministratori di configurare override come descritto in [Usare spoof intelligence per configurare i mittenti di posta elettronica non autenticata consentiti](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email).

  - Creare un ticket di supporto con Microsoft 365 per creare una sostituzione per la lista di distribuzione al fine di trattarla come legittima. Per altre informazioni, vedere [Contattare il supporto per i prodotti per le aziende - Guida per amministratori](../../admin/contact-support-for-business-products.md).

Se il problema persiste, è possibile segnalare il messaggio come falso positivo a Microsoft. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

È anche possibile contattare l'amministratore, che può aprire un ticket di supporto con Microsoft. Il team di sviluppo Microsoft analizzerà il motivo per cui il messaggio è stato contrassegnato come spoofing.

## <a name="considerations-for-anti-spoofing-protection"></a>Considerazioni per la protezione anti-spoofing

Gli amministratori che attualmente inviano messaggi a Microsoft 365 devono assicurarsi che la posta elettronica venga autenticata correttamente. In caso contrario, potrebbero essere contrassegnati come posta indesiderata o phishing. Per altre informazioni, vedere [Soluzioni per i mittenti legittimi che inviano messaggi di posta elettronica non autenticati](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).