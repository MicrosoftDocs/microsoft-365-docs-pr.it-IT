---
title: Intelligence del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Gli amministratori possono ottenere informazioni sui codici di errore associati al recapito dei messaggi utilizzando i connettori (noti anche come intelligence del flusso di posta).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44f2272c98f0c011c05cbe728e720f4d3180c09d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844671"
---
# <a name="mail-flow-intelligence-in-eop"></a>Intelligence del flusso di posta in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, in genere si utilizza un connettore per instradare i messaggi di posta elettronica da EOP all'ambiente di posta elettronica locale. È inoltre possibile utilizzare un connettore per instradare i messaggi Microsoft 365 a un'organizzazione partner. Quando Microsoft 365 recapitare questi messaggi tramite il connettore, vengono accodati in Microsoft 365. Microsoft 365 continuerà a ripetere il recapito per ogni messaggio per 24 ore. Dopo 24 ore, il messaggio in coda scadrà e il messaggio verrà restituito al mittente originale in un rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito).

Microsoft 365 viene generato un errore quando non è possibile recapitare un messaggio utilizzando un connettore. Gli errori più comuni e le relative soluzioni sono descritti in questo articolo. Collettivamente, gli errori di accodamento e notifica per i messaggi non recapitabili inviati tramite connettori sono noti come _intelligence del flusso di posta_.

## <a name="error-code-450-44312-dns-query-failed"></a>Codice errore: 450 4.4.312 Query DNS non riuscita

In genere, questo errore Microsoft 365 tentativo di connettersi a uno smart host specificato nel connettore, ma la query DNS per trovare gli indirizzi IP dello smart host non è riuscita. Alcune possibili cause di questo errore:

- Si è verificato un errore relativo al servizio di hosting DNS del proprio dominio (la terza parte che gestisce i server dei nomi autorevoli per il dominio).

- Di recente, il dominio è scaduto e di conseguenza il record MX non può essere recuperato.

- Il record MX del dominio è stato modificato di recente e i server DNS hanno ancora le informazioni DNS memorizzate nella cache per il dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>Come è possibile correggere il codice di errore 450 4.4.312?

- Collaborare con il servizio di hosting DNS per identificare e risolvere il problema con il dominio.

- Se l'errore viene dall'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Codice errore: 450 4.4.315 Timeout della connessione

In genere, questo significa Microsoft 365 non è possibile connettersi al server di posta elettronica di destinazione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:

- Il server di posta elettronica locale non è disponibile.

- Si è verificato un errore nelle impostazioni smart host del connettore, quindi Microsoft 365 sta tentando di connettersi all'indirizzo IP errato.

### <a name="how-do-i-fix-error-code-450-44315"></a>Come è possibile correggere il codice di errore 450 4.4.315?

- Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni. Ad esempio, se il flusso di posta funziona correttamente e non sono state modificate le impostazioni del connettore, è necessario controllare l'ambiente di posta elettronica locale per verificare se il server non è disponibile o se sono state apportate modifiche all'infrastruttura di rete(ad esempio, sono stati modificati provider di servizi Internet, quindi ora si dispone di indirizzi IP diversi).

- Se l'errore viene dall'organizzazione partner (ad esempio, un provider di servizi cloud di terze parti), contattare il partner per risolvere il problema.

## <a name="error-code-450-44316-connection-refused"></a>Codice errore: 450 4.4.316 Connessione rifiutata

In genere, questo errore indica Microsoft 365 si è verificato un errore di connessione quando ha tentato di connettersi al server di posta elettronica di destinazione. Una causa probabile di questo errore è che il firewall blocca le connessioni Microsoft 365 indirizzi IP. In caso contrario, questo errore potrebbe essere dovuto alla progettazione se è stata eseguita la migrazione completa del sistema di posta elettronica locale a Microsoft 365 e si arresta l'ambiente di posta elettronica locale.

### <a name="how-do-i-fix-error-code-450-44316"></a>Come è possibile correggere il codice di errore 450 4.4.316?

- Se nell'ambiente locale sono presenti cassette postali, è necessario modificare le impostazioni del firewall per consentire le connessioni da indirizzi IP di Microsoft 365 sulla porta TCP 25 ai server di posta elettronica locali. Per un elenco degli indirizzi IP Microsoft 365, vedere [Microsoft 365 URL e intervalli di indirizzi IP.](../../enterprise/urls-and-ip-address-ranges.md)

