---
title: Trasferire un sito di SharePoint in una posizione geografica diversa
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Scopri come spostare un sito SharePoint in una posizione geografica diversa all'interno dell'ambiente multi-geografico e comunicare le aspettative delle modifiche agli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a49098045dbce94ef1c474497b8da1b397ac0b0
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362355"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a><span data-ttu-id="145fa-103">Trasferire un sito di SharePoint in una posizione geografica diversa</span><span class="sxs-lookup"><span data-stu-id="145fa-103">Move a SharePoint site to a different geo location</span></span>

<span data-ttu-id="145fa-104">Con il trasferimento geografico dei siti di SharePoint, è possibile spostare siti di SharePoint in posizioni geografiche diverse all'interno del proprio ambiente multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="145fa-104">With SharePoint site geo move, you can move SharePoint sites to other geo locations within your multi-geo environment.</span></span>

<span data-ttu-id="145fa-105">È possibile trasferire da una posizione geografica a un'altra i tipi di siti seguenti:</span><span class="sxs-lookup"><span data-stu-id="145fa-105">The following types of site can be moved between geo locations:</span></span>

- <span data-ttu-id="145fa-106">Microsoft 365 Siti connessi a gruppi, inclusi quelli associati a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="145fa-106">Microsoft 365 Group-connected sites, including those associated with Microsoft Teams</span></span>
- <span data-ttu-id="145fa-107">Siti moderni non associati a gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="145fa-107">Modern sites without a Microsoft 365 Group association</span></span>
- <span data-ttu-id="145fa-108">Siti di SharePoint classici</span><span class="sxs-lookup"><span data-stu-id="145fa-108">Classic SharePoint sites</span></span>
- <span data-ttu-id="145fa-109">Siti di comunicazioni</span><span class="sxs-lookup"><span data-stu-id="145fa-109">Communication sites</span></span>

<span data-ttu-id="145fa-110">Per spostare un sito da una posizione geografica all'altra è necessario essere un amministratore globale o un amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="145fa-110">You must be a Global Administrator or SharePoint Administrator to move a site between geo locations.</span></span>

<span data-ttu-id="145fa-111">Durante il trasferimento geografico del sito di SharePoint esiste una finestra di sola lettura di circa 4-6 ore, in base al contenuto del sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-111">There is a read-only window during the SharePoint site geo move of approximately 4-6 hours, depending on site contents.</span></span>

## <a name="best-practices"></a><span data-ttu-id="145fa-112">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="145fa-112">Best practices</span></span>

- <span data-ttu-id="145fa-113">Provare a eseguire il trasferimento di un sito di SharePoint in un sito di test per acquisire familiarità con la procedura.</span><span class="sxs-lookup"><span data-stu-id="145fa-113">Try a SharePoint site move on a test site to get familiar with the procedure.</span></span>
- <span data-ttu-id="145fa-114">Verificare se il sito possa essere spostato prima di pianificare o eseguire lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="145fa-114">Validate whether the site can be moved prior to scheduling or performing the move.</span></span>
- <span data-ttu-id="145fa-115">Quando è possibile, pianificare i trasferimenti di siti tra posizioni geografiche al di fuori dell'orario di ufficio, per ridurre l'impatto sugli utenti.</span><span class="sxs-lookup"><span data-stu-id="145fa-115">When possible schedule cross-geo sites moves for outside business hours to reduce user impact.</span></span>
- <span data-ttu-id="145fa-116">Informare gli utenti interessati prima dello spostamento di siti.</span><span class="sxs-lookup"><span data-stu-id="145fa-116">Communicate with impacted users prior to the sites move.</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="145fa-117">Comunicazioni agli utenti</span><span class="sxs-lookup"><span data-stu-id="145fa-117">Communicating to your users</span></span>

