---
title: Come Sender Policy Framework (SPF) impedisce lo spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su Microsoft 365 il record TXT SPF (Sender Policy Framework) in DNS per garantire che i sistemi di posta elettronica di destinazione ritieni attendibili i messaggi inviati dal dominio personalizzato.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 972f283f6138bafcebd877a19f0bfc429e0eed03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205385"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Uso di Sender Policy Framework (SPF) in Microsoft 365 per impedire lo spoofing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 **Riepilogo:** In questo articolo viene descritto Microsoft 365 il record TXT SPF (Sender Policy Framework) in DNS per garantire che i sistemi di posta elettronica di destinazione ritienino attendibili i messaggi inviati dal dominio personalizzato. Questo vale per la posta in uscita inviata da Microsoft 365. I messaggi inviati da Microsoft 365 a un destinatario entro Microsoft 365 passeranno sempre SPF.

Un record TXT SPF è un record DNS che consente di impedire lo spoofing e il phishing verificando il nome del dominio da cui vengono inviati i messaggi di posta elettronica. SPF consente di convalidare l'origine dei messaggi di posta elettronica verificando l'indirizzo IP del mittente in base al proprietario del dominio del mittente.

> [!NOTE]
> I tipi di record SPF sono stati deprecati dall'Internet Engineering Task Force (IETF) nel 2014. Assicurarsi quindi di utilizzare i record TXT in DNS per pubblicare le informazioni SPF. Il resto di questo articolo utilizza il termine record TXT SPF per maggiore chiarezza.

Gli amministratori di dominio pubblicano le informazioni SPF in record TXT in DNS. Le informazioni SPF identificano i server di posta elettronica in uscita autorizzati. I sistemi di posta elettronica di destinazione verificano che l'origine dei messaggi sia un server di posta elettronica in uscita autorizzato. Se si ha già familiarità con SPF o si dispone di una distribuzione semplice ed è sufficiente sapere cosa includere nel record TXT SPF in DNS per Microsoft 365, è possibile passare a Configurare SPF in Microsoft 365 per impedire [lo spoofing.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Se non si dispone di una distribuzione completamente ospitata in Microsoft 365 o si desiderano ulteriori informazioni sul funzionamento di SPF o su come risolvere i problemi relativi a SPF per Microsoft 365, continuare a leggere.

> [!NOTE]
> In precedenza, era necessario aggiungere un record SPF o TXT diverso al dominio personalizzato se si utilizzava anche SharePoint Online. Ciò non è più necessario. Questa modifica dovrebbe ridurre il rischio che i messaggi di notifica di SharePoint Online finiscano nella cartella Posta indesiderata. Non è necessario apportare modifiche immediatamente, ma se viene visualizzato l'errore "troppe ricerche", modificare il record TXT SPF come descritto in Set up SPF in Microsoft 365 per impedire [lo spoofing.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Funzionamento di SPF per impedire lo spoofing e il phishing in Microsoft 365
<a name="HowSPFWorks"> </a>

SPF determina se un mittente è autorizzato a inviare per conto di un dominio. Se il mittente non è autorizzato a farlo, ovvero se la posta elettronica non supera il controllo SPF nel server di ricezione, i criteri contro la posta indesiderata configurati su tale server determinano cosa fare con il messaggio.

Ogni record TXT SPF è costituito da tre parti: la dichiarazione che si tratta di un record TXT SPF, gli indirizzi IP autorizzati all'invio della posta dal dominio e i domini esterni in grado di inviare per conto del dominio, e una regola di imposizione. È necessario disporre di tutti e tre gli elementi per avere un record TXT SPF valido. In questo articolo viene descritto come creare il record TXT SPF e vengono fornite le procedure consigliate per l'utilizzo dei servizi in Microsoft 365. Vengono inoltre forniti i collegamenti alle istruzioni sull'uso del registrar per pubblicare il record in DNS.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>Nozioni principali su SFP: Indirizzi IP autorizzati all'invio dal dominio personalizzato
<a name="SPFBasicsIPaddresses"> </a>

Ecco la sintassi di base di una regola SPF:

v=spf1 \<IP\>\<enforcement rule\>

Si supponga, ad esempio, che sia presente la seguente regola SPF per contoso.com:

v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

In questo esempio la regola SPF indica al server di posta elettronica ricevente di accettare solo messaggi provenienti da questi indirizzi IP per il dominio contoso.com:

