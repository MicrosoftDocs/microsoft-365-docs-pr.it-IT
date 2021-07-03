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
description: Monitorare i messaggi di posta elettronica non riusciti e ritardati inviati a o da account che hanno un impatto aziendale elevato.
ms.openlocfilehash: 86e01e591823c94d8279f975ed7de24cc65776dc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286142"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="e00ba-103">Gestire e monitorare gli account con priorità</span><span class="sxs-lookup"><span data-stu-id="e00ba-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="e00ba-104">In ogni Microsoft 365, ci sono persone essenziali, come dirigenti, dirigenti, manager o altri utenti che hanno accesso a informazioni sensibili, proprietarie o ad alta priorità.</span><span class="sxs-lookup"><span data-stu-id="e00ba-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="e00ba-105">Per aiutare l'organizzazione a proteggere questi account, ora puoi designare utenti specifici come account prioritari e sfruttare funzionalità specifiche dell'app che forniscono loro una protezione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="e00ba-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="e00ba-106">In futuro, più app e funzionalità supporteranno gli account prioritari e, per iniziare, abbiamo annunciato due funzionalità: la protezione degli **account** prioritari e il monitoraggio del flusso **di posta premium.**</span><span class="sxs-lookup"><span data-stu-id="e00ba-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="e00ba-107">**Protezione dell'account** con priorità - Microsoft Defender per Office 365 (in precedenza Office 365 Advanced Threat Protection) supporta gli account di priorità come tag che possono essere utilizzati nei filtri in avvisi, report e indagini.</span><span class="sxs-lookup"><span data-stu-id="e00ba-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="e00ba-108">Per altre informazioni, vedere [Tag utente in Microsoft Defender per Office 365](../../security/office-365-security/user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="e00ba-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="e00ba-109">Una domanda naturale è: "Tutti gli utenti non sono una priorità?</span><span class="sxs-lookup"><span data-stu-id="e00ba-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="e00ba-110">Perché non designare tutti gli utenti come account di priorità?"</span><span class="sxs-lookup"><span data-stu-id="e00ba-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="e00ba-111">Sì, tutti gli utenti sono una priorità, ma la protezione dell'account con priorità offre i seguenti vantaggi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="e00ba-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="e00ba-112">**Euristica** aggiuntiva: l'analisi del flusso di posta nei datacenter Microsoft indica che i modelli di flusso di posta per i dirigenti aziendali sono diversi dal dipendente medio.</span><span class="sxs-lookup"><span data-stu-id="e00ba-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="e00ba-113">La protezione dell'account con priorità offre ulteriori euristiche specifiche per i dirigenti aziendali che non andranno a vantaggio di un dipendente normale.</span><span class="sxs-lookup"><span data-stu-id="e00ba-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="e00ba-114">**Visibilità aggiuntiva** nei report: in effetti, le informazioni per tutti gli utenti (o tutti gli utenti interessati) sono già disponibili negli avvisi, nei report e nelle indagini.</span><span class="sxs-lookup"><span data-stu-id="e00ba-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="e00ba-115">Il tag degli account di priorità come filtro consente di assegnare in modo specifico le indagini.</span><span class="sxs-lookup"><span data-stu-id="e00ba-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="e00ba-116">**Premium monitoraggio della posta Flow** - Un flusso di posta integro può essere fondamentale per il successo aziendale e i ritardi o gli errori di recapito possono avere un impatto negativo sull'azienda.</span><span class="sxs-lookup"><span data-stu-id="e00ba-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="e00ba-117">È possibile scegliere una soglia per i messaggi di posta elettronica non riusciti o ritardati, ricevere avvisi quando tale soglia viene superata e visualizzare un rapporto dei problemi di posta elettronica per gli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="e00ba-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="e00ba-118">Per ulteriori informazioni, vedere [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="e00ba-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="e00ba-119">Per le procedure consigliate per la sicurezza per gli account con priorità, vedere [Suggerimenti per la sicurezza per gli account con priorità.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="e00ba-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e00ba-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e00ba-120">Before you begin</span></span>

<span data-ttu-id="e00ba-121">La **funzionalità di protezione degli account** priority descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e00ba-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="e00ba-122">Microsoft Defender per Office 365 Piano 2, inclusi quelli con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="e00ba-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="e00ba-123">La **Premium di monitoraggio** Flow posta elettronica descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e00ba-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="e00ba-124">L'organizzazione deve disporre di un numero di licenze di almeno 5.000, da uno dei prodotti o da una combinazione dei seguenti prodotti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e00ba-124">Your organization needs to have a license count of at least 5,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="e00ba-125">Ad esempio, l'organizzazione può avere 3.000 licenze di Office 365 E3 e 2.500 Microsoft 365 E5, per un totale di 5.500 licenze dei prodotti idonei.</span><span class="sxs-lookup"><span data-stu-id="e00ba-125">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="e00ba-126">L’organizzazione deve avere almeno 50 utenti Exchange Online attivi al mese</span><span class="sxs-lookup"><span data-stu-id="e00ba-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="e00ba-127">È possibile monitorare fino a 250 account con priorità.</span><span class="sxs-lookup"><span data-stu-id="e00ba-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="e00ba-128">Quando si applica la protezione dell'account con priorità a una cassetta postale, è consigliabile applicare la protezione dell'account con priorità anche agli utenti che hanno accesso alla cassetta postale (ad esempio, il CEO e l'assistente esecutivo del CEO che gestisce il calendario del CEO).</span><span class="sxs-lookup"><span data-stu-id="e00ba-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="e00ba-129">Aggiungere account con priorità dalla pagina Installazione</span><span class="sxs-lookup"><span data-stu-id="e00ba-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="e00ba-130">Aggiungere account di priorità dalla **pagina Installazione**.</span><span class="sxs-lookup"><span data-stu-id="e00ba-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="e00ba-131">Passare al interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="e00ba-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="e00ba-132">Vai a **Configurazione**  >  **Conoscenza dell'organizzazione** e scegli **Visualizza** in **Monitora gli account più importanti.**</span><span class="sxs-lookup"><span data-stu-id="e00ba-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="e00ba-133">Selezionare **Informazioni di base** o **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="e00ba-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="e00ba-134">Nel **campo di** ricerca della pagina Aggiungi account priorità digitare il nome o l'indirizzo di posta elettronica della persona che si desidera aggiungere all'elenco degli account di priorità.</span><span class="sxs-lookup"><span data-stu-id="e00ba-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="e00ba-135">Puoi anche impostare la soglia della posta elettronica per i messaggi di posta elettronica non riusciti o ritardati e ottenere un rapporto settimanale dei problemi per gli account con priorità.</span><span class="sxs-lookup"><span data-stu-id="e00ba-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="e00ba-136">Selezionare l'utente e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e00ba-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="e00ba-137">È inoltre possibile aggiungere account con priorità dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="e00ba-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="e00ba-138">Aggiungere account con priorità dalla pagina Utenti attivi</span><span class="sxs-lookup"><span data-stu-id="e00ba-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="e00ba-139">Aggiungere account con priorità dalla pagina Utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="e00ba-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="e00ba-140">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e00ba-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="e00ba-141">Vai a **Utenti** Utenti attivi e seleziona i tre  >   punti (altre azioni) nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="e00ba-141">Go to **Users** > **Active users** and select the three dots (more actions) at the top of the page.</span></span> <span data-ttu-id="e00ba-142">Selezionare **Gestisci account con priorità**.</span><span class="sxs-lookup"><span data-stu-id="e00ba-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="e00ba-143">Selezionare **Aggiungi account** e  nel campo di ricerca della pagina Aggiungi account priorità digitare il nome della persona che si desidera aggiungere all'elenco degli account di priorità.</span><span class="sxs-lookup"><span data-stu-id="e00ba-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="e00ba-144">Selezionare l'utente e scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e00ba-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="e00ba-145">Rimuovere un utente dall'elenco degli account con priorità</span><span class="sxs-lookup"><span data-stu-id="e00ba-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="e00ba-146">Passare al interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="e00ba-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="e00ba-147">Vai a **Configurazione**  >  **Conoscenza dell'organizzazione** e scegli **Visualizza** in **Monitora gli account più importanti.**</span><span class="sxs-lookup"><span data-stu-id="e00ba-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="e00ba-148">Nella pagina **Monitora la maggior parte degli account** scegliere Account con **priorità** in Gestisci **questa funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="e00ba-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="e00ba-149">Nella pagina **Account di priorità** selezionare l'utente o gli utenti che si desidera rimuovere dall'elenco e scegliere Rimuovi **account.**</span><span class="sxs-lookup"><span data-stu-id="e00ba-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e00ba-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e00ba-150">Related topics</span></span>

[<span data-ttu-id="e00ba-151">Utilizzo di account con priorità in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e00ba-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
