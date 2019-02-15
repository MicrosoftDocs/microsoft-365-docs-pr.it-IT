---
title: Informazioni di riferimento sulle impostazioni conFigurabili per Microsoft Managed Desktop
description: Impostazione delle categorie per le impostazioni configurabili in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051097"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="96cb7-104">Riferimento alle impostazioni conFigurabili-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="96cb7-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="96cb7-p101">In questo argomento sono elencate le categorie di impostazioni che i clienti possono configurare con Microsoft Managed Desktop. Ogni categoria di impostazioni include informazioni su requisiti, procedure consigliate e su come personalizzare la categoria di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="96cb7-p101">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop. Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="96cb7-107">Immagine di sfondo del desktop</span><span class="sxs-lookup"><span data-stu-id="96cb7-107">Desktop background picture</span></span>
<span data-ttu-id="96cb7-p102">È possibile personalizzare l'immagine di sfondo del desktop per i dispositivi Microsoft Managed Desktop nell'organizzazione. È possibile utilizzarlo per applicare un marchio aziendale o un marketing</span><span class="sxs-lookup"><span data-stu-id="96cb7-p102">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization. You might use this to apply a company brand or marketing</span></span> 

### <a name="requirements"></a><span data-ttu-id="96cb7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96cb7-110">Requirements</span></span>

<span data-ttu-id="96cb7-111">Questi requisiti devono essere soddisfatti per un'immagine di sfondo del desktop:</span><span class="sxs-lookup"><span data-stu-id="96cb7-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="96cb7-112">Formato file immagine-. jpg, JPEG o. png</span><span class="sxs-lookup"><span data-stu-id="96cb7-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="96cb7-113">Percorso del file-host in un percorso http sicuro (HTTPS) attendibile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="96cb7-114">Non consentiti-i percorsi http e di condivisione file (UNC) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="96cb7-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="96cb7-115">Personalizzare e distribuire l'immagine di sfondo del desktop</span><span class="sxs-lookup"><span data-stu-id="96cb7-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="96cb7-116">**Per aggiungere un'immagine di sfondo del desktop personalizzata**</span><span class="sxs-lookup"><span data-stu-id="96cb7-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="96cb7-117">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="96cb7-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="96cb7-118">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="96cb7-119">Nell' \*\*\*\* area di lavoro configurabile selezionare **immagine di sfondo del desktop**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="96cb7-120">Immettere il percorso dell'immagine che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="96cb7-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="96cb7-121">Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle all'anello di prova.</span><span class="sxs-lookup"><span data-stu-id="96cb7-121">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="96cb7-122">Pagine iniziali del browser</span><span class="sxs-lookup"><span data-stu-id="96cb7-122">Browser start pages</span></span>
<span data-ttu-id="96cb7-p103">Le pagine iniziali del browser vengono aperte nelle singole schede quando gli utenti avviano Microsoft Edge. Se si desidera consentire agli utenti di aprire facilmente una serie di siti che utilizzano frequentemente, aggiungere una pagina iniziale del browser per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="96cb7-p103">Browser start pages open in individual tabs when your users start Microsoft Edge. If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="96cb7-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96cb7-125">Requirements</span></span>

<span data-ttu-id="96cb7-p104">È necessario fornire il nome di dominio completo (FQDN) per i siti Intranet o Internet per le pagine iniziali del browser. Se i siti interni sono configurati, consentire agli utenti di sapere che l'accesso a questi siti è consentito solo quando si è connessi alla rete interna quando si è in ufficio o quando si è connessi a una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="96cb7-p104">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages. If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="96cb7-128">Personalizzare e distribuire le pagine iniziali del browser</span><span class="sxs-lookup"><span data-stu-id="96cb7-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="96cb7-129">**Per aggiungere una pagina iniziale del browser**</span><span class="sxs-lookup"><span data-stu-id="96cb7-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="96cb7-130">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="96cb7-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="96cb7-131">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="96cb7-132">Nell' \*\*\*\* area di lavoro configurabile selezionare **pagine iniziali del browser**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="96cb7-133">Selezionare **Aggiungi pagina iniziale**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="96cb7-134">Nella **pagina Aggiungi inizio browser**immettere l'URL del sito che si desidera utilizzare e quindi fare clic su **Aggiungi pagina iniziale**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="96cb7-135">Ripetere i passaggi 1-5 per altre pagine iniziali del browser.</span><span class="sxs-lookup"><span data-stu-id="96cb7-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="96cb7-136">Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle all'anello di prova.</span><span class="sxs-lookup"><span data-stu-id="96cb7-136">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="96cb7-137">Posizione dell'elenco dei siti in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="96cb7-137">Enterprise mode site list location</span></span>

