---
title: Protezione anti-spoofing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: Informazioni per amministratori sulle funzionalità anti-spoofing disponibili in Exchange Online Protection (EOP), che possono contribuire a ridurre gli attacchi di phishing da mittenti e domini contraffatti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 17228f634dc4aee9cfd416ca676920a5b4e0fba2
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779495"
---
# <a name="anti-spoofing-protection-in-eop"></a>Protezione anti-spoofing in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, EOP include funzionalità per la protezione dell'organizzazione dai mittenti di spoofing (falsificati).

Quando si tratta di proteggere gli utenti, Microsoft prende seriamente in considerazione il rischio di phishing. Lo spoofing è una tecnica comune usata dagli utenti malintenzionati. **I messaggi oggetto di spoofing sembrano provenire da una persona o una posizione diversa da quella reale**. Questa tecnica viene spesso usata in campagne di phishing progettate per ottenere le credenziali dell'utente. La tecnologia anti-spoofing in EOP esamina specificamente la contraffazione dell'intestazione From nel corpo del messaggio, usata per mostrare il mittente dei messaggi nei client di posta elettronica. Se EOP rileva con alta probabilità che l'intestazione From è contraffatta, il messaggio viene identificato come falsificato.

In EOP sono disponibili le tecnologie anti-spoofing seguenti:

- **Autenticazione e-mail**: parte integrante di qualsiasi iniziativa anti-spoofing è l'uso dell'autenticazione e-mail, nota anche come convalida della posta elettronica, tramite i record SPF, DKIM e DMARC nel DNS. È possibile configurare questi record per un dominio in modo che i sistemi di posta elettronica di destinazione possano controllare la validità dei messaggi che dichiarano di provenire da mittenti in tale dominio. Per i messaggi in ingresso, Microsoft 365 richiede l'autenticazione di posta elettronica per i domini dei mittenti. Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).

  EOP analizza e blocca i messaggi che non è possibile autenticare con una combinazione di metodi standard di autenticazione della posta elettronica e tecniche basate sulla reputazione del mittente.

  ![Controlli anti-spoofing di EOP](../../media/eop-anti-spoofing-protection.png)

- **Dati analitici di Spoof intelligence**: rivedere i messaggi oggetto di spoofing dai mittenti nei domini interni ed esterni negli ultimi 7 giorni e consentire o bloccare tali mittenti. Per altre informazioni, vedere [Dati analitici di spoof intelligence in EOP](learn-about-spoof-intelligence.md).

- **Consentire o bloccare i mittenti di spoofing nel tenant Elenco consentiti/bloccati**: quando si esegue l'override del verdetto nei dati analitici di spoof intelligence, il mittente di spoofing diventa una voce nell'Elenco consentiti/bloccati manuale che compare unicamente nella scheda **Spoofing** nel tenant Elenco consentiti/bloccati. Inoltre, è possibile creare, consentire o bloccare manualmente le voci per i mittenti di spoofing prima che vengano rilevati da spoof intelligence. Per altre informazioni, vedere [Gestire il tenant Elenco consentiti/blcocati in EOP](tenant-allow-block-list.md).

