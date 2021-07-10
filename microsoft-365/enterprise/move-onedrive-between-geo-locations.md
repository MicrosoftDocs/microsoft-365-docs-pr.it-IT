---
title: Spostare un sito OneDrive in un'altra posizione geografica
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Informazioni sullo spostamento di un OneDrive in una posizione geografica diversa, inclusa la pianificazione degli spostamenti del sito e la comunicazione delle aspettative agli utenti.
ms.openlocfilehash: 9e75c8e4102f82d4ab6e0f99ea26e1c0ad8b4bab
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362247"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="3f478-103">Spostare un sito OneDrive in un'altra posizione geografica</span><span class="sxs-lookup"><span data-stu-id="3f478-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="3f478-104">Con OneDrive geo, puoi spostare la posizione geografica di un OneDrive utente in una posizione geografica diversa.</span><span class="sxs-lookup"><span data-stu-id="3f478-104">With OneDrive geo move, you can move a user's OneDrive to a different geo location.</span></span> <span data-ttu-id="3f478-105">OneDrive lo spostamento geografico viene eseguito dall'amministratore di SharePoint Online o dall Microsoft 365 amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="3f478-105">OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator.</span></span> <span data-ttu-id="3f478-106">Prima di avviare un OneDrive geografico, assicurati di informare l'utente il cui OneDrive viene spostato e consiglia di chiudere tutti i file per tutta la durata dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="3f478-106">Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move.</span></span> <span data-ttu-id="3f478-107">Se l'utente ha aperto un documento utilizzando il client Office durante lo spostamento, al termine dello spostamento il documento dovrà essere salvato nel nuovo percorso. Lo spostamento può essere pianificato per un'ora futura, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="3f478-107">(If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="3f478-108">Il servizio OneDrive usa i blob di Azure Archiviazione per archiviare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="3f478-108">The OneDrive service uses Azure Blob Storage to store content.</span></span> <span data-ttu-id="3f478-109">Il Archiviazione BLOB associato al OneDrive dell'utente verrà spostato dall'origine alla posizione geografica di destinazione entro 40 giorni dalla disponibilità dell'OneDrive di destinazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3f478-109">The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user.</span></span> <span data-ttu-id="3f478-110">L'accesso al OneDrive dell'utente verrà ripristinato non appena sarà disponibile OneDrive destinazione.</span><span class="sxs-lookup"><span data-stu-id="3f478-110">The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="3f478-111">Durante OneDrive finestra di spostamento geografico (circa 2-6 ore) la OneDrive dell'utente è impostata su sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3f478-111">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="3f478-112">L'utente può comunque accedere ai propri file tramite l'app sincronizzazione OneDrive o il sito OneDrive in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3f478-112">The user can still access their files via the OneDrive sync app or their OneDrive site in SharePoint Online.</span></span> <span data-ttu-id="3f478-113">Dopo OneDrive spostamento geografico, l'utente verrà automaticamente connesso al proprio OneDrive nella posizione geografica di destinazione quando accede a OneDrive nell'icona di avvio delle app Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f478-113">After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher.</span></span> <span data-ttu-id="3f478-114">L'app di sincronizzazione inizierà automaticamente la sincronizzazione dalla nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="3f478-114">The sync app will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="3f478-115">Le procedure descritte in questo articolo richiedono il [modulo PowerShell di Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="3f478-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="3f478-116">Disposizioni agli utenti</span><span class="sxs-lookup"><span data-stu-id="3f478-116">Communicating to your users</span></span>

