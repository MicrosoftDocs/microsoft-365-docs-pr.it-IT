---
title: Gestire gli URL consentiti e bloccati nell'elenco Consenti/blocca tenant
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come configurare le voci URL nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance.
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845943"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-103">Gestire URL e file nell'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="567f5-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="567f5-104">Le funzionalità descritte in questo argomento sono in anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="567f5-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="567f5-105">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto di filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="567f5-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="567f5-106">Ad esempio, un buon messaggio potrebbe essere contrassegnato come negativo (falso positivo) oppure potrebbe essere consentito un messaggio non valido tramite (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="567f5-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="567f5-107">L'elenco Consenti/blocca tenant nel centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtraggio di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="567f5-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="567f5-108">L'elenco Consenti/blocca tenant viene utilizzato durante il flusso di posta e al momento dell'utente fa clic su.</span><span class="sxs-lookup"><span data-stu-id="567f5-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="567f5-109">È possibile specificare gli URL da consentire o bloccare nell'elenco tenant Allow/Block.</span><span class="sxs-lookup"><span data-stu-id="567f5-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="567f5-110">In questo argomento viene descritto come configurare le voci nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con le cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="567f5-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="567f5-111">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="567f5-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="567f5-112">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="567f5-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="567f5-113">Per accedere direttamente alla pagina dell' **elenco Consenti/blocca tenant** , utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="567f5-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="567f5-114">I valori degli URL disponibili sono descritti nella [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="567f5-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="567f5-115">L'elenco Consenti/blocca tenant consente un massimo di 500 voci per gli URL.</span><span class="sxs-lookup"><span data-stu-id="567f5-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="567f5-116">Una voce dovrebbe essere attiva entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="567f5-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="567f5-117">Le voci di blocco hanno la precedenza su Consenti voci.</span><span class="sxs-lookup"><span data-stu-id="567f5-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="567f5-118">Per impostazione predefinita, le voci nell'elenco Consenti/blocca tenant scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="567f5-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="567f5-119">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="567f5-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="567f5-120">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="567f5-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="567f5-121">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="567f5-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="567f5-122">È necessario disporre delle autorizzazioni per eseguire le procedure di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="567f5-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="567f5-123">Per aggiungere e rimuovere valori dall'elenco Consenti/blocca tenant, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="567f5-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="567f5-124">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="567f5-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="567f5-125">**Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="567f5-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="567f5-126">Per l'accesso in sola lettura all'elenco Consenti/blocca tenant, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="567f5-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="567f5-127">**Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="567f5-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="567f5-128">**Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="567f5-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-129">Utilizzare il Centro sicurezza & conformità per creare le voci URL nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="567f5-130">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="567f5-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="567f5-131">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="567f5-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="567f5-132">Nella pagina **elenco Consenti/blocca tenant** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Aggiungi**</span><span class="sxs-lookup"><span data-stu-id="567f5-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="567f5-133">Nel riquadro a comparsa **Aggiungi nuovo URL** visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="567f5-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="567f5-134">**Aggiungere URL con caratteri jolly**: immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="567f5-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="567f5-135">**Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** gli URL specificati.</span><span class="sxs-lookup"><span data-stu-id="567f5-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="567f5-136">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="567f5-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="567f5-137">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.</span><span class="sxs-lookup"><span data-stu-id="567f5-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="567f5-138">oppure</span><span class="sxs-lookup"><span data-stu-id="567f5-138">or</span></span>

     - <span data-ttu-id="567f5-139">Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai:</span><span class="sxs-lookup"><span data-stu-id="567f5-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="567f5-141">.</span><span class="sxs-lookup"><span data-stu-id="567f5-141">.</span></span>

   - <span data-ttu-id="567f5-142">**Nota facoltativa**: immettere il testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="567f5-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="567f5-143">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="567f5-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-144">Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="567f5-145">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="567f5-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="567f5-146">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="567f5-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="567f5-147">Fare clic sulle intestazioni di colonna seguenti per ordinare in ordine crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="567f5-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="567f5-148">**Valore**</span><span class="sxs-lookup"><span data-stu-id="567f5-148">**Value**</span></span>
- <span data-ttu-id="567f5-149">**Azione**: **blocca** o **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="567f5-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="567f5-150">**Data dell'ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="567f5-150">**Last updated date**</span></span>
- <span data-ttu-id="567f5-151">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="567f5-151">**Expiration date**</span></span>
- <span data-ttu-id="567f5-152">**Nota**</span><span class="sxs-lookup"><span data-stu-id="567f5-152">**Note**</span></span>