- **Criteri anti-phishing**: in EOP e Microsoft Defender per Office 365, i criteri anti-phishing contengono le seguenti impostazioni anti-spoofing:
  - Attivare o disattivare spoof intelligence.
  - Attivare o disattivare l'identificazione dei mittenti non autenticati in Outlook.
  - Specificare l'azione per i mittenti di spoofing bloccati.

  Per altre informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

  **Nota**: i criteri anti-phishing in Microsoft Defender per Office 365 contengono protezioni aggiuntive, inclusa la protezione da **imitazione**. Per altre informazioni, vedere [Impostazioni esclusive nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- **Report di rilevamento spoofing**: per altre informazioni, vedere [Report di rilevamento spoofing](view-email-security-reports.md#spoof-detections-report).

  **Nota**: Le organizzazioni Defender per Office 365 possono anche usare i Rilevamenti in tempo reale (Piano 1) o Esplora minacce (Piano 2) per visualizzare le informazioni relative ai tentativi di phishing. Per altre informazioni, vedere [Analisi e risposta alle minacce di Microsoft 365](office-365-ti.md).

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

  Il messaggio proveniva effettivamente da Microsoft, ma gli utenti sono diventati sospettosi. Poiché è difficile capire la differenza tra un messaggio di reimpostazione della password autentico e uno contraffatto, molti utenti potrebbero ignorare il messaggio, segnalarlo come posta indesiderata o segnalarlo inutilmente a Microsoft come phishing.

## <a name="different-types-of-spoofing"></a>Tipi diversi di spoofing

Microsoft distingue tra due diversi tipi di spoofing dei messaggi:

- **Spoofing intra-organizzazione**: anche noto come spoofing _self-to-self_. Ad esempio:

  - Il mittente e il destinatario si trovano nello stesso dominio:
    > Da: chris@contoso.com <br> A: michelle@contoso.com

  - Il mittente e il destinatario si trovano in sottodomini nello stesso dominio:
    > Da: laura@marketing.fabrikam.com <br> A: julia@engineering.fabrikam.com

  - Il mittente e il destinatario si trovano in domini diversi che appartengono alla stessa organizzazione, vale a dire che entrambi i domini sono configurati come [domini accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nella stessa organizzazione:
    > Da: mittente @ microsoft.com <br> A: destinatario @ bing.com

    Negli indirizzi di posta elettronica vengono usati spazi per impedire la raccolta da parte di spambot.

  I messaggi che non superano l'[autenticazione composita](email-validation-and-authentication.md#composite-authentication) per spoofing intra-organizzazione contengono i valori di intestazione seguenti:

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - `reason=6xx` indica lo spoofing intra-organizzazione.

  - SFTY è il livello di sicurezza del messaggio. 9 indica il phishing, .11 indica lo spoofing intra-organizzazione.

- **Spoofing tra domini**: i domini del mittente e del destinatario sono diversi e non hanno relazioni gli uni con gli altri (si parla anche di domini esterni). Ad esempio:
    > Da: chris@contoso.com <br> A: michelle@tailspintoys.com

  I messaggi che non superano l'[autenticazione composita](email-validation-and-authentication.md#composite-authentication) a causa dello spoofing tra domini contengono i valori di intestazione seguenti:

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - `reason=000` indica che il messaggio non ha superato l'autenticazione e-mail esplicita. `reason=001` indica che il messaggio non ha superato l'autenticazione e-mail implicita.

  - `SFTY` è il livello di sicurezza del messaggio. 9 indica il phishing, .22 indica lo spoofing tra domini.

> [!NOTE]
> Se è stato ricevuto un messaggio come ***compauth=fail reason=###** _ e devi conoscere l'autenticazione composita (compauth) e i valori correlati allo spoofing, vedi [_Intestazioni dei messaggi antispam in Microsoft 365*](anti-spam-message-headers.md). Oppure passa direttamente ai codici [*motivo*](anti-spam-message-headers.md).

Per altre informazioni su DMARC, vedere [Usare DMARC per convalidare la posta elettronica in Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="problems-with-anti-spoofing-protection"></a>Problemi correlati alla protezione anti-spoofing

È noto che le liste di distribuzione, dette anche elenchi di discussione, hanno problemi con l'anti-spoofing a causa del modo in cui inoltrano e modificano i messaggi.

Ad esempio, Gabriela Laureano (glaureano@contoso.com) è interessata al birdwatching, aderisce alla lista di distribuzione birdwatchers@fabrikam.com e invia il messaggio seguente alla lista:

> **Da:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **A:** Elenchi di Discussione dei Birdwatcher \<birdwatchers@fabrikam.com\> <br> **Oggetto:** ottimo avvistamento dei Jays blu sula cima del Monte Rainier questa settimana <p> Qualche utente desidera controllare la vista dal Monte Rainer questa settimana?

Il server della lista di distribuzione riceve il messaggio, ne modifica il contenuto e lo riproduce ai membri della lista. Il messaggio riprodotto ha lo stesso indirizzo del mittente (glaureano@contoso.com), ma è stato modificato aggiungendo un tag alla riga dell'oggetto e un piè di pagina in fondo. Questo tipo di modifica è comune nelle liste di distribuzione e può generare falsi positivi.

> **Da:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **A:** Elenchi di Discussione dei Birdwatcher \<birdwatchers@fabrikam.com\> <br> **Oggetto:** [BIRDWATCHING] ottimo avvistamento dei Jays blu sula cima del Monte Rainier questa settimana <p> Qualche utente desidera controllare la vista dal Monte Rainer questa settimana? <p> Questo messaggio è stato inviato all'elenco di discussione degli amanti del birdwatching. È possibile annullare l’iscrizione in qualsiasi momento.

Per consentire ai messaggi delle liste di distribuzione di superare i controlli anti-spoofing, eseguire le operazioni seguenti in base al fatto che si controlli o meno la lista di distribuzione:

- L'organizzazione è proprietaria della lista di distribuzione:

  - Consultare le domande frequenti su DMARC.org e leggere la domanda: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F) (Gestisco una lista di distribuzione e desidero interagire con DMARC, cosa devo fare?).

  - Leggere le istruzioni in questo post di blog: [A tip for mailing list operators to interoperate with DMARC to avoid failures](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures) (Un suggerimento per gli operatori delle liste di distribuzione che interagiscono con DMARC per evitare errori).

  - Prendere in considerazione l'installazione degli aggiornamenti nel server delle liste di distribuzione per supportare ARC, vedere<http://arc-spec.org>.

- L'organizzazione non è proprietaria della lista di distribuzione:

  - Chiedere al gestore della lista di distribuzione di configurare l'autenticazione e-mail per il dominio da cui la lista di distribuzione esegue l'inoltro.

    Quando un numero sufficiente di mittenti risponde ai proprietari dei domini che dovrebbero impostare i record di autenticazione della posta elettronica, li sprona a intervenire. Anche se Microsoft è compatibile con i proprietari di dominio per pubblicare i record necessari, è ancora più utile quando i singoli utenti lo richiedono.

  - Creare regole di posta in arrivo nel client di posta elettronica per spostare i messaggi nella cartella Posta in arrivo. Inoltre, è possibile chiedere agli amministratori di configurare gli override come descritto in [Dati analitici di spoof intelligence in EOP](learn-about-spoof-intelligence.md) e [Gestire il tenant Elenco consentiti/bloccati](tenant-allow-block-list.md).

  - Creare un ticket di supporto con Microsoft 365 per creare una sostituzione per la lista di distribuzione al fine di trattarla come legittima. Per altre informazioni, vedere [Contattare il supporto per i prodotti per le aziende - Guida per amministratori](../../business-video/get-help-support.md).

Se il problema persiste, è possibile segnalare il messaggio come falso positivo a Microsoft. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

È anche possibile contattare l'amministratore, che può aprire un ticket di supporto con Microsoft. Il team di sviluppo Microsoft analizzerà il motivo per cui il messaggio è stato contrassegnato come spoofing.

## <a name="considerations-for-anti-spoofing-protection"></a>Considerazioni per la protezione anti-spoofing

Gli amministratori che attualmente inviano messaggi a Microsoft 365 devono assicurarsi che la posta elettronica venga autenticata correttamente. In caso contrario, potrebbero essere contrassegnati come posta indesiderata o phishing. Per altre informazioni, vedere [Soluzioni per i mittenti legittimi che inviano messaggi di posta elettronica non autenticati](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).

I mittenti di un elenco di mittenti di un utente (o amministratore) specifico ignoreranno delle parti dello stack di filtraggio, inclusa la protezione contro lo spoofing. Per altre informazioni, vedere [Mittenti attendibili di Outlook](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).

Gli amministratori devono evitare, se possibile, di usare gli elenchi di mittenti consentiti o di domini consentiti. Questi mittenti ignorano tutte le protezioni da posta indesiderata, spoofing e phishing, e anche l'autenticazione del mittente (SPF, DKIM, DMARC). Per altre informazioni, vedere [Usare gli elenchi di mittenti o domini consentiti](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).