- Indirizzo IP #1

- Indirizzo IP #2

- Indirizzo IP #3

Questa regola SPF indica al server di posta elettronica ricevente che se un messaggio proviene da contoso.com, ma non da uno di questi tre indirizzi IP, il server di ricezione deve applicare la regola di imposizione al messaggio. La regola di imposizione è in genere una di queste opzioni:

- **Errore bloccante.** Contrassegnare il messaggio con "Errore bloccante" nella busta del messaggio e quindi seguire il criterio contro la posta indesiderata configurato del server di ricezione per questo tipo di messaggio.

- **Errore non bloccante.** Contrassegnare il messaggio con "Errore non bloccante" nella busta del messaggio. In genere, i server di posta elettronica sono configurati per recapitare questi messaggi comunque. La maggior parte degli utenti finali non visualizza questo contrassegno.

- **Neutro.** Non eseguire nessuna operazione, ovvero non contrassegnare la busta del messaggio. In genere è il criterio riservato a motivi di test ed è utilizzato raramente.

Negli esempi seguenti viene illustrato il funzionamento di SPF in diverse situazioni. In questi esempi, contoso.com è il mittente e woodgrovebank.com è il destinatario.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Esempio 1: Autenticazione di un messaggio di posta elettronica inviato direttamente dal mittente al destinatario
<a name="spfExample1"> </a>

SPF è ideale quando il percorso dal mittente al destinatario è diretto, ad esempio:

