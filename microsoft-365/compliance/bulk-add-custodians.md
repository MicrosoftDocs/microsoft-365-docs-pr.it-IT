---
title: Importare i responsabile in un caso di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Utilizzare lo strumento di importazione per aggiungere rapidamente più responsabile e le origini dati associate a un caso in Advanced eDiscovery.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740303"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="3d9da-103">Importare i responsabile in un caso di Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3d9da-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="3d9da-104">Per i casi di Advanced eDiscovery che coinvolgono molti amministratori, è possibile importare più amministratori contemporaneamente utilizzando un file CSV contenente le informazioni necessarie per aggiungerli a un caso.</span><span class="sxs-lookup"><span data-stu-id="3d9da-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="3d9da-105">Importare i responsabile</span><span class="sxs-lookup"><span data-stu-id="3d9da-105">Import custodians</span></span>

1. <span data-ttu-id="3d9da-106">Aprire il caso advanced eDiscovery e selezionare la **scheda Origini** dati.</span><span class="sxs-lookup"><span data-stu-id="3d9da-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="3d9da-107">Fare **clic su Aggiungi responsabile dell'importazione**  >  **dell'origine dati.**</span><span class="sxs-lookup"><span data-stu-id="3d9da-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="3d9da-108">Nella pagina **a comparsa Importa i responsabile** fare clic su Scarica un modello **vuoto** per scaricare un file CSV del modello di responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Scaricare un modello CSV dalla pagina a comparsa Importare i responsabile](../media/ImportCustodians1.png)

4. <span data-ttu-id="3d9da-110">Aggiungere le informazioni del responsabile al file CSV e salvarle nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="3d9da-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="3d9da-111">Per informazioni sulle proprietà necessarie nel [file CSV,](#custodian-csv-file) vedere la sezione relativa al file CSV del responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="3d9da-112">Dopo aver preparato il file CSV con le informazioni  del responsabile, tornare alla scheda Origini dati e fare di nuovo clic su Aggiungi responsabile dell'importazione  >  **dell'origine** dati.</span><span class="sxs-lookup"><span data-stu-id="3d9da-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="3d9da-113">Nella pagina **a comparsa Importa i responsabile** fare clic su **Sfoglia** e quindi caricare il file CSV contenente le informazioni sui responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="3d9da-114">Dopo il caricamento del file CSV, viene creato e visualizzato un processo denominato **BulkAddCustodian** nella **scheda Processi.** Il processo convalida i responsabile e le origini dati associate e quindi li aggiunge alla **pagina Origini** dati del caso.</span><span class="sxs-lookup"><span data-stu-id="3d9da-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="3d9da-115">File CSV del responsabile</span><span class="sxs-lookup"><span data-stu-id="3d9da-115">Custodian CSV file</span></span>

