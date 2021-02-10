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
description: Gli amministratori possono imparare a visualizzare e configurare le impostazioni globali (l'elenco e la protezione "Blocca gli URL seguenti" per le app di Office 365) per i collegamenti sicuri in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165728"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f771d-103">Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f771d-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f771d-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f771d-104">**Applies to**</span></span>
- [<span data-ttu-id="f771d-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="f771d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="f771d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f771d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="f771d-107">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f771d-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="f771d-108">Per informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="f771d-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f771d-109">Collegamenti sicuri è una funzionalità di [Microsoft Defender per Office 365](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="f771d-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="f771d-110">Per altre informazioni, vedere [Collegamenti sicuri in Microsoft Defender per Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="f771d-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="f771d-111">La maggior parte delle impostazioni dei collegamenti sicuri viene configurata nei criteri Collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="f771d-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="f771d-112">Per istruzioni, vedere [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f771d-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="f771d-113">Tuttavia, collegamenti sicuri utilizza anche impostazioni globali che si applicano a tutti gli utenti inclusi nei criteri collegamenti sicuri attivi.</span><span class="sxs-lookup"><span data-stu-id="f771d-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="f771d-114">Queste aree di impostazioni globali:</span><span class="sxs-lookup"><span data-stu-id="f771d-114">These global settings area:</span></span>

- <span data-ttu-id="f771d-115">**L'elenco Blocca gli URL** seguenti.</span><span class="sxs-lookup"><span data-stu-id="f771d-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="f771d-116">Per ulteriori informazioni, vedere [l'elenco "Bloccare gli URL seguenti" per i collegamenti sicuri](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="f771d-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="f771d-117">Protezione collegamenti sicuri per le app di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f771d-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="f771d-118">Per altre informazioni, vedere [Impostazioni dei collegamenti sicuri per le app di Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="f771d-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="f771d-119">È possibile configurare le impostazioni globali dei collegamenti sicuri nel Centro sicurezza & e conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni ai componenti aggiuntivi di Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="f771d-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f771d-120">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f771d-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f771d-121">Le funzionalità fornite dalle impostazioni globali per i collegamenti sicuri vengono applicate solo agli utenti inclusi nei criteri collegamenti sicuri attivi.</span><span class="sxs-lookup"><span data-stu-id="f771d-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="f771d-122">Non è disponibile alcun criterio collegamenti sicuri predefinito o predefinito, pertanto è necessario creare almeno un criterio Collegamenti sicuri affinché queste impostazioni globali siano attive.</span><span class="sxs-lookup"><span data-stu-id="f771d-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="f771d-123">Per istruzioni, vedere [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f771d-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="f771d-124">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f771d-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f771d-125">Per passare direttamente alla **pagina Collegamenti sicuri,** utilizzare <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="f771d-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="f771d-126">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f771d-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f771d-127">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f771d-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f771d-128">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="f771d-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f771d-129">Per configurare le impostazioni globali per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f771d-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f771d-130">Per l'accesso in sola lettura alle impostazioni globali per i  collegamenti  sicuri, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f771d-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f771d-131">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f771d-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="f771d-132">**Note**:</span><span class="sxs-lookup"><span data-stu-id="f771d-132">**Notes**:</span></span>

  - <span data-ttu-id="f771d-133">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f771d-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f771d-134">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="f771d-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="f771d-135">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f771d-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="f771d-136">Per i valori consigliati per le impostazioni globali per i collegamenti sicuri, vedere [Impostazioni collegamenti sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="f771d-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="f771d-137">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="f771d-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="f771d-138">[Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="f771d-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="f771d-139">Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri collegamenti sicuri esistenti.</span><span class="sxs-lookup"><span data-stu-id="f771d-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="f771d-140">Configurare l'elenco "Blocca gli URL seguenti" nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="f771d-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="f771d-141">**L'elenco Blocca gli URL seguenti identifica** i collegamenti che devono essere sempre bloccati dall'analisi dei collegamenti sicuri nelle app supportate.</span><span class="sxs-lookup"><span data-stu-id="f771d-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="f771d-142">Per ulteriori informazioni, vedere l'elenco "Bloccare gli [URL seguenti" per Collegamenti sicuri.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="f771d-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="f771d-143">Nel Centro sicurezza & conformità, accedere **a** Collegamenti sicuri dei criteri di gestione delle minacce ATP e quindi fare clic \>  \> su **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="f771d-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="f771d-144">Nel riquadro **a comparsa dei criteri** collegamenti sicuri per l'organizzazione visualizzato passare alla casella Blocca gli **URL** seguenti.</span><span class="sxs-lookup"><span data-stu-id="f771d-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="f771d-145">Configurare una o più voci come descritto nella sintassi delle voci per [l'elenco "Blocca gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="f771d-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="f771d-146">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f771d-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="f771d-147">Configurare l'elenco "Blocca gli URL seguenti" in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f771d-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="f771d-148">Per informazioni dettagliate sulla sintassi delle voci, vedere La sintassi delle voci per [l'elenco "Bloccare gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="f771d-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="f771d-149">È possibile utilizzare il cmdlet **Get-AtpPolicyForO365** per visualizzare le voci esistenti nella _proprietà BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="f771d-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="f771d-150">Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la seguente sintassi in PowerShell di Exchange Online o PowerShell di Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="f771d-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="f771d-151">In questo esempio vengono aggiunte le voci seguenti all'elenco:</span><span class="sxs-lookup"><span data-stu-id="f771d-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="f771d-152">Bloccare il dominio, i sottodomini e i percorsi per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f771d-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="f771d-153">Bloccare la ricerca di sottodomini, ma non il dominio padre o altri sottodomini in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="f771d-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="f771d-154">Per aggiungere o rimuovere valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f771d-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="f771d-155">In questo esempio viene aggiunta una nuova voce per adatum.com e viene rimossa la voce per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f771d-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="f771d-156">Configurare la protezione dei collegamenti sicuri per le app di Office 365 nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="f771d-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="f771d-157">La protezione collegamenti sicuri per le app di Office 365 si applica ai documenti nelle app desktop, mobili e Web di Office supportate.</span><span class="sxs-lookup"><span data-stu-id="f771d-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="f771d-158">Per altre informazioni, vedere [Impostazioni dei collegamenti sicuri per le app di Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="f771d-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="f771d-159">Nel Centro sicurezza & conformità, accedere **a** Collegamenti sicuri dei criteri di gestione delle minacce ATP e quindi fare clic \>  \> su **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="f771d-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="f771d-160">Nel riquadro **a comparsa dei criteri** collegamenti sicuri per l'organizzazione, configurare le impostazioni seguenti nella sezione Impostazioni applicabili al contenuto ad eccezione della **posta** elettronica:</span><span class="sxs-lookup"><span data-stu-id="f771d-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="f771d-161">**Applicazioni di Office 365:** verificare che l'interruttore sia a destra per abilitare Collegamenti sicuri per le app di Office 365 ![ supportate: attivare o disattivare ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="f771d-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="f771d-162">**Non tenere traccia quando** gli utenti fanno clic su Collegamenti sicuri: spostare l'interruttore a sinistra per tenere traccia dei clic degli utenti correlati agli URL bloccati nelle app di Office 365 ![ supportate: disattivare ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="f771d-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="f771d-163">**Non** consentire agli utenti di fare clic su Collegamenti sicuri all'URL originale: verificare che l'interruttore sia a destra per impedire agli utenti di fare clic sull'URL bloccato originale nelle app di Office 365 supportate: ![ Attiva/Disattiva. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="f771d-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="f771d-164">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f771d-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="f771d-165">Configurare la protezione dei collegamenti sicuri per le app di Office 365 in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f771d-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="f771d-166">Se si preferisce utilizzare PowerShell per configurare la protezione dei collegamenti sicuri per le app di Office 365, utilizzare la sintassi seguente in PowerShell di Exchange Online o PowerShell di Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="f771d-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="f771d-167">In questo esempio vengono configurate le impostazioni seguenti per la protezione dei collegamenti sicuri nelle app di Office 365:</span><span class="sxs-lookup"><span data-stu-id="f771d-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="f771d-168">Collegamenti sicuri per le app di Office 365 è attivato (non viene utilizzato il parametro _EnableSafeLinksForO365Clients_ e il valore predefinito è $true).</span><span class="sxs-lookup"><span data-stu-id="f771d-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="f771d-169">I clic degli utenti correlati agli URL bloccati nelle app di Office 365 supportate vengono monitorati.</span><span class="sxs-lookup"><span data-stu-id="f771d-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="f771d-170">Agli utenti non è consentito fare clic sull'URL bloccato originale nelle app di Office 365 supportate (non viene utilizzato il parametro _AllowClickThrough_ e il valore predefinito è $false).</span><span class="sxs-lookup"><span data-stu-id="f771d-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="f771d-171">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="f771d-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f771d-172">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="f771d-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="f771d-173">Per verificare di aver configurato correttamente le impostazioni  globali per i collegamenti sicuri (l'elenco Blocca gli URL seguenti e le impostazioni di protezione delle app di Office 365), eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f771d-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="f771d-174">Nel Centro sicurezza & conformità, accedere  a Collegamenti sicuri \>  \> **ATP** dei criteri di gestione delle minacce, fare clic su Impostazioni globali e verificare le impostazioni nel riquadro a comparsa visualizzato.</span><span class="sxs-lookup"><span data-stu-id="f771d-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="f771d-175">In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, eseguire il comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="f771d-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="f771d-176">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="f771d-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
