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
ms.openlocfilehash: f60e2f29bf9b880e9d2247fa59554300ae348a03
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683212"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-103">Gestire URL nell'elenco di tenant consentiti/bloccati</span><span class="sxs-lookup"><span data-stu-id="9fafc-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="9fafc-104">Le funzionalità descritte in questo articolo sono in anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="9fafc-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="9fafc-105">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto di filtraggio EOP.</span><span class="sxs-lookup"><span data-stu-id="9fafc-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="9fafc-106">Ad esempio, un buon messaggio potrebbe essere contrassegnato come negativo (falso positivo) oppure potrebbe essere consentito un messaggio non valido tramite (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="9fafc-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="9fafc-107">L'elenco Consenti/blocca tenant nel centro sicurezza & conformità consente di ignorare manualmente i verdetti di filtraggio di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9fafc-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="9fafc-108">L'elenco Consenti/blocca tenant viene utilizzato durante il flusso di posta e al momento dell'utente fa clic su.</span><span class="sxs-lookup"><span data-stu-id="9fafc-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="9fafc-109">È possibile specificare gli URL da consentire o bloccare nell'elenco tenant Allow/Block.</span><span class="sxs-lookup"><span data-stu-id="9fafc-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="9fafc-110">In questo argomento viene descritto come configurare le voci nell'elenco Consenti/blocca tenant nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con le cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9fafc-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9fafc-111">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="9fafc-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9fafc-112">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9fafc-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9fafc-113">Per accedere direttamente alla pagina dell' **elenco Consenti/blocca tenant** , utilizzare <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="9fafc-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="9fafc-114">I valori degli URL disponibili sono descritti nella [sintassi degli URL per la sezione tenant Consenti/blocca elenco](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9fafc-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="9fafc-115">L'elenco Consenti/blocca tenant consente un massimo di 500 voci per gli URL.</span><span class="sxs-lookup"><span data-stu-id="9fafc-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="9fafc-116">Una voce dovrebbe essere attiva entro 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="9fafc-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="9fafc-117">Le voci di blocco hanno la precedenza su Consenti voci.</span><span class="sxs-lookup"><span data-stu-id="9fafc-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="9fafc-118">Per impostazione predefinita, le voci nell'elenco Consenti/blocca tenant scadranno dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="9fafc-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="9fafc-119">È possibile specificare una data o impostarla in modo che non scada mai.</span><span class="sxs-lookup"><span data-stu-id="9fafc-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="9fafc-120">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9fafc-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9fafc-121">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9fafc-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9fafc-122">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="9fafc-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9fafc-123">Per aggiungere e rimuovere valori dall'elenco Consenti/blocca tenant, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="9fafc-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9fafc-124">Per l'accesso in sola lettura all'elenco Consenti/blocca tenant, è necessario essere membri dei gruppi di ruoli **lettore globale** o **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="9fafc-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="9fafc-125">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9fafc-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="9fafc-126">**Note**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-126">**Notes**:</span></span>

  - <span data-ttu-id="9fafc-127">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9fafc-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9fafc-128">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9fafc-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="9fafc-129">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9fafc-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-130">Utilizzare il Centro sicurezza & conformità per creare le voci URL nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9fafc-131">Per informazioni dettagliate sulla sintassi per le voci URL, vedere la [sintassi degli URL per la sezione tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9fafc-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="9fafc-132">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \>  \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9fafc-133">Nella pagina **elenco Consenti/blocca tenant** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Aggiungi**</span><span class="sxs-lookup"><span data-stu-id="9fafc-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="9fafc-134">Nel riquadro a comparsa **Aggiungi nuovo URL** visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9fafc-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9fafc-135">**Aggiungere URL con caratteri jolly**: immettere un URL per riga, fino a un massimo di 20.</span><span class="sxs-lookup"><span data-stu-id="9fafc-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="9fafc-136">**Blocca/Consenti**: consente di selezionare se si desidera **consentire** o **bloccare** gli URL specificati.</span><span class="sxs-lookup"><span data-stu-id="9fafc-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="9fafc-137">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fafc-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9fafc-138">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per le voci.</span><span class="sxs-lookup"><span data-stu-id="9fafc-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="9fafc-139">oppure</span><span class="sxs-lookup"><span data-stu-id="9fafc-139">or</span></span>

     - <span data-ttu-id="9fafc-140">Spostare l'interruttore verso destra per configurare le voci in modo che non scadano mai:</span><span class="sxs-lookup"><span data-stu-id="9fafc-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="9fafc-142">.</span><span class="sxs-lookup"><span data-stu-id="9fafc-142">.</span></span>

   - <span data-ttu-id="9fafc-143">**Nota facoltativa**: immettere il testo descrittivo per le voci.</span><span class="sxs-lookup"><span data-stu-id="9fafc-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9fafc-144">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-145">Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9fafc-146">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \>  \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9fafc-147">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="9fafc-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="9fafc-148">Fare clic sulle intestazioni di colonna seguenti per ordinare in ordine crescente o decrescente:</span><span class="sxs-lookup"><span data-stu-id="9fafc-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="9fafc-149">**Valore**</span><span class="sxs-lookup"><span data-stu-id="9fafc-149">**Value**</span></span>
