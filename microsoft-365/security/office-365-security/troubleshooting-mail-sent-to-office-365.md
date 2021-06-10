---
title: Risoluzione dei problemi della posta elettronica inviati a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni per la risoluzione dei problemi relativi all'invio di posta elettronica alle Microsoft 365 & nelle procedure consigliate per l'invio di posta in blocco Microsoft 365 clienti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c3017b0e7d0c583c9038f695f9f47010ff92c18a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206153"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Risoluzione dei problemi della posta elettronica inviati a Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)

In questo articolo vengono fornite informazioni sulla risoluzione dei problemi per i mittenti che riscontrano problemi durante il tentativo di inviare messaggi di posta elettronica alle cartelle Posta in arrivo in Microsoft 365 e procedure consigliate per l'invio di posta in blocco ai clienti.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>Si sta gestendo la reputazione di invio dell'IP e del dominio?

Le tecnologie di filtro EOP sono progettate per fornire protezione da posta indesiderata per Microsoft 365 e altri prodotti Microsoft come Exchange Server. Ci avvaliamo anche di SPF, DKIM e DMARC; Tecnologie di autenticazione della posta elettronica che consentono di risolvere il problema di spoofing e phishing verificando che il dominio che invia il messaggio di posta elettronica sia autorizzato a farlo. Il filtro EOP è influenzato da una serie di fattori correlati all'IP di invio, al dominio, all'autenticazione, alla precisione degli elenchi, alle percentuali di reclamo, al contenuto e altro ancora. Di questi, uno dei fattori principali per la reputazione di un mittente e la loro capacità di recapitare la posta elettronica è la frequenza di reclami per la posta indesiderata.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>Si sta inviando posta elettronica da nuovi indirizzi IP?

Gli indirizzi IP non utilizzati in precedenza per inviare posta elettronica in genere non hanno alcuna reputazione creata nei nostri sistemi. Di conseguenza, è più probabile che i messaggi di posta elettronica provenienti da nuovi indirizzi IP si verifichino problemi di recapito. Una volta che l'IP ha creato una reputazione per non inviare posta indesiderata, EOP in genere consentirà una migliore esperienza di recapito della posta elettronica.

I nuovi IP aggiunti per i domini autenticati con record SPF esistenti in genere hanno il vantaggio di ereditare parte della reputazione di invio del dominio. Se il dominio ha una buona reputazione di invio, i nuovi IP potrebbero avere tempi di avvio più rapidi. Un nuovo IP può aspettarsi di essere completamente dilagato entro un paio di settimane o prima a seconda del volume, dell'accuratezza dell'elenco e delle percentuali di reclami per la posta indesiderata.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Verificare che il DNS sia configurato correttamente

Per istruzioni su come creare e gestire i record DNS, incluso il record MX necessario per il routing della posta, è necessario contattare il provider di hosting DNS.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Assicurarsi di non annunciarsi come IP non instradabile

È possibile che non si accettino messaggi di posta elettronica provenienti da mittenti che non riescono a eseguire una ricerca DNS inversa. In alcuni casi, i mittenti legittimi si annunciano in modo errato come IP non instradabile su Internet quando tentano di aprire una connessione a EOP. Gli indirizzi IP riservati per la rete privata (non instradabile) includono:

- 192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>È stato ricevuto un rapporto di mancato recapito (NDR) quando si invia un messaggio di posta elettronica a un utente in Office 365

Alcuni problemi di recapito sono il risultato del blocco dell'indirizzo IP del mittente da parte di Microsoft o perché l'account utente viene identificato come mittente escluso a causa di precedenti attività di posta indesiderata. Se si ritiene di aver ricevuto il rapporto di mancato recapito per errore, seguire innanzitutto le istruzioni nel messaggio del rapporto di mancato recapito per risolvere il problema.

Per ulteriori informazioni sull'errore ricevuto, vedere l'elenco dei codici di errore in [Rapporti di mancato](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)recapito di posta elettronica in Exchange Online .

 Ad esempio, se si riceve il rapporto di mancato recapito seguente, indica che l'indirizzo IP di invio è stato bloccato da Microsoft:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Per richiedere la rimozione da questo elenco, è possibile utilizzare il portale di rimozione per rimuovere se [stessi dall'elenco dei mittenti bloccati.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Il messaggio di posta elettronica è stato atterrato nella cartella Posta indesiderata del destinatario

Se un messaggio è stato erroneamente identificato come posta indesiderata da EOP, è possibile collaborare con il destinatario per inviare questo messaggio falso positivo al team di analisi della posta indesiderata di Microsoft, che valuterà e analerà il messaggio. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>Il traffico proveniente dall'indirizzo IP viene limitato da EOP

Se si riceve un rapporto di mancato recapito da EOP che indica che l'indirizzo IP viene limitato da EOP, ad esempio:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

Il rapporto di mancato recapito è stato ricevuto perché sono state rilevate attività sospette dall'indirizzo IP e sono state temporaneamente limitate durante un'ulteriore valutazione. Se il sospetto viene chiarito attraverso la valutazione, questa restrizione verrà revocata a breve.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>I can't receive email from senders in Microsoft 365

 Per ricevere messaggi dai nostri utenti, assicurati che la rete consenta le connessioni dagli indirizzi IP utilizzati da EOP nei nostri datacenter. Per ulteriori informazioni, vedere [Exchange Online Protection IP](../../enterprise/urls-and-ip-address-ranges.md).

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Procedure consigliate per l'invio di posta elettronica in blocco Microsoft 365 utenti

