---
title: Configurare le impostazioni globali per le impostazioni dei collegamenti sicuri in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come visualizzare e configurare le impostazioni globali (l'elenco ' blocca gli URL seguenti ' e la protezione per le app di Office 365) per i collegamenti sicuri in Office 365 Advanced Threat Protection (ATP).
ms.openlocfilehash: 6ca18bfb555419a8f4a61b55715f328ed7da5e88
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328534"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="2819d-103">Configurare le impostazioni globali per i collegamenti sicuri in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="2819d-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="2819d-104">Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="2819d-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="2819d-105">Se si è un utente di casa che cerca informazioni su Safelinks in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="2819d-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2819d-106">Collegamenti attendibili è una funzionalità di [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora in cui si fa clic su verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="2819d-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="2819d-107">Per ulteriori informazioni, vedere [collegamenti sicuri in Office 365 ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="2819d-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="2819d-108">È possibile configurare la maggior parte delle impostazioni dei collegamenti sicuri nei criteri collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="2819d-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="2819d-109">Per istruzioni, vedere [configurare i criteri dei collegamenti sicuri in Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2819d-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="2819d-110">Tuttavia, i collegamenti sicuri utilizzano anche le impostazioni globali che si applicano a tutti gli utenti inclusi in tutti i criteri collegamenti sicuri attivi.</span><span class="sxs-lookup"><span data-stu-id="2819d-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="2819d-111">Queste aree delle impostazioni globali:</span><span class="sxs-lookup"><span data-stu-id="2819d-111">These global settings area:</span></span>

- <span data-ttu-id="2819d-112">**Blocca l'elenco degli URL seguenti** .</span><span class="sxs-lookup"><span data-stu-id="2819d-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="2819d-113">Per ulteriori informazioni, vedere [l'elenco "blocca gli URL seguenti" per i collegamenti sicuri](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="2819d-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="2819d-114">Protezione dei collegamenti sicuri per le app di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2819d-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="2819d-115">Per ulteriori informazioni, vedere [impostazioni dei collegamenti sicuri per le app di Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="2819d-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="2819d-116">È possibile configurare le impostazioni globali dei collegamenti sicuri nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi di Office 365 ATP).</span><span class="sxs-lookup"><span data-stu-id="2819d-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2819d-117">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="2819d-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2819d-118">Le funzionalità fornite dalle impostazioni globali per i collegamenti sicuri vengono applicate solo agli utenti inclusi nei criteri dei collegamenti sicuri attivi.</span><span class="sxs-lookup"><span data-stu-id="2819d-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="2819d-119">Non esiste alcun criterio di collegamenti sicuri incorporato o predefinito, pertanto è necessario creare almeno un criterio collegamenti sicuri affinché tali impostazioni globali siano attive.</span><span class="sxs-lookup"><span data-stu-id="2819d-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="2819d-120">Per istruzioni, vedere [configurare i criteri dei collegamenti sicuri in Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2819d-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="2819d-121">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2819d-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2819d-122">Per accedere direttamente alla pagina **collegamenti sicuri di ATP** , utilizzare <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="2819d-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="2819d-123">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2819d-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2819d-124">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2819d-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2819d-125">Per visualizzare e configurare le impostazioni globali per i collegamenti sicuri, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="2819d-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="2819d-126">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2819d-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="2819d-127">**Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="2819d-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="2819d-128">Per i valori consigliati per le impostazioni globali per i collegamenti sicuri, vedere [Safe Links Settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="2819d-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="2819d-129">Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="2819d-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="2819d-130">Le [nuove funzionalità vengono continuamente aggiunte al trifosfato di adenosina](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="2819d-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="2819d-131">Man mano che si aggiungono nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri dei collegamenti sicuri esistenti.</span><span class="sxs-lookup"><span data-stu-id="2819d-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="2819d-132">Configurare l'elenco "blocca gli URL seguenti" nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="2819d-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="2819d-133">Il **blocco l'elenco degli URL seguente** identifica i collegamenti che devono essere sempre bloccati dall'analisi dei collegamenti sicuri nelle app supportate.</span><span class="sxs-lookup"><span data-stu-id="2819d-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="2819d-134">Per ulteriori informazioni, vedere [l'elenco "blocca gli URL seguenti" per i collegamenti sicuri](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="2819d-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="2819d-135">Nel centro sicurezza & conformità, accedere a collegamenti sicuri ATP per i criteri di **gestione delle minacce** \> **Policy** \> **ATP Safe Links**e quindi fare clic su **Impostazioni globali**.</span><span class="sxs-lookup"><span data-stu-id="2819d-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="2819d-136">Nel **criterio collegamenti sicuri per l'organizzazione** è possibile volare fuori che viene visualizzato, passare alla casella **blocca gli URL seguenti** .</span><span class="sxs-lookup"><span data-stu-id="2819d-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="2819d-137">Configurare una o più voci come descritto in [sintassi voce per l'elenco "blocca gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="2819d-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="2819d-138">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2819d-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="2819d-139">Configurare l'elenco "blocca gli URL seguenti" in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2819d-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="2819d-140">Per informazioni dettagliate sulla sintassi delle voci, vedere la [sintassi della voce per l'elenco "blocca gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="2819d-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="2819d-141">È possibile utilizzare il cmdlet **Get-AtpPolicyForO365** per visualizzare le voci esistenti nella proprietà _BlockURLs_ .</span><span class="sxs-lookup"><span data-stu-id="2819d-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="2819d-142">Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2819d-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="2819d-143">In questo esempio vengono aggiunte all'elenco le voci seguenti:</span><span class="sxs-lookup"><span data-stu-id="2819d-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="2819d-144">Bloccare il dominio, i sottodomini e i percorsi di fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="2819d-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="2819d-145">Bloccare la ricerca sottodominio, ma non il dominio padre o altri sottodomini in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="2819d-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="2819d-146">Per aggiungere o rimuovere valori senza alterare altre voci esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2819d-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="2819d-147">In questo esempio viene aggiunta una nuova voce per adatum.com e viene rimossa la voce per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="2819d-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="2819d-148">Configurare la protezione dei collegamenti sicuri per le app di Office 365 nel centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="2819d-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="2819d-149">Protezione dei collegamenti sicuri per le app di Office 365 si applica ai documenti nelle app desktop, mobili e Web di Office supportate.</span><span class="sxs-lookup"><span data-stu-id="2819d-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="2819d-150">Per ulteriori informazioni, vedere [impostazioni dei collegamenti sicuri per le app di Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="2819d-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="2819d-151">Nel centro sicurezza & conformità, accedere a collegamenti sicuri ATP per i criteri di **gestione delle minacce** \> **Policy** \> **ATP Safe Links**e quindi fare clic su **Impostazioni globali**.</span><span class="sxs-lookup"><span data-stu-id="2819d-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="2819d-152">Nel **criterio collegamenti sicuri per l'organizzazione** è possibile volare fuori, configurare le impostazioni seguenti nelle **impostazioni che si applicano al contenuto, ad eccezione della sezione posta elettronica** :</span><span class="sxs-lookup"><span data-stu-id="2819d-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="2819d-153">**Applicazioni di office 365**: verificare che l'interruttore sia a destra per abilitare i collegamenti sicuri per le app di Office 365 supportate: ![ attiva o disattiva l'attivazione ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="2819d-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="2819d-154">**Non monitorare quando gli utenti fanno clic su collegamenti sicuri**: spostare l'interruttore verso sinistra per tener conto dei clic degli utenti relativi agli URL bloccati nelle app di Office 365 supportate: disattivazione ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="2819d-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="2819d-155">**Non consentire agli utenti di fare clic su collegamenti sicuri con l'URL originale**: verificare che l'interruttore sia a destra per impedire agli utenti di fare clic sull'URL bloccato originale nelle app di Office 365 supportate: ![ Attiva/disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="2819d-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="2819d-156">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2819d-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="2819d-157">Configurare la protezione dei collegamenti sicuri per le app di Office 365 in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2819d-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="2819d-158">Se si preferisce utilizzare PowerShell per configurare la protezione dei collegamenti sicuri per le app di Office 365, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2819d-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="2819d-159">In questo esempio vengono configurate le impostazioni seguenti per la protezione dei collegamenti sicuri nelle app di Office 365:</span><span class="sxs-lookup"><span data-stu-id="2819d-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="2819d-160">I collegamenti sicuri per le app di Office 365 sono attivati (non si utilizza il parametro _EnableSafeLinksForO365Clients_ e il valore predefinito è $true).</span><span class="sxs-lookup"><span data-stu-id="2819d-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="2819d-161">Gli utenti che fanno clic su URL bloccati nelle app di Office 365 supportate vengono monitorati.</span><span class="sxs-lookup"><span data-stu-id="2819d-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="2819d-162">Agli utenti non è consentito fare clic sull'URL bloccato originale nelle app di Office 365 supportate (non si utilizza il parametro _AllowClickThrough_ e il valore predefinito è $false).</span><span class="sxs-lookup"><span data-stu-id="2819d-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="2819d-163">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="2819d-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2819d-164">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="2819d-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="2819d-165">Per verificare di aver configurato correttamente le impostazioni globali per i collegamenti sicuri ( **blocca l'elenco degli URL seguenti** e le impostazioni di protezione delle app di Office 365), eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2819d-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="2819d-166">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per i \> **Policy** \> **collegamenti sicuri ATP**, fare clic su **Impostazioni globali**e verificare le impostazioni nel volo che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2819d-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="2819d-167">In Exchange Online PowerShell o Exchange Online Protection PowerShell, eseguire il comando riportato di seguito e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2819d-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="2819d-168">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="2819d-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
