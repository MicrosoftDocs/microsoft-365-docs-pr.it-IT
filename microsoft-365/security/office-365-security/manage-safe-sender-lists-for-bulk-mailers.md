---
title: Gestire gli elenchi di mittenti attendibili per messaggi inviati in blocco
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: "Se si desidera utilizzare elenchi di mittenti attendibili, è necessario sapere che Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio rispetta i mittenti e i domini attendibili esaminando l'indirizzo RFC 5321. MailFrom e l'indirizzo RFC 5322. from, mentre Outlook aggiunge l'indirizzo RFC 5322. from all'elenco dei mittenti attendibili di un utente. Nota: il servizio controlla sia l'indirizzo 5321. MailFrom sia l'indirizzo 5322. from per i mittenti e i domini bloccati."
ms.openlocfilehash: 2dcfd73cc987290bbc8ca8111580a374216a843e
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970302"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="33206-105">Gestire gli elenchi di mittenti attendibili per messaggi inviati in blocco</span><span class="sxs-lookup"><span data-stu-id="33206-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="33206-106">Se si desidera utilizzare elenchi di mittenti attendibili, è necessario sapere che Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="33206-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="33206-107">Il servizio Office 365 rispetta i mittenti e i domini attendibili esaminando `RFC 5321.MailFrom` l'indirizzo e `RFC 5322.From` l'indirizzo, mentre Outlook aggiunge `RFC 5322.From` l'indirizzo all'elenco dei mittenti attendibili di un utente.</span><span class="sxs-lookup"><span data-stu-id="33206-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="33206-108">(Nota: il servizio controlla sia l' `5321.MailFrom` indirizzo che `5322.From` l'indirizzo per i mittenti e i domini bloccati).</span><span class="sxs-lookup"><span data-stu-id="33206-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="33206-109">L' `SMTP MAIL FROM` indirizzo, altrimenti noto come `RFC 5321.MailFrom address`, è l'indirizzo di posta elettronica utilizzato per eseguire i controlli SPF e, se non è possibile recapitare la posta, il percorso in cui il messaggio è stato recapitato.</span><span class="sxs-lookup"><span data-stu-id="33206-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="33206-110">Si tratta di questo indirizzo di posta elettronica che viene `Return-Path` inserito nelle intestazioni del messaggio per impostazione predefinita, anche se è possibile che il mittente designi un `Return-Path` indirizzo diverso.</span><span class="sxs-lookup"><span data-stu-id="33206-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="33206-111">L' `From:` indirizzo nelle intestazioni del messaggio, altrimenti noto come `RFC 5322.From` indirizzo, è l'indirizzo di posta elettronica visualizzato nel client di posta elettronica, ad esempio Outlook.</span><span class="sxs-lookup"><span data-stu-id="33206-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="33206-112">La maggior parte del tempo, `5321.MailFrom` gli `5322.From` indirizzi e sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="33206-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="33206-113">Questa è la caratteristica tipica della comunicazione da persona a persona.</span><span class="sxs-lookup"><span data-stu-id="33206-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="33206-114">Tuttavia, quando viene inviato un messaggio di posta elettronica per conto di qualcun altro, gli indirizzi sono spesso diversi.</span><span class="sxs-lookup"><span data-stu-id="33206-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="33206-115">Questo accade solitamente più spesso per i messaggi di posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="33206-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="33206-116">Si supponga, ad esempio, che la compagnia aerea Blu laggiù abbia assunto Margie ' s Travel per inviare la propria pubblicità tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="33206-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="33206-117">È quindi possibile ottenere un messaggio nella posta in arrivo dal mittente blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="33206-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="33206-118">In questo esempio:</span><span class="sxs-lookup"><span data-stu-id="33206-118">In this example:</span></span>

- <span data-ttu-id="33206-119">L' `5321.MailFrom` indirizzo è blueyonder.Airlines@margiestravel.com.</span><span class="sxs-lookup"><span data-stu-id="33206-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="33206-120">L' `5322.From` indirizzo è blueyonder@news.blueyonderairlines.com, che è quello che vedrai in Outlook.</span><span class="sxs-lookup"><span data-stu-id="33206-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="33206-121">Per evitare che il messaggio venga filtrato, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33206-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="33206-122">**Come utente**: aggiungere l' `RFC 5322.From` indirizzo come mittente attendibile in Outlook.</span><span class="sxs-lookup"><span data-stu-id="33206-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="33206-123">**Come amministratore**: impostare una regola del [flusso di posta](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (nota anche come regola di trasporto).</span><span class="sxs-lookup"><span data-stu-id="33206-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
