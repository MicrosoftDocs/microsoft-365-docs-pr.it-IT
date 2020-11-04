---
title: Intelligence del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Gli amministratori possono ottenere informazioni sui codici di errore associati al recapito dei messaggi utilizzando i connettori (noti anche come Intelligence del flusso di posta).
ms.openlocfilehash: 461d9bfa91d88b8bbec52d5aad6ec7a2e534bc96
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877802"
---
# <a name="mail-flow-intelligence-in-eop"></a>Intelligence del flusso di posta in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, si utilizza in genere un connettore per instradare i messaggi di posta elettronica da EOP all'ambiente di posta elettronica locale. È inoltre possibile utilizzare un connettore per instradare i messaggi da Microsoft 365 a un'organizzazione partner. Quando Microsoft 365 non è in grado di recapitare questi messaggi tramite il connettore, vengono accodati in Microsoft 365. Microsoft 365 continuerà a riprovare il recapito per ogni messaggio per 24 ore. Dopo 24 ore, il messaggio in coda scadrà e il messaggio verrà restituito al mittente originale in un rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo).

Microsoft 365 genera un errore quando un messaggio non può essere recapitato utilizzando un connettore. In questo argomento sono descritti gli errori più comuni e le relative soluzioni. Gli errori di Accodamento e di notifica per i messaggi non recapitabili inviati tramite connettori sono noti come _Intelligence del flusso di posta_.

## <a name="error-code-450-44312-dns-query-failed"></a>Codice errore: 450 4.4.312 Query DNS non riuscita

In genere, questo errore indica che Microsoft 365 ha tentato di connettersi allo smart host specificato nel connettore, ma la query DNS per individuare gli indirizzi IP dello smart host ha avuto esito negativo. Alcune possibili cause di questo errore:

- Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).

- Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.

- Il record MX del dominio è stato recentemente modificato e i server DNS hanno ancora le informazioni DNS precedentemente memorizzate nella cache per il dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>Come risolvere il codice di errore 450 4.4.312?

- Collaborare con il servizio di hosting DNS per identificare e risolvere il problema con il dominio.

- Se l'errore è dell'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Codice errore: 450 4.4.315 Timeout della connessione

In genere, questo significa che Microsoft 365 non è in grado di connettersi al server di posta elettronica di destinazione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:

- Il server di posta elettronica locale è inattiva.

- Si è verificato un errore nelle impostazioni dello smart host del connettore, quindi Microsoft 365 sta tentando di connettersi all'indirizzo IP errato.

### <a name="how-do-i-fix-error-code-450-44315"></a>Come risolvere il codice di errore 450 4.4.315?

- Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni. Ad esempio, se il flusso di posta funziona correttamente e non sono state modificate le impostazioni del connettore, è necessario controllare l'ambiente di posta elettronica locale per verificare se il server è inattivo o se sono state apportate modifiche all'infrastruttura di rete (ad esempio, i provider di servizi Internet sono stati modificati).

- Se l'errore è dell'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.

## <a name="error-code-450-44316-connection-refused"></a>Codice errore: 450 4.4.316 Connessione rifiutata

In genere, questo errore indica che Microsoft 365 ha riscontrato un errore di connessione quando ha tentato di connettersi al server di posta elettronica di destinazione. Una probabile causa di questo errore è che il firewall sta bloccando le connessioni dagli indirizzi IP di Microsoft 365. In alternativa, questo errore potrebbe essere dovuto alla progettazione se la migrazione del sistema di posta elettronica locale è stata completata in Microsoft 365 e arrestare l'ambiente di posta elettronica locale.

### <a name="how-do-i-fix-error-code-450-44316"></a>Come risolvere il codice di errore 450 4.4.316?

- Se si dispone di cassette postali nell'ambiente locale, è necessario modificare le impostazioni del firewall per consentire le connessioni dagli indirizzi IP di Microsoft 365 sulla porta TCP 25 ai server di posta elettronica locali. Per un elenco degli indirizzi IP di Microsoft 365, vedere [URL e intervalli di indirizzi IP di microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).