<span data-ttu-id="3f478-p104">Quando si effettua lo spostamento dei siti di OneDrive tra le posizioni geografiche, è importante comunicare agli utenti cosa aspettarsi. Questo può aiutare a ridurre la confusione degli utenti e le conseguenti chiamate all'help desk. Inviare una email agli utenti prima dello spostamento per fornire loro le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="3f478-p104">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect. This can help reduce user confusion and calls to your help desk. Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="3f478-120">Quando si prevede di effettuare lo spostamento e la durata del processo</span><span class="sxs-lookup"><span data-stu-id="3f478-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="3f478-121">Verso quale posizione geografica si sta spostando OneDrive e l'URL per accedere alla nuova posizione</span><span class="sxs-lookup"><span data-stu-id="3f478-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="3f478-122">Evitare di chiudere i file e apportare modifiche durante lo spostamento</span><span class="sxs-lookup"><span data-stu-id="3f478-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="3f478-123">Le autorizzazioni e la condivisione dei file non cambieranno in seguito allo spostamento</span><span class="sxs-lookup"><span data-stu-id="3f478-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="3f478-124">Cosa aspettarsi dall'[esperienza utente in ambiente multi-geografico](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="3f478-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="3f478-125">È necessario inviare agli utenti un'email nel momento in cui lo spostamento è stato completato correttamente informandoli della possibilità di riprendere a lavorare in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3f478-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="3f478-126">Pianificazione degli spostamenti dei siti di OneDrive</span><span class="sxs-lookup"><span data-stu-id="3f478-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="3f478-p105">È possibile pianificare gli spostamenti dei siti di OneDrive in anticipo (come descritto più avanti in questo articolo). È consigliabile iniziare con un numero limitato di utenti per convalidare i flussi di lavoro e le strategie di comunicazione. Una volta acquisita familiarità con la procedura, è possibile pianificare gli spostamenti nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3f478-p105">You can schedule OneDrive site moves in advance (described later in this article). We recommend that you start with a small number of users to validate your workflows and communication strategies. Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="3f478-130">È possibile pianificare fino a 4.000 spostamenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="3f478-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="3f478-131">Una volta iniziati gli spostamenti, è possibile pianificarne di nuovi, con un massimo di 4.000 spostamenti in sospeso in coda in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3f478-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="3f478-132">Le dimensioni massime di OneDrive che consentono lo spostamento sono 1 TB (1 TB).</span><span class="sxs-lookup"><span data-stu-id="3f478-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="3f478-133">Spostamento di un sito OneDrive</span><span class="sxs-lookup"><span data-stu-id="3f478-133">Moving a OneDrive site</span></span>

<span data-ttu-id="3f478-134">Per eseguire un OneDrive geografico, l'amministratore tenant deve innanzitutto impostare la posizione geografica preferita dell'utente sulla posizione geografica appropriata.</span><span class="sxs-lookup"><span data-stu-id="3f478-134">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location.</span></span> <span data-ttu-id="3f478-135">Dopo aver impostato il file PDL, attendere almeno 24 ore per la sincronizzazione dell'aggiornamento PDL tra le posizioni geografiche prima di avviare lo spostamento OneDrive geo.</span><span class="sxs-lookup"><span data-stu-id="3f478-135">Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="3f478-136">Quando si utilizzano i cmdlet di spostamento geografico, connettersi al servizio SpO nella posizione geografica OneDrive corrente dell'utente, utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3f478-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="3f478-137">Ad esempio: per spostare OneDrive'utente "Matt@contosoenergy.onmicrosoft.com", connettersi all'interfaccia di amministrazione di EUR SharePoint in quanto l'OneDrive dell'utente si trova nella posizione geografica EUR:</span><span class="sxs-lookup"><span data-stu-id="3f478-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Screenshot della finestra di PowerShell con il cmdlet connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="3f478-139">Convalida dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="3f478-139">Validating the environment</span></span>

