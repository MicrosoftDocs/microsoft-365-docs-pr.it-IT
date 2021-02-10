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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono conoscere le impostazioni e i filtri di protezione da posta indesiderata che consentono di evitare la posta indesiderata in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ae2c4f42d42c37f5b7a7df2b6c8306fd390b0af
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175860"
---
# <a name="anti-spam-protection-in-eop"></a>Protezione da posta indesiderata in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> Questo argomento è destinato agli amministratori. Per gli argomenti relativi agli utenti finali, vedere [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) e Learn about junk email and [phishing.](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i messaggi di posta elettronica vengono protetti automaticamente dalla posta indesiderata (posta indesiderata) da EOP.

La roadmap di sicurezza della posta elettronica di Microsoft prevede un approccio tra prodotti non corrispondente. La tecnologia di protezione da posta indesiderata e anti-phishing di EOP viene applicata nelle piattaforme di posta elettronica per fornire agli utenti gli strumenti e le innovazioni più recenti per la protezione da posta indesiderata e anti-phishing in tutta la rete. L'obiettivo di EOP è offrire un servizio di posta elettronica completo e utilizzabile che consente di rilevare e proteggere gli utenti dalla posta indesiderata, dalle minacce fraudolente alla posta elettronica (phishing) e dal malware.

Con la crescita dell'uso della posta elettronica, anche l'uso improprio della posta elettronica. La posta indesiderata non monitorata può intasare le cartelle di posta in arrivo e le reti, influire sulla soddisfazione degli utenti e ostacolare l'efficacia delle comunicazioni di posta elettronica legittime. Ecco perché Microsoft continua a investire in tecnologie di protezione dalla posta indesiderata. In parole semplici, inizia con il contenere e filtrare la posta indesiderata.

