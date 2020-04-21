---
title: Risolvere i problemi relativi alle cassette postali condivise
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Provare queste soluzioni se si verificano problemi con le cassette postali condivise.
ms.openlocfilehash: 52aac8ab6936dfeba2ae4b5b7a80c45029ec6105
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628748"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="67e38-103">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="67e38-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="67e38-104">Se viene visualizzato un messaggio di errore durante la creazione o l'utilizzo di una cassetta postale condivisa, provare queste possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="67e38-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="67e38-105">Errore durante la creazione di cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="67e38-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="67e38-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="67e38-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="67e38-107">Se viene visualizzato il messaggio di errore, **l'indirizzo proxy "SMTP: <nome\>della cassetta postale condivisa" è già utilizzato dagli indirizzi proxy o legacyExchangeDN di\<"Name>". Scegliere un altro indirizzo proxy**, significa che si sta tentando di assegnare alla cassetta postale condivisa un nome già in uso.</span><span class="sxs-lookup"><span data-stu-id="67e38-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="67e38-108">Ad esempio, supponiamo di voler assegnare a due cassette postali condivise i nomi info@dominio1 e info@dominio2.</span><span class="sxs-lookup"><span data-stu-id="67e38-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="67e38-109">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="67e38-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="67e38-110">Usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67e38-110">Use Windows PowerShell.</span></span> <span data-ttu-id="67e38-111">Per istruzioni, vedere questo post di Blog: [creare cassette postali condivise con lo stesso alias in domini diversi](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="67e38-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="67e38-112">Denominare la seconda cassetta postale condivisa qualcosa di diverso dall'inizio per aggirare l'errore.</span><span class="sxs-lookup"><span data-stu-id="67e38-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="67e38-113">Quindi, nell'interfaccia di amministrazione, rinominare la cassetta postale condivisa in quello che si vuole che sia.</span><span class="sxs-lookup"><span data-stu-id="67e38-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="67e38-114">Errore relativo all'utilizzo di autorizzazioni di invio quando si utilizza una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="67e38-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="67e38-115">Se è stata creata una cassetta postale condivisa e quindi si tenta di inviare un messaggio, è possibile che venga visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="67e38-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="67e38-116">**Non è stato possibile inviare il messaggio. Non si dispone dell'autorizzazione per l'invio del messaggio per conto dell'utente specificato.**</span><span class="sxs-lookup"><span data-stu-id="67e38-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="67e38-117">Questo messaggio viene visualizzato quando si verifica un problema di latenza della replica in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67e38-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="67e38-118">Se le informazioni sulla nuova cassetta postale condivisa (o aggiunta di un utente) vengono replicate in tutti i Data Center, il testo dovrebbe scomparire tra un'ora.</span><span class="sxs-lookup"><span data-stu-id="67e38-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="67e38-119">Attendere un'ora e quindi riprovare per inviare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="67e38-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="67e38-120">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="67e38-120">Related articles</span></span>

[<span data-ttu-id="67e38-121">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="67e38-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="67e38-122">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="67e38-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="67e38-123">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="67e38-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="67e38-124">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="67e38-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="67e38-125">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="67e38-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