<span data-ttu-id="567f5-153">Fare clic su **gruppo** per raggruppare le voci in base all' **azione** (**blocca** o **Consenti**) o **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="567f5-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="567f5-154">Fare clic su **ricerca**, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="567f5-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="567f5-155">Al termine, fare clic su **Pulisci** ![ icona ricerca in ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) chiaro.</span><span class="sxs-lookup"><span data-stu-id="567f5-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="567f5-156">Fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="567f5-156">Click **Filter**.</span></span> <span data-ttu-id="567f5-157">Nel riquadro a comparsa del **filtro** visualizzato, configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="567f5-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="567f5-158">**Azione**: selezionare **Consenti**, **blocca** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="567f5-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="567f5-159">**Non scade mai**: selezionare disattivata (disattivazione ![ ](../../media/scc-toggle-off.png) ) o attivata ( ![ attiva o disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="567f5-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="567f5-160">**Ultimo aggiornamento**: selezionare una data di inizio (**da**), una data di fine (**a**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="567f5-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="567f5-161">**Data di scadenza**: selezionare una data di inizio (**da**), una data**di**fine (a) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="567f5-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="567f5-162">Al termine, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="567f5-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="567f5-163">Per cancellare i filtri esistenti, fare clic su **filtro**e, nel riquadro a comparsa **filtro** visualizzato, fare clic su **Pulisci filtri**.</span><span class="sxs-lookup"><span data-stu-id="567f5-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-164">Utilizzare il Centro sicurezza & conformità per modificare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="567f5-165">Non è possibile modificare il valore dell'URL stesso.</span><span class="sxs-lookup"><span data-stu-id="567f5-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="567f5-166">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="567f5-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="567f5-167">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="567f5-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="567f5-168">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="567f5-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="567f5-169">Selezionare la voce che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="567f5-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="567f5-170">Nel riquadro a comparsa visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="567f5-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="567f5-171">**Blocca/Consenti**: selezionare **Consenti** o **blocca**.</span><span class="sxs-lookup"><span data-stu-id="567f5-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="567f5-172">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="567f5-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="567f5-173">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per la voce.</span><span class="sxs-lookup"><span data-stu-id="567f5-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="567f5-174">oppure</span><span class="sxs-lookup"><span data-stu-id="567f5-174">or</span></span>

     - <span data-ttu-id="567f5-175">Spostare l'interruttore verso destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="567f5-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="567f5-177">.</span><span class="sxs-lookup"><span data-stu-id="567f5-177">.</span></span>

   - <span data-ttu-id="567f5-178">**Nota facoltativa**: immettere il testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="567f5-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="567f5-179">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="567f5-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-180">Utilizzare il Centro sicurezza & conformità per rimuovere le voci dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="567f5-181">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="567f5-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="567f5-182">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="567f5-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="567f5-183">Selezionare la voce che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="567f5-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="567f5-184">Nella finestra di dialogo di avviso visualizzata, fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="567f5-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-185">Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-186">Utilizzo di PowerShell per aggiungere voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="567f5-187">Per aggiungere voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="567f5-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="567f5-188">In questo esempio viene aggiunta una voce di blocco URL per contoso.com e tutti i sottodomini (ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="567f5-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="567f5-189">Poiché non sono stati utilizzati i parametri ExpirationDate o NOEXPIRE, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="567f5-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="567f5-190">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="567f5-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-191">Utilizzo di PowerShell per visualizzare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="567f5-192">Per visualizzare le voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="567f5-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="567f5-193">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="567f5-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="567f5-194">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="567f5-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-195">Utilizzo di PowerShell per modificare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="567f5-196">Non è possibile modificare il valore dell'URL stesso.</span><span class="sxs-lookup"><span data-stu-id="567f5-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="567f5-197">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="567f5-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="567f5-198">Per modificare le voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="567f5-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="567f5-199">In questo esempio viene modificata la data di scadenza della voce specificata.</span><span class="sxs-lookup"><span data-stu-id="567f5-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="567f5-200">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="567f5-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-201">Utilizzo di PowerShell per rimuovere le voci dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="567f5-202">Per rimuovere le voci dall'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="567f5-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="567f5-203">In questo esempio viene rimossa la voce URL specificata dall'elenco Consenti/blocca tenant.</span><span class="sxs-lookup"><span data-stu-id="567f5-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="567f5-204">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="567f5-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="567f5-205">Sintassi URL per l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="567f5-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="567f5-206">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="567f5-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="567f5-207">Le estensioni dei nomi di file non sono consentite (ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="567f5-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="567f5-208">Unicode non è supportato, ma Punycode è.</span><span class="sxs-lookup"><span data-stu-id="567f5-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="567f5-209">I nomi host sono consentiti se sono soddisfatte tutte le seguenti affermazioni:</span><span class="sxs-lookup"><span data-stu-id="567f5-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="567f5-210">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="567f5-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="567f5-211">Vi è almeno un carattere a sinistra del punto.</span><span class="sxs-lookup"><span data-stu-id="567f5-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="567f5-212">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="567f5-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="567f5-213">Ad esempio, `t.co` è consentito, `.com` oppure `contoso.` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="567f5-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="567f5-214">I sottopercorsi non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="567f5-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="567f5-215">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="567f5-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="567f5-216">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="567f5-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="567f5-217">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="567f5-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="567f5-218">Ad esempio, `*.contoso.com` è consentita, `*contoso.com` non è consentita.</span><span class="sxs-lookup"><span data-stu-id="567f5-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="567f5-219">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="567f5-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="567f5-220">Ad esempio, `contoso.com/*` è consentito, `contoso.com*` oppure `contoso.com/ab*` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="567f5-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="567f5-221">Tutti i sottopercorsi non sono impliciti in un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="567f5-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="567f5-222">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="567f5-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="567f5-223">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="567f5-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="567f5-224">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="567f5-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="567f5-225">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="567f5-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="567f5-226">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="567f5-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="567f5-227">Ad esempio `~contoso.com` `contoso.com` , include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="567f5-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="567f5-228">Le voci URL che contengono protocolli (ad esempio,, `http://` `https://` o `ftp://` ) avranno esito negativo, perché le voci URL si applicano a tutti i protocolli.</span><span class="sxs-lookup"><span data-stu-id="567f5-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="567f5-229">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="567f5-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="567f5-230">Le virgolette (' or ') sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="567f5-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="567f5-231">Un URL deve includere tutti i reindirizzamenti laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="567f5-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="567f5-232">Scenari di immissione URL</span><span class="sxs-lookup"><span data-stu-id="567f5-232">URL entry scenarios</span></span>

<span data-ttu-id="567f5-233">Le voci URL valide e i relativi risultati sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="567f5-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="567f5-234">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="567f5-234">Scenario: No wildcards</span></span>

<span data-ttu-id="567f5-235">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="567f5-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="567f5-236">**Consenti corrispondenza**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="567f5-237">**Consenti non confrontato**:</span><span class="sxs-lookup"><span data-stu-id="567f5-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="567f5-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-238">abc-contoso.com</span></span>
  - <span data-ttu-id="567f5-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="567f5-239">contoso.com/a</span></span>
  - <span data-ttu-id="567f5-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="567f5-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="567f5-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="567f5-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-243">www.contoso.com</span></span>
  - <span data-ttu-id="567f5-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="567f5-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="567f5-245">**Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-245">**Block match**:</span></span>

  - <span data-ttu-id="567f5-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-246">contoso.com</span></span>
  - <span data-ttu-id="567f5-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="567f5-247">contoso.com/a</span></span>
  - <span data-ttu-id="567f5-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="567f5-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="567f5-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="567f5-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-251">www.contoso.com</span></span>
  - <span data-ttu-id="567f5-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="567f5-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="567f5-253">**Blocca non confrontato**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="567f5-254">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="567f5-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="567f5-255">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="567f5-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="567f5-256">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="567f5-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-257">www.contoso.com</span></span>
  - <span data-ttu-id="567f5-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="567f5-259">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="567f5-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="567f5-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-260">123contoso.com</span></span>
  - <span data-ttu-id="567f5-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-261">contoso.com</span></span>
  - <span data-ttu-id="567f5-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="567f5-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="567f5-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="567f5-264">Scenario: carattere jolly destro nella parte superiore del percorso</span><span class="sxs-lookup"><span data-stu-id="567f5-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="567f5-265">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="567f5-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="567f5-266">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="567f5-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="567f5-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="567f5-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="567f5-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="567f5-269">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="567f5-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="567f5-270">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="567f5-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="567f5-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-271">contoso.com</span></span>
  - <span data-ttu-id="567f5-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="567f5-272">contoso.com/a</span></span>
  - <span data-ttu-id="567f5-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-273">www.contoso.com</span></span>
  - <span data-ttu-id="567f5-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="567f5-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="567f5-275">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="567f5-275">Scenario: Left tilde</span></span>

<span data-ttu-id="567f5-276">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="567f5-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="567f5-277">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="567f5-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-278">contoso.com</span></span>
  - <span data-ttu-id="567f5-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-279">www.contoso.com</span></span>
  - <span data-ttu-id="567f5-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="567f5-281">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="567f5-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="567f5-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-282">123contoso.com</span></span>
  - <span data-ttu-id="567f5-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="567f5-283">contoso.com/abc</span></span>
  - <span data-ttu-id="567f5-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="567f5-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="567f5-285">Scenario: suffisso con caratteri jolly giusti</span><span class="sxs-lookup"><span data-stu-id="567f5-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="567f5-286">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="567f5-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="567f5-287">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="567f5-288">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="567f5-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="567f5-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="567f5-289">contoso.com/a</span></span>
  - <span data-ttu-id="567f5-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="567f5-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="567f5-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="567f5-291">contoso.com/ab</span></span>
  - <span data-ttu-id="567f5-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="567f5-292">contoso.com/b</span></span>
  - <span data-ttu-id="567f5-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="567f5-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="567f5-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="567f5-294">contoso.com/ba</span></span>

- <span data-ttu-id="567f5-295">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="567f5-296">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="567f5-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="567f5-297">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="567f5-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="567f5-298">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="567f5-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="567f5-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="567f5-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="567f5-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="567f5-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="567f5-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="567f5-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="567f5-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="567f5-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="567f5-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="567f5-304">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="567f5-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="567f5-305">Scenario: tilde sinistro e destro</span><span class="sxs-lookup"><span data-stu-id="567f5-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="567f5-306">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="567f5-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="567f5-307">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="567f5-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-308">contoso.com</span></span>
  - <span data-ttu-id="567f5-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="567f5-309">contoso.com/a</span></span>
  - <span data-ttu-id="567f5-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-310">www.contoso.com</span></span>
  - <span data-ttu-id="567f5-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="567f5-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="567f5-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="567f5-313">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="567f5-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="567f5-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-314">123contoso.com</span></span>
  - <span data-ttu-id="567f5-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="567f5-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="567f5-316">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="567f5-316">Scenario: IP address</span></span>

<span data-ttu-id="567f5-317">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="567f5-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="567f5-318">**Consenti** corrispondenza e **blocca corrispondenza**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="567f5-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="567f5-319">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="567f5-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="567f5-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="567f5-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="567f5-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="567f5-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="567f5-322">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="567f5-322">IP address with right wildcard</span></span>

<span data-ttu-id="567f5-323">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="567f5-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="567f5-324">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="567f5-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="567f5-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="567f5-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="567f5-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="567f5-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="567f5-327">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="567f5-327">Examples of invalid entries</span></span>

<span data-ttu-id="567f5-328">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="567f5-328">The following entries are invalid:</span></span>

- <span data-ttu-id="567f5-329">**Valori di dominio mancanti o non validi**:</span><span class="sxs-lookup"><span data-stu-id="567f5-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="567f5-330">contoso</span><span class="sxs-lookup"><span data-stu-id="567f5-330">contoso</span></span>
  - <span data-ttu-id="567f5-331">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="567f5-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="567f5-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="567f5-332">\*.com</span></span>
  - <span data-ttu-id="567f5-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="567f5-333">\*.pdf</span></span>

- <span data-ttu-id="567f5-334">**Carattere jolly su testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="567f5-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="567f5-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="567f5-335">\*contoso.com</span></span>
  - <span data-ttu-id="567f5-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="567f5-336">contoso.com\*</span></span>
  - <span data-ttu-id="567f5-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="567f5-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="567f5-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="567f5-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="567f5-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="567f5-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="567f5-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="567f5-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="567f5-341">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="567f5-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="567f5-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="567f5-342">contoso.com:443</span></span>
  - <span data-ttu-id="567f5-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="567f5-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="567f5-344">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="567f5-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="567f5-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="567f5-345">\*.\*</span></span>

- <span data-ttu-id="567f5-346">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="567f5-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="567f5-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="567f5-347">conto\*so.com</span></span>
  - <span data-ttu-id="567f5-348">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="567f5-348">conto~so.com</span></span>

- <span data-ttu-id="567f5-349">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="567f5-349">**Double wildcards**</span></span>

  - <span data-ttu-id="567f5-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="567f5-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="567f5-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="567f5-351">contoso.com/\*/\*</span></span>