- Se non è necessario recapitare altri messaggi all'ambiente locale, fare clic su **Correggi ora** nell'avviso in modo che Microsoft 365 possa rifiutare immediatamente i messaggi con destinatari non validi. Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema:

  - Nell'interfaccia di [amministrazione di Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disabilitare o eliminare il connettore che invia messaggi di posta elettronica da Microsoft 365 all'ambiente di posta elettronica locale:

    1. Nell'interfaccia di amministrazione di Exchange, andare a connettori del **flusso di posta** \> **Connectors**.

    2. Selezionare il connettore con il **From** valore da **Office 365** e il valore **per** il **server di posta elettronica dell'organizzazione** ed eseguire una delle operazioni seguenti:

       - Eliminare il connettore facendo clic su **Elimina** ![ icona Rimuovi](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Disabilitare il connettore facendo clic su **modifica** ![ icona modifica ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) e deselezionando **attivarlo**.

  - Modificare il dominio accettato in Microsoft 365 associato all'ambiente di posta elettronica locale dall' **inoltro interno** a **autorevole**. Per istruzioni, vedere [Manage Accepted Domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Nota** : in genere, queste modifiche impiegano tra 30 minuti e un'ora per rendere effettive le operazioni. Dopo un'ora, verificare che l'errore non sia più stato ricevuto.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.

In genere, questo errore indica che Microsoft 365 è connesso al server di posta elettronica di destinazione, ma il server ha risposto con un errore immediato o non soddisfa i requisiti di connessione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:

- Il server di posta elettronica di destinazione ha risposto con un messaggio di errore "servizio non disponibile", che indica che il server non è in grado di mantenere la comunicazione con Microsoft 365.

- Il connettore è configurato per richiedere TLS, ma il server di posta elettronica di destinazione non supporta TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Come risolvere il codice di errore 450 4.4.317?

- Verificare le impostazioni e i certificati TLS nei server di posta elettronica locali e le impostazioni TLS sul connettore.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Codice errore: 450 4.4.318 Connessione interrotta improvvisamente

In genere, questo errore indica che Microsoft 365 ha difficoltà a comunicare con l'ambiente di posta elettronica locale, in modo che la connessione sia stata eliminata. Alcune possibili cause di questo errore:

- Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.

- Il server di posta elettronica locale non funziona correttamente (ad esempio, il servizio si blocca, si arresta in modo anomalo o con risorse di sistema ridotte), causando il timeout del server e la chiusura della connessione a Microsoft 365.

- Esistono problemi di rete tra l'ambiente locale e Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Come risolvere il codice di errore 450 4.4.318?

- Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.

- Se il problema è causato da problemi di rete tra l'ambiente locale e Microsoft 365, contattare il team di rete per risolvere il problema.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Codice errore: 450 4.7.320 Convalida del certificato non riuscita

In genere, questo errore indica che Microsoft 365 ha riscontrato un errore durante il tentativo di convalidare il certificato del server di posta elettronica di destinazione. Nei dettagli dell'errore è riportata una sua spiegazione. Ad esempio:

- Certificato scaduto

- Mancata corrispondenza oggetto certificato

- Certificato non più valido

### <a name="how-do-i-fix-error-code-450-47320"></a>Come risolvere il codice di errore 450 4.7.320?

- Consente di risolvere il certificato o le impostazioni sul connettore in modo che i messaggi in coda in Microsoft 365 possano essere recapitati.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="other-error-codes"></a>Altri codici errore

Microsoft 365 ha difficoltà a recapitare i messaggi al server di posta elettronica locale o partner. Utilizzare le informazioni **Server di destinazione** nell'errore per esaminare l'errore nel proprio ambiente o per modificare il connettore in presenza di un errore di configurazione.

Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
