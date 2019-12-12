---
title: Accedere al portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: Viene visualizzato un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica si trova in Office 365? Se si ritiene di non dover ricevere tale messaggio di errore, è possibile utilizzare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365.
ms.openlocfilehash: 1cc4958c8ba680e49a454da1f3c7bfd009399da0
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971614"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>Usare il portale per l'esclusione di indirizzi IP dal filtro della posta indesiderata per rimuoversi dall'elenco mittenti bloccati di Office 365

Viene visualizzato un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica si trova in Office 365? Se si ritiene di non dover ricevere tale messaggio di errore, è possibile utilizzare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365.

## <a name="what-is-the-office-365-blocked-senders-list"></a>Che cos'è l'elenco dei mittenti bloccati di Office 365?

Microsoft utilizza l'elenco dei mittenti bloccati per proteggere i propri clienti da posta indesiderata, spoofing e attacchi di phishing. L'indirizzo IP del server di posta degli utenti, ovvero l'indirizzo utilizzato dal proprio server di posta per l'identificazione su Internet, è stato contrassegnato come potenziale minaccia in Office 365 per qualche motivo particolare. Quando l'indirizzo IP viene aggiunto all'elenco, Office 365 impedisce tutte le ulteriori comunicazioni tra tale indirizzo e un cliente qualsiasi tramite i datacenter.

Gli utenti scoprono di essere stati aggiunti all'elenco quando ricevono una risposta a un messaggio di posta elettronica che include un errore simile a quanto segue:

> 550 5.7.606-649 Access Denied, Banned Inviing IP [_indirizzo IP_]; Per richiedere la rimozione da questo elenco, https://sender.office.com/ visitare e seguire le indicazioni. Per ulteriori informazioni [, vedere rapporti di mancato recapito della posta elettronica in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

_IP address_ è l'indirizzo IP del computer in cui è in esecuzione il server di posta.

### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Per accedere al portale di esclusione di Office 365 e rimuoversi dall'elenco dei mittenti bloccati

1. In un browser Web, andare a [https://sender.office.com](https://sender.office.com).

2. Seguire le istruzioni visualizzate sulla pagina. Accertarsi di utilizzare l'indirizzo di posta elettronica al quale è stato recapitato il messaggio di errore e l'indirizzo IP specificato nel messaggio di errore. È possibile immettere solo un indirizzo di posta elettronica e un indirizzo IP per accesso.

3. Fare clic su **Invia**.

    Il portale invia un messaggio di posta elettronica all'indirizzo di posta elettronica fornito. Il messaggio di posta elettronica avrà un aspetto analogo al seguente: ![screenshot del messaggio di posta elettronica ricevuto quando si invia una richiesta tramite il portale di esclusione](../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Fare clic sul collegamento di conferma nel messaggio di posta elettronica inviato all'utente dal portale di esclusione.

    In questo modo si torna al portale di esclusione.

5. Nel portale di esclusione, fare clic su **Escludi indirizzo IP dall'elenco**.

    Dopo la rimozione dell'indirizzo IP dall'elenco dei mittenti bloccati, i messaggi di posta elettronica dall'indirizzo IP verranno recapitati ai destinatari che utilizzano Office 365. Pertanto, assicurarsi che la posta elettronica inviata da tale indirizzo IP non sia offensiva o dannosa; in caso contrario, l'indirizzo IP verrà bloccato di nuovo.

    > [!NOTE]
    > Potrebbe richiedere fino a 24 ore o i risultati possono variare notevolmente prima che vengano rimosse le restrizioni.

Informazioni su [come impedire che i messaggi di posta elettronica reali vengano contrassegnati come posta indesiderata in office 365](../../compliance/prevent-email-from-being-marked-as-spam.md ) e che [controllino la posta indesiderata in uscita in Office 365](outbound-spam-controls.md) per impedire la blacklist di IP.
