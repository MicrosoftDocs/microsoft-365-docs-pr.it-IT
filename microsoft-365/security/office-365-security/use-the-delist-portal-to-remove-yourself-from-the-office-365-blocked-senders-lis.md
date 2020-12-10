---
title: Rimuovi dall'elenco Mittenti bloccati
f1.keywords:
- NOCSH
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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: In questo articolo viene illustrato come utilizzare il portale di esclusione per rimuovere se stessi dall'elenco dei mittenti bloccati di Microsoft 365.
ms.openlocfilehash: 0c87d467db004a50502402b05eb0fa3283aa46c5
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614763"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="cc435-103">Usare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati</span><span class="sxs-lookup"><span data-stu-id="cc435-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cc435-104">Quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica è in Microsoft 365, viene visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="cc435-104">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="cc435-105">Se si ritiene che non sia necessario ricevere il messaggio di errore, è possibile utilizzare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="cc435-105">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="cc435-106">Che cos'è l'elenco Mittenti bloccati?</span><span class="sxs-lookup"><span data-stu-id="cc435-106">What is the blocked senders list?</span></span>

<span data-ttu-id="cc435-107">Microsoft utilizza l'elenco dei mittenti bloccati per proteggere i propri clienti da posta indesiderata, spoofing e attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="cc435-107">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="cc435-108">L'indirizzo IP del server di posta, ovvero l'indirizzo utilizzato dal server di posta elettronica per identificarsi su Internet, è stato contrassegnato come potenziale pericolo per Microsoft 365 per una serie di motivi.</span><span class="sxs-lookup"><span data-stu-id="cc435-108">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="cc435-109">Quando Microsoft 365 aggiunge l'indirizzo IP all'elenco, impedisce tutte le comunicazioni successive tra l'indirizzo IP e uno qualsiasi dei clienti tramite i datacenter.</span><span class="sxs-lookup"><span data-stu-id="cc435-109">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="cc435-110">Gli utenti scoprono di essere stati aggiunti all'elenco quando ricevono una risposta a un messaggio di posta elettronica che include un errore simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cc435-110">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="cc435-111">550 5.7.606-649 Access Denied, Banned Inviing IP [_indirizzo IP_]; Per richiedere la rimozione da questo elenco <https://sender.office.com/> , visitare e seguire le indicazioni.</span><span class="sxs-lookup"><span data-stu-id="cc435-111">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="cc435-112">Per ulteriori informazioni [, vedere rapporti di mancato recapito della posta elettronica in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="cc435-112">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="cc435-113">_IP address_ è l'indirizzo IP del computer in cui è in esecuzione il server di posta.</span><span class="sxs-lookup"><span data-stu-id="cc435-113">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="cc435-114">Per utilizzare il portale di delist per rimuovere se stessi dall'elenco dei mittenti bloccati</span><span class="sxs-lookup"><span data-stu-id="cc435-114">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="cc435-115">In un browser Web, andare a <https://sender.office.com>.</span><span class="sxs-lookup"><span data-stu-id="cc435-115">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="cc435-p104">Seguire le istruzioni visualizzate sulla pagina. Accertarsi di utilizzare l'indirizzo di posta elettronica al quale è stato recapitato il messaggio di errore e l'indirizzo IP specificato nel messaggio di errore. È possibile immettere solo un indirizzo di posta elettronica e un indirizzo IP per accesso.</span><span class="sxs-lookup"><span data-stu-id="cc435-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="cc435-119">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="cc435-119">Click **Submit**.</span></span>

    <span data-ttu-id="cc435-120">Il portale invia un messaggio di posta elettronica all'indirizzo di posta elettronica fornito.</span><span class="sxs-lookup"><span data-stu-id="cc435-120">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="cc435-121">Il messaggio di posta elettronica avrà un aspetto analogo al seguente: ![ screenshot del messaggio di posta elettronica ricevuto quando si invia una richiesta tramite il portale di esclusione](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="cc435-121">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="cc435-122">Fare clic sul collegamento di conferma nel messaggio di posta elettronica inviato all'utente dal portale di esclusione.</span><span class="sxs-lookup"><span data-stu-id="cc435-122">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="cc435-123">In questo modo si torna al portale di esclusione.</span><span class="sxs-lookup"><span data-stu-id="cc435-123">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="cc435-124">Nel portale di esclusione, fare clic su **Escludi indirizzo IP dall'elenco**.</span><span class="sxs-lookup"><span data-stu-id="cc435-124">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="cc435-125">Dopo che l'indirizzo IP è stato rimosso dall'elenco dei mittenti bloccati, i messaggi di posta elettronica provenienti da tale indirizzo IP verranno recapitati ai destinatari che utilizzano Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc435-125">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="cc435-126">Pertanto, assicurarsi che la posta elettronica inviata da tale indirizzo IP non sia offensiva o dannosa; in caso contrario, l'indirizzo IP verrà bloccato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="cc435-126">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc435-127">Potrebbe richiedere fino a 24 ore o i risultati possono variare notevolmente prima che vengano rimosse le restrizioni.</span><span class="sxs-lookup"><span data-stu-id="cc435-127">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="cc435-128">Vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md) e la [protezione da posta indesiderata in uscita in EOP](outbound-spam-controls.md) per impedire che un IP venga bloccato.</span><span class="sxs-lookup"><span data-stu-id="cc435-128">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>
