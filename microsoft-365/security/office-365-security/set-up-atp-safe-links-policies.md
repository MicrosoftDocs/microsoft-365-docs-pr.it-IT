---
title: Configurare i criteri per i collegamenti sicuri in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come visualizzare, creare, modificare ed eliminare i criteri per i collegamenti sicuri e le impostazioni dei collegamenti sicuri globali in Microsoft Defender per Office 365.
ms.openlocfilehash: 8a6d8a7ad567b658f04cb0b28800d4edbc33ec67
ms.sourcegitcommit: f81ca61f74f11a7436a6172538c3bda81b484d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675242"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e731d-103">Configurare i criteri per i collegamenti sicuri in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="e731d-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="e731d-104">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="e731d-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="e731d-105">Se si è un utente di casa che cerca informazioni su Safelinks in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="e731d-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="e731d-106">Collegamenti attendibili è una funzionalità di [Microsoft Defender per Office 365](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora in cui si fa clic su verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="e731d-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="e731d-107">Per ulteriori informazioni, vedere [collegamenti sicuri in Microsoft Defender per Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="e731d-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="e731d-108">Non esiste alcun criterio di collegamenti sicuri incorporato o predefinito.</span><span class="sxs-lookup"><span data-stu-id="e731d-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="e731d-109">Per ottenere l'analisi dei collegamenti sicuri degli URL, è necessario creare uno o più criteri per i collegamenti sicuri, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e731d-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="e731d-110">È possibile configurare le impostazioni globali per la protezione di collegamenti sicuri **all'esterno** dei criteri collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-110">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="e731d-111">Per istruzioni, vedere [configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="e731d-111">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="e731d-112">È possibile configurare i criteri per i collegamenti sicuri nel centro sicurezza & conformità o in PowerShell (Exchange Online PowerShell per organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online, ma con gli abbonamenti del componente aggiuntivo Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="e731d-112">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="e731d-113">Gli elementi di base di un criterio collegamenti sicuri sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e731d-113">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="e731d-114">**Il criterio collegamenti sicuri**: attiva la protezione dei collegamenti sicuri, attiva l'analisi degli URL in tempo reale, specifica se attendere che l'analisi in tempo reale venga completata prima di recapitare il messaggio, attivare la ricerca per i messaggi interni, specificare se tenere presenti gli scatti degli utenti sugli URL e specificare se consentire agli utenti di fare clic su trogolo all'URL originale.</span><span class="sxs-lookup"><span data-stu-id="e731d-114">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="e731d-115">**La regola per i collegamenti sicuri**: specifica i filtri priorità e destinatario (a chi si applica il criterio).</span><span class="sxs-lookup"><span data-stu-id="e731d-115">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="e731d-116">La differenza tra questi due elementi non è ovvia quando si gestiscono le politiche dei collegamenti sicuri nel centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="e731d-116">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e731d-117">Quando si crea un criterio per i collegamenti sicuri, si sta effettivamente creando una regola per i collegamenti sicuri e il criterio collegamenti sicuri associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="e731d-117">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="e731d-118">Quando si modifica un criterio per i collegamenti sicuri, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola dei collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-118">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="e731d-119">Tutte le altre impostazioni modificano il criterio collegamenti sicuri associato.</span><span class="sxs-lookup"><span data-stu-id="e731d-119">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="e731d-120">Quando si rimuove un criterio per i collegamenti sicuri, la regola collegamenti sicuri e i criteri collegamenti sicuri associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="e731d-120">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="e731d-121">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="e731d-121">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="e731d-122">Per ulteriori informazioni, vedere la sezione [use Exchange Online PowerShell or standalone EOP PowerShell per configurare i criteri dei collegamenti sicuri](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e731d-122">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e731d-123">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="e731d-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e731d-124">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e731d-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e731d-125">Per passare direttamente alla pagina **collegamenti sicuri** , utilizzare <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="e731d-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="e731d-126">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e731d-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e731d-127">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e731d-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e731d-128">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="e731d-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e731d-129">Per creare, modificare ed eliminare i criteri per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="e731d-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e731d-130">Per l'accesso in sola lettura ai criteri per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **lettore globale** o lettore di **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="e731d-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e731d-131">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e731d-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e731d-132">**Note**:</span><span class="sxs-lookup"><span data-stu-id="e731d-132">**Notes**:</span></span>

  - <span data-ttu-id="e731d-133">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e731d-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e731d-134">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e731d-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="e731d-135">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e731d-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e731d-136">Per le impostazioni consigliate per i criteri collegamenti sicuri, vedere [impostazioni dei criteri collegamenti sicuri](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="e731d-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="e731d-137">Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="e731d-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="e731d-138">Le [nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="e731d-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="e731d-139">Man mano che si aggiungono nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri dei collegamenti sicuri esistenti.</span><span class="sxs-lookup"><span data-stu-id="e731d-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="e731d-140">Utilizzare il Centro sicurezza & conformità per creare i criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="e731d-141">La creazione di un criterio collegamenti sicuri personalizzato nel centro sicurezza & conformità crea la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="e731d-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="e731d-142">Nel centro sicurezza & conformità, accedere a  \>  \> **collegamenti sicuri ATP** per i criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="e731d-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e731d-143">Nella pagina **collegamenti sicuri** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e731d-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="e731d-144">Verrà visualizzata la procedura guidata **nuovo criterio collegamenti sicuri** .</span><span class="sxs-lookup"><span data-stu-id="e731d-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="e731d-145">Nella pagina **Name Your Policy** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e731d-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="e731d-146">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="e731d-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="e731d-147">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="e731d-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="e731d-148">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e731d-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="e731d-149">Nella pagina **Impostazioni** che viene visualizzata, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e731d-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e731d-150">**Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi**: selezionare Attiva per abilitare la protezione dei collegamenti sicuri per i collegamenti nei **messaggi di posta** elettronica.</span><span class="sxs-lookup"><span data-stu-id="e731d-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="e731d-151">**Selezionare l'azione per gli URL sconosciuti o potenzialmente dannosi all'interno di Microsoft teams** **: selezionare Attiva** per abilitare la protezione dei collegamenti sicuri per i collegamenti nei team.</span><span class="sxs-lookup"><span data-stu-id="e731d-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="e731d-152">**Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file**: selezionare questa impostazione per abilitare l'analisi in tempo reale dei collegamenti nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e731d-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="e731d-153">**Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio**: selezionare questa impostazione per attendere il completamento dell'analisi degli URL in tempo reale prima di recapitare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e731d-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="e731d-154">**Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**: selezionare questa impostazione per applicare il criterio collegamenti sicuri ai messaggi tra i mittenti interni e i destinatari interni.</span><span class="sxs-lookup"><span data-stu-id="e731d-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="e731d-155">**Non tenere traccia dei clic degli utenti**: lasciare questa impostazione deselezionata per abilitare l'utente di verifica facendo clic sugli URL nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e731d-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="e731d-156">**Non consentire agli utenti di fare clic sull'URL originale**: selezionare questa impostazione per impedire agli utenti di fare clic sull'URL originale nelle [pagine di avviso](atp-safe-links.md#warning-pages-from-safe-links).</span><span class="sxs-lookup"><span data-stu-id="e731d-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="e731d-157">**Non riscrivere gli URL seguenti**: consente di accedere agli URL specificati che altrimenti verrebbero bloccati da collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="e731d-158">Nella casella digitare l'URL o il valore desiderato e quindi fare clic su</span><span class="sxs-lookup"><span data-stu-id="e731d-158">In the box, type the URL or value that you want, and then click</span></span> ![Icona Aggiungi pulsante](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="e731d-160">.</span><span class="sxs-lookup"><span data-stu-id="e731d-160">.</span></span>

     <span data-ttu-id="e731d-161">Per rimuovere una voce esistente, selezionarla e fare clic su</span><span class="sxs-lookup"><span data-stu-id="e731d-161">To remove an existing entry, select it and then click</span></span> ![Icona pulsante Elimina](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="e731d-163">.</span><span class="sxs-lookup"><span data-stu-id="e731d-163">.</span></span>

     <span data-ttu-id="e731d-164">Per la sintassi delle voci, vedere [la sintassi della voce per l'elenco "non riscrivere gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="e731d-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="e731d-165">Per informazioni dettagliate su queste impostazioni, vedere [impostazioni dei collegamenti sicuri per i messaggi di posta elettronica](atp-safe-links.md#safe-links-settings-for-email-messages) e [le impostazioni dei collegamenti sicuri per Microsoft teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="e731d-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="e731d-166">Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri standard e rigorosi, vedere [Safe Links Policy Settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="e731d-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="e731d-167">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e731d-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="e731d-168">Nella pagina **applicata alla** pagina che viene visualizzata, identificare i destinatari interni ai quali si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="e731d-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="e731d-169">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e731d-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="e731d-170">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="e731d-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="e731d-171">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="e731d-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="e731d-172">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="e731d-172">Click **Add a condition**.</span></span> <span data-ttu-id="e731d-173">Nell'elenco a discesa che viene visualizzato, selezionare una condizione in **applicato se**:</span><span class="sxs-lookup"><span data-stu-id="e731d-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="e731d-174">**Il destinatario è**: consente di specificare una o più cassette postali, utenti di posta elettronica o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e731d-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="e731d-175">**Il destinatario è un membro di**: consente di specificare uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e731d-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="e731d-176">**Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e731d-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="e731d-177">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con una **qualsiasi di queste** caselle.</span><span class="sxs-lookup"><span data-stu-id="e731d-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="e731d-178">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="e731d-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="e731d-179">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e731d-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="e731d-180">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="e731d-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="e731d-181">Per rimuovere singole voci, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sul valore.</span><span class="sxs-lookup"><span data-stu-id="e731d-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="e731d-182">Per rimuovere l'intera condizione, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sulla condizione.</span><span class="sxs-lookup"><span data-stu-id="e731d-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="e731d-183">Per aggiungere una condizione aggiuntiva, fare clic su **Aggiungi condizione** e selezionare un valore restante in **applicato se**.</span><span class="sxs-lookup"><span data-stu-id="e731d-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="e731d-184">Per aggiungere eccezioni, fare clic su **Aggiungi condizione** e selezionare un'eccezione in **except if**.</span><span class="sxs-lookup"><span data-stu-id="e731d-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="e731d-185">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="e731d-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="e731d-186">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e731d-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="e731d-187">Nella pagina **Verifica le impostazioni** che viene visualizzata, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e731d-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="e731d-188">È possibile fare clic su **modifica** su ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="e731d-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="e731d-189">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e731d-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="e731d-190">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="e731d-191">Nel centro sicurezza & conformità, accedere a  \>  \> **collegamenti sicuri ATP** per i criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="e731d-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e731d-192">Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="e731d-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="e731d-193">I dettagli del criterio vengono visualizzati in un volo</span><span class="sxs-lookup"><span data-stu-id="e731d-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="e731d-194">Utilizzare il Centro sicurezza & conformità per modificare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="e731d-195">Nel centro sicurezza & conformità, accedere a  \>  \> **collegamenti sicuri ATP** per i criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="e731d-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e731d-196">Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="e731d-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e731d-197">Nei dettagli del criterio, fare clic su **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="e731d-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="e731d-198">Le impostazioni disponibili nel volo visualizzato sono identiche a quelle descritte nella sezione [use the Security & Compliance Center to create Safe Links Policies](#use-the-security--compliance-center-to-create-safe-links-policies) .</span><span class="sxs-lookup"><span data-stu-id="e731d-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="e731d-199">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e731d-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="e731d-200">Abilitare o disabilitare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="e731d-201">Nel centro sicurezza & conformità, accedere a  \>  \> **collegamenti sicuri ATP** per i criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="e731d-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e731d-202">Si noti il valore nella colonna **stato** :</span><span class="sxs-lookup"><span data-stu-id="e731d-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="e731d-203">Spostare l'interruttore a sinistra per disabilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="e731d-203">Move the toggle to the left to disable the policy:</span></span> ![Disattiva criterio](../../media/scc-toggle-off.png)<span data-ttu-id="e731d-205">.</span><span class="sxs-lookup"><span data-stu-id="e731d-205">.</span></span>

   - <span data-ttu-id="e731d-206">Spostare l'interruttore a destra per abilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="e731d-206">Move the toggle to the right to enable the policy:</span></span> ![Attiva il criterio](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="e731d-208">.</span><span class="sxs-lookup"><span data-stu-id="e731d-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="e731d-209">Impostare la priorità dei criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="e731d-210">Per impostazione predefinita, ai criteri collegamenti sicuri viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (le politiche più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="e731d-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="e731d-211">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="e731d-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="e731d-212">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="e731d-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="e731d-213">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="e731d-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="e731d-214">I criteri collegamenti sicuri vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).</span><span class="sxs-lookup"><span data-stu-id="e731d-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="e731d-215">**Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità dei criteri collegamenti sicuri dopo averlo creato.</span><span class="sxs-lookup"><span data-stu-id="e731d-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="e731d-216">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola per i collegamenti sicuri (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="e731d-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="e731d-217">Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="e731d-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="e731d-218">Nel centro sicurezza & conformità, accedere a  \>  \> **collegamenti sicuri ATP** per i criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="e731d-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e731d-219">Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="e731d-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e731d-220">Nei dettagli dei criteri volare che viene visualizzato, fare clic sul pulsante priorità disponibile:</span><span class="sxs-lookup"><span data-stu-id="e731d-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="e731d-221">Il criterio collegamenti sicuri con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="e731d-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="e731d-222">Il criterio collegamenti sicuri con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="e731d-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="e731d-223">Se si dispone di tre o più criteri per i collegamenti sicuri, i criteri tra i valori di priorità più alti e quelli più bassi sono disponibili per i pulsanti **aumenta priorità** e **Riduci priorità** .</span><span class="sxs-lookup"><span data-stu-id="e731d-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="e731d-224">Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="e731d-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="e731d-225">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e731d-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="e731d-226">Utilizzare il Centro sicurezza & conformità per rimuovere i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="e731d-227">Nel centro sicurezza & conformità, accedere a  \>  \> **collegamenti sicuri ATP** per i criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="e731d-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="e731d-228">Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="e731d-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="e731d-229">Nei dettagli dei criteri che vengono visualizzati, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="e731d-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="e731d-230">Utilizzare PowerShell di Exchange Online o standalone EOP PowerShell per configurare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="e731d-231">Come descritto in precedenza, un criterio per i collegamenti sicuri è costituito da un criterio collegamenti sicuri e da una regola per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="e731d-232">In PowerShell, la differenza tra i criteri collegamenti sicuri e le regole per i collegamenti sicuri è evidente.</span><span class="sxs-lookup"><span data-stu-id="e731d-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="e731d-233">Per gestire i criteri collegamenti sicuri è possibile utilizzare i cmdlet **\* -SafeLinksPolicy** e gestire le regole per i collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="e731d-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="e731d-234">In PowerShell, creare innanzitutto il criterio collegamenti sicuri, quindi creare la regola collegamenti sicuri che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="e731d-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="e731d-235">In PowerShell, è possibile modificare le impostazioni nel criterio collegamenti sicuri e la regola collegamenti sicuri separatamente.</span><span class="sxs-lookup"><span data-stu-id="e731d-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="e731d-236">Quando si rimuove un criterio per i collegamenti sicuri da PowerShell, la regola relativa ai collegamenti sicuri corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="e731d-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="e731d-237">Utilizzo di PowerShell per creare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="e731d-238">La creazione di un criterio collegamenti sicuri in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="e731d-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="e731d-239">Creare il criterio collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="e731d-240">Creare la regola per i collegamenti sicuri che specifica il criterio collegamenti sicuri a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="e731d-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="e731d-241">**Note**:</span><span class="sxs-lookup"><span data-stu-id="e731d-241">**Notes**:</span></span>

- <span data-ttu-id="e731d-242">È possibile creare una nuova regola per i collegamenti sicuri e assegnare un criterio di collegamenti sicuri esistente e non associato.</span><span class="sxs-lookup"><span data-stu-id="e731d-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="e731d-243">Una regola per i collegamenti sicuri non può essere associata a più di un criterio collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="e731d-244">È possibile configurare le impostazioni seguenti sui nuovi criteri collegamenti sicuri in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="e731d-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="e731d-245">Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="e731d-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="e731d-246">Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="e731d-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="e731d-247">Un nuovo criterio collegamenti sicuri creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="e731d-248">Passaggio 1: utilizzare PowerShell per creare un criterio per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="e731d-249">Per creare un criterio per i collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="e731d-250">**Note**:</span><span class="sxs-lookup"><span data-stu-id="e731d-250">**Notes**:</span></span>

- <span data-ttu-id="e731d-251">Per informazioni dettagliate sulla sintassi delle voci da utilizzare per il parametro _DoNotRewriteUrls_ , vedere la [sintassi relativa alla voce per l'elenco "non riscrivere gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="e731d-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="e731d-252">Per ulteriori informazioni sulla sintassi che è possibile utilizzare per il parametro _DoNotRewriteUrls_ quando si modificano i criteri collegamenti sicuri esistenti utilizzando il cmdlet **set-SafeLinksPolicy** , vedere la sezione [Use PowerShell to Modify Safe Links Policies](#use-powershell-to-modify-safe-links-policies) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e731d-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="e731d-253">In questo esempio viene creato un criterio per i collegamenti sicuri denominato contoso all con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e731d-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="e731d-254">Attiva l'analisi e la riscrittura degli URL nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e731d-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="e731d-255">Attiva l'analisi degli URL nei team (toccare solo anteprima).</span><span class="sxs-lookup"><span data-stu-id="e731d-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="e731d-256">Attiva l'analisi in tempo reale degli URL cliccati, inclusi i collegamenti cliccati che puntano ai file.</span><span class="sxs-lookup"><span data-stu-id="e731d-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="e731d-257">Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e731d-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="e731d-258">Attiva l'analisi e la riscrittura degli URL per i messaggi interni.</span><span class="sxs-lookup"><span data-stu-id="e731d-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="e731d-259">Monitorare gli utenti che si riferiscono alla protezione dei collegamenti sicuri (non si utilizza il parametro _DoNotTrackUserClicks_ e il valore predefinito è $false, il che significa che i clic dell'utente vengono registrati).</span><span class="sxs-lookup"><span data-stu-id="e731d-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="e731d-260">Non consentire agli utenti di fare clic sull'URL originale.</span><span class="sxs-lookup"><span data-stu-id="e731d-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="e731d-261">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="e731d-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="e731d-262">Passaggio 2: utilizzare PowerShell per creare una regola per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="e731d-263">Per creare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="e731d-264">In questo esempio viene creata una regola per i collegamenti sicuri denominata Contoso all con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e731d-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="e731d-265">La regola è associata al criterio per i collegamenti sicuri denominato contoso all.</span><span class="sxs-lookup"><span data-stu-id="e731d-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="e731d-266">La regola viene applicata a tutti i destinatari del dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e731d-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="e731d-267">Poiché non si utilizza il parametro _Priority_ , viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="e731d-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="e731d-268">La regola è abilitata (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="e731d-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="e731d-269">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="e731d-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="e731d-270">Utilizzo di PowerShell per visualizzare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="e731d-271">Per visualizzare i criteri collegamenti sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e731d-272">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="e731d-273">In questo esempio vengono restituite informazioni dettagliate per il criterio collegamenti sicuri denominato contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="e731d-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="e731d-274">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="e731d-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="e731d-275">Utilizzo di PowerShell per visualizzare le regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="e731d-276">Per visualizzare le regole per i collegamenti sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="e731d-277">In questo esempio viene restituito un elenco riepilogativo di tutte le regole relative ai collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="e731d-278">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e731d-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="e731d-279">In questo esempio vengono restituite informazioni dettagliate per la regola per i collegamenti sicuri denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="e731d-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="e731d-280">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="e731d-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="e731d-281">Utilizzo di PowerShell per modificare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="e731d-282">Non è possibile rinominare un criterio di collegamenti sicuri in PowerShell (il cmdlet **set-SafeLinksPolicy** non ha un parametro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="e731d-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="e731d-283">Quando si rinomina un criterio per i collegamenti sicuri nel centro sicurezza & conformità, si sta solo rinominando la _regola_ dei collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="e731d-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="e731d-284">L'unica ulteriore considerazione per la modifica dei criteri collegamenti sicuri in PowerShell è la sintassi disponibile per il parametro _DoNotRewriteUrls_ (l' [elenco "non riscrivere gli URL seguenti"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="e731d-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="e731d-285">Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la sintassi seguente: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="e731d-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="e731d-286">Per aggiungere o rimuovere valori senza alterare altre voci esistenti, utilizzare la sintassi seguente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="e731d-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="e731d-287">In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio per i collegamenti sicuri come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri collegamenti sicuri](#step-1-use-powershell-to-create-a-safe-links-policy) più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e731d-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="e731d-288">Per modificare un criterio collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="e731d-289">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="e731d-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="e731d-290">Utilizzo di PowerShell per modificare le regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="e731d-291">L'unica impostazione che non è disponibile quando si modifica una regola per i collegamenti sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e731d-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="e731d-292">Per abilitare o disabilitare le regole per i collegamenti sicuri esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="e731d-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="e731d-293">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una regola per i collegamenti sicuri](#step-2-use-powershell-to-create-a-safe-links-rule) descritta in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e731d-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="e731d-294">Per modificare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="e731d-295">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="e731d-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="e731d-296">Utilizzo di PowerShell per abilitare o disabilitare le regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="e731d-297">L'abilitazione o disabilitazione di una regola per i collegamenti sicuri in PowerShell consente di abilitare o disabilitare l'intero criterio collegamenti sicuri (la regola collegamenti sicuri e il criterio collegamenti sicuri assegnati).</span><span class="sxs-lookup"><span data-stu-id="e731d-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="e731d-298">Per abilitare o disabilitare una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="e731d-299">In questo esempio viene disabilitata la regola per i collegamenti sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e731d-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e731d-300">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="e731d-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e731d-301">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="e731d-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="e731d-302">Utilizzo di PowerShell per impostare la priorità delle regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="e731d-303">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="e731d-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="e731d-304">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="e731d-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="e731d-305">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="e731d-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="e731d-306">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="e731d-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="e731d-307">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="e731d-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="e731d-308">Per impostare la priorità di una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="e731d-p123">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="e731d-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="e731d-311">**Nota**: per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="e731d-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="e731d-312">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="e731d-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="e731d-313">Utilizzo di PowerShell per rimuovere i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="e731d-314">Quando si utilizza PowerShell per rimuovere un criterio per i collegamenti sicuri, la regola relativa ai collegamenti sicuri corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="e731d-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="e731d-315">Per rimuovere un criterio collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="e731d-316">In questo esempio viene rimosso il criterio collegamenti sicuri denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e731d-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="e731d-317">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="e731d-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="e731d-318">Utilizzo di PowerShell per rimuovere le regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e731d-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="e731d-319">Quando si utilizza PowerShell per rimuovere una regola per i collegamenti sicuri, il criterio collegamenti sicuri corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="e731d-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="e731d-320">Per rimuovere una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e731d-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="e731d-321">In questo esempio viene rimossa la regola per i collegamenti sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="e731d-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="e731d-322">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="e731d-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="e731d-323">Per verificare che i collegamenti sicuri siano in grado di analizzare i messaggi, controllare i report disponibili di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="e731d-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="e731d-324">Per ulteriori informazioni, vedere [visualizzare i report per Defender per Office 365](view-reports-for-atp.md) e [usare Esplora risorse nel centro sicurezza & Compliance](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="e731d-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e731d-325">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="e731d-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="e731d-326">Per verificare che i criteri collegamenti sicuri siano stati creati, modificati o rimossi correttamente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e731d-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="e731d-327">Nel centro sicurezza & conformità, accedere a  \>  \> **collegamenti sicuri ATP** per i criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="e731d-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="e731d-328">Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="e731d-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="e731d-329">Per visualizzare ulteriori dettagli, selezionare il criterio dall'elenco e visualizzare i dettagli all'interno del volo.</span><span class="sxs-lookup"><span data-stu-id="e731d-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="e731d-330">In Exchange Online PowerShell o Exchange Online Protection PowerShell, sostituire \<Name\> con il nome del criterio o della regola, eseguire il comando riportato di seguito e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e731d-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
