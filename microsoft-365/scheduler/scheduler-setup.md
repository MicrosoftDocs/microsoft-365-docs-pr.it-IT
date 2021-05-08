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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286189"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="7e664-103">Configurazione dell'utilità di pianificazione per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7e664-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="7e664-104">Per configurare l'utilità di Microsoft 365, di seguito sono riportati i prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="7e664-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="7e664-105">**Cosa serve?**</span><span class="sxs-lookup"><span data-stu-id="7e664-105">**What do I need?**</span></span> |<span data-ttu-id="7e664-106">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7e664-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="7e664-107">Cassetta postale di Cortana</span><span class="sxs-lookup"><span data-stu-id="7e664-107">Cortana mailbox</span></span> |<span data-ttu-id="7e664-108">Gli amministratori tenant dovranno impostare una cassetta postale da utilizzare come cassetta postale "Cortana" (ovvero, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="7e664-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="7e664-109">Cassetta postale di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7e664-109">Exchange Online mailbox</span></span> |<span data-ttu-id="7e664-110">Gli utenti devono disporre di un Exchange Online di posta elettronica e calendario</span><span class="sxs-lookup"><span data-stu-id="7e664-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="7e664-111">Licenza dell'utilità di pianificazione</span><span class="sxs-lookup"><span data-stu-id="7e664-111">Scheduler license</span></span> |<span data-ttu-id="7e664-112">Per informazioni sulle licenze e sui prezzi, vedere [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="7e664-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="7e664-113">Creare una cassetta postale per Cortana</span><span class="sxs-lookup"><span data-stu-id="7e664-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="7e664-114">Una Exchange nel tenant funge da cassetta postale di Cortana per il tenant per inviare e ricevere messaggi di posta elettronica da e verso Cortana.</span><span class="sxs-lookup"><span data-stu-id="7e664-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="7e664-115">Tutti i messaggi di posta elettronica inviati a Cortana vengono conservati nella cassetta postale Cortana del tenant in base ai criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="7e664-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="7e664-116">Utilizzare l'Microsoft 365 di amministrazione per creare una nuova cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="7e664-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="7e664-117">È consigliabile un criterio di conservazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="7e664-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="7e664-118">Utilizzare il nome Cortana nell'indirizzo SMTP principale della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="7e664-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="7e664-119">Sono consigliati nomi quali "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana.Scheduler@yourdomain.com".</span><span class="sxs-lookup"><span data-stu-id="7e664-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="7e664-120">Contatta Microsoft (scheduler_m365@microsoft.com) per abilitare la cassetta postale di Cortana.</span><span class="sxs-lookup"><span data-stu-id="7e664-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7e664-121">È necessario contattare Microsoft per configurare la cassetta postale di Cortana per l'utilizzo del servizio Utilità di pianificazione tramite posta elettronica scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7e664-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="7e664-122">L'abilitazione della cassetta postale di Cortana può richiedere fino a due settimane.</span><span class="sxs-lookup"><span data-stu-id="7e664-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="7e664-123">Cassetta postale di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7e664-123">Exchange Online mailbox</span></span>
<span data-ttu-id="7e664-124">L'utilità di pianificazione è un componente aggiuntivo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e664-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="7e664-125">Gli organizzatori della riunione devono disporre di una Exchange Online e di un calendario per il funzionamento dell'Utilità di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7e664-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="7e664-126">Requisiti di Exchange</span><span class="sxs-lookup"><span data-stu-id="7e664-126">Exchange requirements</span></span>

<span data-ttu-id="7e664-127">Oltre all'Utilità di pianificazione delle licenze, è necessario disporre di una delle licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e664-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="7e664-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="7e664-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="7e664-129">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="7e664-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="7e664-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="7e664-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="7e664-131">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="7e664-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="7e664-132">Exchange Online Licenza Piano 1 o Piano 2.</span><span class="sxs-lookup"><span data-stu-id="7e664-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="7e664-133">**L'utilità Microsoft 365** non è disponibile per gli utenti di Office 365 gestiti da 21Vianet in Cina.</span><span class="sxs-lookup"><span data-stu-id="7e664-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="7e664-134">Inoltre, non è disponibile per gli utenti di Microsoft 365 con il cloud tedesco che usa il trustee dei dati German Telekom.</span><span class="sxs-lookup"><span data-stu-id="7e664-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="7e664-135">È supportato per gli utenti in Germania il cui percorso dati non è incluso nel datacenter tedesco.</span><span class="sxs-lookup"><span data-stu-id="7e664-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="7e664-136">Questa caratteristica non è supportata per gli utenti di Government Cloud, inclusi GCC, Consumer, GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="7e664-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
