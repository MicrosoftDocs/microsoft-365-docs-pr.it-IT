---
title: Business intelligence di flusso di posta elettronica in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Gli amministratori possono ottenere informazioni sui codici di errore associati al recapito dei messaggi utilizzando i connettori di Office 365 (noto anche come Intelligence del flusso di posta).
ms.openlocfilehash: d49937afb379b43821d905001e8aee21ca86eb52
ms.sourcegitcommit: b91d75d2631166ddd158d26a0a476e26391a58ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "37886859"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Intelligence del flusso di posta in Office 365

In genere, si utilizza un connettore per instradare i messaggi di posta elettronica dall'organizzazione di Office 365 all'ambiente di posta elettronica locale. È anche possibile usare un connettore per instradare i messaggi da Office 365 a un'organizzazione partner. Quando Office 365 non è in grado di recapitare tali messaggi attraverso il connettore, questi ultimi vengono messi in coda in Office 365. Office 365 continuerà a riprovare il recapito per ogni messaggio per 24 ore. Dopo 24 ore, il messaggio in coda scadrà e il messaggio verrà restituito al mittente originale in un rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo).

Office 365 genera un errore quando un messaggio non può essere recapitato utilizzando un connettore. In questo argomento sono descritti gli errori più comuni e le relative soluzioni. Gli errori di Accodamento e di notifica per i messaggi non recapitabili inviati tramite connettori sono noti come _Intelligence del flusso di posta_.

## <a name="error-code-450-44312-dns-query-failed"></a>Codice errore: 450 4.4.312 Query DNS non riuscita

In genere, questo errore indica che Office 365 ha tentato di connettersi allo smart host specificato nel connettore, ma la query DNS per individuare gli indirizzi IP dello smart host ha avuto esito negativo. Alcune possibili cause di questo errore:

- Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).

- Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.

- Il record MX del dominio è stato recentemente modificato e i server DNS di Office 365 hanno ancora le informazioni DNS memorizzate in precedenza per il dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>Come risolvere il codice di errore 450 4.4.312?

- Collaborare con il servizio di hosting DNS per identificare e risolvere il problema con il dominio.

- Se l'errore è dell'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Codice errore: 450 4.4.315 Timeout della connessione

In genere, questo significa che Office 365 non è in grado di connettersi al server di posta elettronica di destinazione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:

- Il server di posta elettronica locale è inattiva.

- Si è verificato un errore relativo alle impostazione dello smart host del connettore, quindi Office 365 prova a connettersi all'indirizzo IP sbagliato.

### <a name="how-do-i-fix-error-code-450-44315"></a>Come risolvere il codice di errore 450 4.4.315?

- Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni. Ad esempio, se il flusso di posta funziona correttamente e non sono state modificate le impostazioni del connettore, è necessario controllare l'ambiente di posta elettronica locale per verificare se il server è inattivo o se sono state apportate modifiche all'infrastruttura di rete (ad esempio, sono stati modificati i provider di servizi Internet, quindi sono presenti diversi indirizzi IP.

- Se l'errore è dell'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.

## <a name="error-code-450-44316-connection-refused"></a>Codice errore: 450 4.4.316 Connessione rifiutata

In genere, questo errore indica che Office 365 ha riscontrato un errore di connessione quando ha tentato di connettersi al server di posta elettronica di destinazione. Una delle probabili cause di questo errore è la presenza di un firewall che blocca le connessioni dagli indirizzi IP di Office 365. In alternativa, questo errore potrebbe essere dovuto alla progettazione se la migrazione del sistema di posta elettronica locale è stata completata in Office 365 e arrestare l'ambiente di posta elettronica locale.

### <a name="how-do-i-fix-error-code-450-44316"></a>Come risolvere il codice di errore 450 4.4.316?

- Se si dispone di cassette postali nell'ambiente locale, è necessario modificare le impostazioni del firewall per consentire le connessioni dagli indirizzi IP di Office 365 sulla porta TCP 25 ai server di posta elettronica locali. Per visualizzare un elenco degli indirizzi IP di Office 365, vedere [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).

- Se non devono essere recapitati più messaggi nell'ambiente locale, fare clic su **Correggi ora** nell'avviso affinché Office 365 possa rifiutare immediatamente i messaggi con destinatari non validi. Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema:

  - Nell'interfaccia di [amministrazione di Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disabilitare o eliminare il connettore che invia messaggi di posta elettronica da Office 365 all'ambiente di posta elettronica locale:

    1. Nell'interfaccia di amministrazione di Exchange, andare a **connettori**del **flusso** \> di posta.

    2. Selezionare il connettore con il **** valore da **Office 365** e il valore **per** il **server di posta elettronica dell'organizzazione** ed eseguire una delle operazioni seguenti:

       - Eliminare il connettore facendo clic su **Elimina** ![icona Rimuovi](../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Disabilitare il connettore facendo clic su **modifica** ![icona](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) modifica e deselezionando **attiva**.

  - Modificare il dominio accettato in Office 365 associato all'ambiente di posta elettronica locale dall' **inoltro interno** a **autorevole**. Per istruzioni, vedere [Manage Accepted Domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).

  **Nota**: in genere, queste modifiche impiegano tra 30 minuti e un'ora per rendere effettive le operazioni. Dopo un'ora, verificare che l'errore non sia più stato ricevuto.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.

In genere, questo errore indica che Office 365 è connesso al server di posta elettronica di destinazione, ma il server ha risposto con un errore immediato o non soddisfa i requisiti di connessione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:

- Il server di posta elettronica di destinazione ha risposto con un messaggio di errore "servizio non disponibile", che indica che il server non è in grado di mantenere la comunicazione con Office 365.

- Il connettore è configurato per richiedere TLS, ma il server di posta elettronica di destinazione non supporta TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Come risolvere il codice di errore 450 4.4.317?

- Verificare le impostazioni e i certificati TLS nei server di posta elettronica locali e le impostazioni TLS sul connettore.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Codice errore: 450 4.4.318 Connessione interrotta improvvisamente

In genere, questo errore indica che Office 365 ha difficoltà a comunicare con l'ambiente di posta elettronica locale, in modo che la connessione sia stata eliminata. Alcune possibili cause di questo errore:

- Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.

- Il server di posta elettronica locale non funziona correttamente (ad esempio, il servizio si blocca, si arresta in modo anomalo o con risorse di sistema ridotte), causando il timeout del server e la chiusura della connessione a Office 365.

- Sono presenti errori di rete tra l'ambiente locale e Office 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Come risolvere il codice di errore 450 4.4.318?

- Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.

- Se il problema è causato da problemi di rete tra l'ambiente locale e Office 365, contattare il team di rete per risolvere il problema.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Codice errore: 450 4.7.320 Convalida del certificato non riuscita

In genere, questo errore indica che Office 365 ha riscontrato un errore durante il tentativo di convalidare il certificato del server di posta elettronica di destinazione. Nei dettagli dell'errore è riportata una sua spiegazione. Ad esempio:

- Certificato scaduto

- Mancata corrispondenza oggetto certificato

- Certificato non più valido

### <a name="how-do-i-fix-error-code-450-47320"></a>Come risolvere il codice di errore 450 4.7.320?

- Consente di risolvere il certificato o le impostazioni sul connettore in modo che i messaggi in coda in Office 365 possano essere recapitati.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="other-error-codes"></a>Altri codici errore

Office 365 ha difficoltà a recapitare i messaggi al server di posta elettronica locale o partner. Utilizzare le informazioni **Server di destinazione** nell'errore per esaminare l'errore nel proprio ambiente o per modificare il connettore in presenza di un errore di configurazione.

Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
