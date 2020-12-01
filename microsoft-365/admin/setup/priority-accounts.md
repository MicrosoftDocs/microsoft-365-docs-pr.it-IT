---
title: Gestire e monitorare gli account prioritari
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Monitorare i messaggi di posta elettronica non riusciti e in ritardo inviati o ricevuti da account che hanno un impatto elevato sulle aziende.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477614"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="eb6b9-103">Gestire e monitorare gli account prioritari</span><span class="sxs-lookup"><span data-stu-id="eb6b9-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="eb6b9-104">In ogni organizzazione Microsoft 365 esistono persone indispensabili, come i dirigenti, i leader, i Manager o gli altri utenti che hanno accesso a informazioni sensibili, proprietarie o ad alta priorità.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="eb6b9-105">Per aiutare l'organizzazione a proteggere questi account, è ora possibile designare gli utenti specifici come account prioritari e sfruttare le funzionalità specifiche per le app che forniscono protezione supplementare.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="eb6b9-106">In futuro, altre app e funzionalità supporteranno gli account prioritari e, per iniziare, sono state annunciate due funzionalità: **protezione degli account prioritari** e **monitoraggio del flusso di posta Premium**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="eb6b9-107">**Protezione degli account prioritari** -Microsoft Defender per Office 365 (in precedenza Office 365 Advanced Threat Protection) supporta gli account prioritari come tag che possono essere utilizzati nei filtri in avvisi, rapporti ed indagini.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="eb6b9-108">Per ulteriori informazioni, vedere i [tag degli utenti in Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="eb6b9-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="eb6b9-109">**Monitoraggio del flusso di posta Premium** -il flusso di posta integro può essere fondamentale per il successo aziendale e i ritardi o gli errori di recapito possono avere un impatto negativo sull'azienda.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="eb6b9-110">È possibile scegliere una soglia per i messaggi di posta elettronica non riusciti o ritardati, ricevere avvisi al termine del superamento della soglia e visualizzare un report di problemi relativi alla posta per gli account prioritari.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="eb6b9-111">Per ulteriori informazioni, vedere [i problemi di posta elettronica per il rapporto account prioritari nell'interfaccia di amministrazione di Exchange moderna](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span><span class="sxs-lookup"><span data-stu-id="eb6b9-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="eb6b9-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="eb6b9-112">Before you begin</span></span>

<span data-ttu-id="eb6b9-113">La caratteristica di **protezione degli account prioritari** descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb6b9-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="eb6b9-114">Microsoft Defender per Office 365 piano 2, compresi quelli con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="eb6b9-115">La funzionalità di **monitoraggio del flusso di posta Premium** descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb6b9-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="eb6b9-116">L'organizzazione deve disporre di un numero di licenza di almeno 10.000, da uno o da una combinazione dei prodotti seguenti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="eb6b9-117">Ad esempio, l'organizzazione può avere 3000 licenze Office 365 E3 e 8500 Microsoft 365 E5, per un totale di 11.500 licenze dai prodotti di qualificazione.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="eb6b9-118">L'organizzazione deve disporre di almeno 50 utenti mensili di Exchange Online attivi.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="eb6b9-119">È possibile monitorare fino a 250 account prioritari.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="eb6b9-120">Aggiungere gli account prioritari dalla pagina di installazione</span><span class="sxs-lookup"><span data-stu-id="eb6b9-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="eb6b9-121">Aggiungere gli account prioritari dalla **pagina di installazione**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="eb6b9-122">Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="eb6b9-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eb6b9-123">Andare alla pagina relativa alla **configurazione**  >  **dell'organizzazione** e scegliere **Visualizza** in **Monitor gli account più importanti**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="eb6b9-124">Selezionare **inizia** o **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="eb6b9-125">Nel campo di ricerca della pagina **Aggiungi account di priorità** Digitare il nome o l'indirizzo di posta elettronica della persona che si desidera aggiungere all'elenco degli account prioritari.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="eb6b9-126">È inoltre possibile impostare la soglia di posta elettronica per i messaggi non riusciti o in ritardo e ottenere un rapporto settimanale dei problemi per gli account prioritari.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="eb6b9-127">Selezionare l'utente e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="eb6b9-128">È inoltre possibile aggiungere gli account prioritari dalla pagina utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="eb6b9-129">Aggiungere gli account prioritari dalla pagina utenti attivi</span><span class="sxs-lookup"><span data-stu-id="eb6b9-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="eb6b9-130">Aggiungere gli account prioritari dalla pagina utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="eb6b9-131">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eb6b9-132">Passare a **utenti**  >  **attivi** e scegliere **...** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="eb6b9-133">Selezionare **Gestisci account prioritari**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="eb6b9-134">Selezionare **Aggiungi account** e nella pagina **Aggiungi account di priorità** , nel campo di ricerca, digitare il nome della persona che si desidera aggiungere all'elenco degli account prioritari.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="eb6b9-135">Selezionare l'utente e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="eb6b9-136">Rimuovere un utente dall'elenco degli account prioritari</span><span class="sxs-lookup"><span data-stu-id="eb6b9-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="eb6b9-137">Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="eb6b9-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="eb6b9-138">Andare alla pagina relativa alla **configurazione**  >  **dell'organizzazione** e scegliere **Visualizza** in **Monitor gli account più importanti**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="eb6b9-139">Nella pagina **monitora gli account più** fare clic su **account prioritari** in **Gestisci questa funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="eb6b9-140">Nella pagina **account prioritari** selezionare l'utente o gli utenti che si desidera rimuovere dall'elenco e scegliere, rimuovere gli **account**.</span><span class="sxs-lookup"><span data-stu-id="eb6b9-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb6b9-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="eb6b9-141">Related topics</span></span>

[<span data-ttu-id="eb6b9-142">Utilizzo degli account prioritari in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb6b9-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)