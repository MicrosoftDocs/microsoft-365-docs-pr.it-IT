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
ms.openlocfilehash: 1548eda760b7b6b19214cb834d7fc43357dc0357
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985493"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-103">Gestire l'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9514a-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="9514a-104">**Applies to**</span></span>
- [<span data-ttu-id="9514a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9514a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9514a-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="9514a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9514a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9514a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="9514a-108">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="9514a-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="9514a-109">Se l'organizzazione non dispone delle funzionalità di spoofing come descritto in questo articolo, vedere l'esperienza di gestione dello spoofing precedente in Gestire i mittenti contraffatti utilizzando i criteri di spoof intelligence e [spoof intelligence insight in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="9514a-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="9514a-110">Non è possibile configurare **gli** URL consentiti o gli elementi di file nell'elenco tenant consentiti/bloccati in questo momento.</span><span class="sxs-lookup"><span data-stu-id="9514a-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="9514a-111">Nelle Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile che non si sia d'accordo con il verdetto del filtro EOP.</span><span class="sxs-lookup"><span data-stu-id="9514a-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="9514a-112">Ad esempio, un buon messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non positivo potrebbe essere consentito (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="9514a-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="9514a-113">L'elenco Tenant consentiti/Microsoft 365 Defender consente di ignorare manualmente i Microsoft 365 di filtro.</span><span class="sxs-lookup"><span data-stu-id="9514a-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="9514a-114">L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento dei clic dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9514a-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="9514a-115">È possibile specificare i seguenti tipi di sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="9514a-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="9514a-116">URL da bloccare.</span><span class="sxs-lookup"><span data-stu-id="9514a-116">URLs to block.</span></span>
- <span data-ttu-id="9514a-117">File da bloccare.</span><span class="sxs-lookup"><span data-stu-id="9514a-117">Files to block.</span></span>
- <span data-ttu-id="9514a-118">Mittenti contraffatti per consentire o bloccare.</span><span class="sxs-lookup"><span data-stu-id="9514a-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="9514a-119">Se si esegue l'override del verdetto consenti o blocca nell'analisi [di spoofing](learn-about-spoof-intelligence.md)intelligence, il mittente contraffatto diventa una voce di autorizzazione o blocco manuale che viene visualizzata solo nella scheda **Spoofing** nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="9514a-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="9514a-120">È inoltre possibile creare manualmente voci consentite o bloccate per i mittenti falsificati prima che siano rilevate dall'intelligence di spoofing.</span><span class="sxs-lookup"><span data-stu-id="9514a-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="9514a-121">In questo articolo viene descritto come configurare le voci nell'elenco tenant consentiti/bloccati nel portale di Microsoft 365 Defender o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9514a-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9514a-122">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="9514a-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9514a-123">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="9514a-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="9514a-124">Per passare direttamente alla pagina **Tenant Allow/Block Lists,** utilizzare <https://security.microsoft.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="9514a-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="9514a-125">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="9514a-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="9514a-126">Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="9514a-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="9514a-127">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="9514a-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="9514a-128">I valori hash percettivi (pHash) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="9514a-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="9514a-129">I valori url disponibili sono descritti nella [sintassi dell'URL](#url-syntax-for-the-tenant-allowblock-list) per la sezione Elenco tenant consentiti/bloccati più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9514a-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="9514a-130">L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="9514a-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="9514a-131">Il numero massimo di caratteri per ogni voce è:</span><span class="sxs-lookup"><span data-stu-id="9514a-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="9514a-132">Hash dei file = 64</span><span class="sxs-lookup"><span data-stu-id="9514a-132">File hashes = 64</span></span>
  - <span data-ttu-id="9514a-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="9514a-133">URL = 250</span></span>

- <span data-ttu-id="9514a-134">Una voce deve essere attiva entro 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="9514a-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="9514a-135">Per impostazione predefinita, le voci nell'elenco tenant consentiti/bloccati scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="9514a-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="9514a-136">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="9514a-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="9514a-137">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9514a-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9514a-138">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9514a-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9514a-139">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="9514a-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9514a-140">**URL e file**:</span><span class="sxs-lookup"><span data-stu-id="9514a-140">**URLs and files**:</span></span>
    - <span data-ttu-id="9514a-141">Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="9514a-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="9514a-142">Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9514a-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="9514a-143">**Spoofing**: una delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="9514a-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="9514a-144">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="9514a-144">**Organization Management**</span></span>
    - <span data-ttu-id="9514a-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span><span class="sxs-lookup"><span data-stu-id="9514a-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="9514a-146">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="9514a-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="9514a-147">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9514a-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9514a-148">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9514a-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="9514a-149">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9514a-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-150">Utilizzare il portale Microsoft 365 Defender per creare voci url di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9514a-151">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9514a-152">Nella pagina **Elenco tenant consentiti/bloccati** verificare che la scheda **URL** sia selezionata e quindi fare clic su Blocca ![ icona ](../../media/m365-cc-sc-create-icon.png) **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="9514a-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="9514a-153">Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="9514a-154">**Aggiungere URL con caratteri jolly:** immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="9514a-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="9514a-155">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9514a-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="9514a-156">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="9514a-157">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Rimuovi su per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. </span><span class="sxs-lookup"><span data-stu-id="9514a-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="9514a-158">oppure</span><span class="sxs-lookup"><span data-stu-id="9514a-158">or</span></span>

     - <span data-ttu-id="9514a-159">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="9514a-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="9514a-161">.</span><span class="sxs-lookup"><span data-stu-id="9514a-161">.</span></span>
   - <span data-ttu-id="9514a-162">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="9514a-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9514a-163">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-164">Utilizzare il portale Microsoft 365 Defender per creare voci di file bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9514a-165">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9514a-166">Nella pagina **Elenco tenant consentiti/bloccati** selezionare la **scheda File** e quindi fare clic su Blocca ![ icona ](../../media/m365-cc-sc-create-icon.png) **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="9514a-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="9514a-167">Nel riquadro **a comparsa Blocca** file visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="9514a-168">**Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="9514a-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="9514a-169">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="9514a-170">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Rimuovi su per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. </span><span class="sxs-lookup"><span data-stu-id="9514a-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="9514a-171">oppure</span><span class="sxs-lookup"><span data-stu-id="9514a-171">or</span></span>

     - <span data-ttu-id="9514a-172">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="9514a-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="9514a-174">.</span><span class="sxs-lookup"><span data-stu-id="9514a-174">.</span></span>
   - <span data-ttu-id="9514a-175">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="9514a-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9514a-176">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-177">Utilizzare il portale Microsoft 365 Defender per creare voci di mittente contraffatte consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-178">**Note**:</span><span class="sxs-lookup"><span data-stu-id="9514a-178">**Notes**:</span></span>

- <span data-ttu-id="9514a-179">Solo la _combinazione_ dell'utente contraffatto e dell'infrastruttura di invio definita nella coppia di domini è consentita o bloccata in modo specifico dallo spoofing. </span><span class="sxs-lookup"><span data-stu-id="9514a-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="9514a-180">Quando si configura una voce consenti o blocca per una coppia di domini, i messaggi di tale coppia di domini non vengono più visualizzati nelle informazioni di spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="9514a-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="9514a-181">Le voci per i mittenti contraffatti non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="9514a-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="9514a-182">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9514a-183">Nella pagina **Elenco tenant consentiti/non consentiti** selezionare la scheda **Spoofing** e quindi fare clic su ![ Blocca icona ](../../media/m365-cc-sc-create-icon.png) **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="9514a-184">Nel riquadro **a comparsa Aggiungi nuove coppie** di domini visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="9514a-185">**Aggiungere nuove coppie di domini con caratteri jolly:** immettere una coppia di domini per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="9514a-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="9514a-186">Per informazioni dettagliate sulla sintassi per le voci dei mittenti falsificati, vedere la sintassi della coppia di domini per le voci del mittente contraffatte nella sezione [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9514a-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="9514a-187">**Tipo di spoofing**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="9514a-188">**Interno**: il mittente contraffatto si trova in un dominio appartenente all'organizzazione (un [dominio accettato).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="9514a-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="9514a-189">**Esterno:** il mittente contraffatto si trova in un dominio esterno.</span><span class="sxs-lookup"><span data-stu-id="9514a-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="9514a-190">**Azione**: selezionare **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="9514a-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="9514a-191">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-192">Utilizzare il portale Microsoft 365 Defender per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9514a-193">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9514a-194">Selezionare la scheda desiderata.</span><span class="sxs-lookup"><span data-stu-id="9514a-194">Select the tab you want.</span></span> <span data-ttu-id="9514a-195">Le colonne disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="9514a-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="9514a-196">**URL**:</span><span class="sxs-lookup"><span data-stu-id="9514a-196">**URLs**:</span></span>
     - <span data-ttu-id="9514a-197">**Value**: URL.</span><span class="sxs-lookup"><span data-stu-id="9514a-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="9514a-198">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="9514a-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="9514a-199">**Ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="9514a-199">**Last updated**</span></span>
     - <span data-ttu-id="9514a-200">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="9514a-200">**Remove on**</span></span>
     - <span data-ttu-id="9514a-201">**Note**</span><span class="sxs-lookup"><span data-stu-id="9514a-201">**Notes**</span></span>
   - <span data-ttu-id="9514a-202">**File**</span><span class="sxs-lookup"><span data-stu-id="9514a-202">**Files**</span></span>
     - <span data-ttu-id="9514a-203">**Value**: Hash del file.</span><span class="sxs-lookup"><span data-stu-id="9514a-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="9514a-204">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="9514a-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="9514a-205">**Ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="9514a-205">**Last updated**</span></span>
     - <span data-ttu-id="9514a-206">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="9514a-206">**Remove on**</span></span>
     - <span data-ttu-id="9514a-207">**Note**</span><span class="sxs-lookup"><span data-stu-id="9514a-207">**Notes**</span></span>
   - <span data-ttu-id="9514a-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9514a-208">**Spoofing**</span></span>
     - <span data-ttu-id="9514a-209">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="9514a-209">**Spoofed user**</span></span>
     - <span data-ttu-id="9514a-210">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="9514a-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="9514a-211">**Tipo di spoofing**: valore **Internal** o **External.**</span><span class="sxs-lookup"><span data-stu-id="9514a-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="9514a-212">**Action**: valore **Block o** **Allow.**</span><span class="sxs-lookup"><span data-stu-id="9514a-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="9514a-213">È possibile fare clic su un'intestazione di colonna per eseguire l'ordinamento crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="9514a-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="9514a-214">È possibile fare **clic su Gruppo** per raggruppare i risultati.</span><span class="sxs-lookup"><span data-stu-id="9514a-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="9514a-215">I valori disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="9514a-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="9514a-216">**URL:** è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="9514a-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="9514a-217">**File**: è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="9514a-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="9514a-218">**Spoofing**: è possibile raggruppare i risultati in base **al tipo Azione** o **Spoofing.**</span><span class="sxs-lookup"><span data-stu-id="9514a-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="9514a-219">Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="9514a-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="9514a-220">Al termine, fare clic su Cancella icona ![ ricerca ](../../media/m365-cc-sc-close-icon.png) **Cancella ricerca**.</span><span class="sxs-lookup"><span data-stu-id="9514a-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="9514a-221">Fare **clic su** Filtro per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="9514a-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="9514a-222">I valori disponibili **nel** riquadro a comparsa Filtro visualizzato dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="9514a-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="9514a-223">**URL**</span><span class="sxs-lookup"><span data-stu-id="9514a-223">**URLs**</span></span>
     - <span data-ttu-id="9514a-224">**Azione**</span><span class="sxs-lookup"><span data-stu-id="9514a-224">**Action**</span></span>
     - <span data-ttu-id="9514a-225">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="9514a-225">**Never expire**</span></span>
     - <span data-ttu-id="9514a-226">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="9514a-226">**Last updated date**</span></span>
     - <span data-ttu-id="9514a-227">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="9514a-227">**Remove on**</span></span>
   - <span data-ttu-id="9514a-228">**File**</span><span class="sxs-lookup"><span data-stu-id="9514a-228">**Files**</span></span>
     - <span data-ttu-id="9514a-229">**Azione**</span><span class="sxs-lookup"><span data-stu-id="9514a-229">**Action**</span></span>
     - <span data-ttu-id="9514a-230">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="9514a-230">**Never expire**</span></span>
     - <span data-ttu-id="9514a-231">**Ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="9514a-231">**Last updated**</span></span>
     - <span data-ttu-id="9514a-232">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="9514a-232">**Remove on**</span></span>
   - <span data-ttu-id="9514a-233">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9514a-233">**Spoofing**</span></span>
     - <span data-ttu-id="9514a-234">**Azione**</span><span class="sxs-lookup"><span data-stu-id="9514a-234">**Action**</span></span>
     - <span data-ttu-id="9514a-235">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="9514a-235">**Spoof type**</span></span>

   <span data-ttu-id="9514a-236">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="9514a-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="9514a-237">Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="9514a-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-238">Utilizzare il Microsoft 365 Defender per modificare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9514a-239">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9514a-240">Selezionare la scheda contenente il tipo di voce che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="9514a-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="9514a-241">**URL**</span><span class="sxs-lookup"><span data-stu-id="9514a-241">**URLs**</span></span>
   - <span data-ttu-id="9514a-242">**File**</span><span class="sxs-lookup"><span data-stu-id="9514a-242">**Files**</span></span>
   - <span data-ttu-id="9514a-243">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9514a-243">**Spoofing**</span></span>

3. <span data-ttu-id="9514a-244">Selezionare la voce che si desidera modificare e quindi fare clic su ![ Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="9514a-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="9514a-245">I valori che è possibile modificare nel riquadro a comparsa visualizzato dipendono dalla scheda selezionata nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="9514a-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="9514a-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="9514a-246">**URLs**</span></span>
     - <span data-ttu-id="9514a-247">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9514a-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="9514a-248">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="9514a-248">**Optional note**</span></span>
   - <span data-ttu-id="9514a-249">**File**</span><span class="sxs-lookup"><span data-stu-id="9514a-249">**Files**</span></span>
     - <span data-ttu-id="9514a-250">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9514a-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="9514a-251">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="9514a-251">**Optional note**</span></span>
   - <span data-ttu-id="9514a-252">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9514a-252">**Spoofing**</span></span>
     - <span data-ttu-id="9514a-253">**Azione**: è possibile modificare il valore in **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="9514a-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="9514a-254">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9514a-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-255">Utilizzare il portale Microsoft 365 Defender per rimuovere le voci dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9514a-256">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9514a-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9514a-257">Selezionare la scheda contenente il tipo di voce che si desidera rimuovere:</span><span class="sxs-lookup"><span data-stu-id="9514a-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="9514a-258">**URL**</span><span class="sxs-lookup"><span data-stu-id="9514a-258">**URLs**</span></span>
   - <span data-ttu-id="9514a-259">**File**</span><span class="sxs-lookup"><span data-stu-id="9514a-259">**Files**</span></span>
   - <span data-ttu-id="9514a-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="9514a-260">**Spoofing**</span></span>

3. <span data-ttu-id="9514a-261">Selezionare la voce che si desidera rimuovere e quindi fare clic su ![ Elimina icona ](../../media/m365-cc-sc-delete-icon.png) **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="9514a-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="9514a-262">Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="9514a-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-263">Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-264">Usare PowerShell per aggiungere voci di file o URL di blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-265">Per aggiungere voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="9514a-266">In questo esempio viene aggiunta una voce del file di blocco per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="9514a-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="9514a-267">In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini(ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9514a-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="9514a-268">Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="9514a-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="9514a-269">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9514a-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-270">Usare PowerShell per aggiungere voci di mittente spoofing consentite o bloccate all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-271">Per aggiungere voci di mittente contraffatto nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="9514a-272">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="9514a-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-273">Utilizzare PowerShell per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-274">Per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="9514a-275">In questo esempio vengono restituite le informazioni per il valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="9514a-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="9514a-276">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="9514a-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="9514a-277">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="9514a-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-278">Utilizzare PowerShell per visualizzare le voci dei mittenti contraffatti consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-279">Per visualizzare le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="9514a-280">In questo esempio vengono restituite tutte le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="9514a-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="9514a-281">In questo esempio vengono restituite tutte le voci del mittente spoofing consentite interne.</span><span class="sxs-lookup"><span data-stu-id="9514a-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="9514a-282">In questo esempio vengono restituite tutte le voci di mittente contraffatte bloccate esterne.</span><span class="sxs-lookup"><span data-stu-id="9514a-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="9514a-283">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="9514a-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-284">Utilizzare PowerShell per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-285">Per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="9514a-286">In questo esempio viene modificata la data di scadenza della voce url di blocco specificata.</span><span class="sxs-lookup"><span data-stu-id="9514a-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="9514a-287">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9514a-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-288">Utilizzare PowerShell per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-289">Per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="9514a-290">In questo esempio la voce del mittente contraffatto viene modificata da consenti a blocca.</span><span class="sxs-lookup"><span data-stu-id="9514a-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="9514a-291">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="9514a-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-292">Utilizzare PowerShell per rimuovere voci di URL o file dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-293">Per rimuovere le voci di file e URL dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9514a-294">In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="9514a-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="9514a-295">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9514a-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-296">Utilizzare PowerShell per rimuovere le voci consenti o blocca mittente contraffatte dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-297">Per rimuovere le voci del mittente di spoofing consentite o bloccate dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9514a-298">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="9514a-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-299">Sintassi dell'URL per l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="9514a-300">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="9514a-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="9514a-301">Le estensioni dei nomi di file non sono consentite(ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="9514a-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="9514a-302">Unicode non è supportato, ma Punycode lo è.</span><span class="sxs-lookup"><span data-stu-id="9514a-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="9514a-303">I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="9514a-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="9514a-304">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="9514a-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="9514a-305">A sinistra del punto è presente almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="9514a-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="9514a-306">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="9514a-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="9514a-307">Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.</span><span class="sxs-lookup"><span data-stu-id="9514a-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="9514a-308">I sottopercorso non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="9514a-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="9514a-309">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9514a-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="9514a-310">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="9514a-311">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="9514a-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="9514a-312">Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.</span><span class="sxs-lookup"><span data-stu-id="9514a-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="9514a-313">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="9514a-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="9514a-314">Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.</span><span class="sxs-lookup"><span data-stu-id="9514a-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="9514a-315">Tutti i percorsi secondari non sono implicati da un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="9514a-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="9514a-316">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9514a-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="9514a-317">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="9514a-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="9514a-318">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="9514a-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="9514a-319">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="9514a-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="9514a-320">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="9514a-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="9514a-321">Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9514a-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="9514a-322">Le voci URL contenenti protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.</span><span class="sxs-lookup"><span data-stu-id="9514a-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="9514a-323">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="9514a-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="9514a-324">Le virgolette (' o ") sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="9514a-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="9514a-325">Se possibile, un URL deve includere tutti i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="9514a-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="9514a-326">Scenari di immissione url</span><span class="sxs-lookup"><span data-stu-id="9514a-326">URL entry scenarios</span></span>

<span data-ttu-id="9514a-327">Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9514a-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="9514a-328">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="9514a-328">Scenario: No wildcards</span></span>

<span data-ttu-id="9514a-329">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9514a-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="9514a-330">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="9514a-331">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="9514a-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="9514a-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-332">abc-contoso.com</span></span>
  - <span data-ttu-id="9514a-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9514a-333">contoso.com/a</span></span>
  - <span data-ttu-id="9514a-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="9514a-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="9514a-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9514a-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-337">www.contoso.com</span></span>
  - <span data-ttu-id="9514a-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9514a-339">**Corrispondenza blocco**:</span><span class="sxs-lookup"><span data-stu-id="9514a-339">**Block match**:</span></span>

  - <span data-ttu-id="9514a-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-340">contoso.com</span></span>
  - <span data-ttu-id="9514a-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9514a-341">contoso.com/a</span></span>
  - <span data-ttu-id="9514a-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="9514a-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="9514a-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9514a-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-345">www.contoso.com</span></span>
  - <span data-ttu-id="9514a-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9514a-347">**Blocco non corrispondente**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="9514a-348">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="9514a-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="9514a-349">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9514a-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="9514a-350">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9514a-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9514a-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-351">www.contoso.com</span></span>
  - <span data-ttu-id="9514a-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9514a-353">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9514a-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9514a-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-354">123contoso.com</span></span>
  - <span data-ttu-id="9514a-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-355">contoso.com</span></span>
  - <span data-ttu-id="9514a-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="9514a-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9514a-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="9514a-358">Scenario: carattere jolly destro all'inizio del percorso</span><span class="sxs-lookup"><span data-stu-id="9514a-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="9514a-359">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="9514a-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="9514a-360">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9514a-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9514a-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="9514a-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="9514a-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9514a-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9514a-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="9514a-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="9514a-364">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9514a-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9514a-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-365">contoso.com</span></span>
  - <span data-ttu-id="9514a-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9514a-366">contoso.com/a</span></span>
  - <span data-ttu-id="9514a-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-367">www.contoso.com</span></span>
  - <span data-ttu-id="9514a-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="9514a-369">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="9514a-369">Scenario: Left tilde</span></span>

<span data-ttu-id="9514a-370">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9514a-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="9514a-371">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9514a-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9514a-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-372">contoso.com</span></span>
  - <span data-ttu-id="9514a-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-373">www.contoso.com</span></span>
  - <span data-ttu-id="9514a-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9514a-375">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9514a-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9514a-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-376">123contoso.com</span></span>
  - <span data-ttu-id="9514a-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9514a-377">contoso.com/abc</span></span>
  - <span data-ttu-id="9514a-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9514a-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="9514a-379">Scenario: suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="9514a-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="9514a-380">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9514a-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="9514a-381">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9514a-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9514a-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9514a-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="9514a-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9514a-383">contoso.com/a</span></span>
  - <span data-ttu-id="9514a-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9514a-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9514a-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9514a-385">contoso.com/ab</span></span>
  - <span data-ttu-id="9514a-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9514a-386">contoso.com/b</span></span>
  - <span data-ttu-id="9514a-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9514a-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9514a-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9514a-388">contoso.com/ba</span></span>

- <span data-ttu-id="9514a-389">**Allow not matched** e **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="9514a-390">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="9514a-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="9514a-391">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9514a-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="9514a-392">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9514a-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9514a-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9514a-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="9514a-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9514a-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9514a-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9514a-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="9514a-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9514a-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9514a-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9514a-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="9514a-398">**Allow not matched** e **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9514a-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="9514a-399">Scenario: tilde sinistra e destra</span><span class="sxs-lookup"><span data-stu-id="9514a-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="9514a-400">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="9514a-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="9514a-401">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9514a-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9514a-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-402">contoso.com</span></span>
  - <span data-ttu-id="9514a-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9514a-403">contoso.com/a</span></span>
  - <span data-ttu-id="9514a-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-404">www.contoso.com</span></span>
  - <span data-ttu-id="9514a-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9514a-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="9514a-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9514a-407">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9514a-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9514a-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-408">123contoso.com</span></span>
  - <span data-ttu-id="9514a-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="9514a-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="9514a-410">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="9514a-410">Scenario: IP address</span></span>

<span data-ttu-id="9514a-411">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="9514a-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="9514a-412">**Allow match** and **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9514a-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="9514a-413">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9514a-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9514a-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9514a-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="9514a-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9514a-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="9514a-416">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="9514a-416">IP address with right wildcard</span></span>

<span data-ttu-id="9514a-417">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="9514a-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="9514a-418">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9514a-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9514a-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="9514a-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="9514a-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="9514a-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="9514a-421">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="9514a-421">Examples of invalid entries</span></span>

<span data-ttu-id="9514a-422">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="9514a-422">The following entries are invalid:</span></span>

- <span data-ttu-id="9514a-423">**Valori di dominio mancanti o non validi:**</span><span class="sxs-lookup"><span data-stu-id="9514a-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="9514a-424">contoso</span><span class="sxs-lookup"><span data-stu-id="9514a-424">contoso</span></span>
  - <span data-ttu-id="9514a-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="9514a-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="9514a-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="9514a-426">\*.com</span></span>
  - <span data-ttu-id="9514a-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="9514a-427">\*.pdf</span></span>

- <span data-ttu-id="9514a-428">**Caratteri jolly per il testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="9514a-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="9514a-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9514a-429">\*contoso.com</span></span>
  - <span data-ttu-id="9514a-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="9514a-430">contoso.com\*</span></span>
  - <span data-ttu-id="9514a-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9514a-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="9514a-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="9514a-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="9514a-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="9514a-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="9514a-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="9514a-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="9514a-435">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="9514a-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="9514a-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="9514a-436">contoso.com:443</span></span>
  - <span data-ttu-id="9514a-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="9514a-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="9514a-438">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="9514a-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="9514a-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="9514a-439">\*.\*</span></span>

- <span data-ttu-id="9514a-440">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="9514a-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="9514a-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="9514a-441">conto\*so.com</span></span>
  - <span data-ttu-id="9514a-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="9514a-442">conto~so.com</span></span>

- <span data-ttu-id="9514a-443">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="9514a-443">**Double wildcards**</span></span>

  - <span data-ttu-id="9514a-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="9514a-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="9514a-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="9514a-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9514a-446">Sintassi della coppia di domini per le voci del mittente contraffatte nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9514a-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9514a-447">Una coppia di domini per un mittente contraffatto nell'elenco tenant consentiti/bloccati utilizza la sintassi seguente: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="9514a-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="9514a-448">**Utente contraffatto:** questo valore include l'indirizzo di posta elettronica  dell'utente contraffatto visualizzato nella casella Da nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9514a-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="9514a-449">Questo indirizzo è noto anche come `5322.From` indirizzo.</span><span class="sxs-lookup"><span data-stu-id="9514a-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="9514a-450">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="9514a-450">Valid values include:</span></span>
  - <span data-ttu-id="9514a-451">Un singolo indirizzo di posta elettronica (ad esempio, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9514a-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="9514a-452">Un dominio di posta elettronica (ad esempio, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9514a-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="9514a-453">Il carattere jolly (ad esempio, \* ).</span><span class="sxs-lookup"><span data-stu-id="9514a-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="9514a-454">**Infrastruttura di invio:** questo valore indica l'origine dei messaggi provenienti dall'utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="9514a-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="9514a-455">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="9514a-455">Valid values include:</span></span>
  - <span data-ttu-id="9514a-456">Il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine (ad esempio, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="9514a-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="9514a-457">Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="9514a-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="9514a-458">Ecco alcuni esempi di coppie di domini valide per identificare i mittenti contraffatti:</span><span class="sxs-lookup"><span data-stu-id="9514a-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="9514a-459">Il numero massimo di voci del mittente contraffatto è 1000.</span><span class="sxs-lookup"><span data-stu-id="9514a-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="9514a-460">L'aggiunta di una coppia di domini consente o blocca *solo* la combinazione dell'utente contraffatto *e dell'infrastruttura* di invio.</span><span class="sxs-lookup"><span data-stu-id="9514a-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="9514a-461">Non consente la posta elettronica dell'utente contraffatto da alcuna origine, né consente la posta elettronica dall'origine dell'infrastruttura di invio per qualsiasi utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="9514a-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="9514a-462">Ad esempio, aggiungere una voce allow per la coppia di domini seguente:</span><span class="sxs-lookup"><span data-stu-id="9514a-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="9514a-463">**Dominio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="9514a-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="9514a-464">**Infrastruttura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="9514a-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="9514a-465">Solo i messaggi provenienti da tale dominio e *la* coppia di infrastruttura di invio possono effettuare lo spoofing.</span><span class="sxs-lookup"><span data-stu-id="9514a-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="9514a-466">Altri mittenti che tentano di eseguire lo spoofing gmail.com non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="9514a-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="9514a-467">I messaggi provenienti da mittenti in altri domini provenienti da tms.mx.com vengono controllati dalla spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="9514a-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