- <span data-ttu-id="9fafc-150">**Azione**: **blocca** o **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="9fafc-151">**Data dell'ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="9fafc-151">**Last updated date**</span></span>
- <span data-ttu-id="9fafc-152">**Data di scadenza**</span><span class="sxs-lookup"><span data-stu-id="9fafc-152">**Expiration date**</span></span>
- <span data-ttu-id="9fafc-153">**Nota**</span><span class="sxs-lookup"><span data-stu-id="9fafc-153">**Note**</span></span>

<span data-ttu-id="9fafc-154">Fare clic su **gruppo** per raggruppare le voci in base all' **azione** (**blocca** o **Consenti**) o **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="9fafc-155">Fare clic su **ricerca**, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="9fafc-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="9fafc-156">Al termine, fare clic su **Pulisci** ![ icona ricerca in ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) chiaro.</span><span class="sxs-lookup"><span data-stu-id="9fafc-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="9fafc-157">Fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-157">Click **Filter**.</span></span> <span data-ttu-id="9fafc-158">Nel riquadro a comparsa del **filtro** visualizzato, configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9fafc-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="9fafc-159">**Azione**: selezionare **Consenti**, **blocca** o entrambi.</span><span class="sxs-lookup"><span data-stu-id="9fafc-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="9fafc-160">**Non scade mai**: selezionare disattivata: attiva ![ ](../../media/scc-toggle-off.png) o disattiva: attiva o disattiva l'opzione ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="9fafc-160">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="9fafc-161">**Ultimo aggiornamento**: selezionare una data di inizio (**da**), una data di fine (**a**) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="9fafc-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="9fafc-162">**Data di scadenza**: selezionare una data di inizio (**da**), una data **di** fine (a) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="9fafc-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="9fafc-163">Al termine, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="9fafc-164">Per cancellare i filtri esistenti, fare clic su **filtro** e, nel riquadro a comparsa **filtro** visualizzato, fare clic su **Pulisci filtri**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-165">Utilizzare il Centro sicurezza & conformità per modificare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9fafc-166">Non è possibile modificare il valore dell'URL stesso.</span><span class="sxs-lookup"><span data-stu-id="9fafc-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="9fafc-167">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="9fafc-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="9fafc-168">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \>  \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9fafc-169">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="9fafc-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="9fafc-170">Selezionare la voce che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="9fafc-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="9fafc-171">Nel riquadro a comparsa visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9fafc-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9fafc-172">**Blocca/Consenti**: selezionare **Consenti** o **blocca**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="9fafc-173">Non **scade mai**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fafc-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9fafc-174">Verificare che l'impostazione sia disattivata ( ![ disattivazione disattivata ](../../media/scc-toggle-off.png) ) e che venga utilizzata la casella **scadenza** per specificare la data di scadenza per la voce.</span><span class="sxs-lookup"><span data-stu-id="9fafc-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="9fafc-175">oppure</span><span class="sxs-lookup"><span data-stu-id="9fafc-175">or</span></span>

     - <span data-ttu-id="9fafc-176">Spostare l'interruttore verso destra per configurare la voce in modo che non scada mai:</span><span class="sxs-lookup"><span data-stu-id="9fafc-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Attiva](../../media/scc-toggle-on.png)<span data-ttu-id="9fafc-178">.</span><span class="sxs-lookup"><span data-stu-id="9fafc-178">.</span></span>

   - <span data-ttu-id="9fafc-179">**Nota facoltativa**: immettere il testo descrittivo per la voce.</span><span class="sxs-lookup"><span data-stu-id="9fafc-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="9fafc-180">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-181">Utilizzare il Centro sicurezza & conformità per rimuovere le voci dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9fafc-182">Nel centro sicurezza & conformità accedere a elenchi di criteri di **gestione delle minacce** \>  \> **tenant/Block**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9fafc-183">Selezionare la scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="9fafc-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="9fafc-184">Selezionare la voce che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="9fafc-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="9fafc-185">Nella finestra di dialogo di avviso visualizzata, fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9fafc-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-186">Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-187">Utilizzo di PowerShell per aggiungere voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9fafc-188">Per aggiungere voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9fafc-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9fafc-189">In questo esempio viene aggiunta una voce di blocco URL per contoso.com e tutti i sottodomini (ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9fafc-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="9fafc-190">Poiché non sono stati utilizzati i parametri ExpirationDate o NOEXPIRE, la voce scade dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="9fafc-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="9fafc-191">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="9fafc-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-192">Utilizzo di PowerShell per visualizzare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9fafc-193">Per visualizzare le voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9fafc-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="9fafc-194">In questo esempio vengono restituiti tutti gli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="9fafc-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="9fafc-195">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="9fafc-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-196">Utilizzo di PowerShell per modificare le voci nell'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9fafc-197">Non è possibile modificare il valore dell'URL stesso.</span><span class="sxs-lookup"><span data-stu-id="9fafc-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="9fafc-198">Al contrario, è necessario eliminare la voce e ricrearla.</span><span class="sxs-lookup"><span data-stu-id="9fafc-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="9fafc-199">Per modificare le voci nell'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9fafc-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9fafc-200">In questo esempio viene modificata la data di scadenza della voce specificata.</span><span class="sxs-lookup"><span data-stu-id="9fafc-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="9fafc-201">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="9fafc-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-202">Utilizzo di PowerShell per rimuovere le voci dall'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9fafc-203">Per rimuovere le voci dall'elenco Consenti/blocca tenant, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9fafc-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9fafc-204">In questo esempio viene rimossa la voce URL specificata dall'elenco Consenti/blocca tenant.</span><span class="sxs-lookup"><span data-stu-id="9fafc-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="9fafc-205">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="9fafc-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="9fafc-206">Sintassi URL per l'elenco Consenti/blocca tenant</span><span class="sxs-lookup"><span data-stu-id="9fafc-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="9fafc-207">Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.</span><span class="sxs-lookup"><span data-stu-id="9fafc-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="9fafc-208">Le estensioni dei nomi di file non sono consentite (ad esempio, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="9fafc-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="9fafc-209">Unicode non è supportato, ma Punycode è.</span><span class="sxs-lookup"><span data-stu-id="9fafc-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="9fafc-210">I nomi host sono consentiti se sono soddisfatte tutte le seguenti affermazioni:</span><span class="sxs-lookup"><span data-stu-id="9fafc-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="9fafc-211">Il nome host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="9fafc-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="9fafc-212">Vi è almeno un carattere a sinistra del punto.</span><span class="sxs-lookup"><span data-stu-id="9fafc-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="9fafc-213">A destra del punto sono presenti almeno due caratteri.</span><span class="sxs-lookup"><span data-stu-id="9fafc-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="9fafc-214">Ad esempio, `t.co` è consentito, `.com` oppure `contoso.` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="9fafc-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="9fafc-215">I sottopercorsi non sono impliciti.</span><span class="sxs-lookup"><span data-stu-id="9fafc-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="9fafc-216">Ad esempio, `contoso.com` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9fafc-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="9fafc-217">I caratteri jolly (\*) sono consentiti negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fafc-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="9fafc-218">Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.</span><span class="sxs-lookup"><span data-stu-id="9fafc-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="9fafc-219">Ad esempio, `*.contoso.com` è consentita, `*contoso.com` non è consentita.</span><span class="sxs-lookup"><span data-stu-id="9fafc-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="9fafc-220">Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="9fafc-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="9fafc-221">Ad esempio, `contoso.com/*` è consentito, `contoso.com*` oppure `contoso.com/ab*` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="9fafc-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="9fafc-222">Tutti i sottopercorsi non sono impliciti in un carattere jolly destro.</span><span class="sxs-lookup"><span data-stu-id="9fafc-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="9fafc-223">Ad esempio, `contoso.com/*` non include `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9fafc-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="9fafc-224">`*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).</span><span class="sxs-lookup"><span data-stu-id="9fafc-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="9fafc-225">I caratteri jolly non sono consentiti negli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="9fafc-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="9fafc-226">Il carattere tilde (~) è disponibile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fafc-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="9fafc-227">Una tilde sinistra implica un dominio e tutti i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="9fafc-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="9fafc-228">Ad esempio `~contoso.com` `contoso.com` , include e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9fafc-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="9fafc-229">Le voci URL che contengono protocolli (ad esempio,, `http://` `https://` o `ftp://` ) avranno esito negativo, perché le voci URL si applicano a tutti i protocolli.</span><span class="sxs-lookup"><span data-stu-id="9fafc-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="9fafc-230">Un nome utente o una password non sono supportati o richiesti.</span><span class="sxs-lookup"><span data-stu-id="9fafc-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="9fafc-231">Le virgolette (' or ') sono caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="9fafc-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="9fafc-232">Un URL deve includere tutti i reindirizzamenti laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="9fafc-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="9fafc-233">Scenari di immissione URL</span><span class="sxs-lookup"><span data-stu-id="9fafc-233">URL entry scenarios</span></span>

