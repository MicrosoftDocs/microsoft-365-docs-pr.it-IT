---
title: Creare elenchi di mittenti bloccati
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
description: Gli amministratori possono ottenere informazioni sulle opzioni disponibili e preferite per bloccare i messaggi in ingresso in Exchange Online Protection (EOP).
ms.openlocfilehash: 2862fa4a33a31eac9c61f94aa929133d2dc69fc8
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545901"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Creare elenchi di mittenti bloccati in EOP

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP offre molteplici modalità di blocco della posta elettronica da mittenti indesiderati. Queste opzioni includono i mittenti bloccati di Outlook, gli elenchi di mittenti bloccati o gli elenchi di dominio bloccati nei criteri di protezione da posta indesiderata, le regole del flusso di posta di Exchange (note anche come regole di trasporto) e l'elenco indirizzi IP bloccati (filtro connessioni). In modo collettivo, è possibile considerare queste opzioni come _elenchi di mittenti bloccati_.

Il metodo migliore per bloccare i mittenti varia in base all'ambito di impatto. Per un singolo utente, la soluzione corretta potrebbe essere mittenti bloccati di Outlook. Per molti utenti, una delle altre opzioni sarebbe più appropriata. Le opzioni seguenti sono classificate in base all'ambito e all'ampiezza dell'impatto. L'elenco passa da stretto a vasto, ma *leggere le specifiche per i* suggerimenti completi.

