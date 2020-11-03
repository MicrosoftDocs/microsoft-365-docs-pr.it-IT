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
ms.openlocfilehash: 0817e6441540086bf679c6533b1bad2e4087b4b9
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841458"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="724f8-103">Abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="724f8-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="724f8-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="724f8-104">The admin center is changing.</span></span> <span data-ttu-id="724f8-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="724f8-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="724f8-106">Microsoft 365 Usage Analytics non è ancora disponibile per la community di Microsoft 365 US Government.</span><span class="sxs-lookup"><span data-stu-id="724f8-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="724f8-107">Passaggi per abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="724f8-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="724f8-108">Per iniziare a utilizzare l'analisi di utilizzo di Microsoft 365, è necessario prima di tutto rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365 e quindi avviare l'app modello in Power BI.</span><span class="sxs-lookup"><span data-stu-id="724f8-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="724f8-109">Ottenere Power BI</span><span class="sxs-lookup"><span data-stu-id="724f8-109">Get Power BI</span></span>

<span data-ttu-id="724f8-110">Se non si dispone già di Power BI, è possibile [iscriversi a Power bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="724f8-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="724f8-111">Seleziona **prova gratis** per iscriversi a una versione di valutazione o **Acquista ora** per ottenere Power bi Pro.</span><span class="sxs-lookup"><span data-stu-id="724f8-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="724f8-112">È anche possibile espandere **Prodotti** per acquistare una versione di Power BI.</span><span class="sxs-lookup"><span data-stu-id="724f8-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="724f8-113">È necessaria una licenza Power BI Pro per l'installazione, la personalizzazione e la distribuzione di un'app modello.</span><span class="sxs-lookup"><span data-stu-id="724f8-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="724f8-114">Per ulteriori informazioni, vedere [prerequisiti](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="724f8-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="724f8-115">Per condividere i dati, sia lei che le persone con cui si condividono i dati, è necessaria una licenza Power BI Pro o il contenuto deve trovarsi in un'area di lavoro in un [servizio Power bi Premium](https://docs.microsoft.com/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="724f8-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="724f8-116">Abilitazione dell'app modello</span><span class="sxs-lookup"><span data-stu-id="724f8-116">Enable the template app</span></span>

<span data-ttu-id="724f8-117">Per abilitare l'app modello, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="724f8-117">To enable the template app, you have to be one of the following:</span></span> 
- <span data-ttu-id="724f8-118">**Amministratore globale**</span><span class="sxs-lookup"><span data-stu-id="724f8-118">**Global administrator**</span></span>
- <span data-ttu-id="724f8-119">**Lettore di report**</span><span class="sxs-lookup"><span data-stu-id="724f8-119">**Report reader**</span></span>
- <span data-ttu-id="724f8-120">**Amministratore di Exchange**</span><span class="sxs-lookup"><span data-stu-id="724f8-120">**Exchange administrator**</span></span>
- <span data-ttu-id="724f8-121">**Amministratore di Skype for business**</span><span class="sxs-lookup"><span data-stu-id="724f8-121">**Skype for Business administrator**</span></span>
- <span data-ttu-id="724f8-122">**Amministratore di SharePoint**</span><span class="sxs-lookup"><span data-stu-id="724f8-122">**SharePoint administrator**</span></span> 
  
<span data-ttu-id="724f8-123">Per ulteriori informazioni, vedere informazioni [sui ruoli di amministratore](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="724f8-123">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="724f8-124">Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.</span><span class="sxs-lookup"><span data-stu-id="724f8-124">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="724f8-125">Nella pagina **utilizzo** individuare la scheda **Microsoft 365 Usage Analytics** e quindi fare clic su **Avvia** .</span><span class="sxs-lookup"><span data-stu-id="724f8-125">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started** .</span></span>
    
3. <span data-ttu-id="724f8-126">Nel riquadro rapporti che si apre, impostare **rendere disponibili i dati di Microsoft 365 Usage Analytics for Power bi** to **on** \> **Save** .</span><span class="sxs-lookup"><span data-stu-id="724f8-126">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save** .</span></span> 
  
<span data-ttu-id="724f8-127">Il processo di raccolta dei dati verrà completato in due o 48 ore, a seconda delle dimensioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="724f8-127">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="724f8-128">Il pulsante **Vai a Power bi** verrà abilitato (non più grigio) quando la raccolta dati è stata completata.</span><span class="sxs-lookup"><span data-stu-id="724f8-128">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="724f8-129">Avviare l'app modello</span><span class="sxs-lookup"><span data-stu-id="724f8-129">Start the template app</span></span>

<span data-ttu-id="724f8-130">Per avviare l'app modello, è necessario essere un **amministratore globale** , un **lettore di report** , un **amministratore di Exchange** , un amministratore **di Skype for business** o un **amministratore di SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="724f8-130">To start the template app, you have to be either a **global administrator** , **report reader** , **Exchange administrator** , **Skype for Business administrator** , or **SharePoint administrator** .</span></span> 
  
1. <span data-ttu-id="724f8-131">Copiare l'ID tenant e selezionare **Vai a Power bi** .</span><span class="sxs-lookup"><span data-stu-id="724f8-131">Copy the tenant ID and select **Go to Power BI** .</span></span>
    
2.  <span data-ttu-id="724f8-132">Dopo aver scaricato Power BI, eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="724f8-132">When you get to Power BI, sign in.</span></span> <span data-ttu-id="724f8-133">Quindi **Seleziona app** -> per **ottenere app** dal menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="724f8-133">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="724f8-134">Nella scheda **app** Digitare Microsoft 365 nella casella di ricerca e quindi selezionare **Analisi utilizzo Microsoft 365** \> **ottenerlo subito** .</span><span class="sxs-lookup"><span data-stu-id="724f8-134">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now** .</span></span>

    <span data-ttu-id="724f8-135">[![Seleziona Ottieni subito](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="724f8-135">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="724f8-136">Dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="724f8-136">Once the app is installed.</span></span> <span data-ttu-id="724f8-137">Selezionare il riquadro per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="724f8-137">Select the tile to open it.</span></span>

5.  <span data-ttu-id="724f8-138">Selezionare **Esplora app** per visualizzare l'app con dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="724f8-138">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="724f8-139">Scegliere **Connect** per connettere l'app ai dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="724f8-139">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="724f8-140">Scegliere **Connect** , nella schermata **connetti a Microsoft 365 Usage Analytics** , quindi digitare l'ID tenant (senza trattini) copiato nel passaggio (1), quindi selezionare **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="724f8-140">Choose **Connect** , on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next** .</span></span>
    
7. <span data-ttu-id="724f8-141">Nella schermata successiva, selezionare **OAuth2** come accesso al **Metodo** \> **di** autenticazione.</span><span class="sxs-lookup"><span data-stu-id="724f8-141">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in** .</span></span> <span data-ttu-id="724f8-142">Se si sceglie qualsiasi altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="724f8-142">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Scegliere l'account Microsoft come metodo di autenticazione](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="724f8-144">Dopo aver creato un'istanza dell'app modello, il Dashboard Microsoft 365 Usage Analytics sarà disponibile in Power BI sul Web.</span><span class="sxs-lookup"><span data-stu-id="724f8-144">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="724f8-145">Il caricamento iniziale del dashboard richiederà da 2 a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="724f8-145">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="724f8-146">Le aggregazioni a livello di tenant saranno disponibili in tutti i report.</span><span class="sxs-lookup"><span data-stu-id="724f8-146">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="724f8-147">I **dettagli a livello di utente diventeranno disponibili solo dopo il 1 ° o 15 ° giorno del mese di calendario dopo l'opt-in** .</span><span class="sxs-lookup"><span data-stu-id="724f8-147">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in** .</span></span> <span data-ttu-id="724f8-148">Ciò avrà un impatto su tutti i report in attività utente.</span><span class="sxs-lookup"><span data-stu-id="724f8-148">This will impact all reports under User Activity.</span></span> <span data-ttu-id="724f8-149">Per suggerimenti su come visualizzare e utilizzare i report, vedere [esplorazione e utilizzo dei report in Microsoft 365 Usage Analytics](navigate-and-utilize-reports.md) .</span><span class="sxs-lookup"><span data-stu-id="724f8-149">See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports.</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="724f8-150">Rendere anonimi i dati raccolti</span><span class="sxs-lookup"><span data-stu-id="724f8-150">Make the collected data anonymous</span></span>

<span data-ttu-id="724f8-151">Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="724f8-151">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="724f8-152">In questo modo vengono nascoste informazioni identificabili, ad esempio i nomi di utenti, gruppi e siti, nei report e nell'app modello.</span><span class="sxs-lookup"><span data-stu-id="724f8-152">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="724f8-153">Nell'interfaccia di amministrazione passare alla **pagina Impostazioni** \> **organizzazione** e quindi in scheda **Servizi** scegliere **report** .</span><span class="sxs-lookup"><span data-stu-id="724f8-153">In the admin center, go to the **Settings** \> **Org Settings** , and under **Services** tab, choose **Reports** .</span></span>
    
2. <span data-ttu-id="724f8-154">Selezionare **report** , quindi scegliere di **visualizzare gli identificatori anonimi** .</span><span class="sxs-lookup"><span data-stu-id="724f8-154">Select **Reports** , and then choose to **Display anonymous identifiers** .</span></span> <span data-ttu-id="724f8-155">Questa impostazione viene applicata sia ai report sull'utilizzo che all'app modello.</span><span class="sxs-lookup"><span data-stu-id="724f8-155">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="724f8-156">Selezionare **Salva modifiche** .</span><span class="sxs-lookup"><span data-stu-id="724f8-156">Select **Save changes** .</span></span>