![Diagramma che mostra in che modo SPF autentica la posta elettronica inviata direttamente da un server all'altro.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Quando woodgrovebank.com riceve il messaggio, se l'indirizzo IP #1 è nel record TXT SPF per contoso.com, il messaggio passa il controllo SPF e viene autenticato.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Esempio 2: Indirizzo del mittente falsificato non supera il controllo SPF
<a name="spfExample2"> </a>

Si supponga che un truffatore trovi un modo per effettuare lo spoofing di contoso.com:

![Diagramma che mostra in che modo SPF autentica la posta elettronica inviata da un server falsificato.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Poiché l'indirizzo IP #12 non è nel record TXT SPF di contoso.com, il messaggio non supera il controllo SPF e il destinatario può scegliere di contrassegnarlo come posta indesiderata.

### <a name="example-3-spf-and-forwarded-messages"></a>Esempio 3: SPF e messaggi inoltrati
<a name="spfExample3"> </a>

Uno svantaggio di SPF consiste nel fatto che non funziona quando un messaggio di posta elettronica è stato inoltrato. Ad esempio, si supponga che l'utente in woodgrovebank.com abbia configurato una regola di inoltro per inviare tutta la posta elettronica a un account di outlook.com:

![Diagramma che mostra come SPF non sia in grado di autenticare la posta elettronica che viene inoltrata.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

Il messaggio all'inizio supera il controllo SPF in woodgrovebank.com, ma poi non passa quello in outlook.com perché l'IP #25 non è nel record TXT SPF di contoso.com. Outlook.com potrebbe quindi contrassegnare il messaggio come posta indesiderata. Per risolvere il problema, utilizzare SPF insieme ad altri metodi di autenticazione di posta elettronica quali DKIM e DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>Nozioni principali su SFP: Inclusione di domini di terze parti in grado di inviare posta elettronica per conto del proprio dominio
<a name="SPFBasicsIncludes"> </a>

Oltre agli indirizzi IP, è possibile configurare il record TXT SPF anche in modo che includa domini come mittenti. Questi vengono aggiunti al record TXT SPF come istruzioni "#include". Ad esempio, contoso.com potrebbe includere tutti gli indirizzi IP dei server di posta da contoso.net e contoso.org, anch'essi di sua proprietà. A tale scopo, contoso.com pubblica un record TXT SPF simile al seguente:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Quando il server di ricezione visualizza questo record in DNS, esegue anche una ricerca DNS sul record TXT SPF per contoso.net e quindi per contoso.org. Se viene trovata un'istruzione include aggiuntiva all'interno dei record per contoso.net o contoso.org, seguirà anche quelle. Per evitare attacchi Denial of Service, il numero massimo di ricerche DNS per un singolo messaggio di posta elettronica è 10. Ogni istruzione #include rappresenta una ricerca DNS aggiuntiva. Se un messaggio supera il limite di 10, il messaggio non supera il controllo SPF. Una volta raggiunto questo limite, a seconda del modo in cui è configurato il server di ricezione, il mittente potrebbe ricevere un messaggio che indica che il messaggio ha generato "troppe ricerche" o che il "numero massimo di hop per il messaggio è stato superato" (cosa che può verificarsi quando le ricerche si esattino e superano il timeout DNS). Per suggerimenti su come evitare questo problema, vedere [Risoluzione dei problemi: procedure consigliate per SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Requisiti per il record TXT SPF e il Microsoft 365
<a name="SPFReqsinO365"> </a>

Se si configura la posta durante la configurazione di Microsoft 365, è già stato creato un record TXT SPF che identifica i server di messaggistica Microsoft come fonte legittima di posta per il dominio. Questo record probabilmente sarà simile al seguente:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Se si è un cliente completamente ospitato, cio? non si dispone di server di posta locali che inviano posta in uscita, questo è l'unico record TXT SPF che è necessario pubblicare per Office 365.

Se si dispone di una distribuzione ibrida, ovvero alcune cassette postali locali e altre ospitate in Microsoft 365, oppure se si è un cliente autonomo di Exchange Online Protection (EOP), ovvero l'organizzazione utilizza EOP per proteggere le cassette postali locali, è consigliabile aggiungere l'indirizzo IP in uscita per ogni server di posta perimetrale locale al record TXT SPF in DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Creare il record TXT SPF per Microsoft 365
<a name="FormYourSPF"> </a>

Utilizzare le informazioni relative alla sintassi fornite in questo articolo per formare il record TXT SPF per il dominio personalizzato. Anche se sono disponibili altre opzioni di sintassi non menzionate qui, queste sono le opzioni più comunemente utilizzate. Dopo aver creato il record, è necessario aggiornare il record nel registrar del dominio.

Per informazioni sui domini da includere per la Microsoft 365, vedere Record DNS esterni [necessari per SPF.](../../enterprise/external-domain-name-system-records.md) Utilizzare le [istruzioni dettagliate ](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) per aggiornare i record (TXT) SPF per il registrar.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>Sintassi del record TXT SPF per Microsoft 365
<a name="SPFSyntaxO365"> </a>

Un record TXT SPF tipico per Microsoft 365 ha la sintassi seguente:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Ad esempio:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

dove:

- **v=spf1** è obbligatorio. Ciò definisce il record TXT come record TXT SPF.

- **ip4** indica che si utilizzano indirizzi IP in versione 4. **ip6** indica che si utilizzano indirizzi IP in versione 6. Se sono in uso indirizzi IP IPv6, sostituire **ip4** con **ip6** negli esempi forniti in questo articolo. È inoltre possibile specificare intervalli di indirizzi IP utilizzando la notazione CIDR, ad esempio **ip4:192.168.0.1/26**.

- _IP address_ è l'indirizzo IP da aggiungere al record TXT SPF. In genere, questo è l'indirizzo IP del server di posta in uscita per l'organizzazione. È possibile elencare più server di posta in uscita. Per ulteriori informazioni, vedere [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).

- _domain name_ è il dominio da aggiungere come mittente legittimo. Per un elenco dei nomi di dominio da includere per Microsoft 365, vedere [Record DNS esterni necessari per SPF.](../../enterprise/external-domain-name-system-records.md)

- La regola di imposizione in genere è una delle seguenti:

  - -all

    Indica un errore bloccante. Se si conoscono tutti gli indirizzi IP autorizzati per il dominio, elencarli nel record TXT SPF e utilizzare il qualificatore -all (errore bloccante). Inoltre, se si usa solo SPF, ovvero se non si utilizza DMARC o DKIM, è necessario usare il qualificatore -all. È consigliabile usare sempre questo qualificatore.

  - ~all

    Indica un errore non bloccante. Se non si è certi di avere l'elenco completo degli indirizzi IP, utilizzare il qualificatore ~all (errore non bloccante). Inoltre, se si utilizza DMARC con p=quarantine o p=reject, è possibile usare ~all. In caso contrario, utilizzare -all.

  - ?all

    Indica un elemento neutro. Si usa durante il test di SPF. Non è consigliabile usare questo qualificatore nella distribuzione in tempo reale.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Esempio: record TXT SPF da utilizzare quando tutta la posta viene inviata da Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Se tutta la posta viene inviata da Microsoft 365, usa questa opzione nel record TXT SPF:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Esempio: record TXT SPF per uno scenario ibrido con un'Exchange Server locale Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

In un ambiente ibrido, se l'indirizzo IP del server Exchange locale è 192.168.0.1, per impostare la regola di imposizione SPF sull'errore bloccante, formare il record TXT SPF come segue:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Esempio: record TXT SPF per più server di posta locali in uscita e Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Se l'utente ha più server di posta in uscita, includere l'indirizzo IP per ciascun server di posta nel record TXT SPF e separare ogni indirizzo IP con uno spazio seguito da "ip4:". Ad esempio:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Passaggi successivi: Configurare SPF per Microsoft 365
<a name="SPFNextSteps"> </a>

Dopo aver formulato il record TXT SPF, seguire i passaggi descritti in [Set up SPF in Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) per impedire lo spoofing per aggiungerlo al dominio.

SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da questi problemi, dopo aver configurato SPF, è necessario configurare anche DKIM e DMARC per Microsoft 365. Per iniziare, vedere [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md). Successivamente, vedere [Utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Risoluzione dei problemi: procedure consigliate per SPF in Microsoft 365
<a name="SPFTroubleshoot"> </a>

È possibile creare un solo record TXT SPF per il dominio personalizzato. La creazione di più record causa un round robin e SPF ha esito negativo. Per evitare questo problema, è possibile creare record distinti per ogni sottodominio. Ad esempio, creare un record per contoso.com e un altro per bulkmail.contoso.com.

Se un messaggio di posta elettronica causa più di 10 ricerche DNS prima di essere recapitato, il server di posta di ricezione risponderà con un errore permanente, noto anche come  _permerror_, e il messaggio non supererà il controllo SPF. Il server di ricezione può rispondere anche con un rapporto di mancato recapito (NDR) che contiene un errore simile al seguente:

- Il messaggio ha superato il numero massimo di hop.

- Il messaggio ha richiesto un numero eccessivo di ricerche.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Evitare l'errore "troppe ricerche" quando si utilizzano domini di terze parti con Microsoft 365
<a name="SPFTroubleshoot"> </a>

Alcuni record TXT SPF per i domini di terze parti passano direttamente al server di ricezione per eseguire un numero elevato di ricerche DNS. Ad esempio, al momento, Salesforce.com contiene 5 istruzioni #include nel relativo record:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Per evitare l'errore, è possibile implementare un criterio in cui chiunque invia posta elettronica in blocco, ad esempio, deve utilizzare un sottodominio specifico per questo scopo. È quindi possibile definire un record TXT SPF diverso per il sottodominio che include la posta elettronica in blocco.

 In alcuni casi, come nell'esempio di salesforce.com, è necessario utilizzare il dominio nel record TXT SPF, ma altre volte la terza parte deve avere già creato un sottodominio da utilizzare per questo scopo. Ad esempio, exacttarget.com ha creato un sottodominio che è necessario usare per il record TXT SPF:

```text
cust-spf.exacttarget.com
```

Quando si includono domini di terze parti nel record TXT SPF, è necessario confermare con la terza parte quale dominio o sottodominio usare per evitare di superare il limite di 10 ricerche.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Come visualizzare il record TXT SPF corrente e determinare il numero di ricerche necessarie
<a name="SPFTroubleshoot"> </a>

È possibile utilizzare nslookup per visualizzare i record DNS, incluso il record TXT SPF. In alternativa, sono disponibili numerosi strumenti online gratuiti che consentono di visualizzare i contenuti del record TXT SPF. Osservando il record TXT SPF e seguendo la catena di istruzioni #include e reindirizzamenti, è possibile determinare il numero di ricerche DNS necessarie per il record. Alcuni strumenti online consentono anche di contare e visualizzare tali ricerche. Tenere traccia di questo numero consente di evitare che i messaggi inviati dall'organizzazione attivino un errore permanente, denominato permerror, dal server di ricezione.

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="SPFTroubleshoot"> </a>

Sono necessarie informazioni sull'aggiunta del record TXT SPF? Leggere l'articolo [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) per informazioni dettagliate sull'utilizzo di Sender Policy Framework con il dominio personalizzato in Microsoft 365. [Le intestazioni dei messaggi di posta indesiderata](anti-spam-message-headers.md) includono la sintassi e i campi di intestazione utilizzati Microsoft 365 per i controlli SPF.
