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
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726817"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-103">Gestire gli URL e i file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="1f6c4-104">Le funzionalità descritte in questo argomento sono in anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="1f6c4-105">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto di filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="1f6c4-106">Ad esempio, un buon messaggio potrebbe essere contrassegnato come negativo (falso positivo) oppure potrebbe essere consentito un messaggio non valido tramite (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="1f6c4-107">L'elenco Consenti/blocca tenant nel centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtraggio di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="1f6c4-108">L'elenco Consenti/blocca tenant viene utilizzato durante il flusso di posta e al momento dell'utente fa clic su.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="1f6c4-109">È possibile specificare gli URL e i file da consentire o bloccare nell'elenco tenant Allow/Block.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="1f6c4-110">In questo argomento viene descritto come configurare le voci nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con le cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1f6c4-111">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="1f6c4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1f6c4-112">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1f6c4-113">Per accedere direttamente alla pagina dell' **elenco Consenti/blocca tenant** , utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="1f6c4-114">È possibile specificare i file utilizzando il valore hash SHA256 del file.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="1f6c4-115">Per trovare il valore hash di SHA256 di un file in Windows, al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="1f6c4-116">Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="1f6c4-117">I valori dell'hash percettivo (pHash) non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="1f6c4-118">I valori degli URL disponibili sono descritti nella [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="1f6c4-119">L'elenco Consenti/blocca tenant consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="1f6c4-120">Una voce dovrebbe essere attiva entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="1f6c4-121">Le voci di blocco hanno la precedenza su Consenti voci.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="1f6c4-122">Per impostazione predefinita, le voci nell'elenco Consenti/blocca tenant scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="1f6c4-123">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="1f6c4-124">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1f6c4-125">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1f6c4-126">Prima di poter eseguire le procedure descritte in questo argomento, è necessario assegnare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="1f6c4-127">Per aggiungere e rimuovere valori dall'elenco Consenti/blocca tenant, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1f6c4-128">**Gestione organizzazione** o **amministratore della sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1f6c4-129">Gestione dell' **organizzazione** o **gestione dell'igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="1f6c4-130">Per l'accesso in sola lettura all'elenco Consenti/blocca tenant, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1f6c4-131">**Lettore di sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1f6c4-132">**Gestione dell'organizzazione in sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-133">Utilizzare il Centro sicurezza & conformità per creare le voci URL nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1f6c4-134">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="1f6c4-135">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1f6c4-136">Nella pagina **elenco Consenti/blocca tenant** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Aggiungi**</span><span class="sxs-lookup"><span data-stu-id="1f6c4-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="1f6c4-137">Nel riquadro a comparsa **Aggiungi nuovo URL** visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1f6c4-138">**Aggiungere URL con caratteri jolly**: immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1f6c4-139">**Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** gli URL specificati.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="1f6c4-140">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1f6c4-141">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1f6c4-142">oppure</span><span class="sxs-lookup"><span data-stu-id="1f6c4-142">or</span></span>

     - <span data-ttu-id="1f6c4-143">Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1f6c4-145">.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-145">.</span></span>

   - <span data-ttu-id="1f6c4-146">**Nota facoltativa**: immettere il testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1f6c4-147">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-148">Utilizzare il Centro sicurezza & conformità per creare voci di file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1f6c4-149">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1f6c4-150">Nella pagina **elenco Consenti/blocca tenant** selezionare scheda **file** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="1f6c4-151">Nel riquadro a comparsa dei **nuovi file** che viene visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1f6c4-152">**Aggiungere gli hash dei file**: immettere un valore hash SHA256 per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1f6c4-153">**Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** i file specificati.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="1f6c4-154">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1f6c4-155">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1f6c4-156">oppure</span><span class="sxs-lookup"><span data-stu-id="1f6c4-156">or</span></span>

     - <span data-ttu-id="1f6c4-157">Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1f6c4-159">.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-159">.</span></span>

   - <span data-ttu-id="1f6c4-160">**Nota facoltativa**: immettere il testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1f6c4-161">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-162">Utilizzare il Centro sicurezza & conformità per visualizzare le voci di URL e file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1f6c4-163">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1f6c4-164">Selezionare la scheda **URL** o la scheda **file** .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="1f6c4-165">Fare clic sulle intestazioni di colonna seguenti per ordinare in ordine crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="1f6c4-166">**Valore**: l'URL o il file hash.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="1f6c4-167">**Azione**: **blocca** o **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="1f6c4-168">**Data dell'ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="1f6c4-168">**Last updated date**</span></span>
- <span data-ttu-id="1f6c4-169">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="1f6c4-169">**Expiration date**</span></span>
- <span data-ttu-id="1f6c4-170">**Nota**</span><span class="sxs-lookup"><span data-stu-id="1f6c4-170">**Note**</span></span>

<span data-ttu-id="1f6c4-171">Fare clic su **gruppo** per raggruppare le voci in base all' **azione** (**blocca** o **Consenti**) o **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="1f6c4-172">Fare clic su **ricerca**, immettere tutto o parte di un valore URL o file e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="1f6c4-173">Al termine, fare clic su **Pulisci** ![ icona ricerca in ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) chiaro.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="1f6c4-174">Fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-174">Click **Filter**.</span></span> <span data-ttu-id="1f6c4-175">Nel riquadro a comparsa del **filtro** visualizzato, configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="1f6c4-176">**Azione**: selezionare **Consenti**, **blocca** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="1f6c4-177">**Non scade mai**: selezionare disattivata (disattivazione ![ ](../../media/scc-toggle-off.png) ) o attivata ( ![ attiva o disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="1f6c4-178">**Ultimo aggiornamento**: selezionare una data di inizio (**da**), una data di fine (**a**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="1f6c4-179">**Data di scadenza**: selezionare una data di inizio (**da**), una data**di**fine (a) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="1f6c4-180">Al termine, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="1f6c4-181">Per cancellare i filtri esistenti, fare clic su **filtro**e, nel riquadro a comparsa **filtro** visualizzato, fare clic su **Pulisci filtri**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-182">Utilizzare il Centro sicurezza & conformità per modificare le voci di URL e file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1f6c4-183">Non è possibile modificare l'URL o il valore del file stesso.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="1f6c4-184">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="1f6c4-185">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1f6c4-186">Selezionare la scheda **URL** o la scheda **file** .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="1f6c4-187">Selezionare la voce che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="1f6c4-188">Nel riquadro a comparsa visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1f6c4-189">**Blocca/Consenti**: selezionare **Consenti** o **blocca**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="1f6c4-190">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1f6c4-191">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per la voce.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="1f6c4-192">oppure</span><span class="sxs-lookup"><span data-stu-id="1f6c4-192">or</span></span>

     - <span data-ttu-id="1f6c4-193">Spostare l'interruttore verso destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1f6c4-195">.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-195">.</span></span>

   - <span data-ttu-id="1f6c4-196">**Nota facoltativa**: immettere il testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="1f6c4-197">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-198">Utilizzare il Centro sicurezza & conformità per rimuovere URL e voci di file dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1f6c4-199">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1f6c4-200">Selezionare la scheda **URL** o la scheda **file** .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="1f6c4-201">Selezionare la voce che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="1f6c4-202">Nella finestra di dialogo di avviso visualizzata, fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-203">Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-204">Utilizzo di PowerShell per aggiungere URL e voci di file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1f6c4-205">Per aggiungere voci di URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1f6c4-206">In questo esempio viene aggiunta una voce di blocco URL per contoso.com e tutti i sottodomini (ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="1f6c4-207">Poiché non sono stati utilizzati i parametri ExpirationDate o NOEXPIRE, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="1f6c4-208">In questo esempio viene aggiunta una voce Consenti file per i file specificati che non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="1f6c4-209">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-210">Utilizzo di PowerShell per visualizzare le voci degli URL e dei file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1f6c4-211">Per visualizzare le voci relative a URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="1f6c4-212">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="1f6c4-213">In questo esempio vengono restituite le informazioni relative al valore hash del file specificato.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="1f6c4-214">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-215">Utilizzo di PowerShell per modificare le voci di URL e file nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1f6c4-216">Non è possibile modificare l'URL o il valore del file stesso.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="1f6c4-217">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="1f6c4-218">Per modificare le voci di URL e file nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1f6c4-219">In questo esempio viene modificata la data di scadenza della voce specificata.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="1f6c4-220">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-221">Utilizzo di PowerShell per rimuovere URL e voci di file dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1f6c4-222">Per rimuovere l'URL e le voci di file dall'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1f6c4-223">In questo esempio viene rimossa la voce URL specificata dall'elenco Consenti/blocca tenant.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="1f6c4-224">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="1f6c4-225">Sintassi URL per l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="1f6c4-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="1f6c4-226">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="1f6c4-227">Le estensioni dei nomi di file non sono consentite (ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="1f6c4-228">Unicode non è supportato, ma Punycode è.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="1f6c4-229">I nomi host sono consentiti se sono soddisfatte tutte le seguenti affermazioni:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="1f6c4-230">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="1f6c4-231">Vi è almeno un carattere a sinistra del punto.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="1f6c4-232">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="1f6c4-233">Ad esempio, `t.co` è consentito, `.com` oppure `contoso.` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="1f6c4-234">I sottopercorsi non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="1f6c4-235">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="1f6c4-236">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="1f6c4-237">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="1f6c4-238">Ad esempio, `*.contoso.com` è consentita, `*contoso.com` non è consentita.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="1f6c4-239">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="1f6c4-240">Ad esempio, `contoso.com/*` è consentito, `contoso.com*` oppure `contoso.com/ab*` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="1f6c4-241">Tutti i sottopercorsi non sono impliciti in un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="1f6c4-242">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="1f6c4-243">`*.com*`non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="1f6c4-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="1f6c4-244">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="1f6c4-245">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="1f6c4-246">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="1f6c4-247">Ad esempio `~contoso.com` `contoso.com` , include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1f6c4-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="1f6c4-248">Le voci URL che contengono protocolli (ad esempio,, `http://` `https://` o `ftp://` ) avranno esito negativo, perché le voci URL si applicano a tutti i protocolli.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="1f6c4-249">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="1f6c4-250">Le virgolette (' or ') sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="1f6c4-251">Un URL deve includere tutti i reindirizzamenti laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="1f6c4-252">Scenari di immissione URL</span><span class="sxs-lookup"><span data-stu-id="1f6c4-252">URL entry scenarios</span></span>

<span data-ttu-id="1f6c4-253">Le voci URL valide e i relativi risultati sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1f6c4-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="1f6c4-254">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="1f6c4-254">Scenario: No wildcards</span></span>

<span data-ttu-id="1f6c4-255">**Voce**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="1f6c4-256">**Consenti corrispondenza**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="1f6c4-257">**Consenti non confrontato**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="1f6c4-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-258">abc-contoso.com</span></span>
  - <span data-ttu-id="1f6c4-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-259">contoso.com/a</span></span>
  - <span data-ttu-id="1f6c4-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="1f6c4-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1f6c4-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-263">www.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-264">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="1f6c4-265">**Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-265">**Block match**:</span></span>

  - <span data-ttu-id="1f6c4-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-266">contoso.com</span></span>
  - <span data-ttu-id="1f6c4-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-267">contoso.com/a</span></span>
  - <span data-ttu-id="1f6c4-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="1f6c4-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1f6c4-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-271">www.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-272">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1f6c4-273">**Blocca non confrontato**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="1f6c4-274">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="1f6c4-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="1f6c4-275">**Voce**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="1f6c4-276">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1f6c4-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-277">www.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1f6c4-279">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1f6c4-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-280">123contoso.com</span></span>
  - <span data-ttu-id="1f6c4-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-281">contoso.com</span></span>
  - <span data-ttu-id="1f6c4-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="1f6c4-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1f6c4-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="1f6c4-284">Scenario: carattere jolly destro nella parte superiore del percorso</span><span class="sxs-lookup"><span data-stu-id="1f6c4-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="1f6c4-285">**Voce**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="1f6c4-286">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1f6c4-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="1f6c4-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="1f6c4-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1f6c4-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1f6c4-289">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="1f6c4-290">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1f6c4-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-291">contoso.com</span></span>
  - <span data-ttu-id="1f6c4-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-292">contoso.com/a</span></span>
  - <span data-ttu-id="1f6c4-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-293">www.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-294">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="1f6c4-295">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="1f6c4-295">Scenario: Left tilde</span></span>

<span data-ttu-id="1f6c4-296">**Voce**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="1f6c4-297">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1f6c4-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-298">contoso.com</span></span>
  - <span data-ttu-id="1f6c4-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-299">www.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1f6c4-301">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1f6c4-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-302">123contoso.com</span></span>
  - <span data-ttu-id="1f6c4-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1f6c4-303">contoso.com/abc</span></span>
  - <span data-ttu-id="1f6c4-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1f6c4-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="1f6c4-305">Scenario: suffisso con caratteri jolly giusti</span><span class="sxs-lookup"><span data-stu-id="1f6c4-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="1f6c4-306">**Voce**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="1f6c4-307">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1f6c4-308">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="1f6c4-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-309">contoso.com/a</span></span>
  - <span data-ttu-id="1f6c4-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1f6c4-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1f6c4-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1f6c4-311">contoso.com/ab</span></span>
  - <span data-ttu-id="1f6c4-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1f6c4-312">contoso.com/b</span></span>
  - <span data-ttu-id="1f6c4-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1f6c4-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1f6c4-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1f6c4-314">contoso.com/ba</span></span>

- <span data-ttu-id="1f6c4-315">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="1f6c4-316">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="1f6c4-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="1f6c4-317">**Voce**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="1f6c4-318">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1f6c4-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1f6c4-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="1f6c4-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1f6c4-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1f6c4-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="1f6c4-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1f6c4-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1f6c4-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1f6c4-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="1f6c4-324">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1f6c4-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="1f6c4-325">Scenario: tilde sinistro e destro</span><span class="sxs-lookup"><span data-stu-id="1f6c4-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="1f6c4-326">**Voce**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="1f6c4-327">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1f6c4-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-328">contoso.com</span></span>
  - <span data-ttu-id="1f6c4-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-329">contoso.com/a</span></span>
  - <span data-ttu-id="1f6c4-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-330">www.contoso.com</span></span>
  - <span data-ttu-id="1f6c4-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1f6c4-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="1f6c4-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1f6c4-333">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1f6c4-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-334">123contoso.com</span></span>
  - <span data-ttu-id="1f6c4-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="1f6c4-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="1f6c4-336">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="1f6c4-336">Scenario: IP address</span></span>

<span data-ttu-id="1f6c4-337">**Voce**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="1f6c4-338">**Consenti** corrispondenza e **blocca corrispondenza**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1f6c4-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="1f6c4-339">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1f6c4-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="1f6c4-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1f6c4-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="1f6c4-342">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="1f6c4-342">IP address with right wildcard</span></span>

<span data-ttu-id="1f6c4-343">**Voce**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="1f6c4-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="1f6c4-344">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1f6c4-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="1f6c4-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="1f6c4-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="1f6c4-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="1f6c4-347">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="1f6c4-347">Examples of invalid entries</span></span>

<span data-ttu-id="1f6c4-348">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-348">The following entries are invalid:</span></span>

- <span data-ttu-id="1f6c4-349">**Valori di dominio mancanti o non validi**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="1f6c4-350">contoso</span><span class="sxs-lookup"><span data-stu-id="1f6c4-350">contoso</span></span>
  - <span data-ttu-id="1f6c4-351">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="1f6c4-352">\*. com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-352">\*.com</span></span>
  - <span data-ttu-id="1f6c4-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="1f6c4-353">\*.pdf</span></span>

- <span data-ttu-id="1f6c4-354">**Carattere jolly su testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="1f6c4-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-355">\*contoso.com</span></span>
  - <span data-ttu-id="1f6c4-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-356">contoso.com\*</span></span>
  - <span data-ttu-id="1f6c4-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1f6c4-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="1f6c4-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="1f6c4-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="1f6c4-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="1f6c4-361">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="1f6c4-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="1f6c4-362">contoso.com:443</span></span>
  - <span data-ttu-id="1f6c4-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="1f6c4-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="1f6c4-364">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="1f6c4-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-365">\*.\*</span></span>

- <span data-ttu-id="1f6c4-366">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="1f6c4-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="1f6c4-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-367">conto\*so.com</span></span>
  - <span data-ttu-id="1f6c4-368">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="1f6c4-368">conto~so.com</span></span>

- <span data-ttu-id="1f6c4-369">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="1f6c4-369">**Double wildcards**</span></span>

  - <span data-ttu-id="1f6c4-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="1f6c4-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="1f6c4-371">contoso.com/\*/\*</span></span>
