---
title: Domande frequenti sulla protezione da posta indesiderata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sulla protezione da posta indesiderata in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae91e1184d8b95b936065f785b3c6bfecf9f250f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206873"
---
# <a name="anti-spam-protection-faq"></a>Domande frequenti sulla protezione da posta indesiderata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In questo argomento vengono fornite domande frequenti e risposte sulla protezione antimalware per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online o organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online.

Per domande e risposte sulla quarantena, vedere [Domande frequenti sulla quarantena](quarantine-faq.md).

Per domande e risposte sulla protezione antimalware, vedere [Domande frequenti sulla protezione antimalware.](anti-malware-protection-faq-eop.md)

Per domande e risposte sulla protezione anti-spoofing, vedere Domande frequenti sulla protezione [anti-spoofing.](anti-spoofing-protection-faq.md)

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>Per impostazione predefinita, cosa accade a un messaggio identificato come posta indesiderata?

**Per i messaggi in ingresso:** La maggior parte della posta indesiderata viene eliminata tramite il filtro connessioni, che si basa sull'indirizzo IP del server di posta elettronica di origine. I criteri di protezione da posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) esaminano e classificano i messaggi come posta indesiderata, in blocco o phishing. Per impostazione predefinita, i messaggi classificati come posta indesiderata o in blocco vengono recapitati nella cartella Posta indesiderata del destinatario, mentre i messaggi classificati come phishing vengono messi in quarantena. È possibile modificare il criterio di protezione da posta indesiderata predefinito (applicabile a tutti i destinatari) oppure creare criteri di protezione da posta indesiderata personalizzati con impostazioni più rigorose per gruppi specifici di utenti (ad esempio, è possibile mettere in quarantena la posta indesiderata inviata ai dirigenti). Per ulteriori informazioni, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md) e [Recommended anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

> [!IMPORTANT]
> Nelle distribuzioni ibride in cui EOP protegge le cassette postali locali, è necessario configurare due regole del flusso di posta di Exchange (note anche come regole di trasporto) nell'organizzazione exchange locale per rilevare le intestazioni del filtro posta indesiderata di EOP aggiunte ai messaggi. Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **Per i messaggi in uscita:** Il messaggio viene instradato attraverso il [pool](high-risk-delivery-pool-for-outbound-messages.md) di recapito ad alto rischio o viene restituito al mittente in un rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito). Per ulteriori informazioni sulla protezione da posta indesiderata in uscita, vedere [Outbound spam controls](outbound-spam-controls.md).

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>Che cos'è una variante di posta indesiderata zero-day e come viene gestita dal servizio?

Una variante di posta indesiderata zero-day è una variante sconosciuta di posta indesiderata di prima generazione che non è mai stata acquisita o analizzata, quindi i filtri di protezione da posta indesiderata non hanno ancora informazioni disponibili per rilevarla. Dopo che un campione di posta indesiderata zero-day è stato acquisito e analizzato dai nostri analisti della posta indesiderata, se soddisfa i criteri di classificazione della posta indesiderata, i filtri di protezione da posta indesiderata vengono aggiornati per rilevarlo e non viene più considerato "zero-day".

**Nota:** Se si riceve un messaggio che potrebbe essere una variante di posta indesiderata zero-day, per aiutarci a migliorare il servizio, inviare il messaggio a Microsoft utilizzando uno dei metodi descritti in Segnalare messaggi e file a [Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>È necessario configurare il servizio per fornire la protezione dalla posta indesiderata?

Dopo l'iscrizione al servizio e l'aggiunta del dominio, il filtro posta indesiderata viene abilitato automaticamente. Per impostazione predefinita, il filtro della posta indesiderata è ottimizzato per proteggere l'utente senza bisogno di alcuna configurazione aggiuntiva (a parte l'eccezione notata in precedenza per i clienti autonomi EOP autonomi in ambienti ibridi). Gli amministratori possono modificare le impostazioni predefinite del filtro posta indesiderata per soddisfare al meglio le esigenze dell'organizzazione. Per una maggiore granularità, è inoltre possibile creare criteri di protezione da posta indesiderata e criteri di protezione da posta indesiderata in uscita che vengono applicati a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sui criteri predefiniti, ma è possibile modificarne il livello di priorità (l'ordine di esecuzione).

Per ulteriori informazioni, vedere i seguenti argomenti:

[Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365](recommended-settings-for-eop-and-office365.md)

[Configurare il filtro connessioni in EOP](configure-the-connection-filter-policy.md)

[Configurare criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)

