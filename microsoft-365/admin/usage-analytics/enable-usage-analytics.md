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
description: Informazioni su come iniziare a raccogliere dati per il tenant usando l'app modello Analisi di utilizzo di Microsoft 365 in Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114238"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="50e45-103">Abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50e45-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="50e45-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="50e45-104">The admin center is changing.</span></span> <span data-ttu-id="50e45-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="50e45-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="50e45-106">L'analisi dell'utilizzo di Microsoft 365 non è ancora disponibile per Microsoft 365 US Government Community.</span><span class="sxs-lookup"><span data-stu-id="50e45-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="50e45-107">Procedura per abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50e45-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="50e45-108">Per iniziare a usare l'analisi dell'utilizzo di Microsoft 365, è necessario prima rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365, quindi avviare l'app modello in Power BI.</span><span class="sxs-lookup"><span data-stu-id="50e45-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="50e45-109">Ottenere Power BI</span><span class="sxs-lookup"><span data-stu-id="50e45-109">Get Power BI</span></span>

<span data-ttu-id="50e45-110">Se non si dispone già di Power BI, è possibile iscriversi [a Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="50e45-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="50e45-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="50e45-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="50e45-112">È anche possibile espandere **Prodotti** per acquistare una versione di Power BI.</span><span class="sxs-lookup"><span data-stu-id="50e45-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="50e45-113">È necessaria una licenza di Power BI Pro per installare, personalizzare e distribuire un'app modello.</span><span class="sxs-lookup"><span data-stu-id="50e45-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="50e45-114">Per ulteriori informazioni, vedere [Prerequisiti.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="50e45-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="50e45-115">Per condividere i dati, sia l'utente che le persone con cui si condividono i dati, è necessaria una licenza di Power BI Pro oppure il contenuto deve essere in un'area di lavoro in un servizio [Power BI Premium.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="50e45-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="50e45-116">Abilitare l'app modello</span><span class="sxs-lookup"><span data-stu-id="50e45-116">Enable the template app</span></span>

<span data-ttu-id="50e45-117">Per abilitare l'app modello, è necessario essere un **amministratore globale.**</span><span class="sxs-lookup"><span data-stu-id="50e45-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="50e45-118">Per [ulteriori informazioni, vedere](../add-users/about-admin-roles.md) i ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="50e45-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="50e45-119">Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.</span><span class="sxs-lookup"><span data-stu-id="50e45-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="50e45-120">Nella pagina **Utilizzo** individuare la scheda Analisi di utilizzo **di Microsoft 365** e selezionare **Introduzione.**</span><span class="sxs-lookup"><span data-stu-id="50e45-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="50e45-121">Nel riquadro Report visualizzato impostare Rendi disponibili i dati per l'analisi dell'utilizzo di **Microsoft 365 per Power BI** su **Al** \> **salvataggio.**</span><span class="sxs-lookup"><span data-stu-id="50e45-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="50e45-122">Il processo di raccolta dei dati verrà completato in due-48 ore a seconda delle dimensioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="50e45-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="50e45-123">Il **pulsante Vai a Power BI** verrà abilitato (non più grigio) al termine della raccolta dei dati.</span><span class="sxs-lookup"><span data-stu-id="50e45-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="50e45-124">Avviare l'app modello</span><span class="sxs-lookup"><span data-stu-id="50e45-124">Start the template app</span></span>

<span data-ttu-id="50e45-125">Per avviare l'app modello, è necessario essere un amministratore **globale,** un lettore di **report,** un amministratore di **Exchange,** un amministratore **di Skype for Business** o un amministratore di **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="50e45-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="50e45-126">Copiare l'ID tenant e **selezionare Vai a Power BI.**</span><span class="sxs-lookup"><span data-stu-id="50e45-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="50e45-127">Dopo aver scaricato Power BI, eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="50e45-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="50e45-128">Seleziona **quindi App** per ottenere -> **app** dal menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="50e45-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="50e45-129">Nella scheda **App** digitare Microsoft 365 nella casella di ricerca e quindi selezionare Analisi di utilizzo di **Microsoft 365.** \> </span><span class="sxs-lookup"><span data-stu-id="50e45-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="50e45-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="50e45-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="50e45-131">Dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="50e45-131">Once the app is installed.</span></span> <span data-ttu-id="50e45-132">Seleziona il riquadro per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="50e45-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="50e45-133">Seleziona **Esplora app per** visualizzare l'app con dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="50e45-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="50e45-134">Scegliere **Connetti** per connettere l'app ai dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="50e45-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="50e45-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1) and select **Next**.</span><span class="sxs-lookup"><span data-stu-id="50e45-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="50e45-136">Nella schermata successiva, selezionare **OAuth2 come** **metodo di autenticazione** Per \> **accedere.**</span><span class="sxs-lookup"><span data-stu-id="50e45-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="50e45-137">Se scegli qualsiasi altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="50e45-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Scegliere l'account Microsoft come metodo di autenticazione](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="50e45-139">Dopo aver creato un'istanza dell'app modello, il dashboard di analisi dell'utilizzo di Microsoft 365 sarà disponibile in Power BI sul Web.</span><span class="sxs-lookup"><span data-stu-id="50e45-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="50e45-140">Il caricamento iniziale del dashboard può richiedere da 2 a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="50e45-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="50e45-141">Le aggregazioni a livello di tenant saranno disponibili in tutti i report dopo il consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="50e45-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="50e45-142">I dettagli a livello di utente saranno disponibili solo il **5 del mese di calendario successivo dopo aver scelto**.</span><span class="sxs-lookup"><span data-stu-id="50e45-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="50e45-143">Questo inciderà su tutti i report in Attività utente (vedere Esplorare e usare i report nell'analisi dell'utilizzo di [Microsoft 365](navigate-and-utilize-reports.md) per suggerimenti su come visualizzare e usare questi report).</span><span class="sxs-lookup"><span data-stu-id="50e45-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="50e45-144">Rendere anonimi i dati raccolti</span><span class="sxs-lookup"><span data-stu-id="50e45-144">Make the collected data anonymous</span></span>

<span data-ttu-id="50e45-145">Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="50e45-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="50e45-146">In questo modo verranno nascosti i nomi di utenti, gruppi e siti nei report e nell'app modello.</span><span class="sxs-lookup"><span data-stu-id="50e45-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="50e45-147">Nell'interfaccia di amministrazione  passare a Impostazioni organizzazione e nella scheda \> Servizi scegliere **Report.** </span><span class="sxs-lookup"><span data-stu-id="50e45-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="50e45-148">Selezionare **Report** e quindi scegliere Visualizza **identificatori anonimi.**</span><span class="sxs-lookup"><span data-stu-id="50e45-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="50e45-149">Questa impostazione viene applicata sia ai report di utilizzo che all'app modello.</span><span class="sxs-lookup"><span data-stu-id="50e45-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="50e45-150">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="50e45-150">Select **Save changes**.</span></span>
