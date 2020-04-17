---
title: Creare elenchi di mittenti attendibili in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Gli amministratori possono ottenere informazioni sulle opzioni disponibili in Office 365 e EOP che consentono ai messaggi in ingresso di ignorare il filtro posta indesiderata.
ms.openlocfilehash: 4b50a4b63377c0f3e7b12592c512449f1a3adc12
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528630"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Creare elenchi di mittenti attendibili in Office 365

Se si è un cliente di Office 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, EOP offre diversi modi per garantire che gli utenti ricevano messaggi di posta elettronica da mittenti attendibili. Queste opzioni includono le regole del flusso di posta di Exchange (note anche come regole di trasporto), i mittenti attendibili di Outlook, l'elenco indirizzi IP consentiti (filtro connessioni) e gli elenchi di mittenti consentiti o gli elenchi di domini consentiti nei criteri di protezione dalla posta In modo collettivo, è possibile considerare queste opzioni come _elenchi di mittenti attendibili_.

Gli elenchi di mittenti attendibili disponibili sono descritti nell'elenco seguente, in ordine da quelli consigliati come meno consigliati:

1. Regole del flusso di posta

2. Mittenti attendibili di Outlook

3. Elenco indirizzi IP consentiti (filtro connessioni)

4. Elenchi mittenti consentiti o elenchi di domini consentiti (criteri di protezione dalla posta indesiderata

Le regole del flusso di posta consentono la massima flessibilità per garantire che vengano consentiti solo i messaggi giusti. Il mittente consentito e gli elenchi di domini consentiti nei criteri di protezione da posta indesiderata non sono sicuri come l'elenco indirizzi IP consentiti, perché il dominio di posta elettronica del mittente è facilmente falsificato Tuttavia, l'elenco indirizzi IP consentiti presenta anche un rischio, perché la posta elettronica proveniente da _qualsiasi_ dominio inviato da tale indirizzo IP ignorerà il filtro di posta indesiderata.

> [!IMPORTANT]
> <ul><li>Fare attenzione a monitorare attentamente *tutte le* eccezioni che è necessario filtrare per la posta indesiderata utilizzando elenchi di mittenti attendibili.</li><li>Anche se è possibile utilizzare gli elenchi di mittenti attendibili per ottenere falsi positivi (un buon messaggio di posta elettronica contrassegnato come posta indesiderata), è consigliabile considerare l'utilizzo di elenchi di mittenti attendibili come soluzione temporanea che dovrebbe essere evitata se possibile. Non è consigliabile gestire falsi positivi utilizzando elenchi di mittenti attendibili, perché le eccezioni ai filtri per la posta indesiderata possono aprire l'organizzazione allo spoofing e ad altri attacchi. Se si insiste sull'utilizzo degli elenchi di mittenti attendibili per la gestione dei falsi positivi, è necessario essere vigili e mantenere l'argomento [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md) in pronto.</li><li>Per consentire a un dominio di inviare messaggi di posta elettronica non autenticati (bypass anti-spoofing) ma non di ignorare i controlli di protezione dalla posta indesiderata e antimalware, è possibile aggiungerlo all' [elenco dei mittenti attendibili di AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)</li><li>EOP e Outlook ispezionano diverse proprietà dei messaggi per determinare il mittente del messaggio. Per ulteriori informazioni, vedere la sezione [considerazioni sulla posta elettronica in blocco](#considerations-for-bulk-email) più avanti in questo argomento.</li></ul>

Al contrario, sono inoltre disponibili diverse opzioni per bloccare la posta elettronica da origini specifiche tramite _elenchi di mittenti bloccati_. Per altre informazioni, vedere [Creare elenchi di mittenti bloccati in Office 365](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>Consigliato Utilizzare le regole del flusso di posta

Le regole del flusso di posta in Exchange Online e in EOP autonomo utilizzano le condizioni e le eccezioni per identificare i messaggi e le azioni che devono essere eseguite per tali messaggi. Per ulteriori informazioni, vedere [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

Nell'esempio seguente si presuppone che sia necessario inviare posta elettronica da contoso.com per ignorare il filtro posta indesiderata. A tale scopo, configurare le impostazioni seguenti:

1. **Condizione**: **il dominio del mittente** \> **è** \> contoso.com.

2. Configurare una delle seguenti impostazioni:

   - **Condizione della regola del flusso di posta**: **l'intestazione** \> di un messaggio include una o più **delle seguenti parole** \> **nome intestazione**: `Authentication-Results` \> **valore intestazione**: `dmarc=pass` oppure `dmarc=bestguesspass`.

     Questa condizione verifica lo stato di autenticazione del mittente del dominio di posta elettronica di invio per assicurarsi che il dominio di invio non venga falsificato. Per ulteriori informazioni sull'autenticazione della posta elettronica, vedere [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md).

   - **Elenco indirizzi IP consentiti**: specificare l'indirizzo IP o l'intervallo di indirizzo di origine nel criterio di filtro delle connessioni.
  
     Utilizzare questa impostazione se il dominio di invio non dispone dell'autenticazione. Essere il più restrittivo possibile quando si tratta di indirizzi IP di origine nell'elenco IP consentiti. È consigliabile un intervallo di indirizzi IP pari o inferiore a 24 (meno è migliore). Non utilizzare intervalli di indirizzi IP che appartengono a servizi di consumo (ad esempio, outlook.com) o a infrastrutture condivise.

   > [!IMPORTANT]
   > <ul><li>Non configurare mai la configurazione delle regole del flusso di posta con *solo* il dominio del mittente come condizione per ignorare il filtro posta indesiderata. In questo modo, si aumenterà *significativamente* la probabilità che i pirati informatici possano falsificare il dominio di invio (o rappresentare l'indirizzo di posta elettronica completo), ignorare tutti i filtri di posta indesiderata e ignorare i controlli di autenticazione del mittente in modo che il messaggio arrivi nella posta in arrivo del destinatario</li><li>Non utilizzare domini proprietari (noti anche come domini accettati) o domini più diffusi (ad esempio, microsoft.com) come condizioni nelle regole del flusso di posta. In questo modo viene considerato un rischio elevato perché crea opportunità per gli aggressori di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati.</li><li>Se si consente a un indirizzo IP che si trova dietro un gateway NAT (Network Address Translation), è necessario conoscere i server coinvolti nel pool NAT per conoscere l'ambito dell'elenco indirizzi IP consentiti. Gli indirizzi IP e i partecipanti NAT possono cambiare. È necessario controllare periodicamente le voci dell'elenco indirizzi IP consentiti nell'ambito delle procedure di manutenzione standard.</li></ul>

3. **Condizioni facoltative**:

   - **Il mittente** \> **è interno/esterno** \> all' **esterno dell'organizzazione**: questa condizione è implicita, ma è possibile utilizzarla per tenere conto dei server di posta elettronica locali che potrebbero non essere configurati correttamente.

   - **L'** \> oggetto o il corpo dell'oggetto o del corpo **include una delle** \> \<parole chiave\>seguenti: se è possibile limitare ulteriormente i messaggi tramite parole chiave o frasi nella riga dell'oggetto o nel corpo del messaggio, è possibile utilizzare tali parole come condizione.

4. **Azione**: configurare entrambe le azioni nella regola:

   a. **Modifica le proprietà** \> del messaggio impostare il **filtro di posta**indesiderata bypass **del livello** \> di probabilità di posta indesiderata.

   b. **L'intestazione di un messaggio** \> **include una di queste parole** \> **nome intestazione**: \<CustomHeaderName\> **valore intestazione**: \<CustomHeaderValue\>.

      Ad esempio, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Se nella regola sono presenti più domini, è possibile personalizzare il testo dell'intestazione in base alle proprie esigenze.

      Quando un messaggio ignora il filtro posta indesiderata a causa di una regola del `SFV:SKN` flusso di posta, il valore viene contrassegnato nell'intestazione **X-Forefront-antispam-report** . Se il messaggio è proveniente da un'origine presente nell'elenco indirizzi IP consentiti `IPV:CAL` , viene aggiunto anche il valore. Questi valori possono essere utili per la risoluzione dei problemi.

![Impostazioni delle regole del flusso di posta in EAC per ignorare il filtro posta indesiderata.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Utilizzo di mittenti attendibili di Outlook

Invece di un'impostazione organizzativa, gli utenti o gli amministratori possono aggiungere gli indirizzi di posta elettronica del mittente all'elenco Mittenti attendibili nella cassetta postale. Per istruzioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange online in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

Quando i messaggi ignorano il filtro posta indesiderata a causa dell'elenco dei mittenti attendibili di un utente, il campo di intestazione **X-Forefront-antispam-report** conterrà il valore `SFV:SFE`, che indica che la posta indesiderata, la falsificazione e il filtro phishing sono stati ignorati.

## <a name="use-the-ip-allow-list"></a>Utilizzare l'elenco indirizzi IP consentiti

Se non è possibile utilizzare le regole del flusso di posta come descritto in precedenza, è consigliabile aggiungere il server o i server di posta elettronica di origine all'elenco indirizzi IP consentiti nel criterio di filtro delle connessioni. Per ulteriori informazioni, vedere [Configure Connection Filtering in Office 365](configure-the-connection-filter-policy.md).

**Note**:

- È importante mantenere al minimo il numero di indirizzi IP consentiti, in modo da evitare di usare interi intervalli di indirizzi IP quando possibile.

- Non utilizzare intervalli di indirizzi IP che appartengono a servizi di consumo (ad esempio, outlook.com) o a infrastrutture condivise.

- Esaminare periodicamente le voci nell'elenco indirizzi IP consentiti e rimuovere le voci che non sono più necessarie.

> [!CAUTION]
> Senza ulteriori verifiche, come le regole del flusso di posta, la posta elettronica proveniente da origini nell'elenco indirizzi IP consentiti ignora il filtro posta indesiderata e l'autenticazione mittente (SPF, DKIM, DMARC). Questo crea un rischio elevato che gli aggressori recapitano messaggi di posta elettronica alla posta in arrivo altrimenti filtrati.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Utilizzare elenchi di mittenti consentiti o elenchi di domini consentiti

L'opzione meno desiderata consiste nell'utilizzare l'elenco dei mittenti consentiti o l'elenco dei domini consentiti nei criteri di protezione da posta indesiderata È consigliabile evitare questa opzione *se possibile* perché i mittenti ignorano tutti i messaggi di posta indesiderata, la protezione da spoofing e phishing e l'autenticazione del mittente (SPF, DKIM, DMARC). Questo metodo viene utilizzato in modo ottimale solo per i test temporanei. La procedura dettagliata è disponibile in [configurare i criteri di protezione dalla posta indesiderata nell'argomento Office 365](configure-your-spam-filter-policies.md) .

Il limite massimo per questi elenchi è approssimativamente pari a 1000 voci; anche se, sarà possibile immettere 30 voci nel portale. Per aggiungere più di 30 voci, è necessario utilizzare PowerShell.

> [!CAUTION]
> <ul><li>Questo metodo crea un rischio elevato che gli aggressori recapitano correttamente la posta elettronica alla posta in arrivo che altrimenti verrebbe filtrata.</li><li>Non utilizzare domini proprietari (noti anche come domini accettati) o domini più diffusi (ad esempio, microsoft.com) negli elenchi di domini consentiti.</li></ul>

## <a name="considerations-for-bulk-email"></a>Considerazioni per i messaggi di posta elettronica in blocco

Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio. La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP. Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio. La busta del messaggio è descritta in RFC 5321 e l'intestazione del messaggio è descritta in RFC 5322. I destinatari non vedono mai la busta reale del messaggio perché viene generata dal processo di trasmissione del messaggio e non è in realtà parte del messaggio.

- L' `5321.MailFrom` indirizzo (noto anche come indirizzo di **posta elettronica** , mittente P1 o mittente busta) è l'indirizzo di posta elettronica utilizzato per la trasmissione SMTP del messaggio. Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (sebbene sia possibile che il mittente designi un indirizzo di posta elettronica diverso per il **percorso restituito** ). Se il messaggio non può essere recapitato, è il destinatario del rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo).

- L' `5322.From` indirizzo di posta elettronica del mittente viene visualizzato nei client di posta elettronica (noto anche come indirizzo **da** o mittente P2) e è l'indirizzo di posta elettronica nel campo dell'intestazione **from** .

Spesso, gli `5321.MailFrom` indirizzi `5322.From` e sono uguali (comunicazione da persona a persona). Tuttavia, quando viene inviato un messaggio di posta elettronica per conto di qualcun altro, gli indirizzi sono spesso diversi. Questo accade solitamente più spesso per i messaggi di posta elettronica in blocco.

Si supponga, ad esempio, che la compagnia aerea Blu laggiù abbia assunto Margie ' s Travel per inviare la propria pubblicità tramite posta elettronica. Il messaggio che viene visualizzato nella posta in arrivo ha le seguenti proprietà:

- L' `5321.MailFrom` indirizzo è blueyonder.Airlines@margiestravel.com.

- L' `5322.From` indirizzo è blueyonder@news.blueyonderairlines.com, che è quello che vedrai in Outlook.

Elenchi di mittenti attendibili e elenchi di domini attendibili nei criteri di protezione da posta `5321.MailFrom` indesiderata in EOP ispezionare sia gli indirizzi che `5322.From` quelli. I mittenti attendibili di Outlook utilizzano `5322.From` solo l'indirizzo.

Per evitare che il messaggio venga filtrato, è possibile eseguire le operazioni seguenti:

- Aggiungere blueyonder@news.blueyonderairlines.com (l' `5322.From` indirizzo) come mittente sicuro di Outlook.

- [Utilizzare una regola del flusso di posta](#recommended-use-mail-flow-rules) con una condizione che consente di cercare i messaggi `5322.From` provenienti da blueyonder@news.blueyonderairlines.com ( `5321.MailFrom`l'indirizzo, blueyonder.Airlines@margiestravel.com () o entrambi.

Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in Office 365](create-safe-sender-lists-in-office-365.md).
