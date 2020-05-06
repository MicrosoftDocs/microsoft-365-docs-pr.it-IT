---
title: Protezione dalla posta indesiderata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni sulle impostazioni e sui filtri di protezione da posta indesiderata che consentono di prevenire la posta indesiderata in Exchange Online e Microsoft 365.
ms.openlocfilehash: 96132bf66438861eb117aedd841f7912de1258cc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034059"
---
# <a name="anti-spam-protection-in-microsoft-365"></a>Protezione dalla posta indesiderata in Microsoft 365

> [!NOTE]
> Questo argomento è destinato a Microsoft 365 Admins. Per gli argomenti degli utenti finali, vedere [Panoramica del filtro posta indesiderata](https://support.Microsoft.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) e informazioni [sulla posta indesiderata e sul phishing](https://support.Microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

Se si è un cliente Microsoft 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, i messaggi di posta elettronica vengono protetti automaticamente dalla posta indesiderata (posta indesiderata) da EOP.

La Guida di orientamento alla sicurezza della posta elettronica di Microsoft comporta un approccio cross-product senza eguali. La tecnologia di protezione da posta indesiderata e anti-phishing di EOP viene applicata nelle piattaforme di posta elettronica per offrire agli utenti gli strumenti e le innovazioni più recenti di protezione dalla posta indesiderata e anti-phishing nella rete L'obiettivo di EOP è offrire un servizio di posta elettronica completo e utilizzabile che aiuti a rilevare e proteggere gli utenti dalla posta indesiderata, dalle minacce alla posta elettronica fraudolente (phishing) e da malware.

L'utilizzo della posta elettronica è cresciuto, quindi ha un abuso di posta elettronica. La posta indesiderata non monitorata può intasare le cassette postali e le reti, influire sulla soddisfazione degli utenti e ostacolare l'efficacia delle comunicazioni di posta elettronica. Ecco perché Microsoft continua a investire nelle tecnologie di protezione dalla posta indesiderata. In poche parole, viene avviato contenendo e filtrando la posta indesiderata.

## <a name="anti-spam-technologies-in-eop"></a>Tecnologie di protezione da posta indesiderata in EOP

Per contribuire alla riduzione della posta indesiderata, EOP include la protezione della posta indesiderata che utilizza tecnologie di filtro della posta indesiderata per identificare e separare la posta indesiderata Il filtro per la posta indesiderata di EOP viene fornito dalle minacce note e dalla posta indesiderata e dall'utente dalla piattaforma consumer, Outlook.com. Il feedback in corso da parte degli utenti di EOP nel programma di classificazione della posta indesiderata contribuisce a garantire che le tecnologie EOP siano continuamente addestrate e migliorate.

Le impostazioni di protezione da posta indesiderata in EOP sono costituite dalle seguenti tecnologie:

- **Filtro connessioni**: identifica i server di origine della posta elettronica buoni e cattivi all'inizio della connessione di posta elettronica in ingresso tramite l'elenco indirizzi IP consentiti, l'elenco indirizzi IP bloccati e l' *elenco di indirizzi* attendibili (un elenco dinamico ma non modificabile dei mittenti affidabili gestiti da Microsoft). Queste impostazioni vengono configurate nel criterio di filtro delle connessioni. Per ulteriori informazioni, vedere [Configure Connection Filtering in Microsoft 365](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Spoof Intelligence utilizza il filtro connessioni per creare gli elenchi Consenti e blocca dei mittenti che eseguono lo spoofing del dominio di posta elettronica. Per ulteriori informazioni, vedere [Learn more about spoofing Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- **Filtro posta indesiderata (filtro contenuto)**: EOP utilizza la posta indesiderata del filtro di posta indesiderata **, la**posta **indesiderata** **, e-mail di** **phishing** e posta elettronica di **phishing con elevata sicurezza** per classificare i messaggi. È possibile configurare le azioni da intraprendere in base a queste sentenze ed è possibile configurare le opzioni di notifica degli utenti finali per i messaggi che sono stati messi in quarantena anziché recapitati. Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > Per impostazione predefinita, il filtro posta indesiderata è configurato per inviare messaggi contrassegnati come posta indesiderata alla cartella posta indesiderata del destinatario. Tuttavia, negli ambienti ibridi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare due regole del flusso di posta (note anche come regole di trasporto) nell'organizzazione di Exchange locale per riconoscere le intestazioni di posta indesiderata di EOP che vengono aggiunte ai messaggi. Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtro posta indesiderata in uscita**: EOP verifica inoltre che gli utenti non inviino posta indesiderata, sia nel contenuto del messaggio in uscita o superando i limiti dei messaggi in uscita. Per ulteriori informazioni, vedere [configurare il filtro per la posta indesiderata in uscita in Microsoft 365](configure-the-outbound-spam-policy.md).

- **Intelligence spoof**: per ulteriori informazioni, vedere [Learn more about spoofing intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Gestire gli errori nel filtraggio della posta indesiderata

È possibile che i messaggi validi possano essere identificati come posta indesiderata (noti anche come falsi positivi) oppure che la posta indesiderata può essere recapitata nella cartella in arrivo. È possibile utilizzare i suggerimenti descritti nelle sezioni seguenti per scoprire cosa è successo e impedire che accada in futuro.

Di seguito sono riportate alcune procedure consigliate che si applicano a uno scenario:

- Invia sempre messaggi non classificati a Microsoft. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

- **Esaminare le intestazioni dei messaggi di protezione da posta indesiderata**: questi valori indicano il motivo per cui un messaggio è stato contrassegnato come posta indesiderata o perché ha ignorato il filtro posta indesiderata. Per ulteriori informazioni, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md).

- Impostare il **record MX su microsoft 365**: affinché EOP fornisca la protezione ottimale, è consigliabile che la posta elettronica sia stata recapitata a Microsoft 365 prima. Per istruzioni, vedere [creare record DNS in qualsiasi provider di hosting DNS per Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Se il record MX punta a un'altra posizione (ad esempio, una soluzione di protezione da posta indesiderata o un dispositivo di terze parti), è difficile per EOP fornire un filtro di posta indesiderata accurato. In questo scenario, è necessario configurare il filtro avanzato per i connettori (noti anche come _Ignora elenco_). Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Utilizzo dell'autenticazione della posta elettronica**: se si è proprietari di un dominio di posta elettronica, è possibile utilizzare DNS per garantire che i messaggi provenienti da mittenti del dominio siano legittimi. Per evitare la posta indesiderata e la falsificazione dello spoofing in EOP, utilizzare tutti i metodi di autenticazione della posta elettronica seguenti:

  - **SPF**: Sender Policy Framework verifica l'indirizzo IP di origine del messaggio in base al proprietario del dominio di invio. Per una breve introduzione a SPF e per configurarla rapidamente, vedere [set up SPF to help prevenire spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Per informazioni più dettagliate su come Microsoft 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), consultare innanzitutto [Come Microsoft 365 utilizza Sender Policy Framework (SPF) per prevenire lo spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys identificata la posta elettronica aggiunge una firma digitale all'intestazione del messaggio dei messaggi inviati dal dominio. Per ulteriori informazioni, vedere [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: l'autenticazione dei messaggi basata sul dominio, la creazione di report e la conformità consentono ai sistemi di posta elettronica di destinazione di determinare cosa fare con i messaggi che non hanno esito positivo o DKIM controlli e fornisce un altro livello di attendibilità per i partner di posta elettronica. Per ulteriori informazioni, vedere [utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](use-dmarc-to-validate-email.md).

- **Verificare le impostazioni di posta elettronica in blocco**: la soglia di livello conforme (BCL) configurata nei criteri di protezione da posta indesiderata determina se la posta elettronica in blocco (nota anche come _posta grigia_) è contrassegnata come indesiderata. L'impostazione di solo PowerShell _MarkAsSpamBulkMail_ che è attiva per impostazione predefinita contribuisce anche ai risultati. Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedire il recapito della posta indesiderata nella posta in arrivo

- **Verificare le impostazioni dell'organizzazione**: guardare fuori per le impostazioni che consentono ai messaggi di ignorare il filtro posta indesiderata (ad esempio, se si aggiunge un dominio all'elenco dei domini consentiti nei criteri di protezione da posta indesiderata). Per le impostazioni consigliate, vedere [impostazioni consigliate per EOP e Microsoft 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md) e [creare elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md).

- **Verificare che la regola di posta indesiderata sia abilitata nella cassetta postale dell'utente**: è abilitata per impostazione predefinita, ma se è disabilitata, i messaggi contrassegnati come posta indesiderata non possono essere spostati nella cartella posta indesiderata. Per ulteriori informazioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange online in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Utilizzare gli elenchi di mittenti bloccati disponibili**: per informazioni, vedere [creare elenchi di mittenti bloccati](create-block-sender-lists-in-office-365.md).

- **Annullamento della sottoscrizione alla posta elettronica in blocco** Se il messaggio è stato sottoscritto da un utente (newsletter, annunci di prodotti e così via) e contiene un collegamento di annullamento della sottoscrizione da un'origine attendibile, è consigliabile chiedergli di annullare la sottoscrizione.

- **EOP autonomo: creare regole del flusso di posta in Exchange locale per i verdetti del filtro della posta indesiderata di EOP**: in ambienti EOP indipendenti in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (note anche come regole di trasporto) in Exchange locale per tradurre il verdetto del filtro della posta indesiderata in modo che la regola Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Impedire che la posta elettronica venga identificata come posta indesiderata

Di seguito sono riportati alcuni passaggi che è possibile eseguire per impedire falsi positivi:

- **Verificare le impostazioni del filtro posta indesiderata di Outlook dell'utente**:

  - **Verificare che il filtro posta indesiderata di Outlook sia disabilitato**: quando il filtro posta indesiderata di Outlook è impostato sul valore predefinito **nessun filtro automatico**, Outlook non cerca di classificare i massaggi come posta indesiderata.  Quando è impostato su **basso** o **alto**, il filtro posta indesiderata di Outlook utilizza la propria tecnologia di filtro SmartScreen per identificare e spostare la posta indesiderata nella cartella posta indesiderata, in modo da poter ottenere falsi positivi. Si noti che Microsoft ha interrotto la produzione di aggiornamenti delle definizioni di posta indesiderata per i filtri di SmartScreen in Exchange e Outlook nel novembre 2016. Le definizioni di posta indesiderata di SmartScreen esistenti sono state lasciate sul posto, ma la loro efficacia potrebbe peggiorare nel tempo.

  - **Verificare che l'impostazione ' solo elenchi attendibili di Outlook ' sia disabilitata**: quando questa impostazione è abilitata, solo i messaggi provenienti da mittenti nell'elenco Mittenti attendibili dell'utente o nell'elenco destinatari attendibili vengono recapitati nella posta in arrivo. la posta elettronica proveniente da tutti gli utenti viene automaticamente spostata nella cartella posta indesiderata.

  Per ulteriori informazioni su queste impostazioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange online in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Utilizzare gli elenchi di mittenti attendibili disponibili**: per informazioni, vedere [creare elenchi di mittenti attendibili] (create-Safe-sender-lists-in-office-365.MD.

- **Verificare che gli utenti siano entro i limiti di invio e ricezione** , come descritto in [ricezione e invio dei limiti](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) nella descrizione del servizio Exchange Online.

- **EOP autonomo: utilizzare la sincronizzazione della directory**: se si utilizza EOP autonomo per proteggere l'organizzazione di Exchange locale, è necessario sincronizzare le impostazioni utente con il servizio utilizzando la sincronizzazione della directory. In questo modo, si ha la certezza che gli elenchi dei Mittenti attendibili vengano rispettati da Exchange Online Protection. Per ulteriori informazioni, vedere [Utilizzare la sincronizzazione della directory per gestire gli utenti di posta](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Normativa sulla protezione da posta indesiderata

Microsoft, riteniamo che lo sviluppo di nuove tecnologie e autoregolamentazione richieda il supporto di politiche governative effettive e di quadri giuridici. La proliferazione di posta indesiderata a livello mondiale ha spinto numerose organizzazioni legislative a regolare la posta elettronica commerciale. In molti paesi sono ora presenti leggi che combattono per la posta indesiderata. Gli Stati Uniti dispongono di leggi federali e statali che disciplinano lo spam e questo approccio complementare contribuisce a limitare la posta indesiderata, consentendo al commercio elettronico legittimo di prosperare. L'Act CAN-SPAM espande gli strumenti disponibili per limitare i messaggi di posta elettronica fraudolenti e ingannevoli.