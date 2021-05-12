---
title: Creare elenchi di mittenti bloccati
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
description: Gli amministratori possono conoscere le opzioni disponibili e preferite per bloccare i messaggi in ingresso in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fa2a5e0c71f14838dc8446431f5ea02a535fb787
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331455"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Creare elenchi di mittenti bloccati in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP offre diversi modi per bloccare la posta elettronica da mittenti indesiderati. Queste opzioni includono i mittenti bloccati di Outlook, gli elenchi dei mittenti bloccati o gli elenchi di domini bloccati nei criteri di protezione dalla posta indesiderata, le regole del flusso di posta di Exchange (note anche come regole di trasporto) e l'elenco indirizzi IP bloccati (filtro connessioni). Collettivamente, è possibile pensare a queste opzioni come _elenchi di mittenti bloccati._

Il metodo migliore per bloccare i mittenti varia in base all'ambito di impatto. Per un singolo utente, la soluzione giusta potrebbe essere Outlook Blocked Senders. Per molti utenti, una delle altre opzioni sarebbe più appropriata. Le opzioni seguenti sono classificate in base all'ambito di impatto e all'ampiezza. L'elenco va da stretto a ampio, ma *leggere le specifiche per* suggerimenti completi.

1. Mittenti bloccati di Outlook (l'elenco Mittenti bloccati archiviato in ogni cassetta postale)

2. Elenchi di mittenti bloccati o elenchi di domini bloccati (criteri di protezione da posta indesiderata)

3. Regole del flusso di posta

4. Elenco indirizzi IP non attendibili (filtro connessioni)

> [!NOTE]
> Anche se è possibile utilizzare le impostazioni di blocco a livello di organizzazione per risolvere i falsi negativi (posta indesiderata senza risposta), è consigliabile inviare tali messaggi a Microsoft per l'analisi. La gestione dei falsi negativi tramite elenchi di blocco aumenta in modo significativo il sovraccarico amministrativo. Se si utilizzano elenchi di blocco per deviare la posta indesiderata senza risposta, è necessario tenere pronto l'argomento Segnalare messaggi e file a [Microsoft.](report-junk-email-messages-to-microsoft.md)

Al contrario, sono disponibili anche diverse opzioni per consentire sempre la posta elettronica da origini specifiche utilizzando _elenchi di mittenti attendibili._ Per altre informazioni, vedere [Creare elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Nozioni di base sul messaggio di posta elettronica

Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio. La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP. Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio. La busta del messaggio è descritta in RFC 5321 e l'intestazione del messaggio è descritta in RFC 5322. I destinatari non vedono mai la busta effettiva del messaggio perché viene generata dal processo di trasmissione del messaggio e non fa effettivamente parte del messaggio.

- L'indirizzo (noto anche come indirizzo `5321.MailFrom` **MAIL FROM,** mittente P1 o mittente della busta) è l'indirizzo di posta elettronica utilizzato nella trasmissione SMTP del messaggio. Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (anche se è possibile che il mittente designi un indirizzo di posta elettronica **Return-Path** diverso). Se il messaggio non può essere recapitato, è il destinatario del rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito).

- L'indirizzo (noto anche come indirizzo mittente o mittente P2) è l'indirizzo di posta elettronica nel campo di intestazione Da ed è l'indirizzo di posta elettronica del mittente visualizzato nei client di posta `5322.From` elettronica.  

Spesso, gli indirizzi e sono uguali (comunicazione da `5321.MailFrom` persona a `5322.From` persona). Tuttavia, quando la posta elettronica viene inviata per conto di un altro utente, gli indirizzi possono essere diversi.

Gli elenchi di mittenti bloccati e di domini bloccati nei criteri di protezione da posta indesiderata in EOP controllano sia `5321.MailFrom` gli indirizzi che gli `5322.From` indirizzi. L'indirizzo viene utilizzato solo dai mittenti bloccati di `5322.From` Outlook.

## <a name="use-outlook-blocked-senders"></a>Utilizzare i mittenti bloccati di Outlook

Quando solo un numero limitato di utenti ha ricevuto posta elettronica indesiderata, gli utenti o gli amministratori possono aggiungere gli indirizzi di posta elettronica del mittente all'elenco Mittenti bloccati nella cassetta postale. Per istruzioni, vedere [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).

Quando i messaggi vengono bloccati a causa dell'elenco Mittenti bloccati di un utente, il campo di intestazione **X-Forefront-Antispam-Report** conterrà il valore `SFV:BLK` .

> [!NOTE]
> Se i messaggi indesiderati sono newsletter provenienti da un'origine affidabile e riconoscibile, l'annullamento della sottoscrizione dal messaggio di posta elettronica è un'altra opzione per impedire all'utente di ricevere i messaggi.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Utilizzare elenchi di mittenti bloccati o elenchi di domini bloccati

Quando più utenti sono interessati, l'ambito è più ampio, quindi l'opzione migliore successiva è elenchi di mittenti bloccati o elenchi di domini bloccati nei criteri di protezione da posta indesiderata. I messaggi provenienti dai mittenti degli elenchi sono contrassegnati come posta  indesiderata con alta probabilità e l'azione configurata per il verdetto Filtro posta indesiderata ad alta probabilità viene eseguita sul messaggio. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).

Il limite massimo per questi elenchi è di circa 1000 voci.

## <a name="use-mail-flow-rules"></a>Usare le regole del flusso di posta

Se è necessario bloccare i messaggi inviati a utenti specifici o all'intera organizzazione, è possibile utilizzare le regole del flusso di posta. Le regole del flusso di posta sono più flessibili rispetto agli elenchi dei mittenti bloccati o ai domini dei mittenti bloccati perché possono anche cercare parole chiave o altre proprietà nei messaggi indesiderati.

Indipendentemente dalle condizioni o dalle eccezioni utilizzate per identificare i messaggi, è necessario configurare l'azione per impostare il livello di probabilità di posta indesiderata (SCL) del messaggio su 9, che contrassegna il messaggio come posta indesiderata con alta **probabilità.** Per ulteriori informazioni, vedere [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> È facile creare regole esenti da aggressività, quindi è importante identificare solo i messaggi che si desidera bloccare utilizzando criteri molto specifici.  Inoltre, assicurarsi di abilitare il controllo sulla regola e testare i risultati della regola per assicurarsi che tutto funzioni come previsto.

## <a name="use-the-ip-block-list"></a>Utilizzare l'elenco indirizzi IP bloccati

Quando non è possibile utilizzare una delle altre opzioni  per bloccare un mittente, è consigliabile utilizzare l'elenco indirizzi IP bloccati nel criterio filtro connessioni. Per ulteriori informazioni, vedere [Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md). È importante mantenere il numero minimo di indirizzi IP bloccati, pertanto non è consigliabile bloccare interi intervalli *di* indirizzi IP.

È  consigliabile evitare in particolare di aggiungere intervalli di indirizzi IP appartenenti a servizi consumer (ad esempio, outlook.com) o infrastrutture condivise e verificare inoltre di esaminare l'elenco degli indirizzi IP bloccati nell'ambito di una manutenzione regolare.
