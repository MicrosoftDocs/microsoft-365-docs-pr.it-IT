---
title: Abilitare l'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Informazioni su come avviare la raccolta dei dati per il tenant utilizzando l'app modello di analisi di utilizzo di Microsoft 365 in Power BI.
ms.openlocfilehash: 20228b0e2070065834ce203e22af619480311367
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502950"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b285b-103">Abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b285b-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b285b-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="b285b-104">The admin center is changing.</span></span> <span data-ttu-id="b285b-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b285b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b285b-106">Microsoft 365 Usage Analytics non è ancora disponibile per la community di Microsoft 365 US Government.</span><span class="sxs-lookup"><span data-stu-id="b285b-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b285b-107">Passaggi per abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b285b-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="b285b-108">Per iniziare a utilizzare l'analisi di utilizzo di Microsoft 365, è necessario prima di tutto rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365 e quindi avviare l'app modello in Power BI.</span><span class="sxs-lookup"><span data-stu-id="b285b-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="b285b-109">Ottenere Power BI</span><span class="sxs-lookup"><span data-stu-id="b285b-109">Get Power BI</span></span>

<span data-ttu-id="b285b-110">Se non si dispone già di Power BI, è possibile [iscriversi a Power bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="b285b-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="b285b-111">Seleziona **prova gratis** per iscriversi a una versione di valutazione o **Acquista ora** per ottenere Power bi Pro.</span><span class="sxs-lookup"><span data-stu-id="b285b-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="b285b-112">È anche possibile espandere **Prodotti** per acquistare una versione di Power BI.</span><span class="sxs-lookup"><span data-stu-id="b285b-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="b285b-113">È necessaria una licenza Power BI Pro per l'installazione, la personalizzazione e la distribuzione di un'app modello.</span><span class="sxs-lookup"><span data-stu-id="b285b-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="b285b-114">Per ulteriori informazioni, vedere [prerequisiti](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="b285b-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="b285b-115">È necessaria una licenza Power BI Pro per condividere il contenuto e le persone con cui condividerlo o il contenuto deve trovarsi in un'area di lavoro con una [capacità Premium](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="b285b-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="b285b-116">Abilitazione dell'app modello</span><span class="sxs-lookup"><span data-stu-id="b285b-116">Enable the template app</span></span>

<span data-ttu-id="b285b-117">Per abilitare l'app modello, è necessario essere un **amministratore globale**, un **lettore di report**, un **amministratore di Exchange**, un amministratore **di Skype for business**o un **amministratore di SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b285b-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="b285b-118">Per ulteriori informazioni, vedere informazioni [sui ruoli di amministratore](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="b285b-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="b285b-119">Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.</span><span class="sxs-lookup"><span data-stu-id="b285b-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="b285b-120">Nella pagina **utilizzo** individuare la scheda **Microsoft 365 Usage Analytics** e quindi fare clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="b285b-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="b285b-121">Nel riquadro rapporti che si apre, impostare **rendere disponibili i dati di Microsoft 365 Usage Analytics for Power bi** to **on** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="b285b-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="b285b-122">In questo modo viene avviato il processo di raccolta dei dati e il completamento verrà eseguito tra 2 e 48 ore, a seconda delle dimensioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="b285b-122">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="b285b-123">Il pulsante **Vai a Power bi** verrà abilitato (non più grigio) quando la raccolta dati è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b285b-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="b285b-124">Avviare l'app modello</span><span class="sxs-lookup"><span data-stu-id="b285b-124">Initiate the template app</span></span>

<span data-ttu-id="b285b-125">Per avviare l'app modello, è necessario essere un **amministratore globale**, un lettore di **report**, un **amministratore di Exchange**, un amministratore **di Skype for business**o un **amministratore di SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b285b-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="b285b-126">Copiare l'ID tenant e selezionare **Vai a Power bi**.</span><span class="sxs-lookup"><span data-stu-id="b285b-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="b285b-127">Dopo aver scaricato Power BI, eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b285b-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="b285b-128">Seleziona app->Ottieni app dal menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="b285b-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="b285b-129">Nella scheda **app** Digitare Microsoft 365 nella casella di ricerca e quindi selezionare **Analisi utilizzo Microsoft 365** \> **ottenerlo subito**.</span><span class="sxs-lookup"><span data-stu-id="b285b-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="b285b-130">[![Seleziona Ottieni subito](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="b285b-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="b285b-131">Dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="b285b-131">Once the app is installed.</span></span> <span data-ttu-id="b285b-132">Fare clic sul riquadro per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b285b-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="b285b-133">Fare clic su **Esplora app** per visualizzare l'app con dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="b285b-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="b285b-134">Fare clic su **Connetti** per connettere l'app ai dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b285b-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="b285b-135">Dopo aver fatto clic su **Connetti**, nella schermata **connetti a Microsoft 365 Usage Analytics** digitare l'ID tenant (senza trattini) copiato nel passaggio (1) e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b285b-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="b285b-136">Nella schermata successiva, selezionare **OAuth2** come accesso al **Metodo** \> **di**autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b285b-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="b285b-137">Se si sceglie qualsiasi altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b285b-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="b285b-139">Dopo aver creato un'istanza dell'app modello, il Dashboard Microsoft 365 Usage Analytics sarà disponibile in Power BI sul Web.</span><span class="sxs-lookup"><span data-stu-id="b285b-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="b285b-140">Il caricamento iniziale del dashboard richiederà da 2 a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="b285b-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="b285b-141">Le aggregazioni a livello di tenant saranno disponibili in tutti i report.</span><span class="sxs-lookup"><span data-stu-id="b285b-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="b285b-142">I **dettagli a livello di utente diventeranno disponibili solo dopo il 1 ° o 15 ° giorno del mese di calendario dopo l'opt-in**.</span><span class="sxs-lookup"><span data-stu-id="b285b-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="b285b-143">Questo influirà su tutti i report in attività utente (vedere [navigare e utilizzare i report di analisi di utilizzo di Microsoft 365](navigate-and-utilize-reports.md) per suggerimenti su come visualizzare e utilizzare questi report).</span><span class="sxs-lookup"><span data-stu-id="b285b-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="b285b-144">Rendere anonimi i dati raccolti</span><span class="sxs-lookup"><span data-stu-id="b285b-144">Make the collected data anonymous</span></span>

<span data-ttu-id="b285b-145">Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b285b-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="b285b-146">In questo modo vengono nascoste informazioni identificabili, ad esempio i nomi di utenti, gruppi e siti, nei report e nell'app modello.</span><span class="sxs-lookup"><span data-stu-id="b285b-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="b285b-147">Nell'interfaccia di amministrazione passare alla **pagina Impostazioni** \> **organizzazione**e quindi in scheda **Servizi** scegliere **report**.</span><span class="sxs-lookup"><span data-stu-id="b285b-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="b285b-148">Selezionare **report**, quindi scegliere di **visualizzare gli identificatori anonimi**.</span><span class="sxs-lookup"><span data-stu-id="b285b-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="b285b-149">Questa impostazione viene applicata sia ai report sull'utilizzo che all'app modello.</span><span class="sxs-lookup"><span data-stu-id="b285b-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="b285b-150">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="b285b-150">Select **Save changes**.</span></span>