<span data-ttu-id="9fafc-234">Le voci URL valide e i relativi risultati sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9fafc-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="9fafc-235">Scenario: nessun carattere jolly</span><span class="sxs-lookup"><span data-stu-id="9fafc-235">Scenario: No wildcards</span></span>

<span data-ttu-id="9fafc-236">**Voce**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9fafc-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="9fafc-237">**Consenti corrispondenza**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="9fafc-238">**Consenti non confrontato**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="9fafc-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-239">abc-contoso.com</span></span>
  - <span data-ttu-id="9fafc-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-240">contoso.com/a</span></span>
  - <span data-ttu-id="9fafc-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="9fafc-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="9fafc-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9fafc-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-244">www.contoso.com</span></span>
  - <span data-ttu-id="9fafc-245">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="9fafc-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9fafc-246">**Blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-246">**Block match**:</span></span>

  - <span data-ttu-id="9fafc-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-247">contoso.com</span></span>
  - <span data-ttu-id="9fafc-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-248">contoso.com/a</span></span>
  - <span data-ttu-id="9fafc-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="9fafc-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="9fafc-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9fafc-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-252">www.contoso.com</span></span>
  - <span data-ttu-id="9fafc-253">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="9fafc-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9fafc-254">**Blocca non confrontato**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="9fafc-255">Scenario: carattere jolly sinistro (sottodominio)</span><span class="sxs-lookup"><span data-stu-id="9fafc-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="9fafc-256">**Voce**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9fafc-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="9fafc-257">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9fafc-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-258">www.contoso.com</span></span>
  - <span data-ttu-id="9fafc-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9fafc-260">**Consenti non corrispondente** e **non corrisponde** a un blocco:</span><span class="sxs-lookup"><span data-stu-id="9fafc-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9fafc-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-261">123contoso.com</span></span>
  - <span data-ttu-id="9fafc-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-262">contoso.com</span></span>
  - <span data-ttu-id="9fafc-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="9fafc-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9fafc-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="9fafc-265">Scenario: carattere jolly destro nella parte superiore del percorso</span><span class="sxs-lookup"><span data-stu-id="9fafc-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="9fafc-266">**Voce**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="9fafc-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="9fafc-267">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9fafc-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="9fafc-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="9fafc-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9fafc-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9fafc-270">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="9fafc-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="9fafc-271">**Consenti non corrispondente** e **non corrisponde** a un blocco:</span><span class="sxs-lookup"><span data-stu-id="9fafc-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9fafc-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-272">contoso.com</span></span>
  - <span data-ttu-id="9fafc-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-273">contoso.com/a</span></span>
  - <span data-ttu-id="9fafc-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-274">www.contoso.com</span></span>
  - <span data-ttu-id="9fafc-275">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="9fafc-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="9fafc-276">Scenario: tilde sinistra</span><span class="sxs-lookup"><span data-stu-id="9fafc-276">Scenario: Left tilde</span></span>

