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
ms.openlocfilehash: ea7090cd65634138f9677960beab7770825a6e86
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950677"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="80966-103">Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geografico</span><span class="sxs-lookup"><span data-stu-id="80966-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="80966-104">Exchange Online PowerShell è necessario per visualizzare e configurare le proprietà multi Geo nell'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80966-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="80966-105">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="80966-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="80966-106">È necessario il [modulo di PowerShell di Microsoft Azure Active Directory](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 o versione successiva in V1. x per visualizzare la proprietà**PreferredDataLocation** sugli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="80966-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="80966-107">Gli oggetti utente sincronizzati con AAD Connect in AAD non possono contenere i valori **PreferredDataLocation** modificati direttamente tramite ADD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80966-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="80966-108">Gli oggetti utente solo cloud possono essere modificati tramite AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80966-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="80966-109">Per connettersi a PowerShell di Azure Active Directory, vedere [Connettersi a PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="80966-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="80966-110">È possibile connettersi direttamente a una posizione geografica con PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80966-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="80966-111">In genere, PowerShell di Exchange Online si connetterà alla posizione geografica centrale.</span><span class="sxs-lookup"><span data-stu-id="80966-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="80966-112">Tuttavia, è anche possibile connettersi alla posizioni geografiche satellite.</span><span class="sxs-lookup"><span data-stu-id="80966-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="80966-113">Per una migliore prestazione, è consigliabile connettersi direttamente alla posizione geografica satellite quando si gestiscono solo gli utenti di tale specifica posizione.</span><span class="sxs-lookup"><span data-stu-id="80966-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="80966-114">I requisiti per l'installazione e l'uso del modulo EXO V2 sono descritti in [Installazione e gestione del modulo V2 EXO](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="80966-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="80966-115">Per connettere Exchange Online PowerShell a una specifica posizione geografica, il parametro *ConnectionURI* è diverso rispetto alle normali istruzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="80966-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="80966-116">Il resto dei comandi e i valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="80966-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="80966-117">In particolare, è necessario aggiungere il `?email=<emailaddress>` valore alla fine del valore _ConnectionURI_ .</span><span class="sxs-lookup"><span data-stu-id="80966-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="80966-118">`<emailaddress>` è l'indirizzo di posta elettronica di **qualsiasi** cassetta postale nella posizione geografica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="80966-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="80966-119">Le autorizzazioni per la cassetta postale o la relazione con le credenziali non sono un fattore. l'indirizzo di posta elettronica indica semplicemente a Exchange Online PowerShell dove effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="80966-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="80966-120">I clienti Microsoft 365 o Microsoft 365 GCC in genere non è necessario utilizzare il parametro _ConnectionURI_ per connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80966-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="80966-121">Tuttavia, per connettersi a una specifica posizione geografica, è necessario utilizzare il parametro _ConnectionURI_ in modo che sia possibile utilizzare `?email=<emailaddress>` il valore.</span><span class="sxs-lookup"><span data-stu-id="80966-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="80966-122">Connettersi a una posizione geografica in PowerShell di Exchange Online utilizzando l'autenticazione a più fattori (AMF)</span><span class="sxs-lookup"><span data-stu-id="80966-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="80966-123">In una finestra di Windows PowerShell caricare il modulo EXO V2 eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="80966-124">Nell'esempio seguente, admin@contoso.onmicrosoft.com è l'account di amministratore e la posizione geografica di destinazione è il luogo in cui risiede la cassetta postale olga@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="80966-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="80966-125">Connettersi a una posizione geografica in Exchange Online PowerShell senza l'utilizzo dell'AMF</span><span class="sxs-lookup"><span data-stu-id="80966-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="80966-126">In una finestra di Windows PowerShell caricare il modulo EXO V2 eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="80966-127">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="80966-128">Nella finestra di dialogo che viene visualizzata **Richiesta credenziali di Windows PowerShell** digitare l'account e la password aziendale o dell'istituto di istruzione, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="80966-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="80966-129">Nell'esempio seguente, la posizione geografica di destinazione è quella in cui risiede la cassetta postale olga@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="80966-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="80966-130">Visualizzare le posizioni geografiche disponibili configurate nella propria organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80966-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="80966-131">Per visualizzare l'elenco di località geografiche configurate in Microsoft 365 Multi-Geo, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="80966-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="80966-132">Visualizzare la posizione geografica centrale per la propria organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80966-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="80966-133">Per visualizzare la posizione geografica centrale del proprio tenant, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="80966-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="80966-134">Individuare la posizione geografica di una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="80966-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="80966-135">La cmdlet **Get-Mailbox** in PowerShell di Exchange Online mostra le seguenti proprietà multi-geografica relative alle cassette postali:</span><span class="sxs-lookup"><span data-stu-id="80966-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="80966-136">**Database**: le prime 3 lettere del nome del database corrispondono al codice geografico, che indica dove la cassetta postale è attualmente ubicata.</span><span class="sxs-lookup"><span data-stu-id="80966-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="80966-137">Per cassette postali di archiviazione Online, sarà necessario usare le proprietà di **ArchiveDatabase**.</span><span class="sxs-lookup"><span data-stu-id="80966-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="80966-138">**MailboxRegion**: specifica il codice posizione geografica impostato dall'amministratore (sincronizzato da **PreferredDataLocation** in Azure AD).</span><span class="sxs-lookup"><span data-stu-id="80966-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="80966-139">**MailboxRegionLastUpdateTime**: indica quando MailboxRegion è stato aggiornato l’ultima volta (automaticamente o manualmente).</span><span class="sxs-lookup"><span data-stu-id="80966-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="80966-140">Per visualizzare le proprietà di una cassetta postale, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="80966-141">Ad esempio, per visualizzare le informazioni di posizione geografica della cassetta postale chris@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="80966-142">L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="80966-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="80966-143">Se il codice della posizione geografica nel nome del database non corrisponde al valore di **MailboxRegion** , la cassetta postale viene automaticamente inserita in una coda di rilocazione e spostata nella posizione geografica specificata dal valore **MailboxRegion** (Exchange Online Cerca la mancata corrispondenza tra questi valori di proprietà).</span><span class="sxs-lookup"><span data-stu-id="80966-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="80966-144">Spostare una cassetta postale esistente solo nel cloud in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="80966-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="80966-145">Un utente solo cloud è un utente non sincronizzato con il tenant tramite AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="80966-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="80966-146">Tale utente è stato creato direttamente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80966-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="80966-147">Usare il cmdlet**Get-MsolUser** e **Set-MsolUser** nel modulo di Azure Active Directory per Windows PowerShell per visualizzare o specificare la posizione geografica in cui verrà archiviata la cassetta postale dell'utente solo cloud.</span><span class="sxs-lookup"><span data-stu-id="80966-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="80966-148">Per visualizzare i valori **PreferredDataLocation** di un utente, utilizzare la sintassi in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="80966-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="80966-149">Ad esempio, per visualizzare i valori **PreferredDataLocation** dell’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="80966-150">Per modificare il valore**PreferredDataLocation** per un utente solo cloud, utilizzare la sintassi seguente in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="80966-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="80966-151">Ad esempio, per impostare i valori **PreferredDataLocation** sulla geografica dell’Unione Europea per l’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="80966-152">Come accennato in precedenza, non è possibile utilizzare questa procedura per gli oggetti utente sincronizzati da Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="80966-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="80966-153">È necessario modificare il valore **PreferredDataLocation** in Active Directory e sincronizzarlo con AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="80966-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="80966-154">Per ulteriori informazioni, vedere [Sincronizzazione di Azure Active Directory Connect: configurare il percorso di dati preferito per le risorse di Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="80966-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="80966-155">Il tempo necessario per spostare una cassetta postale in una nuova posizione geografica dipende da diversi fattori:</span><span class="sxs-lookup"><span data-stu-id="80966-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="80966-156">Le dimensioni e tipo di cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="80966-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="80966-157">Il numero totale di cassette postali di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="80966-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="80966-158">La disponibilità delle risorse di spostamento.</span><span class="sxs-lookup"><span data-stu-id="80966-158">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="80966-159">Disattivazione della migrazione per cassette postali in blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="80966-159">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="80966-160">Le cassette postali in blocco per controversia legale che vengono conservate per eDiscovery non possono essere spostate modificando i valori **PreferredDataLocation** dal loro stato di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="80966-160">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="80966-161">Per spostare una cassetta postale disabilitata in blocco per controversia legale:</span><span class="sxs-lookup"><span data-stu-id="80966-161">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="80966-162">Assegnare una licenza temporanea alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="80966-162">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="80966-163">Modificare il **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="80966-163">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="80966-164">Rimuovere la licenza dalla cassetta postale dopo che è stata spostata nella posizione geografica selezionata per ripristinare la disattivazione.</span><span class="sxs-lookup"><span data-stu-id="80966-164">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="80966-165">Creare nuove cassette postali nel cloud in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="80966-165">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="80966-166">Per creare una nuova cassetta postale in una posizione geografica specifica, è necessario procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="80966-166">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="80966-167">Configurare il valore **PreferredDataLocation** come descritto nella sezione precedente *prima che* venga creata la cassetta postale in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80966-167">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="80966-168">Ad esempio, configurare il valore **PreferredDataLocation** per un utente prima di assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="80966-168">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="80966-169">Assegnare una licenza contemporaneamente all’impostazione del valore **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="80966-169">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="80966-170">Per creare un nuovo utente solo cloud con licenza (non sincronizzato con AAD Connect) in un determinata posizione geografica, usare la sintassi seguente in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="80966-170">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="80966-171">In questo esempio crea un nuovo account utente per Elizabeth Brunner con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="80966-171">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="80966-172">Nome dell'entità utente: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="80966-172">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="80966-173">Nome: entrambe</span><span class="sxs-lookup"><span data-stu-id="80966-173">First name: Elizabeth</span></span>
- <span data-ttu-id="80966-174">Cognome: Brunner</span><span class="sxs-lookup"><span data-stu-id="80966-174">Last name: Brunner</span></span>
- <span data-ttu-id="80966-175">Nome visualizzato: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="80966-175">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="80966-176">Password: generata casualmente e visualizzata nei risultati del comando (in quanto non vengono usati i parametri della *Password*)</span><span class="sxs-lookup"><span data-stu-id="80966-176">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="80966-177">Licenza: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="80966-177">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="80966-178">Posizione: Australia (AUS)</span><span class="sxs-lookup"><span data-stu-id="80966-178">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="80966-179">Per ulteriori informazioni sulla creazione di nuovi account utente e la ricerca di valori di LicenseAssignment in Azure AD PowerShell, vedere [Creare account utente con PowerShell](create-user-accounts-with-microsoft-365-powershell.md) e [Visualizzare le licenze e i servizi con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="80966-179">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="80966-180">Se si sta utilizzando PowerShell di Exchange Online per abilitare una cassetta postale si desidera che questa sia creata direttamente nella posizione geografica specificata in **PreferredDataLocation**, è necessario utilizzare un cmdlet di Exchange Online come **Enable-Mailbox** o **New-Mailbox** direttamente con il servizio di cloud.</span><span class="sxs-lookup"><span data-stu-id="80966-180">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="80966-181">Se si usa il cmdlet di Exchange PowerShell locale**Enable-RemoteMailbox**, la cassetta postale verrà creata nella posizione geografica centrale.</span><span class="sxs-lookup"><span data-stu-id="80966-181">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="80966-182">Effettuare l’integrazione di cassette postali locali esistenti in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="80966-182">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="80966-183">È possibile usare i processi e gli strumenti standard di integrazione per eseguire la migrazione di una cassetta postale di un'organizzazione di Exchange locale a Exchange Online, tra cui la [Dashboard di migrazione nell'interfaccia](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)e il cmdlet [New-MigrationBatch ](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80966-183">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="80966-184">Il primo passaggio consiste nel verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e verificare che sia configurato il corretto valore della **PreferredDataLocation** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80966-184">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="80966-185">Gli strumenti di integrazione rispetteranno il valore **PreferredDataLocation** e verrà eseguita la migrazione delle cassette postali direttamente alla posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="80966-185">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="80966-186">Oppure, la procedura seguente consente di aggiungere cassette postali direttamente a una posizione geografica specifica tramite il cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80966-186">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="80966-187">Verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e che la **PreferredDataLocation** sia impostata sul valore desiderato in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80966-187">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="80966-188">Il valore di **PreferredDataLocation** sarà sincronizzato con l’attributo di**MailboxRegion** del corrispondente oggetto utente di posta in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80966-188">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="80966-189">Connettersi direttamente a specifici posizioni geografiche satellite seguendo le istruzioni di connessione dei passaggi precedenti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="80966-189">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="80966-190">Nella finestra di PowerShell di Exchange Online, archiviare le credenziali di amministratore locale usate per eseguire la migrazione delle cassette postali in una variabile, eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-190">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="80966-191">Su PowerShell di Exchange Online, creare una nuova **New-MoveRequest** simile all’esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="80966-191">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="80966-192">Ripetere il passaggio #4 per ogni cassetta postale di cui è necessario eseguire la migrazione dall’Exchange locale alla posizione satellite con cui si è attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="80966-192">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="80966-193">Se è necessario eseguire la migrazione di altre cassette postali a diverse posizioni geografiche satellite, ripetere i passaggi da 2 a 4 per ogni località satellite specifica.</span><span class="sxs-lookup"><span data-stu-id="80966-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="80966-194">Creazione di report multi-geografici</span><span class="sxs-lookup"><span data-stu-id="80966-194">Multi-geo reporting</span></span>

<span data-ttu-id="80966-195">**I report sull'utilizzo di Multi-Geo** nell’interfaccia di amministrazione di Microsoft 365 mostrano il numero di utenti in base alla località geografica.</span><span class="sxs-lookup"><span data-stu-id="80966-195">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="80966-196">Il report mostra la distribuzione degli utenti per il mese corrente e fornisce i dati cronologici dagli ultimi 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="80966-196">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="80966-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80966-197">See also</span></span>

[<span data-ttu-id="80966-198">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="80966-198">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
