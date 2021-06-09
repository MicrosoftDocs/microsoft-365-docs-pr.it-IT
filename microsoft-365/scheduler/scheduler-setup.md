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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809192"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="7840a-103">Configurazione dell'utilità di pianificazione per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7840a-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="7840a-104">Per configurare l'utilità di Microsoft 365, di seguito sono riportati i prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="7840a-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="7840a-105">**Cosa serve?**</span><span class="sxs-lookup"><span data-stu-id="7840a-105">**What do I need?**</span></span> |<span data-ttu-id="7840a-106">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7840a-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="7840a-107">Cassetta postale di Cortana</span><span class="sxs-lookup"><span data-stu-id="7840a-107">Cortana mailbox</span></span> |<span data-ttu-id="7840a-108">Gli amministratori tenant dovranno impostare una cassetta postale da utilizzare come cassetta postale "Cortana" (ovvero, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="7840a-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="7840a-109">Cassetta postale di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7840a-109">Exchange Online mailbox</span></span> |<span data-ttu-id="7840a-110">Gli utenti devono disporre di un Exchange Online di posta elettronica e calendario</span><span class="sxs-lookup"><span data-stu-id="7840a-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="7840a-111">Licenza dell'utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="7840a-111">Scheduler license</span></span> |<span data-ttu-id="7840a-112">Per informazioni sulle licenze e sui prezzi, vedere [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="7840a-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="7840a-113">Creare una cassetta postale per Cortana</span><span class="sxs-lookup"><span data-stu-id="7840a-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="7840a-114">Una Exchange nel tenant funge da cassetta postale di Cortana per il tenant per inviare e ricevere messaggi di posta elettronica da e verso Cortana.</span><span class="sxs-lookup"><span data-stu-id="7840a-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="7840a-115">Tutti i messaggi di posta elettronica inviati a Cortana vengono conservati nella cassetta postale Cortana del tenant in base ai criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7840a-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="7840a-116">Utilizzare l'Microsoft 365 di amministrazione per creare una cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="7840a-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="7840a-117">È consigliabile un criterio di conservazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="7840a-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="7840a-118">Utilizzare il nome Cortana nell'indirizzo SMTP principale della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="7840a-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="7840a-119">Sono consigliati nomi quali "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana.Scheduler@yourdomain.com".</span><span class="sxs-lookup"><span data-stu-id="7840a-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="7840a-120">Designare la cassetta postale come Assistente utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="7840a-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="7840a-121">Dopo aver creato una cassetta postale univoca per L'utilità di pianificazione di Cortana, è necessario designare la cassetta postale per Microsoft 365 formalmente.</span><span class="sxs-lookup"><span data-stu-id="7840a-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="7840a-122">Dopo aver designato la cassetta postale di Cortana Scheduler, sarà disponibile per pianificare le riunioni per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7840a-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="7840a-123">Per designare la cassetta postale dell'utilità di pianificazione di Cortana, un amministratore autorizzato deve eseguire un comando di PowerShell su una riga.</span><span class="sxs-lookup"><span data-stu-id="7840a-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="7840a-124">Connessione per Microsoft 365 di esecuzione remota di PowerShell per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7840a-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="7840a-125">Eseguire il seguente script di PowerShell per designare la cassetta postale per l'utilità di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="7840a-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="7840a-126">Dopo aver eseguito questo comando "set" sulla cassetta postale dell'utilità di pianificazione di Cortana, viene impostato un nuovo "PersistedCapability" sulla cassetta postale per notare che questa cassetta postale è "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="7840a-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="7840a-127">Segui questi passaggi per connettere l'organizzazione a PowerShell se non l'hai fatto in precedenza: Connessione [a Microsoft 365 con PowerShell - Microsoft 365 Enterprise | Documenti Microsoft](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="7840a-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="7840a-128">Per individuare la cassetta postale dell'organizzazione attualmente impostata come assistente utilità di pianificazione di Cortana, esegui la funzione get:</span><span class="sxs-lookup"><span data-stu-id="7840a-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> <span data-ttu-id="7840a-129">La cassetta postale dell'utilità di pianificazione potrebbe richiedere fino a due ore per completare il provisioning per impostare la funzionalità SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="7840a-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="7840a-130">Cassetta postale di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7840a-130">Exchange Online mailbox</span></span>
<span data-ttu-id="7840a-131">L'utilità di pianificazione è un componente aggiuntivo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7840a-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="7840a-132">Gli organizzatori della riunione devono disporre di una Exchange Online e di un calendario per il funzionamento dell'Utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7840a-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="7840a-133">Requisiti di Exchange</span><span class="sxs-lookup"><span data-stu-id="7840a-133">Exchange requirements</span></span>

<span data-ttu-id="7840a-134">Oltre all'Utilità di pianificazione delle licenze, è necessario disporre di una delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="7840a-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="7840a-135">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="7840a-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="7840a-136">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="7840a-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="7840a-137">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="7840a-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="7840a-138">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="7840a-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="7840a-139">Exchange Online Licenza Piano 1 o Piano 2.</span><span class="sxs-lookup"><span data-stu-id="7840a-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="7840a-140">**L'utilità Microsoft 365** non è disponibile per gli utenti di Office 365 gestiti da 21Vianet in Cina.</span><span class="sxs-lookup"><span data-stu-id="7840a-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="7840a-141">Inoltre, non è disponibile per gli utenti di Microsoft 365 con il cloud tedesco che usa il trustee dei dati German Telekom.</span><span class="sxs-lookup"><span data-stu-id="7840a-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="7840a-142">È supportato per gli utenti in Germania il cui percorso dati non è incluso nel datacenter tedesco.</span><span class="sxs-lookup"><span data-stu-id="7840a-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="7840a-143">Questa caratteristica non è supportata per gli utenti di Government Cloud, inclusi GCC, Consumer, GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="7840a-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