<span data-ttu-id="9fafc-277">**Voce**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9fafc-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="9fafc-278">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9fafc-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-279">contoso.com</span></span>
  - <span data-ttu-id="9fafc-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-280">www.contoso.com</span></span>
  - <span data-ttu-id="9fafc-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9fafc-282">**Consenti non corrispondente** e **non corrisponde** a un blocco:</span><span class="sxs-lookup"><span data-stu-id="9fafc-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9fafc-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-283">123contoso.com</span></span>
  - <span data-ttu-id="9fafc-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9fafc-284">contoso.com/abc</span></span>
  - <span data-ttu-id="9fafc-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9fafc-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="9fafc-286">Scenario: suffisso con caratteri jolly giusti</span><span class="sxs-lookup"><span data-stu-id="9fafc-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="9fafc-287">**Voce**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9fafc-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="9fafc-288">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9fafc-289">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="9fafc-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="9fafc-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-290">contoso.com/a</span></span>
  - <span data-ttu-id="9fafc-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9fafc-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9fafc-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9fafc-292">contoso.com/ab</span></span>
  - <span data-ttu-id="9fafc-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9fafc-293">contoso.com/b</span></span>
  - <span data-ttu-id="9fafc-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9fafc-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9fafc-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9fafc-295">contoso.com/ba</span></span>

