---
title: Raccogliere informazioni di diagnostica di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come raccogliere informazioni di diagnostica di eDiscovery per un caso di supporto Microsoft.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926556"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="f90a6-103">Raccogliere informazioni di diagnostica di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f90a6-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="f90a6-104">Occasionalmente i tecnici del supporto Tecnico Microsoft richiedono informazioni specifiche sul problema quando si apre un caso di supporto relativo a Core eDiscovery o Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f90a6-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="f90a6-105">In questo articolo vengono fornite indicazioni su come raccogliere informazioni di diagnostica per aiutare i tecnici del supporto tecnico ad analizzare e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="f90a6-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="f90a6-106">In genere, non è necessario raccogliere queste informazioni finché non viene richiesto da un tecnico del supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f90a6-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f90a6-107">L'output dei cmdlet e le informazioni di diagnostica descritte in questo articolo possono includere informazioni riservate su controversie legali o indagini interne nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f90a6-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="f90a6-108">Prima di inviare le informazioni di diagnostica non elaborate al supporto tecnico Microsoft, è consigliabile esaminare le informazioni e redigere eventuali informazioni riservate (ad esempio nomi o altre informazioni sulle parti per controversia legale o indagine) sostituendola con `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="f90a6-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="f90a6-109">L'utilizzo di questo metodo indicherà anche al tecnico del supporto Tecnico Microsoft che le informazioni sono stati redatti.</span><span class="sxs-lookup"><span data-stu-id="f90a6-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="f90a6-110">Raccogliere informazioni di diagnostica per Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f90a6-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="f90a6-111">La raccolta di informazioni di diagnostica per Core eDiscovery è basata su cmdlet, quindi dovrai usare PowerShell per centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="f90a6-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="f90a6-112">Gli esempi di PowerShell seguenti eseguono cmdlet e quindi salvano l'output in un file di testo specificato.</span><span class="sxs-lookup"><span data-stu-id="f90a6-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="f90a6-113">Nella maggior parte dei casi, è necessario eseguire solo uno di questi comandi.</span><span class="sxs-lookup"><span data-stu-id="f90a6-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="f90a6-114">Per eseguire i cmdlet seguenti, [connettersi a PowerShell </span> & Centro sicurezza](/powershell/exchange/connect-to-scc-powershell)e conformità.</span><span class="sxs-lookup"><span data-stu-id="f90a6-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="f90a6-115">Dopo aver eseguito la connessione, eseguire uno o più dei comandi seguenti e assicurarsi di sostituire i segnaposto con i nomi degli oggetti effettivi.</span><span class="sxs-lookup"><span data-stu-id="f90a6-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="f90a6-116">Dopo aver esaminato il file di testo generato e aver redatto le informazioni riservate, inviarle al tecnico del supporto Tecnico Microsoft che sta lavorando al caso.</span><span class="sxs-lookup"><span data-stu-id="f90a6-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="f90a6-117">È inoltre possibile eseguire i comandi di questa sezione per raccogliere  informazioni di diagnostica per le ricerche e le esportazioni elencate nella pagina Ricerca contenuto nel Centro Microsoft 365 conformità.</span><span class="sxs-lookup"><span data-stu-id="f90a6-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="f90a6-118">Raccogliere informazioni sulle ricerche</span><span class="sxs-lookup"><span data-stu-id="f90a6-118">Collect information about searches</span></span>

<span data-ttu-id="f90a6-119">Il comando seguente raccoglie informazioni utili quando si analizzano i problemi relativi a una ricerca contenuto o a una ricerca associata a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="f90a6-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="f90a6-120">Raccogliere informazioni sulle azioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="f90a6-120">Collect information about search actions</span></span>

<span data-ttu-id="f90a6-121">Il comando seguente raccoglie informazioni per analizzare i problemi relativi all'anteprima, all'esportazione o all'eliminazione dei risultati di una ricerca contenuto o di una ricerca associata a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="f90a6-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="f90a6-122">È possibile identificare il nome dell'azione di ricerca facendo clic su un'esportazione elencata nella **scheda** Esportazioni. Per identificare i nomi delle azioni di anteprima ed eliminazione, è possibile eseguire il cmdlet **Get-ComplianceSearchAction** per visualizzare un elenco di tutte le azioni.</span><span class="sxs-lookup"><span data-stu-id="f90a6-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="f90a6-123">Il formato per il nome dell'azione di ricerca viene creato aggiungendo `_Preview` , o al nome della ricerca `_Export` `_Purge` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f90a6-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="f90a6-124">Raccogliere informazioni sui blocchi di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f90a6-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="f90a6-125">Quando un blocco di eDiscovery associato a un caso di eDiscovery di base non funziona come previsto, eseguire il comando seguente per raccogliere informazioni sui criteri di blocco del caso e sulla regola di blocco del caso associata per il blocco di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f90a6-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="f90a6-126">Il *nome del criterio di conservazione delle* maiuscole e minuscole nel comando seguente corrisponde al nome del blocco eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f90a6-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="f90a6-127">È possibile identificare questo nome nelle schede **Esenzioni** nel caso core eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f90a6-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="f90a6-128">Raccogliere tutte le informazioni sul caso</span><span class="sxs-lookup"><span data-stu-id="f90a6-128">Collect all case information</span></span>

<span data-ttu-id="f90a6-129">A volte, non è evidente quali informazioni sono necessarie al supporto tecnico Microsoft per analizzare il problema.</span><span class="sxs-lookup"><span data-stu-id="f90a6-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="f90a6-130">In questo caso, è possibile raccogliere tutte le informazioni di diagnostica per un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="f90a6-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="f90a6-131">Il nome del caso core **di eDiscovery** nel comando seguente corrisponde al nome di un caso visualizzato nella pagina Core *eDiscovery* nel Centro Microsoft 365 conformità.</span><span class="sxs-lookup"><span data-stu-id="f90a6-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="f90a6-132">Raccogliere informazioni di diagnostica per Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f90a6-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="f90a6-133">La **Impostazioni** in un caso Advanced eDiscovery consente di copiare rapidamente le informazioni di diagnostica per il caso.</span><span class="sxs-lookup"><span data-stu-id="f90a6-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="f90a6-134">Le informazioni di diagnostica vengono salvate negli Appunti in modo da poter essere incollate in un file di testo e inviate al supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f90a6-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="f90a6-135">Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su Mostra > **eDiscovery > Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="f90a6-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="f90a6-136">Selezionare un caso e quindi fare clic sulla **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="f90a6-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="f90a6-137">In **Informazioni caso** fare clic su **Seleziona.**</span><span class="sxs-lookup"><span data-stu-id="f90a6-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="f90a6-138">Nella pagina a comparsa fai clic su **Copia informazioni di** diagnostica per copiare le informazioni negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f90a6-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="f90a6-139">Aprire un file di testo (in Blocco note) e quindi incollare le informazioni nel file di testo.</span><span class="sxs-lookup"><span data-stu-id="f90a6-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="f90a6-140">Salvare il file di testo e assegnare un nome simile `AeD Diagnostic Info YYYY.MM.DD` (ad esempio, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="f90a6-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="f90a6-141">Dopo aver esaminato il file e aver redatto le informazioni riservate, inviarlo al tecnico del supporto Tecnico Microsoft che sta lavorando al caso.</span><span class="sxs-lookup"><span data-stu-id="f90a6-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>