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
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233363"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="0ec43-103">Gestire e monitorare gli account con priorità</span><span class="sxs-lookup"><span data-stu-id="0ec43-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="0ec43-104">In ogni organizzazione di Microsoft 365 ci sono persone essenziali, come dirigenti, dirigenti, responsabili o altri utenti che hanno accesso a informazioni sensibili, proprietarie o ad alta priorità.</span><span class="sxs-lookup"><span data-stu-id="0ec43-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="0ec43-105">Per aiutare l'organizzazione a proteggere questi account, ora puoi designare utenti specifici come account prioritari e sfruttare funzionalità specifiche dell'app che forniscono loro una protezione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="0ec43-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="0ec43-106">In futuro, più app e funzionalità supporteranno gli account con priorità e, per iniziare, abbiamo annunciato due funzionalità: protezione degli **account** prioritari e monitoraggio del flusso **di posta premium.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="0ec43-107">**Protezione dell'account** con priorità: Microsoft Defender per Office 365 (in precedenza Office 365 Advanced Threat Protection) supporta gli account con priorità come tag che possono essere usati nei filtri in avvisi, report e indagini.</span><span class="sxs-lookup"><span data-stu-id="0ec43-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="0ec43-108">Per altre informazioni, vedere [Tag utente in Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)</span><span class="sxs-lookup"><span data-stu-id="0ec43-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags).</span></span>
- <span data-ttu-id="0ec43-109">**Monitoraggio del flusso di** posta premium: un flusso di posta integro può essere fondamentale per il successo aziendale e i ritardi o gli errori di recapito possono avere un impatto negativo sull'azienda.</span><span class="sxs-lookup"><span data-stu-id="0ec43-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="0ec43-110">È possibile scegliere una soglia per i messaggi di posta elettronica non riusciti o ritardati, ricevere avvisi quando tale soglia viene superata e visualizzare un rapporto dei problemi di posta elettronica per gli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="0ec43-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="0ec43-111">Per ulteriori informazioni, consultare il report Problemi di posta elettronica per gli [account con priorità nell'interfaccia di amministrazione di Exchange moderna](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="0ec43-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="0ec43-112">Per le procedure consigliate per la sicurezza degli account con priorità, vedere [Suggerimenti per la sicurezza per gli account con priorità.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="0ec43-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0ec43-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0ec43-113">Before you begin</span></span>

<span data-ttu-id="0ec43-114">La **funzionalità di protezione dell'account** Priority descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ec43-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="0ec43-115">Microsoft Defender per Office 365 Piano 2, inclusi quelli con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="0ec43-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="0ec43-116">La **funzionalità di monitoraggio del** flusso di posta Premium descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ec43-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="0ec43-117">L'organizzazione deve disporre di un numero di licenze di almeno 10.000, di uno dei prodotti o di una combinazione dei prodotti seguenti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0ec43-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="0ec43-118">Ad esempio, l'organizzazione può avere 3000 licenze di Office 365 E3 e 8500 Microsoft 365 E5, per un totale di 11.500 licenze dei prodotti idonei.</span><span class="sxs-lookup"><span data-stu-id="0ec43-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="0ec43-119">L’organizzazione deve avere almeno 50 utenti Exchange Online attivi al mese</span><span class="sxs-lookup"><span data-stu-id="0ec43-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec43-120">È possibile monitorare fino a 250 account con priorità.</span><span class="sxs-lookup"><span data-stu-id="0ec43-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="0ec43-121">Aggiungere account con priorità dalla pagina Di installazione</span><span class="sxs-lookup"><span data-stu-id="0ec43-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="0ec43-122">Aggiungere account con priorità dalla **pagina Di installazione.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="0ec43-123">Passare all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="0ec43-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0ec43-124">Passare a **Configurazione**  >  **conoscenze organizzative** e scegliere **Visualizza** in **Monitora gli account più importanti.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="0ec43-125">Selezionare **Inizia o** **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="0ec43-126">Nel campo di ricerca **della** pagina Aggiungi account priorità digitare il nome o l'indirizzo di posta elettronica della persona che si desidera aggiungere all'elenco degli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="0ec43-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="0ec43-127">È inoltre possibile impostare la soglia di posta elettronica per i messaggi di posta elettronica non riusciti o ritardati e ottenere un rapporto settimanale dei problemi per gli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="0ec43-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="0ec43-128">Selezionare l'utente e scegliere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="0ec43-129">È inoltre possibile aggiungere account con priorità dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="0ec43-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="0ec43-130">Aggiungere account con priorità dalla pagina Utenti attivi</span><span class="sxs-lookup"><span data-stu-id="0ec43-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="0ec43-131">Aggiungere account con priorità dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="0ec43-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="0ec43-132">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0ec43-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0ec43-133">Go to **Users**  >  **Active users** and choose **...** at the top of the page.</span><span class="sxs-lookup"><span data-stu-id="0ec43-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="0ec43-134">Selezionare **Gestisci account con priorità.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="0ec43-135">Selezionare **Aggiungi account** e  nel campo di ricerca della pagina Aggiungi account priorità digitare il nome della persona che si desidera aggiungere all'elenco degli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="0ec43-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="0ec43-136">Selezionare l'utente e scegliere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="0ec43-137">Rimuovere un utente dall'elenco degli account con priorità</span><span class="sxs-lookup"><span data-stu-id="0ec43-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="0ec43-138">Passare all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="0ec43-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0ec43-139">Passare a **Configurazione**  >  **conoscenze organizzative** e scegliere **Visualizza** in **Monitora gli account più importanti.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="0ec43-140">Nella pagina **Monitora la maggior parte degli account** scegliere Account con **priorità** in Gestisci **questa funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="0ec43-141">Nella pagina **Account con** priorità selezionare l'utente o gli utenti che si desidera rimuovere dall'elenco e scegliere **Rimuovi account.**</span><span class="sxs-lookup"><span data-stu-id="0ec43-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ec43-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0ec43-142">Related topics</span></span>

[<span data-ttu-id="0ec43-143">Uso degli account con priorità in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ec43-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)