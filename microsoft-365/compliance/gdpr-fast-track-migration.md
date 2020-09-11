---
title: GDPR
description: Suggerimenti tecnici Microsoft — SET DI STRUMENTI DI MIGRAZIONE DI FASTTRACK PER INVIARE LE RICHIESTE DI ELIMINAZIONE
keywords: Migrazione di FastTrack, Microsoft 365 Education, Documentazione Microsoft 365, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 162a64535f82f24411121ed81e36078511eb8eba
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416912"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="30480-104">Set di strumenti di migrazione di FastTrack per inviare una richiesta di eliminazione</span><span class="sxs-lookup"><span data-stu-id="30480-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="30480-105">Scopo del set di strumenti</span><span class="sxs-lookup"><span data-stu-id="30480-105">Toolset purpose</span></span>

<span data-ttu-id="30480-p101">Se si è un cliente attualmente coinvolto in una migrazione di FastTrack, eliminando l'account utente non sarà eliminata la copia dei dati utilizzata dal team di Microsoft FastTrack, che viene conservata con il solo scopo di completare la migrazione. Se durante la migrazione si desidera che il team di Microsoft FastTrack elimini anche la copia dei dati, è possibile inviare una richiesta tramite questo set di strumenti. In condizioni normali di attività, Microsoft FastTrack eliminerà tutte le copie dei dati una volta completata la migrazione.</span><span class="sxs-lookup"><span data-stu-id="30480-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="30480-109">Piattaforme supportate</span><span class="sxs-lookup"><span data-stu-id="30480-109">Supported platforms</span></span>
<span data-ttu-id="30480-p102">Microsoft supporta la versione iniziale di questo set di strumenti nella piattaforma Windows e nella console di PowerShell. Il set di strumenti supporta le seguenti piattaforme:</span><span class="sxs-lookup"><span data-stu-id="30480-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="30480-112">***Tabella 1 — Piattaforme supportate da questo set di strumenti***</span><span class="sxs-lookup"><span data-stu-id="30480-112">***Table 1 — Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="30480-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="30480-113">**Windows 7**</span></span>|<span data-ttu-id="30480-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="30480-114">**Windows 8**</span></span>|<span data-ttu-id="30480-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="30480-115">**Windows 10**</span></span>|<span data-ttu-id="30480-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="30480-116">**Windows Server 2012**</span></span>|<span data-ttu-id="30480-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="30480-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="30480-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="30480-118">PS 5.0</span></span>|<span data-ttu-id="30480-119">Non</span><span class="sxs-lookup"><span data-stu-id="30480-119">Not</span></span><br/><span data-ttu-id="30480-120">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-120">Supported</span></span>|<span data-ttu-id="30480-121">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-121">Supported</span></span>|<span data-ttu-id="30480-122">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-122">Supported</span></span>|<span data-ttu-id="30480-123">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-123">Supported</span></span>|<span data-ttu-id="30480-124">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-124">Supported</span></span>|
|<span data-ttu-id="30480-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="30480-125">PS 5.1</span></span>|<span data-ttu-id="30480-126">Non</span><span class="sxs-lookup"><span data-stu-id="30480-126">Not</span></span><br/><span data-ttu-id="30480-127">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-127">Supported</span></span>|<span data-ttu-id="30480-128">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-128">Supported</span></span>|<span data-ttu-id="30480-129">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-129">Supported</span></span>|<span data-ttu-id="30480-130">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-130">Supported</span></span>|<span data-ttu-id="30480-131">Supportato</span><span class="sxs-lookup"><span data-stu-id="30480-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="30480-132">Ottenere il set di strumenti</span><span class="sxs-lookup"><span data-stu-id="30480-132">Obtaining the toolset</span></span>

<span data-ttu-id="30480-p103">Il set di strumenti è disponibile in PowerShell Gallery nell'applicazione console di PowerShell. Per individuare e caricare questo modulo cmdlet, aprire PowerShell in modalità di amministratore in modo da avere le autorizzazioni adeguate per installare il modulo. Se non si è mai utilizzato prima PowerShell, passare alla barra delle applicazioni di Windows e digitare nella casella di ricerca "PowerShell". Selezionare l'applicazione console con pulsante destro del mouse e scegliere l'opzione **Esegui come amministratore**, quindi fare clic su **Sì** per eseguire Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30480-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell — Esegui come amministratore](../media/fasttrack-powershell_image.png)