- <span data-ttu-id="9fafc-296">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="9fafc-297">Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro</span><span class="sxs-lookup"><span data-stu-id="9fafc-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="9fafc-298">**Voce**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9fafc-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="9fafc-299">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9fafc-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9fafc-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="9fafc-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9fafc-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9fafc-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="9fafc-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9fafc-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9fafc-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9fafc-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="9fafc-305">**Consenti non corrispondente** e **blocco non corrispondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9fafc-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="9fafc-306">Scenario: tilde sinistro e destro</span><span class="sxs-lookup"><span data-stu-id="9fafc-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="9fafc-307">**Voce**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="9fafc-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="9fafc-308">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9fafc-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-309">contoso.com</span></span>
  - <span data-ttu-id="9fafc-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-310">contoso.com/a</span></span>
  - <span data-ttu-id="9fafc-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-311">www.contoso.com</span></span>
  - <span data-ttu-id="9fafc-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9fafc-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="9fafc-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9fafc-314">**Consenti non corrispondente** e **non corrisponde** a un blocco:</span><span class="sxs-lookup"><span data-stu-id="9fafc-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9fafc-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-315">123contoso.com</span></span>
  - <span data-ttu-id="9fafc-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="9fafc-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="9fafc-317">Scenario: indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="9fafc-317">Scenario: IP address</span></span>

<span data-ttu-id="9fafc-318">**Voce**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="9fafc-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="9fafc-319">**Consenti** corrispondenza e **blocca corrispondenza**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9fafc-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="9fafc-320">**Consenti non corrispondente** e **non corrisponde** a un blocco:</span><span class="sxs-lookup"><span data-stu-id="9fafc-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9fafc-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="9fafc-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9fafc-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="9fafc-323">Indirizzo IP con carattere jolly destro</span><span class="sxs-lookup"><span data-stu-id="9fafc-323">IP address with right wildcard</span></span>

<span data-ttu-id="9fafc-324">**Voce**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="9fafc-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="9fafc-325">**Consenti** corrispondenza e **blocca corrispondenza**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9fafc-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="9fafc-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="9fafc-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="9fafc-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="9fafc-328">Esempi di voci non valide</span><span class="sxs-lookup"><span data-stu-id="9fafc-328">Examples of invalid entries</span></span>

<span data-ttu-id="9fafc-329">Le voci seguenti non sono valide:</span><span class="sxs-lookup"><span data-stu-id="9fafc-329">The following entries are invalid:</span></span>

- <span data-ttu-id="9fafc-330">**Valori di dominio mancanti o non validi**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="9fafc-331">contoso</span><span class="sxs-lookup"><span data-stu-id="9fafc-331">contoso</span></span>
  - <span data-ttu-id="9fafc-332">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="9fafc-333">\*. com</span><span class="sxs-lookup"><span data-stu-id="9fafc-333">\*.com</span></span>
  - <span data-ttu-id="9fafc-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="9fafc-334">\*.pdf</span></span>

- <span data-ttu-id="9fafc-335">**Carattere jolly su testo o senza caratteri di spaziatura**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="9fafc-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-336">\*contoso.com</span></span>
  - <span data-ttu-id="9fafc-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-337">contoso.com\*</span></span>
  - <span data-ttu-id="9fafc-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9fafc-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="9fafc-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="9fafc-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="9fafc-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="9fafc-342">**Indirizzi IP con porte**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="9fafc-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="9fafc-343">contoso.com:443</span></span>
  - <span data-ttu-id="9fafc-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="9fafc-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="9fafc-345">**Caratteri jolly non descrittivi**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="9fafc-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-346">\*.\*</span></span>

- <span data-ttu-id="9fafc-347">**Caratteri jolly intermedi**:</span><span class="sxs-lookup"><span data-stu-id="9fafc-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="9fafc-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="9fafc-348">conto\*so.com</span></span>
  - <span data-ttu-id="9fafc-349">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="9fafc-349">conto~so.com</span></span>

- <span data-ttu-id="9fafc-350">**Caratteri jolly doppi**</span><span class="sxs-lookup"><span data-stu-id="9fafc-350">**Double wildcards**</span></span>

  - <span data-ttu-id="9fafc-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="9fafc-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="9fafc-352">contoso.com/\*/\*</span></span>
