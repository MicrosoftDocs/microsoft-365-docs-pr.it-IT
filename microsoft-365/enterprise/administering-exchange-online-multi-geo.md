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
ms.openlocfilehash: 645d48066ca02dbf3480e20ae30dc187f84293cf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690949"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="125be-103">Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geografico</span><span class="sxs-lookup"><span data-stu-id="125be-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="125be-104">È richiesta la Sessione remota di PowerShell per visualizzare e configurare le proprietà multi-geografiche nell’ambiente di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="125be-104">Remote PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="125be-105">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="125be-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="125be-106">È necessario il [modulo di PowerShell di Microsoft Azure Active Directory](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 o versione successiva in V1. x per visualizzare la proprietà**PreferredDataLocation** sugli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="125be-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="125be-107">Gli oggetti utente sincronizzati con AAD Connect in AAD non possono contenere i valori **PreferredDataLocation** modificati direttamente tramite ADD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="125be-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="125be-108">Gli oggetti utente solo cloud possono essere modificati tramite AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="125be-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="125be-109">Per connettersi a PowerShell di Azure Active Directory, vedere [Connettersi a PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="125be-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="125be-110">È possibile connettersi direttamente a una posizione geografica con PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="125be-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="125be-111">In genere, PowerShell di Exchange Online si connetterà alla posizione geografica centrale.</span><span class="sxs-lookup"><span data-stu-id="125be-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="125be-112">Tuttavia, è anche possibile connettersi alla posizioni geografiche satellite.</span><span class="sxs-lookup"><span data-stu-id="125be-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="125be-113">Per una migliore prestazione, è consigliabile connettersi direttamente alla posizione geografica satellite quando si gestiscono solo gli utenti di tale specifica posizione.</span><span class="sxs-lookup"><span data-stu-id="125be-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="125be-114">Per connettersi a una posizione geografica specifica, il parametro *ConnectionUri* è diversa dalle ordinarie istruzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="125be-114">To connect to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="125be-115">Il resto dei comandi e i valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="125be-115">The rest of the commands and values are the same.</span></span> <span data-ttu-id="125be-116">Ecco come procedere:</span><span class="sxs-lookup"><span data-stu-id="125be-116">The steps are:</span></span>

1. <span data-ttu-id="125be-117">Nel computer locale, aprire Windows PowerShell ed eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="125be-117">On your local computer, open Windows PowerShell and run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="125be-118">Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell** digitare l'account e la password aziendale o dell'istituto di istruzione, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="125be-118">In the **Windows PowerShell Credential Request** dialog box, type your work or school account and password, and then click **OK**.</span></span>

2. <span data-ttu-id="125be-119">Sostituire `<emailaddress>` con l'indirizzo di posta elettronica di **eventuali** cassette postali nella specifica posizione geografica e eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="125be-119">Replace `<emailaddress>` with the email address of **any** mailbox in the target geo location and run the following command.</span></span> <span data-ttu-id="125be-120">Le autorizzazioni per la cassetta postale e la relazione con le credenziali nel passaggio 1 non sono un fattore; l'indirizzo di posta elettronica indica semplicemente a Exchange Online dove connettersi.</span><span class="sxs-lookup"><span data-stu-id="125be-120">Your permissions on the mailbox and the relationship to your credentials in Step 1 are not a factor; the email address simply tells Exchange Online where to connect.</span></span>
  
   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=<emailaddress> -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

   <span data-ttu-id="125be-121">Ad esempio, se olga@contoso.onmicrosoft.com è l'indirizzo di posta elettronica di una cassetta postale valida nella posizione geografica a cui si desidera connettersi, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="125be-121">For example, if olga@contoso.onmicrosoft.com is the email address of a valid mailbox in the geo location where you want to connect, run the following command:</span></span>

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

3. <span data-ttu-id="125be-122">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="125be-122">Run the following command:</span></span>

    ```powershell
    Import-PSSession $Session
    ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="125be-123">Visualizzare le posizioni geografiche disponibili configurate nella propria organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="125be-123">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="125be-124">Per visualizzare l'elenco di località geografiche configurate in Microsoft 365 Multi-Geo, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="125be-124">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="125be-125">Visualizzare la posizione geografica centrale per la propria organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="125be-125">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="125be-126">Per visualizzare la posizione geografica centrale del proprio tenant, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="125be-126">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="125be-127">Individuare la posizione geografica di una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="125be-127">Find the geo location of a mailbox</span></span>

<span data-ttu-id="125be-128">La cmdlet **Get-Mailbox** in PowerShell di Exchange Online mostra le seguenti proprietà multi-geografica relative alle cassette postali:</span><span class="sxs-lookup"><span data-stu-id="125be-128">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="125be-129">**Database**: le prime 3 lettere del nome del database corrispondono al codice geografico, che indica dove la cassetta postale è attualmente ubicata.</span><span class="sxs-lookup"><span data-stu-id="125be-129">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="125be-130">Per cassette postali di archiviazione Online, sarà necessario usare le proprietà di **ArchiveDatabase**.</span><span class="sxs-lookup"><span data-stu-id="125be-130">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="125be-131">**MailboxRegion**: specifica il codice posizione geografica impostato dall'amministratore (sincronizzato da **PreferredDataLocation** in Azure AD).</span><span class="sxs-lookup"><span data-stu-id="125be-131">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="125be-132">**MailboxRegionLastUpdateTime**: indica quando MailboxRegion è stato aggiornato l’ultima volta (automaticamente o manualmente).</span><span class="sxs-lookup"><span data-stu-id="125be-132">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="125be-133">Per visualizzare le proprietà di una cassetta postale, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="125be-133">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="125be-134">Ad esempio, per visualizzare le informazioni di posizione geografica della cassetta postale chris@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="125be-134">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="125be-135">L'output del comando avrà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="125be-135">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="125be-136">Se il codice della posizione geografica nel nome del database non corrisponde al valore di **MailboxRegion** , la cassetta postale viene automaticamente inserita in una coda di rilocazione e spostata nella posizione geografica specificata dal valore **MailboxRegion** (Exchange Online Cerca la mancata corrispondenza tra questi valori di proprietà).</span><span class="sxs-lookup"><span data-stu-id="125be-136">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="125be-137">Spostare una cassetta postale esistente solo nel cloud in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="125be-137">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="125be-138">Un utente solo cloud è un utente non sincronizzato con il tenant tramite AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="125be-138">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="125be-139">Tale utente è stato creato direttamente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="125be-139">This user was created directly in Azure AD.</span></span> <span data-ttu-id="125be-140">Usare il cmdlet**Get-MsolUser** e **Set-MsolUser** nel modulo di Azure Active Directory per Windows PowerShell per visualizzare o specificare la posizione geografica in cui verrà archiviata la cassetta postale dell'utente solo cloud.</span><span class="sxs-lookup"><span data-stu-id="125be-140">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="125be-141">Per visualizzare i valori **PreferredDataLocation** di un utente, utilizzare la sintassi in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="125be-141">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="125be-142">Ad esempio, per visualizzare i valori **PreferredDataLocation** dell’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="125be-142">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="125be-143">Per modificare il valore**PreferredDataLocation** per un utente solo cloud, utilizzare la sintassi seguente in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="125be-143">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="125be-144">Ad esempio, per impostare i valori **PreferredDataLocation** sulla geografica dell’Unione Europea per l’utente michelle@contoso.onmicrosoft.com, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="125be-144">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
> - <span data-ttu-id="125be-145">Come accennato in precedenza, non è possibile utilizzare questa procedura per gli oggetti utente sincronizzati da Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="125be-145">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="125be-146">È necessario modificare il valore **PreferredDataLocation** in Active Directory e sincronizzarlo con AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="125be-146">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="125be-147">Per ulteriori informazioni, vedere [Sincronizzazione di Azure Active Directory Connect: configurare il percorso di dati preferito per le risorse di Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="125be-147">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
> 
> - <span data-ttu-id="125be-148">Il tempo necessario per spostare una cassetta postale in una nuova posizione geografica dipende da diversi fattori:</span><span class="sxs-lookup"><span data-stu-id="125be-148">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
> 
>   - <span data-ttu-id="125be-149">Le dimensioni e tipo di cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="125be-149">The size and type of mailbox.</span></span>
> 
>   - <span data-ttu-id="125be-150">Il numero totale di cassette postali di cui eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="125be-150">The number of mailboxes being moved.</span></span>
> 
>   - <span data-ttu-id="125be-151">La disponibilità delle risorse di spostamento.</span><span class="sxs-lookup"><span data-stu-id="125be-151">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="125be-152">Disattivazione della migrazione per cassette postali in blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="125be-152">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="125be-153">Le cassette postali in blocco per controversia legale che vengono conservate per eDiscovery non possono essere spostate modificando i valori **PreferredDataLocation** dal loro stato di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="125be-153">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="125be-154">Per spostare una cassetta postale disabilitata in blocco per controversia legale:</span><span class="sxs-lookup"><span data-stu-id="125be-154">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="125be-155">Assegnare una licenza temporanea alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="125be-155">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="125be-156">Modificare il **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="125be-156">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="125be-157">Rimuovere la licenza dalla cassetta postale dopo che è stata spostata nella posizione geografica selezionata per ripristinare la disattivazione.</span><span class="sxs-lookup"><span data-stu-id="125be-157">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="125be-158">Creare nuove cassette postali nel cloud in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="125be-158">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="125be-159">Per creare una nuova cassetta postale in una posizione geografica specifica, è necessario procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="125be-159">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="125be-160">Configurare il valore **PreferredDataLocation** come descritto nella sezione precedente *prima che* venga creata la cassetta postale in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="125be-160">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="125be-161">Ad esempio, configurare il valore **PreferredDataLocation** per un utente prima di assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="125be-161">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="125be-162">Assegnare una licenza contemporaneamente all’impostazione del valore **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="125be-162">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="125be-163">Per creare un nuovo utente solo cloud con licenza (non sincronizzato con AAD Connect) in un determinata posizione geografica, usare la sintassi seguente in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="125be-163">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="125be-164">In questo esempio crea un nuovo account utente per Elizabeth Brunner con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="125be-164">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="125be-165">Nome dell'entità utente: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="125be-165">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>

- <span data-ttu-id="125be-166">Nome: entrambe</span><span class="sxs-lookup"><span data-stu-id="125be-166">First name: Elizabeth</span></span>

- <span data-ttu-id="125be-167">Cognome: Brunner</span><span class="sxs-lookup"><span data-stu-id="125be-167">Last name: Brunner</span></span>

- <span data-ttu-id="125be-168">Nome visualizzato: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="125be-168">Display name: Elizabeth Brunner</span></span>

- <span data-ttu-id="125be-169">Password: generata casualmente e visualizzata nei risultati del comando (in quanto non vengono usati i parametri della *Password*)</span><span class="sxs-lookup"><span data-stu-id="125be-169">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>

- <span data-ttu-id="125be-170">Licenza: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="125be-170">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>

- <span data-ttu-id="125be-171">Posizione: Australia (AUS)</span><span class="sxs-lookup"><span data-stu-id="125be-171">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="125be-172">Per ulteriori informazioni sulla creazione di nuovi account utente e la ricerca di valori di LicenseAssignment in Azure AD PowerShell, vedere [Creare account utente con PowerShell](create-user-accounts-with-microsoft-365-powershell.md) e [Visualizzare le licenze e i servizi con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="125be-172">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="125be-173">Se si sta utilizzando PowerShell di Exchange Online per abilitare una cassetta postale si desidera che questa sia creata direttamente nella posizione geografica specificata in **PreferredDataLocation**, è necessario utilizzare un cmdlet di Exchange Online come **Enable-Mailbox** o **New-Mailbox** direttamente con il servizio di cloud.</span><span class="sxs-lookup"><span data-stu-id="125be-173">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="125be-174">Se si usa il cmdlet di Exchange PowerShell locale**Enable-RemoteMailbox**, la cassetta postale verrà creata nella posizione geografica centrale.</span><span class="sxs-lookup"><span data-stu-id="125be-174">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="125be-175">Effettuare l’integrazione di cassette postali locali esistenti in una posizione geografica specifica</span><span class="sxs-lookup"><span data-stu-id="125be-175">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="125be-176">È possibile usare i processi e gli strumenti standard di integrazione per eseguire la migrazione di una cassetta postale di un'organizzazione di Exchange locale a Exchange Online, tra cui la [Dashboard di migrazione nell'interfaccia](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)e il cmdlet [New-MigrationBatch ](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="125be-176">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="125be-177">Il primo passaggio consiste nel verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e verificare che sia configurato il corretto valore della **PreferredDataLocation** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="125be-177">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="125be-178">Gli strumenti di integrazione rispetteranno il valore **PreferredDataLocation** e verrà eseguita la migrazione delle cassette postali direttamente alla posizione geografica specificata.</span><span class="sxs-lookup"><span data-stu-id="125be-178">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="125be-179">Oppure, la procedura seguente consente di aggiungere cassette postali direttamente a una posizione geografica specifica tramite il cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="125be-179">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="125be-180">Verificare che esista un oggetto utente per ogni cassetta postale su cui effettuare l’integrazione e che la **PreferredDataLocation** sia impostata sul valore desiderato in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="125be-180">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="125be-181">Il valore di **PreferredDataLocation** sarà sincronizzato con l’attributo di**MailboxRegion** del corrispondente oggetto utente di posta in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="125be-181">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="125be-182">Connettersi direttamente a specifici posizioni geografiche satellite seguendo le istruzioni di connessione dei passaggi precedenti di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="125be-182">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="125be-183">Nella finestra di PowerShell di Exchange Online, archiviare le credenziali di amministratore locale usate per eseguire la migrazione delle cassette postali in una variabile, eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="125be-183">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="125be-184">Su PowerShell di Exchange Online, creare una nuova **New-MoveRequest** simile all’esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="125be-184">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="125be-185">Ripetere il passaggio #4 per ogni cassetta postale di cui è necessario eseguire la migrazione dall’Exchange locale alla posizione satellite con cui si è attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="125be-185">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="125be-186">Se è necessario eseguire la migrazione di altre cassette postali a diverse posizioni geografiche satellite, ripetere i passaggi da 2 a 4 per ogni località satellite specifica.</span><span class="sxs-lookup"><span data-stu-id="125be-186">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="125be-187">Creazione di report multi-geografici</span><span class="sxs-lookup"><span data-stu-id="125be-187">Multi-geo reporting</span></span>

<span data-ttu-id="125be-188">**I report sull'utilizzo di Multi-Geo** nell’interfaccia di amministrazione di Microsoft 365 mostrano il numero di utenti in base alla località geografica.</span><span class="sxs-lookup"><span data-stu-id="125be-188">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="125be-189">Il report mostra la distribuzione degli utenti per il mese corrente e fornisce i dati cronologici dagli ultimi 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="125be-189">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="125be-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="125be-190">See also</span></span>

[<span data-ttu-id="125be-191">Gestione di Microsoft 365 ed Exchange Online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="125be-191">Managing Microsoft 365 and Exchange Online with Windows PowerShell</span></span>](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
