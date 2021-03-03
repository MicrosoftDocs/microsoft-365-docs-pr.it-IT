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
description: Gli amministratori possono imparare a configurare gli elementi consentiti e bloccati nell'elenco tenant consentiti/bloccati nel portale di sicurezza.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 960fbf26b610485fb46c935b04aedcc593b85752
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407251"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-103">Gestire l'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0cbbb-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-104">**Applies to**</span></span>
- [<span data-ttu-id="0cbbb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0cbbb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0cbbb-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="0cbbb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0cbbb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cbbb-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="0cbbb-108">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="0cbbb-109">Non è possibile configurare **gli** elementi consentiti nell'elenco tenant consentiti/bloccati in questo momento.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="0cbbb-110">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto filtro EOP.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="0cbbb-111">Ad esempio, un messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non erto potrebbe essere consentito (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="0cbbb-112">L'elenco tenant consentiti/bloccati nel Centro sicurezza & conformità consente di ignorare manualmente i verdetti del filtro di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="0cbbb-113">L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento in cui l'utente fa clic.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="0cbbb-114">È possibile specificare URL o file da bloccare sempre.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="0cbbb-115">In questo articolo viene descritto come configurare le voci nell'elenco Tenant consentiti/bloccati nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni Di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0cbbb-116">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="0cbbb-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0cbbb-117">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0cbbb-118">Per passare direttamente alla pagina **Elenco tenant consentiti/bloccati,** utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="0cbbb-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="0cbbb-119">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="0cbbb-120">Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="0cbbb-121">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="0cbbb-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="0cbbb-122">I valori hash percettivi (pHash) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="0cbbb-123">I valori url disponibili sono descritti nella sintassi dell'URL per la sezione Tenant [Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="0cbbb-124">L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="0cbbb-125">Una voce deve essere attiva entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="0cbbb-126">Per impostazione predefinita, le voci nell'elenco tenant consentite/bloccate scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="0cbbb-127">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="0cbbb-128">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0cbbb-129">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0cbbb-130">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in **Exchange Online:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-130">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0cbbb-131">Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli Gestione organizzazione o **Amministratore** sicurezza. </span><span class="sxs-lookup"><span data-stu-id="0cbbb-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0cbbb-132">Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati,  è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza. </span><span class="sxs-lookup"><span data-stu-id="0cbbb-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0cbbb-133">Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-133">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="0cbbb-134">**Note**:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-134">**Notes**:</span></span>

  - <span data-ttu-id="0cbbb-135">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="0cbbb-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0cbbb-136">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="0cbbb-137">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-138">Usare il Centro sicurezza & conformità per creare voci URL nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0cbbb-139">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione Tenant [Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="0cbbb-140">Nel Centro sicurezza e & conformità passare **a** Elenchi di \>  \> **blocco/consentiti** tenant dei criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0cbbb-141">Nella pagina **Elenco indirizzi consentiti/blocca tenant** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Blocca**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="0cbbb-142">Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0cbbb-143">**Aggiungere URL da bloccare:** immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0cbbb-144">**Nessuna scadenza:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0cbbb-145">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. </span><span class="sxs-lookup"><span data-stu-id="0cbbb-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0cbbb-146">oppure</span><span class="sxs-lookup"><span data-stu-id="0cbbb-146">or</span></span>

     - <span data-ttu-id="0cbbb-147">Spostare l'interruttore a destra per configurare le voci in modo che non scadono mai:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="0cbbb-149">.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-149">.</span></span>

   - <span data-ttu-id="0cbbb-150">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0cbbb-151">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-152">Usare il Centro sicurezza & conformità per creare voci di file nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0cbbb-153">Nel Centro sicurezza e & conformità passare **a** Elenchi di \>  \> **blocco/consentiti** tenant dei criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0cbbb-154">Nella pagina **Elenco tenant consentiti/blocca** selezionare la **scheda File** e quindi fare clic su **Blocca.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="0cbbb-155">Nel riquadro **a comparsa Aggiungi file da** bloccare, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0cbbb-156">**Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0cbbb-157">**Nessuna scadenza:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0cbbb-158">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. </span><span class="sxs-lookup"><span data-stu-id="0cbbb-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0cbbb-159">oppure</span><span class="sxs-lookup"><span data-stu-id="0cbbb-159">or</span></span>

     - <span data-ttu-id="0cbbb-160">Spostare l'interruttore a destra per configurare le voci in modo che non scadono mai:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="0cbbb-162">.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-162">.</span></span>

   - <span data-ttu-id="0cbbb-163">**Nota facoltativa:** immettere un testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0cbbb-164">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-165">Usare il Centro sicurezza & conformità per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0cbbb-166">Nel Centro sicurezza e & conformità passare **a** Elenchi di \>  \> **blocco/consentiti** tenant dei criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0cbbb-167">Selezionare la **scheda URL** o **File.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="0cbbb-168">Fare clic sulle intestazioni di colonna seguenti per eseguire l'ordinamento crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="0cbbb-169">**Valore**: l'URL o l'hash del file.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="0cbbb-170">**Data ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-170">**Last updated date**</span></span>
- <span data-ttu-id="0cbbb-171">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-171">**Expiration date**</span></span>
- <span data-ttu-id="0cbbb-172">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-172">**Note**</span></span>

<span data-ttu-id="0cbbb-173">Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="0cbbb-174">Al termine, fare clic su Cancella **l'icona** ![ Cancella ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ricerca.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="0cbbb-175">Fare **clic su Filtro.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-175">Click **Filter**.</span></span> <span data-ttu-id="0cbbb-176">Nel riquadro **a** comparsa Filtro visualizzato configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="0cbbb-177">**Non scadere**: seleziona Disattivato: ![ Attiva o ](../../media/scc-toggle-off.png) disattiva: ![ Attiva/Disattiva. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="0cbbb-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="0cbbb-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="0cbbb-179">**Data di** scadenza: selezionare una data di inizio (**Da**), una data di fine (**A**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="0cbbb-180">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="0cbbb-181">Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-182">Utilizzare il Centro sicurezza & conformità per modificare le voci di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0cbbb-183">Non è possibile modificare l'URL o i valori di file bloccati esistenti all'interno di una voce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="0cbbb-184">Per modificare questi valori, è necessario eliminare e ricreare la voce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="0cbbb-185">Nel Centro sicurezza e & conformità passare **a** Elenchi di \>  \> **blocco/consentiti** tenant dei criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0cbbb-186">Selezionare la **scheda URL** o **File.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="0cbbb-187">Selezionare la voce di blocco che si desidera modificare e quindi fare clic **sull'icona** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Modifica.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="0cbbb-188">Nel riquadro a comparsa visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0cbbb-189">**Nessuna scadenza:** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0cbbb-190">Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la ![ data di scadenza per la ](../../media/scc-toggle-off.png) voce. </span><span class="sxs-lookup"><span data-stu-id="0cbbb-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="0cbbb-191">oppure</span><span class="sxs-lookup"><span data-stu-id="0cbbb-191">or</span></span>

     - <span data-ttu-id="0cbbb-192">Spostare l'interruttore a destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="0cbbb-194">.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-194">.</span></span>

   - <span data-ttu-id="0cbbb-195">**Nota facoltativa:** immettere un testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="0cbbb-196">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-197">Usare il Centro sicurezza & conformità per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0cbbb-198">Nel Centro sicurezza e & conformità passare **a** Elenchi di \>  \> **blocco/consentiti** tenant dei criteri di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0cbbb-199">Selezionare la **scheda URL** o **File.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="0cbbb-200">Selezionare la voce di blocco che si desidera rimuovere e quindi fare clic **sull'icona** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Elimina.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="0cbbb-201">Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-202">Utilizzare PowerShell di Exchange Online o PowerShell di EOP autonomo per configurare l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-203">Utilizzare PowerShell per aggiungere voci di blocco all'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="0cbbb-204">Per aggiungere voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0cbbb-205">In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini ,ad esempio contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="0cbbb-206">Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="0cbbb-207">In questo esempio viene aggiunta una voce di blocco per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="0cbbb-208">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0cbbb-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-209">Utilizzare PowerShell per visualizzare le voci nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0cbbb-210">Per visualizzare le voci nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="0cbbb-211">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="0cbbb-212">In questo esempio vengono restituite informazioni sul valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="0cbbb-213">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0cbbb-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-214">Utilizzare PowerShell per modificare le voci di blocco nell'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0cbbb-215">Non è possibile modificare l'URL o i valori di file esistenti all'interno di una voce di blocco.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="0cbbb-216">Per modificare questi valori, è necessario eliminare e ricreare la voce.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="0cbbb-217">Per modificare le voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0cbbb-218">In questo esempio viene modificata la data di scadenza della voce di blocco specificata.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="0cbbb-219">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0cbbb-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-220">Utilizzare PowerShell per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="0cbbb-221">Per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="0cbbb-222">In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/non consentiti.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="0cbbb-223">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0cbbb-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="0cbbb-224">Sintassi dell'URL per l'elenco tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="0cbbb-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="0cbbb-225">Gli indirizzi IP4v e IPv6 sono consentiti, ma non le porte TCP/UDP.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="0cbbb-226">Le estensioni dei nomi di file non sono consentite (ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="0cbbb-227">Unicode non è supportato, ma Punycode lo è.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="0cbbb-228">I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="0cbbb-229">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="0cbbb-230">A sinistra del punto è presente almeno un carattere.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="0cbbb-231">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="0cbbb-232">Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="0cbbb-233">I sottopercorso non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="0cbbb-234">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="0cbbb-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="0cbbb-235">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="0cbbb-236">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="0cbbb-237">Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="0cbbb-238">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="0cbbb-239">Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="0cbbb-240">Tutti i sottopercorso non sono implicati da un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="0cbbb-241">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="0cbbb-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="0cbbb-242">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="0cbbb-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="0cbbb-243">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="0cbbb-244">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="0cbbb-245">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="0cbbb-246">Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="0cbbb-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="0cbbb-247">Le voci URL che contengono protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="0cbbb-248">Un nome utente o una password non sono supportati o necessari.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="0cbbb-249">Le virgolette (' o ") sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="0cbbb-250">Se possibile, un URL deve includere tutti i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="0cbbb-251">Scenari di immissione url</span><span class="sxs-lookup"><span data-stu-id="0cbbb-251">URL entry scenarios</span></span>

<span data-ttu-id="0cbbb-252">Le voci url valide e i relativi risultati sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0cbbb-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="0cbbb-253">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="0cbbb-253">Scenario: No wildcards</span></span>

<span data-ttu-id="0cbbb-254">**Voce:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="0cbbb-255">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="0cbbb-256">**Consenti senza corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="0cbbb-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-257">abc-contoso.com</span></span>
  - <span data-ttu-id="0cbbb-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-258">contoso.com/a</span></span>
  - <span data-ttu-id="0cbbb-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="0cbbb-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0cbbb-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-262">www.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0cbbb-264">**Corrispondenza di blocco:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-264">**Block match**:</span></span>

  - <span data-ttu-id="0cbbb-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-265">contoso.com</span></span>
  - <span data-ttu-id="0cbbb-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-266">contoso.com/a</span></span>
  - <span data-ttu-id="0cbbb-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="0cbbb-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0cbbb-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-270">www.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0cbbb-272">**Blocco non corrispondente:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="0cbbb-273">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="0cbbb-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="0cbbb-274">**Voce:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="0cbbb-275">**Consenti corrispondenza e** **Blocca corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0cbbb-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-276">www.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0cbbb-278">**Allow not matched** and **Block not matched:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0cbbb-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-279">123contoso.com</span></span>
  - <span data-ttu-id="0cbbb-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-280">contoso.com</span></span>
  - <span data-ttu-id="0cbbb-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="0cbbb-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0cbbb-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="0cbbb-283">Scenario: carattere jolly destro all'inizio del percorso</span><span class="sxs-lookup"><span data-stu-id="0cbbb-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="0cbbb-284">**Voce:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="0cbbb-285">**Consenti corrispondenza e** **Blocca corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0cbbb-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="0cbbb-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="0cbbb-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0cbbb-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0cbbb-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="0cbbb-289">**Allow not matched** and **Block not matched:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0cbbb-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-290">contoso.com</span></span>
  - <span data-ttu-id="0cbbb-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-291">contoso.com/a</span></span>
  - <span data-ttu-id="0cbbb-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-292">www.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="0cbbb-294">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="0cbbb-294">Scenario: Left tilde</span></span>

<span data-ttu-id="0cbbb-295">**Voce:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="0cbbb-296">**Consenti corrispondenza e** **Blocca corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0cbbb-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-297">contoso.com</span></span>
  - <span data-ttu-id="0cbbb-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-298">www.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0cbbb-300">**Allow not matched** and **Block not matched:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0cbbb-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-301">123contoso.com</span></span>
  - <span data-ttu-id="0cbbb-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0cbbb-302">contoso.com/abc</span></span>
  - <span data-ttu-id="0cbbb-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0cbbb-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="0cbbb-304">Scenario: suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="0cbbb-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="0cbbb-305">**Voce:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="0cbbb-306">**Consenti corrispondenza e** **Blocca corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0cbbb-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="0cbbb-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-308">contoso.com/a</span></span>
  - <span data-ttu-id="0cbbb-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0cbbb-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0cbbb-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0cbbb-310">contoso.com/ab</span></span>
  - <span data-ttu-id="0cbbb-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0cbbb-311">contoso.com/b</span></span>
  - <span data-ttu-id="0cbbb-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0cbbb-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0cbbb-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0cbbb-313">contoso.com/ba</span></span>

- <span data-ttu-id="0cbbb-314">**Allow not matched** and **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="0cbbb-315">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="0cbbb-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="0cbbb-316">**Voce:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="0cbbb-317">**Consenti corrispondenza e** **Blocca corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0cbbb-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0cbbb-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="0cbbb-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0cbbb-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0cbbb-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="0cbbb-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0cbbb-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0cbbb-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0cbbb-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="0cbbb-323">**Allow not matched** and **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0cbbb-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="0cbbb-324">Scenario: tilde sinistra e destra</span><span class="sxs-lookup"><span data-stu-id="0cbbb-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="0cbbb-325">**Voce:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="0cbbb-326">**Consenti corrispondenza e** **Blocca corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0cbbb-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-327">contoso.com</span></span>
  - <span data-ttu-id="0cbbb-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-328">contoso.com/a</span></span>
  - <span data-ttu-id="0cbbb-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-329">www.contoso.com</span></span>
  - <span data-ttu-id="0cbbb-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0cbbb-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="0cbbb-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0cbbb-332">**Allow not matched** and **Block not matched:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0cbbb-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-333">123contoso.com</span></span>
  - <span data-ttu-id="0cbbb-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="0cbbb-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="0cbbb-335">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="0cbbb-335">Scenario: IP address</span></span>

<span data-ttu-id="0cbbb-336">**Voce:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="0cbbb-337">**Allow match** and **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0cbbb-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="0cbbb-338">**Allow not matched** and **Block not matched:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0cbbb-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="0cbbb-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0cbbb-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="0cbbb-341">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="0cbbb-341">IP address with right wildcard</span></span>

<span data-ttu-id="0cbbb-342">**Voce:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="0cbbb-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="0cbbb-343">**Consenti corrispondenza e** **Blocca corrispondenza:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0cbbb-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="0cbbb-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="0cbbb-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="0cbbb-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="0cbbb-346">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="0cbbb-346">Examples of invalid entries</span></span>

<span data-ttu-id="0cbbb-347">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="0cbbb-347">The following entries are invalid:</span></span>

- <span data-ttu-id="0cbbb-348">**Valori di dominio mancanti o non validi:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="0cbbb-349">contoso</span><span class="sxs-lookup"><span data-stu-id="0cbbb-349">contoso</span></span>
  - <span data-ttu-id="0cbbb-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="0cbbb-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-351">\*.com</span></span>
  - <span data-ttu-id="0cbbb-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="0cbbb-352">\*.pdf</span></span>

- <span data-ttu-id="0cbbb-353">**Carattere jolly per il testo o senza caratteri di spaziatura:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="0cbbb-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-354">\*contoso.com</span></span>
  - <span data-ttu-id="0cbbb-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-355">contoso.com\*</span></span>
  - <span data-ttu-id="0cbbb-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0cbbb-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="0cbbb-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="0cbbb-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="0cbbb-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="0cbbb-360">**Indirizzi IP con porte:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="0cbbb-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="0cbbb-361">contoso.com:443</span></span>
  - <span data-ttu-id="0cbbb-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="0cbbb-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="0cbbb-363">**Caratteri jolly non descrittivi:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="0cbbb-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-364">\*.\*</span></span>

- <span data-ttu-id="0cbbb-365">**Caratteri jolly intermedi:**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="0cbbb-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-366">conto\*so.com</span></span>
  - <span data-ttu-id="0cbbb-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="0cbbb-367">conto~so.com</span></span>

- <span data-ttu-id="0cbbb-368">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="0cbbb-368">**Double wildcards**</span></span>

  - <span data-ttu-id="0cbbb-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="0cbbb-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="0cbbb-370">contoso.com/\*/\*</span></span>
