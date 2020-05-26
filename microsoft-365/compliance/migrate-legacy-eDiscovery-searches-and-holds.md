---
title: Eseguire la migrazione delle ricerche e delle esenzioni eDiscovery legacy al centro conformità di Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 216ec3853f1b55c7fb34de3a236f50094202bca5
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352466"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="1f18e-102">Eseguire la migrazione delle ricerche e delle esenzioni eDiscovery legacy al centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f18e-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="1f18e-103">Microsoft 365 Compliance Center offre una migliore esperienza per l'utilizzo di eDiscovery, tra cui: maggiore affidabilità, prestazioni migliori e numerose funzionalità su misura per i flussi di lavoro di eDiscovery, tra cui i casi di organizzazione del contenuto, i set di revisione per esaminare contenuto e analisi per facilitare la raccolta dei dati per la revisione, ad esempio il raggruppamento quasi duplicato, il threading di posta elettronica, l'</span><span class="sxs-lookup"><span data-stu-id="1f18e-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="1f18e-104">Per aiutare i clienti a sfruttare le funzionalità nuove e migliorate, in questo articolo vengono fornite indicazioni di base su come eseguire la migrazione delle ricerche eDiscovery sul posto e l'esenzioni dall'interfaccia di amministrazione di Exchange al centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f18e-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="1f18e-105">Poiché esistono numerosi scenari diversi, in questo articolo vengono fornite indicazioni generali per le ricerche di transizione e vengono conservate in un caso di eDiscovery di base nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f18e-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1f18e-106">L'utilizzo dei casi di eDiscovery non è sempre necessario, ma aggiunge un ulteriore livello di sicurezza consentendo di assegnare le autorizzazioni per controllare chi ha accesso ai casi di eDiscovery nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f18e-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1f18e-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1f18e-107">Before you begin</span></span>

- <span data-ttu-id="1f18e-108">Per eseguire i comandi di PowerShell descritti in questo articolo, è necessario essere membri del gruppo di ruoli eDiscovery Manager nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="1f18e-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="1f18e-109">È inoltre necessario essere membri del gruppo di ruoli Gestione individuazione nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="1f18e-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="1f18e-110">In questo articolo vengono fornite indicazioni su come creare un'esenzione di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1f18e-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="1f18e-111">Il criterio di blocco verrà applicato alle cassette postali tramite un processo asincrono.</span><span class="sxs-lookup"><span data-stu-id="1f18e-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="1f18e-112">Quando si crea un'esenzione eDiscovery, è necessario creare sia CaseHoldPolicy che CaseHoldRule, altrimenti il blocco non verrà creato e i percorsi di contenuto non verranno mantenuti.</span><span class="sxs-lookup"><span data-stu-id="1f18e-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="1f18e-113">Passaggio 1: connettersi a PowerShell di Exchange Online e Centro sicurezza & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f18e-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="1f18e-114">Il primo passaggio consiste nel connettersi a PowerShell di Exchange Online e al centro sicurezza & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f18e-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="1f18e-115">È possibile copiare lo script seguente, incollarlo in una finestra di PowerShell e quindi eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="1f18e-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="1f18e-116">Verranno richieste le credenziali per l'organizzazione a cui si desidera effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="1f18e-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="1f18e-117">È necessario eseguire i comandi nei passaggi seguenti della sessione di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f18e-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="1f18e-118">Passaggio 2: ottenere un elenco delle ricerche eDiscovery sul posto tramite Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="1f18e-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="1f18e-119">Dopo aver eseguito l'autenticazione, è possibile ottenere un elenco delle ricerche eDiscovery sul posto eseguendo il cmdlet **Get-MailboxSearch** .</span><span class="sxs-lookup"><span data-stu-id="1f18e-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="1f18e-120">Copiare e incollare il comando seguente in PowerShell e quindi eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="1f18e-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="1f18e-121">Un elenco di ricerche verrà elencato con i relativi nomi e lo stato di qualsiasi archiviazione sul posto.</span><span class="sxs-lookup"><span data-stu-id="1f18e-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="1f18e-122">L'output del cmdlet sarà analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="1f18e-122">The cmdlet output will be similar to the following:</span></span>