<span data-ttu-id="3d9da-116">Dopo aver scaricato il modello di responsabile CSV, è possibile aggiungere i responsabile e l'origine dati corrispondente in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="3d9da-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="3d9da-117">Assicurarsi di non modificare i nomi delle colonne nella riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="3d9da-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="3d9da-118">Utilizzare le colonne tipo di carico di lavoro e posizione del carico di lavoro per associare altre origini dati a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="3d9da-119">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="3d9da-119">Column name</span></span>|<span data-ttu-id="3d9da-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d9da-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="3d9da-121">**Contatto responsabileEmail**</span><span class="sxs-lookup"><span data-stu-id="3d9da-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="3d9da-122">Indirizzo di posta elettronica UPN del responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-122">The custodian's UPN email address.</span></span> <span data-ttu-id="3d9da-123">Ad esempio, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="3d9da-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="3d9da-124">**Exchange abilitato**</span><span class="sxs-lookup"><span data-stu-id="3d9da-124">**Exchange Enabled**</span></span> | <span data-ttu-id="3d9da-125">Valore TRUE/FALSE per includere o non includere la cassetta postale del responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="3d9da-126">**OneDrive abilitato**</span><span class="sxs-lookup"><span data-stu-id="3d9da-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="3d9da-127">Valore TRUE/FALSE per includere o non includere l'account OneDrive for Business del responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="3d9da-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="3d9da-128">**Is OnHold**</span></span>        | <span data-ttu-id="3d9da-129">Valore TRUE/FALSE per indicare se le origini dati del responsabile devono essere in attesa.</span><span class="sxs-lookup"><span data-stu-id="3d9da-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="3d9da-130">**Tipo Carico di lavoro1**</span><span class="sxs-lookup"><span data-stu-id="3d9da-130">**Workload1 Type**</span></span>         |<span data-ttu-id="3d9da-131">Valore stringa che indica il tipo di origine dati da associare al responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="3d9da-132">I valori possibili includono:</span><span class="sxs-lookup"><span data-stu-id="3d9da-132">Possible values include:</span></span> <br/><span data-ttu-id="3d9da-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="3d9da-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="3d9da-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="3d9da-134">- SharePointSite</span></span><br/><span data-ttu-id="3d9da-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="3d9da-135">- TeamsMailbox</span></span><br/><span data-ttu-id="3d9da-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="3d9da-136">- TeamsSite</span></span><br/> <span data-ttu-id="3d9da-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="3d9da-137">- YammerMailbox</span></span><br/><span data-ttu-id="3d9da-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="3d9da-138">- YammerSite</span></span> |
|<span data-ttu-id="3d9da-139">**Posizione carico di lavoro 1**</span><span class="sxs-lookup"><span data-stu-id="3d9da-139">**Workload1 Location**</span></span>     | <span data-ttu-id="3d9da-140">A seconda del tipo di carico di lavoro, si tratta della posizione dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3d9da-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="3d9da-141">Ad esempio, l'indirizzo di posta elettronica per una cassetta postale di Exchange o l'URL di un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d9da-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="3d9da-142">Ecco un esempio di un file CSV con le informazioni del responsabile:</span><span class="sxs-lookup"><span data-stu-id="3d9da-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="3d9da-143">Contatto responsabileEmail</span><span class="sxs-lookup"><span data-stu-id="3d9da-143">Custodian contactEmail</span></span>      | <span data-ttu-id="3d9da-144">Exchange abilitato</span><span class="sxs-lookup"><span data-stu-id="3d9da-144">Exchange Enabled</span></span> | <span data-ttu-id="3d9da-145">OneDrive abilitato</span><span class="sxs-lookup"><span data-stu-id="3d9da-145">OneDrive Enabled</span></span> | <span data-ttu-id="3d9da-146">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="3d9da-146">Is OnHold</span></span> | <span data-ttu-id="3d9da-147">Tipo Carico di lavoro1</span><span class="sxs-lookup"><span data-stu-id="3d9da-147">Workload1 Type</span></span> | <span data-ttu-id="3d9da-148">Posizione carico di lavoro 1</span><span class="sxs-lookup"><span data-stu-id="3d9da-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="3d9da-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d9da-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="3d9da-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="3d9da-150">TRUE</span></span>             | <span data-ttu-id="3d9da-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="3d9da-151">TRUE</span></span>             | <span data-ttu-id="3d9da-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="3d9da-152">TRUE</span></span>      | <span data-ttu-id="3d9da-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="3d9da-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="3d9da-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d9da-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="3d9da-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="3d9da-155">TRUE</span></span>             | <span data-ttu-id="3d9da-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="3d9da-156">TRUE</span></span>             | <span data-ttu-id="3d9da-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="3d9da-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="3d9da-158">Convalida del responsabile e dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="3d9da-158">Custodian and data source validation</span></span>

<span data-ttu-id="3d9da-159">Dopo aver caricato il file CSV del responsabile, Advanced eDiscovery esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d9da-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="3d9da-160">Convalida i responsabile e le relative origini dati.</span><span class="sxs-lookup"><span data-stu-id="3d9da-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="3d9da-161">Indicizza tutte le origini dati per ogni responsabile e le mette in attesa (se la proprietà **Is OnHold** nel file CSV è impostata su TRUE).</span><span class="sxs-lookup"><span data-stu-id="3d9da-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="3d9da-162">Convalida del responsabile</span><span class="sxs-lookup"><span data-stu-id="3d9da-162">Custodian validation</span></span>

