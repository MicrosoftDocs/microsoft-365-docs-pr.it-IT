---
title: Risolvere i problemi relativi alle cassette postali condivise
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Potrebbero verificarsi errori durante la configurazione delle cassette postali condivise. Provare queste soluzioni se si verificano problemi con le cassette postali condivise.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706131"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="6dae4-104">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="6dae4-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="6dae4-105">Se vengono visualizzati messaggi di errore durante la creazione o l'utilizzo di una cassetta postale condivisa, provare queste possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="6dae4-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="6dae4-106">Errore durante la creazione di cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="6dae4-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="6dae4-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="6dae4-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="6dae4-108">Se viene visualizzato il messaggio di errore, l'indirizzo proxy "smtp:<shared mailbox name " è già utilizzato dagli indirizzi proxy o **\> LegacyExchangeDN di " \<name> ". Scegliere un altro indirizzo proxy** significa che si sta tentando di assegnare alla cassetta postale condivisa un nome già in uso.</span><span class="sxs-lookup"><span data-stu-id="6dae4-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="6dae4-109">Ad esempio, supponiamo di voler assegnare a due cassette postali condivise i nomi info@dominio1 e info@dominio2.</span><span class="sxs-lookup"><span data-stu-id="6dae4-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="6dae4-110">È possibile eseguire questa operazione in due modi:</span><span class="sxs-lookup"><span data-stu-id="6dae4-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="6dae4-111">Usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6dae4-111">Use Windows PowerShell.</span></span> <span data-ttu-id="6dae4-112">Vedere questo post di blog per istruzioni: [Creare cassette postali condivise con lo stesso alias in domini diversi](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="6dae4-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="6dae4-113">Assegnare alla seconda cassetta postale condivisa un nome diverso dall'inizio per aggirare l'errore.</span><span class="sxs-lookup"><span data-stu-id="6dae4-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="6dae4-114">Nell'interfaccia di amministrazione rinominare quindi la cassetta postale condivisa in base alle impostazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="6dae4-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="6dae4-115">Errore di non disporre delle autorizzazioni di invio quando si utilizza una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="6dae4-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="6dae4-116">Se è stata creata una cassetta postale condivisa e quindi si tenta di inviare un messaggio da essa, è possibile ottenere quanto seguente:</span><span class="sxs-lookup"><span data-stu-id="6dae4-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="6dae4-117">**Impossibile inviare il messaggio. Non si dispone dell'autorizzazione per inviare il messaggio per conto dell'utente specificato.**</span><span class="sxs-lookup"><span data-stu-id="6dae4-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="6dae4-118">Questo messaggio viene visualizzato quando Microsoft 365 si verifica un problema di latenza di replica.</span><span class="sxs-lookup"><span data-stu-id="6dae4-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="6dae4-119">Dovrebbe andare via tra circa un'ora, quando le informazioni sulla nuova cassetta postale condivisa (o sull'utente aggiunto) vengono replicate in tutti i data center.</span><span class="sxs-lookup"><span data-stu-id="6dae4-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="6dae4-120">Attendere un'ora e quindi riprovare a inviare un messaggio.</span><span class="sxs-lookup"><span data-stu-id="6dae4-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="6dae4-121">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="6dae4-121">Related content</span></span>

<span data-ttu-id="6dae4-122">[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6dae4-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="6dae4-123">[Creare una cassetta postale condivisa](create-a-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6dae4-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6dae4-124">[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6dae4-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6dae4-125">[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6dae4-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6dae4-126">[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6dae4-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