<span data-ttu-id="145fa-118">Quando si trasferiscono siti di SharePoint in posizioni geografiche diverse, è importante comunicare cosa avverrà agli utenti del sito, o in generale a chiunque abbia la possibilità di modificare il sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-118">When moving SharePoint sites between geo locations, it's important to communicate to the sites' users (generally anyone with the ability to edit the site) what to expect.</span></span> <span data-ttu-id="145fa-119">Questo può aiutare a ridurre la confusione degli utenti e le conseguenti chiamate all'help desk.</span><span class="sxs-lookup"><span data-stu-id="145fa-119">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="145fa-120">Inviare un'e-mail agli utenti prima del trasferimento per fornire loro le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="145fa-120">Email your sites' users before the move and let them know the following information:</span></span>

- <span data-ttu-id="145fa-121">Quando si prevede di eseguire lo spostamento e la durata del processo</span><span class="sxs-lookup"><span data-stu-id="145fa-121">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="145fa-122">In quale posizione geografica si sta spostando il sito e l'URL per accedere alla nuova posizione</span><span class="sxs-lookup"><span data-stu-id="145fa-122">What geo location their site is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="145fa-123">L'indicazione di chiudere i file e non apportare modifiche durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-123">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="145fa-124">Le autorizzazioni di condivisione e sui file non cambieranno in seguito al trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-124">File permissions and sharing will not change because of the move.</span></span>
- <span data-ttu-id="145fa-125">Cosa aspettarsi dall'esperienza utente in ambiente multi-geografico</span><span class="sxs-lookup"><span data-stu-id="145fa-125">What to expect from the user experience in a multi-geo environment</span></span>

<span data-ttu-id="145fa-126">Assicurarsi di inviare agli utenti del sito un'e-mail nel momento in cui lo spostamento è stato completato correttamente informandoli della possibilità di riprendere a lavorare nei siti.</span><span class="sxs-lookup"><span data-stu-id="145fa-126">Be sure to send your sites' users an email when the move has successfully completed informing them that they can resume working on their sites.</span></span>

## <a name="scheduling-sharepoint-site-moves"></a><span data-ttu-id="145fa-127">Pianificazione dello spostamento di siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="145fa-127">Scheduling SharePoint site moves</span></span>

