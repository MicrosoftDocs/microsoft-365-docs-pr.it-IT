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
ms.openlocfilehash: dbd4694a7442b3898d24304dc78fc95c28c9a905
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394954"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-103">Gestire l'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="44c91-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="44c91-104">**Applies to**</span></span>
- [<span data-ttu-id="44c91-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="44c91-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="44c91-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="44c91-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="44c91-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44c91-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="44c91-108">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="44c91-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="44c91-109">Se l'organizzazione non dispone delle funzionalità di spoofing come descritto in questo articolo, vedere l'esperienza di gestione dello spoofing precedente in Gestire i mittenti contraffatti utilizzando i criteri di spoof intelligence e [spoof intelligence insight in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="44c91-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="44c91-110">Non è possibile configurare **gli** URL consentiti o gli elementi di file nell'elenco tenant consentiti/bloccati in questo momento.</span><span class="sxs-lookup"><span data-stu-id="44c91-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="44c91-111">Nelle Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile che non si sia d'accordo con il verdetto del filtro EOP.</span><span class="sxs-lookup"><span data-stu-id="44c91-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="44c91-112">Ad esempio, un buon messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non positivo potrebbe essere consentito (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="44c91-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="44c91-113">L'elenco Tenant consentiti/Microsoft 365 Defender consente di ignorare manualmente i Microsoft 365 di filtro.</span><span class="sxs-lookup"><span data-stu-id="44c91-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="44c91-114">L'elenco tenant consenti/blocca viene utilizzato durante il flusso di posta per i messaggi in arrivo (non si applica ai messaggi intra-org) e al momento dei clic dell'utente.</span><span class="sxs-lookup"><span data-stu-id="44c91-114">The Tenant Allow/Block List is used during mail flow for incoming messages (does not apply to intra-org messages) and at the time of user clicks.</span></span> <span data-ttu-id="44c91-115">È possibile specificare i seguenti tipi di sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="44c91-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="44c91-116">URL da bloccare.</span><span class="sxs-lookup"><span data-stu-id="44c91-116">URLs to block.</span></span>
- <span data-ttu-id="44c91-117">File da bloccare.</span><span class="sxs-lookup"><span data-stu-id="44c91-117">Files to block.</span></span>
- <span data-ttu-id="44c91-118">Mittenti contraffatti per consentire o bloccare.</span><span class="sxs-lookup"><span data-stu-id="44c91-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="44c91-119">Se si esegue l'override del verdetto consenti o blocca nell'analisi [di spoofing](learn-about-spoof-intelligence.md)intelligence, il mittente contraffatto diventa una voce di autorizzazione o blocco manuale che viene visualizzata solo nella scheda **Spoofing** nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="44c91-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="44c91-120">È inoltre possibile creare manualmente voci consentite o bloccate per i mittenti falsificati prima che siano rilevate dall'intelligence di spoofing.</span><span class="sxs-lookup"><span data-stu-id="44c91-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="44c91-121">In questo articolo viene descritto come configurare le voci nell'elenco tenant consentiti/bloccati nel portale di Microsoft 365 Defender o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="44c91-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="44c91-122">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="44c91-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="44c91-123">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="44c91-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="44c91-124">Per passare direttamente alla pagina **Tenant Allow/Block Lists,** utilizzare <https://security.microsoft.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="44c91-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="44c91-125">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="44c91-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="44c91-126">Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="44c91-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="44c91-127">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="44c91-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="44c91-128">I valori hash percettivi (pHash) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="44c91-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="44c91-129">I valori url disponibili sono descritti nella [sintassi dell'URL](#url-syntax-for-the-tenant-allowblock-list) per la sezione Elenco tenant consentiti/bloccati più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="44c91-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="44c91-130">L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="44c91-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="44c91-131">Il numero massimo di caratteri per ogni voce è:</span><span class="sxs-lookup"><span data-stu-id="44c91-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="44c91-132">Hash dei file = 64</span><span class="sxs-lookup"><span data-stu-id="44c91-132">File hashes = 64</span></span>
  - <span data-ttu-id="44c91-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="44c91-133">URL = 250</span></span>

- <span data-ttu-id="44c91-134">Una voce deve essere attiva entro 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="44c91-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="44c91-135">Per impostazione predefinita, le voci nell'elenco tenant consentiti/bloccati scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="44c91-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="44c91-136">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="44c91-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="44c91-137">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="44c91-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="44c91-138">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="44c91-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="44c91-139">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="44c91-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="44c91-140">**URL e file**:</span><span class="sxs-lookup"><span data-stu-id="44c91-140">**URLs and files**:</span></span>
    - <span data-ttu-id="44c91-141">Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="44c91-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="44c91-142">Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="44c91-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="44c91-143">**Spoofing**: una delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="44c91-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="44c91-144">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="44c91-144">**Organization Management**</span></span>
    - <span data-ttu-id="44c91-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span><span class="sxs-lookup"><span data-stu-id="44c91-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="44c91-146">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="44c91-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="44c91-147">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44c91-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="44c91-148">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="44c91-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="44c91-149">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="44c91-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-150">Utilizzare il portale Microsoft 365 Defender per creare voci url di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="44c91-151">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="44c91-152">Nella pagina **Elenco tenant consentiti/bloccati** verificare che la scheda **URL** sia selezionata e quindi fare clic su Blocca ![ icona ](../../media/m365-cc-sc-create-icon.png) **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="44c91-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="44c91-153">Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="44c91-154">**Aggiungere URL con caratteri jolly:** immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="44c91-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="44c91-155">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="44c91-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="44c91-156">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="44c91-157">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Rimuovi su per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. </span><span class="sxs-lookup"><span data-stu-id="44c91-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="44c91-158">oppure</span><span class="sxs-lookup"><span data-stu-id="44c91-158">or</span></span>

     - <span data-ttu-id="44c91-159">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="44c91-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="44c91-161">.</span><span class="sxs-lookup"><span data-stu-id="44c91-161">.</span></span>
   - <span data-ttu-id="44c91-162">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="44c91-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="44c91-163">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-164">Utilizzare il portale Microsoft 365 Defender per creare voci di file bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="44c91-165">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="44c91-166">Nella pagina **Elenco tenant consentiti/bloccati** selezionare la **scheda File** e quindi fare clic su Blocca ![ icona ](../../media/m365-cc-sc-create-icon.png) **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="44c91-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="44c91-167">Nel riquadro **a comparsa Blocca** file visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="44c91-168">**Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="44c91-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="44c91-169">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="44c91-170">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Rimuovi su per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. </span><span class="sxs-lookup"><span data-stu-id="44c91-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="44c91-171">oppure</span><span class="sxs-lookup"><span data-stu-id="44c91-171">or</span></span>

     - <span data-ttu-id="44c91-172">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="44c91-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="44c91-174">.</span><span class="sxs-lookup"><span data-stu-id="44c91-174">.</span></span>
   - <span data-ttu-id="44c91-175">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="44c91-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="44c91-176">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-177">Utilizzare il portale Microsoft 365 Defender per creare voci di mittente contraffatte consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-178">**Note**:</span><span class="sxs-lookup"><span data-stu-id="44c91-178">**Notes**:</span></span>

- <span data-ttu-id="44c91-179">Solo la _combinazione_ dell'utente contraffatto e dell'infrastruttura di invio definita nella coppia di domini è consentita o bloccata in modo specifico dallo spoofing. </span><span class="sxs-lookup"><span data-stu-id="44c91-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="44c91-180">Quando si configura una voce consenti o blocca per una coppia di domini, i messaggi di tale coppia di domini non vengono più visualizzati nelle informazioni di spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="44c91-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="44c91-181">Le voci per i mittenti contraffatti non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="44c91-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="44c91-182">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="44c91-183">Nella pagina **Elenco tenant consentiti/non consentiti** selezionare la scheda **Spoofing** e quindi fare clic su ![ Blocca icona ](../../media/m365-cc-sc-create-icon.png) **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="44c91-184">Nel riquadro **a comparsa Aggiungi nuove coppie** di domini visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="44c91-185">**Aggiungere nuove coppie di domini con caratteri jolly:** immettere una coppia di domini per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="44c91-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="44c91-186">Per informazioni dettagliate sulla sintassi per le voci dei mittenti falsificati, vedere la sintassi della coppia di domini per le voci del mittente contraffatte nella sezione [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="44c91-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="44c91-187">**Tipo di spoofing**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="44c91-188">**Interno**: il mittente contraffatto si trova in un dominio appartenente all'organizzazione (un [dominio accettato).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="44c91-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="44c91-189">**Esterno:** il mittente contraffatto si trova in un dominio esterno.</span><span class="sxs-lookup"><span data-stu-id="44c91-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="44c91-190">**Azione**: selezionare **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="44c91-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="44c91-191">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-192">Utilizzare il portale Microsoft 365 Defender per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="44c91-193">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="44c91-194">Selezionare la scheda desiderata.</span><span class="sxs-lookup"><span data-stu-id="44c91-194">Select the tab you want.</span></span> <span data-ttu-id="44c91-195">Le colonne disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="44c91-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="44c91-196">**URL**:</span><span class="sxs-lookup"><span data-stu-id="44c91-196">**URLs**:</span></span>
     - <span data-ttu-id="44c91-197">**Value**: URL.</span><span class="sxs-lookup"><span data-stu-id="44c91-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="44c91-198">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="44c91-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="44c91-199">**Ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="44c91-199">**Last updated**</span></span>
     - <span data-ttu-id="44c91-200">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="44c91-200">**Remove on**</span></span>
     - <span data-ttu-id="44c91-201">**Note**</span><span class="sxs-lookup"><span data-stu-id="44c91-201">**Notes**</span></span>
   - <span data-ttu-id="44c91-202">**File**</span><span class="sxs-lookup"><span data-stu-id="44c91-202">**Files**</span></span>
     - <span data-ttu-id="44c91-203">**Value**: Hash del file.</span><span class="sxs-lookup"><span data-stu-id="44c91-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="44c91-204">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="44c91-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="44c91-205">**Ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="44c91-205">**Last updated**</span></span>
     - <span data-ttu-id="44c91-206">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="44c91-206">**Remove on**</span></span>
     - <span data-ttu-id="44c91-207">**Note**</span><span class="sxs-lookup"><span data-stu-id="44c91-207">**Notes**</span></span>
   - <span data-ttu-id="44c91-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="44c91-208">**Spoofing**</span></span>
     - <span data-ttu-id="44c91-209">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="44c91-209">**Spoofed user**</span></span>
     - <span data-ttu-id="44c91-210">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="44c91-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="44c91-211">**Tipo di spoofing**: valore **Internal** o **External.**</span><span class="sxs-lookup"><span data-stu-id="44c91-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="44c91-212">**Action**: valore **Block o** **Allow.**</span><span class="sxs-lookup"><span data-stu-id="44c91-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="44c91-213">È possibile fare clic su un'intestazione di colonna per eseguire l'ordinamento crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="44c91-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="44c91-214">È possibile fare **clic su Gruppo** per raggruppare i risultati.</span><span class="sxs-lookup"><span data-stu-id="44c91-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="44c91-215">I valori disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="44c91-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="44c91-216">**URL:** è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="44c91-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="44c91-217">**File**: è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="44c91-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="44c91-218">**Spoofing**: è possibile raggruppare i risultati in base **al tipo Azione** o **Spoofing.**</span><span class="sxs-lookup"><span data-stu-id="44c91-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="44c91-219">Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="44c91-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="44c91-220">Al termine, fare clic su Cancella icona ![ ricerca ](../../media/m365-cc-sc-close-icon.png) **Cancella ricerca**.</span><span class="sxs-lookup"><span data-stu-id="44c91-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="44c91-221">Fare **clic su** Filtro per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="44c91-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="44c91-222">I valori disponibili **nel** riquadro a comparsa Filtro visualizzato dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="44c91-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="44c91-223">**URL**</span><span class="sxs-lookup"><span data-stu-id="44c91-223">**URLs**</span></span>
     - <span data-ttu-id="44c91-224">**Azione**</span><span class="sxs-lookup"><span data-stu-id="44c91-224">**Action**</span></span>
     - <span data-ttu-id="44c91-225">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="44c91-225">**Never expire**</span></span>
     - <span data-ttu-id="44c91-226">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="44c91-226">**Last updated date**</span></span>
     - <span data-ttu-id="44c91-227">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="44c91-227">**Remove on**</span></span>
   - <span data-ttu-id="44c91-228">**File**</span><span class="sxs-lookup"><span data-stu-id="44c91-228">**Files**</span></span>
     - <span data-ttu-id="44c91-229">**Azione**</span><span class="sxs-lookup"><span data-stu-id="44c91-229">**Action**</span></span>
     - <span data-ttu-id="44c91-230">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="44c91-230">**Never expire**</span></span>
     - <span data-ttu-id="44c91-231">**Ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="44c91-231">**Last updated**</span></span>
     - <span data-ttu-id="44c91-232">**Rimuovi su**</span><span class="sxs-lookup"><span data-stu-id="44c91-232">**Remove on**</span></span>
   - <span data-ttu-id="44c91-233">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="44c91-233">**Spoofing**</span></span>
     - <span data-ttu-id="44c91-234">**Azione**</span><span class="sxs-lookup"><span data-stu-id="44c91-234">**Action**</span></span>
     - <span data-ttu-id="44c91-235">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="44c91-235">**Spoof type**</span></span>

   <span data-ttu-id="44c91-236">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="44c91-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="44c91-237">Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="44c91-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-238">Utilizzare il Microsoft 365 Defender per modificare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="44c91-239">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="44c91-240">Selezionare la scheda contenente il tipo di voce che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="44c91-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="44c91-241">**URL**</span><span class="sxs-lookup"><span data-stu-id="44c91-241">**URLs**</span></span>
   - <span data-ttu-id="44c91-242">**File**</span><span class="sxs-lookup"><span data-stu-id="44c91-242">**Files**</span></span>
   - <span data-ttu-id="44c91-243">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="44c91-243">**Spoofing**</span></span>

3. <span data-ttu-id="44c91-244">Selezionare la voce che si desidera modificare e quindi fare clic su ![ Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="44c91-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="44c91-245">I valori che è possibile modificare nel riquadro a comparsa visualizzato dipendono dalla scheda selezionata nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="44c91-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="44c91-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="44c91-246">**URLs**</span></span>
     - <span data-ttu-id="44c91-247">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="44c91-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="44c91-248">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="44c91-248">**Optional note**</span></span>
   - <span data-ttu-id="44c91-249">**File**</span><span class="sxs-lookup"><span data-stu-id="44c91-249">**Files**</span></span>
     - <span data-ttu-id="44c91-250">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="44c91-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="44c91-251">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="44c91-251">**Optional note**</span></span>
   - <span data-ttu-id="44c91-252">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="44c91-252">**Spoofing**</span></span>
     - <span data-ttu-id="44c91-253">**Azione**: è possibile modificare il valore in **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="44c91-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="44c91-254">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="44c91-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-255">Utilizzare il portale Microsoft 365 Defender per rimuovere le voci dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="44c91-256">Nel portale Microsoft 365 Defender, passare a Criteri **& regole regole** criteri di minaccia \>  \> **Sezione** Tenant \> **Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="44c91-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="44c91-257">Selezionare la scheda contenente il tipo di voce che si desidera rimuovere:</span><span class="sxs-lookup"><span data-stu-id="44c91-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="44c91-258">**URL**</span><span class="sxs-lookup"><span data-stu-id="44c91-258">**URLs**</span></span>
   - <span data-ttu-id="44c91-259">**File**</span><span class="sxs-lookup"><span data-stu-id="44c91-259">**Files**</span></span>
   - <span data-ttu-id="44c91-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="44c91-260">**Spoofing**</span></span>

3. <span data-ttu-id="44c91-261">Selezionare la voce che si desidera rimuovere e quindi fare clic su ![ Elimina icona ](../../media/m365-cc-sc-delete-icon.png) **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="44c91-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="44c91-262">Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="44c91-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-263">Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-264">Usare PowerShell per aggiungere voci di file o URL di blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-265">Per aggiungere voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="44c91-266">In questo esempio viene aggiunta una voce del file di blocco per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="44c91-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="44c91-267">In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini(ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="44c91-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="44c91-268">Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="44c91-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="44c91-269">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="44c91-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-270">Usare PowerShell per aggiungere voci di mittente spoofing consentite o bloccate all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-271">Per aggiungere voci di mittente contraffatto nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="44c91-272">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="44c91-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-273">Utilizzare PowerShell per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-274">Per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="44c91-275">In questo esempio vengono restituite le informazioni per il valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="44c91-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="44c91-276">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="44c91-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="44c91-277">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="44c91-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-278">Utilizzare PowerShell per visualizzare le voci dei mittenti contraffatti consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-279">Per visualizzare le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="44c91-280">In questo esempio vengono restituite tutte le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="44c91-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="44c91-281">In questo esempio vengono restituite tutte le voci del mittente spoofing consentite interne.</span><span class="sxs-lookup"><span data-stu-id="44c91-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="44c91-282">In questo esempio vengono restituite tutte le voci di mittente contraffatte bloccate esterne.</span><span class="sxs-lookup"><span data-stu-id="44c91-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="44c91-283">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="44c91-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-284">Utilizzare PowerShell per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-285">Per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="44c91-286">In questo esempio viene modificata la data di scadenza della voce url di blocco specificata.</span><span class="sxs-lookup"><span data-stu-id="44c91-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="44c91-287">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="44c91-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-288">Utilizzare PowerShell per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-289">Per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="44c91-290">In questo esempio la voce del mittente contraffatto viene modificata da consenti a blocca.</span><span class="sxs-lookup"><span data-stu-id="44c91-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="44c91-291">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="44c91-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-292">Utilizzare PowerShell per rimuovere voci di URL o file dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-293">Per rimuovere le voci di file e URL dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="44c91-294">In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="44c91-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="44c91-295">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="44c91-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-296">Utilizzare PowerShell per rimuovere le voci consenti o blocca mittente contraffatte dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-297">Per rimuovere le voci del mittente di spoofing consentite o bloccate dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="44c91-298">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="44c91-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-299">Sintassi dell'URL per l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="44c91-300">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="44c91-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="44c91-301">Le estensioni dei nomi di file non sono consentite(ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="44c91-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="44c91-302">Unicode non è supportato, ma Punycode lo è.</span><span class="sxs-lookup"><span data-stu-id="44c91-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="44c91-303">I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="44c91-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="44c91-304">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="44c91-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="44c91-305">A sinistra del punto è presente almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="44c91-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="44c91-306">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="44c91-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="44c91-307">Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.</span><span class="sxs-lookup"><span data-stu-id="44c91-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="44c91-308">I sottopercorso non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="44c91-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="44c91-309">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="44c91-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="44c91-310">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="44c91-311">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="44c91-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="44c91-312">Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.</span><span class="sxs-lookup"><span data-stu-id="44c91-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="44c91-313">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="44c91-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="44c91-314">Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.</span><span class="sxs-lookup"><span data-stu-id="44c91-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="44c91-315">Tutti i percorsi secondari non sono implicati da un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="44c91-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="44c91-316">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="44c91-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="44c91-317">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="44c91-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="44c91-318">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="44c91-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="44c91-319">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="44c91-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="44c91-320">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="44c91-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="44c91-321">Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="44c91-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="44c91-322">Le voci URL contenenti protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.</span><span class="sxs-lookup"><span data-stu-id="44c91-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="44c91-323">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="44c91-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="44c91-324">Le virgolette (' o ") sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="44c91-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="44c91-325">Se possibile, un URL deve includere tutti i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="44c91-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="44c91-326">Scenari di immissione url</span><span class="sxs-lookup"><span data-stu-id="44c91-326">URL entry scenarios</span></span>

<span data-ttu-id="44c91-327">Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="44c91-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="44c91-328">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="44c91-328">Scenario: No wildcards</span></span>

<span data-ttu-id="44c91-329">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="44c91-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="44c91-330">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="44c91-331">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="44c91-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="44c91-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-332">abc-contoso.com</span></span>
  - <span data-ttu-id="44c91-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="44c91-333">contoso.com/a</span></span>
  - <span data-ttu-id="44c91-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="44c91-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="44c91-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="44c91-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-337">www.contoso.com</span></span>
  - <span data-ttu-id="44c91-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="44c91-339">**Corrispondenza blocco**:</span><span class="sxs-lookup"><span data-stu-id="44c91-339">**Block match**:</span></span>

  - <span data-ttu-id="44c91-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-340">contoso.com</span></span>
  - <span data-ttu-id="44c91-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="44c91-341">contoso.com/a</span></span>
  - <span data-ttu-id="44c91-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="44c91-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="44c91-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="44c91-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-345">www.contoso.com</span></span>
  - <span data-ttu-id="44c91-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="44c91-347">**Blocco non corrispondente**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="44c91-348">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="44c91-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="44c91-349">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="44c91-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="44c91-350">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="44c91-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="44c91-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-351">www.contoso.com</span></span>
  - <span data-ttu-id="44c91-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="44c91-353">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="44c91-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="44c91-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-354">123contoso.com</span></span>
  - <span data-ttu-id="44c91-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-355">contoso.com</span></span>
  - <span data-ttu-id="44c91-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="44c91-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="44c91-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="44c91-358">Scenario: carattere jolly destro all'inizio del percorso</span><span class="sxs-lookup"><span data-stu-id="44c91-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="44c91-359">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="44c91-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="44c91-360">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="44c91-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="44c91-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="44c91-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="44c91-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="44c91-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="44c91-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="44c91-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="44c91-364">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="44c91-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="44c91-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-365">contoso.com</span></span>
  - <span data-ttu-id="44c91-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="44c91-366">contoso.com/a</span></span>
  - <span data-ttu-id="44c91-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-367">www.contoso.com</span></span>
  - <span data-ttu-id="44c91-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="44c91-369">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="44c91-369">Scenario: Left tilde</span></span>

<span data-ttu-id="44c91-370">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="44c91-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="44c91-371">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="44c91-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="44c91-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-372">contoso.com</span></span>
  - <span data-ttu-id="44c91-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-373">www.contoso.com</span></span>
  - <span data-ttu-id="44c91-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="44c91-375">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="44c91-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="44c91-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-376">123contoso.com</span></span>
  - <span data-ttu-id="44c91-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="44c91-377">contoso.com/abc</span></span>
  - <span data-ttu-id="44c91-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="44c91-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="44c91-379">Scenario: suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="44c91-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="44c91-380">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="44c91-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="44c91-381">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="44c91-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="44c91-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="44c91-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="44c91-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="44c91-383">contoso.com/a</span></span>
  - <span data-ttu-id="44c91-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="44c91-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="44c91-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="44c91-385">contoso.com/ab</span></span>
  - <span data-ttu-id="44c91-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="44c91-386">contoso.com/b</span></span>
  - <span data-ttu-id="44c91-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="44c91-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="44c91-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="44c91-388">contoso.com/ba</span></span>

- <span data-ttu-id="44c91-389">**Allow not matched** e **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="44c91-390">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="44c91-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="44c91-391">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="44c91-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="44c91-392">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="44c91-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="44c91-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="44c91-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="44c91-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="44c91-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="44c91-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="44c91-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="44c91-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="44c91-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="44c91-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="44c91-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="44c91-398">**Allow not matched** e **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="44c91-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="44c91-399">Scenario: tilde sinistra e destra</span><span class="sxs-lookup"><span data-stu-id="44c91-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="44c91-400">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="44c91-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="44c91-401">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="44c91-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="44c91-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-402">contoso.com</span></span>
  - <span data-ttu-id="44c91-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="44c91-403">contoso.com/a</span></span>
  - <span data-ttu-id="44c91-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-404">www.contoso.com</span></span>
  - <span data-ttu-id="44c91-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="44c91-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="44c91-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="44c91-407">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="44c91-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="44c91-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-408">123contoso.com</span></span>
  - <span data-ttu-id="44c91-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="44c91-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="44c91-410">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="44c91-410">Scenario: IP address</span></span>

<span data-ttu-id="44c91-411">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="44c91-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="44c91-412">**Allow match** and **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="44c91-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="44c91-413">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="44c91-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="44c91-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="44c91-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="44c91-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="44c91-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="44c91-416">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="44c91-416">IP address with right wildcard</span></span>

<span data-ttu-id="44c91-417">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="44c91-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="44c91-418">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="44c91-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="44c91-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="44c91-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="44c91-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="44c91-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="44c91-421">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="44c91-421">Examples of invalid entries</span></span>

<span data-ttu-id="44c91-422">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="44c91-422">The following entries are invalid:</span></span>

- <span data-ttu-id="44c91-423">**Valori di dominio mancanti o non validi:**</span><span class="sxs-lookup"><span data-stu-id="44c91-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="44c91-424">contoso</span><span class="sxs-lookup"><span data-stu-id="44c91-424">contoso</span></span>
  - <span data-ttu-id="44c91-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="44c91-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="44c91-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="44c91-426">\*.com</span></span>
  - <span data-ttu-id="44c91-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="44c91-427">\*.pdf</span></span>

- <span data-ttu-id="44c91-428">**Caratteri jolly per il testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="44c91-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="44c91-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="44c91-429">\*contoso.com</span></span>
  - <span data-ttu-id="44c91-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="44c91-430">contoso.com\*</span></span>
  - <span data-ttu-id="44c91-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="44c91-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="44c91-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="44c91-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="44c91-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="44c91-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="44c91-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="44c91-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="44c91-435">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="44c91-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="44c91-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="44c91-436">contoso.com:443</span></span>
  - <span data-ttu-id="44c91-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="44c91-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="44c91-438">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="44c91-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="44c91-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="44c91-439">\*.\*</span></span>

- <span data-ttu-id="44c91-440">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="44c91-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="44c91-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="44c91-441">conto\*so.com</span></span>
  - <span data-ttu-id="44c91-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="44c91-442">conto~so.com</span></span>

- <span data-ttu-id="44c91-443">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="44c91-443">**Double wildcards**</span></span>

  - <span data-ttu-id="44c91-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="44c91-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="44c91-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="44c91-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="44c91-446">Sintassi della coppia di domini per le voci del mittente contraffatte nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="44c91-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="44c91-447">Una coppia di domini per un mittente contraffatto nell'elenco tenant consentiti/bloccati utilizza la sintassi seguente: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="44c91-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="44c91-448">**Utente contraffatto:** questo valore include l'indirizzo di posta elettronica  dell'utente contraffatto visualizzato nella casella Da nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="44c91-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="44c91-449">Questo indirizzo è noto anche come `5322.From` indirizzo.</span><span class="sxs-lookup"><span data-stu-id="44c91-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="44c91-450">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="44c91-450">Valid values include:</span></span>
  - <span data-ttu-id="44c91-451">Un singolo indirizzo di posta elettronica (ad esempio, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="44c91-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="44c91-452">Un dominio di posta elettronica (ad esempio, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="44c91-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="44c91-453">Il carattere jolly (ad esempio, \* ).</span><span class="sxs-lookup"><span data-stu-id="44c91-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="44c91-454">**Infrastruttura di invio:** questo valore indica l'origine dei messaggi provenienti dall'utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="44c91-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="44c91-455">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="44c91-455">Valid values include:</span></span>
  - <span data-ttu-id="44c91-456">Il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine (ad esempio, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="44c91-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="44c91-457">Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="44c91-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="44c91-458">Ecco alcuni esempi di coppie di domini valide per identificare i mittenti contraffatti:</span><span class="sxs-lookup"><span data-stu-id="44c91-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="44c91-459">Il numero massimo di voci del mittente contraffatto è 1000.</span><span class="sxs-lookup"><span data-stu-id="44c91-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="44c91-460">L'aggiunta di una coppia di domini consente o blocca *solo* la combinazione dell'utente contraffatto *e dell'infrastruttura* di invio.</span><span class="sxs-lookup"><span data-stu-id="44c91-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="44c91-461">Non consente la posta elettronica dell'utente contraffatto da alcuna origine, né consente la posta elettronica dall'origine dell'infrastruttura di invio per qualsiasi utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="44c91-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="44c91-462">Ad esempio, aggiungere una voce allow per la coppia di domini seguente:</span><span class="sxs-lookup"><span data-stu-id="44c91-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="44c91-463">**Dominio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="44c91-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="44c91-464">**Infrastruttura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="44c91-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="44c91-465">Solo i messaggi provenienti da tale dominio e *la* coppia di infrastruttura di invio possono effettuare lo spoofing.</span><span class="sxs-lookup"><span data-stu-id="44c91-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="44c91-466">Altri mittenti che tentano di eseguire lo spoofing gmail.com non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="44c91-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="44c91-467">I messaggi provenienti da mittenti in altri domini provenienti da tms.mx.com vengono controllati dalla spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="44c91-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
