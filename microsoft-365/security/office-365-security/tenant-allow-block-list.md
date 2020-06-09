---
title: Gestire gli URL e i file bloccati e consentiti nell'elenco Consenti/blocca tenant
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono ottenere informazioni su come configurare le voci di URL e file nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance.
ms.openlocfilehash: 0143ee2601a4cb9593c79f8c6c62d1f06914088f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613421"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-103">Gestire gli URL e i file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="d4ae4-104">Le funzionalità descritte in questo argomento sono in anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="d4ae4-105">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto di filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="d4ae4-106">Ad esempio, un buon messaggio potrebbe essere contrassegnato come negativo (falso positivo) oppure potrebbe essere consentito un messaggio non valido tramite (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="d4ae4-107">L'elenco Consenti/blocca tenant nel centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtraggio di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="d4ae4-108">L'elenco Consenti/blocca tenant viene utilizzato durante il flusso di posta e al momento dell'utente fa clic su.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="d4ae4-109">È possibile specificare gli URL e i file da consentire o bloccare nell'elenco tenant Allow/Block.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="d4ae4-110">In questo argomento viene descritto come configurare le voci nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con le cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d4ae4-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d4ae4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d4ae4-112">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d4ae4-113">Per accedere direttamente alla pagina dell' **elenco Consenti/blocca tenant** , utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="d4ae4-114">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="d4ae4-115">Per trovare il valore hash di SHA256 di un file in Windows, al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="d4ae4-116">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="d4ae4-117">I valori dell'hash percettivo (pHash) non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="d4ae4-118">I valori degli URL disponibili sono descritti nella [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="d4ae4-119">L'elenco Consenti/blocca tenant consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="d4ae4-120">Una voce dovrebbe essere attiva entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="d4ae4-121">Le voci di blocco hanno la precedenza su Consenti voci.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="d4ae4-122">Per impostazione predefinita, le voci nell'elenco Consenti/blocca tenant scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="d4ae4-123">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="d4ae4-124">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d4ae4-125">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d4ae4-126">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d4ae4-127">Per aggiungere e rimuovere valori dall'elenco Consenti/blocca tenant, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d4ae4-128">Per l'accesso in sola lettura all'elenco Consenti/blocca tenant, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="d4ae4-129">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-130">Utilizzare il Centro sicurezza & conformità per creare le voci URL nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d4ae4-131">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="d4ae4-132">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d4ae4-133">Nella pagina **elenco Consenti/blocca tenant** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Aggiungi**</span><span class="sxs-lookup"><span data-stu-id="d4ae4-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="d4ae4-134">Nel riquadro a comparsa **Aggiungi nuovo URL** visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d4ae4-135">**Aggiungere URL con caratteri jolly**: immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="d4ae4-136">**Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** gli URL specificati.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="d4ae4-137">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="d4ae4-138">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="d4ae4-139">oppure</span><span class="sxs-lookup"><span data-stu-id="d4ae4-139">or</span></span>

     - <span data-ttu-id="d4ae4-140">Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="d4ae4-142">.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-142">.</span></span>

   - <span data-ttu-id="d4ae4-143">**Nota facoltativa**: immettere il testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="d4ae4-144">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-145">Utilizzare il Centro sicurezza & conformità per creare voci di file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d4ae4-146">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d4ae4-147">Nella pagina **elenco Consenti/blocca tenant** selezionare scheda **file** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="d4ae4-148">Nel riquadro a comparsa dei **nuovi file** che viene visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d4ae4-149">**Aggiungere gli hash dei file**: immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="d4ae4-150">**Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** i file specificati.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="d4ae4-151">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="d4ae4-152">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="d4ae4-153">oppure</span><span class="sxs-lookup"><span data-stu-id="d4ae4-153">or</span></span>

     - <span data-ttu-id="d4ae4-154">Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="d4ae4-156">.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-156">.</span></span>

   - <span data-ttu-id="d4ae4-157">**Nota facoltativa**: immettere il testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="d4ae4-158">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-159">Utilizzare il Centro sicurezza & conformità per visualizzare le voci di URL e file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d4ae4-160">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d4ae4-161">Selezionare la scheda **URL** o la scheda **file** .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="d4ae4-162">Fare clic sulle intestazioni di colonna seguenti per ordinare in ordine crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="d4ae4-163">**Valore**: l'URL o il file hash.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="d4ae4-164">**Azione**: **blocca** o **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="d4ae4-165">**Data dell'ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="d4ae4-165">**Last updated date**</span></span>
- <span data-ttu-id="d4ae4-166">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="d4ae4-166">**Expiration date**</span></span>
- <span data-ttu-id="d4ae4-167">**Nota**</span><span class="sxs-lookup"><span data-stu-id="d4ae4-167">**Note**</span></span>

<span data-ttu-id="d4ae4-168">Fare clic su **gruppo** per raggruppare le voci in base all' **azione** (**blocca** o **Consenti**) o **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="d4ae4-169">Fare clic su **ricerca**, immettere tutto o parte di un valore URL o file e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="d4ae4-170">Al termine, fare clic su **Pulisci** ![ icona ricerca in ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) chiaro.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="d4ae4-171">Fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-171">Click **Filter**.</span></span> <span data-ttu-id="d4ae4-172">Nel riquadro a comparsa del **filtro** visualizzato, configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="d4ae4-173">**Azione**: selezionare **Consenti**, **blocca** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="d4ae4-174">**Non scade mai**: selezionare disattivata (disattivazione ![ ](../../media/scc-toggle-off.png) ) o attivata ( ![ attiva o disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="d4ae4-175">**Ultimo aggiornamento**: selezionare una data di inizio (**da**), una data di fine (**a**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="d4ae4-176">**Data di scadenza**: selezionare una data di inizio (**da**), una data**di**fine (a) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="d4ae4-177">Al termine, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="d4ae4-178">Per cancellare i filtri esistenti, fare clic su **filtro**e, nel riquadro a comparsa **filtro** visualizzato, fare clic su **Pulisci filtri**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-179">Utilizzare il Centro sicurezza & conformità per modificare le voci di URL e file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d4ae4-180">Non è possibile modificare l'URL o il valore del file stesso.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="d4ae4-181">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="d4ae4-182">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d4ae4-183">Selezionare la scheda **URL** o la scheda **file** .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="d4ae4-184">Selezionare la voce che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="d4ae4-185">Nel riquadro a comparsa visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d4ae4-186">**Blocca/Consenti**: selezionare **Consenti** o **blocca**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="d4ae4-187">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="d4ae4-188">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per la voce.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="d4ae4-189">oppure</span><span class="sxs-lookup"><span data-stu-id="d4ae4-189">or</span></span>

     - <span data-ttu-id="d4ae4-190">Spostare l'interruttore verso destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="d4ae4-192">.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-192">.</span></span>

   - <span data-ttu-id="d4ae4-193">**Nota facoltativa**: immettere il testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="d4ae4-194">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-195">Utilizzare il Centro sicurezza & conformità per rimuovere URL e voci di file dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d4ae4-196">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d4ae4-197">Selezionare la scheda **URL** o la scheda **file** .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="d4ae4-198">Selezionare la voce che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="d4ae4-199">Nella finestra di dialogo di avviso visualizzata, fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-200">Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-201">Utilizzo di PowerShell per aggiungere URL e voci di file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d4ae4-202">Per aggiungere voci di URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="d4ae4-203">In questo esempio viene aggiunta una voce di blocco URL per contoso.com e tutti i sottodomini (ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="d4ae4-204">Poiché non sono stati utilizzati i parametri ExpirationDate o NOEXPIRE, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="d4ae4-205">In questo esempio viene aggiunta una voce Consenti file per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="d4ae4-206">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-207">Utilizzo di PowerShell per visualizzare le voci degli URL e dei file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d4ae4-208">Per visualizzare le voci relative a URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="d4ae4-209">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="d4ae4-210">In questo esempio vengono restituite le informazioni relative al valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="d4ae4-211">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-212">Utilizzo di PowerShell per modificare le voci di URL e file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d4ae4-213">Non è possibile modificare l'URL o il valore del file stesso.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="d4ae4-214">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="d4ae4-215">Per modificare le voci di URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="d4ae4-216">In questo esempio viene modificata la data di scadenza della voce specificata.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="d4ae4-217">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-218">Utilizzo di PowerShell per rimuovere URL e voci di file dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="d4ae4-219">Per rimuovere l'URL e le voci di file dall'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="d4ae4-220">In questo esempio viene rimossa la voce URL specificata dall'elenco Consenti/blocca tenant.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="d4ae4-221">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="d4ae4-222">Sintassi URL per l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="d4ae4-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="d4ae4-223">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="d4ae4-224">Le estensioni dei nomi di file non sono consentite (ad esempio, test. pdf).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="d4ae4-225">Unicode non è supportato, ma Punycode è.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="d4ae4-226">I nomi host sono consentiti se sono soddisfatte tutte le seguenti affermazioni:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="d4ae4-227">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="d4ae4-228">Vi è almeno un carattere a sinistra del punto.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="d4ae4-229">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="d4ae4-230">Ad esempio, `t.co` è consentito, `.com` oppure `contoso.` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="d4ae4-231">I sottopercorsi non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="d4ae4-232">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="d4ae4-233">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="d4ae4-234">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="d4ae4-235">Ad esempio, `*.contoso.com` è consentita, `*contoso.com` non è consentita.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="d4ae4-236">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="d4ae4-237">Ad esempio, `contoso.com/*` è consentito, `contoso.com*` oppure `contoso.com/ab*` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="d4ae4-238">Tutti i sottopercorsi non sono impliciti in un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="d4ae4-239">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="d4ae4-240">`*.com*`non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="d4ae4-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="d4ae4-241">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="d4ae4-242">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="d4ae4-243">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="d4ae4-244">Ad esempio `~contoso.com` `contoso.com` , include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="d4ae4-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="d4ae4-245">Le voci URL che contengono protocolli (ad esempio,, `http://` `https://` o `ftp://` ) avranno esito negativo, perché le voci URL si applicano a tutti i protocolli.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="d4ae4-246">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="d4ae4-247">Le virgolette (' or ') sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="d4ae4-248">Un URL deve includere tutti i reindirizzamenti laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="d4ae4-249">Scenari di immissione URL</span><span class="sxs-lookup"><span data-stu-id="d4ae4-249">URL entry scenarios</span></span>

<span data-ttu-id="d4ae4-250">Le voci URL valide e i relativi risultati sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d4ae4-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="d4ae4-251">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="d4ae4-251">Scenario: No wildcards</span></span>

<span data-ttu-id="d4ae4-252">**Voce**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="d4ae4-253">**Consenti corrispondenza**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="d4ae4-254">**Consenti non confrontato**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="d4ae4-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-255">abc-contoso.com</span></span>
  - <span data-ttu-id="d4ae4-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-256">contoso.com/a</span></span>
  - <span data-ttu-id="d4ae4-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="d4ae4-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="d4ae4-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-260">www.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-261">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="d4ae4-262">**Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-262">**Block match**:</span></span>

  - <span data-ttu-id="d4ae4-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-263">contoso.com</span></span>
  - <span data-ttu-id="d4ae4-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-264">contoso.com/a</span></span>
  - <span data-ttu-id="d4ae4-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="d4ae4-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="d4ae4-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-268">www.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-269">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="d4ae4-270">**Blocca non confrontato**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="d4ae4-271">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="d4ae4-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="d4ae4-272">**Voce**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="d4ae4-273">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d4ae4-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-274">www.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d4ae4-276">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d4ae4-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-277">123contoso.com</span></span>
  - <span data-ttu-id="d4ae4-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-278">contoso.com</span></span>
  - <span data-ttu-id="d4ae4-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="d4ae4-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d4ae4-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="d4ae4-281">Scenario: carattere jolly destro nella parte superiore del percorso</span><span class="sxs-lookup"><span data-stu-id="d4ae4-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="d4ae4-282">**Voce**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="d4ae4-283">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d4ae4-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="d4ae4-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="d4ae4-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d4ae4-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d4ae4-286">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="d4ae4-287">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d4ae4-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-288">contoso.com</span></span>
  - <span data-ttu-id="d4ae4-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-289">contoso.com/a</span></span>
  - <span data-ttu-id="d4ae4-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-290">www.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-291">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="d4ae4-292">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="d4ae4-292">Scenario: Left tilde</span></span>

<span data-ttu-id="d4ae4-293">**Voce**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="d4ae4-294">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d4ae4-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-295">contoso.com</span></span>
  - <span data-ttu-id="d4ae4-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-296">www.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d4ae4-298">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d4ae4-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-299">123contoso.com</span></span>
  - <span data-ttu-id="d4ae4-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d4ae4-300">contoso.com/abc</span></span>
  - <span data-ttu-id="d4ae4-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d4ae4-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="d4ae4-302">Scenario: suffisso con caratteri jolly giusti</span><span class="sxs-lookup"><span data-stu-id="d4ae4-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="d4ae4-303">**Voce**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="d4ae4-304">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d4ae4-305">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="d4ae4-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-306">contoso.com/a</span></span>
  - <span data-ttu-id="d4ae4-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d4ae4-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d4ae4-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="d4ae4-308">contoso.com/ab</span></span>
  - <span data-ttu-id="d4ae4-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d4ae4-309">contoso.com/b</span></span>
  - <span data-ttu-id="d4ae4-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="d4ae4-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="d4ae4-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="d4ae4-311">contoso.com/ba</span></span>

- <span data-ttu-id="d4ae4-312">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="d4ae4-313">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="d4ae4-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="d4ae4-314">**Voce**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="d4ae4-315">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d4ae4-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="d4ae4-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="d4ae4-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d4ae4-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d4ae4-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="d4ae4-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="d4ae4-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="d4ae4-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="d4ae4-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="d4ae4-321">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d4ae4-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="d4ae4-322">Scenario: tilde sinistro e destro</span><span class="sxs-lookup"><span data-stu-id="d4ae4-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="d4ae4-323">**Voce**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="d4ae4-324">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d4ae4-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-325">contoso.com</span></span>
  - <span data-ttu-id="d4ae4-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-326">contoso.com/a</span></span>
  - <span data-ttu-id="d4ae4-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-327">www.contoso.com</span></span>
  - <span data-ttu-id="d4ae4-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d4ae4-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="d4ae4-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d4ae4-330">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d4ae4-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-331">123contoso.com</span></span>
  - <span data-ttu-id="d4ae4-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="d4ae4-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="d4ae4-333">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="d4ae4-333">Scenario: IP address</span></span>

<span data-ttu-id="d4ae4-334">**Voce**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="d4ae4-335">**Consenti** corrispondenza e **blocca corrispondenza**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="d4ae4-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="d4ae4-336">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d4ae4-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="d4ae4-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="d4ae4-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="d4ae4-339">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="d4ae4-339">IP address with right wildcard</span></span>

<span data-ttu-id="d4ae4-340">**Voce**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="d4ae4-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="d4ae4-341">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d4ae4-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="d4ae4-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="d4ae4-343">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="d4ae4-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="d4ae4-344">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="d4ae4-344">Examples of invalid entries</span></span>

<span data-ttu-id="d4ae4-345">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-345">The following entries are invalid:</span></span>

- <span data-ttu-id="d4ae4-346">**Valori di dominio mancanti o non validi**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="d4ae4-347">contoso</span><span class="sxs-lookup"><span data-stu-id="d4ae4-347">contoso</span></span>
  - <span data-ttu-id="d4ae4-348">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="d4ae4-349">\*. com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-349">\*.com</span></span>
  - <span data-ttu-id="d4ae4-350">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="d4ae4-350">\*.pdf</span></span>

- <span data-ttu-id="d4ae4-351">**Carattere jolly su testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="d4ae4-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-352">\*contoso.com</span></span>
  - <span data-ttu-id="d4ae4-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-353">contoso.com\*</span></span>
  - <span data-ttu-id="d4ae4-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="d4ae4-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="d4ae4-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="d4ae4-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="d4ae4-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="d4ae4-358">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="d4ae4-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="d4ae4-359">contoso.com:443</span></span>
  - <span data-ttu-id="d4ae4-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="d4ae4-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="d4ae4-361">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="d4ae4-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-362">\*.\*</span></span>

- <span data-ttu-id="d4ae4-363">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="d4ae4-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="d4ae4-364">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-364">conto\*so.com</span></span>
  - <span data-ttu-id="d4ae4-365">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="d4ae4-365">conto~so.com</span></span>

- <span data-ttu-id="d4ae4-366">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="d4ae4-366">**Double wildcards**</span></span>

  - <span data-ttu-id="d4ae4-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="d4ae4-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="d4ae4-368">contoso.com/\*/\*</span></span>