![PowerShell — Consenti all'app di apportare modifiche](../media/fasttrack-run-powershell_image.png)

<span data-ttu-id="30480-p104">Una volta aperta la console, è necessario impostare le autorizzazioni per l'esecuzione dello script. Digitare il comando seguente per consentire l'esecuzione di script: "Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope:Process"</span><span class="sxs-lookup"><span data-stu-id="30480-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process’</span></span>

<span data-ttu-id="30480-141">Verrà richiesto di confermare l'azione, in quanto l'amministratore può modificare l'ambito a propria discrezione.</span><span class="sxs-lookup"><span data-stu-id="30480-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="30480-142">***Impostare criteri di esecuzione***</span><span class="sxs-lookup"><span data-stu-id="30480-142">***Set Execution Policy***</span></span>

![Impostare la modifica dei criteri di esecuzione in PowerShell](../media/powershell-set-execution-policy_image.png)

<span data-ttu-id="30480-144">Dopo che la console è impostata per consentire lo script, eseguire il comando seguente per installare il modulo:</span><span class="sxs-lookup"><span data-stu-id="30480-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="30480-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span><span class="sxs-lookup"><span data-stu-id="30480-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="30480-146">Prerequisiti per il modulo</span><span class="sxs-lookup"><span data-stu-id="30480-146">Prerequisites for module</span></span>
<span data-ttu-id="30480-p105">Per eseguire correttamente il modulo, è necessario installare moduli dipendenti da utilizzare, nel caso in cui non siano già installati. Potrebbe essere necessario riavviare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30480-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="30480-149">Per poter inviare un DSR, è necessario accedere prima con le credenziali di Office 365: immettendo le credenziali appropriate viene convalidato lo stato di amministratore globale e vengono raccolte le informazioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="30480-149">In order to submit a DSR, you must first log in using your Office 365 credentials — entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="30480-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span><span class="sxs-lookup"><span data-stu-id="30480-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="30480-151">Una volta eseguito l'accesso, le credenziali e la chiave saranno conservate per l'utilizzo con i moduli FastTrack per il resto della sessione corrente di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30480-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="30480-152">Se è necessario connettersi a un ambiente cloud diverso da quello commerciale, sarà necessario aggiungere *-Environment* al comando *Login* con uno dei seguenti ambienti validi:</span><span class="sxs-lookup"><span data-stu-id="30480-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>
- <span data-ttu-id="30480-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="30480-153">AzureCloud</span></span>
- <span data-ttu-id="30480-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="30480-154">AzureChinaCloud</span></span>
- <span data-ttu-id="30480-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="30480-155">AzureGermanCloud</span></span>
- <span data-ttu-id="30480-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="30480-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="30480-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span><span class="sxs-lookup"><span data-stu-id="30480-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="30480-158">Per inviare una richiesta DSR, eseguire il comando seguente: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span><span class="sxs-lookup"><span data-stu-id="30480-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="30480-p106">Al termine dell'operazione, il cmdlet restituirà un oggetto ID transazione, che è consigliabile conservare.</span><span class="sxs-lookup"><span data-stu-id="30480-p106">On success — the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="30480-161">Verificare lo stato di una richiesta transazione</span><span class="sxs-lookup"><span data-stu-id="30480-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="30480-162">Eseguire la funzione seguente usando l'ID transazione ottenuto in precedenza: Get-FastTrackGdprDsrRequest -TransactionID: "IDTransazione"</span><span class="sxs-lookup"><span data-stu-id="30480-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="30480-163">Codici di stato transazione</span><span class="sxs-lookup"><span data-stu-id="30480-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="30480-164">**Transazione**</span><span class="sxs-lookup"><span data-stu-id="30480-164">**Transaction**</span></span> |<span data-ttu-id="30480-165">**Stato**</span><span class="sxs-lookup"><span data-stu-id="30480-165">**Status**</span></span>|
|<span data-ttu-id="30480-166">**Creato**</span><span class="sxs-lookup"><span data-stu-id="30480-166">**Created**</span></span> |<span data-ttu-id="30480-167">La richiesta è stata creata</span><span class="sxs-lookup"><span data-stu-id="30480-167">Request has been created</span></span>|
|<span data-ttu-id="30480-168">**Operazione non riuscita**</span><span class="sxs-lookup"><span data-stu-id="30480-168">**Failed**</span></span>|<span data-ttu-id="30480-169">Non è stato possibile creare la richiesta; inviarla nuovamente o contattare l'assistenza</span><span class="sxs-lookup"><span data-stu-id="30480-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="30480-170">**Operazione completata**</span><span class="sxs-lookup"><span data-stu-id="30480-170">**Completed**</span></span>|<span data-ttu-id="30480-171">La richiesta è stata completata e purificata</span><span class="sxs-lookup"><span data-stu-id="30480-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="30480-172">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="30480-172">Learn more</span></span>
[<span data-ttu-id="30480-173">Centro protezione Microsoft</span><span class="sxs-lookup"><span data-stu-id="30480-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview
)
