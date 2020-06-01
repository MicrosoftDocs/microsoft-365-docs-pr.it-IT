---
title: Aggiungere in blocco i depositari a un caso avanzato di eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432439"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="7dca3-102">Aggiungere in blocco i depositari a un caso di eDiscovery avanzato (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7dca3-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="7dca3-103">Per i casi di eDiscovery avanzati che coinvolgono numerosi depositari, è possibile importare più depositari contemporaneamente in un file CSV che contiene tutte le informazioni necessarie per aggiungerle a un caso.</span><span class="sxs-lookup"><span data-stu-id="7dca3-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="7dca3-104">Aggiungere in blocco i depositari</span><span class="sxs-lookup"><span data-stu-id="7dca3-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="7dca3-105">Immettere il caso e passare alla scheda **origini** .</span><span class="sxs-lookup"><span data-stu-id="7dca3-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="7dca3-106">Fare clic su **Importa depositari**</span><span class="sxs-lookup"><span data-stu-id="7dca3-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="7dca3-107">Nella pagina riquadro a comparsa, fare clic su **Scarica un modello vuoto** per scaricare un file del modello del custode CSV.</span><span class="sxs-lookup"><span data-stu-id="7dca3-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="7dca3-108">Aggiungere le informazioni di custodia al file CSV e salvarlo nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="7dca3-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="7dca3-109">Per informazioni sulle proprietà del file CSV, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="7dca3-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="7dca3-110">Nella scheda **origini** fare clic di nuovo su **Importa depositari** .</span><span class="sxs-lookup"><span data-stu-id="7dca3-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="7dca3-111">Nella pagina riquadro a comparsa fare clic su **Sfoglia** e caricare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="7dca3-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="7dca3-112">Dopo il caricamento del file CSV, viene creato e visualizzato un processo di BulkAddCustodian nella scheda **processi** . Il processo consente di convalidare i depositari e le origini dati corrispondenti e quindi di aggiungerli alla scheda **depositari** nella pagina **origini** del caso.</span><span class="sxs-lookup"><span data-stu-id="7dca3-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="7dca3-113">File CSV del custode</span><span class="sxs-lookup"><span data-stu-id="7dca3-113">Custodian CSV file</span></span>

<span data-ttu-id="7dca3-114">Dopo aver scaricato il modello CSV, è possibile aggiungere depositari e l'origine dati in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="7dca3-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="7dca3-115">Assicurarsi di non modificare i nomi delle colonne nella riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="7dca3-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="7dca3-116">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7dca3-116">Column name</span></span>|<span data-ttu-id="7dca3-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7dca3-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="7dca3-118">**ContactEmail custode**</span><span class="sxs-lookup"><span data-stu-id="7dca3-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="7dca3-119">Indirizzo di posta elettronica UPN del custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-119">UPN email of custodian.</span></span> <span data-ttu-id="7dca3-120">Esempio: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7dca3-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="7dca3-121">**Exchange abilitato**</span><span class="sxs-lookup"><span data-stu-id="7dca3-121">**Exchange Enabled**</span></span> | <span data-ttu-id="7dca3-122">Valore TRUE/FALSE se si desidera aggiungere la cassetta postale del custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="7dca3-123">**OneDrive abilitato**</span><span class="sxs-lookup"><span data-stu-id="7dca3-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="7dca3-124">Valore vero/falso se si desidera aggiungere l'account OneDrive for business del custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="7dca3-125">**È OnHold**</span><span class="sxs-lookup"><span data-stu-id="7dca3-125">**Is OnHold**</span></span>        | <span data-ttu-id="7dca3-126">Valore TRUE/FALSE se si desidera che il custode venga premuto.</span><span class="sxs-lookup"><span data-stu-id="7dca3-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="7dca3-127">**Tipo di Workload1**</span><span class="sxs-lookup"><span data-stu-id="7dca3-127">**Workload1 Type**</span></span>         | <span data-ttu-id="7dca3-128">Valore stringa che indica il tipo di origine dati da associare al custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="7dca3-129">I valori possibili includono:</span><span class="sxs-lookup"><span data-stu-id="7dca3-129">Possible values include:</span></span> <br /><span data-ttu-id="7dca3-130">ExchangeMailbox, SitoSharePoint, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="7dca3-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="7dca3-131">**Percorso Workload1**</span><span class="sxs-lookup"><span data-stu-id="7dca3-131">**Workload1 Location**</span></span>     | <span data-ttu-id="7dca3-132">A seconda del tipo di carico di lavoro, si tratta del percorso dei dati del carico di lavoro, ad esempio l'indirizzo di posta elettronica di una cassetta postale di Exchange o l'URL di un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7dca3-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="7dca3-133">Di seguito è riportato un esempio di file CSV con informazioni sul custode:</span><span class="sxs-lookup"><span data-stu-id="7dca3-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="7dca3-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="7dca3-134">ContactEmail</span></span>      | <span data-ttu-id="7dca3-135">Exchange abilitato</span><span class="sxs-lookup"><span data-stu-id="7dca3-135">Exchange Enabled</span></span> | <span data-ttu-id="7dca3-136">OneDrive abilitato</span><span class="sxs-lookup"><span data-stu-id="7dca3-136">OneDrive Enabled</span></span> | <span data-ttu-id="7dca3-137">È OnHold</span><span class="sxs-lookup"><span data-stu-id="7dca3-137">Is OnHold</span></span> | <span data-ttu-id="7dca3-138">Tipo di Workload1</span><span class="sxs-lookup"><span data-stu-id="7dca3-138">Workload1 Type</span></span> | <span data-ttu-id="7dca3-139">Percorso Workload1</span><span class="sxs-lookup"><span data-stu-id="7dca3-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="7dca3-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7dca3-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="7dca3-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dca3-141">TRUE</span></span>             | <span data-ttu-id="7dca3-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dca3-142">TRUE</span></span>             | <span data-ttu-id="7dca3-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dca3-143">TRUE</span></span>      | <span data-ttu-id="7dca3-144">SitoSharePoint</span><span class="sxs-lookup"><span data-stu-id="7dca3-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="7dca3-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7dca3-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="7dca3-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dca3-146">TRUE</span></span>             | <span data-ttu-id="7dca3-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dca3-147">TRUE</span></span>             | <span data-ttu-id="7dca3-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="7dca3-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="7dca3-149">Convalida del custode e dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="7dca3-149">Custodian and data source validation</span></span>