- Se non devono essere recapitati altri messaggi all'ambiente locale, fare clic su Correggi ora nell'avviso in modo che Microsoft 365 possa rifiutare immediatamente i messaggi con destinatari non validi.  Questo consente di ridurre il rischio di superare la quota dell'organizzazione per i destinatari non validi, che possono compromettere il recapito dei messaggi normali. In alternativa, è possibile utilizzare le istruzioni seguenti per risolvere manualmente il problema:

  - Nell'Exchange di amministrazione [(EAC)](/Exchange/exchange-admin-center)disabilitare o eliminare il connettore che recapita la posta elettronica da Microsoft 365 all'ambiente di posta elettronica locale:

    1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Connettori**.

    2. Selezionare il connettore con **i** valori  **Da Office 365** e A per il server di posta elettronica **dell'organizzazione** ed eseguire una delle operazioni seguenti:
       - Eliminare il connettore facendo clic **sull'icona** ![ Elimina Rimuovi](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)
       - Disabilitare il connettore facendo **clic su Modifica** icona Modifica e ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **deselezionando Attiva.**

  - Modificare il dominio accettato in Microsoft 365 associato all'ambiente di posta elettronica locale da **Inoltro** interno **a Autorevole**. Per istruzioni, vedere [Manage accepted domains in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **Nota:** in genere, queste modifiche richiedono tra 30 minuti e un'ora per essere effettive. Dopo un'ora, verificare di non ricevere più l'errore.

- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Codice errore: 450 4.4.317 Impossibile connettersi al server remoto.

In genere, questo errore Microsoft 365 connesso al server di posta elettronica di destinazione, ma il server ha risposto con un errore immediato o non soddisfa i requisiti di connessione. Nei dettagli dell'errore è riportata una spiegazione del problema. Ad esempio:

- Il server di posta elettronica di destinazione ha risposto con un errore "Servizio non disponibile", che indica che il server non è in grado di mantenere la comunicazione con Microsoft 365.
- Il connettore è configurato per richiedere TLS, ma il server di posta elettronica di destinazione non supporta TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Come è possibile correggere il codice di errore 450 4.4.317?

- Verificare le impostazioni e i certificati TLS nei server di posta elettronica locali e le impostazioni TLS nel connettore.
- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Codice errore: 450 4.4.318 Connessione interrotta improvvisamente

In genere, questo errore Microsoft 365 problemi di comunicazione con l'ambiente di posta elettronica locale, quindi la connessione è stata interrotta. Alcune possibili cause di questo errore:

- Il firewall utilizza le regole di verifica del pacchetto SMTP e tali regole non funzionano correttamente.
- Il server di posta elettronica locale non funziona correttamente , ad esempio arresti anomali del servizio, arresti anomali o risorse di sistema limitate, causando il timeout del server e la chiusura della connessione a Microsoft 365.
- Esistono problemi di rete tra l'ambiente locale e Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Come è possibile correggere il codice di errore 450 4.4.318?

- Trovare informazioni sulla situazione adatta al proprio caso e apportare le dovute correzioni.
- Se il problema è causato da problemi di rete tra l'ambiente locale e Microsoft 365, contattare il team di rete per risolvere il problema.
- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Codice errore: 450 4.7.320 Convalida del certificato non riuscita

In genere, questo errore indica Microsoft 365 si è verificato un errore durante il tentativo di convalidare il certificato del server di posta elettronica di destinazione. Nei dettagli dell'errore è riportata una sua spiegazione. Ad esempio:

- Certificato scaduto
- Mancata corrispondenza oggetto certificato
- Certificato non più valido

### <a name="how-do-i-fix-error-code-450-47320"></a>Come è possibile correggere il codice di errore 450 4.7.320?

- Correggere il certificato o le impostazioni del connettore in modo che i messaggi in coda Microsoft 365 possano essere recapitati.
- Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.

## <a name="other-error-codes"></a>Altri codici errore

Microsoft 365 problemi di recapito dei messaggi al server di posta elettronica locale o partner. Utilizzare le informazioni **Server di destinazione** nell'errore per esaminare l'errore nel proprio ambiente o per modificare il connettore in presenza di un errore di configurazione.

Se l'errore è generato nell'organizzazione del partner (ad esempio, il provider di servizi cloud di terze parti), è necessario contattarlo e chiedere la risoluzione del problema.
