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
ms.openlocfilehash: 2f97308bfc3600e4e85f5ac92d951b12d9a50f24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928533"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-103">Gestire l'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f189c-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f189c-104">**Applies to**</span></span>
- [<span data-ttu-id="f189c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f189c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f189c-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="f189c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f189c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f189c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="f189c-108">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f189c-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="f189c-109">Non è possibile **configurare gli** elementi consentiti nell'elenco tenant consentiti/bloccati in questo momento.</span><span class="sxs-lookup"><span data-stu-id="f189c-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="f189c-110">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile che non si sia d'accordo con il verdetto del filtro EOP.</span><span class="sxs-lookup"><span data-stu-id="f189c-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f189c-111">Ad esempio, un buon messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non positivo potrebbe essere consentito (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="f189c-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f189c-112">L'elenco Tenant consentiti/bloccati nel Centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtro di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f189c-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f189c-113">L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento dei clic dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f189c-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f189c-114">È possibile specificare URL o file da bloccare sempre.</span><span class="sxs-lookup"><span data-stu-id="f189c-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="f189c-115">In questo articolo viene descritto come configurare le voci nell'elenco consenti/blocca tenant nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="f189c-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f189c-116">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f189c-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f189c-117">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f189c-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f189c-118">Per passare direttamente alla pagina **Elenco tenant consentiti/bloccati,** utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="f189c-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f189c-119">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="f189c-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="f189c-120">Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="f189c-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="f189c-121">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="f189c-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="f189c-122">I valori hash percettivi (pHash) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="f189c-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="f189c-123">I valori url disponibili sono descritti nella [sintassi dell'URL](#url-syntax-for-the-tenant-allowblock-list) per la sezione Elenco tenant consentiti/bloccati più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="f189c-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="f189c-124">L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="f189c-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="f189c-125">Il numero massimo di caratteri per ogni voce è:</span><span class="sxs-lookup"><span data-stu-id="f189c-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="f189c-126">Hash dei file = 64</span><span class="sxs-lookup"><span data-stu-id="f189c-126">File hashes = 64</span></span>
  - <span data-ttu-id="f189c-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="f189c-127">URL = 250</span></span>

- <span data-ttu-id="f189c-128">Una voce deve essere attiva entro 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="f189c-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="f189c-129">Per impostazione predefinita, le voci nell'elenco tenant consentiti/bloccati scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f189c-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f189c-130">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="f189c-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f189c-131">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f189c-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f189c-132">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f189c-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f189c-133">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="f189c-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f189c-134">Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="f189c-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f189c-135">Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f189c-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f189c-136">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="f189c-136">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="f189c-137">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f189c-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f189c-138">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f189c-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="f189c-139">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f189c-139">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-140">Utilizzare il Centro sicurezza & conformità per creare voci URL nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f189c-141">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="f189c-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="f189c-142">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f189c-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f189c-143">Nella pagina **Elenco tenant consentiti/bloccati** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Blocca**</span><span class="sxs-lookup"><span data-stu-id="f189c-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="f189c-144">Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f189c-145">**Aggiungi URL da bloccare:** immetti un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="f189c-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f189c-146">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f189c-147">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="f189c-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="f189c-148">oppure</span><span class="sxs-lookup"><span data-stu-id="f189c-148">or</span></span>

     - <span data-ttu-id="f189c-149">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="f189c-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="f189c-151">.</span><span class="sxs-lookup"><span data-stu-id="f189c-151">.</span></span>

   - <span data-ttu-id="f189c-152">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="f189c-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f189c-153">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f189c-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-154">Utilizzare il Centro sicurezza & conformità per creare voci di file nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f189c-155">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f189c-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f189c-156">Nella pagina **Elenco tenant consentiti/bloccati** selezionare **la scheda File** e quindi fare clic su **Blocca.**</span><span class="sxs-lookup"><span data-stu-id="f189c-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="f189c-157">Nel riquadro **a comparsa Aggiungi file da** bloccare, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f189c-158">**Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="f189c-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f189c-159">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f189c-160">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. </span><span class="sxs-lookup"><span data-stu-id="f189c-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f189c-161">oppure</span><span class="sxs-lookup"><span data-stu-id="f189c-161">or</span></span>

     - <span data-ttu-id="f189c-162">Spostare l'interruttore a destra per configurare le voci in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="f189c-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="f189c-164">.</span><span class="sxs-lookup"><span data-stu-id="f189c-164">.</span></span>

   - <span data-ttu-id="f189c-165">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="f189c-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f189c-166">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f189c-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-167">Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f189c-168">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f189c-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f189c-169">Selezionare la **scheda URL** o **La scheda** File.</span><span class="sxs-lookup"><span data-stu-id="f189c-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="f189c-170">Fare clic sulle intestazioni di colonna seguenti per eseguire l'ordinamento crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="f189c-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f189c-171">**Valore**: URL o hash del file.</span><span class="sxs-lookup"><span data-stu-id="f189c-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="f189c-172">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="f189c-172">**Last updated date**</span></span>
- <span data-ttu-id="f189c-173">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="f189c-173">**Expiration date**</span></span>
- <span data-ttu-id="f189c-174">**Nota**</span><span class="sxs-lookup"><span data-stu-id="f189c-174">**Note**</span></span>

<span data-ttu-id="f189c-175">Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="f189c-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f189c-176">Al termine, fare clic su Cancella **ricerca** ![ Cancella icona di ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ricerca.</span><span class="sxs-lookup"><span data-stu-id="f189c-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f189c-177">Fare clic **su Filtro.**</span><span class="sxs-lookup"><span data-stu-id="f189c-177">Click **Filter**.</span></span> <span data-ttu-id="f189c-178">Nel riquadro **a** comparsa Filtro visualizzato configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f189c-179">**Non scadere mai**: Selezionare Disattivato: ![ Attiva o ](../../media/scc-toggle-off.png) disattiva: ![ Attiva/Disattiva. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="f189c-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="f189c-180">**Last updated**: Selezionare una data di inizio (**From**), una data di fine (**To**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="f189c-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f189c-181">**Data di** scadenza: selezionare una data di inizio (**Da**), una data di fine (**A**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="f189c-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f189c-182">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="f189c-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f189c-183">Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="f189c-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-184">Utilizzare il Centro sicurezza & conformità per modificare le voci di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f189c-185">Non è possibile modificare l'URL o i valori di file bloccati esistenti all'interno di una voce.</span><span class="sxs-lookup"><span data-stu-id="f189c-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="f189c-186">Per modificare questi valori, è necessario eliminare e ricreare la voce.</span><span class="sxs-lookup"><span data-stu-id="f189c-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="f189c-187">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f189c-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f189c-188">Selezionare la **scheda URL** o **La scheda** File.</span><span class="sxs-lookup"><span data-stu-id="f189c-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f189c-189">Selezionare la voce di blocco che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="f189c-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f189c-190">Nel riquadro a comparsa visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f189c-191">**Non scadere mai:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f189c-192">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per la voce. </span><span class="sxs-lookup"><span data-stu-id="f189c-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="f189c-193">oppure</span><span class="sxs-lookup"><span data-stu-id="f189c-193">or</span></span>

     - <span data-ttu-id="f189c-194">Spostare l'interruttore a destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="f189c-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="f189c-196">.</span><span class="sxs-lookup"><span data-stu-id="f189c-196">.</span></span>

   - <span data-ttu-id="f189c-197">**Nota facoltativa:** immettere un testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="f189c-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f189c-198">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f189c-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-199">Utilizzare il Centro sicurezza & conformità per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f189c-200">Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.</span><span class="sxs-lookup"><span data-stu-id="f189c-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f189c-201">Selezionare la **scheda URL** o **La scheda** File.</span><span class="sxs-lookup"><span data-stu-id="f189c-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f189c-202">Selezionare la voce di blocco che si desidera rimuovere e quindi fare clic su **Elimina** ![ Icona ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Elimina.</span><span class="sxs-lookup"><span data-stu-id="f189c-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f189c-203">Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="f189c-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-204">Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per configurare l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-205">Usare PowerShell per aggiungere voci di blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f189c-206">Per aggiungere voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f189c-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f189c-207">In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini(ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f189c-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f189c-208">Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f189c-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="f189c-209">In questo esempio viene aggiunta una voce del file di blocco per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="f189c-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="f189c-210">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f189c-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-211">Utilizzare PowerShell per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f189c-212">Per visualizzare le voci nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f189c-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f189c-213">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="f189c-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="f189c-214">In questo esempio vengono restituite le informazioni per il valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="f189c-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="f189c-215">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f189c-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-216">Utilizzare PowerShell per modificare le voci di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f189c-217">Non è possibile modificare l'URL o i valori di file esistenti all'interno di una voce di blocco.</span><span class="sxs-lookup"><span data-stu-id="f189c-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="f189c-218">Per modificare questi valori, è necessario eliminare e ricreare la voce.</span><span class="sxs-lookup"><span data-stu-id="f189c-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="f189c-219">Per modificare le voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f189c-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f189c-220">In questo esempio viene modificata la data di scadenza della voce di blocco specificata.</span><span class="sxs-lookup"><span data-stu-id="f189c-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f189c-221">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f189c-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-222">Usare PowerShell per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f189c-223">Per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f189c-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f189c-224">In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/bloccati.</span><span class="sxs-lookup"><span data-stu-id="f189c-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f189c-225">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f189c-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f189c-226">Sintassi dell'URL per l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="f189c-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f189c-227">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="f189c-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f189c-228">Le estensioni dei nomi di file non sono consentite(ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="f189c-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f189c-229">Unicode non è supportato, ma Punycode lo è.</span><span class="sxs-lookup"><span data-stu-id="f189c-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f189c-230">I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="f189c-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="f189c-231">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="f189c-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="f189c-232">A sinistra del punto è presente almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="f189c-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f189c-233">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="f189c-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f189c-234">Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.</span><span class="sxs-lookup"><span data-stu-id="f189c-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f189c-235">I sottopercorso non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="f189c-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="f189c-236">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f189c-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f189c-237">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f189c-238">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="f189c-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f189c-239">Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.</span><span class="sxs-lookup"><span data-stu-id="f189c-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f189c-240">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="f189c-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f189c-241">Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.</span><span class="sxs-lookup"><span data-stu-id="f189c-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f189c-242">Tutti i percorsi secondari non sono implicati da un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="f189c-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f189c-243">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f189c-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f189c-244">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="f189c-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f189c-245">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="f189c-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f189c-246">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="f189c-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f189c-247">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="f189c-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f189c-248">Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f189c-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f189c-249">Le voci URL contenenti protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.</span><span class="sxs-lookup"><span data-stu-id="f189c-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f189c-250">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="f189c-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f189c-251">Le virgolette (' o ") sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="f189c-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f189c-252">Se possibile, un URL deve includere tutti i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="f189c-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f189c-253">Scenari di immissione url</span><span class="sxs-lookup"><span data-stu-id="f189c-253">URL entry scenarios</span></span>

<span data-ttu-id="f189c-254">Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f189c-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f189c-255">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="f189c-255">Scenario: No wildcards</span></span>

<span data-ttu-id="f189c-256">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f189c-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f189c-257">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f189c-258">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="f189c-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="f189c-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-259">abc-contoso.com</span></span>
  - <span data-ttu-id="f189c-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f189c-260">contoso.com/a</span></span>
  - <span data-ttu-id="f189c-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="f189c-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="f189c-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f189c-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-264">www.contoso.com</span></span>
  - <span data-ttu-id="f189c-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f189c-266">**Corrispondenza blocco**:</span><span class="sxs-lookup"><span data-stu-id="f189c-266">**Block match**:</span></span>

  - <span data-ttu-id="f189c-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-267">contoso.com</span></span>
  - <span data-ttu-id="f189c-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f189c-268">contoso.com/a</span></span>
  - <span data-ttu-id="f189c-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="f189c-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="f189c-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f189c-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-272">www.contoso.com</span></span>
  - <span data-ttu-id="f189c-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f189c-274">**Blocco non corrispondente**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f189c-275">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="f189c-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f189c-276">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f189c-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f189c-277">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f189c-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f189c-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-278">www.contoso.com</span></span>
  - <span data-ttu-id="f189c-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f189c-280">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f189c-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f189c-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-281">123contoso.com</span></span>
  - <span data-ttu-id="f189c-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-282">contoso.com</span></span>
  - <span data-ttu-id="f189c-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="f189c-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f189c-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f189c-285">Scenario: carattere jolly destro all'inizio del percorso</span><span class="sxs-lookup"><span data-stu-id="f189c-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f189c-286">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f189c-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f189c-287">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f189c-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f189c-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f189c-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="f189c-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f189c-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f189c-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="f189c-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f189c-291">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f189c-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f189c-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-292">contoso.com</span></span>
  - <span data-ttu-id="f189c-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f189c-293">contoso.com/a</span></span>
  - <span data-ttu-id="f189c-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-294">www.contoso.com</span></span>
  - <span data-ttu-id="f189c-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="f189c-296">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="f189c-296">Scenario: Left tilde</span></span>

<span data-ttu-id="f189c-297">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f189c-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f189c-298">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f189c-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f189c-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-299">contoso.com</span></span>
  - <span data-ttu-id="f189c-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-300">www.contoso.com</span></span>
  - <span data-ttu-id="f189c-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f189c-302">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f189c-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f189c-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-303">123contoso.com</span></span>
  - <span data-ttu-id="f189c-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f189c-304">contoso.com/abc</span></span>
  - <span data-ttu-id="f189c-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f189c-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f189c-306">Scenario: suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="f189c-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f189c-307">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f189c-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f189c-308">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f189c-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f189c-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f189c-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f189c-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f189c-310">contoso.com/a</span></span>
  - <span data-ttu-id="f189c-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f189c-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f189c-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f189c-312">contoso.com/ab</span></span>
  - <span data-ttu-id="f189c-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f189c-313">contoso.com/b</span></span>
  - <span data-ttu-id="f189c-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f189c-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f189c-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f189c-315">contoso.com/ba</span></span>

- <span data-ttu-id="f189c-316">**Allow not matched** e **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f189c-317">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="f189c-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f189c-318">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f189c-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f189c-319">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f189c-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f189c-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f189c-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f189c-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f189c-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f189c-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f189c-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="f189c-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f189c-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f189c-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f189c-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f189c-325">**Allow not matched** e **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f189c-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f189c-326">Scenario: tilde sinistra e destra</span><span class="sxs-lookup"><span data-stu-id="f189c-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f189c-327">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f189c-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f189c-328">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f189c-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f189c-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-329">contoso.com</span></span>
  - <span data-ttu-id="f189c-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f189c-330">contoso.com/a</span></span>
  - <span data-ttu-id="f189c-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-331">www.contoso.com</span></span>
  - <span data-ttu-id="f189c-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f189c-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="f189c-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f189c-334">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f189c-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f189c-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-335">123contoso.com</span></span>
  - <span data-ttu-id="f189c-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f189c-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f189c-337">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="f189c-337">Scenario: IP address</span></span>

<span data-ttu-id="f189c-338">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f189c-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f189c-339">**Allow match** and **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f189c-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f189c-340">**Allow not matched** e **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="f189c-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f189c-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f189c-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="f189c-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f189c-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f189c-343">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="f189c-343">IP address with right wildcard</span></span>

<span data-ttu-id="f189c-344">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f189c-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f189c-345">**Consenti corrispondenza** e **Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="f189c-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f189c-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f189c-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="f189c-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f189c-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f189c-348">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="f189c-348">Examples of invalid entries</span></span>

<span data-ttu-id="f189c-349">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="f189c-349">The following entries are invalid:</span></span>

- <span data-ttu-id="f189c-350">**Valori di dominio mancanti o non validi:**</span><span class="sxs-lookup"><span data-stu-id="f189c-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f189c-351">contoso</span><span class="sxs-lookup"><span data-stu-id="f189c-351">contoso</span></span>
  - <span data-ttu-id="f189c-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="f189c-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="f189c-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="f189c-353">\*.com</span></span>
  - <span data-ttu-id="f189c-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="f189c-354">\*.pdf</span></span>

- <span data-ttu-id="f189c-355">**Caratteri jolly per il testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="f189c-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f189c-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f189c-356">\*contoso.com</span></span>
  - <span data-ttu-id="f189c-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f189c-357">contoso.com\*</span></span>
  - <span data-ttu-id="f189c-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f189c-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="f189c-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f189c-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="f189c-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f189c-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="f189c-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f189c-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="f189c-362">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="f189c-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f189c-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f189c-363">contoso.com:443</span></span>
  - <span data-ttu-id="f189c-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f189c-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="f189c-365">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="f189c-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f189c-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f189c-366">\*.\*</span></span>

- <span data-ttu-id="f189c-367">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="f189c-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f189c-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f189c-368">conto\*so.com</span></span>
  - <span data-ttu-id="f189c-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="f189c-369">conto~so.com</span></span>

- <span data-ttu-id="f189c-370">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="f189c-370">**Double wildcards**</span></span>

  - <span data-ttu-id="f189c-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f189c-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f189c-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f189c-372">contoso.com/\*/\*</span></span>