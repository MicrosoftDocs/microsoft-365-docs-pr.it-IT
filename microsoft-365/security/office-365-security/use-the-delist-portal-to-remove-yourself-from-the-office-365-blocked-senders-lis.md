---
title: Rimuovere se stessi dall'elenco dei mittenti bloccati
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: In questo articolo viene illustrato come usare il portale di rimozione per rimuoversi dall'elenco dei mittenti bloccati di Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c11fced30ef52315ecb44dda51e6825d36b57c7e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287522"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Usare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Si riceve un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica è in Microsoft 365? Se si pensa di non ricevere il messaggio di errore, è possibile utilizzare il portale di rimozione per rimuoversi dall'elenco dei mittenti bloccati.

## <a name="what-is-the-blocked-senders-list"></a>Che cos'è l'elenco dei mittenti bloccati?

Microsoft utilizza l'elenco dei mittenti bloccati per proteggere i propri clienti da posta indesiderata, spoofing e attacchi di phishing. L'indirizzo IP del server di posta, cio? l'indirizzo utilizzato dal server di posta per identificarsi su Internet, è stato contrassegnato come potenziale minaccia per Microsoft 365 per una serie di motivi. Quando Microsoft 365 aggiunge l'indirizzo IP all'elenco, impedisce tutte le ulteriori comunicazioni tra l'indirizzo IP e qualsiasi cliente tramite i datacenter.

Gli utenti scoprono di essere stati aggiunti all'elenco quando ricevono una risposta a un messaggio di posta elettronica che include un errore simile a quanto segue:

> 550 5.7.606-649 Accesso negato, IP di invio escluso [_indirizzo IP_]; Per richiedere la rimozione da questo elenco, visitare <https://sender.office.com/> e seguire le istruzioni. Per ulteriori informazioni, vedere [Rapporti di mancato recapito della posta elettronica in Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

_IP address_ è l'indirizzo IP del computer in cui è in esecuzione il server di posta.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Per utilizzare il portale di eliminazione per rimuoversi dall'elenco dei mittenti bloccati

1. In un browser Web, andare a <https://sender.office.com>.

2. Seguire le istruzioni visualizzate sulla pagina. Accertarsi di utilizzare l'indirizzo di posta elettronica al quale è stato recapitato il messaggio di errore e l'indirizzo IP specificato nel messaggio di errore. È possibile immettere solo un indirizzo di posta elettronica e un indirizzo IP per accesso.

3. Fare clic su **Invia**.

    Il portale invia un messaggio di posta elettronica all'indirizzo di posta elettronica fornito. Il messaggio di posta elettronica avrà un aspetto simile al ![ seguente: Screenshot della posta elettronica ricevuta quando si invia una richiesta tramite il portale di diserta](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Fare clic sul collegamento di conferma nel messaggio di posta elettronica inviato all'utente dal portale di esclusione.

    In questo modo si torna al portale di esclusione.

5. Nel portale di esclusione, fare clic su **Escludi indirizzo IP dall'elenco**.

    Una volta rimosso l'indirizzo IP dall'elenco dei mittenti bloccati, i messaggi di posta elettronica da tale indirizzo IP verranno recapitati ai destinatari che usano Microsoft 365. Pertanto, assicurarsi che la posta elettronica inviata da tale indirizzo IP non sia offensiva o dannosa; in caso contrario, l'indirizzo IP verrà bloccato di nuovo.

    > [!NOTE]
    > Potrebbero essere necessario fino a 24 ore o i risultati possono variare notevolmente prima della rimozione delle restrizioni.

Vedere [Creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md) e Protezione da posta indesiderata in uscita in [EOP](outbound-spam-controls.md) per impedire il blocco di un IP.