Se spesso si eseguano campagne di posta elettronica in blocco Microsoft 365 utenti e si desidera garantire che i messaggi di posta elettronica arrivino in modo sicuro e corretto, seguire i suggerimenti in questa sezione.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Verificare che il nome del mittente rifletta chi sta inviando il messaggio

L'oggetto Subject deve essere un breve riepilogo dell'oggetto del messaggio e il corpo del messaggio deve indicare chiaramente e in modo sintetico l'offerta, il servizio o il prodotto. Ad esempio:

Impostazione corretta:

> Da: marketing@shoppershandbag.com <br> Oggetto: Catalogo aggiornato per la stagione di Natale.

Impostazione non corretta:

> Da: someone@outlook.com <br> Oggetto: Cataloghi

Più è facile per gli utenti sapere chi si è e cosa si sta facendo, minore sarà la difficoltà a eseguire il recapito tramite la maggior parte dei filtri di posta indesiderata.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Includi sempre un'opzione di annullamento della sottoscrizione nei messaggi di posta elettronica della campagna

I messaggi di posta elettronica di marketing, in particolare le newsletter, devono sempre includere un modo per annullare la sottoscrizione di messaggi di posta elettronica futuri. Ad esempio:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Alcuni mittenti includono questa opzione richiedendo ai destinatari di inviare un messaggio di posta elettronica a un determinato alias con "Annulla sottoscrizione" nell'oggetto. Non è preferibile all'esempio con un solo clic precedente. Se si sceglie di richiedere ai destinatari di inviare un messaggio di posta elettronica, assicurarsi che, quando fanno clic sul collegamento, tutti i campi obbligatori siano precompilato.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Utilizzare l'opzione di consenso esplicito doppio per la registrazione della posta elettronica o della newsletter di marketing

Questa procedura consigliata per il settore è consigliata se l'azienda richiede o incoraggia gli utenti a registrare le informazioni di contatto per accedere al prodotto o ai servizi. Alcune società fanno in modo che gli utenti si immatrino automaticamente per la commercializzazione di messaggi di posta elettronica o newsletter durante il processo di registrazione, ma questa è considerata una pratica di marketing discutibile nel mondo del filtro della posta elettronica.

Durante il processo di registrazione, se la casella di controllo "Sì, inviami la newsletter" o "Sì, inviami offerte speciali" è selezionata per impostazione predefinita, gli utenti che non prestano particolare attenzione potrebbero iscriversi involontariamente per inviare messaggi di posta elettronica di marketing o newsletter che non desiderano ricevere.

 Consigliamo invece l'opzione di consenso esplicito doppio, il che significa che la casella di controllo per i messaggi di posta elettronica o le newsletter di marketing è deselezionata per impostazione predefinita. Inoltre, dopo l'invio del modulo di registrazione, all'utente viene inviato un messaggio di posta elettronica di verifica con un URL che consente di confermare la decisione di ricevere messaggi di posta elettronica di marketing.

 In questo modo si garantisce che solo gli utenti che desiderano ricevere messaggi di posta elettronica di marketing siano registrati per i messaggi di posta elettronica, cancellando successivamente la società mittente di eventuali pratiche di marketing della posta elettronica discutibile.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Verificare che il contenuto dei messaggi di posta elettronica sia trasparente e tracciabile

Tanto importante quanto il modo in cui vengono inviati i messaggi di posta elettronica è il contenuto che contengono. Quando si crea contenuto di posta elettronica, utilizzare le procedure consigliate seguenti per assicurarsi che i messaggi di posta elettronica non siano contrassegnati dai servizi di filtro della posta elettronica:

- Quando il messaggio di posta elettronica richiede ai destinatari di aggiungere il mittente alla rubrica, deve essere chiaramente detto che tale azione non è una garanzia di recapito.

- I reindirizzamenti inclusi nel corpo del messaggio devono essere simili e coerenti e non multipli e vari. Un reindirizzamento in questo contesto è qualsiasi elemento che punta al messaggio, ad esempio collegamenti e documenti. Se hai molti collegamenti pubblicitari o Annulla sottoscrizione o Aggiorna i collegamenti profilo, devono puntare tutti allo stesso dominio. Ad esempio:

  Corretto (tutti i domini sono uguali):

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Non corretto (tutti i domini sono diversi):

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Evitare contenuti con immagini e allegati di grandi dimensioni o messaggi composti esclusivamente da un'immagine.

- Le impostazioni P3P o privacy pubblica devono chiaramente segnalare la presenza di pixel di tracciamento (bug Web o beacon).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Rimuovere alias di posta elettronica non corretti dai database

Qualsiasi alias di posta elettronica nel database che crea un rimbalzo non è necessario e mette i messaggi di posta elettronica in uscita a rischio di un ulteriore controllo da parte dei servizi di filtro della posta elettronica. Verificare che il database di posta elettronica sia aggiornato.