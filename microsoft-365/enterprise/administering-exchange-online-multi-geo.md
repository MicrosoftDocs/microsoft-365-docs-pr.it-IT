---
title: Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geografico
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Informazioni su come amministrare le impostazioni di Exchange Online Multi-Geo nell'ambiente Microsoft 365 con PowerShell.
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552008"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="08a0c-103">Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geografico</span><span class="sxs-lookup"><span data-stu-id="08a0c-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="08a0c-104">Exchange Online PowerShell è necessario per visualizzare e configurare le proprietà multi Geo nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08a0c-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="08a0c-105">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="08a0c-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="08a0c-106">È necessario il [modulo di PowerShell di Microsoft Azure Active Directory](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 o versione successiva in V1. x per visualizzare la proprietà **PreferredDataLocation** sugli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="08a0c-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="08a0c-107">Gli oggetti utente sincronizzati con AAD Connect in AAD non possono contenere i valori **PreferredDataLocation** modificati direttamente tramite ADD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08a0c-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="08a0c-108">Gli oggetti utente solo cloud possono essere modificati tramite AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08a0c-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="08a0c-109">Per connettersi a PowerShell di Azure Active Directory, vedere [Connettersi a PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="08a0c-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="08a0c-110">È possibile connettersi direttamente a una posizione geografica con PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="08a0c-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="08a0c-111">In genere, PowerShell di Exchange Online si connetterà alla posizione geografica centrale.</span><span class="sxs-lookup"><span data-stu-id="08a0c-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="08a0c-112">Tuttavia, è anche possibile connettersi alla posizioni geografiche satellite.</span><span class="sxs-lookup"><span data-stu-id="08a0c-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="08a0c-113">Per una migliore prestazione, è consigliabile connettersi direttamente alla posizione geografica satellite quando si gestiscono solo gli utenti di tale specifica posizione.</span><span class="sxs-lookup"><span data-stu-id="08a0c-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="08a0c-114">I requisiti per l'installazione e l'uso del modulo EXO V2 sono descritti in [Installazione e gestione del modulo V2 EXO](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="08a0c-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="08a0c-115">Per connettere Exchange Online PowerShell a una specifica posizione geografica, il parametro *ConnectionURI* è diverso rispetto alle normali istruzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="08a0c-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="08a0c-116">Il resto dei comandi e i valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="08a0c-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="08a0c-117">In particolare, è necessario aggiungere il `?email=<emailaddress>` valore alla fine del valore _ConnectionURI_ .</span><span class="sxs-lookup"><span data-stu-id="08a0c-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="08a0c-118">`<emailaddress>` è l'indirizzo di posta elettronica di **qualsiasi** cassetta postale nella posizione geografica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="08a0c-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="08a0c-119">Le autorizzazioni per la cassetta postale o la relazione con le credenziali non sono un fattore. l'indirizzo di posta elettronica indica semplicemente a Exchange Online PowerShell dove effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="08a0c-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="08a0c-120">I clienti Microsoft 365 o Microsoft 365 GCC in genere non è necessario utilizzare il parametro _ConnectionURI_ per connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="08a0c-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="08a0c-121">Tuttavia, per connettersi a una specifica posizione geografica, è necessario utilizzare il parametro _ConnectionURI_ in modo che sia possibile utilizzare `?email=<emailaddress>` il valore.</span><span class="sxs-lookup"><span data-stu-id="08a0c-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="08a0c-122">Connettersi a una posizione geografica in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="08a0c-122">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="08a0c-123">Le seguenti istruzioni di connessione funzionano per gli account che sono o non sono configurati per l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="08a0c-123">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="08a0c-124">In una finestra di Windows PowerShell caricare il modulo EXO V2 eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="08a0c-124">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="08a0c-125">Nell'esempio seguente, admin@contoso.onmicrosoft.com è l'account di amministratore e la posizione geografica di destinazione è il luogo in cui risiede la cassetta postale olga@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="08a0c-125">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="08a0c-126">Immettere la password per il admin@contoso.onmicrosoft.com nel prompt visualizzato.</span><span class="sxs-lookup"><span data-stu-id="08a0c-126">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="08a0c-127">Se l'account è configurato per l'AMF, è necessario immettere anche il codice di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="08a0c-127">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="08a0c-128">Visualizzare le posizioni geografiche disponibili configurate nella propria organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08a0c-128">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="08a0c-129">Per visualizzare l'elenco di località geografiche configurate in Microsoft 365 Multi-Geo, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="08a0c-129">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="08a0c-130">Visualizzare la posizione geografica centrale per la propria organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08a0c-130">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="08a0c-131">Per visualizzare la posizione geografica centrale del proprio tenant, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="08a0c-131">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="08a0c-132">Individuare la posizione geografica di una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="08a0c-132">Find the geo location of a mailbox</span></span>

<span data-ttu-id="08a0c-133">La cmdlet **Get-Mailbox** in PowerShell di Exchange Online mostra le seguenti proprietà multi-geografica relative alle cassette postali:</span><span class="sxs-lookup"><span data-stu-id="08a0c-133">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="08a0c-134">**Database**: le prime 3 lettere del nome del database corrispondono al codice geografico, che indica dove la cassetta postale è attualmente ubicata.</span><span class="sxs-lookup"><span data-stu-id="08a0c-134">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="08a0c-135">Per cassette postali di archiviazione Online, sarà necessario usare le proprietà di **ArchiveDatabase**.</span><span class="sxs-lookup"><span data-stu-id="08a0c-135">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="08a0c-136">**MailboxRegion**: specifica il codice posizione geografica impostato dall'amministratore (sincronizzato da **PreferredDataLocation** in Azure AD).</span><span class="sxs-lookup"><span data-stu-id="08a0c-136">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="08a0c-137">**MailboxRegionLastUpdateTime**: indica quando MailboxRegion è stato aggiornato l’ultima volta (automaticamente o manualmente).</span><span class="sxs-lookup"><span data-stu-id="08a0c-137">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="08a0c-138">Per visualizzare le proprietà di una cassetta postale, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="08a0c-138">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="08a0c-139">Ad esempio, per visualizzare le informazioni di posizione geografica della cassetta postale chris@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="08a0c-139">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="08a0c-140">L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="08a0c-140">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="08a0c-141">Se il codice della posizione geografica nel nome del database non corrisponde al valore di **MailboxRegion** , la cassetta postale viene automaticamente inserita in una coda di rilocazione e spostata nella posizione geografica specificata dal valore **MailboxRegion** (Exchange Online Cerca la mancata corrispondenza tra questi valori di proprietà).</span><span class="sxs-lookup"><span data-stu-id="08a0c-141">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="08a0c-142">Spostare una cassetta postale esistente solo nel cloud in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="08a0c-142">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="08a0c-143">Un utente solo cloud è un utente non sincronizzato con il tenant tramite AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="08a0c-143">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="08a0c-144">Tale utente è stato creato direttamente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="08a0c-144">This user was created directly in Azure AD.</span></span> <span data-ttu-id="08a0c-145">Usare il cmdlet **Get-MsolUser** e **Set-MsolUser** nel modulo di Azure Active Directory per Windows PowerShell per visualizzare o specificare la posizione geografica in cui verrà archiviata la cassetta postale dell'utente solo cloud.</span><span class="sxs-lookup"><span data-stu-id="08a0c-145">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="08a0c-146">Per visualizzare i valori **PreferredDataLocation** di un utente, utilizzare la sintassi in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="08a0c-146">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="08a0c-147">Ad esempio, per visualizzare i valori **PreferredDataLocation** dell’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="08a0c-147">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="08a0c-148">Per modificare il valore **PreferredDataLocation** per un utente solo cloud, utilizzare la sintassi seguente in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="08a0c-148">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="08a0c-149">Ad esempio, per impostare i valori **PreferredDataLocation** sulla geografica dell’Unione Europea per l’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="08a0c-149">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="08a0c-150">Come accennato in precedenza, non è possibile utilizzare questa procedura per gli oggetti utente sincronizzati da Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="08a0c-150">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="08a0c-151">È necessario modificare il valore **PreferredDataLocation** in Active Directory e sincronizzarlo con AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="08a0c-151">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="08a0c-152">Per ulteriori informazioni, vedere [Sincronizzazione di Azure Active Directory Connect: configurare il percorso di dati preferito per le risorse di Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="08a0c-152">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="08a0c-153">Il tempo necessario per spostare una cassetta postale in una nuova posizione geografica dipende da diversi fattori:</span><span class="sxs-lookup"><span data-stu-id="08a0c-153">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="08a0c-154">Le dimensioni e tipo di cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="08a0c-154">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="08a0c-155">Il numero totale di cassette postali di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="08a0c-155">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="08a0c-156">La disponibilità delle risorse di spostamento.</span><span class="sxs-lookup"><span data-stu-id="08a0c-156">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="08a0c-157">Spostare una cassetta postale inattiva in una specifica Geo</span><span class="sxs-lookup"><span data-stu-id="08a0c-157">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="08a0c-158">Non è possibile spostare le cassette postali inattive conservate ai fini della conformità, ad esempio le cassette postali in blocco per controversia legale, modificando il relativo valore **PreferredDataLocation** .</span><span class="sxs-lookup"><span data-stu-id="08a0c-158">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="08a0c-159">Per spostare una cassetta postale inattiva in un altro geografico, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="08a0c-159">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="08a0c-160">Recuperare la cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="08a0c-160">Recover the inactive mailbox.</span></span> <span data-ttu-id="08a0c-161">Per istruzioni, vedere [recuperare una cassetta postale inattiva](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="08a0c-161">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="08a0c-162">Evitare che l'Assistente cartelle gestite esegua l'elaborazione della cassetta postale recuperata sostituendo \<MailboxIdentity\> con il nome, l'alias, l'account o l'indirizzo di posta elettronica della cassetta postale ed eseguendo il comando seguente in [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="08a0c-162">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="08a0c-163">Assegnare una licenza di **Exchange Online piano 2** alla cassetta postale recuperata.</span><span class="sxs-lookup"><span data-stu-id="08a0c-163">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="08a0c-164">Questo passaggio è necessario per riportare la cassetta postale sul blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="08a0c-164">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="08a0c-165">Per istruzioni, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="08a0c-165">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="08a0c-166">Configurare il valore **PreferredDataLocation** nella cassetta postale come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="08a0c-166">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="08a0c-167">Dopo aver confermato che la cassetta postale è stata spostata nella nuova posizione geografica, riposizionare la cassetta postale recuperata sul blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="08a0c-167">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="08a0c-168">Per istruzioni, vedere [inserire una cassetta postale per il blocco per controversia legale](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="08a0c-168">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="08a0c-169">Dopo aver verificato che il blocco per controversia legale sia sul posto, consentire all'Assistente cartelle gestite di elaborare nuovamente la cassetta postale sostituendo \<MailboxIdentity\> con il nome, l'alias, l'account o l'indirizzo di posta elettronica della cassetta postale ed eseguendo il comando seguente in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="08a0c-169">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="08a0c-170">Rendere la cassetta postale inattiva di nuovo rimuovendo l'account utente associato alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="08a0c-170">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="08a0c-171">Per istruzioni, vedere [eliminare un utente dall'organizzazione](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span><span class="sxs-lookup"><span data-stu-id="08a0c-171">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="08a0c-172">Questo passaggio rilascia anche la licenza di Exchange Online piano 2 per altri usi.</span><span class="sxs-lookup"><span data-stu-id="08a0c-172">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="08a0c-173">**Nota**: quando si sposta una cassetta postale inattiva in un'altra posizione geografica, si potrebbe influire sui risultati della ricerca del contenuto o sulla possibilità di eseguire ricerche nella cassetta postale dall'ex posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="08a0c-173">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="08a0c-174">Per ulteriori informazioni, vedere [ricerca ed esportazione di contenuto in ambienti multi-Geo](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span><span class="sxs-lookup"><span data-stu-id="08a0c-174">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="08a0c-175">Creare nuove cassette postali nel cloud in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="08a0c-175">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="08a0c-176">Per creare una nuova cassetta postale in una posizione geografica specifica, è necessario procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="08a0c-176">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="08a0c-177">Configurare il valore **PreferredDataLocation** come descritto nello spostamento precedente [di una cassetta postale di solo cloud esistente in una](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) sezione geografica specifica *prima* di creare la cassetta postale in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="08a0c-177">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="08a0c-178">Ad esempio, configurare il valore **PreferredDataLocation** su un utente prima di assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="08a0c-178">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="08a0c-179">Assegnare una licenza contemporaneamente all’impostazione del valore **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="08a0c-179">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="08a0c-180">Per creare un nuovo utente solo cloud con licenza (non sincronizzato con AAD Connect) in un determinata posizione geografica, usare la sintassi seguente in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="08a0c-180">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="08a0c-181">In questo esempio crea un nuovo account utente per Elizabeth Brunner con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="08a0c-181">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="08a0c-182">Nome dell'entità utente: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="08a0c-182">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="08a0c-183">Nome: entrambe</span><span class="sxs-lookup"><span data-stu-id="08a0c-183">First name: Elizabeth</span></span>
- <span data-ttu-id="08a0c-184">Cognome: Brunner</span><span class="sxs-lookup"><span data-stu-id="08a0c-184">Last name: Brunner</span></span>
- <span data-ttu-id="08a0c-185">Nome visualizzato: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="08a0c-185">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="08a0c-186">Password: generata casualmente e visualizzata nei risultati del comando (in quanto non vengono usati i parametri della *Password*)</span><span class="sxs-lookup"><span data-stu-id="08a0c-186">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="08a0c-187">Licenza: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="08a0c-187">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="08a0c-188">Posizione: Australia (AUS)</span><span class="sxs-lookup"><span data-stu-id="08a0c-188">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="08a0c-189">Per ulteriori informazioni sulla creazione di nuovi account utente e la ricerca di valori di LicenseAssignment in Azure AD PowerShell, vedere [Creare account utente con PowerShell](create-user-accounts-with-microsoft-365-powershell.md) e [Visualizzare le licenze e i servizi con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="08a0c-189">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="08a0c-190">Se si sta utilizzando PowerShell di Exchange Online per abilitare una cassetta postale si desidera che questa sia creata direttamente nella posizione geografica specificata in **PreferredDataLocation**, è necessario utilizzare un cmdlet di Exchange Online come **Enable-Mailbox** o **New-Mailbox** direttamente con il servizio di cloud.</span><span class="sxs-lookup"><span data-stu-id="08a0c-190">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="08a0c-191">Se si usa il cmdlet di Exchange PowerShell locale **Enable-RemoteMailbox**, la cassetta postale verrà creata nella posizione geografica centrale.</span><span class="sxs-lookup"><span data-stu-id="08a0c-191">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="08a0c-192">Effettuare l’integrazione di cassette postali locali esistenti in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="08a0c-192">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="08a0c-193">È possibile usare i processi e gli strumenti standard di integrazione per eseguire la migrazione di una cassetta postale di un'organizzazione di Exchange locale a Exchange Online, tra cui la [Dashboard di migrazione nell'interfaccia](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)e il cmdlet [New-MigrationBatch ](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="08a0c-193">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="08a0c-194">Il primo passaggio consiste nel verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e verificare che sia configurato il corretto valore della **PreferredDataLocation** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="08a0c-194">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="08a0c-195">Gli strumenti di integrazione rispetteranno il valore **PreferredDataLocation** e verrà eseguita la migrazione delle cassette postali direttamente alla posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="08a0c-195">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="08a0c-196">Oppure, la procedura seguente consente di aggiungere cassette postali direttamente a una posizione geografica specifica tramite il cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="08a0c-196">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="08a0c-197">Verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e che la **PreferredDataLocation** sia impostata sul valore desiderato in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="08a0c-197">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="08a0c-198">Il valore di **PreferredDataLocation** sarà sincronizzato con l’attributo di **MailboxRegion** del corrispondente oggetto utente di posta in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="08a0c-198">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="08a0c-199">Connettersi direttamente a specifici posizioni geografiche satellite seguendo le istruzioni di connessione dei passaggi precedenti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="08a0c-199">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="08a0c-200">Nella finestra di PowerShell di Exchange Online, archiviare le credenziali di amministratore locale usate per eseguire la migrazione delle cassette postali in una variabile, eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="08a0c-200">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="08a0c-201">Su PowerShell di Exchange Online, creare una nuova **New-MoveRequest** simile all’esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="08a0c-201">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="08a0c-202">Ripetere il passaggio #4 per ogni cassetta postale di cui è necessario eseguire la migrazione dall’Exchange locale alla posizione satellite con cui si è attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="08a0c-202">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="08a0c-203">Se è necessario eseguire la migrazione di altre cassette postali a diverse posizioni geografiche satellite, ripetere i passaggi da 2 a 4 per ogni località satellite specifica.</span><span class="sxs-lookup"><span data-stu-id="08a0c-203">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="08a0c-204">Creazione di report multi-geografici</span><span class="sxs-lookup"><span data-stu-id="08a0c-204">Multi-geo reporting</span></span>

<span data-ttu-id="08a0c-205">**I report sull'utilizzo di Multi-Geo** nell’interfaccia di amministrazione di Microsoft 365 mostrano il numero di utenti in base alla località geografica.</span><span class="sxs-lookup"><span data-stu-id="08a0c-205">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="08a0c-206">Il report mostra la distribuzione degli utenti per il mese corrente e fornisce i dati cronologici dagli ultimi 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="08a0c-206">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="08a0c-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08a0c-207">See also</span></span>

[<span data-ttu-id="08a0c-208">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="08a0c-208">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
