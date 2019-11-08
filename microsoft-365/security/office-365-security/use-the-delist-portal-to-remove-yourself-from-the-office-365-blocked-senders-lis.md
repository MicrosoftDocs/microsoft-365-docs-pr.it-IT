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
ms.openlocfilehash: c02234379fe2b5d8fc09f81b1b407fec45900e3f
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030620"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a><span data-ttu-id="0e482-104">Usare il portale per l'esclusione di indirizzi IP dal filtro della posta indesiderata per rimuoversi dall'elenco mittenti bloccati di Office 365</span><span class="sxs-lookup"><span data-stu-id="0e482-104">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>

<span data-ttu-id="0e482-p102">Viene visualizzato un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica si trova in Office 365? Se si ritiene di non dover ricevere tale messaggio di errore, è possibile utilizzare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e482-p102">Are you getting an error message when you try to send an email to a recipient whose email address is in Office 365? If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the Office 365 blocked senders list.</span></span>
  
## <a name="what-is-the-office-365-blocked-senders-list"></a><span data-ttu-id="0e482-107">Che cos'è l'elenco dei mittenti bloccati di Office 365?</span><span class="sxs-lookup"><span data-stu-id="0e482-107">What is the Office 365 blocked senders list?</span></span>

<span data-ttu-id="0e482-p103">Microsoft utilizza l'elenco dei mittenti bloccati per proteggere i propri clienti da posta indesiderata, spoofing e attacchi di phishing. L'indirizzo IP del server di posta degli utenti, ovvero l'indirizzo utilizzato dal proprio server di posta per l'identificazione su Internet, è stato contrassegnato come potenziale minaccia in Office 365 per qualche motivo particolare. Quando l'indirizzo IP viene aggiunto all'elenco, Office 365 impedisce tutte le ulteriori comunicazioni tra tale indirizzo e un cliente qualsiasi tramite i datacenter.</span><span class="sxs-lookup"><span data-stu-id="0e482-p103">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks. Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Office 365 for one of a variety of reasons. When Office 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>
  
<span data-ttu-id="0e482-111">Gli utenti scoprono di essere stati aggiunti all'elenco quando ricevono una risposta a un messaggio di posta elettronica che include un errore simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0e482-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>
  
> <span data-ttu-id="0e482-112">550 5.7.606-649 Access Denied, Banned Inviing IP [_indirizzo IP_]; Per richiedere la rimozione da questo elenco, https://sender.office.com/ visitare e seguire le indicazioni.</span><span class="sxs-lookup"><span data-stu-id="0e482-112">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="0e482-113">Per ulteriori informazioni, vedere [rapporti di mancato recapito della posta elettronica in Office 365](https://go.microsoft.com/fwlink/?LinkID=526653).</span><span class="sxs-lookup"><span data-stu-id="0e482-113">For more information please see [Email non-delivery reports in Office 365](https://go.microsoft.com/fwlink/?LinkID=526653).</span></span>
  
<span data-ttu-id="0e482-114">_IP address_ è l'indirizzo IP del computer in cui è in esecuzione il server di posta.</span><span class="sxs-lookup"><span data-stu-id="0e482-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span> 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="0e482-115">Per accedere al portale di esclusione di Office 365 e rimuoversi dall'elenco dei mittenti bloccati</span><span class="sxs-lookup"><span data-stu-id="0e482-115">To use the Office 365 delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="0e482-116">In un browser Web, andare a [https://sender.office.com](https://sender.office.com).</span><span class="sxs-lookup"><span data-stu-id="0e482-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>
    
2. <span data-ttu-id="0e482-p105">Seguire le istruzioni visualizzate sulla pagina. Accertarsi di utilizzare l'indirizzo di posta elettronica al quale è stato recapitato il messaggio di errore e l'indirizzo IP specificato nel messaggio di errore. È possibile immettere solo un indirizzo di posta elettronica e un indirizzo IP per accesso.</span><span class="sxs-lookup"><span data-stu-id="0e482-p105">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>
    
3. <span data-ttu-id="0e482-120">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="0e482-120">Click **Submit**.</span></span>
    
    <span data-ttu-id="0e482-121">Il portale invia un messaggio di posta elettronica all'indirizzo di posta elettronica fornito.</span><span class="sxs-lookup"><span data-stu-id="0e482-121">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="0e482-122">Il messaggio di posta elettronica avrà un aspetto analogo al seguente: ![screenshot del messaggio di posta elettronica ricevuto quando si invia una richiesta tramite il portale di esclusione](../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="0e482-122">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>
  
4. <span data-ttu-id="0e482-123">Fare clic sul collegamento di conferma nel messaggio di posta elettronica inviato all'utente dal portale di esclusione.</span><span class="sxs-lookup"><span data-stu-id="0e482-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>
    
    <span data-ttu-id="0e482-124">In questo modo si torna al portale di esclusione.</span><span class="sxs-lookup"><span data-stu-id="0e482-124">This brings you back to the delist portal.</span></span>
    
5. <span data-ttu-id="0e482-125">Nel portale di esclusione, fare clic su **Escludi indirizzo IP dall'elenco**.</span><span class="sxs-lookup"><span data-stu-id="0e482-125">In the delist portal, click **Delist IP**.</span></span>
    
    <span data-ttu-id="0e482-p107">Dopo la rimozione dell'indirizzo IP dall'elenco dei mittenti bloccati, i messaggi di posta elettronica dall'indirizzo IP verranno recapitati ai destinatari che utilizzano Office 365. Pertanto, assicurarsi che la posta elettronica inviata da tale indirizzo IP non sia offensiva o dannosa; in caso contrario, l'indirizzo IP verrà bloccato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="0e482-p107">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Office 365. So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e482-128">Potrebbe richiedere fino a 24 ore o i risultati possono variare notevolmente prima che vengano rimosse le restrizioni.</span><span class="sxs-lookup"><span data-stu-id="0e482-128">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>
    
<span data-ttu-id="0e482-129">Informazioni su [come impedire che i messaggi di posta elettronica reali vengano contrassegnati come posta indesiderata in office 365](../../compliance/prevent-email-from-being-marked-as-spam.md ) e che [controllino la posta indesiderata in uscita in Office 365](outbound-spam-controls.md) per impedire la blacklist di IP.</span><span class="sxs-lookup"><span data-stu-id="0e482-129">Read about [How to prevent real email from being marked as spam in Office 365](../../compliance/prevent-email-from-being-marked-as-spam.md ) and [Controlling outbound spam in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
