---
title: Configurazione dell'utilità di Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Configurazione dell'utilità di Microsoft 365.
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362547"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="b1690-103">Configurazione del pianificatore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1690-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="b1690-104">Per configurare l'utilità di Microsoft 365, di seguito sono riportati i prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="b1690-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="b1690-105">Cosa serve?</span><span class="sxs-lookup"><span data-stu-id="b1690-105">What do I need?</span></span> | <span data-ttu-id="b1690-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1690-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="b1690-107">Cortana cassetta postale</span><span class="sxs-lookup"><span data-stu-id="b1690-107">Cortana mailbox</span></span> |<span data-ttu-id="b1690-108">Gli amministratori tenant dovranno impostare una cassetta postale da utilizzare come cassetta postale "Cortana" (ovvero, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="b1690-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="b1690-109">Cassetta postale di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1690-109">Exchange Online mailbox</span></span> |<span data-ttu-id="b1690-110">Gli utenti devono disporre di un Exchange Online di posta elettronica e calendario</span><span class="sxs-lookup"><span data-stu-id="b1690-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="b1690-111">Licenza dell'utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="b1690-111">Scheduler license</span></span> |<span data-ttu-id="b1690-112">Per informazioni sulle licenze e sui prezzi, vedere [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="b1690-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="b1690-113">Creare una cassetta postale per Cortana</span><span class="sxs-lookup"><span data-stu-id="b1690-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="b1690-114">Una Exchange nel tenant funge da cassetta postale Cortana per il tenant per inviare e ricevere messaggi di posta elettronica da Cortana.</span><span class="sxs-lookup"><span data-stu-id="b1690-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="b1690-115">Tutti i messaggi di posta elettronica Cortana vengono conservati nella cassetta postale Cortana tenant in base ai criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b1690-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="b1690-116">Utilizzare il interfaccia di amministrazione di Microsoft 365 per creare una cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="b1690-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="b1690-117">È consigliabile un criterio di conservazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b1690-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="b1690-118">Utilizzare il nome Cortana'indirizzo SMTP principale della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b1690-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="b1690-119">Nomi quali "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana. Scheduler@yourdomain.com' sono consigliati.</span><span class="sxs-lookup"><span data-stu-id="b1690-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="b1690-120">Designare la cassetta postale come Assistente utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="b1690-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="b1690-121">Dopo aver creato una cassetta postale univoca Cortana'Utilità di pianificazione, è necessario designare la cassetta postale per Microsoft 365 formalmente.</span><span class="sxs-lookup"><span data-stu-id="b1690-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="b1690-122">Dopo aver designato la Cortana dell'Utilità di pianificazione, sarà disponibile per pianificare le riunioni per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="b1690-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="b1690-123">Per designare la cassetta Cortana dell'Utilità di pianificazione, un amministratore autorizzato deve eseguire un comando di PowerShell su una riga.</span><span class="sxs-lookup"><span data-stu-id="b1690-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="b1690-124">Connessione per Microsoft 365 di esecuzione remota di PowerShell per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b1690-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="b1690-125">Eseguire il seguente script di PowerShell per designare la cassetta postale per l'utilità di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="b1690-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="b1690-126">Dopo aver eseguito questo comando "set" sulla cassetta postale dell'utilità di pianificazione di Cortana, viene impostato un nuovo "PersistedCapability" sulla cassetta postale per notare che questa cassetta postale è "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="b1690-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="b1690-127">Segui questi passaggi per connettere l'organizzazione a PowerShell se non l'hai fatto in precedenza: Connessione [a Microsoft 365 con PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b1690-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="b1690-128">Per individuare la cassetta postale dell'organizzazione attualmente impostata come assistente Cortana, eseguire la funzione get:</span><span class="sxs-lookup"><span data-stu-id="b1690-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="b1690-129">La cassetta postale dell'utilità di pianificazione potrebbe richiedere fino a due ore per completare il provisioning per impostare la funzionalità SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="b1690-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="b1690-130">Cassetta postale di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1690-130">Exchange Online mailbox</span></span>
<span data-ttu-id="b1690-131">Una licenza dell'utilità di pianificazione è un componente aggiuntivo Microsoft 365, che consente all'organizzatore della riunione di delegare le attività di pianificazione delle riunioni all'assistente Utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b1690-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="b1690-132">Per il funzionamento dell'Utilità di pianificazione, in genere Microsoft 365 licenza, gli organizzatori delle riunioni richiedono i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1690-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="b1690-133">Una cassetta postale designata come cassetta postale assistente utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="b1690-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="b1690-134">Licenza dell'utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="b1690-134">Scheduler license</span></span>
- <span data-ttu-id="b1690-135">Exchange Online cassetta postale e calendario</span><span class="sxs-lookup"><span data-stu-id="b1690-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="b1690-136">I partecipanti alla riunione non richiedono l'utilità di pianificazione o Microsoft 365 licenza.</span><span class="sxs-lookup"><span data-stu-id="b1690-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="b1690-137">Requisiti di licenza dell'utente finale dell'utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="b1690-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="b1690-138">Una licenza dell'Utilità di pianificazione richiede una delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1690-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="b1690-139">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="b1690-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="b1690-140">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="b1690-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="b1690-141">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="b1690-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="b1690-142">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="b1690-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="b1690-143">Exchange Online Licenza Piano 1 o Piano 2.</span><span class="sxs-lookup"><span data-stu-id="b1690-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="b1690-144">L'utilità di Microsoft 365 è disponibile solo in ambienti multi-tenant in tutto il mondo in inglese.</span><span class="sxs-lookup"><span data-stu-id="b1690-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="b1690-145">**L'utilità Microsoft 365** non è disponibile per gli utenti di:</span><span class="sxs-lookup"><span data-stu-id="b1690-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="b1690-146">Microsoft 365 gestito da 21Vianet in Cina</span><span class="sxs-lookup"><span data-stu-id="b1690-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="b1690-147">Microsoft 365 cloud tedesco che usa il trustee dei dati German Telekom</span><span class="sxs-lookup"><span data-stu-id="b1690-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="b1690-148">Cloud per enti pubblici GCC, consumer, GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="b1690-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="b1690-149">L'utilità di pianificazione supporta gli utenti in Germania la cui posizione dati non si trova nel datacenter tedesco.</span><span class="sxs-lookup"><span data-stu-id="b1690-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
