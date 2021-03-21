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
ms.openlocfilehash: 46646f35d3b41821424269f66721fbf829d339f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928203"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="d6c0a-103">Come configurare Exchange Server locale per utilizzare l'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="d6c0a-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="d6c0a-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d6c0a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d6c0a-105">L'autenticazione moderna ibrida (HMA, Hybrid Modern Authentication) è un metodo di gestione delle identità che offre un'autenticazione e un'autorizzazione utente più sicure ed è disponibile per le distribuzioni ibride locali del server Exchange.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="d6c0a-106">FYI</span><span class="sxs-lookup"><span data-stu-id="d6c0a-106">FYI</span></span>

<span data-ttu-id="d6c0a-107">Prima di iniziare, chiamo:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-107">Before we begin, I call:</span></span>

- <span data-ttu-id="d6c0a-108">HMA per \> l'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="d6c0a-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="d6c0a-109">EXCH locale di Exchange \></span><span class="sxs-lookup"><span data-stu-id="d6c0a-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="d6c0a-110">EXO di Exchange Online \></span><span class="sxs-lookup"><span data-stu-id="d6c0a-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="d6c0a-111">Inoltre, se un elemento grafico in questo articolo ha un oggetto "grigio" o "in grigio", significa che l'elemento visualizzato in grigio non è incluso nella configurazione specifica *di HMA.*</span><span class="sxs-lookup"><span data-stu-id="d6c0a-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="d6c0a-112">Abilitazione dell'autenticazione moderna ibrida</span><span class="sxs-lookup"><span data-stu-id="d6c0a-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="d6c0a-113">L'attivazione di HMA significa:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="d6c0a-114">Assicurarsi di soddisfare i prereq prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="d6c0a-115">Poiché molti **prerequisiti sono** comuni sia per Skype for Business che per Exchange, panoramica dell'autenticazione moderna ibrida e prerequisiti per l'utilizzo con i server Skype for Business ed [Exchange locali.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d6c0a-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="d6c0a-116">Eseguire questa operazione prima di iniziare una delle operazioni descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="d6c0a-117">Aggiunta di URL del servizio Web locale come nomi dell'entità servizio **(SPN)** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="d6c0a-118">Verificare che tutte le directory virtuali siano abilitate per HMA</span><span class="sxs-lookup"><span data-stu-id="d6c0a-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="d6c0a-119">Verifica dell'oggetto EvoSTS Auth Server</span><span class="sxs-lookup"><span data-stu-id="d6c0a-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="d6c0a-120">Abilitazione di HMA in EXCH.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="d6c0a-121">**Nota** La tua versione di Office supporta Ma?</span><span class="sxs-lookup"><span data-stu-id="d6c0a-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="d6c0a-122">Vedere [Funzionamento dell'autenticazione moderna per le app client di Office 2013 e Office 2016.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="d6c0a-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="d6c0a-123">Assicurarsi di soddisfare tutti i prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d6c0a-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="d6c0a-124">Poiché molti prerequisiti sono comuni sia per Skype for Business che per Exchange, vedere Panoramica dell'autenticazione moderna ibrida e prerequisiti per usarlo con i server Skype for Business ed [Exchange locali.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d6c0a-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="d6c0a-125">Eseguire questa  *operazione prima*  di iniziare una delle operazioni descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="d6c0a-126">Aggiungere URL del servizio Web locale come SPN in Azure AD</span><span class="sxs-lookup"><span data-stu-id="d6c0a-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="d6c0a-127">Eseguire i comandi che assegnano gli URL del servizio Web locale come SPN di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="d6c0a-128">Gli SPN vengono utilizzati dai computer client e dai dispositivi durante l'autenticazione e l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="d6c0a-129">Tutti gli URL che possono essere usati per connettersi da locale ad Azure Active Directory (Azure AD) devono essere registrati in Azure AD (inclusi spazi dei nomi interni ed esterni).</span><span class="sxs-lookup"><span data-stu-id="d6c0a-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="d6c0a-130">Innanzitutto, raccogliere tutti gli URL che è necessario aggiungere in AAD.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="d6c0a-131">Eseguire questi comandi in locale:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="d6c0a-132">Verificare che gli URL a cui i client possano connettersi siano elencati come nomi dell'entità servizio HTTPS in AAD.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="d6c0a-133">Prima di tutto, connettersi ad AAD con [queste istruzioni.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d6c0a-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="d6c0a-134">**Nota** È necessario utilizzare _l'opzione Connect-MsolService_ di questa pagina per poter utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="d6c0a-135">Per gli URL correlati a Exchange, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="d6c0a-136">Prendere nota (e screenshot per un confronto successivo) dell'output di questo comando, che deve includere un URL  *https:// autodiscover.yourdomain.com*  e  *https:// mail.yourdomain.com,* ma costituito principalmente da SPN che iniziano con 000000002-0000-0ff1-ce00-0000000000000/.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="d6c0a-137">Se mancano https:// URL locali, sarà necessario aggiungere tali record specifici all'elenco.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="d6c0a-138">Se i record MAPI/HTTP, EWS, ActiveSync, OAB e Autodiscover interni ed esterni non sono visualizzati in questo elenco, è necessario aggiungerli utilizzando il comando seguente (gli URL di esempio sono ' `mail.corp.contoso.com` ' e ' ', ma è necessario sostituire gli URL di esempio con i propri `owa.contoso.com` ): </span><span class="sxs-lookup"><span data-stu-id="d6c0a-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="d6c0a-139">Verificare che i nuovi record siano stati aggiunti eseguendo di nuovo il Get-MsolServicePrincipal dal passaggio 2 e esaminando l'output.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="d6c0a-140">Confronta l'elenco/screenshot di prima con il nuovo elenco di SPN.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="d6c0a-141">È inoltre possibile acquisire uno screenshot del nuovo elenco per i record.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="d6c0a-142">Se l'operazione ha avuto esito positivo, nell'elenco verranno visualizzati i due nuovi URL.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="d6c0a-143">In base all'esempio, l'elenco degli SPN includerà ora gli URL specifici  `https://mail.corp.contoso.com`  e  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="d6c0a-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="d6c0a-144">Verificare che le directory virtuali siano configurate correttamente</span><span class="sxs-lookup"><span data-stu-id="d6c0a-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="d6c0a-145">Verificare ora che OAuth sia abilitato correttamente in Exchange in tutte le directory virtuali che Outlook potrebbe utilizzare eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="d6c0a-146">Controlla l'output per assicurarti che **OAuth** sia abilitato in ognuno di questi VDir, avrà un aspetto simile al seguente (e la cosa chiave da vedere è "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="d6c0a-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="d6c0a-147">Se OAuth non è presente in alcun server e in una delle quattro directory virtuali, è necessario aggiungerla utilizzando i comandi pertinenti prima di procedere ([Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)e [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="d6c0a-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="d6c0a-148">Verificare che l'oggetto server di autenticazione EvoSTS sia presente</span><span class="sxs-lookup"><span data-stu-id="d6c0a-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="d6c0a-149">Tornare a Exchange Management Shell locale per l'ultimo comando.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="d6c0a-150">A questo punto è possibile verificare che l'utente locale abbia una voce per il provider di autenticazione evoSTS:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="d6c0a-151">L'output dovrebbe mostrare un AuthServer con nome EvoSts e lo stato "Enabled" deve essere True.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="d6c0a-152">In caso contrario, è consigliabile scaricare ed eseguire la versione più recente della procedura guidata di configurazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="d6c0a-153">**Importante** Se si esegue Exchange 2010 nell'ambiente, il provider di autenticazione EvoSTS non verrà creato.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="d6c0a-154">Abilita HMA</span><span class="sxs-lookup"><span data-stu-id="d6c0a-154">Enable HMA</span></span>