<span data-ttu-id="7dca3-150">Quando si carica il file CSV del custode, Advanced eDiscovery esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dca3-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="7dca3-151">Convalida i depositari e le rispettive origini dati.</span><span class="sxs-lookup"><span data-stu-id="7dca3-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="7dca3-152">Indicizza tutte le origini dati per ogni custode e le inserisce in blocco (se la proprietà è OnHold è impostata su TRUE).</span><span class="sxs-lookup"><span data-stu-id="7dca3-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="7dca3-153">Convalida del custode</span><span class="sxs-lookup"><span data-stu-id="7dca3-153">Custodian validation</span></span>

<span data-ttu-id="7dca3-154">Attualmente, è supportata solo l'importazione di depositari che si trovano in Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="7dca3-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="7dca3-155">È possibile convalidare e trovare i depositari utilizzando il valore UPN nella colonna **posta elettronica di contatto** nel file CSV.</span><span class="sxs-lookup"><span data-stu-id="7dca3-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="7dca3-156">I depositari convalidati vengono automaticamente aggiunti al caso ed elencati nella scheda **depositaria** nella pagina **origini** del caso.</span><span class="sxs-lookup"><span data-stu-id="7dca3-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="7dca3-157">Se un custode non può essere convalidato, sono elencati nel registro degli errori per il processo di BulkAddCustodian elencato nella scheda **processi** nel caso.</span><span class="sxs-lookup"><span data-stu-id="7dca3-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="7dca3-158">Gli amministratori non convalidati non vengono aggiunti al caso.</span><span class="sxs-lookup"><span data-stu-id="7dca3-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="7dca3-159">Convalida dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="7dca3-159">Data source validation</span></span>

<span data-ttu-id="7dca3-160">Dopo aver convalidato i depositari e averne aggiunto il caso, viene convalidata ogni origine dati associata a un custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="7dca3-161">Se non è possibile trovare un'origine dati per un custode, il valore **non convalidato** verrebbe visualizzato nella colonna **convalidata** nella scheda **depositaria** per tale custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="7dca3-162">Correzione di origini dati non convalidate</span><span class="sxs-lookup"><span data-stu-id="7dca3-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="7dca3-163">Per correggere i depositari con origini dati non convalidate:</span><span class="sxs-lookup"><span data-stu-id="7dca3-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="7dca3-164">Nella scheda **custode** selezionare un custode che non è stato convalidato.</span><span class="sxs-lookup"><span data-stu-id="7dca3-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="7dca3-165">Nella pagina a comparsa del custode, scorrere fino alla sezione **origini dati** per visualizzare le origini dati associate al custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="7dca3-166">Sono elencate le origini dati convalidate e non convalidate.</span><span class="sxs-lookup"><span data-stu-id="7dca3-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="7dca3-167">Nella sezione **origini dati** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="7dca3-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="7dca3-168">Nella pagina **scegliere i percorsi di custodia** rimuovere un'origine dati non convalidata.</span><span class="sxs-lookup"><span data-stu-id="7dca3-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="7dca3-169">Nella pagina **Seleziona percorsi aggiuntivi** fare clic su **Aggiorna** per aggiungere origini dati aggiuntive per un custode.</span><span class="sxs-lookup"><span data-stu-id="7dca3-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