<span data-ttu-id="3d9da-163">Attualmente, microsoft supporta solo l'importazione di responsabile inclusi in Azure Active Directory (Azure AD) dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d9da-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="3d9da-164">Lo strumento di importazione dei responsabile trova e convalida i responsabile utilizzando il valore UPN nella colonna **ContactEmail** del responsabile nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="3d9da-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="3d9da-165">I responsabile convalidati vengono aggiunti automaticamente al caso ed elencati nella **scheda Origini** dati del caso.</span><span class="sxs-lookup"><span data-stu-id="3d9da-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="3d9da-166">Se un responsabile non può essere convalidato, viene elencato nel registro errori per il  processo BulkAddCustodian elencato nella scheda Processi.</span><span class="sxs-lookup"><span data-stu-id="3d9da-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="3d9da-167">I responsabile non convalidati non vengono aggiunti al caso o elencati nella **scheda Origini** dati.</span><span class="sxs-lookup"><span data-stu-id="3d9da-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="3d9da-168">Convalida dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="3d9da-168">Data source validation</span></span>

<span data-ttu-id="3d9da-169">Dopo che i responsabile vengono convalidati e aggiunti al caso, vengono aggiunti ogni cassetta postale principale e ogni account di OneDrive associato a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="3d9da-170">Tuttavia, se non è possibile trovare altre origini dati (ad esempio siti di SharePoint, Microsoft Teams, gruppi di Microsoft 365 o gruppi di  Yammer) associate a un  responsabile, nessuna di esse viene assegnata al responsabile e il valore Non convalidato viene visualizzato nella colonna Stato accanto al responsabile nella scheda Origini **dati.**</span><span class="sxs-lookup"><span data-stu-id="3d9da-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="3d9da-171">Per aggiungere origini dati convalidate per un responsabile:</span><span class="sxs-lookup"><span data-stu-id="3d9da-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="3d9da-172">Nella scheda **Origini dati** selezionare un responsabile che contiene origini dati non convalidate.</span><span class="sxs-lookup"><span data-stu-id="3d9da-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="3d9da-173">Nella pagina del riquadro a comparsa  del responsabile scorrere fino alla sezione Posizioni del responsabile per visualizzare sia le origini dati convalidate che le origini dati non convalidate associate al responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="3d9da-174">Fare **clic su** Modifica nella parte superiore della pagina a comparsa per rimuovere origini dati non valide o aggiungerne di nuove.</span><span class="sxs-lookup"><span data-stu-id="3d9da-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="3d9da-175">Dopo aver rimosso le origini dati non convalidate o averne  aggiunto una nuova, il valore **Attivo** viene visualizzato nella colonna Stato del responsabile nella **scheda Origini** dati. Per aggiungere origini che in precedenza non erano valide, segui i passaggi di correzione seguenti per aggiungerle manualmente a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="3d9da-176">Correzione di origini dati non valide</span><span class="sxs-lookup"><span data-stu-id="3d9da-176">Remediating invalid data sources</span></span>

<span data-ttu-id="3d9da-177">Per aggiungere e associare manualmente un'origine dati precedentemente non valida:</span><span class="sxs-lookup"><span data-stu-id="3d9da-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="3d9da-178">Nella scheda **Origini dati selezionare** un responsabile per aggiungere e associare manualmente un'origine dati precedentemente non valida.</span><span class="sxs-lookup"><span data-stu-id="3d9da-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="3d9da-179">Fare **clic** su Modifica nella parte superiore della pagina del riquadro a comparsa per associare cassette postali, siti, gruppi di Teams o Yammer al responsabile.</span><span class="sxs-lookup"><span data-stu-id="3d9da-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="3d9da-180">A tale scopo, fare **clic su Modifica** accanto al tipo di percorso dati appropriato.</span><span class="sxs-lookup"><span data-stu-id="3d9da-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="3d9da-181">Fare **clic su** Avanti per visualizzare la pagina delle impostazioni **di** blocco e configurare l'impostazione di blocco per le origini dati aggiunte.</span><span class="sxs-lookup"><span data-stu-id="3d9da-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="3d9da-182">Fare **clic** su Avanti per visualizzare **la pagina Rivedi** i revisori e quindi su **Invia** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3d9da-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