<span data-ttu-id="3f478-140">Prima di iniziare uno spostamento geografico di OneDrive, consigliamo di convalidare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="3f478-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="3f478-141">Per assicurarsi che tutte le posizioni geografiche siano compatibili, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3f478-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="3f478-142">Verrà visualizzato un elenco delle posizioni geografiche e, se lo spostamento del contenuto tra tali posizioni è consentito, verrà visualizzata la dicitura "Compatibile".</span><span class="sxs-lookup"><span data-stu-id="3f478-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="3f478-143">Se il comando restituisce "Incompatibile", provare a ripetere la convalida dello stato in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3f478-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="3f478-144">Se ad esempio un sito OneDrive contiene un sito secondario, non può essere spostato.</span><span class="sxs-lookup"><span data-stu-id="3f478-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="3f478-145">È possibile utilizzare il cmdlet Start-SPOUserAndContentMove con il parametro -ValidationOnly per verificare che OneDrive possa essere spostato:</span><span class="sxs-lookup"><span data-stu-id="3f478-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="3f478-p109">Se OneDrive può essere spostato verrà restituito il valore Success, altrimenti verrà restituito il valore Fail in caso di blocco a fini giudiziari o di un sito secondario che impedisce lo spostamento. Dopo aver verificato che OneDrive può essere spostato, è possibile avviare lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="3f478-p109">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move. Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="3f478-148">Avviare lo spostamento geografica di OneDrive</span><span class="sxs-lookup"><span data-stu-id="3f478-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="3f478-149">Per avviare lo spostamento, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3f478-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="3f478-150">Con questi parametri:</span><span class="sxs-lookup"><span data-stu-id="3f478-150">Using these parameters:</span></span>

