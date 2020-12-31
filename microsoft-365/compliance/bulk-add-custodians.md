---
title: Importare i depositari in un caso avanzato di eDiscovery
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
description: Utilizzare lo strumento di importazione dto aggiungere rapidamente più depositari e le origini dati associate a un caso in Advanced eDiscovery.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740303"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="1855c-103">Importare i depositari in un caso avanzato di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1855c-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="1855c-104">Per i casi di eDiscovery avanzati che coinvolgono numerosi depositari, è possibile importare più depositari contemporaneamente utilizzando un file CSV che contiene le informazioni necessarie per aggiungerle a un caso.</span><span class="sxs-lookup"><span data-stu-id="1855c-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="1855c-105">Importare i depositari</span><span class="sxs-lookup"><span data-stu-id="1855c-105">Import custodians</span></span>

1. <span data-ttu-id="1855c-106">Aprire il caso Advanced eDiscovery e selezionare la scheda **origini dati** .</span><span class="sxs-lookup"><span data-stu-id="1855c-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="1855c-107">Fare clic su Aggiungi depositari di importazione di **origine dati**  >  .</span><span class="sxs-lookup"><span data-stu-id="1855c-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="1855c-108">Nella pagina **Importa** riquadro a comparsa dei depositari, fare clic su **Scarica un modello vuoto** per scaricare un file CSV del modello di custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Scaricare un modello CSV dalla pagina importazione a comparsa dei depositari](../media/ImportCustodians1.png)

4. <span data-ttu-id="1855c-110">Aggiungere le informazioni di custodia al file CSV e salvarlo nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="1855c-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="1855c-111">Per informazioni sulle proprietà obbligatorie nel file CSV, vedere la sezione [file CSV del custode](#custodian-csv-file) .</span><span class="sxs-lookup"><span data-stu-id="1855c-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="1855c-112">Dopo aver preparato il file CSV con le informazioni sul custode, tornare alla scheda **origini dati** e fare di nuovo clic su Aggiungi depositari di importazione di **origine dati**  >   .</span><span class="sxs-lookup"><span data-stu-id="1855c-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="1855c-113">Nella pagina **Importa** riquadro a comparsa dei depositari fare clic su **Sfoglia** e quindi caricare il file CSV che contiene le informazioni sul custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="1855c-114">Dopo il caricamento del file CSV, viene creato e visualizzato un processo denominato **BulkAddCustodian** nella scheda **processi** . Il processo consente di convalidare i depositari e le origini dati associate e quindi di aggiungerli alla pagina **origini dati** del caso.</span><span class="sxs-lookup"><span data-stu-id="1855c-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="1855c-115">File CSV del custode</span><span class="sxs-lookup"><span data-stu-id="1855c-115">Custodian CSV file</span></span>

