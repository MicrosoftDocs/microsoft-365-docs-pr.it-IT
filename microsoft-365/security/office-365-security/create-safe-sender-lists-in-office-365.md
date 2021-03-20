---
title: Creare elenchi di mittenti attendibili
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono conoscere le opzioni disponibili e preferite per consentire i messaggi in ingresso in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 88c70eea4952eda9315687ae90e2f6834f1edaf8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903821"
---
# <a name="create-safe-sender-lists-in-eop"></a>Creare elenchi di mittenti attendibili in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Se si è un cliente di Microsoft 365 con cassette postali in Exchange Online o un cliente autonomo di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP offre diversi modi per garantire che gli utenti ricevano la posta elettronica da mittenti attendibili. Queste opzioni includono le regole del flusso di posta di Exchange (note anche come regole di trasporto), i mittenti attendibili di Outlook, l'elenco indirizzi IP consentiti (filtro connessioni) e gli elenchi di mittenti consentiti o gli elenchi di domini consentiti nei criteri di protezione da posta indesiderata. Collettivamente, è possibile pensare a queste opzioni come _elenchi di mittenti attendibili._

Gli elenchi di mittenti attendibili disponibili sono descritti nell'elenco seguente nell'ordine dal più consigliato al meno consigliato:

1. Regole del flusso di posta
2. Mittenti attendibili di Outlook
3. Elenco indirizzi IP consentiti (filtro connessioni)
4. Elenchi di mittenti consentiti o elenchi di domini consentiti (criteri di protezione da posta indesiderata)

Le regole del flusso di posta consentono la massima flessibilità per garantire che siano consentiti solo i messaggi di destra. Gli elenchi di mittenti e domini consentiti nei criteri di protezione da posta indesiderata non sono sicuri come l'elenco indirizzi IP consentiti, perché il dominio di posta elettronica del mittente è facilmente contraffatto. Tuttavia, l'elenco indirizzi IP consentiti  presenta anche un rischio, perché la posta elettronica da qualsiasi dominio inviato da tale indirizzo IP ignora il filtro posta indesiderata.

