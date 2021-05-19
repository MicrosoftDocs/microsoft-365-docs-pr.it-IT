---
title: Gestire le autorizzazioni e i blocchi nell'elenco tenant consentiti/bloccati
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a configurare gli elementi consentiti e i blocchi nell'elenco Consenti/Blocca tenant nel portale di sicurezza.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538964"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-103">Gestire l'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a5686-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a5686-104">**Applies to**</span></span>
- [<span data-ttu-id="a5686-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a5686-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a5686-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="a5686-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a5686-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5686-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="a5686-108">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a5686-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="a5686-109">Se l'organizzazione non dispone delle funzionalità di spoofing come descritto in questo articolo, vedere l'esperienza di gestione dello spoofing precedente in Gestire i mittenti contraffatti utilizzando i criteri di spoof intelligence e [spoof intelligence insight in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="a5686-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="a5686-110">Non è possibile configurare **gli** URL consentiti o gli elementi di file nell'elenco tenant consentiti/bloccati in questo momento.</span><span class="sxs-lookup"><span data-stu-id="a5686-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="a5686-111">Nelle Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile che non si sia d'accordo con il verdetto del filtro EOP.</span><span class="sxs-lookup"><span data-stu-id="a5686-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="a5686-112">Ad esempio, un buon messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non positivo potrebbe essere consentito (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="a5686-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="a5686-113">L'elenco Tenant consentiti/bloccati nel Centro sicurezza & conformità consente di ignorare manualmente i Microsoft 365 di filtro.</span><span class="sxs-lookup"><span data-stu-id="a5686-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="a5686-114">L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento dei clic dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a5686-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="a5686-115">È possibile specificare i seguenti tipi di sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="a5686-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="a5686-116">URL da bloccare.</span><span class="sxs-lookup"><span data-stu-id="a5686-116">URLs to block.</span></span>
- <span data-ttu-id="a5686-117">File da bloccare.</span><span class="sxs-lookup"><span data-stu-id="a5686-117">Files to block.</span></span>
- <span data-ttu-id="a5686-118">Domini del mittente della posta in blocco da consentire.</span><span class="sxs-lookup"><span data-stu-id="a5686-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="a5686-119">Per ulteriori informazioni sulla posta in blocco, sul livello di probabilità in blocco (BCL) e sul filtro della posta in blocco in base ai criteri di protezione da posta indesiderata, vedere Livello di reclamo in blocco [(BCL) in EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="a5686-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="a5686-120">Mittenti contraffatti per consentire o bloccare.</span><span class="sxs-lookup"><span data-stu-id="a5686-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="a5686-121">Se si esegue l'override del verdetto consenti o blocca nell'analisi [di spoofing](learn-about-spoof-intelligence.md)intelligence, il mittente contraffatto diventa una voce di autorizzazione o blocco manuale che viene visualizzata solo nella scheda **Spoofing** nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="a5686-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="a5686-122">È inoltre possibile creare manualmente voci consentite o bloccate per i mittenti falsificati prima che siano rilevate dall'intelligence di spoofing.</span><span class="sxs-lookup"><span data-stu-id="a5686-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="a5686-123">In questo articolo viene descritto come configurare le voci nell'elenco consenti/blocca tenant nel Centro sicurezza e conformità di & o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="a5686-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a5686-124">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a5686-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a5686-125">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a5686-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a5686-126">Per passare direttamente alla pagina **Elenco tenant consentiti/bloccati,** utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="a5686-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="a5686-127">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="a5686-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="a5686-128">Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="a5686-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="a5686-129">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="a5686-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="a5686-130">I valori hash percettivi (pHash) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="a5686-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="a5686-131">I valori url disponibili sono descritti nella [sintassi dell'URL](#url-syntax-for-the-tenant-allowblock-list) per la sezione Elenco tenant consentiti/bloccati più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a5686-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="a5686-132">L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="a5686-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="a5686-133">Il numero massimo di caratteri per ogni voce è:</span><span class="sxs-lookup"><span data-stu-id="a5686-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="a5686-134">Hash dei file = 64</span><span class="sxs-lookup"><span data-stu-id="a5686-134">File hashes = 64</span></span>
  - <span data-ttu-id="a5686-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="a5686-135">URL = 250</span></span>

- <span data-ttu-id="a5686-136">Una voce deve essere attiva entro 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="a5686-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="a5686-137">Per impostazione predefinita, le voci nell'elenco tenant consentiti/bloccati scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a5686-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="a5686-138">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="a5686-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="a5686-139">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5686-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a5686-140">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5686-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a5686-141">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a5686-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a5686-142">**URL, file e consenti mittenti in blocco:**</span><span class="sxs-lookup"><span data-stu-id="a5686-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="a5686-143">Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="a5686-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="a5686-144">Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a5686-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="a5686-145">**Spoofing**: una delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="a5686-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="a5686-146">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="a5686-146">**Organization Management**</span></span>
    - <span data-ttu-id="a5686-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span><span class="sxs-lookup"><span data-stu-id="a5686-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="a5686-148">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a5686-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="a5686-149">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5686-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a5686-150">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a5686-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="a5686-151">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a5686-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-152">Utilizzare il Centro sicurezza & conformità per creare voci url di blocco nell'elenco Consenti/Blocca tenant</span><span class="sxs-lookup"><span data-stu-id="a5686-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a5686-153">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a5686-154">Nella pagina **Elenco tenant consentiti/bloccati** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Blocca**</span><span class="sxs-lookup"><span data-stu-id="a5686-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="a5686-155">Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a5686-156">**Aggiungi URL da bloccare:** immetti un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="a5686-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="a5686-157">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a5686-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="a5686-158">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a5686-159">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="a5686-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="a5686-160">oppure</span><span class="sxs-lookup"><span data-stu-id="a5686-160">or</span></span>

     - <span data-ttu-id="a5686-161">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="a5686-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="a5686-163">.</span><span class="sxs-lookup"><span data-stu-id="a5686-163">.</span></span>

   - <span data-ttu-id="a5686-164">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="a5686-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a5686-165">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-166">Usare il Centro sicurezza & conformità per creare voci di file di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a5686-167">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a5686-168">Nella pagina **Elenco tenant consentiti/bloccati** selezionare la **scheda File** e quindi fare clic su **Blocca.**</span><span class="sxs-lookup"><span data-stu-id="a5686-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="a5686-169">Nel riquadro **a comparsa Aggiungi file da** bloccare, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a5686-170">**Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="a5686-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a5686-171">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a5686-172">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="a5686-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a5686-173">oppure</span><span class="sxs-lookup"><span data-stu-id="a5686-173">or</span></span>

     - <span data-ttu-id="a5686-174">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="a5686-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="a5686-176">.</span><span class="sxs-lookup"><span data-stu-id="a5686-176">.</span></span>

   - <span data-ttu-id="a5686-177">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="a5686-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a5686-178">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-179">Utilizzare il Centro sicurezza & conformità per creare voci del dominio del mittente della posta in blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a5686-180">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a5686-181">Nella pagina **Elenco tenant consentiti/bloccati** selezionare la scheda Domini mittente **per bypass BCL** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="a5686-182">Nel riquadro **a comparsa Aggiungi dominio mittente per BCL bypass** visualizzato, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a5686-183">**Aggiungere domini mittente per bypass BCL**: immettere un dominio di origine di buona posta in blocco per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="a5686-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a5686-184">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a5686-185">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="a5686-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a5686-186">oppure</span><span class="sxs-lookup"><span data-stu-id="a5686-186">or</span></span>

     - <span data-ttu-id="a5686-187">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="a5686-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="a5686-189">.</span><span class="sxs-lookup"><span data-stu-id="a5686-189">.</span></span>

4. <span data-ttu-id="a5686-190">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-191">Usare il Centro sicurezza & conformità per creare voci di mittente contraffatte consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-192">**Note**:</span><span class="sxs-lookup"><span data-stu-id="a5686-192">**Notes**:</span></span>

- <span data-ttu-id="a5686-193">Solo la _combinazione_ dell'utente contraffatto e dell'infrastruttura di invio definita nella coppia di domini è consentita o bloccata in modo specifico dallo spoofing. </span><span class="sxs-lookup"><span data-stu-id="a5686-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="a5686-194">Quando si configura una voce consenti o blocca per una coppia di domini, i messaggi di tale coppia di domini non vengono più visualizzati nelle informazioni di spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="a5686-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="a5686-195">Le voci per i mittenti contraffatti non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="a5686-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="a5686-196">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a5686-197">Nella pagina **Elenco tenant consentiti/non consentiti** selezionare la **scheda Spoofing** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="a5686-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="a5686-198">Nel riquadro **a comparsa Aggiungi nuove coppie** di domini visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a5686-199">**Aggiungere nuove coppie di domini con caratteri jolly:** immettere una coppia di domini per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="a5686-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="a5686-200">Per informazioni dettagliate sulla sintassi per le voci dei mittenti falsificati, vedere la sintassi della coppia di domini per le voci del mittente contraffatte nella sezione [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a5686-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="a5686-201">**Tipo di spoofing**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="a5686-202">**Interno**: il mittente contraffatto si trova in un dominio appartenente all'organizzazione (un [dominio accettato).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="a5686-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="a5686-203">**Esterno:** il mittente contraffatto si trova in un dominio esterno.</span><span class="sxs-lookup"><span data-stu-id="a5686-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="a5686-204">**Azione**: selezionare **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="a5686-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="a5686-205">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-206">Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a5686-207">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a5686-208">Selezionare la scheda desiderata.</span><span class="sxs-lookup"><span data-stu-id="a5686-208">Select the tab you want.</span></span> <span data-ttu-id="a5686-209">Le colonne disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="a5686-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="a5686-210">**URL**:</span><span class="sxs-lookup"><span data-stu-id="a5686-210">**URLs**:</span></span>
     - <span data-ttu-id="a5686-211">**Value**: URL.</span><span class="sxs-lookup"><span data-stu-id="a5686-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="a5686-212">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="a5686-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="a5686-213">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="a5686-213">**Last updated date**</span></span>
     - <span data-ttu-id="a5686-214">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="a5686-214">**Expiration date**</span></span>
     - <span data-ttu-id="a5686-215">**Nota**</span><span class="sxs-lookup"><span data-stu-id="a5686-215">**Note**</span></span>

   - <span data-ttu-id="a5686-216">**File**</span><span class="sxs-lookup"><span data-stu-id="a5686-216">**Files**</span></span>
     - <span data-ttu-id="a5686-217">**Value**: Hash del file.</span><span class="sxs-lookup"><span data-stu-id="a5686-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="a5686-218">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="a5686-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="a5686-219">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="a5686-219">**Last updated date**</span></span>
     - <span data-ttu-id="a5686-220">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="a5686-220">**Expiration date**</span></span>
     - <span data-ttu-id="a5686-221">**Nota**</span><span class="sxs-lookup"><span data-stu-id="a5686-221">**Note**</span></span>

   - <span data-ttu-id="a5686-222">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="a5686-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="a5686-223">**Valore**: dominio del mittente della posta in blocco.</span><span class="sxs-lookup"><span data-stu-id="a5686-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="a5686-224">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="a5686-224">**Last updated date**</span></span>
     - <span data-ttu-id="a5686-225">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="a5686-225">**Expiration date**</span></span>

   - <span data-ttu-id="a5686-226">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="a5686-226">**Spoofing**</span></span>
     - <span data-ttu-id="a5686-227">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="a5686-227">**Spoofed user**</span></span>
     - <span data-ttu-id="a5686-228">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="a5686-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="a5686-229">**Tipo di spoofing**: valore **Internal** o **External.**</span><span class="sxs-lookup"><span data-stu-id="a5686-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="a5686-230">**Action**: valore **Block o** **Allow.**</span><span class="sxs-lookup"><span data-stu-id="a5686-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="a5686-231">È possibile fare clic su un'intestazione di colonna per eseguire l'ordinamento crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="a5686-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="a5686-232">È possibile fare **clic su Gruppo** per raggruppare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a5686-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="a5686-233">I valori disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="a5686-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="a5686-234">**URL:** è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="a5686-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="a5686-235">**File**: è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="a5686-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="a5686-236">**Domini mittente per bypass BCL:** **il** gruppo non è disponibile in questa scheda.</span><span class="sxs-lookup"><span data-stu-id="a5686-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="a5686-237">**Spoofing**: è possibile raggruppare i risultati in base **al tipo Azione** o **Spoofing.**</span><span class="sxs-lookup"><span data-stu-id="a5686-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="a5686-238">Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="a5686-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="a5686-239">Al termine, fare clic su Cancella **ricerca** ![ Cancella icona di ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ricerca.</span><span class="sxs-lookup"><span data-stu-id="a5686-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="a5686-240">Fare **clic su** Filtro per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a5686-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="a5686-241">I valori disponibili **nel** riquadro a comparsa Filtro visualizzato dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="a5686-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="a5686-242">**URL**</span><span class="sxs-lookup"><span data-stu-id="a5686-242">**URLs**</span></span>
     - <span data-ttu-id="a5686-243">**Azione**</span><span class="sxs-lookup"><span data-stu-id="a5686-243">**Action**</span></span>
     - <span data-ttu-id="a5686-244">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="a5686-244">**Never expire**</span></span>
     - <span data-ttu-id="a5686-245">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="a5686-245">**Last updated date**</span></span>
     - <span data-ttu-id="a5686-246">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="a5686-246">**Expiration date**</span></span>

   - <span data-ttu-id="a5686-247">**File**</span><span class="sxs-lookup"><span data-stu-id="a5686-247">**Files**</span></span>
     - <span data-ttu-id="a5686-248">**Azione**</span><span class="sxs-lookup"><span data-stu-id="a5686-248">**Action**</span></span>
     - <span data-ttu-id="a5686-249">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="a5686-249">**Never expire**</span></span>
     - <span data-ttu-id="a5686-250">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="a5686-250">**Last updated date**</span></span>
     - <span data-ttu-id="a5686-251">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="a5686-251">**Expiration date**</span></span>

   - <span data-ttu-id="a5686-252">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="a5686-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="a5686-253">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="a5686-253">**Never expire**</span></span>
     - <span data-ttu-id="a5686-254">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="a5686-254">**Last updated date**</span></span>
     - <span data-ttu-id="a5686-255">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="a5686-255">**Expiration date**</span></span>

   - <span data-ttu-id="a5686-256">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="a5686-256">**Spoofing**</span></span>
     - <span data-ttu-id="a5686-257">**Azione**</span><span class="sxs-lookup"><span data-stu-id="a5686-257">**Action**</span></span>
     - <span data-ttu-id="a5686-258">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="a5686-258">**Spoof type**</span></span>

   <span data-ttu-id="a5686-259">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="a5686-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="a5686-260">Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="a5686-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-261">Utilizzare il Centro sicurezza & conformità per modificare le voci nell'elenco Tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a5686-262">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a5686-263">Selezionare la scheda contenente il tipo di voce che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="a5686-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="a5686-264">**URL**</span><span class="sxs-lookup"><span data-stu-id="a5686-264">**URLs**</span></span>
   - <span data-ttu-id="a5686-265">**File**</span><span class="sxs-lookup"><span data-stu-id="a5686-265">**Files**</span></span>
   - <span data-ttu-id="a5686-266">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="a5686-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="a5686-267">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="a5686-267">**Spoofing**</span></span>

3. <span data-ttu-id="a5686-268">Selezionare la voce che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="a5686-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="a5686-269">I valori che è possibile modificare nel riquadro a comparsa visualizzato dipendono dalla scheda selezionata nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="a5686-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="a5686-270">**URL**</span><span class="sxs-lookup"><span data-stu-id="a5686-270">**URLs**</span></span>
     - <span data-ttu-id="a5686-271">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="a5686-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="a5686-272">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="a5686-272">**Optional note**</span></span>

   - <span data-ttu-id="a5686-273">**File**</span><span class="sxs-lookup"><span data-stu-id="a5686-273">**Files**</span></span>
     - <span data-ttu-id="a5686-274">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="a5686-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="a5686-275">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="a5686-275">**Optional note**</span></span>

   - <span data-ttu-id="a5686-276">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="a5686-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="a5686-277">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="a5686-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="a5686-278">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="a5686-278">**Spoofing**</span></span>
     - <span data-ttu-id="a5686-279">**Azione**: è possibile modificare il valore in **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="a5686-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="a5686-280">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a5686-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-281">Utilizzare il Centro sicurezza & conformità per rimuovere le voci dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a5686-282">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="a5686-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a5686-283">Selezionare la scheda contenente il tipo di voce che si desidera rimuovere:</span><span class="sxs-lookup"><span data-stu-id="a5686-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="a5686-284">**URL**</span><span class="sxs-lookup"><span data-stu-id="a5686-284">**URLs**</span></span>
   - <span data-ttu-id="a5686-285">**File**</span><span class="sxs-lookup"><span data-stu-id="a5686-285">**Files**</span></span>
   - <span data-ttu-id="a5686-286">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="a5686-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="a5686-287">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="a5686-287">**Spoofing**</span></span>

3. <span data-ttu-id="a5686-288">Selezionare la voce che si desidera rimuovere e quindi fare clic su **Elimina Icona** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Elimina.</span><span class="sxs-lookup"><span data-stu-id="a5686-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="a5686-289">Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="a5686-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-290">Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-291">Usare PowerShell per aggiungere voci di file o URL di blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-292">Per aggiungere voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="a5686-293">In questo esempio viene aggiunta una voce del file di blocco per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="a5686-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="a5686-294">In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini(ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a5686-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="a5686-295">Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a5686-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="a5686-296">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-297">Utilizzare PowerShell per aggiungere voci di dominio del mittente di posta in blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-298">Per aggiungere voci di dominio consenti mittente di posta in blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="a5686-299">In questo esempio viene aggiunta una voce del mittente in blocco consentita per il dominio specificato che non scade mai.</span><span class="sxs-lookup"><span data-stu-id="a5686-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="a5686-300">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-301">Usare PowerShell per aggiungere voci di mittente spoofing consentite o bloccate all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-302">Per aggiungere voci di mittente contraffatto nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="a5686-303">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-304">Utilizzare PowerShell per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-305">Per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="a5686-306">In questo esempio vengono restituite le informazioni per il valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="a5686-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="a5686-307">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="a5686-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="a5686-308">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="a5686-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-309">Utilizzare PowerShell per visualizzare le voci del dominio del mittente della posta in blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-310">Per visualizzare le voci del dominio del mittente della posta in blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="a5686-311">In questo esempio vengono restituiti tutti i domini di mittenti di posta in blocco consentiti.</span><span class="sxs-lookup"><span data-stu-id="a5686-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="a5686-312">In questo esempio vengono restituite le informazioni per il dominio del mittente in blocco specificato.</span><span class="sxs-lookup"><span data-stu-id="a5686-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="a5686-313">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="a5686-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-314">Utilizzare PowerShell per visualizzare le voci dei mittenti contraffatti consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-315">Per visualizzare le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="a5686-316">In questo esempio vengono restituite tutte le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="a5686-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="a5686-317">In questo esempio vengono restituite tutte le voci del mittente spoofing consentite interne.</span><span class="sxs-lookup"><span data-stu-id="a5686-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="a5686-318">In questo esempio vengono restituite tutte le voci di mittente contraffatte bloccate esterne.</span><span class="sxs-lookup"><span data-stu-id="a5686-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="a5686-319">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-320">Utilizzare PowerShell per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-321">Per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="a5686-322">In questo esempio viene modificata la data di scadenza della voce url di blocco specificata.</span><span class="sxs-lookup"><span data-stu-id="a5686-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="a5686-323">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-324">Utilizzare PowerShell per modificare le voci del dominio del mittente della posta in blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-325">Per modificare le voci del dominio del mittente della posta in blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="a5686-326">In questo esempio viene modificata la scadenza della voce di dominio Consenti mittente di posta in blocco specificata in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="a5686-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="a5686-327">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="a5686-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-328">Utilizzare PowerShell per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-329">Per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="a5686-330">In questo esempio la voce del mittente contraffatto viene modificata da consenti a blocca.</span><span class="sxs-lookup"><span data-stu-id="a5686-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="a5686-331">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-332">Utilizzare PowerShell per rimuovere le voci di dominio, file e dominio del mittente della posta in blocco dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-333">Per rimuovere le voci di dominio consenti posta in blocco del mittente, bloccare le voci di file e bloccare le voci URL dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a5686-334">In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="a5686-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="a5686-335">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-336">Utilizzare PowerShell per rimuovere le voci consenti o blocca mittente contraffatte dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-337">Per rimuovere le voci del mittente di spoofing consentite o bloccate dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a5686-338">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="a5686-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-339">Sintassi dell'URL per l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="a5686-340">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="a5686-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="a5686-341">Le estensioni dei nomi di file non sono consentite(ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="a5686-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="a5686-342">Unicode non è supportato, ma Punycode lo è.</span><span class="sxs-lookup"><span data-stu-id="a5686-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="a5686-343">I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="a5686-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="a5686-344">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="a5686-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="a5686-345">A sinistra del punto è presente almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="a5686-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="a5686-346">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="a5686-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="a5686-347">Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.</span><span class="sxs-lookup"><span data-stu-id="a5686-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="a5686-348">I sottopercorso non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="a5686-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="a5686-349">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="a5686-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="a5686-350">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="a5686-351">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="a5686-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="a5686-352">Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.</span><span class="sxs-lookup"><span data-stu-id="a5686-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="a5686-353">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="a5686-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="a5686-354">Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.</span><span class="sxs-lookup"><span data-stu-id="a5686-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="a5686-355">Tutti i percorsi secondari non sono implicati da un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="a5686-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="a5686-356">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="a5686-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="a5686-357">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="a5686-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="a5686-358">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="a5686-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="a5686-359">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5686-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="a5686-360">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="a5686-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="a5686-361">Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="a5686-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="a5686-362">Le voci URL contenenti protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.</span><span class="sxs-lookup"><span data-stu-id="a5686-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="a5686-363">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="a5686-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="a5686-364">Le virgolette (' o ") sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="a5686-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="a5686-365">Se possibile, un URL deve includere tutti i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="a5686-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="a5686-366">Scenari di immissione url</span><span class="sxs-lookup"><span data-stu-id="a5686-366">URL entry scenarios</span></span>

<span data-ttu-id="a5686-367">Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a5686-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="a5686-368">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="a5686-368">Scenario: No wildcards</span></span>

<span data-ttu-id="a5686-369">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a5686-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="a5686-370">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="a5686-371">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="a5686-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="a5686-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-372">abc-contoso.com</span></span>
  - <span data-ttu-id="a5686-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a5686-373">contoso.com/a</span></span>
  - <span data-ttu-id="a5686-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="a5686-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="a5686-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a5686-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-377">www.contoso.com</span></span>
  - <span data-ttu-id="a5686-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a5686-379">**Corrispondenza blocco**:</span><span class="sxs-lookup"><span data-stu-id="a5686-379">**Block match**:</span></span>

  - <span data-ttu-id="a5686-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-380">contoso.com</span></span>
  - <span data-ttu-id="a5686-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a5686-381">contoso.com/a</span></span>
  - <span data-ttu-id="a5686-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="a5686-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="a5686-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a5686-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-385">www.contoso.com</span></span>
  - <span data-ttu-id="a5686-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a5686-387">**Blocco non corrispondente**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="a5686-388">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="a5686-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="a5686-389">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a5686-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="a5686-390">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="a5686-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a5686-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-391">www.contoso.com</span></span>
  - <span data-ttu-id="a5686-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a5686-393">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="a5686-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a5686-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-394">123contoso.com</span></span>
  - <span data-ttu-id="a5686-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-395">contoso.com</span></span>
  - <span data-ttu-id="a5686-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="a5686-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a5686-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="a5686-398">Scenario: carattere jolly destro all'inizio del percorso</span><span class="sxs-lookup"><span data-stu-id="a5686-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="a5686-399">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="a5686-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="a5686-400">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="a5686-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a5686-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="a5686-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="a5686-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a5686-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a5686-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="a5686-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="a5686-404">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="a5686-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a5686-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-405">contoso.com</span></span>
  - <span data-ttu-id="a5686-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a5686-406">contoso.com/a</span></span>
  - <span data-ttu-id="a5686-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-407">www.contoso.com</span></span>
  - <span data-ttu-id="a5686-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="a5686-409">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="a5686-409">Scenario: Left tilde</span></span>

<span data-ttu-id="a5686-410">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a5686-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="a5686-411">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="a5686-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a5686-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-412">contoso.com</span></span>
  - <span data-ttu-id="a5686-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-413">www.contoso.com</span></span>
  - <span data-ttu-id="a5686-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a5686-415">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="a5686-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a5686-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-416">123contoso.com</span></span>
  - <span data-ttu-id="a5686-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a5686-417">contoso.com/abc</span></span>
  - <span data-ttu-id="a5686-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a5686-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="a5686-419">Scenario: suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="a5686-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="a5686-420">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a5686-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="a5686-421">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="a5686-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a5686-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a5686-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="a5686-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a5686-423">contoso.com/a</span></span>
  - <span data-ttu-id="a5686-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a5686-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a5686-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a5686-425">contoso.com/ab</span></span>
  - <span data-ttu-id="a5686-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a5686-426">contoso.com/b</span></span>
  - <span data-ttu-id="a5686-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a5686-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a5686-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a5686-428">contoso.com/ba</span></span>

- <span data-ttu-id="a5686-429">**Allow not matched** e **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="a5686-430">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="a5686-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="a5686-431">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a5686-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="a5686-432">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="a5686-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a5686-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a5686-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="a5686-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a5686-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a5686-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a5686-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="a5686-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a5686-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a5686-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a5686-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="a5686-438">**Allow not matched** e **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a5686-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="a5686-439">Scenario: tilde sinistra e destra</span><span class="sxs-lookup"><span data-stu-id="a5686-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="a5686-440">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="a5686-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="a5686-441">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="a5686-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a5686-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-442">contoso.com</span></span>
  - <span data-ttu-id="a5686-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a5686-443">contoso.com/a</span></span>
  - <span data-ttu-id="a5686-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-444">www.contoso.com</span></span>
  - <span data-ttu-id="a5686-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a5686-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="a5686-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a5686-447">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="a5686-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a5686-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-448">123contoso.com</span></span>
  - <span data-ttu-id="a5686-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="a5686-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="a5686-450">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="a5686-450">Scenario: IP address</span></span>

<span data-ttu-id="a5686-451">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="a5686-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="a5686-452">**Allow match** and **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a5686-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="a5686-453">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="a5686-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a5686-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a5686-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="a5686-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a5686-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="a5686-456">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="a5686-456">IP address with right wildcard</span></span>

<span data-ttu-id="a5686-457">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="a5686-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="a5686-458">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="a5686-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a5686-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="a5686-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="a5686-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="a5686-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="a5686-461">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="a5686-461">Examples of invalid entries</span></span>

<span data-ttu-id="a5686-462">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="a5686-462">The following entries are invalid:</span></span>

- <span data-ttu-id="a5686-463">**Valori di dominio mancanti o non validi:**</span><span class="sxs-lookup"><span data-stu-id="a5686-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="a5686-464">contoso</span><span class="sxs-lookup"><span data-stu-id="a5686-464">contoso</span></span>
  - <span data-ttu-id="a5686-465">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="a5686-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="a5686-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="a5686-466">\*.com</span></span>
  - <span data-ttu-id="a5686-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="a5686-467">\*.pdf</span></span>

- <span data-ttu-id="a5686-468">**Caratteri jolly per il testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="a5686-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="a5686-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="a5686-469">\*contoso.com</span></span>
  - <span data-ttu-id="a5686-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="a5686-470">contoso.com\*</span></span>
  - <span data-ttu-id="a5686-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a5686-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="a5686-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="a5686-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="a5686-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="a5686-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="a5686-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="a5686-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="a5686-475">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="a5686-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="a5686-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="a5686-476">contoso.com:443</span></span>
  - <span data-ttu-id="a5686-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="a5686-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="a5686-478">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="a5686-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="a5686-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="a5686-479">\*.\*</span></span>

- <span data-ttu-id="a5686-480">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="a5686-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="a5686-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="a5686-481">conto\*so.com</span></span>
  - <span data-ttu-id="a5686-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="a5686-482">conto~so.com</span></span>

- <span data-ttu-id="a5686-483">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="a5686-483">**Double wildcards**</span></span>

  - <span data-ttu-id="a5686-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="a5686-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="a5686-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="a5686-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a5686-486">Sintassi della coppia di domini per le voci del mittente contraffatte nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="a5686-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a5686-487">Una coppia di domini per un mittente contraffatto nell'elenco tenant consentiti/bloccati utilizza la sintassi seguente: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="a5686-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="a5686-488">**Utente contraffatto:** questo valore include l'indirizzo di posta elettronica  dell'utente contraffatto visualizzato nella casella Da nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a5686-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="a5686-489">Questo indirizzo è noto anche come `5322.From` indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a5686-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="a5686-490">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="a5686-490">Valid values include:</span></span>
  - <span data-ttu-id="a5686-491">Un singolo indirizzo di posta elettronica (ad esempio, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a5686-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="a5686-492">Un dominio di posta elettronica (ad esempio, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a5686-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="a5686-493">Il carattere jolly (ad esempio, \* ).</span><span class="sxs-lookup"><span data-stu-id="a5686-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="a5686-494">**Infrastruttura di invio:** questo valore indica l'origine dei messaggi provenienti dall'utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="a5686-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="a5686-495">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="a5686-495">Valid values include:</span></span>
  - <span data-ttu-id="a5686-496">Il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine (ad esempio, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="a5686-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="a5686-497">Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="a5686-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="a5686-498">Ecco alcuni esempi di coppie di domini valide per identificare i mittenti contraffatti:</span><span class="sxs-lookup"><span data-stu-id="a5686-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="a5686-499">L'aggiunta di una coppia di domini consente o blocca *solo* la combinazione dell'utente contraffatto *e dell'infrastruttura* di invio.</span><span class="sxs-lookup"><span data-stu-id="a5686-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="a5686-500">Non consente la posta elettronica dell'utente contraffatto da alcuna origine, né consente la posta elettronica dall'origine dell'infrastruttura di invio per qualsiasi utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="a5686-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="a5686-501">Ad esempio, aggiungere una voce allow per la coppia di domini seguente:</span><span class="sxs-lookup"><span data-stu-id="a5686-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="a5686-502">**Dominio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="a5686-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="a5686-503">**Infrastruttura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="a5686-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="a5686-504">Solo i messaggi provenienti da tale dominio e *la* coppia di infrastruttura di invio possono effettuare lo spoofing.</span><span class="sxs-lookup"><span data-stu-id="a5686-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="a5686-505">Altri mittenti che tentano di eseguire lo spoofing gmail.com non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="a5686-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="a5686-506">I messaggi provenienti da mittenti in altri domini provenienti da tms.mx.com vengono controllati dalla spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="a5686-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
