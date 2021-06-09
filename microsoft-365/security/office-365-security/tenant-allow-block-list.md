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
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809180"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-103">Gestire l'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f05c7-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f05c7-104">**Applies to**</span></span>
- [<span data-ttu-id="f05c7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f05c7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f05c7-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="f05c7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f05c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f05c7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="f05c7-108">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f05c7-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="f05c7-109">Se l'organizzazione non dispone delle funzionalità di spoofing come descritto in questo articolo, vedere l'esperienza di gestione dello spoofing precedente in Gestire i mittenti contraffatti utilizzando i criteri di spoof intelligence e [spoof intelligence insight in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="f05c7-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="f05c7-110">Non è possibile configurare **gli** URL consentiti o gli elementi di file nell'elenco tenant consentiti/bloccati in questo momento.</span><span class="sxs-lookup"><span data-stu-id="f05c7-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="f05c7-111">Nelle Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile che non si sia d'accordo con il verdetto del filtro EOP.</span><span class="sxs-lookup"><span data-stu-id="f05c7-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f05c7-112">Ad esempio, un buon messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non positivo potrebbe essere consentito (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="f05c7-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f05c7-113">L'elenco Tenant consentiti/bloccati nel Centro sicurezza & conformità consente di ignorare manualmente i Microsoft 365 di filtro.</span><span class="sxs-lookup"><span data-stu-id="f05c7-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f05c7-114">L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento dei clic dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f05c7-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f05c7-115">È possibile specificare i seguenti tipi di sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="f05c7-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="f05c7-116">URL da bloccare.</span><span class="sxs-lookup"><span data-stu-id="f05c7-116">URLs to block.</span></span>
- <span data-ttu-id="f05c7-117">File da bloccare.</span><span class="sxs-lookup"><span data-stu-id="f05c7-117">Files to block.</span></span>
- <span data-ttu-id="f05c7-118">Mittenti contraffatti per consentire o bloccare.</span><span class="sxs-lookup"><span data-stu-id="f05c7-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="f05c7-119">Se si esegue l'override del verdetto consenti o blocca nell'analisi [di spoofing](learn-about-spoof-intelligence.md)intelligence, il mittente contraffatto diventa una voce di autorizzazione o blocco manuale che viene visualizzata solo nella scheda **Spoofing** nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="f05c7-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="f05c7-120">È inoltre possibile creare manualmente voci consentite o bloccate per i mittenti falsificati prima che siano rilevate dall'intelligence di spoofing.</span><span class="sxs-lookup"><span data-stu-id="f05c7-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="f05c7-121">In questo articolo viene descritto come configurare le voci nell'elenco consenti/blocca tenant nel Centro sicurezza e conformità di & o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="f05c7-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f05c7-122">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="f05c7-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f05c7-123">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f05c7-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f05c7-124">Per passare direttamente alla pagina **Elenco tenant consentiti/bloccati,** utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="f05c7-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f05c7-125">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="f05c7-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="f05c7-126">Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="f05c7-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="f05c7-127">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="f05c7-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="f05c7-128">I valori hash percettivi (pHash) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="f05c7-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="f05c7-129">I valori url disponibili sono descritti nella [sintassi dell'URL](#url-syntax-for-the-tenant-allowblock-list) per la sezione Elenco tenant consentiti/bloccati più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="f05c7-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="f05c7-130">L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="f05c7-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="f05c7-131">Il numero massimo di caratteri per ogni voce è:</span><span class="sxs-lookup"><span data-stu-id="f05c7-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="f05c7-132">Hash dei file = 64</span><span class="sxs-lookup"><span data-stu-id="f05c7-132">File hashes = 64</span></span>
  - <span data-ttu-id="f05c7-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="f05c7-133">URL = 250</span></span>

- <span data-ttu-id="f05c7-134">Una voce deve essere attiva entro 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="f05c7-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="f05c7-135">Per impostazione predefinita, le voci nell'elenco tenant consentiti/bloccati scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f05c7-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f05c7-136">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="f05c7-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f05c7-137">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f05c7-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f05c7-138">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f05c7-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f05c7-139">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f05c7-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f05c7-140">**URL e file**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-140">**URLs and files**:</span></span>
    - <span data-ttu-id="f05c7-141">Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="f05c7-142">Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f05c7-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="f05c7-143">**Spoofing**: una delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="f05c7-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="f05c7-144">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="f05c7-144">**Organization Management**</span></span>
    - <span data-ttu-id="f05c7-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="f05c7-146">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="f05c7-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="f05c7-147">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f05c7-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f05c7-148">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f05c7-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="f05c7-149">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f05c7-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-150">Utilizzare il Centro sicurezza & conformità per creare voci url di blocco nell'elenco Consenti/Blocca tenant</span><span class="sxs-lookup"><span data-stu-id="f05c7-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f05c7-151">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f05c7-152">Nella pagina **Elenco tenant consentiti/bloccati** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Blocca**</span><span class="sxs-lookup"><span data-stu-id="f05c7-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="f05c7-153">Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f05c7-154">**Aggiungi URL da bloccare:** immetti un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="f05c7-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="f05c7-155">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="f05c7-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="f05c7-156">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f05c7-157">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="f05c7-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="f05c7-158">oppure</span><span class="sxs-lookup"><span data-stu-id="f05c7-158">or</span></span>

     - <span data-ttu-id="f05c7-159">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="f05c7-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="f05c7-161">.</span><span class="sxs-lookup"><span data-stu-id="f05c7-161">.</span></span>

   - <span data-ttu-id="f05c7-162">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="f05c7-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f05c7-163">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-164">Usare il Centro sicurezza & conformità per creare voci di file di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f05c7-165">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f05c7-166">Nella pagina **Elenco tenant consentiti/bloccati** selezionare la **scheda File** e quindi fare clic su **Blocca.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="f05c7-167">Nel riquadro **a comparsa Aggiungi file da** bloccare, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f05c7-168">**Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="f05c7-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f05c7-169">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f05c7-170">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="f05c7-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f05c7-171">oppure</span><span class="sxs-lookup"><span data-stu-id="f05c7-171">or</span></span>

     - <span data-ttu-id="f05c7-172">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="f05c7-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="f05c7-174">.</span><span class="sxs-lookup"><span data-stu-id="f05c7-174">.</span></span>

   - <span data-ttu-id="f05c7-175">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="f05c7-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f05c7-176">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-177">Usare il Centro sicurezza & conformità per creare voci di mittente contraffatte consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-178">**Note**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-178">**Notes**:</span></span>

- <span data-ttu-id="f05c7-179">Solo la _combinazione_ dell'utente contraffatto e dell'infrastruttura di invio definita nella coppia di domini è consentita o bloccata in modo specifico dallo spoofing. </span><span class="sxs-lookup"><span data-stu-id="f05c7-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="f05c7-180">Quando si configura una voce consenti o blocca per una coppia di domini, i messaggi di tale coppia di domini non vengono più visualizzati nelle informazioni di spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="f05c7-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="f05c7-181">Le voci per i mittenti contraffatti non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="f05c7-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="f05c7-182">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f05c7-183">Nella pagina **Elenco tenant consentiti/non consentiti** selezionare la **scheda Spoofing** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="f05c7-184">Nel riquadro **a comparsa Aggiungi nuove coppie** di domini visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f05c7-185">**Aggiungere nuove coppie di domini con caratteri jolly:** immettere una coppia di domini per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="f05c7-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="f05c7-186">Per informazioni dettagliate sulla sintassi per le voci dei mittenti falsificati, vedere la sintassi della coppia di domini per le voci del mittente contraffatte nella sezione [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="f05c7-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="f05c7-187">**Tipo di spoofing**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="f05c7-188">**Interno**: il mittente contraffatto si trova in un dominio appartenente all'organizzazione (un [dominio accettato).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="f05c7-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="f05c7-189">**Esterno:** il mittente contraffatto si trova in un dominio esterno.</span><span class="sxs-lookup"><span data-stu-id="f05c7-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="f05c7-190">**Azione**: selezionare **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="f05c7-191">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-192">Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f05c7-193">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f05c7-194">Selezionare la scheda desiderata.</span><span class="sxs-lookup"><span data-stu-id="f05c7-194">Select the tab you want.</span></span> <span data-ttu-id="f05c7-195">Le colonne disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="f05c7-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="f05c7-196">**URL**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-196">**URLs**:</span></span>
     - <span data-ttu-id="f05c7-197">**Value**: URL.</span><span class="sxs-lookup"><span data-stu-id="f05c7-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="f05c7-198">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="f05c7-199">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="f05c7-199">**Last updated date**</span></span>
     - <span data-ttu-id="f05c7-200">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="f05c7-200">**Expiration date**</span></span>
     - <span data-ttu-id="f05c7-201">**Nota**</span><span class="sxs-lookup"><span data-stu-id="f05c7-201">**Note**</span></span>

   - <span data-ttu-id="f05c7-202">**File**</span><span class="sxs-lookup"><span data-stu-id="f05c7-202">**Files**</span></span>
     - <span data-ttu-id="f05c7-203">**Value**: Hash del file.</span><span class="sxs-lookup"><span data-stu-id="f05c7-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="f05c7-204">**Action**: valore **Block.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="f05c7-205">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="f05c7-205">**Last updated date**</span></span>
     - <span data-ttu-id="f05c7-206">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="f05c7-206">**Expiration date**</span></span>
     - <span data-ttu-id="f05c7-207">**Nota**</span><span class="sxs-lookup"><span data-stu-id="f05c7-207">**Note**</span></span>

   - <span data-ttu-id="f05c7-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="f05c7-208">**Spoofing**</span></span>
     - <span data-ttu-id="f05c7-209">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="f05c7-209">**Spoofed user**</span></span>
     - <span data-ttu-id="f05c7-210">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="f05c7-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="f05c7-211">**Tipo di spoofing**: valore **Internal** o **External.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="f05c7-212">**Action**: valore **Block o** **Allow.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="f05c7-213">È possibile fare clic su un'intestazione di colonna per eseguire l'ordinamento crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="f05c7-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="f05c7-214">È possibile fare **clic su Gruppo** per raggruppare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f05c7-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="f05c7-215">I valori disponibili dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="f05c7-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="f05c7-216">**URL:** è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="f05c7-217">**File**: è possibile raggruppare i risultati in base a **Action.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="f05c7-218">**Domini mittente per bypass BCL:** **il** gruppo non è disponibile in questa scheda.</span><span class="sxs-lookup"><span data-stu-id="f05c7-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="f05c7-219">**Spoofing**: è possibile raggruppare i risultati in base **al tipo Azione** o **Spoofing.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="f05c7-220">Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="f05c7-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f05c7-221">Al termine, fare clic su Cancella **ricerca** ![ Cancella icona di ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ricerca.</span><span class="sxs-lookup"><span data-stu-id="f05c7-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="f05c7-222">Fare **clic su** Filtro per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f05c7-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="f05c7-223">I valori disponibili **nel** riquadro a comparsa Filtro visualizzato dipendono dalla scheda selezionata:</span><span class="sxs-lookup"><span data-stu-id="f05c7-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="f05c7-224">**URL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-224">**URLs**</span></span>
     - <span data-ttu-id="f05c7-225">**Azione**</span><span class="sxs-lookup"><span data-stu-id="f05c7-225">**Action**</span></span>
     - <span data-ttu-id="f05c7-226">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="f05c7-226">**Never expire**</span></span>
     - <span data-ttu-id="f05c7-227">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="f05c7-227">**Last updated date**</span></span>
     - <span data-ttu-id="f05c7-228">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="f05c7-228">**Expiration date**</span></span>

   - <span data-ttu-id="f05c7-229">**File**</span><span class="sxs-lookup"><span data-stu-id="f05c7-229">**Files**</span></span>
     - <span data-ttu-id="f05c7-230">**Azione**</span><span class="sxs-lookup"><span data-stu-id="f05c7-230">**Action**</span></span>
     - <span data-ttu-id="f05c7-231">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="f05c7-231">**Never expire**</span></span>
     - <span data-ttu-id="f05c7-232">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="f05c7-232">**Last updated date**</span></span>
     - <span data-ttu-id="f05c7-233">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="f05c7-233">**Expiration date**</span></span>

   - <span data-ttu-id="f05c7-234">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="f05c7-235">**Non scadere mai**</span><span class="sxs-lookup"><span data-stu-id="f05c7-235">**Never expire**</span></span>
     - <span data-ttu-id="f05c7-236">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="f05c7-236">**Last updated date**</span></span>
     - <span data-ttu-id="f05c7-237">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="f05c7-237">**Expiration date**</span></span>

   - <span data-ttu-id="f05c7-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="f05c7-238">**Spoofing**</span></span>
     - <span data-ttu-id="f05c7-239">**Azione**</span><span class="sxs-lookup"><span data-stu-id="f05c7-239">**Action**</span></span>
     - <span data-ttu-id="f05c7-240">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="f05c7-240">**Spoof type**</span></span>

   <span data-ttu-id="f05c7-241">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="f05c7-242">Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-243">Utilizzare il Centro sicurezza & conformità per modificare le voci nell'elenco Tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f05c7-244">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f05c7-245">Selezionare la scheda contenente il tipo di voce che si desidera modificare:</span><span class="sxs-lookup"><span data-stu-id="f05c7-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="f05c7-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-246">**URLs**</span></span>
   - <span data-ttu-id="f05c7-247">**File**</span><span class="sxs-lookup"><span data-stu-id="f05c7-247">**Files**</span></span>
   - <span data-ttu-id="f05c7-248">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="f05c7-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="f05c7-249">**Spoofing**</span></span>

3. <span data-ttu-id="f05c7-250">Selezionare la voce che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="f05c7-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="f05c7-251">I valori che è possibile modificare nel riquadro a comparsa visualizzato dipendono dalla scheda selezionata nel passaggio precedente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="f05c7-252">**URL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-252">**URLs**</span></span>
     - <span data-ttu-id="f05c7-253">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="f05c7-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="f05c7-254">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="f05c7-254">**Optional note**</span></span>

   - <span data-ttu-id="f05c7-255">**File**</span><span class="sxs-lookup"><span data-stu-id="f05c7-255">**Files**</span></span>
     - <span data-ttu-id="f05c7-256">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="f05c7-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="f05c7-257">**Nota facoltativa**</span><span class="sxs-lookup"><span data-stu-id="f05c7-257">**Optional note**</span></span>

   - <span data-ttu-id="f05c7-258">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="f05c7-259">**Non scadere mai e/o** data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="f05c7-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="f05c7-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="f05c7-260">**Spoofing**</span></span>
     - <span data-ttu-id="f05c7-261">**Azione**: è possibile modificare il valore in **Consenti** o **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="f05c7-262">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-263">Utilizzare il Centro sicurezza & conformità per rimuovere le voci dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f05c7-264">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f05c7-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f05c7-265">Selezionare la scheda contenente il tipo di voce che si desidera rimuovere:</span><span class="sxs-lookup"><span data-stu-id="f05c7-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="f05c7-266">**URL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-266">**URLs**</span></span>
   - <span data-ttu-id="f05c7-267">**File**</span><span class="sxs-lookup"><span data-stu-id="f05c7-267">**Files**</span></span>
   - <span data-ttu-id="f05c7-268">**Domini mittente per bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="f05c7-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="f05c7-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="f05c7-269">**Spoofing**</span></span>

3. <span data-ttu-id="f05c7-270">Selezionare la voce che si desidera rimuovere e quindi fare clic su **Elimina Icona** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Elimina.</span><span class="sxs-lookup"><span data-stu-id="f05c7-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f05c7-271">Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="f05c7-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-272">Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-273">Usare PowerShell per aggiungere voci di file o URL di blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-274">Per aggiungere voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="f05c7-275">In questo esempio viene aggiunta una voce del file di blocco per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="f05c7-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="f05c7-276">In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini(ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f05c7-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f05c7-277">Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f05c7-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="f05c7-278">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f05c7-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-279">Usare PowerShell per aggiungere voci di mittente spoofing consentite o bloccate all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-280">Per aggiungere voci di mittente contraffatto nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="f05c7-281">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="f05c7-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-282">Utilizzare PowerShell per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-283">Per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="f05c7-284">In questo esempio vengono restituite le informazioni per il valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="f05c7-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="f05c7-285">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="f05c7-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="f05c7-286">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f05c7-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-287">Utilizzare PowerShell per visualizzare le voci dei mittenti contraffatti consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-288">Per visualizzare le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="f05c7-289">In questo esempio vengono restituite tutte le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="f05c7-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="f05c7-290">In questo esempio vengono restituite tutte le voci del mittente spoofing consentite interne.</span><span class="sxs-lookup"><span data-stu-id="f05c7-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="f05c7-291">In questo esempio vengono restituite tutte le voci di mittente contraffatte bloccate esterne.</span><span class="sxs-lookup"><span data-stu-id="f05c7-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="f05c7-292">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="f05c7-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-293">Utilizzare PowerShell per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-294">Per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="f05c7-295">In questo esempio viene modificata la data di scadenza della voce url di blocco specificata.</span><span class="sxs-lookup"><span data-stu-id="f05c7-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="f05c7-296">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f05c7-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-297">Utilizzare PowerShell per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-298">Per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="f05c7-299">In questo esempio la voce del mittente contraffatto viene modificata da consenti a blocca.</span><span class="sxs-lookup"><span data-stu-id="f05c7-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="f05c7-300">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="f05c7-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-301">Utilizzare PowerShell per rimuovere voci di URL o file dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-302">Per rimuovere le voci di file e URL dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f05c7-303">In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="f05c7-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f05c7-304">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f05c7-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-305">Utilizzare PowerShell per rimuovere le voci consenti o blocca mittente contraffatte dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-306">Per rimuovere le voci del mittente di spoofing consentite o bloccate dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f05c7-307">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="f05c7-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-308">Sintassi dell'URL per l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f05c7-309">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="f05c7-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f05c7-310">Le estensioni dei nomi di file non sono consentite(ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="f05c7-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f05c7-311">Unicode non è supportato, ma Punycode lo è.</span><span class="sxs-lookup"><span data-stu-id="f05c7-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f05c7-312">I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="f05c7-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="f05c7-313">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="f05c7-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="f05c7-314">A sinistra del punto è presente almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="f05c7-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f05c7-315">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="f05c7-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f05c7-316">Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.</span><span class="sxs-lookup"><span data-stu-id="f05c7-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f05c7-317">I sottopercorso non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="f05c7-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="f05c7-318">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f05c7-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f05c7-319">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f05c7-320">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="f05c7-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f05c7-321">Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.</span><span class="sxs-lookup"><span data-stu-id="f05c7-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f05c7-322">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="f05c7-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f05c7-323">Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.</span><span class="sxs-lookup"><span data-stu-id="f05c7-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f05c7-324">Tutti i percorsi secondari non sono implicati da un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="f05c7-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f05c7-325">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f05c7-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f05c7-326">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="f05c7-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f05c7-327">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="f05c7-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f05c7-328">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f05c7-329">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="f05c7-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f05c7-330">Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f05c7-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f05c7-331">Le voci URL contenenti protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.</span><span class="sxs-lookup"><span data-stu-id="f05c7-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f05c7-332">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="f05c7-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f05c7-333">Le virgolette (' o ") sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="f05c7-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f05c7-334">Se possibile, un URL deve includere tutti i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="f05c7-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f05c7-335">Scenari di immissione url</span><span class="sxs-lookup"><span data-stu-id="f05c7-335">URL entry scenarios</span></span>

<span data-ttu-id="f05c7-336">Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f05c7-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f05c7-337">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="f05c7-337">Scenario: No wildcards</span></span>

<span data-ttu-id="f05c7-338">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f05c7-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f05c7-339">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f05c7-340">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="f05c7-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-341">abc-contoso.com</span></span>
  - <span data-ttu-id="f05c7-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-342">contoso.com/a</span></span>
  - <span data-ttu-id="f05c7-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="f05c7-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="f05c7-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f05c7-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-346">www.contoso.com</span></span>
  - <span data-ttu-id="f05c7-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f05c7-348">**Corrispondenza blocco**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-348">**Block match**:</span></span>

  - <span data-ttu-id="f05c7-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-349">contoso.com</span></span>
  - <span data-ttu-id="f05c7-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-350">contoso.com/a</span></span>
  - <span data-ttu-id="f05c7-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="f05c7-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="f05c7-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f05c7-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-354">www.contoso.com</span></span>
  - <span data-ttu-id="f05c7-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f05c7-356">**Blocco non corrispondente**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f05c7-357">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="f05c7-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f05c7-358">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f05c7-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f05c7-359">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f05c7-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-360">www.contoso.com</span></span>
  - <span data-ttu-id="f05c7-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f05c7-362">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f05c7-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-363">123contoso.com</span></span>
  - <span data-ttu-id="f05c7-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-364">contoso.com</span></span>
  - <span data-ttu-id="f05c7-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="f05c7-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f05c7-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f05c7-367">Scenario: carattere jolly destro all'inizio del percorso</span><span class="sxs-lookup"><span data-stu-id="f05c7-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f05c7-368">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f05c7-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f05c7-369">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f05c7-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f05c7-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="f05c7-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f05c7-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f05c7-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f05c7-373">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f05c7-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-374">contoso.com</span></span>
  - <span data-ttu-id="f05c7-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-375">contoso.com/a</span></span>
  - <span data-ttu-id="f05c7-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-376">www.contoso.com</span></span>
  - <span data-ttu-id="f05c7-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="f05c7-378">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="f05c7-378">Scenario: Left tilde</span></span>

<span data-ttu-id="f05c7-379">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f05c7-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f05c7-380">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f05c7-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-381">contoso.com</span></span>
  - <span data-ttu-id="f05c7-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-382">www.contoso.com</span></span>
  - <span data-ttu-id="f05c7-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f05c7-384">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f05c7-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-385">123contoso.com</span></span>
  - <span data-ttu-id="f05c7-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f05c7-386">contoso.com/abc</span></span>
  - <span data-ttu-id="f05c7-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f05c7-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f05c7-388">Scenario: suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="f05c7-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f05c7-389">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f05c7-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f05c7-390">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f05c7-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f05c7-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-392">contoso.com/a</span></span>
  - <span data-ttu-id="f05c7-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f05c7-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f05c7-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f05c7-394">contoso.com/ab</span></span>
  - <span data-ttu-id="f05c7-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f05c7-395">contoso.com/b</span></span>
  - <span data-ttu-id="f05c7-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f05c7-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f05c7-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f05c7-397">contoso.com/ba</span></span>

- <span data-ttu-id="f05c7-398">**Allow not matched** e **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f05c7-399">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="f05c7-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f05c7-400">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f05c7-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f05c7-401">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f05c7-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f05c7-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f05c7-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f05c7-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f05c7-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="f05c7-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f05c7-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f05c7-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f05c7-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f05c7-407">**Allow not matched** e **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f05c7-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f05c7-408">Scenario: tilde sinistra e destra</span><span class="sxs-lookup"><span data-stu-id="f05c7-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f05c7-409">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f05c7-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f05c7-410">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f05c7-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-411">contoso.com</span></span>
  - <span data-ttu-id="f05c7-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-412">contoso.com/a</span></span>
  - <span data-ttu-id="f05c7-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-413">www.contoso.com</span></span>
  - <span data-ttu-id="f05c7-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f05c7-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="f05c7-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f05c7-416">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f05c7-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-417">123contoso.com</span></span>
  - <span data-ttu-id="f05c7-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f05c7-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f05c7-419">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="f05c7-419">Scenario: IP address</span></span>

<span data-ttu-id="f05c7-420">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f05c7-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f05c7-421">**Allow match** and **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f05c7-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f05c7-422">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f05c7-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="f05c7-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f05c7-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f05c7-425">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="f05c7-425">IP address with right wildcard</span></span>

<span data-ttu-id="f05c7-426">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f05c7-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f05c7-427">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f05c7-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f05c7-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="f05c7-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f05c7-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f05c7-430">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="f05c7-430">Examples of invalid entries</span></span>

<span data-ttu-id="f05c7-431">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="f05c7-431">The following entries are invalid:</span></span>

- <span data-ttu-id="f05c7-432">**Valori di dominio mancanti o non validi:**</span><span class="sxs-lookup"><span data-stu-id="f05c7-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f05c7-433">contoso</span><span class="sxs-lookup"><span data-stu-id="f05c7-433">contoso</span></span>
  - <span data-ttu-id="f05c7-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="f05c7-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-435">\*.com</span></span>
  - <span data-ttu-id="f05c7-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="f05c7-436">\*.pdf</span></span>

- <span data-ttu-id="f05c7-437">**Caratteri jolly per il testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f05c7-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-438">\*contoso.com</span></span>
  - <span data-ttu-id="f05c7-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-439">contoso.com\*</span></span>
  - <span data-ttu-id="f05c7-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f05c7-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="f05c7-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="f05c7-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="f05c7-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="f05c7-444">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f05c7-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f05c7-445">contoso.com:443</span></span>
  - <span data-ttu-id="f05c7-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f05c7-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="f05c7-447">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f05c7-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-448">\*.\*</span></span>

- <span data-ttu-id="f05c7-449">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="f05c7-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f05c7-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-450">conto\*so.com</span></span>
  - <span data-ttu-id="f05c7-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-451">conto~so.com</span></span>

- <span data-ttu-id="f05c7-452">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="f05c7-452">**Double wildcards**</span></span>

  - <span data-ttu-id="f05c7-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f05c7-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f05c7-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f05c7-455">Sintassi della coppia di domini per le voci del mittente contraffatte nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f05c7-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f05c7-456">Una coppia di domini per un mittente contraffatto nell'elenco tenant consentiti/bloccati utilizza la sintassi seguente: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="f05c7-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="f05c7-457">**Utente contraffatto:** questo valore include l'indirizzo di posta elettronica  dell'utente contraffatto visualizzato nella casella Da nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f05c7-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="f05c7-458">Questo indirizzo è noto anche come `5322.From` indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f05c7-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="f05c7-459">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="f05c7-459">Valid values include:</span></span>
  - <span data-ttu-id="f05c7-460">Un singolo indirizzo di posta elettronica (ad esempio, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f05c7-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="f05c7-461">Un dominio di posta elettronica (ad esempio, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f05c7-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="f05c7-462">Il carattere jolly (ad esempio, \* ).</span><span class="sxs-lookup"><span data-stu-id="f05c7-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="f05c7-463">**Infrastruttura di invio:** questo valore indica l'origine dei messaggi provenienti dall'utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="f05c7-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="f05c7-464">Tra i valori validi sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="f05c7-464">Valid values include:</span></span>
  - <span data-ttu-id="f05c7-465">Il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine (ad esempio, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="f05c7-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="f05c7-466">Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="f05c7-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="f05c7-467">Ecco alcuni esempi di coppie di domini valide per identificare i mittenti contraffatti:</span><span class="sxs-lookup"><span data-stu-id="f05c7-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="f05c7-468">Il numero massimo di voci del mittente contraffatto è 1000.</span><span class="sxs-lookup"><span data-stu-id="f05c7-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="f05c7-469">L'aggiunta di una coppia di domini consente o blocca *solo* la combinazione dell'utente contraffatto *e dell'infrastruttura* di invio.</span><span class="sxs-lookup"><span data-stu-id="f05c7-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="f05c7-470">Non consente la posta elettronica dell'utente contraffatto da alcuna origine, né consente la posta elettronica dall'origine dell'infrastruttura di invio per qualsiasi utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="f05c7-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="f05c7-471">Ad esempio, aggiungere una voce allow per la coppia di domini seguente:</span><span class="sxs-lookup"><span data-stu-id="f05c7-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="f05c7-472">**Dominio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="f05c7-473">**Infrastruttura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="f05c7-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="f05c7-474">Solo i messaggi provenienti da tale dominio e *la* coppia di infrastruttura di invio possono effettuare lo spoofing.</span><span class="sxs-lookup"><span data-stu-id="f05c7-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="f05c7-475">Altri mittenti che tentano di eseguire lo spoofing gmail.com non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="f05c7-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="f05c7-476">I messaggi provenienti da mittenti in altri domini provenienti da tms.mx.com vengono controllati dalla spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="f05c7-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