<span data-ttu-id="d6c0a-155">Eseguire il comando seguente in Exchange Management Shell, locale:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="d6c0a-156">Verificare</span><span class="sxs-lookup"><span data-stu-id="d6c0a-156">Verify</span></span>

<span data-ttu-id="d6c0a-157">Dopo aver abilitato HMA, l'accesso successivo di un client userà il nuovo flusso di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="d6c0a-158">Tieni presente che l'attivazione di HMA non attiverà una riautenticazione per alcun client.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="d6c0a-159">I client eserciteranno nuovamente l'autenticazione in base alla durata dei token di autenticazione e/o dei certificati di cui dispongono.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="d6c0a-160">È inoltre necessario tenere premuto IL TASTO CTRL contemporaneamente a fare clic con il pulsante destro del mouse sull'icona del client di Outlook (anche nella barra delle notifiche di Windows) e scegliere "Stato connessione".</span><span class="sxs-lookup"><span data-stu-id="d6c0a-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="d6c0a-161">Cercare l'indirizzo SMTP del client rispetto a un tipo "Authn" di "Bearer", che rappresenta il token del portatore \* utilizzato in OAuth.</span><span class="sxs-lookup"><span data-stu-id="d6c0a-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="d6c0a-162">**Nota** È necessario configurare Skype for Business con HMA?</span><span class="sxs-lookup"><span data-stu-id="d6c0a-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="d6c0a-163">Sono necessari due articoli: uno in cui sono elencate [le topologie](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)supportate e uno che illustra come eseguire [la configurazione.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="d6c0a-163">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="d6c0a-164">Utilizzo dell'autenticazione moderna ibrida con Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="d6c0a-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="d6c0a-165">Se si è un cliente locale che utilizza il server Exchange su TCP 443, ignorare l'elaborazione del traffico per i seguenti intervalli IP:</span><span class="sxs-lookup"><span data-stu-id="d6c0a-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="d6c0a-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d6c0a-166">Related topics</span></span>

[<span data-ttu-id="d6c0a-167">Requisiti di configurazione dell'autenticazione moderna per la transizione da Office 365 dedicato/ITAR a vNext</span><span class="sxs-lookup"><span data-stu-id="d6c0a-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)