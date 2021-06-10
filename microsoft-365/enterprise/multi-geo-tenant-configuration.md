---
title: Configurazione del tenant di Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Questo articolo illustra come aggiungere posizioni satellitari e configurare il tenant per Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9176c66e8d0aa7e893ef137131147f8e0c85d3ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923649"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="bc105-103">Configurazione del tenant di Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="bc105-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="bc105-104">Prima di configurare il tenant per Microsoft 365 Multi-Geo, assicurarsi di aver letto [Piano per Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="bc105-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="bc105-105">Per eseguire la procedura descritta in questo articolo, è necessario un elenco delle posizioni geografiche che si desidera abilitare come località satelliti e gli utenti test che si desidera predisporre in queste posizioni.</span><span class="sxs-lookup"><span data-stu-id="bc105-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="bc105-106">Aggiungere Multi-Geo Capabilities nel piano di Microsoft 365 del tenant</span><span class="sxs-lookup"><span data-stu-id="bc105-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="bc105-107">Per usare Office 365 Multi-Geo, è necessario il piano _Multi-Geo Capabilities in Microsoft 365_.</span><span class="sxs-lookup"><span data-stu-id="bc105-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="bc105-108">Rivolgersi al team dell’account per aggiungere questo piano al tuo tenant.</span><span class="sxs-lookup"><span data-stu-id="bc105-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="bc105-109">Il team dell’account connetterà l’utente con lo specialista della licenza appropriato e configurerà il tenant.</span><span class="sxs-lookup"><span data-stu-id="bc105-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="bc105-p103">Tenere presente che il piano _Multi-Geo Capabilities in Microsoft 365_ è un piano di servizio a livello di utente. È necessaria una licenza per ogni utente da ospitare in una posizione satellite. È possibile aggiungere più licenze nel tempo man mano che si aggiungono utenti alle posizioni satellite.</span><span class="sxs-lookup"><span data-stu-id="bc105-p103">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan. You need a license for each user that you want to host in a satellite location. You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="bc105-113">Una volta che nel tenant è stato effettuato il provisioning del piano _Multi-Geo Capabilities in Microsoft 365_, la scheda **Posizioni geografiche** diventerà disponibile nell'interfaccia di amministrazione di OneDrive e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc105-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="bc105-114">Aggiungere posizioni satellite al tenant</span><span class="sxs-lookup"><span data-stu-id="bc105-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="bc105-115">È necessario aggiungere una posizione satellite per ogni località geografica in cui si desidera memorizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="bc105-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="bc105-116">Nella tabella seguente, sono elencate le località geografiche disponibili:</span><span class="sxs-lookup"><span data-stu-id="bc105-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Schermata della pagina con le località geografiche nell'interfaccia di amministrazione di SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="bc105-118">Per aggiungere una posizione satellite</span><span class="sxs-lookup"><span data-stu-id="bc105-118">To add a satellite location</span></span>

1. <span data-ttu-id="bc105-119">Aprire l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc105-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="bc105-120">Andare alla scheda **Posizioni geografiche**.</span><span class="sxs-lookup"><span data-stu-id="bc105-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="bc105-121">Fare clic su **Aggiungi posizione**.</span><span class="sxs-lookup"><span data-stu-id="bc105-121">Click **Add location**.</span></span>

4. <span data-ttu-id="bc105-122">Selezionare la posizione che si desidera aggiungere, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bc105-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="bc105-123">Digitare il dominio da usare con la posizione geografica, quindi fare clic su **Aggiungi**. </span><span class="sxs-lookup"><span data-stu-id="bc105-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="bc105-124">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bc105-124">Click **Close**.</span></span>

<span data-ttu-id="bc105-p105">Il provisioning può durare da alcune ore fino a 72 ore, a seconda delle dimensioni del tenant. Al termine del provisioning di una posizione satellite, verrà inviato un messaggio di posta elettronica di conferma. Quando la nuova posizione geografica diventa blu sulla mappa nella scheda **Posizioni geografiche** nell'interfaccia di amministrazione di OneDrive, è possibile procedere per impostare la posizione dati preferita dell'utente su tale posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="bc105-p105">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant. Once provisioning of a satellite location has completed, you will receive an email confirmation. When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="bc105-p106">La nuova posizione satellite sarà configurata con le impostazioni predefinite. In questo modo sarà possibile configurare tale posizione satellite in base alle proprie esigenze di conformità locale.</span><span class="sxs-lookup"><span data-stu-id="bc105-p106">Your new satellite location will be set up with default settings. This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="bc105-130">Impostare la posizione dati preferita dell'utente</span><span class="sxs-lookup"><span data-stu-id="bc105-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="bc105-p107">Dopo aver abilitato le posizioni satellite necessarie, è possibile aggiornare gli account utente per utilizzare il percorso dati preferito appropriato. Si consiglia di impostare una posizione dati preferita per ogni utente, anche se l'utente si trova in una posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="bc105-p107">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location. We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc105-133">Se il percorso dei dati preferito dell'utente è impostato su una posizione che non sia stata configurata come posizione satellitare o posizione centrale, il sistema imposterà la posizione centrale come predefinita durante il provisioning dei siti di OneDrive, SharePoint e delle cassette postali di gruppo.</span><span class="sxs-lookup"><span data-stu-id="bc105-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="bc105-134">Si consiglia di iniziare le convalide con un utente di test o con un gruppo limitato di utenti prima di distribuire le funzionalità multi-geografiche in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bc105-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="bc105-135">Sono disponibili due tipi di oggetti utente in Azure Active Directory (Azure AD): solo utenti cloud e utenti sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="bc105-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="bc105-136">Seguire le istruzioni appropriate in base al tipo di utente.</span><span class="sxs-lookup"><span data-stu-id="bc105-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="bc105-137">Sincronizzare la posizione preferita dei dati dell'utente utilizzando Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="bc105-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="bc105-138">Se gli utenti dell'organizzazione sono sincronizzati da un sistema di Active Directory locale con Azure AD, il PreferredDataLocation deve essere popolato in Active Directory e sincronizzato con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bc105-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="bc105-139">Seguire la procedura in [Sincronizzazione di Azure Active Directory Connect: configurare la posizione preferita dei dati per le risorse di Microsoft 365](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) per configurare la sincronizzazione della posizione preferita dei dati da Active Directory Domain Services (AD DS) locale a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bc105-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="bc105-140">È consigliabile includere l'impostazione della posizione dati preferita dell'utente nel processo standard di creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="bc105-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc105-141">Per i nuovi utenti senza il provisioning di OneDrive, attendere almeno 24 ore dopo che il PDL di un utente viene sincronizzato con Azure AD perché le modifiche si propaghino, prima che l'utente acceda a OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="bc105-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="bc105-142">(Impostare la posizione dati preferita prima che l'utente si connetta per effettuare il provisioning di OneDrive for Business consente al nuovo OneDrive dell'utentedi effettuareil provisioning nella posizione corretta.)</span><span class="sxs-lookup"><span data-stu-id="bc105-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="bc105-143">Impostazione della posizione dati preferita per utenti solo cloud</span><span class="sxs-lookup"><span data-stu-id="bc105-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="bc105-144">Se gli utenti dell'azienda non vengono sincronizzati da un sistema Active Directory locale ad Azure AD, significa che sono stati creati in Microsoft 365 o Azure AD e quindi la posizione preferita dei dati deve essere impostata tramite il modulo Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc105-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="bc105-145">La procedura contenuta in questa sezione richiede il [modulo di Microsoft Azure Active Directory per Windows PowerShell](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span><span class="sxs-lookup"><span data-stu-id="bc105-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="bc105-146">Se il modulo è già installato, assicurarsi di eseguire l'aggiornamento alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="bc105-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="bc105-147">[Connettersi e accedere](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) con le credenziali di amministratore globale del tenant.</span><span class="sxs-lookup"><span data-stu-id="bc105-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="bc105-p111">Usare il cmdlet [Set-MsolUser](/powershell/msonline/v1/set-msoluser) per impostare la posizione dati preferita per ognuno degli utenti. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bc105-p111">Use the [Set-MsolUser](/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users. For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="bc105-p112">È possibile controllare che la posizione dati preferita sia stata aggiornata correttamente con il cmdlet Get-MsolUser. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bc105-p112">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet. For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Screenshot della finestra di PowerShell con il iset-msoluser](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="bc105-153">È consigliabile includere l'impostazione della posizione dati preferita dell'utente nel processo standard di creazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="bc105-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc105-154">Per i nuovi utenti senza il provisioning di OneDrive, attendere almeno 24 ore dopo che il PDL di un utente venga sincronizzato con Azure Active Directory perché le modifiche si propaghino, prima che l'utente acceda a OneDrive.</span><span class="sxs-lookup"><span data-stu-id="bc105-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="bc105-155">(Impostare la posizione dati preferita prima che l'utente si connetta per effettuare il provisioning di OneDrive for Business consente al nuovo OneDrive dell'utentedi effettuareil provisioning nella posizione corretta.)</span><span class="sxs-lookup"><span data-stu-id="bc105-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="bc105-156">Provisioning di OneDrive e l'effetto della posizione dati preferita</span><span class="sxs-lookup"><span data-stu-id="bc105-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="bc105-157">Se l'utente ha già un sito OneDrive creato nel tenant, impostare il PDL non sposterà automaticamente il OneDrive esistente.</span><span class="sxs-lookup"><span data-stu-id="bc105-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="bc105-158">Per spostare la posizione di un utente OneDrive, vedere OneDrive for Business [Geo Move](move-onedrive-between-geo-locations.md).</span><span class="sxs-lookup"><span data-stu-id="bc105-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bc105-159">Exchange Online sposta automaticamente la cassetta postale dell'utente se il PLD cambia e MailboxRegion non corrisponde più al codice di posizione geografica del database delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="bc105-159">Exchange Online automatically relocates the user's mailbox if the PLD changes and the MailboxRegion no longer matches the Mailbox Database Geo Location code.</span></span> <span data-ttu-id="bc105-160">Per ulteriori informazioni, vedere [Administering Exchange Online mailboxes in a multi-geo environment](./administering-exchange-online-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="bc105-160">For more information, see [Administering Exchange Online mailboxes in a multi-geo environment](./administering-exchange-online-multi-geo.md).</span></span>

<span data-ttu-id="bc105-161">Se l'utente non dispone di un sito di OneDrive all'interno del tenant, il provisioning di OneDrive verrà eseguito in base al valore della posizione dati preferita, presupponendo che la posizione dati preferita dell'utente corrisponda a una delle posizioni satellite della società.</span><span class="sxs-lookup"><span data-stu-id="bc105-161">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="bc105-162">Configurazione della ricerca multi-geografica</span><span class="sxs-lookup"><span data-stu-id="bc105-162">Configuring Multi-Geo search</span></span>

<span data-ttu-id="bc105-163">Il tenant multi-geografico aggrega le funzionalità di ricerca pertanto le query di ricerca restituiscono i risultati di tutte le posizioni all'interno del tenant.</span><span class="sxs-lookup"><span data-stu-id="bc105-163">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="bc105-164">Per impostazione predefinita, le ricerche da questi punti di ingresso restituiranno risultati aggregati, anche se ogni indice di ricerca si trova nella relativa posizione geografica rilevante:</span><span class="sxs-lookup"><span data-stu-id="bc105-164">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="bc105-165">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="bc105-165">OneDrive for Business</span></span>

- <span data-ttu-id="bc105-166">Delve</span><span class="sxs-lookup"><span data-stu-id="bc105-166">Delve</span></span>

- <span data-ttu-id="bc105-167">Home page di SharePoint</span><span class="sxs-lookup"><span data-stu-id="bc105-167">SharePoint Home</span></span>

- <span data-ttu-id="bc105-168">Centro ricerche</span><span class="sxs-lookup"><span data-stu-id="bc105-168">Search Center</span></span>

<span data-ttu-id="bc105-169">Inoltre, le funzionalità della ricerca multi-geografica possono essere configurate per applicazioni di ricerca personalizzate che utilizzano l'API del servizio di ricerca di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc105-169">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="bc105-170">Consultare [Configurare la ricerca per OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) per ottenere maggiori informazioni, comprese le limitazioni e un confronto delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="bc105-170">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="bc105-171">Convalida della configurazione di Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="bc105-171">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="bc105-172">Ecco alcuni casi di utilizzo di base che è opportuno includere nel piano di convalida prima della distribuzione di Microsoft 365 Multi-Geo su vasta scala all'interno dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="bc105-172">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="bc105-173">Dopo aver completato i test e i casi di utilizzo aggiuntivi di interesse per l'azienda, è possibile procedere con l'aggiunta di utenti nel gruppo pilota iniziale.</span><span class="sxs-lookup"><span data-stu-id="bc105-173">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="bc105-174">**OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="bc105-174">**OneDrive for Business**</span></span>

<span data-ttu-id="bc105-175">Selezionare OneDrive dall'icona di avvio delle app di Microsoft 365 e verificare che si venga indirizzati automaticamente alla posizione geografica appropriata per l'utente, in base alla sua posizione dati preferita.</span><span class="sxs-lookup"><span data-stu-id="bc105-175">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="bc105-176">OneDrive for Business dovrebbe ora iniziare il provisioning in quella posizione.</span><span class="sxs-lookup"><span data-stu-id="bc105-176">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="bc105-177">Una volta effettuato il provisioning, provare a caricare e scaricare alcuni documenti.</span><span class="sxs-lookup"><span data-stu-id="bc105-177">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="bc105-178">**App OneDrive per dispositivi mobili**</span><span class="sxs-lookup"><span data-stu-id="bc105-178">**OneDrive Mobile App**</span></span>

<span data-ttu-id="bc105-179">Accedere all'app OneDrive per dispositivi mobili con le credenziali dell'account di test.</span><span class="sxs-lookup"><span data-stu-id="bc105-179">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="bc105-180">Verificare che sia possibile visualizzare i file di OneDrive for Business e di poterli usare dal dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="bc105-180">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="bc105-181">**Client di sincronizzazione di OneDrive**</span><span class="sxs-lookup"><span data-stu-id="bc105-181">**OneDrive sync client**</span></span>

<span data-ttu-id="bc105-p119">Confermare che il client di sincronizzazione di OneDrive rilevi automaticamente la posizione geografica di OneDrive for Business all'accesso. Se serve scaricare il client di sincronizzazione, è possibile fare clic su **Sincronizza** nella raccolta di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="bc105-p119">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login. If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="bc105-184">**Applicazioni di Office**</span><span class="sxs-lookup"><span data-stu-id="bc105-184">**Office applications**</span></span>

<span data-ttu-id="bc105-p120">Verificare di riuscire ad accedere a OneDrive for Business effettuando l'accesso da un'applicazione Office, come Word. Aprire l'applicazione Office e selezionare "OneDrive – <TenantName>". Office rileverà la posizione di OneDrive e mostrerà i file che possono essere aperti.</span><span class="sxs-lookup"><span data-stu-id="bc105-p120">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word. Open the Office application and select "OneDrive – <TenantName>". Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="bc105-188">**Condivisione**</span><span class="sxs-lookup"><span data-stu-id="bc105-188">**Sharing**</span></span>

<span data-ttu-id="bc105-p121">Provare a condividere i file di OneDrive. Verificare che lo strumento di selezione delle persone mostri tutti gli utenti online di SharePoint indipendentemente dalla loro posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="bc105-p121">Try sharing OneDrive files. Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>