<span data-ttu-id="145fa-128">È possibile pianificare lo spostamenti di siti di SharePoint in anticipo (come descritto più avanti in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="145fa-128">You can schedule SharePoint site moves in advance (described later in this article).</span></span> <span data-ttu-id="145fa-129">Si possono pianificare gli spostamenti come segue:</span><span class="sxs-lookup"><span data-stu-id="145fa-129">You can schedule moves as follows:</span></span>

- <span data-ttu-id="145fa-130">È possibile pianificare fino a 4.000 spostamenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="145fa-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="145fa-131">Una volta iniziati gli spostamenti, è possibile pianificarne di nuovi, con un massimo di 4.000 spostamenti in sospeso in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="145fa-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>

<span data-ttu-id="145fa-132">Per pianificare lo spostamento geografico di un sito di SharePoint per un momento successivo, includere uno dei parametri seguenti quando si inizia lo spostamento:</span><span class="sxs-lookup"><span data-stu-id="145fa-132">To schedule a SharePoint site geo move for a later time, include one of the following parameters when you start the move:</span></span>

- <span data-ttu-id="145fa-133">`PreferredMoveBeginDate` - Il trasferimento inizierà probabilmente in questo orario specificato.</span><span class="sxs-lookup"><span data-stu-id="145fa-133">`PreferredMoveBeginDate` – The move will likely begin at this specified time.</span></span>
- <span data-ttu-id="145fa-134">`PreferredMoveEndDate` - Il trasferimento verrà probabilmente completato entro questo orario specificato, secondo il principio del best effort.</span><span class="sxs-lookup"><span data-stu-id="145fa-134">`PreferredMoveEndDate` – The move will likely be completed by this specified time, on a best effort basis.</span></span>

<span data-ttu-id="145fa-135">L'orario di entrambi i parametri deve essere specificato in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="145fa-135">Time must be specified in Coordinated Universal Time (UTC) for both parameters.</span></span>

## <a name="moving-the-site"></a><span data-ttu-id="145fa-136">Trasferimento del sito</span><span class="sxs-lookup"><span data-stu-id="145fa-136">Moving the site</span></span>

<span data-ttu-id="145fa-137">Per il trasferimento geografico di siti di SharePoint è necessario connettersi ed eseguire l'operazione dall'URL di amministrazione di SharePoint nella posizione geografica in cui è ubicato il sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-137">SharePoint site geo move requires that you connect and perform the move from the SharePoint Admin URL in the geo location where the site is.</span></span>

<span data-ttu-id="145fa-138">Ad esempio, se l'URL del sito <https://contosohealthcare.sharepoint.com/sites/Turbines> è , connettersi all'URL SharePoint admin all'indirizzo <https://contosohealthcare-admin.sharepoint.com> :</span><span class="sxs-lookup"><span data-stu-id="145fa-138">For example, if the site URL is <https://contosohealthcare.sharepoint.com/sites/Turbines>, connect to the SharePoint Admin URL at <https://contosohealthcare-admin.sharepoint.com>:</span></span>

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Finestra di Online Management Shell che mostra il Connect-SPOService comando](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a><span data-ttu-id="145fa-140">Convalida dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="145fa-140">Validating the environment</span></span>

<span data-ttu-id="145fa-141">Prima di pianificare il trasferimento di un sito, è consigliabile eseguire una convalida per assicurarsi che il sito possa essere spostato.</span><span class="sxs-lookup"><span data-stu-id="145fa-141">We recommend that before scheduling any site move, you perform a validation to ensure that the site can be moved.</span></span>

<span data-ttu-id="145fa-142">Non è supportato il trasferimento di siti con:</span><span class="sxs-lookup"><span data-stu-id="145fa-142">We do not support moving sites with:</span></span>

- <span data-ttu-id="145fa-143">Servizi di integrazione applicativa</span><span class="sxs-lookup"><span data-stu-id="145fa-143">Business Connectivity Services</span></span>
- <span data-ttu-id="145fa-144">Moduli di InfoPath</span><span class="sxs-lookup"><span data-stu-id="145fa-144">InfoPath forms</span></span>
- <span data-ttu-id="145fa-145">Modelli applicati di Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="145fa-145">Information Rights Management (IRM) templates applied</span></span>

<span data-ttu-id="145fa-146">Per assicurarsi che tutte le posizioni geografiche siano compatibili, eseguire `Get-SPOGeoMoveCrossCompatibilityStatus`.</span><span class="sxs-lookup"><span data-stu-id="145fa-146">To ensure all geo locations are compatible, run `Get-SPOGeoMoveCrossCompatibilityStatus`.</span></span> <span data-ttu-id="145fa-147">Verranno mostrate tutte le posizioni geografiche e verrà indicato se l'ambiente è compatibile con la posizione geografica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="145fa-147">This will display all your geo locations and whether the environment is compatible with the destination geo location.</span></span>

<span data-ttu-id="145fa-148">Per eseguire un controllo di sola convalida nel sito, usare `Start-SPOSiteContentMove` con il parametro `-ValidationOnly` per verificare se il sito può essere trasferito.</span><span class="sxs-lookup"><span data-stu-id="145fa-148">To perform a validation-only check on your site, use `Start-SPOSiteContentMove` with the `-ValidationOnly` parameter to validate if the site is able to be moved.</span></span> <span data-ttu-id="145fa-149">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="145fa-149">For example:</span></span>

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

<span data-ttu-id="145fa-150">Verrà restituito *Success* se il sito è pronto per il trasferimento oppure *Fail* se sono presenti condizioni di blocco.</span><span class="sxs-lookup"><span data-stu-id="145fa-150">This will return *Success* if the site is ready to be moved or *Fail* if any of blocked conditions are present.</span></span>

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a><span data-ttu-id="145fa-151">Avviare lo spostamento geografico di un sito di SharePoint non associato a gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="145fa-151">Start a SharePoint site geo move for a site with no associated Microsoft 365 Group</span></span>

<span data-ttu-id="145fa-152">Per impostazione predefinita, l'URL iniziale del sito diventerà l'URL della posizione geografica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="145fa-152">By default, initial URL for the site will change to the URL of the destination geo location.</span></span> <span data-ttu-id="145fa-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="145fa-153">For example:</span></span>

<span data-ttu-id="145fa-154">Da <https://Contoso.sharepoint.com/sites/projectx> a <https://ContosoEUR.sharepoint.com/sites/projectx></span><span class="sxs-lookup"><span data-stu-id="145fa-154"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projectx></span></span>

<span data-ttu-id="145fa-155">Per i siti privi di associazioni a gruppi di Microsoft 365, è anche possibile rinominare il sito usando il parametro `-DestinationUrl`.</span><span class="sxs-lookup"><span data-stu-id="145fa-155">For sites with no Microsoft 365 Group association, you can also rename the site by using the `-DestinationUrl` parameter.</span></span> <span data-ttu-id="145fa-156">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="145fa-156">For example:</span></span>

<span data-ttu-id="145fa-157">Da <https://Contoso.sharepoint.com/sites/projectx> a <https://ContosoEUR.sharepoint.com/sites/projecty></span><span class="sxs-lookup"><span data-stu-id="145fa-157"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projecty></span></span>

<span data-ttu-id="145fa-158">Per avviare il trasferimento del sito, eseguire:</span><span class="sxs-lookup"><span data-stu-id="145fa-158">To start the site move, run:</span></span>

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Screenshot della finestra di PowerShell con il cmdlet Start-SPOSiteContentMove](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a><span data-ttu-id="145fa-160">Avviare lo spostamento geografico di un sito di SharePoint a un sito connesso a un gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="145fa-160">Start a SharePoint site geo move for a Microsoft 365 Group-connected site</span></span>

<span data-ttu-id="145fa-161">Per trasferire un sito connesso a un gruppo di Office 365, l'amministratore globale o l’amministratore di SharePoint deve prima di tutto modificare l'attributo relativo alla posizione preferita dei dati per il gruppo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="145fa-161">To move an Office 365 Group-connected site, the Global Administrator or SharePoint Administrator must first change the Preferred Data Location (PDL) attribute for the Office 365 Group.</span></span>

<span data-ttu-id="145fa-162">Per impostare la posizione preferita dei dati per un gruppo di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="145fa-162">To set the PDL for a Microsoft 365 Group:</span></span>

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

<span data-ttu-id="145fa-163">Dopo aver aggiornato il PDL, è possibile avviare il trasferimento del sito:</span><span class="sxs-lookup"><span data-stu-id="145fa-163">Once you have updated the PDL, you can start the site move:</span></span>

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a><span data-ttu-id="145fa-164">Annullare il trasferimento geografico di un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="145fa-164">Cancel a SharePoint site geo move</span></span>

<span data-ttu-id="145fa-165">È possibile interrompere il trasferimento geografico di un sito di SharePoint, purché non sia in corso o non sia stato completato usando il cmdlet `Stop-SPOSiteContentMove`.</span><span class="sxs-lookup"><span data-stu-id="145fa-165">You can stop a SharePoint site geo move, provided the move is not in progress or completed by using the `Stop-SPOSiteContentMove` cmdlet.</span></span>

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a><span data-ttu-id="145fa-166">Determinazione dello stato del trasferimento geografico di un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="145fa-166">Determining the status of a SharePoint site geo move</span></span>

<span data-ttu-id="145fa-167">È possibile determinare lo stato di un trasferimento di sito da o verso la posizione geografica a cui si è connessi con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="145fa-167">You can determine the status of a site move in our out of the geo that you are connected to by using the following cmdlets:</span></span>

- <span data-ttu-id="145fa-168">[Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (siti non connessi a gruppi)</span><span class="sxs-lookup"><span data-stu-id="145fa-168">[Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (non-Group-connected sites)</span></span>
- <span data-ttu-id="145fa-169">[Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (siti connessi a gruppi)</span><span class="sxs-lookup"><span data-stu-id="145fa-169">[Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (Group-connected sites)</span></span>

<span data-ttu-id="145fa-170">Usare il parametro `-SourceSiteUrl` per specificare il sito di cui si vuole vedere lo stato di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-170">Use the `-SourceSiteUrl` parameter to specify the site for which you want to see move status.</span></span>

<span data-ttu-id="145fa-171">Gli stati di trasferimento sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="145fa-171">The move statuses are described in the following table.</span></span>

****

|<span data-ttu-id="145fa-172">Stato</span><span class="sxs-lookup"><span data-stu-id="145fa-172">Status</span></span>|<span data-ttu-id="145fa-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="145fa-173">Description</span></span>|
|---|---|
|<span data-ttu-id="145fa-174">Ready to Trigger</span><span class="sxs-lookup"><span data-stu-id="145fa-174">Ready to Trigger</span></span>|<span data-ttu-id="145fa-175">Lo spostamento non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="145fa-175">The move has not started.</span></span>|
|<span data-ttu-id="145fa-176">Scheduled</span><span class="sxs-lookup"><span data-stu-id="145fa-176">Scheduled</span></span>|<span data-ttu-id="145fa-177">Lo spostamento è in coda, ma non è ancora iniziato.</span><span class="sxs-lookup"><span data-stu-id="145fa-177">The move is in queue but has not yet started.</span></span>|
|<span data-ttu-id="145fa-178">InProgress (n/4)</span><span class="sxs-lookup"><span data-stu-id="145fa-178">InProgress (n/4)</span></span>|<span data-ttu-id="145fa-179">Lo spostamento è in corso in uno dei seguenti stati: Convalida (1/4), Backup (2/4), Ripristino 3/4, Pulizia (4/4).</span><span class="sxs-lookup"><span data-stu-id="145fa-179">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span>|
|<span data-ttu-id="145fa-180">Success</span><span class="sxs-lookup"><span data-stu-id="145fa-180">Success</span></span>|<span data-ttu-id="145fa-181">Lo spostamento è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="145fa-181">The move has completed successfully.</span></span>|
|<span data-ttu-id="145fa-182">Failed</span><span class="sxs-lookup"><span data-stu-id="145fa-182">Failed</span></span>|<span data-ttu-id="145fa-183">Lo spostamento non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="145fa-183">The move failed.</span></span>|
|

<span data-ttu-id="145fa-184">È anche possibile applicare l'opzione `-Verbose` per vedere informazioni aggiuntive sul trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-184">You can also apply the `-Verbose` option to see additional information about the move.</span></span>

## <a name="user-experience"></a><span data-ttu-id="145fa-185">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="145fa-185">User experience</span></span>

<span data-ttu-id="145fa-186">Gli utenti del sito dovrebbero riscontrare un'interruzione minima del servizio durante il trasferimento in un'altra posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="145fa-186">Site users should notice minimal disruption when their site is moved to a different geo location.</span></span> <span data-ttu-id="145fa-187">A parte un breve periodo di disponibilità in sola lettura, i collegamenti e le autorizzazioni esistenti continueranno a funzionare come previsto al termine del trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-187">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="site"></a><span data-ttu-id="145fa-188">Sito</span><span class="sxs-lookup"><span data-stu-id="145fa-188">Site</span></span>

<span data-ttu-id="145fa-189">Durante il trasferimento, il sito viene impostato come di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="145fa-189">While the move is in progress the site is set to read-only.</span></span> <span data-ttu-id="145fa-190">Al termine dello spostamento, l'utente viene indirizzato al nuovo sito nella nuova posizione geografica non fa clic su segnalibri o altri collegamenti al sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-190">Once the move is completed, the user is directed to the new site in the new geo location when they click on bookmarks or other links to the site.</span></span>

### <a name="permissions"></a><span data-ttu-id="145fa-191">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="145fa-191">Permissions</span></span>

<span data-ttu-id="145fa-192">Gli utenti con autorizzazioni per il sito continueranno ad avere accesso al contenuto durante il trasferimento e dopo il suo completamento.</span><span class="sxs-lookup"><span data-stu-id="145fa-192">Users with permissions to site will continue to have access to the site during the move and after it's complete.</span></span>

### <a name="sync-app"></a><span data-ttu-id="145fa-193">App di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="145fa-193">Sync app</span></span>

<span data-ttu-id="145fa-194">L'app di sincronizzazione rileva e trasferisce automaticamente la sincronizzazione nella nuova posizione del sito al termine dello spostamento del sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-194">The sync app will automatically detect and seamlessly transfer syncing to the new site location once the site move is complete.</span></span> <span data-ttu-id="145fa-195">L'utente non deve accedere di nuovo o eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="145fa-195">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="145fa-196">È necessaria la versione 17.3.6943.0625 o successiva dell'app di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="145fa-196">(Version 17.3.6943.0625 or later of the sync app required.)</span></span>

<span data-ttu-id="145fa-197">Se un utente aggiorna un file mentre lo spostamento è in corso, l'app di sincronizzazione informerà l'utente che i caricamenti di file sono in sospeso mentre lo spostamento è in corso.</span><span class="sxs-lookup"><span data-stu-id="145fa-197">If a user updates a file while the move is in progress, the sync app will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="145fa-198">Condivisione dei collegamenti</span><span class="sxs-lookup"><span data-stu-id="145fa-198">Sharing links</span></span>

<span data-ttu-id="145fa-199">Una volta completato il trasferimento geografico del sito di SharePoint, i collegamenti condivisi esistenti dei file spostati reindirizzeranno automaticamente alla nuova posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="145fa-199">When the SharePoint site geo move completes, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="most-recently-used-files-in-office-mru"></a><span data-ttu-id="145fa-200">File usati di recente in Office (MRU)</span><span class="sxs-lookup"><span data-stu-id="145fa-200">Most Recently Used files in Office (MRU)</span></span>

<span data-ttu-id="145fa-201">Il servizio MRU viene aggiornato con l'URL del sito e gli URL del contenuto una volta completato il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-201">The MRU service is updated with the site url and its content URLs once the move completes.</span></span> <span data-ttu-id="145fa-202">Questo si applica a Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="145fa-202">This applies to Word, Excel, and PowerPoint.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="145fa-203">Esperienza con OneNote</span><span class="sxs-lookup"><span data-stu-id="145fa-203">OneNote experience</span></span>

<span data-ttu-id="145fa-204">Il client win32 di OneNote e l'app UWP (Universal Windows Platform) rileveranno e sincronizzeranno automaticamente i blocchi appunti nella nuova posizione del sito al termine del trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-204">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new site location once site move is complete.</span></span> <span data-ttu-id="145fa-205">L'utente non deve accedere di nuovo o eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="145fa-205">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="145fa-206">L'unico indicatore visibile all'utente viene mostrato in caso di sincronizzazione non riuscita del blocco appunti durante lo spostamento del sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-206">The only visible indicator to the user is notebook sync would fail when site move is in progress.</span></span> <span data-ttu-id="145fa-207">Questa esperienza è disponibile nelle versioni del client di OneNote seguenti:</span><span class="sxs-lookup"><span data-stu-id="145fa-207">This experience is available on the following OneNote client versions:</span></span>

- <span data-ttu-id="145fa-208">OneNote win32 – Versione 16.0.8326.2096 (e successive)</span><span class="sxs-lookup"><span data-stu-id="145fa-208">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>
- <span data-ttu-id="145fa-209">OneNote UWP – Versione 16.0.8431.1006 (e successive)</span><span class="sxs-lookup"><span data-stu-id="145fa-209">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>
- <span data-ttu-id="145fa-210">OneNote Mobile App – Versione 16.0.8431.1011 (e successive)</span><span class="sxs-lookup"><span data-stu-id="145fa-210">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a><span data-ttu-id="145fa-211">Teams (applicabile ai siti connessi a gruppi di Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="145fa-211">Teams (applicable to Microsoft 365 Group connected sites)</span></span>

<span data-ttu-id="145fa-212">Al termine dello spostamento geografico del sito di SharePoint, gli utenti avranno accesso ai propri file nel sito del gruppo di Microsoft 365 nell'app Teams.</span><span class="sxs-lookup"><span data-stu-id="145fa-212">When the SharePoint site geo move completes, users will have access to their Microsoft 365 Group site files on the Teams app.</span></span> <span data-ttu-id="145fa-213">Inoltre, i file condivisi tramite la chat di Teams dal proprio sito prima del trasferimento geografico continueranno a funzionare anche dopo il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-213">Additionally, files shared via Teams chat from their site prior to geo move will continue to work after move is complete.</span></span>

### <a name="sharepoint-mobile-app-iosandroid"></a><span data-ttu-id="145fa-214">App SharePoint per dispositivi mobili (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="145fa-214">SharePoint Mobile App (iOS/Android)</span></span>

<span data-ttu-id="145fa-215">L'app SharePoint per dispositivi mobili supporta l'uso di posizioni geografiche diverse ed è in grado di rilevare il trasferimento geografico del sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-215">The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.</span></span>

### <a name="sharepoint-workflows"></a><span data-ttu-id="145fa-216">Flussi di lavoro di SharePoint</span><span class="sxs-lookup"><span data-stu-id="145fa-216">SharePoint workflows</span></span>

<span data-ttu-id="145fa-217">È necessario ripubblicare i flussi di lavoro di SharePoint 2013 dopo il trasferimento del sito.</span><span class="sxs-lookup"><span data-stu-id="145fa-217">SharePoint 2013 workflows need to be republished after the site move.</span></span> <span data-ttu-id="145fa-218">I flussi di lavoro di SharePoint 2010 continueranno a funzionare normalmente.</span><span class="sxs-lookup"><span data-stu-id="145fa-218">SharePoint 2010 workflows should continue to function normally.</span></span>

### <a name="apps"></a><span data-ttu-id="145fa-219">App</span><span class="sxs-lookup"><span data-stu-id="145fa-219">Apps</span></span>

<span data-ttu-id="145fa-220">Se si sposta un sito con le app, è necessario creare nuovamente un'istanza dell'app nella nuova posizione geografica, perché l'app e le relative connessioni potrebbero non essere disponibili nella posizione geografica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="145fa-220">If you are moving a site with apps, you must re-instantiate the app in the site's new geo location as the app and its connections may not be available in the destination geo location.</span></span>

### <a name="flow"></a><span data-ttu-id="145fa-221">Flow</span><span class="sxs-lookup"><span data-stu-id="145fa-221">Flow</span></span>

<span data-ttu-id="145fa-222">Nella maggior parte dei casi, i flussi continueranno a funzionare dopo il trasferimento geografico di un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="145fa-222">In most cases Flows will continue to work after a SharePoint site geo move.</span></span> <span data-ttu-id="145fa-223">È consigliabile testarli una volta completato il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="145fa-223">We recommend that you test them once the move has completed.</span></span>

### <a name="powerapps"></a><span data-ttu-id="145fa-224">PowerApps</span><span class="sxs-lookup"><span data-stu-id="145fa-224">PowerApps</span></span>

<span data-ttu-id="145fa-225">Le PowerApp devono essere ricreate nella posizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="145fa-225">PowerApps need to be recreated in the destination location.</span></span>

### <a name="data-movement-between-geo-locations"></a><span data-ttu-id="145fa-226">Spostamento di dati tra posizioni geografiche</span><span class="sxs-lookup"><span data-stu-id="145fa-226">Data movement between geo locations</span></span>

<span data-ttu-id="145fa-227">SharePoint usa l'archiviazione BLOB di Azure per il contenuto, mentre i metadati associati ai siti e i file sono archiviati in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="145fa-227">SharePoint uses Azure Blob storage for its content, while the metadata associated with sites and its files is stored within SharePoint.</span></span> <span data-ttu-id="145fa-228">Dopo il trasferimento del sito dalla posizione geografica di origine a quella di destinazione, il servizio sposterà anche l'archivio BLOB associato.</span><span class="sxs-lookup"><span data-stu-id="145fa-228">After the site is moved from its source geo location to its destination geo location, the service will also move its associated Blob Storage.</span></span> <span data-ttu-id="145fa-229">Gli spostamenti degli archivi BLOB vengono completati in circa 40 giorni.</span><span class="sxs-lookup"><span data-stu-id="145fa-229">Blob Storage moves complete in approximately 40 days.</span></span>