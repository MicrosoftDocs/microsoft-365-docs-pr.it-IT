---
title: Come configurare Exchange Server locale per utilizzare l'autenticazione moderna ibrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Informazioni su come configurare un Exchange Server locale per l'utilizzo dell'autenticazione moderna ibrida (HMA, Hybrid Modern Authentication), offrendo un'autenticazione e un'autorizzazione degli utenti più sicure.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9393b457c219fb03ae2e8a35c3f795c324919f27
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579723"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="e1904-103">Come configurare Exchange Server locale per utilizzare l'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="e1904-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="e1904-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="e1904-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e1904-105">L'autenticazione moderna ibrida (HMA, Hybrid Modern Authentication) è un metodo di gestione delle identità che offre un'autenticazione e un'autorizzazione utente più sicure ed è disponibile per le distribuzioni ibride locali del server Exchange.</span><span class="sxs-lookup"><span data-stu-id="e1904-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="e1904-106">FYI</span><span class="sxs-lookup"><span data-stu-id="e1904-106">FYI</span></span>

<span data-ttu-id="e1904-107">Prima di iniziare, chiamo:</span><span class="sxs-lookup"><span data-stu-id="e1904-107">Before we begin, I call:</span></span>

- <span data-ttu-id="e1904-108">HMA per \> l'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="e1904-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="e1904-109">EXCH locale di Exchange \></span><span class="sxs-lookup"><span data-stu-id="e1904-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="e1904-110">EXO di Exchange Online \></span><span class="sxs-lookup"><span data-stu-id="e1904-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="e1904-111">Inoltre, se un elemento grafico in questo articolo ha un oggetto "grigio" o "in grigio", significa che l'elemento visualizzato in grigio non è incluso nella configurazione specifica *di HMA.*</span><span class="sxs-lookup"><span data-stu-id="e1904-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="e1904-112">Abilitazione dell'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="e1904-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="e1904-113">L'attivazione di HMA significa:</span><span class="sxs-lookup"><span data-stu-id="e1904-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="e1904-114">Assicurarsi di soddisfare i prereq prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="e1904-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="e1904-115">Poiché molti **prerequisiti sono** comuni sia per Skype for Business che per Exchange, panoramica dell'autenticazione moderna ibrida e prerequisiti per l'utilizzo con i server Skype for Business ed [Exchange locali.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1904-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="e1904-116">Eseguire questa operazione prima di iniziare una delle operazioni descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e1904-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="e1904-117">Aggiunta di URL del servizio Web locale come nomi dell'entità servizio **(SPN)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e1904-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="e1904-118">Se EXCH è ibrido con più **tenant,** questi URL del servizio Web locale devono essere aggiunti come SPN in Azure AD di tutti i tenant che sono ibridi con EXCH.</span><span class="sxs-lookup"><span data-stu-id="e1904-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="e1904-119">Verificare che tutte le directory virtuali siano abilitate per HMA</span><span class="sxs-lookup"><span data-stu-id="e1904-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="e1904-120">Verifica dell'oggetto EvoSTS Auth Server</span><span class="sxs-lookup"><span data-stu-id="e1904-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="e1904-121">Abilitazione di HMA in EXCH.</span><span class="sxs-lookup"><span data-stu-id="e1904-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="e1904-122">La tua versione di Office supporta Ma?</span><span class="sxs-lookup"><span data-stu-id="e1904-122">Does your version of Office support MA?</span></span> <span data-ttu-id="e1904-123">Vedere [Funzionamento dell'autenticazione moderna per le app client di Office 2013 e Office 2016.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="e1904-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="e1904-124">Assicurarsi di soddisfare tutti i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e1904-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="e1904-125">Poiché molti prerequisiti sono comuni sia per Skype for Business che per Exchange, vedere Panoramica dell'autenticazione moderna ibrida e prerequisiti per usarlo con i server Skype for Business ed [Exchange locali.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1904-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="e1904-126">Eseguire questa  *operazione prima*  di iniziare una delle operazioni descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e1904-126">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="e1904-127">Aggiungere URL del servizio Web locale come SPN in Azure AD</span><span class="sxs-lookup"><span data-stu-id="e1904-127">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="e1904-128">Eseguire i comandi che assegnano gli URL del servizio Web locale come SPN di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e1904-128">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="e1904-129">Gli SPN vengono utilizzati dai computer client e dai dispositivi durante l'autenticazione e l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1904-129">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="e1904-130">Tutti gli URL che possono essere usati per connettersi da locale ad Azure Active Directory (Azure AD) devono essere registrati in Azure AD (inclusi spazi dei nomi interni ed esterni).</span><span class="sxs-lookup"><span data-stu-id="e1904-130">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="e1904-131">Innanzitutto, raccogliere tutti gli URL che è necessario aggiungere in AAD.</span><span class="sxs-lookup"><span data-stu-id="e1904-131">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="e1904-132">Eseguire questi comandi in locale:</span><span class="sxs-lookup"><span data-stu-id="e1904-132">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="e1904-133">Verificare che gli URL a cui i client possano connettersi siano elencati come nomi dell'entità servizio HTTPS in AAD.</span><span class="sxs-lookup"><span data-stu-id="e1904-133">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="e1904-134">Se EXCH è ibrido con più **tenant,** questi SPN HTTPS devono essere aggiunti nell'AAD di tutti i tenant ibridi con EXCH.</span><span class="sxs-lookup"><span data-stu-id="e1904-134">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="e1904-135">Prima di tutto, connettersi ad AAD con [queste istruzioni.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e1904-135">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1904-136">È necessario utilizzare _l'opzione Connect-MsolService_ di questa pagina per poter utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e1904-136">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="e1904-137">Per gli URL correlati a Exchange, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e1904-137">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="e1904-138">Prendere nota (e screenshot per un confronto successivo) dell'output di questo comando, che deve includere un URL  *https:// autodiscover.yourdomain.com*  e  *https:// mail.yourdomain.com,* ma costituito principalmente da SPN che iniziano con 000000002-0000-0ff1-ce00-0000000000000/.</span><span class="sxs-lookup"><span data-stu-id="e1904-138">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="e1904-139">Se mancano https:// URL locali, sarà necessario aggiungere tali record specifici all'elenco.</span><span class="sxs-lookup"><span data-stu-id="e1904-139">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="e1904-140">Se i record MAPI/HTTP, EWS, ActiveSync, OAB e Autodiscover interni ed esterni non sono visualizzati in questo elenco, è necessario aggiungerli utilizzando il comando seguente (gli URL di esempio sono ' `mail.corp.contoso.com` ' e ' ', ma è necessario sostituire gli URL di esempio con i propri `owa.contoso.com` ): </span><span class="sxs-lookup"><span data-stu-id="e1904-140">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="e1904-141">Verificare che i nuovi record siano stati aggiunti eseguendo di nuovo il Get-MsolServicePrincipal dal passaggio 2 e esaminando l'output.</span><span class="sxs-lookup"><span data-stu-id="e1904-141">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="e1904-142">Confronta l'elenco/screenshot di prima con il nuovo elenco di SPN.</span><span class="sxs-lookup"><span data-stu-id="e1904-142">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="e1904-143">È inoltre possibile acquisire uno screenshot del nuovo elenco per i record.</span><span class="sxs-lookup"><span data-stu-id="e1904-143">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="e1904-144">Se l'operazione ha avuto esito positivo, nell'elenco verranno visualizzati i due nuovi URL.</span><span class="sxs-lookup"><span data-stu-id="e1904-144">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="e1904-145">In base all'esempio, l'elenco degli SPN includerà ora gli URL specifici  `https://mail.corp.contoso.com`  e  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="e1904-145">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="e1904-146">Verificare che le directory virtuali siano configurate correttamente</span><span class="sxs-lookup"><span data-stu-id="e1904-146">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="e1904-147">Verificare ora che OAuth sia abilitato correttamente in Exchange in tutte le directory virtuali che Outlook potrebbe utilizzare eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1904-147">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="e1904-148">Controlla l'output per assicurarti che **OAuth** sia abilitato in ognuno di questi VDir, avrà un aspetto simile al seguente (e la cosa chiave da vedere è "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="e1904-148">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="e1904-149">Se OAuth non è presente in alcun server e in una delle quattro directory virtuali, è necessario aggiungerla utilizzando i comandi pertinenti prima di procedere ([Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)e [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="e1904-149">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="e1904-150">Verificare che l'oggetto server di autenticazione EvoSTS sia presente</span><span class="sxs-lookup"><span data-stu-id="e1904-150">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="e1904-151">Tornare a Exchange Management Shell locale per l'ultimo comando.</span><span class="sxs-lookup"><span data-stu-id="e1904-151">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="e1904-152">A questo punto è possibile verificare che l'utente locale abbia una voce per il provider di autenticazione evoSTS:</span><span class="sxs-lookup"><span data-stu-id="e1904-152">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="e1904-153">L'output dovrebbe mostrare un AuthServer con nome EvoSts e lo stato "Enabled" deve essere True.</span><span class="sxs-lookup"><span data-stu-id="e1904-153">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="e1904-154">In caso contrario, è consigliabile scaricare ed eseguire la versione più recente della procedura guidata di configurazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="e1904-154">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="e1904-155">Se EXCH è ibrido con più **tenant,** l'output dovrebbe mostrare un AuthServer del nome EvoSts - {GUID} per ogni tenant ibrido con EXCH e lo stato "Enabled" deve essere True per tutti questi oggetti AuthServer.</span><span class="sxs-lookup"><span data-stu-id="e1904-155">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="e1904-156">**Importante** Se si esegue Exchange 2010 nell'ambiente, il provider di autenticazione EvoSTS non verrà creato.</span><span class="sxs-lookup"><span data-stu-id="e1904-156">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="e1904-157">Abilita HMA</span><span class="sxs-lookup"><span data-stu-id="e1904-157">Enable HMA</span></span>

<span data-ttu-id="e1904-158">Eseguire il comando seguente in Exchange Management Shell, locale:</span><span class="sxs-lookup"><span data-stu-id="e1904-158">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="e1904-159">Se la versione EXCH è Exchange 2016 (CU18 o versione successiva) o Exchange 2019 (CU7 o versione successiva) ed è stato configurato un ambiente ibrido con HCW scaricato dopo settembre 2020, eseguire il comando seguente in Exchange Management Shell, locale:</span><span class="sxs-lookup"><span data-stu-id="e1904-159">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="e1904-160">Se EXCH è ibrido con più **tenant,** in EXCH sono presenti più oggetti AuthServer con domini corrispondenti a ogni tenant.</span><span class="sxs-lookup"><span data-stu-id="e1904-160">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="e1904-161">Il flag **IsDefaultAuthorizationEndpoint** deve essere impostato su true (utilizzando il cmdlet **IsDefaultAuthorizationEndpoint)** per uno di questi oggetti AuthServer.</span><span class="sxs-lookup"><span data-stu-id="e1904-161">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="e1904-162">Questo flag non può essere impostato su true per tutti gli oggetti Authserver e HMA viene abilitato anche se il flag **IsDefaultAuthorizationEndpoint** di uno di questi oggetti AuthServer è impostato su true.</span><span class="sxs-lookup"><span data-stu-id="e1904-162">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="e1904-163">Verificare</span><span class="sxs-lookup"><span data-stu-id="e1904-163">Verify</span></span>

<span data-ttu-id="e1904-164">Dopo aver abilitato HMA, l'accesso successivo di un client userà il nuovo flusso di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="e1904-164">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="e1904-165">Tieni presente che l'attivazione di HMA non attiverà una riautenticazione per alcun client.</span><span class="sxs-lookup"><span data-stu-id="e1904-165">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="e1904-166">I client eserciteranno nuovamente l'autenticazione in base alla durata dei token di autenticazione e/o dei certificati di cui dispongono.</span><span class="sxs-lookup"><span data-stu-id="e1904-166">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="e1904-167">È inoltre necessario tenere premuto IL TASTO CTRL contemporaneamente a fare clic con il pulsante destro del mouse sull'icona del client di Outlook (anche nella barra delle notifiche di Windows) e scegliere "Stato connessione".</span><span class="sxs-lookup"><span data-stu-id="e1904-167">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="e1904-168">Cercare l'indirizzo SMTP del client rispetto a un tipo "Authn" di "Bearer", che rappresenta il token del portatore \* utilizzato in OAuth.</span><span class="sxs-lookup"><span data-stu-id="e1904-168">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="e1904-169">È necessario configurare Skype for Business con HMA?</span><span class="sxs-lookup"><span data-stu-id="e1904-169">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="e1904-170">Sono necessari due articoli: uno in cui sono elencate [le topologie](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)supportate e uno che illustra come eseguire [la configurazione.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="e1904-170">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="e1904-171">Utilizzo dell'autenticazione moderna ibrida con Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="e1904-171">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="e1904-172">Se si è un cliente locale che utilizza il server Exchange su TCP 443, ignorare l'elaborazione del traffico per i seguenti intervalli di indirizzi IP:</span><span class="sxs-lookup"><span data-stu-id="e1904-172">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="e1904-173">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e1904-173">Related topics</span></span>

[<span data-ttu-id="e1904-174">Requisiti di configurazione dell'autenticazione moderna per la transizione da Office 365 dedicato/ITAR a vNext</span><span class="sxs-lookup"><span data-stu-id="e1904-174">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
