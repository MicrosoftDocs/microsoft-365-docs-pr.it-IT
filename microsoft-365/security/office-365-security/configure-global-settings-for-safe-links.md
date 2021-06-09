---
title: Configurare le impostazioni globali per le impostazioni dei collegamenti sicuri in Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a visualizzare e configurare le impostazioni globali (l'elenco "Blocca gli URL seguenti" e la protezione per le app Office 365) per i collegamenti sicuri in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e77373657d3167ca8f5bafa544923ab3a2320ce
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821986"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cf8d5-103">Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="cf8d5-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cf8d5-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="cf8d5-104">**Applies to**</span></span>
- [<span data-ttu-id="cf8d5-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="cf8d5-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cf8d5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf8d5-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="cf8d5-107">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="cf8d5-108">Se si è un utente principale che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="cf8d5-109">Collegamenti sicuri è una funzionalità di [Microsoft Defender per Office 365 che](defender-for-office-365.md) fornisce l'analisi URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="cf8d5-110">Per altre informazioni, vedi [Collegamenti sicuri in Microsoft Defender per Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="cf8d5-111">La maggior parte delle impostazioni dei collegamenti sicuri viene configurata nei criteri Collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="cf8d5-112">Per istruzioni, vedi [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="cf8d5-113">Tuttavia, collegamenti sicuri utilizza anche le impostazioni globali seguenti configurate all'esterno dei criteri collegamenti sicuri stessi:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="cf8d5-114">**L'elenco Blocca gli URL seguenti.**</span><span class="sxs-lookup"><span data-stu-id="cf8d5-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="cf8d5-115">Questa impostazione si applica a tutti gli utenti inclusi nei criteri collegamenti sicuri attivi.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="cf8d5-116">Per ulteriori informazioni, vedere [l'elenco "Bloccare](safe-links.md#block-the-following-urls-list-for-safe-links) gli URL seguenti" per Collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="cf8d5-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="cf8d5-117">Protezione dei collegamenti sicuri per Office 365 app.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="cf8d5-118">Queste impostazioni si applicano a tutti gli utenti dell'organizzazione con licenza per Defender per Office 365, indipendentemente dal fatto che gli utenti siano inclusi o meno nei criteri collegamenti sicuri attivi.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="cf8d5-119">Per altre informazioni, vedi [Impostazioni dei collegamenti sicuri per Office 365 app](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="cf8d5-120">È possibile configurare le impostazioni globali dei collegamenti sicuri nel Centro sicurezza Microsoft 365 o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi di Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-120">You can configure the global Safe Links settings in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cf8d5-121">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="cf8d5-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cf8d5-122">Non è disponibile alcun criterio collegamenti sicuri predefinito o predefinito, quindi è necessario creare almeno un criterio Collegamenti sicuri affinché l'elenco Blocca gli **URL** seguenti sia attivo.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="cf8d5-123">Per istruzioni, vedi [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="cf8d5-124">Aprire il Centro sicurezza a <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-124">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="cf8d5-125">Per passare direttamente alla **pagina Collegamenti sicuri,** utilizzare <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="cf8d5-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="cf8d5-126">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cf8d5-127">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cf8d5-128">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cf8d5-129">Per configurare le impostazioni globali per i collegamenti sicuri, è necessario essere membri dei **gruppi di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="cf8d5-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="cf8d5-130">Per l'accesso in sola lettura alle impostazioni globali per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cf8d5-131">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="cf8d5-132">**Note**:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-132">**Notes**:</span></span>

  - <span data-ttu-id="cf8d5-133">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cf8d5-134">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="cf8d5-135">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="cf8d5-136">Per i valori consigliati per le impostazioni globali per i collegamenti sicuri, vedere [Safe Links settings.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="cf8d5-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="cf8d5-137">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="cf8d5-138">[Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="cf8d5-139">Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri collegamenti sicuri esistenti.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a><span data-ttu-id="cf8d5-140">Configurare l'elenco "Blocca gli URL seguenti" nel Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="cf8d5-140">Configure the "Block the following URLs" list in the security center</span></span>

<span data-ttu-id="cf8d5-141">**L'elenco Blocca gli URL** seguenti identifica i collegamenti che devono essere sempre bloccati dall'analisi dei collegamenti sicuri nelle app supportate.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="cf8d5-142">Per ulteriori informazioni, vedere [l'elenco "Bloccare gli URL seguenti" per Collegamenti sicuri.](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="cf8d5-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="cf8d5-143">Nel centro sicurezza passare a Criteri di collaborazione & **e-mail** & regole Criteri di minaccia \>  \>  \>  sezione \> **Collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-143">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="cf8d5-144">Nella pagina **Collegamenti sicuri** fare clic su **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="cf8d5-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="cf8d5-145">Nel riquadro **a comparsa Dei** collegamenti sicuri per l'organizzazione visualizzato passare alla casella Blocca gli **URL** seguenti.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="cf8d5-146">Configurare una o più voci come descritto in [Sintassi voce per l'elenco "Blocca gli URL seguenti".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="cf8d5-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="cf8d5-147">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="cf8d5-148">Configurare l'elenco "Blocca gli URL seguenti" in PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf8d5-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="cf8d5-149">Per informazioni dettagliate sulla sintassi delle voci, vedere [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="cf8d5-150">È possibile utilizzare il cmdlet **Get-AtpPolicyForO365** per visualizzare le voci esistenti nella _proprietà BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="cf8d5-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="cf8d5-151">Per aggiungere valori che sostituiranno eventuali voci esistenti, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="cf8d5-152">In questo esempio vengono aggiunte le voci seguenti all'elenco:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="cf8d5-153">Bloccare il dominio, i sottodomini e i percorsi per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="cf8d5-154">Bloccare la ricerca di sottodomini, ma non il dominio padre o altri sottodomini in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="cf8d5-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="cf8d5-155">Per aggiungere o rimuovere valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="cf8d5-156">In questo esempio viene aggiunta una nuova voce per adatum.com e viene rimossa la voce per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a><span data-ttu-id="cf8d5-157">Configurare la protezione dei collegamenti sicuri per Office 365 app nel Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="cf8d5-157">Configure Safe Links protection for Office 365 apps in the security center</span></span>

<span data-ttu-id="cf8d5-158">La protezione collegamenti sicuri per Office 365 app si applica ai documenti nelle app Office desktop, mobili e Web supportate.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="cf8d5-159">Per altre informazioni, vedi [Impostazioni dei collegamenti sicuri per Office 365 app](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="cf8d5-160">Nel centro sicurezza passare a Criteri di collaborazione & **e-mail** & regole Criteri di minaccia \>  \>  \>  sezione \> **Collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-160">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="cf8d5-161">Nella pagina **Collegamenti sicuri** fare clic su **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="cf8d5-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="cf8d5-162">Nel riquadro **a comparsa** Collegamenti sicuri per l'organizzazione visualizzato configurare le impostazioni seguenti nel Impostazioni che si applicano al contenuto **nelle** app Office 365 supportate:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="cf8d5-163">**Usa collegamenti sicuri nelle app Office 365**: verifica che l'interruttore sia a destra per abilitare Collegamenti sicuri per le app Office 365 supportate: ![ Attiva/disattiva ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="cf8d5-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="cf8d5-164">**Non tenere** traccia quando gli utenti fanno clic su collegamenti protetti nelle app di Office 365 : sposta l'interruttore a sinistra per tenere traccia dei clic degli utenti correlati agli URL bloccati nelle app Office 365 supportate: Disattiva ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="cf8d5-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="cf8d5-165">Non consentire agli utenti di fare clic sull'URL originale nelle app **di Office 365:** verificare che l'interruttore sia a destra per impedire agli utenti di fare clic sull'URL bloccato originale nelle app Office 365 supportate: Attiva/disattiva ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="cf8d5-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="cf8d5-166">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="cf8d5-167">Configurare la protezione dei collegamenti sicuri per Office 365 app in PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf8d5-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="cf8d5-168">Se si preferisce usare PowerShell per configurare la protezione dei collegamenti sicuri per le app Office 365, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="cf8d5-169">In questo esempio vengono configurate le impostazioni seguenti per la protezione dei collegamenti sicuri nelle Office 365 app:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="cf8d5-170">Collegamenti sicuri per Office 365 app è attivato (non viene utilizzato il parametro _EnableSafeLinksForO365Clients_ e il valore predefinito è $true).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="cf8d5-171">I clic degli utenti correlati agli URL bloccati nelle app Office 365 vengono monitorate.</span><span class="sxs-lookup"><span data-stu-id="cf8d5-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="cf8d5-172">Agli utenti non è consentito fare clic sull'URL bloccato originale nelle app Office 365 supportate (non viene utilizzato il parametro _AllowClickThrough_ e il valore predefinito è $false).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="cf8d5-173">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="cf8d5-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="cf8d5-174">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="cf8d5-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="cf8d5-175">Per verificare di aver configurato correttamente le impostazioni  globali per i collegamenti sicuri (l'elenco Blocca gli URL seguenti e le impostazioni di protezione delle app di Office 365), eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="cf8d5-176">Nel centro sicurezza passare **a** Criteri di collaborazione & posta elettronica & Regole Criteri di minaccia sezione Collegamenti sicuri fare clic su Impostazioni globali e verificare le impostazioni nel riquadro a comparsa \>  \>  \>  \>  \> visualizzato. </span><span class="sxs-lookup"><span data-stu-id="cf8d5-176">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="cf8d5-177">In Exchange Online PowerShell o Exchange Online Protection PowerShell, eseguire il comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="cf8d5-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="cf8d5-178">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="cf8d5-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