> [!TIP]
> Le seguenti tecnologie di protezione dalla posta indesiderata sono utili quando si desidera consentire o bloccare i messaggi in base alla busta del messaggio (ad esempio, il dominio del mittente o l'indirizzo IP di origine del messaggio). Per consentire o bloccare i messaggi in base al payload (ad esempio, URL nel messaggio o file allegati), è necessario usare il portale dell'elenco di indirizzi [consentiti/bloccati del tenant.](tenant-allow-block-list.md)

## <a name="anti-spam-technologies-in-eop"></a>Tecnologie di protezione da posta indesiderata in EOP

Per ridurre la posta indesiderata, EOP include la protezione dalla posta indesiderata che utilizza tecnologie di filtro della posta indesiderata proprietarie per identificare e separare la posta indesiderata dalla posta elettronica legittima. Il filtro della posta indesiderata di EOP apprende dalle minacce note di posta indesiderata e phishing e dal feedback degli utenti dalla nostra piattaforma consumer, Outlook.com. Il continuo feedback degli utenti di EOP nel programma di classificazione della posta indesiderata garantisce che le tecnologie EOP siano continuamente addestrate e migliorate.

Le impostazioni di protezione da posta indesiderata in EOP sono disponibili nelle tecnologie seguenti:

- **Filtro connessioni:** identifica i server di origine della posta elettronica buoni e non consentiti all'inizio della connessione alla posta elettronica in ingresso tramite l'elenco indirizzi IP consentiti, l'elenco indirizzi IP bloccati e l'elenco indirizzi attendibili *(un* elenco dinamico ma non modificabile di mittenti attendibili gestito da Microsoft). Queste impostazioni vengono configurate nel criterio di filtro delle connessioni. Per ulteriori informazioni, [vedere Configurare il filtro connessioni.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > Spoof intelligence utilizza il filtro connessioni per creare elenchi di mittenti consentiti e bloccati che effettuano lo spoofing del dominio di posta elettronica. Per ulteriori informazioni, vedere [Altre informazioni sulla spoof intelligence in Microsoft 365.](learn-about-spoof-intelligence.md)

- **Filtro posta indesiderata (filtro contenuto):** EOP utilizza i verdetti del filtro posta indesiderata **Posta** **indesiderata,** Alta probabilità di posta **indesiderata,** Posta elettronica inviata in blocco, Posta elettronica di **phishing** e Posta elettronica **di phishing** ad alta probabilità per classificare i messaggi. È possibile configurare le azioni da eseguire in base a questi verdetti e configurare le opzioni di notifica dell'utente finale per i messaggi messi in quarantena anziché recapitati. Per ulteriori informazioni, vedere Configurare i criteri di protezione dalla posta [indesiderata in Microsoft 365.](configure-your-spam-filter-policies.md)

  > [!NOTE]
  > Per impostazione predefinita, il filtro posta indesiderata è configurato per inviare messaggi contrassegnati come posta indesiderata alla cartella Posta indesiderata del destinatario. Tuttavia, negli ambienti ibridi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare due regole del flusso di posta (note anche come regole di trasporto) nell'organizzazione Exchange locale per riconoscere le intestazioni di posta indesiderata di EOP aggiunte ai messaggi. Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtro posta indesiderata** in uscita : EOP verifica inoltre che gli utenti non inviino posta indesiderata, né nel contenuto dei messaggi in uscita né superando i limiti dei messaggi in uscita. Per ulteriori informazioni, vedere [Configurare il filtro posta indesiderata in uscita in Microsoft 365.](configure-the-outbound-spam-policy.md)

- **Spoof intelligence:** per ulteriori informazioni, vedere [Altre informazioni sulla spoof intelligence in Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="manage-errors-in-spam-filtering"></a>Gestire gli errori nel filtro posta indesiderata

È possibile che i messaggi positivi possano essere identificati come posta indesiderata (noti anche come falsi positivi) o che la posta indesiderata possa essere recapitata nella posta in arrivo. Puoi usare i suggerimenti nelle sezioni seguenti per scoprire cosa è successo e per evitare che accada in futuro.

Ecco alcune procedure consigliate che si applicano a entrambi gli scenari:

- Invia sempre messaggi non classificati in modo erre a Microsoft. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

- **Esaminare le intestazioni dei messaggi di** protezione da posta indesiderata: questi valori diranno perché un messaggio è stato contrassegnato come posta indesiderata o perché ha ignorato il filtro posta indesiderata. Per ulteriori informazioni, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md).

- Puntare il record MX a **Microsoft 365:** per consentire a EOP di fornire la protezione migliore, è sempre consigliabile che la posta elettronica sia stata recapitata prima a Microsoft 365. Per istruzioni, vedere [Creare record DNS presso qualsiasi provider di hosting DNS per Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)

  Se il record MX punta a un'altra posizione(ad esempio, una soluzione o un dispositivo di protezione da posta indesiderata di terze parti), è difficile per EOP fornire un filtro della posta indesiderata accurato. In questo scenario, è necessario configurare il filtro avanzato per i connettori (noto anche come _skip listing)._ Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Utilizzare l'autenticazione** della posta elettronica: se si è proprietari di un dominio di posta elettronica, è possibile utilizzare DNS per garantire che i messaggi provenienti da mittenti in tale dominio siano legittimi. Per impedire la posta indesiderata e lo spoofing indesiderato in EOP, utilizzare tutti i seguenti metodi di autenticazione della posta elettronica:

  - **SPF:** Sender Policy Framework verifica l'indirizzo IP di origine del messaggio rispetto al proprietario del dominio di invio. Per una rapida introduzione a SPF e per configurarla rapidamente, vedere Configurare SPF per prevenire [lo spoofing.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Per informazioni più dettagliate su come Microsoft 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), consultare innanzitutto [Come Microsoft 365 utilizza Sender Policy Framework (SPF) per prevenire lo spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail aggiunge una firma digitale all'intestazione dei messaggi inviati dal dominio. Per informazioni, vedere Usare DKIM per convalidare la posta elettronica in uscita [inviata dal dominio personalizzato in Microsoft 365.](use-dkim-to-validate-outbound-email.md)

  - **DMARC**: Autenticazione, creazione di report e conformità dei messaggi basati sul dominio consente ai sistemi di posta elettronica di destinazione di determinare cosa fare con i messaggi che non riescono a controllare SPF o DKIM e fornisce un altro livello di attendibilità per i partner di posta elettronica. Per altre informazioni, vedere [Usare DMARC per convalidare la posta elettronica in Microsoft 365.](use-dmarc-to-validate-email.md)

- **Verificare le** impostazioni della posta elettronica in blocco: la soglia del livello di conformità in blocco configurata nei criteri di protezione dalla posta indesiderata determina se la posta elettronica in blocco (nota anche come posta grigia) viene contrassegnata come posta indesiderata. Anche l'impostazione solo di _PowerShell MarkAsSpamBulkMail_ attivata per impostazione predefinita contribuisce ai risultati. Per ulteriori informazioni, vedere Configurare i criteri di protezione dalla posta [indesiderata in Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedire il recapito della posta indesiderata nella posta in arrivo

- **Verificare le impostazioni** dell'organizzazione: controllare le impostazioni che consentono ai messaggi di ignorare il filtro posta indesiderata (ad esempio, se si aggiunge il proprio dominio all'elenco dei domini consentiti nei criteri di protezione da posta indesiderata). Per le impostazioni consigliate, vedere Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di [Office 365](recommended-settings-for-eop-and-office365-atp.md) [e Creare elenchi di mittenti attendibili.](create-safe-sender-lists-in-office-365.md)

- **Verificare** che la regola di posta indesiderata sia abilitata nella cassetta postale dell'utente: è abilitata per impostazione predefinita, ma se è disabilitata, i messaggi contrassegnati come posta indesiderata non possono essere spostati nella cartella Posta indesiderata. Per ulteriori informazioni, vedere Configurare le impostazioni di posta indesiderata nelle [cassette postali di Exchange Online in Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Utilizzare gli elenchi di mittenti bloccati disponibili:** per informazioni, vedere [Creare elenchi di mittenti bloccati.](create-block-sender-lists-in-office-365.md)

- **Annullare la sottoscrizione alla posta elettronica in blocco** Se il messaggio è qualcosa a cui l'utente si è iscritto (newsletter, annunci di prodotti e così via) e contiene un collegamento di annullamento della sottoscrizione da una fonte affidabile, valuta la possibilità di chiedere loro semplicemente di annullare la sottoscrizione.

- EOP autonomo: creare regole del flusso di posta nei verdetti del filtro della posta indesiderata di Exchange locale per **EOP:** negli ambienti EOP autonomi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (note anche come regole di trasporto) in Exchange locale per tradurre il verdetto del filtro della posta indesiderata di EOP in modo che la regola di posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Impedire che la posta elettronica venga identificata come posta indesiderata

Ecco alcuni passaggi che puoi eseguire per evitare falsi positivi:

- Verificare le impostazioni del filtro per la posta indesiderata **di Outlook dell'utente:**

  - **Verificare che** il filtro per la posta indesiderata di Outlook sia disabilitato: quando il filtro per la posta indesiderata di Outlook è impostato sul valore predefinito Nessun filtro **automatico,** Outlook non tenta di classificare gli elementi indesiderati come posta indesiderata.  Quando è impostato  su Basso o **Alto,** il filtro per la posta indesiderata di Outlook utilizza la propria tecnologia di filtro SmartScreen per identificare e spostare la posta indesiderata nella cartella Posta indesiderata, in modo da ottenere falsi positivi. Si noti che Microsoft ha smesso di produrre aggiornamenti delle definizioni di posta indesiderata per i filtri SmartScreen in Exchange e Outlook a novembre 2016. Le definizioni di posta indesiderata di SmartScreen esistenti sono state lasciata sul posto, ma è probabile che la loro efficacia si degradi nel tempo.

  - **Verificare** che l'impostazione Solo elenchi indirizzi attendibili di Outlook sia disabilitata: quando questa impostazione è abilitata, solo i messaggi provenienti dai mittenti presenti nell'elenco Mittenti attendibili o nell'elenco Destinatari attendibili dell'utente vengono recapitati nella cartella Posta in arrivo. la posta elettronica di tutti gli altri utenti viene spostata automaticamente nella cartella Posta indesiderata.

  Per ulteriori informazioni su queste impostazioni, vedere Configurare le impostazioni di posta indesiderata nelle [cassette postali di Exchange Online in Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Utilizzare gli elenchi di mittenti attendibili disponibili:** per informazioni, vedere [Creare elenchi di mittenti attendibili.](create-safe-sender-lists-in-office-365.md)

- **Verificare che gli utenti siano entro i limiti di invio** e ricezione, come descritto in [Limiti](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) di ricezione e invio nella descrizione del servizio Exchange Online.

- **EOP autonomo:** utilizzare la sincronizzazione della directory: se si utilizza EOP autonomo per proteggere l'organizzazione exchange locale, è consigliabile sincronizzare le impostazioni utente con il servizio utilizzando la sincronizzazione della directory. In questo modo, si ha la certezza che gli elenchi dei Mittenti attendibili vengano rispettati da Exchange Online Protection. Per ulteriori informazioni, vedere [Utilizzare la sincronizzazione della directory per gestire gli utenti di posta](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Legislazione antispam

Microsoft ritiene che lo sviluppo di nuove tecnologie e autoregolamentazione richieda il supporto di efficaci criteri governativi e quadri normativi. La proliferazione di posta indesiderata in tutto il mondo ha inciso numerosi organi normativi a regolare la posta elettronica commerciale. Molti paesi hanno ora in vigore leggi antispam. Gli Stati Uniti hanno sia leggi federali che statali che regolano la posta indesiderata e questo approccio complementare contribuisce a ridurre la posta indesiderata, consentendo al contempo al legittimo e-commerce di insoddirsi. Can-SPAM Act espande gli strumenti disponibili per limitare i messaggi di posta elettronica fraudolenti e ingannetivi.