<span data-ttu-id="1855c-116">Dopo aver scaricato il modello del custode CSV, è possibile aggiungere depositari e l'origine dati in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="1855c-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="1855c-117">Assicurarsi di non modificare i nomi delle colonne nella riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="1855c-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="1855c-118">Per associare altre origini dati a un custode, utilizzare le colonne del tipo di carico di lavoro e del percorso del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1855c-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="1855c-119">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="1855c-119">Column name</span></span>|<span data-ttu-id="1855c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1855c-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="1855c-121">**ContactEmail custode**</span><span class="sxs-lookup"><span data-stu-id="1855c-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="1855c-122">L'indirizzo di posta elettronica UPN del custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-122">The custodian's UPN email address.</span></span> <span data-ttu-id="1855c-123">Ad esempio, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="1855c-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="1855c-124">**Exchange abilitato**</span><span class="sxs-lookup"><span data-stu-id="1855c-124">**Exchange Enabled**</span></span> | <span data-ttu-id="1855c-125">Valore TRUE/FALSE per includere o meno la cassetta postale del custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="1855c-126">**OneDrive abilitato**</span><span class="sxs-lookup"><span data-stu-id="1855c-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="1855c-127">Valore TRUE/FALSE per includere o meno l'account OneDrive for business del custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="1855c-128">**È OnHold**</span><span class="sxs-lookup"><span data-stu-id="1855c-128">**Is OnHold**</span></span>        | <span data-ttu-id="1855c-129">Valore TRUE/FALSE per indicare se inserire le origini dati del custode in attesa.</span><span class="sxs-lookup"><span data-stu-id="1855c-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="1855c-130">**Tipo di Workload1**</span><span class="sxs-lookup"><span data-stu-id="1855c-130">**Workload1 Type**</span></span>         |<span data-ttu-id="1855c-131">Valore stringa che indica il tipo di origine dati da associare al custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="1855c-132">I valori possibili includono:</span><span class="sxs-lookup"><span data-stu-id="1855c-132">Possible values include:</span></span> <br/><span data-ttu-id="1855c-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="1855c-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="1855c-134">-SitoSharePoint</span><span class="sxs-lookup"><span data-stu-id="1855c-134">- SharePointSite</span></span><br/><span data-ttu-id="1855c-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="1855c-135">- TeamsMailbox</span></span><br/><span data-ttu-id="1855c-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="1855c-136">- TeamsSite</span></span><br/> <span data-ttu-id="1855c-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="1855c-137">- YammerMailbox</span></span><br/><span data-ttu-id="1855c-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="1855c-138">- YammerSite</span></span> |
|<span data-ttu-id="1855c-139">**Percorso Workload1**</span><span class="sxs-lookup"><span data-stu-id="1855c-139">**Workload1 Location**</span></span>     | <span data-ttu-id="1855c-140">A seconda del tipo di carico di lavoro, si tratta del percorso dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1855c-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="1855c-141">Ad esempio, l'indirizzo di posta elettronica di una cassetta postale di Exchange o l'URL di un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1855c-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="1855c-142">Di seguito è riportato un esempio di file CSV con informazioni sul custode:</span><span class="sxs-lookup"><span data-stu-id="1855c-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="1855c-143">ContactEmail custode</span><span class="sxs-lookup"><span data-stu-id="1855c-143">Custodian contactEmail</span></span>      | <span data-ttu-id="1855c-144">Exchange abilitato</span><span class="sxs-lookup"><span data-stu-id="1855c-144">Exchange Enabled</span></span> | <span data-ttu-id="1855c-145">OneDrive abilitato</span><span class="sxs-lookup"><span data-stu-id="1855c-145">OneDrive Enabled</span></span> | <span data-ttu-id="1855c-146">È OnHold</span><span class="sxs-lookup"><span data-stu-id="1855c-146">Is OnHold</span></span> | <span data-ttu-id="1855c-147">Tipo di Workload1</span><span class="sxs-lookup"><span data-stu-id="1855c-147">Workload1 Type</span></span> | <span data-ttu-id="1855c-148">Percorso Workload1</span><span class="sxs-lookup"><span data-stu-id="1855c-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="1855c-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1855c-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="1855c-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="1855c-150">TRUE</span></span>             | <span data-ttu-id="1855c-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="1855c-151">TRUE</span></span>             | <span data-ttu-id="1855c-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="1855c-152">TRUE</span></span>      | <span data-ttu-id="1855c-153">SitoSharePoint</span><span class="sxs-lookup"><span data-stu-id="1855c-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="1855c-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1855c-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="1855c-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="1855c-155">TRUE</span></span>             | <span data-ttu-id="1855c-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="1855c-156">TRUE</span></span>             | <span data-ttu-id="1855c-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="1855c-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="1855c-158">Convalida del custode e dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="1855c-158">Custodian and data source validation</span></span>

<span data-ttu-id="1855c-159">Dopo aver caricato il file CSV del custode, Advanced eDiscovery esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1855c-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="1855c-160">Convalida i depositari e le rispettive origini dati.</span><span class="sxs-lookup"><span data-stu-id="1855c-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="1855c-161">Indicizza tutte le origini dati per ogni custode e le inserisce in blocco (se la proprietà **è OnHold** nel file CSV è impostata su true).</span><span class="sxs-lookup"><span data-stu-id="1855c-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="1855c-162">Convalida del custode</span><span class="sxs-lookup"><span data-stu-id="1855c-162">Custodian validation</span></span>