> [!IMPORTANT]
>
> - Prestare attenzione a monitorare attentamente *eventuali* eccezioni apportate al filtro posta indesiderata utilizzando elenchi di mittenti attendibili.
>
> - Sebbene sia possibile utilizzare gli elenchi di mittenti attendibili per facilitare i falsi positivi (buona posta elettronica contrassegnata come non buona), è consigliabile considerare l'utilizzo degli elenchi di mittenti attendibili come soluzione temporanea da evitare, se possibile. Non è consigliabile gestire i falsi positivi utilizzando elenchi di mittenti attendibili, perché le eccezioni al filtro posta indesiderata possono aprire l'organizzazione a spoofing e altri attacchi. Se si insiste sull'utilizzo degli elenchi di mittenti attendibili per gestire i falsi positivi, è necessario essere attenti e mantenere pronto l'argomento Segnalare messaggi e file a [Microsoft.](report-junk-email-messages-to-microsoft.md)
>
> - Per consentire a un dominio di inviare messaggi di posta elettronica non autenticati (ignorare la protezione anti-spoofing) ma non di ignorare i controlli di protezione da posta indesiderata e antimalware, è possibile aggiungerlo all'elenco Mittenti attendibili [AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)
>
> - EOP e Outlook esaminano diverse proprietà dei messaggi per determinare il mittente del messaggio. Per ulteriori informazioni, vedere la sezione [Considerazioni per la posta elettronica](#considerations-for-bulk-email) in blocco più avanti in questo articolo.

Al contrario, sono disponibili diverse opzioni per bloccare la posta elettronica da origini specifiche utilizzando _elenchi di mittenti bloccati._ Per altre informazioni, vedere [Creare elenchi di mittenti bloccati in EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>(Scelta consigliata) Usare le regole del flusso di posta

Le regole del flusso di posta in Exchange Online e in EOP autonomo utilizzano condizioni ed eccezioni per identificare i messaggi e azioni per specificare le operazioni da eseguire per tali messaggi. Per ulteriori informazioni, vedere [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

L'esempio seguente presuppone che sia necessaria la posta elettronica contoso.com per ignorare il filtro posta indesiderata. A tale scopo, configurare le impostazioni seguenti:

1. **Condizione:** **il dominio del** \> **mittente è** \> contoso.com.

2. Configurare una delle impostazioni seguenti:

   - **Condizione della regola del flusso di posta**: **Un'intestazione** del messaggio include una delle seguenti parole \>  \> **Nome intestazione**: `Authentication-Results` \> **Valore intestazione**: o `dmarc=pass` `dmarc=bestguesspass` .

     Questa condizione controlla lo stato di autenticazione della posta elettronica del dominio di posta elettronica di invio per assicurarsi che il dominio di invio non venga contraffatto. Per ulteriori informazioni sull'autenticazione della posta elettronica, vedere [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC.](use-dmarc-to-validate-email.md)

   - **Elenco indirizzi IP consentiti:** specificare l'indirizzo IP o l'intervallo di indirizzi di origine nel criterio filtro connessioni.

     Utilizzare questa impostazione se il dominio di invio non utilizza l'autenticazione di posta elettronica. Essere il più restrittivo possibile per quanto riguarda gli indirizzi IP di origine nell'elenco indirizzi IP consentiti. È consigliabile un intervallo di indirizzi IP di /24 o inferiore (è meglio meno). Non utilizzare intervalli di indirizzi IP appartenenti a servizi consumer (ad esempio, outlook.com) o infrastrutture condivise.

   > [!IMPORTANT]
   >
   > - Non configurare mai le regole del flusso di posta *con solo* il dominio del mittente come condizione per ignorare il filtro posta indesiderata. In questo  modo si aumenta notevolmente la probabilità che gli utenti malintenzionati possano eseguire lo spoofing del dominio di invio (o rappresentare l'indirizzo di posta elettronica completo), ignorare tutti i filtri della posta indesiderata e ignorare i controlli di autenticazione del mittente in modo che il messaggio arrivi nella posta in arrivo del destinatario.
   >
   > - Non utilizzare domini di cui si è proprietari (noti anche come domini accettati) o domini popolari (ad esempio, microsoft.com) come condizioni nelle regole del flusso di posta. Questa operazione è considerata ad alto rischio perché consente agli utenti malintenzionati di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati.
   >
   > - Se si consente un indirizzo IP dietro un gateway NAT (Network Address Translation), è necessario conoscere i server coinvolti nel pool NAT per conoscere l'ambito dell'elenco indirizzi IP consentiti. Gli indirizzi IP e i partecipanti NAT possono cambiare. È necessario controllare periodicamente le voci dell'elenco indirizzi IP consentiti nell'ambito delle procedure di manutenzione standard.

3. **Condizioni facoltative**:

   - **Il mittente** \> **è interno/esterno** \> **All'esterno** dell'organizzazione: questa condizione è implicita, ma è consigliabile utilizzarla per l'account dei server di posta elettronica locali che potrebbero non essere configurati correttamente.

   - **Oggetto o corpo** \> **l'oggetto o il corpo include una di queste parole** \> : se è possibile limitare ulteriormente i messaggi tramite parole chiave o frasi nella riga dell'oggetto o nel corpo del messaggio, è possibile utilizzare tali parole \<keywords\> come condizione.

4. **Azione:** configurare entrambe le azioni nella regola:

   a. **Modificare le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata** \> **Ignorare il filtro posta indesiderata**.

   b. **Modificare le proprietà del messaggio** \> **set a message header**: **Imposta l'intestazione** \<CustomHeaderName\> **del messaggio sul valore** \<CustomHeaderValue\> .

      Ad esempio, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Se nella regola sono presenti più domini, è possibile personalizzare il testo dell'intestazione in base alle esigenze.

      Quando un messaggio ignora il filtro della posta indesiderata a causa di una regola del flusso di posta, il valore viene contrassegnato nell'intestazione `SFV:SKN` **X-Forefront-Antispam-Report.** Se il messaggio viene inviato da un'origine nell'elenco indirizzi IP consentiti, viene `IPV:CAL` aggiunto anche il valore. Questi valori possono essere utili per la risoluzione dei problemi.

![Impostazioni delle regole del flusso di posta nell'interfaccia di amministrazione di Exchange per ignorare il filtro posta indesiderata.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Utilizzare Mittenti attendibili di Outlook

> [!CAUTION]
> Questo metodo crea un rischio elevato per gli utenti malintenzionati di recapitare correttamente messaggi di posta elettronica nella Posta in arrivo che altrimenti verrebbero filtrati; Tuttavia, gli elenchi Mittenti attendibili o Domini attendibili dell'utente non impediscono il filtro di malware o messaggi di phishing ad alta probabilità.

Anziché un'impostazione dell'organizzazione, gli utenti o gli amministratori possono aggiungere gli indirizzi di posta elettronica dei mittenti all'elenco Mittenti attendibili nella cassetta postale. Per istruzioni, vedere [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md). Ciò non è consigliabile nella maggior parte delle situazioni, poiché i mittenti bypasseranno parti dello stack di filtro. Anche se si considera attendibile il mittente, il mittente può comunque essere compromesso e inviare contenuti dannosi. È meglio lasciare che i filtri esercitino le necessarie per controllare ogni messaggio e quindi segnalare il [falso positivo/negativo](report-junk-email-messages-to-microsoft.md) a Microsoft se i filtri non sono stati applicati. L'esclusione dello stack di filtro interferisce anche con [ZAP.](zero-hour-auto-purge.md)

Quando i messaggi ignorano il filtro posta indesiderata a causa dell'elenco Mittenti attendibili di un utente, il campo di intestazione **X-Forefront-Antispam-Report** conterrà il valore , che indica che il filtro per la posta indesiderata, lo spoofing e il phishing è stato `SFV:SFE` ignorato.

## <a name="use-the-ip-allow-list"></a>Utilizzare l'elenco indirizzi IP consentiti

Se non è possibile utilizzare le regole del flusso di posta come descritto in precedenza, l'opzione migliore successiva è aggiungere il server o i server di posta elettronica di origine all'elenco indirizzi IP consentiti nel criterio filtro connessioni. Per informazioni dettagliate, vedere [Configure connection filtering in EOP.](configure-the-connection-filter-policy.md)

**Note**:

- È importante mantenere il numero minimo di indirizzi IP consentiti, quindi evitare di utilizzare interi intervalli di indirizzi IP quando possibile.

- Non utilizzare intervalli di indirizzi IP appartenenti a servizi consumer (ad esempio, outlook.com) o infrastrutture condivise.

- Esaminare regolarmente le voci nell'elenco indirizzi IP consentiti e rimuovere le voci non più necessarie.

> [!CAUTION]
> Senza ulteriori verifiche come le regole del flusso di posta, i messaggi di posta elettronica provenienti da origini nell'elenco indirizzi IP consentiti ignorano il filtro posta indesiderata e i controlli di autenticazione del mittente (SPF, DKIM, DMARC). Ciò crea un rischio elevato di attacchi che recapitino correttamente messaggi di posta elettronica alla Posta in arrivo che altrimenti verrebbero filtrati; Tuttavia, l'elenco indirizzi IP consentiti non impedisce il filtro di malware o messaggi di phishing ad alta probabilità.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Utilizzare elenchi di mittenti consentiti o elenchi di domini consentiti

L'opzione meno desiderabile è utilizzare l'elenco dei mittenti consentiti o l'elenco di domini consentiti nei criteri di protezione da posta indesiderata. È consigliabile  evitare questa opzione, se possibile, perché i mittenti ignorano tutta la protezione da posta indesiderata, spoofing e phishing e l'autenticazione del mittente (SPF, DKIM, DMARC). È consigliabile usare questo metodo solo per test temporanei. I passaggi dettagliati sono disponibili [nell'argomento Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)

Il limite massimo per questi elenchi è di circa 1000 voci. tuttavia, sarà possibile immettere solo 30 voci nel portale. È necessario utilizzare PowerShell per aggiungere più di 30 voci.

> [!CAUTION]
>
> - Questo metodo crea un rischio elevato per gli utenti malintenzionati di recapitare correttamente messaggi di posta elettronica nella Posta in arrivo che altrimenti verrebbero filtrati; Tuttavia, i mittenti consentiti o gli elenchi di domini consentiti non impediscono il filtro di malware o messaggi di phishing ad alta probabilità.
>
> - Non utilizzare domini di cui si è proprietari (noti anche come domini accettati) o domini popolari (ad esempio, microsoft.com) negli elenchi di domini consentiti.

## <a name="considerations-for-bulk-email"></a>Considerazioni sulla posta elettronica in blocco

Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio. La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP. Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio. La busta del messaggio è descritta in RFC 5321 e l'intestazione del messaggio è descritta in RFC 5322. I destinatari non vedono mai la busta effettiva del messaggio perché viene generata dal processo di trasmissione del messaggio e non fa effettivamente parte del messaggio.

- L'indirizzo (noto anche come indirizzo `5321.MailFrom` **MAIL FROM,** mittente P1 o mittente della busta) è l'indirizzo di posta elettronica utilizzato nella trasmissione SMTP del messaggio. Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (anche se è possibile che il mittente designi un indirizzo di posta elettronica **Return-Path** diverso). Se il messaggio non può essere recapitato, è il destinatario del rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito).

- L'indirizzo (noto anche come indirizzo mittente o mittente P2) è l'indirizzo di posta elettronica nel campo di intestazione Da ed è l'indirizzo di posta elettronica del mittente visualizzato nei client di posta `5322.From` elettronica.  

Spesso, gli indirizzi e sono uguali (comunicazione da `5321.MailFrom` persona a `5322.From` persona). Tuttavia, quando la posta elettronica viene inviata per conto di un altro utente, gli indirizzi possono essere diversi. Questo accade più spesso per i messaggi di posta elettronica in blocco.

Si supponga, ad esempio, che Blue Yonder Airlines abbia assunto Margie's Travel per inviare la pubblicità tramite posta elettronica. Il messaggio ricevuto nella posta in arrivo ha le proprietà seguenti:

- `5321.MailFrom`L'indirizzo è blueyonder.airlines@margiestravel.com.

- L'indirizzo blueyonder@news.blueyonderairlines.com, che è quello `5322.From` che verrà visualizzato in Outlook.

Gli elenchi di mittenti attendibili e di domini attendibili nei criteri di protezione da posta indesiderata in EOP controllano solo gli indirizzi, in modo analogo ai mittenti attendibili di Outlook che `5322.From` utilizzano `5322.From` l'indirizzo.

Per impedire che questo messaggio venga filtrato, è possibile eseguire la procedura seguente:

- Aggiungere blueyonder@news.blueyonderairlines.com `5322.From` (l'indirizzo) come mittente sicuro di Outlook.

- [Utilizzare una regola del flusso di](#recommended-use-mail-flow-rules) posta con una condizione che consente di cercare i messaggi da blueyonder@news.blueyonderairlines.com (l'indirizzo, blueyonder.airlines@margiestravel.com `5322.From` (il ) o `5321.MailFrom` entrambi.

Per ulteriori informazioni, vedere [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).