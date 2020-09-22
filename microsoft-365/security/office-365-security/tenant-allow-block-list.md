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
ms.openlocfilehash: eb9dcc5b239aae1366a0a2e0eebd68b3f0082e6b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202340"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-103">Gestire URL e file nell'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="db8c0-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="db8c0-104">Le funzionalità descritte in questo argomento sono in anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="db8c0-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="db8c0-105">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto di filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="db8c0-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="db8c0-106">Ad esempio, un buon messaggio potrebbe essere contrassegnato come negativo (falso positivo) oppure potrebbe essere consentito un messaggio non valido tramite (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="db8c0-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="db8c0-107">L'elenco Consenti/blocca tenant nel centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtraggio di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db8c0-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="db8c0-108">L'elenco Consenti/blocca tenant viene utilizzato durante il flusso di posta e al momento dell'utente fa clic su.</span><span class="sxs-lookup"><span data-stu-id="db8c0-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="db8c0-109">È possibile specificare gli URL da consentire o bloccare nell'elenco tenant Allow/Block.</span><span class="sxs-lookup"><span data-stu-id="db8c0-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="db8c0-110">In questo argomento viene descritto come configurare le voci nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con le cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="db8c0-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db8c0-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="db8c0-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="db8c0-112">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="db8c0-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="db8c0-113">Per accedere direttamente alla pagina dell' **elenco Consenti/blocca tenant** , utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="db8c0-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="db8c0-114">I valori degli URL disponibili sono descritti nella [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="db8c0-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="db8c0-115">L'elenco Consenti/blocca tenant consente un massimo di 500 voci per gli URL.</span><span class="sxs-lookup"><span data-stu-id="db8c0-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="db8c0-116">Una voce dovrebbe essere attiva entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="db8c0-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="db8c0-117">Le voci di blocco hanno la precedenza su Consenti voci.</span><span class="sxs-lookup"><span data-stu-id="db8c0-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="db8c0-118">Per impostazione predefinita, le voci nell'elenco Consenti/blocca tenant scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="db8c0-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="db8c0-119">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="db8c0-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="db8c0-120">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="db8c0-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="db8c0-121">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="db8c0-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="db8c0-122">È necessario disporre delle autorizzazioni per eseguire le procedure di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="db8c0-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="db8c0-123">Per aggiungere e rimuovere valori dall'elenco Consenti/blocca tenant, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="db8c0-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="db8c0-124">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="db8c0-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="db8c0-125">**Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="db8c0-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="db8c0-126">Per l'accesso in sola lettura all'elenco Consenti/blocca tenant, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="db8c0-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="db8c0-127">**Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="db8c0-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="db8c0-128">**Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="db8c0-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-129">Utilizzare il Centro sicurezza & conformità per creare le voci URL nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="db8c0-130">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="db8c0-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="db8c0-131">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="db8c0-132">Nella pagina **elenco Consenti/blocca tenant** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Aggiungi**</span><span class="sxs-lookup"><span data-stu-id="db8c0-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="db8c0-133">Nel riquadro a comparsa **Aggiungi nuovo URL** visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="db8c0-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="db8c0-134">**Aggiungere URL con caratteri jolly**: immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="db8c0-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="db8c0-135">**Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** gli URL specificati.</span><span class="sxs-lookup"><span data-stu-id="db8c0-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="db8c0-136">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db8c0-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="db8c0-137">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.</span><span class="sxs-lookup"><span data-stu-id="db8c0-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="db8c0-138">oppure</span><span class="sxs-lookup"><span data-stu-id="db8c0-138">or</span></span>

     - <span data-ttu-id="db8c0-139">Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai:</span><span class="sxs-lookup"><span data-stu-id="db8c0-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="db8c0-141">.</span><span class="sxs-lookup"><span data-stu-id="db8c0-141">.</span></span>

   - <span data-ttu-id="db8c0-142">**Nota facoltativa**: immettere il testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="db8c0-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="db8c0-143">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-144">Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="db8c0-145">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="db8c0-146">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="db8c0-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="db8c0-147">Fare clic sulle intestazioni di colonna seguenti per ordinare in ordine crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="db8c0-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="db8c0-148">**Valore**</span><span class="sxs-lookup"><span data-stu-id="db8c0-148">**Value**</span></span>
- <span data-ttu-id="db8c0-149">**Azione**: **blocca** o **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="db8c0-150">**Data dell'ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="db8c0-150">**Last updated date**</span></span>
- <span data-ttu-id="db8c0-151">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="db8c0-151">**Expiration date**</span></span>
- <span data-ttu-id="db8c0-152">**Nota**</span><span class="sxs-lookup"><span data-stu-id="db8c0-152">**Note**</span></span>

<span data-ttu-id="db8c0-153">Fare clic su **gruppo** per raggruppare le voci in base all' **azione** (**blocca** o **Consenti**) o **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="db8c0-154">Fare clic su **ricerca**, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="db8c0-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="db8c0-155">Al termine, fare clic su **Pulisci** ![ icona ricerca in ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) chiaro.</span><span class="sxs-lookup"><span data-stu-id="db8c0-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="db8c0-156">Fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-156">Click **Filter**.</span></span> <span data-ttu-id="db8c0-157">Nel riquadro a comparsa del **filtro** visualizzato, configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="db8c0-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="db8c0-158">**Azione**: selezionare **Consenti**, **blocca** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="db8c0-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="db8c0-159">**Non scade mai**: selezionare disattivata (disattivazione ![ ](../../media/scc-toggle-off.png) ) o attivata ( ![ attiva o disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="db8c0-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="db8c0-160">**Ultimo aggiornamento**: selezionare una data di inizio (**da**), una data di fine (**a**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="db8c0-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="db8c0-161">**Data di scadenza**: selezionare una data di inizio (**da**), una data**di**fine (a) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="db8c0-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="db8c0-162">Al termine, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="db8c0-163">Per cancellare i filtri esistenti, fare clic su **filtro**e, nel riquadro a comparsa **filtro** visualizzato, fare clic su **Pulisci filtri**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-164">Utilizzare il Centro sicurezza & conformità per modificare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="db8c0-165">Non è possibile modificare il valore dell'URL stesso.</span><span class="sxs-lookup"><span data-stu-id="db8c0-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="db8c0-166">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="db8c0-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="db8c0-167">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="db8c0-168">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="db8c0-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="db8c0-169">Selezionare la voce che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="db8c0-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="db8c0-170">Nel riquadro a comparsa visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="db8c0-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="db8c0-171">**Blocca/Consenti**: selezionare **Consenti** o **blocca**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="db8c0-172">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db8c0-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="db8c0-173">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per la voce.</span><span class="sxs-lookup"><span data-stu-id="db8c0-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="db8c0-174">oppure</span><span class="sxs-lookup"><span data-stu-id="db8c0-174">or</span></span>

     - <span data-ttu-id="db8c0-175">Spostare l'interruttore verso destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="db8c0-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="db8c0-177">.</span><span class="sxs-lookup"><span data-stu-id="db8c0-177">.</span></span>

   - <span data-ttu-id="db8c0-178">**Nota facoltativa**: immettere il testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="db8c0-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="db8c0-179">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-180">Utilizzare il Centro sicurezza & conformità per rimuovere le voci dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="db8c0-181">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \> **Policy** \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="db8c0-182">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="db8c0-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="db8c0-183">Selezionare la voce che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="db8c0-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="db8c0-184">Nella finestra di dialogo di avviso visualizzata, fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="db8c0-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-185">Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-186">Utilizzo di PowerShell per aggiungere voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="db8c0-187">Per aggiungere voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db8c0-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="db8c0-188">In questo esempio viene aggiunta una voce di blocco URL per contoso.com e tutti i sottodomini (ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="db8c0-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="db8c0-189">Poiché non sono stati utilizzati i parametri ExpirationDate o NOEXPIRE, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="db8c0-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="db8c0-190">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="db8c0-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-191">Utilizzo di PowerShell per visualizzare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="db8c0-192">Per visualizzare le voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db8c0-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="db8c0-193">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="db8c0-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="db8c0-194">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="db8c0-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-195">Utilizzo di PowerShell per modificare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="db8c0-196">Non è possibile modificare il valore dell'URL stesso.</span><span class="sxs-lookup"><span data-stu-id="db8c0-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="db8c0-197">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="db8c0-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="db8c0-198">Per modificare le voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db8c0-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="db8c0-199">In questo esempio viene modificata la data di scadenza della voce specificata.</span><span class="sxs-lookup"><span data-stu-id="db8c0-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="db8c0-200">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="db8c0-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-201">Utilizzo di PowerShell per rimuovere le voci dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="db8c0-202">Per rimuovere le voci dall'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db8c0-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="db8c0-203">In questo esempio viene rimossa la voce URL specificata dall'elenco Consenti/blocca tenant.</span><span class="sxs-lookup"><span data-stu-id="db8c0-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="db8c0-204">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="db8c0-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="db8c0-205">Sintassi URL per l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="db8c0-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="db8c0-206">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="db8c0-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="db8c0-207">Le estensioni dei nomi di file non sono consentite (ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="db8c0-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="db8c0-208">Unicode non è supportato, ma Punycode è.</span><span class="sxs-lookup"><span data-stu-id="db8c0-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="db8c0-209">I nomi host sono consentiti se sono soddisfatte tutte le seguenti affermazioni:</span><span class="sxs-lookup"><span data-stu-id="db8c0-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="db8c0-210">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="db8c0-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="db8c0-211">Vi è almeno un carattere a sinistra del punto.</span><span class="sxs-lookup"><span data-stu-id="db8c0-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="db8c0-212">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="db8c0-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="db8c0-213">Ad esempio, `t.co` è consentito, `.com` oppure `contoso.` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="db8c0-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="db8c0-214">I sottopercorsi non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="db8c0-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="db8c0-215">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="db8c0-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="db8c0-216">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="db8c0-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="db8c0-217">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="db8c0-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="db8c0-218">Ad esempio, `*.contoso.com` è consentita, `*contoso.com` non è consentita.</span><span class="sxs-lookup"><span data-stu-id="db8c0-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="db8c0-219">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="db8c0-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="db8c0-220">Ad esempio, `contoso.com/*` è consentito, `contoso.com*` oppure `contoso.com/ab*` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="db8c0-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="db8c0-221">Tutti i sottopercorsi non sono impliciti in un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="db8c0-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="db8c0-222">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="db8c0-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="db8c0-223">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="db8c0-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="db8c0-224">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="db8c0-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="db8c0-225">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="db8c0-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="db8c0-226">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="db8c0-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="db8c0-227">Ad esempio `~contoso.com` `contoso.com` , include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="db8c0-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="db8c0-228">Le voci URL che contengono protocolli (ad esempio,, `http://` `https://` o `ftp://` ) avranno esito negativo, perché le voci URL si applicano a tutti i protocolli.</span><span class="sxs-lookup"><span data-stu-id="db8c0-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="db8c0-229">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="db8c0-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="db8c0-230">Le virgolette (' or ') sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="db8c0-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="db8c0-231">Un URL deve includere tutti i reindirizzamenti laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="db8c0-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="db8c0-232">Scenari di immissione URL</span><span class="sxs-lookup"><span data-stu-id="db8c0-232">URL entry scenarios</span></span>

<span data-ttu-id="db8c0-233">Le voci URL valide e i relativi risultati sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="db8c0-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="db8c0-234">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="db8c0-234">Scenario: No wildcards</span></span>

<span data-ttu-id="db8c0-235">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="db8c0-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="db8c0-236">**Consenti corrispondenza**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="db8c0-237">**Consenti non confrontato**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="db8c0-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-238">abc-contoso.com</span></span>
  - <span data-ttu-id="db8c0-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-239">contoso.com/a</span></span>
  - <span data-ttu-id="db8c0-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="db8c0-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="db8c0-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="db8c0-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-243">www.contoso.com</span></span>
  - <span data-ttu-id="db8c0-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="db8c0-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="db8c0-245">**Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-245">**Block match**:</span></span>

  - <span data-ttu-id="db8c0-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-246">contoso.com</span></span>
  - <span data-ttu-id="db8c0-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-247">contoso.com/a</span></span>
  - <span data-ttu-id="db8c0-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="db8c0-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="db8c0-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="db8c0-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-251">www.contoso.com</span></span>
  - <span data-ttu-id="db8c0-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="db8c0-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="db8c0-253">**Blocca non confrontato**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="db8c0-254">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="db8c0-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="db8c0-255">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="db8c0-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="db8c0-256">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="db8c0-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-257">www.contoso.com</span></span>
  - <span data-ttu-id="db8c0-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="db8c0-259">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="db8c0-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="db8c0-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-260">123contoso.com</span></span>
  - <span data-ttu-id="db8c0-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-261">contoso.com</span></span>
  - <span data-ttu-id="db8c0-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="db8c0-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="db8c0-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="db8c0-264">Scenario: carattere jolly destro nella parte superiore del percorso</span><span class="sxs-lookup"><span data-stu-id="db8c0-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="db8c0-265">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="db8c0-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="db8c0-266">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="db8c0-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="db8c0-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="db8c0-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="db8c0-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="db8c0-269">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="db8c0-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="db8c0-270">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="db8c0-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="db8c0-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-271">contoso.com</span></span>
  - <span data-ttu-id="db8c0-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-272">contoso.com/a</span></span>
  - <span data-ttu-id="db8c0-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-273">www.contoso.com</span></span>
  - <span data-ttu-id="db8c0-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="db8c0-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="db8c0-275">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="db8c0-275">Scenario: Left tilde</span></span>

<span data-ttu-id="db8c0-276">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="db8c0-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="db8c0-277">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="db8c0-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-278">contoso.com</span></span>
  - <span data-ttu-id="db8c0-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-279">www.contoso.com</span></span>
  - <span data-ttu-id="db8c0-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="db8c0-281">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="db8c0-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="db8c0-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-282">123contoso.com</span></span>
  - <span data-ttu-id="db8c0-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="db8c0-283">contoso.com/abc</span></span>
  - <span data-ttu-id="db8c0-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="db8c0-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="db8c0-285">Scenario: suffisso con caratteri jolly giusti</span><span class="sxs-lookup"><span data-stu-id="db8c0-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="db8c0-286">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="db8c0-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="db8c0-287">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="db8c0-288">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="db8c0-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="db8c0-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-289">contoso.com/a</span></span>
  - <span data-ttu-id="db8c0-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="db8c0-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="db8c0-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="db8c0-291">contoso.com/ab</span></span>
  - <span data-ttu-id="db8c0-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="db8c0-292">contoso.com/b</span></span>
  - <span data-ttu-id="db8c0-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="db8c0-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="db8c0-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="db8c0-294">contoso.com/ba</span></span>

- <span data-ttu-id="db8c0-295">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="db8c0-296">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="db8c0-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="db8c0-297">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="db8c0-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="db8c0-298">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="db8c0-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="db8c0-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="db8c0-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="db8c0-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="db8c0-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="db8c0-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="db8c0-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="db8c0-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="db8c0-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="db8c0-304">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="db8c0-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="db8c0-305">Scenario: tilde sinistro e destro</span><span class="sxs-lookup"><span data-stu-id="db8c0-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="db8c0-306">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="db8c0-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="db8c0-307">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="db8c0-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-308">contoso.com</span></span>
  - <span data-ttu-id="db8c0-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-309">contoso.com/a</span></span>
  - <span data-ttu-id="db8c0-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-310">www.contoso.com</span></span>
  - <span data-ttu-id="db8c0-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="db8c0-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="db8c0-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="db8c0-313">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="db8c0-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="db8c0-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-314">123contoso.com</span></span>
  - <span data-ttu-id="db8c0-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="db8c0-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="db8c0-316">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="db8c0-316">Scenario: IP address</span></span>

<span data-ttu-id="db8c0-317">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="db8c0-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="db8c0-318">**Consenti** corrispondenza e **blocca corrispondenza**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="db8c0-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="db8c0-319">**Consenti non corrispondente** e **non corrisponde**a un blocco:</span><span class="sxs-lookup"><span data-stu-id="db8c0-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="db8c0-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="db8c0-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="db8c0-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="db8c0-322">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="db8c0-322">IP address with right wildcard</span></span>

<span data-ttu-id="db8c0-323">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="db8c0-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="db8c0-324">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="db8c0-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="db8c0-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="db8c0-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="db8c0-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="db8c0-327">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="db8c0-327">Examples of invalid entries</span></span>

<span data-ttu-id="db8c0-328">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="db8c0-328">The following entries are invalid:</span></span>

- <span data-ttu-id="db8c0-329">**Valori di dominio mancanti o non validi**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="db8c0-330">contoso</span><span class="sxs-lookup"><span data-stu-id="db8c0-330">contoso</span></span>
  - <span data-ttu-id="db8c0-331">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="db8c0-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="db8c0-332">\*.com</span></span>
  - <span data-ttu-id="db8c0-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="db8c0-333">\*.pdf</span></span>

- <span data-ttu-id="db8c0-334">**Carattere jolly su testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="db8c0-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-335">\*contoso.com</span></span>
  - <span data-ttu-id="db8c0-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-336">contoso.com\*</span></span>
  - <span data-ttu-id="db8c0-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="db8c0-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="db8c0-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="db8c0-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="db8c0-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="db8c0-341">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="db8c0-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="db8c0-342">contoso.com:443</span></span>
  - <span data-ttu-id="db8c0-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="db8c0-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="db8c0-344">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="db8c0-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-345">\*.\*</span></span>

- <span data-ttu-id="db8c0-346">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="db8c0-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="db8c0-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="db8c0-347">conto\*so.com</span></span>
  - <span data-ttu-id="db8c0-348">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="db8c0-348">conto~so.com</span></span>

- <span data-ttu-id="db8c0-349">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="db8c0-349">**Double wildcards**</span></span>

  - <span data-ttu-id="db8c0-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="db8c0-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="db8c0-351">contoso.com/\*/\*</span></span>