<span data-ttu-id="1855c-163">Attualmente, è supportata solo l'importazione di custodi che sono inclusi nell'Azure Active Directory (Azure AD) dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1855c-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="1855c-164">Lo strumento di importazione depositaria consente di individuare e convalidare i depositari utilizzando il valore UPN nella colonna **ContactEmail depositaria** nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="1855c-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="1855c-165">I depositari convalidati vengono automaticamente aggiunti al caso ed elencati nella scheda **origini dati** del caso.</span><span class="sxs-lookup"><span data-stu-id="1855c-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="1855c-166">Se un custode non può essere convalidato, sono elencati nel registro degli errori per il processo di BulkAddCustodian elencato nella scheda **processi** nel caso.</span><span class="sxs-lookup"><span data-stu-id="1855c-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="1855c-167">Gli amministratori non convalidati non vengono aggiunti al caso o sono elencati nella scheda **origini dati** .</span><span class="sxs-lookup"><span data-stu-id="1855c-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="1855c-168">Convalida dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="1855c-168">Data source validation</span></span>

<span data-ttu-id="1855c-169">Dopo aver convalidato e aggiunto i depositari al caso, viene aggiunta ogni cassetta postale principale e l'account OneDrive associato a un custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="1855c-170">Tuttavia, se non è possibile trovare una delle altre origini dati (ad esempio, siti di SharePoint, Microsoft teams, gruppi di Microsoft 365 o gruppi di Yammer) associati a un custode, nessuno di essi viene assegnato al custode e il valore **non convalidato** viene visualizzato nella colonna **stato** accanto al custode nella scheda **origini dati** .</span><span class="sxs-lookup"><span data-stu-id="1855c-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="1855c-171">Per aggiungere origini dati convalidate per un custode:</span><span class="sxs-lookup"><span data-stu-id="1855c-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="1855c-172">Nella scheda **origini dati** selezionare un custode che contiene origini dati che non vengono convalidate.</span><span class="sxs-lookup"><span data-stu-id="1855c-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="1855c-173">Nella pagina riquadro a comparsa custode, scorrere fino alla sezione **percorsi custodia** per visualizzare le origini dati convalidate e non convalidate associate al custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="1855c-174">Fare clic su **modifica** nella parte superiore della pagina a comparsa per rimuovere origini dati non valide o aggiungerne di nuove.</span><span class="sxs-lookup"><span data-stu-id="1855c-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="1855c-175">Dopo aver rimosso le origini dati non convalidate o averne aggiunto uno nuovo, il valore **attivo** viene visualizzato nella colonna **stato** per il custode nella scheda **origini dati** . Per aggiungere fonti che in precedenza risultavano non valide, seguire i passaggi di correzione riportati di seguito per aggiungerli manualmente a un custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="1855c-176">Correzione di origini dati non valide</span><span class="sxs-lookup"><span data-stu-id="1855c-176">Remediating invalid data sources</span></span>

<span data-ttu-id="1855c-177">Per aggiungere e associare manualmente un'origine dati precedentemente non valida:</span><span class="sxs-lookup"><span data-stu-id="1855c-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="1855c-178">Nella scheda **origini dati** selezionare un custode per aggiungere manualmente e associare un'origine dati precedentemente non valida.</span><span class="sxs-lookup"><span data-stu-id="1855c-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="1855c-179">Fare clic su **modifica** nella parte superiore della pagina a comparsa per associare le cassette postali, i siti, i team o i gruppi di Yammer al custode.</span><span class="sxs-lookup"><span data-stu-id="1855c-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="1855c-180">A tale scopo, fare clic su **modifica** accanto al tipo di percorso dati appropriato.</span><span class="sxs-lookup"><span data-stu-id="1855c-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="1855c-181">Fare clic su **Avanti** per visualizzare la pagina **impostazioni di blocco** e configurare l'impostazione di blocco per le origini dati aggiunte.</span><span class="sxs-lookup"><span data-stu-id="1855c-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="1855c-182">Fare clic su **Avanti** per visualizzare la pagina **revisione dei custodi** e quindi fare clic su **Submit** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1855c-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