1. Mittenti bloccati di Outlook (l'elenco dei mittenti bloccati archiviati in ogni cassetta postale)

2. Elenchi di mittenti bloccati o bloccati (criteri di protezione dalla posta indesiderata)

3. Regole del flusso di posta

4. L'elenco indirizzi IP bloccati (filtro connessioni)

> [!NOTE]
> Anche se è possibile utilizzare le impostazioni di blocco a livello dell'organizzazione per risolvere i falsi negativi (posta indesiderata), è necessario inviare tali messaggi a Microsoft per l'analisi. La gestione dei falsi negativi tramite gli elenchi bloccati aumenta significativamente il sovraccarico amministrativo. Se si utilizzano gli elenchi bloccati per deflettere la posta indesiderata, è necessario mantenere l'argomento [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md) in pronto.

Al contrario, sono inoltre disponibili diverse opzioni per consentire sempre la posta elettronica da origini specifiche utilizzando _elenchi di mittenti attendibili_. Per altre informazioni, vedere [Creare elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Nozioni fondamentali sui messaggi di posta elettronica

Un messaggio di posta elettronica SMTP standard è costituito da una *busta del messaggio* e dal contenuto del messaggio. La busta del messaggio contiene le informazioni necessarie per la trasmissione e il recapito del messaggio tra i server SMTP. Il contenuto del messaggio include i campi di intestazione del messaggio (denominati collettivamente *intestazione del messaggio*) e il corpo del messaggio. La busta del messaggio è descritta in RFC 5321 e l'intestazione del messaggio è descritta in RFC 5322. I destinatari non vedono mai la busta reale del messaggio perché viene generata dal processo di trasmissione del messaggio e non è in realtà parte del messaggio.

- L'indirizzo `5321.MailFrom` (noto anche come indirizzo di **posta elettronica** , mittente P1 o mittente busta) è l'indirizzo di posta elettronica utilizzato per la trasmissione SMTP del messaggio. Questo indirizzo di posta elettronica viene in genere registrato nel campo di intestazione **Return-Path** nell'intestazione del messaggio (sebbene sia possibile che il mittente designi un indirizzo di posta elettronica diverso per il **percorso restituito** ). Se il messaggio non può essere recapitato, è il destinatario del rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo).

- L'indirizzo di posta `5322.From` elettronica del mittente viene visualizzato nei client di posta elettronica (noto anche come indirizzo **da** o mittente P2) e è l'indirizzo di posta elettronica nel campo dell'intestazione **from** .

Spesso, gli `5321.MailFrom` `5322.From` indirizzi e sono uguali (comunicazione da persona a persona). Tuttavia, quando viene inviato un messaggio di posta elettronica per conto di qualcun altro, gli indirizzi possono essere diversi.

Gli elenchi di mittenti bloccati e gli elenchi di domini bloccati nei criteri di protezione da posta indesiderata in EOP ispezionano sia gli `5321.MailFrom` indirizzi che quelli `5322.From` . I mittenti bloccati di Outlook usano solo l' `5322.From` indirizzo.

## <a name="use-outlook-blocked-senders"></a>Utilizzo di mittenti bloccati di Outlook

Quando solo un numero limitato di utenti ha ricevuto messaggi di posta elettronica indesiderati, gli utenti o gli amministratori possono aggiungere gli indirizzi di posta elettronica del mittente all'elenco dei mittenti bloccati nella cassetta postale. Per istruzioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

Quando i messaggi vengono bloccati correttamente a causa dell'elenco dei mittenti bloccati di un utente, il campo di intestazione **X-Forefront-antispam-report** conterrà il valore `SFV:BLK` .

> [!NOTE]
> Se i messaggi indesiderati sono newsletter provenienti da un'origine attendibile e riconoscibile, l'annullamento della sottoscrizione al messaggio di posta elettronica è un'altra opzione per impedire all'utente di ricevere i messaggi.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Utilizzo degli elenchi di mittenti bloccati o degli elenchi di dominio bloccati

Quando più utenti sono coinvolti, l'ambito è più ampio, quindi l'opzione migliore successiva è l'elenco dei mittenti bloccati o degli elenchi di dominio bloccati nei criteri di protezione da posta indesiderata. I messaggi provenienti da mittenti negli elenchi sono contrassegnati come **posta indesiderata**e l'azione configurata per il verdetto del filtro di **posta indesiderata** viene eseguita sul messaggio. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).

Il limite massimo per questi elenchi è approssimativamente pari a 1000 voci.

## <a name="use-mail-flow-rules"></a>Utilizzare le regole del flusso di posta

Se è necessario bloccare i messaggi inviati a utenti specifici o all'intera organizzazione, è possibile utilizzare le regole del flusso di posta. Le regole del flusso di posta sono più flessibili rispetto al blocco degli elenchi di mittenti o degli elenchi di dominio del mittente bloccati perché possono anche cercare parole chiave o altre proprietà nei messaggi indesiderati.

Indipendentemente dalle condizioni o dalle eccezioni utilizzate per identificare i messaggi, è necessario configurare l'azione per impostare il livello di probabilità di posta indesiderata (SCL) del messaggio su 9, che contrassegna il messaggio come **posta indesiderata**. Per ulteriori informazioni, vedere [utilizzo delle regole del flusso di posta per impostare il livello SCL nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> È facile creare regole *eccessivamente* aggressive, quindi è importante identificare solo i messaggi che si desidera bloccare utilizzando criteri molto specifici. Assicurarsi inoltre di abilitare il controllo della regola e verificare i risultati della regola per garantire che tutto funzioni come previsto.

## <a name="use-the-ip-block-list"></a>Utilizzare l'elenco indirizzi IP bloccati

Quando non è possibile utilizzare una delle altre opzioni per bloccare un *mittente, è* necessario utilizzare l'elenco indirizzi IP bloccati nel criterio di filtro delle connessioni. Per ulteriori informazioni, vedere [Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md). È importante mantenere il numero minimo di indirizzi IP bloccati, quindi *non* è consigliabile bloccare interi intervalli di indirizzi.

È consigliabile *evitare di* aggiungere intervalli di indirizzi IP che appartengono ai servizi consumer (ad esempio, Outlook.com) o alle infrastrutture condivise e verificare che l'elenco degli indirizzi IP bloccati venga esaminato come parte di una manutenzione regolare.