[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>Se viene modificato un criterio di posta indesiderata, quando tempo trascorre prima che modifiche vengano applicate?

Fino a 1 ora.

## <a name="is-bulk-email-filtering-automatically-enabled"></a>Il filtro della posta elettronica in blocco è abilitato per impostazione predefinita?

Sì. Per ulteriori informazioni sulla posta elettronica in blocco, vedere Qual è la differenza tra posta indesiderata [e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md).

## <a name="does-the-service-provide-url-filtering"></a>Il servizio offre filtro URL?

Sì, il servizio dispone di un filtro URL che controlla la presenza di URL all'interno dei messaggi. Se vengono rilevati contenuti indesiderati o sospetti associati all'URL, il messaggio viene contrassegnato come posta indesiderata.

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>In che modo gli utenti che utilizzano il servizio inviano falsi negativi (posta indesiderata) e falsi positivi (posta non indesiderata) a Microsoft?

I messaggi di posta indesiderata e non possono essere inviati a Microsoft per l'analisi in diversi modi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="can-i-get-spam-reports"></a>È possibile ricevere rapporti sulla posta indesiderata?

Sì, ad esempio, è possibile ottenere un report di rilevamento della posta indesiderata nell'interfaccia di amministrazione di Microsoft 365. Questo report mostra il volume di posta indesiderata come conteggio dei messaggi univoci. Per ulteriori informazioni sulla segnalazione, vedere i seguenti collegamenti:

Clienti di Exchange Online: [monitoraggio, creazione di report e traccia dei messaggi in Exchange Online](/exchange/monitoring/monitoring)

Clienti EOP autonomi: [segnalazione e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>Qualcuno mi ha inviato un messaggio e non riesco a trovarlo. Sospetto che sia stato identificato come posta indesiderata. Esiste uno strumento per scoprirlo?

Sì, lo strumento di traccia dei messaggi consente di seguire i messaggi di posta elettronica nel loro percorso attraverso il servizio e scoprire cosa è accaduto. Per ulteriori informazioni su come utilizzare lo strumento di traccia dei messaggi per scoprire perché un messaggio è stato contrassegnato come posta indesiderata, vedere Un messaggio è stato [contrassegnato come posta indesiderata?](/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>Se gli utenti inviano posta indesiderata in uscita, la limitazione del servizio (limite di frequenza) sarà la posta elettronica?

Se più della metà della posta inviata da un utente tramite il servizio entro un determinato intervallo di tempo (ad esempio, per ora), viene determinata come posta indesiderata da EOP, all'utente verrà impedito di inviare messaggi. Nella maggior parte dei casi, se un messaggio in uscita viene determinato come posta indesiderata, viene instradato attraverso il pool di recapito ad alto rischio, riducendo così la probabilità che il normale pool IP in uscita venga aggiunto a un elenco di indirizzi non attendibili.

È possibile inviare una notifica a un indirizzo di posta elettronica specificato quando a un mittente viene impedito l'invio di posta indesiderata. Per ulteriori informazioni su questa impostazione, vedere [Configure the outbound spam policy.](configure-the-outbound-spam-policy.md)

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>È possibile utilizzare un provider antimalware e di protezione dalla posta indesiderata di terze parti insieme a Exchange Online?

Sì. Anche se ti consigliamo di indirizzare il record MX a Microsoft, ci rendiamo conto che esistono motivi aziendali legittimi per instradare la posta elettronica a un luogo diverso da Microsoft.

- **In ingresso:** modificare i record MX in modo che puntino al provider di terze parti e quindi reindirizzare i messaggi a EOP per un'ulteriore elaborazione. Per ulteriori informazioni, vedere [Enhanced Filtering for connectors in Exchange Online.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **Outbound:** configurare il routing smart host da Microsoft 365 al provider di terze parti di destinazione.

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Microsoft dispone di documentazione su come è possibile proteggersi da tentativi di phishing?

Sì. Per altre informazioni, vedi [Proteggere la privacy su Internet](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>I messaggi di posta indesiderata e malware vengono analizzati da coloro a cui sono indirizzati o vengono trasferiti a entità giudiziarie?

Il servizio si concentra sul rilevamento e sulla rimozione di posta indesiderata e malware, tuttavia occasionalmente ci occupiamo di analizzare campagne di attacco o posta indesiderata specialmente pericolose e dannose e di perseguire gli autori. A tale scopo è possibile la collaborazione con le unità legali e di crimini digitali per eliminare botnet spammer, impedire agli spammer di utilizzare il servizio (se lo usano per inviare posta in uscita) e passare le informazioni agli enti giudiziari per il procedimento penale.

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>Quali sono le procedure ottimali per la posta i uscita che garantiscono che la posta venga recapitata?

Le linee guida presentate di seguito rappresentano le procedure ottimali per l'invio di messaggi di posta elettronica.

- **Il dominio di posta elettronica di origine deve essere risolto in DNS.**

  Ad esempio, se il mittente è user@fabrikam, il dominio fabrikam viene risolto nell'indirizzo IP 192.0.43.10.

  Se un dominio di invio non ha record A e record MX in DNS, il servizio instrada il messaggio attraverso il pool di recapito ad altro rischio a prescindere che il contenuto del messaggio sia posta indesiderata o meno. Per ulteriori informazioni sul pool di recapito ad alto rischio, vedere Pool di recapito ad alto rischio [per i messaggi in uscita.](high-risk-delivery-pool-for-outbound-messages.md)

- **Il server di posta elettronica in uscita deve avere una voce DNS inversa (PTR).**

  Ad esempio, se l'indirizzo IP di origine della posta elettronica è 192.0.43.10, la voce DNS inversa sarà `43-10.any.icann.org` .'

- **I comandi HELO/EHLO e MAIL FROM devono essere coerenti e presenti in formato nome di dominio anziché di indirizzo IP.**

  Il comando HELO/EHLO deve essere configurato in modo da corrispondere al DNS inverso dell'indirizzo IP di invio in modo che il dominio resti lo stesso tra le diverse parti delle intestazioni dei messaggi.

- **Accertarsi che in DNS siano impostati i record SPF corretti.**

  I record SPF consentono di verificare che la posta inviata da un dominio giunga veramente da tale dominio e non sia soggetta a spoofing. Per ulteriori informazioni sui record SPF, vedere i seguenti collegamenti:

  [Configurazione di SPF per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#how-can-i-validate-spf-records-for-my-domain)

- **Per accedere alla posta elettronica con DKIM, utilizzare la canonicalizzazione semplice.**

  Se un mittente desidera accedere ai propri messaggi utilizzando DKIM (Domain Keys Identified Mail) e desidera inviare la posta in uscita tramite il servizio, deve accedere utilizzando l'algoritmo di canonicalizzazione semplice delle intestazioni. L'accesso con una canonicalizzazione più complessa potrebbe invalidare la firma quando passa attraverso il servizio.

- **I proprietari dei domini devono disporre di informazioni accurate nel database WHOIS.**

  Tale database identifica i proprietari del dominio e indica come contattarli immettendo la società padre stabile, il punto di contatto e i server dei nomi.

- **Peri programmi di posta in blocco, il nome Da: deve riflettere il mittente del messaggio mentre la riga dell'oggetto del messaggio deve essere un breve riepilogo delle informazioni contenute nel messaggio.**

  Il corpo del messaggio deve contenere una chiara indicazione dell'offerta, servizio o prodotto. Ad esempio, se un mittente sta inviando posta in blocco per la società Contoso, i campi Da e Oggetto devono essere simili ai seguenti:

  > Da: marketing@contoso.com <br> Oggetto: Nuovo catalogo per Natale!

  Di seguito viene riportato un esempio di cosa non fare, perché non è descrittivo:

  > Da: utente@hotmail.com <br> Oggetto: Cataloghi

- **Se si invia posta in blocco a molti destinatari e il messaggio è in formato newsletter, nella parte finale del messaggio occorre fornire un modo per annullare la sottoscrizione.**

  L'opzione che consente di annullare la sottoscrizione sarà simile alla seguente:

  > Questo messaggio è stato inviato a esempio@contoso.com da mittente@fabrikam.com. Aggiornare il profilo/indirizzo di posta elettronica | Rimozione immediata con **SafeUnsubscribe** &trade; | Informativa sulla privacy

- **Se si invia posta elettronica in blocco, l'acquisizione dell'elenco deve essere eseguita utilizzando double opt-in, uno standard del settore.**

  Double opt-in è una procedura che richiede che l'utente esegua due azioni per registrarsi per la posta di marketing.

  1. La prima azione consiste nel selezionare una casella di controllo precedentemente non selezionata per indicare che desidera ricevere ulteriori offerte o messaggi di posta elettronica.

  2. La seconda azione viene eseguita quando il commerciante invia un messaggi di posta elettronica di conferma all'indirizzo di posta elettronica fornito dall'utente chiedendogli di fare clic sul un collegamento sensibile al tempo per completare la conferma.

  L'utilizzo della doppia conferma contribuisce alla buona reputazione per i mittenti di posta elettronica in blocco.

- **I mittenti in blocco devono creare contenuto trasparente per cui possono essere ritenuti responsabili:**

  1. Le espressioni che richiedono ai destinatari di aggiungere il mittente alla rubrica devono indicare che tale azione non è una garanzia di recapito.

  2. Quando si costruiscono i reindirizzamenti nel corpo del messaggio, utilizzare uno stile di collegamento coerente.

  3. Non inviare immagini o allegati di grandi dimensioni o messaggi composti unicamente da un'immagine.

  4. Nell'uso di pixel di verifica (bug Web o beacon), indicarne chiaramente la presenza delle impostazioni P3P o della privacy pubblica.

- **Formattare i messaggi di mancato recapito in uscita.**

  Quando si generano messaggi di notifica sullo stato del recapito (noti anche come rapporti di mancato recapito, rapporti di mancato recapito o messaggi di mancato recapito), i mittenti devono seguire il formato di un mancato recapito come specificato in [RFC 3464.](https://www.ietf.org/rfc/rfc3464.txt)

- **Rimuovere gli indirizzi di posta elettronica di restituzione per utenti inesistenti.**

  Se si riceve un rapporto di mancato recapito per un indirizzo di posta elettronica non più in uso, rimuovere l'alias di posta elettronica inesistente dall'elenco. Gli indirizzi di posta elettronica possono cambiare nel tempo.

- **Utilizzare il programma SNDS (Smart Network Data Services) di Hotmail.**

  Hotmail utilizza un programma chiamato Smart Network Data Services che consente ai mittenti di verificare i reclami inviati dagli utenti finali. SNDS è il portale principale per la risoluzione dei problemi di recapito a Hotmail.