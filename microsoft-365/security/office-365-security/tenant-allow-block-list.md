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
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587588"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-103">Gestire l'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9a5e4-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-104">**Applies to**</span></span>
- [<span data-ttu-id="9a5e4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9a5e4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9a5e4-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="9a5e4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9a5e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a5e4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="9a5e4-108">Non è possibile **configurare gli** elementi consentiti nell'elenco tenant consentiti/bloccati in questo momento.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="9a5e4-109">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile che non si sia d'accordo con il verdetto del filtro EOP.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="9a5e4-110">Ad esempio, un buon messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non positivo potrebbe essere consentito (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="9a5e4-111">L'elenco Tenant consentiti/bloccati nel Centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtro di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="9a5e4-112">L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento dei clic dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="9a5e4-113">È possibile specificare URL o file da bloccare sempre.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="9a5e4-114">In questo articolo viene descritto come configurare le voci nell'elenco consenti/blocca tenant nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9a5e4-115">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9a5e4-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9a5e4-116">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9a5e4-117">Per passare direttamente alla pagina **Elenco tenant consentiti/bloccati,** utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="9a5e4-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="9a5e4-118">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="9a5e4-119">Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="9a5e4-120">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="9a5e4-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="9a5e4-121">I valori hash percettivi (pHash) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="9a5e4-122">I valori url disponibili sono descritti nella [sintassi dell'URL](#url-syntax-for-the-tenant-allowblock-list) per la sezione Elenco tenant consentiti/bloccati più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="9a5e4-123">L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="9a5e4-124">Il numero massimo di caratteri per ogni voce è:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="9a5e4-125">Hash dei file = 64</span><span class="sxs-lookup"><span data-stu-id="9a5e4-125">File hashes = 64</span></span>
  - <span data-ttu-id="9a5e4-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="9a5e4-126">URL = 250</span></span>

- <span data-ttu-id="9a5e4-127">Una voce deve essere attiva entro 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="9a5e4-128">Per impostazione predefinita, le voci nell'elenco tenant consentiti/bloccati scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="9a5e4-129">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="9a5e4-130">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9a5e4-131">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9a5e4-132">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9a5e4-133">Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9a5e4-134">Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="9a5e4-135">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="9a5e4-136">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9a5e4-137">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="9a5e4-138">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-139">Utilizzare il Centro sicurezza & conformità per creare voci URL nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9a5e4-140">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="9a5e4-141">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9a5e4-142">Nella pagina **Elenco tenant consentiti/bloccati** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Blocca**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="9a5e4-143">Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9a5e4-144">**Aggiungi URL da bloccare:** immetti un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="9a5e4-145">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9a5e4-146">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="9a5e4-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="9a5e4-147">oppure</span><span class="sxs-lookup"><span data-stu-id="9a5e4-147">or</span></span>

     - <span data-ttu-id="9a5e4-148">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="9a5e4-150">.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-150">.</span></span>

   - <span data-ttu-id="9a5e4-151">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9a5e4-152">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-153">Utilizzare il Centro sicurezza & conformità per creare voci di file nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9a5e4-154">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9a5e4-155">Nella pagina **Elenco tenant consentiti/bloccati** selezionare **la scheda File** e quindi fare clic su **Blocca.**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="9a5e4-156">Nel riquadro **a comparsa Aggiungi file da** bloccare, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9a5e4-157">**Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="9a5e4-158">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9a5e4-159">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="9a5e4-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="9a5e4-160">oppure</span><span class="sxs-lookup"><span data-stu-id="9a5e4-160">or</span></span>

     - <span data-ttu-id="9a5e4-161">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="9a5e4-163">.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-163">.</span></span>

   - <span data-ttu-id="9a5e4-164">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9a5e4-165">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-166">Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9a5e4-167">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9a5e4-168">Selezionare la **scheda URL** o **La scheda** File.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="9a5e4-169">Fare clic sulle intestazioni di colonna seguenti per eseguire l'ordinamento crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="9a5e4-170">**Valore**: URL o hash del file.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="9a5e4-171">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-171">**Last updated date**</span></span>
- <span data-ttu-id="9a5e4-172">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-172">**Expiration date**</span></span>
- <span data-ttu-id="9a5e4-173">**Nota**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-173">**Note**</span></span>

<span data-ttu-id="9a5e4-174">Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="9a5e4-175">Al termine, fare clic su Cancella **ricerca** ![ Cancella icona di ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ricerca.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="9a5e4-176">Fare clic **su Filtro.**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-176">Click **Filter**.</span></span> <span data-ttu-id="9a5e4-177">Nel riquadro **a** comparsa Filtro visualizzato configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="9a5e4-178">**Non scadere mai**: Selezionare Disattivato: ![ Attiva o ](../../media/scc-toggle-off.png) disattiva: ![ Attiva/Disattiva. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="9a5e4-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="9a5e4-179">**Last updated**: Selezionare una data di inizio (**From**), una data di fine (**To**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="9a5e4-180">**Data di** scadenza: selezionare una data di inizio (**Da**), una data di fine (**A**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="9a5e4-181">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="9a5e4-182">Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-183">Utilizzare il Centro sicurezza & conformità per modificare le voci di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9a5e4-184">Non è possibile modificare l'URL o i valori di file bloccati esistenti all'interno di una voce.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="9a5e4-185">Per modificare questi valori, è necessario eliminare e ricreare la voce.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="9a5e4-186">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9a5e4-187">Selezionare la **scheda URL** o **La scheda** File.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="9a5e4-188">Selezionare la voce di blocco che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="9a5e4-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="9a5e4-189">Nel riquadro a comparsa visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9a5e4-190">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9a5e4-191">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per la voce. </span><span class="sxs-lookup"><span data-stu-id="9a5e4-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="9a5e4-192">oppure</span><span class="sxs-lookup"><span data-stu-id="9a5e4-192">or</span></span>

     - <span data-ttu-id="9a5e4-193">Spostare l'interruttore a destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="9a5e4-195">.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-195">.</span></span>

   - <span data-ttu-id="9a5e4-196">**Nota facoltativa:** immettere un testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="9a5e4-197">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-198">Utilizzare il Centro sicurezza & conformità per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9a5e4-199">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9a5e4-200">Selezionare la **scheda URL** o **La scheda** File.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="9a5e4-201">Selezionare la voce di blocco che si desidera rimuovere e quindi fare clic su **Elimina** ![ Icona ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Elimina.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="9a5e4-202">Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-203">Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per configurare l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-204">Usare PowerShell per aggiungere voci di blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="9a5e4-205">Per aggiungere voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9a5e4-206">In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini(ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="9a5e4-207">Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="9a5e4-208">In questo esempio viene aggiunta una voce del file di blocco per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="9a5e4-209">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9a5e4-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-210">Utilizzare PowerShell per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9a5e4-211">Per visualizzare le voci nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="9a5e4-212">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="9a5e4-213">In questo esempio vengono restituite le informazioni per il valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="9a5e4-214">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-215">Utilizzare PowerShell per modificare le voci di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9a5e4-216">Non è possibile modificare l'URL o i valori di file esistenti all'interno di una voce di blocco.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="9a5e4-217">Per modificare questi valori, è necessario eliminare e ricreare la voce.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="9a5e4-218">Per modificare le voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9a5e4-219">In questo esempio viene modificata la data di scadenza della voce di blocco specificata.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="9a5e4-220">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9a5e4-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-221">Usare PowerShell per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9a5e4-222">Per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9a5e4-223">In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="9a5e4-224">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9a5e4-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="9a5e4-225">Sintassi dell'URL per l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9a5e4-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="9a5e4-226">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="9a5e4-227">Le estensioni dei nomi di file non sono consentite(ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="9a5e4-228">Unicode non è supportato, ma Punycode lo è.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="9a5e4-229">I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="9a5e4-230">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="9a5e4-231">A sinistra del punto è presente almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="9a5e4-232">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="9a5e4-233">Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="9a5e4-234">I sottopercorso non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="9a5e4-235">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9a5e4-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="9a5e4-236">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="9a5e4-237">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="9a5e4-238">Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="9a5e4-239">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="9a5e4-240">Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="9a5e4-241">Tutti i percorsi secondari non sono implicati da un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="9a5e4-242">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9a5e4-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="9a5e4-243">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="9a5e4-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="9a5e4-244">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="9a5e4-245">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="9a5e4-246">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="9a5e4-247">Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9a5e4-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="9a5e4-248">Le voci URL contenenti protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="9a5e4-249">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="9a5e4-250">Le virgolette (' o ") sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="9a5e4-251">Se possibile, un URL deve includere tutti i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="9a5e4-252">Scenari di immissione url</span><span class="sxs-lookup"><span data-stu-id="9a5e4-252">URL entry scenarios</span></span>

<span data-ttu-id="9a5e4-253">Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9a5e4-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="9a5e4-254">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="9a5e4-254">Scenario: No wildcards</span></span>

<span data-ttu-id="9a5e4-255">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="9a5e4-256">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="9a5e4-257">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="9a5e4-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-258">abc-contoso.com</span></span>
  - <span data-ttu-id="9a5e4-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-259">contoso.com/a</span></span>
  - <span data-ttu-id="9a5e4-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="9a5e4-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9a5e4-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-263">www.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9a5e4-265">**Corrispondenza blocco**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-265">**Block match**:</span></span>

  - <span data-ttu-id="9a5e4-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-266">contoso.com</span></span>
  - <span data-ttu-id="9a5e4-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-267">contoso.com/a</span></span>
  - <span data-ttu-id="9a5e4-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="9a5e4-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9a5e4-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-271">www.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9a5e4-273">**Blocco non corrispondente**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="9a5e4-274">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="9a5e4-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="9a5e4-275">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="9a5e4-276">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9a5e4-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-277">www.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9a5e4-279">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9a5e4-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-280">123contoso.com</span></span>
  - <span data-ttu-id="9a5e4-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-281">contoso.com</span></span>
  - <span data-ttu-id="9a5e4-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="9a5e4-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9a5e4-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="9a5e4-284">Scenario: carattere jolly destro all'inizio del percorso</span><span class="sxs-lookup"><span data-stu-id="9a5e4-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="9a5e4-285">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="9a5e4-286">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9a5e4-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="9a5e4-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="9a5e4-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9a5e4-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9a5e4-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="9a5e4-290">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9a5e4-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-291">contoso.com</span></span>
  - <span data-ttu-id="9a5e4-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-292">contoso.com/a</span></span>
  - <span data-ttu-id="9a5e4-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-293">www.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="9a5e4-295">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="9a5e4-295">Scenario: Left tilde</span></span>

<span data-ttu-id="9a5e4-296">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="9a5e4-297">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9a5e4-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-298">contoso.com</span></span>
  - <span data-ttu-id="9a5e4-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-299">www.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9a5e4-301">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9a5e4-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-302">123contoso.com</span></span>
  - <span data-ttu-id="9a5e4-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9a5e4-303">contoso.com/abc</span></span>
  - <span data-ttu-id="9a5e4-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9a5e4-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="9a5e4-305">Scenario: suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="9a5e4-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="9a5e4-306">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="9a5e4-307">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9a5e4-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="9a5e4-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-309">contoso.com/a</span></span>
  - <span data-ttu-id="9a5e4-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9a5e4-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9a5e4-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9a5e4-311">contoso.com/ab</span></span>
  - <span data-ttu-id="9a5e4-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9a5e4-312">contoso.com/b</span></span>
  - <span data-ttu-id="9a5e4-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9a5e4-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9a5e4-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9a5e4-314">contoso.com/ba</span></span>

- <span data-ttu-id="9a5e4-315">**Allow not matched** e **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="9a5e4-316">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="9a5e4-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="9a5e4-317">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="9a5e4-318">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9a5e4-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9a5e4-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="9a5e4-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9a5e4-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9a5e4-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="9a5e4-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9a5e4-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9a5e4-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9a5e4-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="9a5e4-324">**Allow not matched** e **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9a5e4-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="9a5e4-325">Scenario: tilde sinistra e destra</span><span class="sxs-lookup"><span data-stu-id="9a5e4-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="9a5e4-326">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="9a5e4-327">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9a5e4-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-328">contoso.com</span></span>
  - <span data-ttu-id="9a5e4-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-329">contoso.com/a</span></span>
  - <span data-ttu-id="9a5e4-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-330">www.contoso.com</span></span>
  - <span data-ttu-id="9a5e4-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9a5e4-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="9a5e4-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9a5e4-333">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9a5e4-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-334">123contoso.com</span></span>
  - <span data-ttu-id="9a5e4-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="9a5e4-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="9a5e4-336">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="9a5e4-336">Scenario: IP address</span></span>

<span data-ttu-id="9a5e4-337">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="9a5e4-338">**Allow match** and **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9a5e4-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="9a5e4-339">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9a5e4-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="9a5e4-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9a5e4-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="9a5e4-342">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="9a5e4-342">IP address with right wildcard</span></span>

<span data-ttu-id="9a5e4-343">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="9a5e4-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="9a5e4-344">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9a5e4-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="9a5e4-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="9a5e4-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="9a5e4-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="9a5e4-347">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="9a5e4-347">Examples of invalid entries</span></span>

<span data-ttu-id="9a5e4-348">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-348">The following entries are invalid:</span></span>

- <span data-ttu-id="9a5e4-349">**Valori di dominio mancanti o non validi:**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="9a5e4-350">contoso</span><span class="sxs-lookup"><span data-stu-id="9a5e4-350">contoso</span></span>
  - <span data-ttu-id="9a5e4-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="9a5e4-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-352">\*.com</span></span>
  - <span data-ttu-id="9a5e4-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="9a5e4-353">\*.pdf</span></span>

- <span data-ttu-id="9a5e4-354">**Caratteri jolly per il testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="9a5e4-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-355">\*contoso.com</span></span>
  - <span data-ttu-id="9a5e4-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-356">contoso.com\*</span></span>
  - <span data-ttu-id="9a5e4-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9a5e4-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="9a5e4-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="9a5e4-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="9a5e4-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="9a5e4-361">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="9a5e4-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="9a5e4-362">contoso.com:443</span></span>
  - <span data-ttu-id="9a5e4-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="9a5e4-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="9a5e4-364">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="9a5e4-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-365">\*.\*</span></span>

- <span data-ttu-id="9a5e4-366">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="9a5e4-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="9a5e4-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-367">conto\*so.com</span></span>
  - <span data-ttu-id="9a5e4-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="9a5e4-368">conto~so.com</span></span>

- <span data-ttu-id="9a5e4-369">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="9a5e4-369">**Double wildcards**</span></span>

  - <span data-ttu-id="9a5e4-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="9a5e4-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="9a5e4-371">contoso.com/\*/\*</span></span>