-   <span data-ttu-id="3f478-151">_UserPrincipalName_ – UPN dell'utente il cui OneDrive viene spostato.</span><span class="sxs-lookup"><span data-stu-id="3f478-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="3f478-152">_DestinationDataLocation:_ Geo-Location in cui è necessario spostare OneDrive'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3f478-152">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved.</span></span> <span data-ttu-id="3f478-153">Deve essere uguale alla posizione dati preferita dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3f478-153">This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="3f478-154">Ad esempio, per spostare OneDrive di matt@contosoenergy.onmicrosoft.com da EUR a AUS, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3f478-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Screenshot della finestra di PowerShell con il cmdlet Start-SPOUserAndContentMove](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="3f478-156">Per pianificare lo spostamento geografica in un secondo momento, utilizzare uno dei parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f478-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="3f478-p111">_PreferredMoveBeginDate_ – Lo spostamento probabilmente inizierà a un orario specifico. L'ora deve essere specificata in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="3f478-p111">_PreferredMoveBeginDate_ – The move will likely begin at this specified time. Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="3f478-p112">_PreferredMoveEndDate_ – Lo spostamento probabilmente finirà entro un orario specifico, sulla base del best effort. L'ora deve essere specificata in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="3f478-p112">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis. Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="3f478-161">Annullare uno spostamento geografico di OneDrive</span><span class="sxs-lookup"><span data-stu-id="3f478-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="3f478-162">È possibile interrompere lo spostamento geografico dell'OneDrive utente, purché lo spostamento non sia in corso o completato utilizzando il cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3f478-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="3f478-163">Dove _UserPrincipalName_ è il nome dell'entità utente (UPN) dell'utente titolare del OneDrive di cui si desidera interrompere lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="3f478-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="3f478-164">Determinare lo stato corrente</span><span class="sxs-lookup"><span data-stu-id="3f478-164">Determining current status</span></span>

<span data-ttu-id="3f478-165">È possibile controllare lo stato di un OneDrive geo in o fuori dalla posizione geografica a cui si è connessi utilizzando il cmdlet Get-SPOUserAndContentMoveState.</span><span class="sxs-lookup"><span data-stu-id="3f478-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="3f478-166">Gli stati di trasferimento sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3f478-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f478-167">Stato</span><span class="sxs-lookup"><span data-stu-id="3f478-167">Status</span></span></th>
<th align="left"><span data-ttu-id="3f478-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f478-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="3f478-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="3f478-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="3f478-170">Lo spostamento non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="3f478-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3f478-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="3f478-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="3f478-172">Lo spostamento è in corso in uno dei seguenti stati: Convalida (1/4), Backup (2/4), Ripristino 3/4, Pulizia (4/4).</span><span class="sxs-lookup"><span data-stu-id="3f478-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3f478-173">Success</span><span class="sxs-lookup"><span data-stu-id="3f478-173">Success</span></span></td>
<td align="left"><span data-ttu-id="3f478-174">Lo spostamento è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3f478-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3f478-175">Failed</span><span class="sxs-lookup"><span data-stu-id="3f478-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="3f478-176">Lo spostamento non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="3f478-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3f478-177">Per trovare lo stato dello spostamento di un utente specifico, utilizzare il parametro UserPrincipalName:</span><span class="sxs-lookup"><span data-stu-id="3f478-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="3f478-178">Per trovare lo stato di tutti gli spostamenti in ingresso o in uscita dalla posizione geografica a cui si è connessi, utilizzare il parametro MoveState con uno dei valori seguenti: NotStarted, InProgress, Success, Failed, All.</span><span class="sxs-lookup"><span data-stu-id="3f478-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="3f478-179">È anche possibile aggiungere il parametro `-Verbose` per descrizioni più dettagliate dello stato di spostamento.</span><span class="sxs-lookup"><span data-stu-id="3f478-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="3f478-180">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="3f478-180">User Experience</span></span>

<span data-ttu-id="3f478-p113">Gli utenti di OneDrive dovrebbero riscontrare un'interruzione minima del proprio OneDrive durante lo spostamento a un'altra posizione geografica. A parte un breve periodo di disponibilità in sola lettura di OneDrive, i collegamenti e le autorizzazioni esistenti continueranno a funzionare come previsto al termine dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="3f478-p113">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location. Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="users-onedrive"></a><span data-ttu-id="3f478-183">Informazioni dell'OneDrive</span><span class="sxs-lookup"><span data-stu-id="3f478-183">User's OneDrive</span></span>

<span data-ttu-id="3f478-184">Mentre lo spostamento è in corso, la OneDrive dell'utente è impostata su sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3f478-184">While the move is in progress the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="3f478-185">Una volta completato lo spostamento, l'utente viene indirizzato al OneDrive nella nuova posizione geografica quando passa OneDrive'icona di avvio delle app di Microsoft 365 o a un Web browser.</span><span class="sxs-lookup"><span data-stu-id="3f478-185">Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="3f478-186">Autorizzazioni per il contenuto di OneDrive</span><span class="sxs-lookup"><span data-stu-id="3f478-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="3f478-187">Gli utenti con autorizzazioni OneDrive contenuto continueranno ad avere accesso al contenuto durante lo spostamento e dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="3f478-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-app"></a><span data-ttu-id="3f478-188">sincronizzazione OneDrive app</span><span class="sxs-lookup"><span data-stu-id="3f478-188">OneDrive sync app</span></span> 

<span data-ttu-id="3f478-189">L sincronizzazione OneDrive app rileverà automaticamente e trasferirà senza problemi la sincronizzazione nella nuova posizione OneDrive una volta completato OneDrive spostamento geografico.</span><span class="sxs-lookup"><span data-stu-id="3f478-189">The OneDrive sync app will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete.</span></span> <span data-ttu-id="3f478-190">L'utente non deve eseguire di nuovo l'accesso o eseguire altre azioni.</span><span class="sxs-lookup"><span data-stu-id="3f478-190">The user does not need to sign-in again or take any other action.</span></span>  <span data-ttu-id="3f478-191">È necessaria la versione 17.3.6943.0625 o successiva dell'app di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f478-191">(Version 17.3.6943.0625 or later of the sync app required.)</span></span>

<span data-ttu-id="3f478-192">Se un utente aggiorna un file mentre è OneDrive lo spostamento geografico, l'app di sincronizzazione informerà l'utente che i caricamenti di file sono in sospeso mentre lo spostamento è in corso.</span><span class="sxs-lookup"><span data-stu-id="3f478-192">If a user updates a file while the OneDrive geo move is in progress, the sync app will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="3f478-193">Condivisione dei collegamenti</span><span class="sxs-lookup"><span data-stu-id="3f478-193">Sharing links</span></span> 

<span data-ttu-id="3f478-194">Al completamento dello spostamento geografico di OneDrive, i collegamenti condivisi esistenti dei file spostati verranno reindirizzati automaticamente alla nuova posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="3f478-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="3f478-195">Esperienza con OneNote</span><span class="sxs-lookup"><span data-stu-id="3f478-195">OneNote Experience</span></span> 

<span data-ttu-id="3f478-p116">Il client win32 di OneNote e l'app UWP (Universal Windows Platform) rileveranno automaticamente e sincronizzeranno facilmente i blocchi appunti nella nuova posizione di OneDrive al termine dello spostamento geografico. L'utente non deve accedere di nuovo o eseguire altre operazioni. L'unico indicatore visibile all'utente viene visualizzato in caso di sincronizzazione non riuscita del blocco appunti durante lo spostamento geografico di OneDrive. Questa esperienza è disponibile nelle seguenti versioni client di OneNote:</span><span class="sxs-lookup"><span data-stu-id="3f478-p116">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete. The user does not need to sign-in again or take any other action. The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress. This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="3f478-200">OneNote win32 – Versione 16.0.8326.2096 (e successive)</span><span class="sxs-lookup"><span data-stu-id="3f478-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="3f478-201">OneNote UWP – Versione 16.0.8431.1006 (e successive)</span><span class="sxs-lookup"><span data-stu-id="3f478-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="3f478-202">OneNote Mobile App – Versione 16.0.8431.1011 (e successive)</span><span class="sxs-lookup"><span data-stu-id="3f478-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="3f478-203">App Teams</span><span class="sxs-lookup"><span data-stu-id="3f478-203">Teams app</span></span>

<span data-ttu-id="3f478-p117">Al completamento dello spostamento geografico di OneDrive, gli utenti avranno accesso ai propri file di OneDrive nell'app Teams. Inoltre, i file condivisi tramite la chat di Teams dal proprio OneDrive, prima dello spostamento geografico, continueranno a funzionare anche al termine dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="3f478-p117">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app. Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-mobile-app-ios"></a><span data-ttu-id="3f478-206">OneDrive App per dispositivi mobili (iOS)</span><span class="sxs-lookup"><span data-stu-id="3f478-206">OneDrive Mobile App (iOS)</span></span> 

<span data-ttu-id="3f478-207">Al termine dello spostamento geografico di OneDrive, l'utente deve uscire e accedere di nuovo all'app Mobile per iOS per eseguire la sincronizzazione con la nuova posizione di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3f478-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="3f478-208">I gruppi e siti seguiti esistenti</span><span class="sxs-lookup"><span data-stu-id="3f478-208">Existing followed groups and sites</span></span>

<span data-ttu-id="3f478-209">I siti e i gruppi seguiti verranno visualizzati nella posizione dell'OneDrive indipendentemente dalla posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="3f478-209">Followed sites and groups will show up in the user's OneDrive regardless of their geo location.</span></span> <span data-ttu-id="3f478-210">I siti e i gruppi ospitati in un'altra posizione geografica verranno aperti in una scheda separata.</span><span class="sxs-lookup"><span data-stu-id="3f478-210">Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="3f478-211">Delve Aggiornamenti degli URL geografici</span><span class="sxs-lookup"><span data-stu-id="3f478-211">Delve Geo URL updates</span></span>

<span data-ttu-id="3f478-212">Gli utenti verranno inviati al Delve geo corrispondente al PDL solo dopo che il OneDrive è stato spostato nella nuova posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="3f478-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