<span data-ttu-id="96cb7-p105">Se si dispone di siti Web e app specifici che si conoscono con problemi di compatibilità con Microsoft Edge, è possibile utilizzare l'elenco dei siti in modalità Enterprise in modo che i siti Web vengano aperti automaticamente tramite Internet Explorer 11. Inoltre, se si è certi che i siti Intranet non funzioneranno correttamente con Microsoft Edge, è possibile impostare tutti i siti Intranet per l'apertura automatica tramite Internet Explorer 11. Se si utilizza la modalità organizzazione, è possibile continuare a utilizzare Microsoft Edge come browser predefinito, garantendo anche che le app continuino a funzionare in Internet Explorer 11. Per ulteriori informazioni sugli elenchi di siti in modalità Enterprise, vedere [Enterprise Mode and Enterprise site lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span><span class="sxs-lookup"><span data-stu-id="96cb7-p105">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11. Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11. For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="96cb7-142">È possibile specificare una posizione di https://o il percorso di una condivisione interna in cui è stato ospitato l'elenco dei siti in modalità organizzazione.</span><span class="sxs-lookup"><span data-stu-id="96cb7-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="96cb7-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96cb7-143">Requirements</span></span>

<span data-ttu-id="96cb7-144">Questi requisiti devono essere soddisfatti per il file dell'elenco dei siti in modalità Enterprise:</span><span class="sxs-lookup"><span data-stu-id="96cb7-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="96cb7-145">Formato di file-file XML che soddisfa i [requisiti dei file](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="96cb7-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="96cb7-146">File location-host file in un percorso HTTPS interno.</span><span class="sxs-lookup"><span data-stu-id="96cb7-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="96cb7-147">Non consentito: l'hosting su una condivisione file interna, come *//ShareName*, non è consentito</span><span class="sxs-lookup"><span data-stu-id="96cb7-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="96cb7-148">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="96cb7-148">Best practices</span></span>

<span data-ttu-id="96cb7-149">Queste procedure consigliate sono disponibili per consentire ai clienti di prendere decisioni per modernizzare l'infrastruttura IT:</span><span class="sxs-lookup"><span data-stu-id="96cb7-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="96cb7-p106">**Scegliere un numero limitato di siti** : Microsoft Managed Desktop utilizza Microsoft Edge come browser preferito per migliorare la sicurezza complessiva per l'organizzazione e l'usabilità per gli utenti. La maggior parte dei siti in questo elenco è per le app Web legacy che richiedono una versione precedente di un browser che non includerà il numero di funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="96cb7-p106">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users. Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="96cb7-p107">Si conSideri **un'alternativa** : si consideri un sito diverso o un'app Web che non richiede un browser meno recente. In alternativa, è consigliabile aggiornare il sito in modo che possa utilizzare browser più recenti. I browser più recenti utilizzano la tecnologia più recente e contribuiscono a migliorare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="96cb7-p107">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser. Or, consider updating the site so that it can use newer browsers. Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="96cb7-155">Personalizzare e distribuire il percorso dell'elenco delle modalità sito Enterprise</span><span class="sxs-lookup"><span data-stu-id="96cb7-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="96cb7-156">**Per aggiungere una posizione nell'elenco delle modalità sito dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="96cb7-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="96cb7-157">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="96cb7-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="96cb7-158">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="96cb7-159">Nell' \*\*\*\* area di lavoro configurabile selezionare **percorso dell'elenco dei siti in modalità Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="96cb7-160">Immettere il percorso HTTPS per l'elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="96cb7-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="96cb7-161">Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle all'anello di prova.</span><span class="sxs-lookup"><span data-stu-id="96cb7-161">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="96cb7-162">Siti attendibili</span><span class="sxs-lookup"><span data-stu-id="96cb7-162">Trusted sites</span></span>

<span data-ttu-id="96cb7-p108">I siti attendibili consentono di personalizzare le aree di sicurezza o il luogo in cui è possibile utilizzare un sito per diversi siti. Le aree di sicurezza includono:</span><span class="sxs-lookup"><span data-stu-id="96cb7-p108">Trusted sites allow you to customize security zones, or where a site can be used, for different sites. Security zones include:</span></span> 
- <span data-ttu-id="96cb7-165">Zona 1-area Intranet locale</span><span class="sxs-lookup"><span data-stu-id="96cb7-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="96cb7-166">Zona 2-area siti attendibili</span><span class="sxs-lookup"><span data-stu-id="96cb7-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="96cb7-167">Zona 3-area Internet</span><span class="sxs-lookup"><span data-stu-id="96cb7-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="96cb7-168">Zona 4-area siti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="96cb7-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="96cb7-169">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96cb7-169">Requirements</span></span>

<span data-ttu-id="96cb7-170">Specificare il nome di dominio completo (FQDN) per i siti Intranet o Internet per ogni sito attendibile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="96cb7-171">Personalizzare e distribuire siti attendibili</span><span class="sxs-lookup"><span data-stu-id="96cb7-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="96cb7-172">**Per aggiungere un sito attendibile**</span><span class="sxs-lookup"><span data-stu-id="96cb7-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="96cb7-173">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="96cb7-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="96cb7-174">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="96cb7-175">Nell' \*\*\*\* area di lavoro configurabile selezionare **siti attendibili**e quindi fare clic su **Aggiungi sito attendibile**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="96cb7-176">In **Aggiungi sito attendibile**immettere l'URL, scegliere un'area di sicurezza e quindi fare clic su **Aggiungi sito attendibile**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="96cb7-177">Ripetere i passaggi 1-4 per ogni sito attendibile che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="96cb7-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="96cb7-178">Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle all'anello di prova.</span><span class="sxs-lookup"><span data-stu-id="96cb7-178">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

<span data-ttu-id="96cb7-179">**Per rimuovere un sito attendibile**</span><span class="sxs-lookup"><span data-stu-id="96cb7-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="96cb7-180">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="96cb7-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="96cb7-181">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="96cb7-182">Nell' \*\*\*\* area di lavoro configurabile selezionare **siti attendibili**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="96cb7-183">Selezionare il sito che si desidera eliminare, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="96cb7-184">Ripetere i passaggi 1-4 per ogni sito attendibile che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="96cb7-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="96cb7-185">Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle all'anello di prova.</span><span class="sxs-lookup"><span data-stu-id="96cb7-185">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="proxy"></a><span data-ttu-id="96cb7-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="96cb7-186">Proxy</span></span>
<span data-ttu-id="96cb7-p109">È possibile gestire le impostazioni del proxy di rete per l'organizzazione. Aggiungere il server proxy e il numero di porta e quindi aggiungere le eccezioni del sito proxy. Microsoft Managed Desktop include un insieme di eccezioni proxy predefinite che sono necessarie per l'utilizzo del servizio. L'elenco di esclusione predefinito può essere modificato solo dal servizio Microsoft Managed Desktop.  Per ulteriori informazioni, vedere [configurazione di rete per Microsoft managEd desktop](../get-ready/network.md).</span><span class="sxs-lookup"><span data-stu-id="96cb7-p109">You can manage network proxy settings for your organization. Add your proxy server and port number, and then add your proxy site exceptions. Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate. The default exclusion list may only be modified by the Microsoft Managed Desktop service.  For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="96cb7-192">Le eccezioni del sito proxy aggiunte nel portale Microsoft Managed Desktop vengono inserite nelle eccezioni proxy predefinite incluse in Microsoft Managed Desktop Service.</span><span class="sxs-lookup"><span data-stu-id="96cb7-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="96cb7-p110">L'aggiornamento dell'elenco di eccezioni proxy predefinito è sempre prioritario rispetto alle distribuzioni dei clienti. Questo significa che la distribuzione a fasi verrà sospesa se esiste una distribuzione per l'elenco delle eccezioni del proxy predefinito.</span><span class="sxs-lookup"><span data-stu-id="96cb7-p110">Updating the default proxy exception list is always prioritized over customer deployments. This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="96cb7-195">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96cb7-195">Requirements</span></span>

<span data-ttu-id="96cb7-196">Questi requisiti devono essere soddisfatti per le eccezioni del server proxy e del sito proxy:</span><span class="sxs-lookup"><span data-stu-id="96cb7-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="96cb7-197">Deve essere un indirizzo del server e un numero di porta validi</span><span class="sxs-lookup"><span data-stu-id="96cb7-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="96cb7-198">Gli URL devono essere un sito http valido</span><span class="sxs-lookup"><span data-stu-id="96cb7-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="96cb7-199">Personalizzare e distribuire proxy</span><span class="sxs-lookup"><span data-stu-id="96cb7-199">Customize and deploy proxies</span></span>

<span data-ttu-id="96cb7-200">**Per aggiungere una singola eccezione del sito proxy**</span><span class="sxs-lookup"><span data-stu-id="96cb7-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="96cb7-201">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="96cb7-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="96cb7-202">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="96cb7-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="96cb7-203">Nell' \*\*\*\* area di lavoro configurabile selezionare **proxy**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="96cb7-204">Immettere l' **Indirizzo** e il **numero di porta** del server proxy, quindi selezionare **Aggiungi eccezione proxy**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="96cb7-205">Immettere l'URL di un sito http valido e quindi fare clic su **Aggiungi eccezione proxy**.</span><span class="sxs-lookup"><span data-stu-id="96cb7-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="96cb7-206">Ripetere i passaggi 1-5 per ogni sito attendibile che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="96cb7-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="96cb7-207">Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle all'anello di prova.</span><span class="sxs-lookup"><span data-stu-id="96cb7-207">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="96cb7-208">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="96cb7-208">Additional resources</span></span>
- [<span data-ttu-id="96cb7-209">Panoramica delle impostazioni conFigurabili</span><span class="sxs-lookup"><span data-stu-id="96cb7-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="96cb7-210">Distribuire le impostazioni configurabili</span><span class="sxs-lookup"><span data-stu-id="96cb7-210">Deploy configurable settings</span></span>](config-setting-deploy.md)