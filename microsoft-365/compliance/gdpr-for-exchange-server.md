---
title: GDPR per Exchange Server
description: Informazioni su come gestire i requisiti del GDPR per Exchange Server locale, ad esempio la conservazione degli elementi eliminati e la raccolta automatica dei dati.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 7d2f482ad06f9ed44467795f310aecb2c44eea0d
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547322"
---
# <a name="gdpr-for-exchange-server"></a>GDPR per Exchange Server

Nell'ambito di protezione delle informazioni personali, si consiglia quanto segue:

-   Utilizzare [tag e criteri di conservazione](https://technet.microsoft.com/library/dd297955(v=exchg.160).aspx) in Exchange Server per implementare un criterio di ciclo di vita della posta elettronica.

-   Distribuire [Information Rights Management](https://technet.microsoft.com/library/dd638140(v=exchg.160).aspx) per limitare chi ha accesso alle informazioni archiviate in Exchange Server.

-   Attivare la [crittografia BitLocker](https://blogs.technet.microsoft.com/exchange/2015/10/20/enabling-bitlocker-on-exchange-servers/) nei server.

## <a name="identifying-in-scope-content"></a>Identificare il contenuto nell'ambito

Exchange usa due archivi principali per il contenuto generato dall'utente finale: cassette postali e cartelle pubbliche. Il contenuto archiviato nella cassetta postale di un utente è associato in modo univoco a quell'utente e costituisce il suo repository predefinito di Exchange. I dati archiviati nella cassetta postale di un utente includono il contenuto creato con i client Outlook, Outlook sul Web (in precedenza Outlook Web App), Exchange ActiveSync, Skype for Business e altri strumenti di terze parti che si connettono ai server di Exchange tramite POP, IMAP o Servizi Web Exchange. Esempi di questi elementi sono: messaggi, elementi del calendario (riunioni e appuntamenti), contatti, note e attività. Eliminando la cassetta postale di un utente viene eliminato il contenuto generato da o inviato direttamente all'utente nel contesto della sua cassetta postale. È possibile eliminare le cassette postali degli utenti tramite l'interfaccia di amministrazione di Exchange o il cmdlet [Remove-Mailbox](https://docs.microsoft.com/powershell/module/exchange/remove-mailbox) in Exchange Management Shell.\
Nota: Il parametro Permanent sul cmdlet Remove-Mailbox deve essere utilizzato con cautela poiché i dati non saranno recuperabili se si utilizza questa opzione.

Exchange fornisce anche le cassette postali condivise che consentono a uno o più utenti di inviare e ricevere il contenuto archiviato in una cassetta postale comune. La cassetta postale condivisa è un'entità univoca non associata a un singolo account, ma accessibile da più utenti che possono inviare, ricevere ed esaminare i contenuti di posta elettronica al suo interno. Le cassette postali condivise sono gestite tramite l'interfaccia di amministrazione di Exchange e tramite gli stessi cmdlet utilizzati per gestire le normali cassette postali degli utenti. Se è necessario rimuovere singoli messaggi da una cassetta postale, sono disponibili opzioni diverse a seconda della versione di Exchange. In Exchange Server 2010 e 2013, è possibile usare il cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) con il parametro DeleteContent per identificare e rimuovere i messaggi da una cassetta postale. In Exchange Server 2016 e versioni successive è necessario usare la funzionalità [New-ComplianceSearch](https://technet.microsoft.com/library/ff459253(v=exchg.160).aspx).

Le cartelle pubbliche sono un'implementazione dell'archiviazione condivisa che non è associata a un utente specifico. Gli utenti possono invece accedere alle cartelle pubbliche per generare contenuto. L'implementazione delle cartelle pubbliche effettiva varia a seconda della versione di Exchange (Exchange Server 2010 utilizza un'implementazione diversa rispetto a Exchange Server 2013 e versioni successive). Per gestire il contenuto delle cartelle pubbliche sono disponibili strumenti limitati. Gli strumenti client (ad esempio Outlook) sono il meccanismo principale per la gestione dei contenuti nelle cartelle pubbliche. Sono disponibili cmdlet per la gestione degli oggetti della cartella pubblica, ma non per la gestione dei singoli elementi contenuti nella cartella pubblica. Sarà probabilmente necessario uno script personalizzato che usa i Servizi Web Exchange o altri strumenti di terze parti per gestire gli elementi delle cartelle pubbliche.

Il requisito principale probabilmente gestirà il contenuto della cassetta postale dell'utente individuale. Questo requisito verrà risolto facilmente utilizzando gli strumenti di grafica o basati su cmdlet usati regolarmente per gestire le cassette postali. Se è necessario trattare il contenuto su più cassette postali o i tipi di risorse [eDiscovery](https://technet.microsoft.com/library/dd298021(v=exchg.160).aspx) è la soluzione migliore in Exchange per identificare il contenuto nell'ambito.

## <a name="deleted-item-retention"></a>Mantenimento elementi eliminati

Quando si eliminano messaggi individuali o elementi da una cassetta postale (non l'intera cassetta postale o una risorsa cartella pubblica) il contenuto viene mantenuto in un modulo ripristinabile in base al valore del parametro DeletedItemRetention per il database della cassetta postale o database della cartella pubblica. Il valore predefinito è pari a 14 giorni, ma questo valore può essere configurato dall'amministratore di Exchange.

## <a name="removing-soft-deleted-and-disconnected-mailboxes"></a>Rimozione di cassette postali disconnesse ed eliminate temporaneamente

Quando una cassetta postale di Exchange viene disattivata, eliminata o spostata tra database (ad esempio, durante il bilanciamento del carico), la cassetta postale viene posizionata nello stato disabilitato, eliminato temporaneamente o disconnesso a seconda dell'operazione. Con la cassetta postale in uno di questi stati, Exchange mantiene la cassetta postale, con il relativo contenuto, in base al valore corrente del parametro MailboxRetention specificato per il database delle cassette postali. Il valore predefinito è di 30 giorni, ma questo valore può essere configurato dall'amministratore di Exchange. È possibile usare il cmdlet [Remove-StoreMailbox](https://docs.microsoft.com/powershell/module/exchange/remove-storemailbox) per forzare Exchange a rimuovere definitivamente (eliminare) tutti i dati associati a una cassetta postale prima della scadenza naturale del periodo di conservazione.

> [!IMPORTANT]
> Utilizzare il cmdlet Remove-StoreMailbox con cautela poiché genera una perdita di dati irreversibile per la cassetta postale di destinazione. 

## <a name="on-prem-to-cloud-migrations"></a>Migrazioni da locale al cloud

Durante la migrazione dei dati da Exchange Server a Exchange Online, i dati inclusi nella migrazione possono continuare a risiedere nel server Exchange locale di origine in un formato recuperabile da un amministratore di Exchange. Per impostazione predefinita, questi dati vengono automaticamente rimossi dal database entro 30 giorni (vedere la sezione precedente Rimozione di cassette postali disconnesse ed eliminate temporaneamente).

## <a name="automatic-data-collection-reported-to-microsoft-by-exchange-server"></a>Raccolta automatica dei dati segnalata a Microsoft da Exchange Server

Exchange Server distribuiti in ambienti locali non forniscono alcun tipo di segnalazione automatica o di acquisizione dati dell'utente finale a Microsoft. Exchange Server con abilitata la segnalazione di dump di arresto anomalo del sistema di Dr Watson nel sistema operativo Windows possono ricevere contenuto di memoria limitato al momento in cui viene visualizzato il report di arresto anomalo.