![Esempio di PowerShell Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="1f18e-124">Passaggio 3: ottenere informazioni sulle ricerche eDiscovery sul posto e sulle archiviazioni sul posto in cui si desidera eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="1f18e-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="1f18e-125">Anche in questo caso, si utilizzerà il cmdlet **Get-MailboxSearch** , ma questa volta per ottenere le proprietà della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1f18e-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="1f18e-126">È possibile archiviare queste proprietà in una variabile per utilizzarla in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1f18e-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="1f18e-127">Nell'esempio seguente vengono archiviati i risultati del cmdlet **Get-MailboxSearch** in una variabile e quindi vengono visualizzate le proprietà della ricerca.</span><span class="sxs-lookup"><span data-stu-id="1f18e-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="1f18e-128">L'output di questi due comandi sarà analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="1f18e-128">The output of these two commands will be similar to the following:</span></span>

![Esempio di output di PowerShell dall'utilizzo di Get-MailboxSearch per una singola ricerca](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="1f18e-130">La durata del blocco sul posto in questo esempio è indefinita (*ItemHoldPeriod: Unlimited*).</span><span class="sxs-lookup"><span data-stu-id="1f18e-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="1f18e-131">Questo è tipico degli scenari di eDiscovery e di indagine legale.</span><span class="sxs-lookup"><span data-stu-id="1f18e-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="1f18e-132">Se la durata del blocco ha un valore diverso da quello indefinito, è probabile che il blocco venga utilizzato per mantenere il contenuto in uno scenario di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1f18e-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="1f18e-133">Invece di utilizzare i cmdlet di eDiscovery nel centro sicurezza & Compliance PowerShell per gli scenari di conservazione, si consiglia di utilizzare [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) e [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) per mantenere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="1f18e-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="1f18e-134">Il risultato dell'utilizzo di questi cmdlet sarà analogo all'utilizzo di **New-CaseHoldPolicy** e **New-CaseHoldRule**, ma è possibile specificare un periodo di conservazione e un'azione di conservazione, ad esempio l'eliminazione del contenuto dopo la scadenza del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="1f18e-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="1f18e-135">Inoltre, l'utilizzo dei cmdlet di conservazione non richiede l'associazione dell'esenzione di conservazione a un caso di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1f18e-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="1f18e-136">Passaggio 4: creare un caso nel centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f18e-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="1f18e-137">Per creare un blocco eDiscovery, è necessario creare un caso di eDiscovery per associare il blocco a.</span><span class="sxs-lookup"><span data-stu-id="1f18e-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="1f18e-138">Nell'esempio seguente viene creato un caso di eDiscovery utilizzando un nome di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="1f18e-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="1f18e-139">Verranno archiviate le proprietà del nuovo caso in una variabile per l'utilizzo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1f18e-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="1f18e-140">È possibile visualizzare tali proprietà eseguendo il `$case | FL` comando dopo aver creato il caso.</span><span class="sxs-lookup"><span data-stu-id="1f18e-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Esempio di esecuzione del comando New-ComplianceCase](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="1f18e-142">Passaggio 5: creare il blocco eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1f18e-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="1f18e-143">Dopo aver creato il caso, è possibile creare il blocco e associarlo al caso creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1f18e-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="1f18e-144">È importante tenere presente che è necessario creare un criterio di blocco del caso e una regola di blocco del caso.</span><span class="sxs-lookup"><span data-stu-id="1f18e-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="1f18e-145">Se la regola di blocco del caso non viene creata dopo aver creato il criterio di blocco del caso, il blocco di eDiscovery non verrà creato e qualsiasi contenuto non verrà messo in attesa.</span><span class="sxs-lookup"><span data-stu-id="1f18e-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="1f18e-146">Eseguire i seguenti comandi per ricreare il blocco di eDiscovery che si desidera migrare.</span><span class="sxs-lookup"><span data-stu-id="1f18e-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="1f18e-147">In questi esempi vengono utilizzate le proprietà dall'archiviazione sul posto del passaggio 3 di cui si desidera eseguire la migrazione.</span><span class="sxs-lookup"><span data-stu-id="1f18e-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="1f18e-148">Il primo comando crea un nuovo criterio di blocco del caso e salva le proprietà in una variabile.</span><span class="sxs-lookup"><span data-stu-id="1f18e-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="1f18e-149">Il secondo comando crea la regola di blocco del caso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1f18e-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Esempio di utilizzo dei cmdlet NewCaseHoldPolicy e NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="1f18e-151">Passaggio 6: verificare l'esenzione di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1f18e-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="1f18e-152">Per assicurarsi che non vi siano problemi nella creazione del blocco, è consigliabile verificare che lo stato di distribuzione di archiviazione sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1f18e-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="1f18e-153">Distribuzione significa che il blocco è stato applicato a tutti i percorsi di contenuto specificati nel parametro *ExchangeLocation* nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1f18e-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="1f18e-154">A tale scopo, è possibile eseguire il cmdlet **Get-CaseHoldPolicy** .</span><span class="sxs-lookup"><span data-stu-id="1f18e-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="1f18e-155">Poiché le proprietà salvate nella variabile *$policy* creata nel passaggio precedente non vengono aggiornate automaticamente nella variabile, è necessario eseguire nuovamente il cmdlet per verificare che la distribuzione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1f18e-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="1f18e-156">La distribuzione dei criteri di blocco del caso può richiedere da 5 a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="1f18e-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="1f18e-157">Eseguire il seguente comando per verificare che il blocco eDiscovery sia stato distribuito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1f18e-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="1f18e-158">Il valore di **Success** per la proprietà *Proprietà distributionstatus* indica che il blocco è stato inserito correttamente nei percorsi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="1f18e-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="1f18e-159">Se la distribuzione non è ancora stata completata, verrà visualizzato un valore di **Pending** .</span><span class="sxs-lookup"><span data-stu-id="1f18e-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![Esempio di Get-CaseHoldPolicy di PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="1f18e-161">Passaggio 7: creare la ricerca</span><span class="sxs-lookup"><span data-stu-id="1f18e-161">Step 7: Create the search</span></span>

<span data-ttu-id="1f18e-162">L'ultimo passaggio consiste nel ricreare la ricerca identificata nel passaggio 3 e associarla al caso.</span><span class="sxs-lookup"><span data-stu-id="1f18e-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="1f18e-163">Dopo aver creato la ricerca, è possibile eseguirla utilizzando il cmdlet **Start-ComplianceSearch** o eseguirla in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1f18e-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Esempio di PowerShell New-ComplianceSearch](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="1f18e-165">Passaggio 8: verificare il caso, il blocco e la ricerca nel centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f18e-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="1f18e-166">Per assicurarsi che tutto sia configurato correttamente, passare al centro conformità di Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="1f18e-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 Compliance Center eDiscovery](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="1f18e-168">Il caso creato nel passaggio 3 è elencato nella pagina principale di **eDiscovery** .</span><span class="sxs-lookup"><span data-stu-id="1f18e-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="1f18e-169">Aprire il caso e quindi tenere presente che il blocco creato nel passaggio 4 è elencato nella scheda **esenzioni** . È possibile fare clic sul blocco per visualizzare i dettagli, incluso il numero di cassette postali a cui è applicato il blocco e lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1f18e-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![eDiscovery contiene nel centro conformità di Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="1f18e-171">La ricerca creata al passaggio 7 è elencata nella scheda **ricerche** del caso eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1f18e-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![ricerca di casi di eDiscovery nel centro conformità di Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="1f18e-173">Se si esegue la migrazione di una ricerca eDiscovery sul posto ma non la si associa a un caso di eDiscovery, questa verrà elencata nella pagina Ricerca contenuto del centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f18e-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="1f18e-174">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="1f18e-174">More information</span></span>

- <span data-ttu-id="1f18e-175">Per ulteriori informazioni su eDiscovery sul posto & conserva nell'interfaccia di amministrazione di Exchange, vedere:</span><span class="sxs-lookup"><span data-stu-id="1f18e-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="1f18e-176">eDiscovery sul posto</span><span class="sxs-lookup"><span data-stu-id="1f18e-176">In-Place eDiscovery</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="1f18e-177">Conservazione in locale e per controversia legale</span><span class="sxs-lookup"><span data-stu-id="1f18e-177">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="1f18e-178">Per ulteriori informazioni sui cmdlet di PowerShell utilizzati nell'articolo, vedere:</span><span class="sxs-lookup"><span data-stu-id="1f18e-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="1f18e-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="1f18e-179">Get-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="1f18e-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="1f18e-180">New-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="1f18e-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="1f18e-181">New-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="1f18e-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="1f18e-182">New-CaseHoldRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="1f18e-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="1f18e-183">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="1f18e-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1f18e-184">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="1f18e-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1f18e-185">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="1f18e-186">Per ulteriori informazioni sul centro conformità di Microsoft 365, vedere [Overview of the microsoft 365 Compliance Center](microsoft-365-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1f18e-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>
