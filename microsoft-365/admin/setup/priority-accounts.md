---
title: Gestire e monitorare gli account con priorità
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
description: Monitorare i messaggi di posta elettronica non riusciti e ritardati inviati a o da account con un impatto aziendale elevato.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477614"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="b94ff-103">Gestire e monitorare gli account con priorità</span><span class="sxs-lookup"><span data-stu-id="b94ff-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="b94ff-104">In ogni organizzazione di Microsoft 365 ci sono persone essenziali, come dirigenti, dirigenti, responsabili o altri utenti che hanno accesso a informazioni sensibili, proprietarie o ad alta priorità.</span><span class="sxs-lookup"><span data-stu-id="b94ff-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="b94ff-105">Per aiutare l'organizzazione a proteggere questi account, ora puoi designare utenti specifici come account prioritari e sfruttare funzionalità specifiche dell'app che forniscono loro una protezione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b94ff-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="b94ff-106">In futuro, più app e funzionalità supporteranno gli account con priorità e, per iniziare, abbiamo annunciato due funzionalità: protezione degli **account** prioritari e monitoraggio del flusso **di posta premium.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="b94ff-107">**Protezione dell'account** con priorità: Microsoft Defender per Office 365 (in precedenza Office 365 Advanced Threat Protection) supporta gli account con priorità come tag che possono essere usati nei filtri in avvisi, report e indagini.</span><span class="sxs-lookup"><span data-stu-id="b94ff-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="b94ff-108">Per altre informazioni, vedere [Tag utente in Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="b94ff-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="b94ff-109">**Monitoraggio del flusso di** posta premium: un flusso di posta integro può essere fondamentale per il successo aziendale e i ritardi o gli errori di recapito possono avere un impatto negativo sull'azienda.</span><span class="sxs-lookup"><span data-stu-id="b94ff-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="b94ff-110">È possibile scegliere una soglia per i messaggi di posta elettronica non riusciti o ritardati, ricevere avvisi quando tale soglia viene superata e visualizzare un rapporto dei problemi di posta elettronica per gli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="b94ff-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="b94ff-111">Per ulteriori informazioni, vedere La segnalazione dei problemi di posta elettronica [per gli account con priorità nell'interfaccia di amministrazione di Exchange moderna.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="b94ff-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b94ff-112">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b94ff-112">Before you begin</span></span>

<span data-ttu-id="b94ff-113">La **funzionalità di protezione dell'account** Priority descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b94ff-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="b94ff-114">Microsoft Defender per Office 365 Piano 2, inclusi quelli con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="b94ff-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="b94ff-115">La **funzionalità di monitoraggio del** flusso di posta Premium descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b94ff-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="b94ff-116">L'organizzazione deve disporre di un numero di licenze di almeno 10.000, di uno dei prodotti o di una combinazione dei prodotti seguenti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b94ff-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="b94ff-117">Ad esempio, l'organizzazione può avere 3000 licenze di Office 365 E3 e 8500 Microsoft 365 E5, per un totale di 11.500 licenze dei prodotti idonei.</span><span class="sxs-lookup"><span data-stu-id="b94ff-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="b94ff-118">L’organizzazione deve avere almeno 50 utenti Exchange Online attivi al mese</span><span class="sxs-lookup"><span data-stu-id="b94ff-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="b94ff-119">È possibile monitorare fino a 250 account con priorità.</span><span class="sxs-lookup"><span data-stu-id="b94ff-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="b94ff-120">Aggiungere account con priorità dalla pagina Di installazione</span><span class="sxs-lookup"><span data-stu-id="b94ff-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="b94ff-121">Aggiungere account con priorità dalla **pagina Di installazione.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="b94ff-122">Passare all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="b94ff-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b94ff-123">Passare a **Configurazione**  >  **conoscenze organizzative** e scegliere **Visualizza** in **Monitora gli account più importanti.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="b94ff-124">Selezionare **Inizia o** **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="b94ff-125">Nel campo di ricerca **della** pagina Aggiungi account priorità digitare il nome o l'indirizzo di posta elettronica della persona che si desidera aggiungere all'elenco degli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="b94ff-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="b94ff-126">È inoltre possibile impostare la soglia di posta elettronica per i messaggi di posta elettronica non riusciti o ritardati e ottenere un rapporto settimanale dei problemi per gli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="b94ff-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="b94ff-127">Selezionare l'utente e scegliere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="b94ff-128">È inoltre possibile aggiungere account con priorità dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="b94ff-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="b94ff-129">Aggiungere account con priorità dalla pagina Utenti attivi</span><span class="sxs-lookup"><span data-stu-id="b94ff-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="b94ff-130">Aggiungere account con priorità dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="b94ff-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="b94ff-131">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b94ff-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b94ff-132">Go to **Users**  >  **Active users** and choose **...** at the top of the page.</span><span class="sxs-lookup"><span data-stu-id="b94ff-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="b94ff-133">Selezionare **Gestisci account con priorità.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="b94ff-134">Selezionare **Aggiungi account** e  nel campo di ricerca della pagina Aggiungi account priorità digitare il nome della persona che si desidera aggiungere all'elenco degli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="b94ff-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="b94ff-135">Selezionare l'utente e scegliere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="b94ff-136">Rimuovere un utente dall'elenco degli account con priorità</span><span class="sxs-lookup"><span data-stu-id="b94ff-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="b94ff-137">Passare all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="b94ff-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b94ff-138">Passare a **Configurazione**  >  **conoscenze organizzative** e scegliere **Visualizza** in **Monitora gli account più importanti.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="b94ff-139">Nella pagina **Monitora la maggior parte degli account** scegliere Account con **priorità** in Gestisci **questa funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="b94ff-140">Nella pagina **Account con** priorità selezionare l'utente o gli utenti che si desidera rimuovere dall'elenco e scegliere **Rimuovi account.**</span><span class="sxs-lookup"><span data-stu-id="b94ff-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b94ff-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b94ff-141">Related topics</span></span>

[<span data-ttu-id="b94ff-142">Uso degli account con priorità in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b94ff-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)