---
title: Abilitare l'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Scopri come iniziare a raccogliere dati per il tenant usando l'app Microsoft 365 modello Analisi di utilizzo in Power BI.
ms.openlocfilehash: 329878365aa07da4615a849ad04cde7f75a07872
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593370"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c3d20-103">Abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3d20-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="c3d20-104">Microsoft 365'analisi dei dati di utilizzo non è ancora disponibile per Microsoft 365 per il governo Community.</span><span class="sxs-lookup"><span data-stu-id="c3d20-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c3d20-105">Passaggi per abilitare l'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3d20-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="c3d20-106">Per iniziare a usare Microsoft 365 di utilizzo, devi prima rendere disponibili i dati nell'interfaccia di amministrazione di Microsoft 365, quindi avviare l'app modello in Power BI.</span><span class="sxs-lookup"><span data-stu-id="c3d20-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="c3d20-107">Ottenere Power BI</span><span class="sxs-lookup"><span data-stu-id="c3d20-107">Get Power BI</span></span>

<span data-ttu-id="c3d20-108">Se non si dispone già di Power BI, è possibile iscriversi [a Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="c3d20-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="c3d20-109">Seleziona **Prova gratuitamente** per iscriverti a una versione di valutazione o Acquista ora per ottenere Power BI Pro. </span><span class="sxs-lookup"><span data-stu-id="c3d20-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="c3d20-110">È anche possibile espandere **Prodotti** per acquistare una versione di Power BI.</span><span class="sxs-lookup"><span data-stu-id="c3d20-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="c3d20-111">È necessaria una licenza Power BI Pro per installare, personalizzare e distribuire un'app modello.</span><span class="sxs-lookup"><span data-stu-id="c3d20-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="c3d20-112">Per ulteriori informazioni, vedere [Prerequisiti](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c3d20-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="c3d20-113">Per condividere i dati, sia l'utente che le persone con cui si condividono i dati, è necessaria una licenza di Power BI Pro o il contenuto deve essere in un'area di lavoro in un servizio [premium di Power BI](/power-bi/service-premium-what-is).</span><span class="sxs-lookup"><span data-stu-id="c3d20-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="c3d20-114">Abilitare l'app modello</span><span class="sxs-lookup"><span data-stu-id="c3d20-114">Enable the template app</span></span>

<span data-ttu-id="c3d20-115">Per abilitare l'app modello, devi essere un **amministratore globale.**</span><span class="sxs-lookup"><span data-stu-id="c3d20-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="c3d20-116">Per [ulteriori informazioni, vedere](../add-users/about-admin-roles.md) Sui ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c3d20-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="c3d20-117">Nell'interfaccia di amministrazione passare alla scheda **Impostazioni** \> **Impostazioni organizzazione** \> **Servizi.**</span><span class="sxs-lookup"><span data-stu-id="c3d20-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span> 
    
2. <span data-ttu-id="c3d20-118">Nella scheda **Servizi** selezionare  **Report**.</span><span class="sxs-lookup"><span data-stu-id="c3d20-118">On the **Services** tab, select  **Reports**.</span></span>
    
3. <span data-ttu-id="c3d20-119">Nel riquadro Report che si apre imposta Rendi disponibili i dati del **report** Microsoft 365 analisi di utilizzo per Power BI su **Al** \> **salvataggio.**</span><span class="sxs-lookup"><span data-stu-id="c3d20-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="c3d20-120">Il processo di raccolta dei dati verrà completato in due-48 ore a seconda delle dimensioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="c3d20-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="c3d20-121">Il **pulsante Vai a Power BI** verrà abilitato (non più grigio) al termine della raccolta dei dati.</span><span class="sxs-lookup"><span data-stu-id="c3d20-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="c3d20-122">Avviare l'app modello</span><span class="sxs-lookup"><span data-stu-id="c3d20-122">Start the template app</span></span>

<span data-ttu-id="c3d20-123">Per avviare l'app modello, devi essere un amministratore **globale,** un lettore di **report,** Exchange **amministratore,** Skype for Business **amministratore** o SharePoint **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="c3d20-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="c3d20-124">Copiare l'ID tenant e **selezionare Vai a Power BI**.</span><span class="sxs-lookup"><span data-stu-id="c3d20-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="c3d20-125">Dopo aver scaricato Power BI, eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c3d20-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="c3d20-126">Seleziona **Quindi App** Ottieni -> **app** dal menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="c3d20-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="c3d20-127">Nella scheda **App** digita Microsoft 365 nella casella di ricerca e quindi seleziona Microsoft 365 analisi di **utilizzo** \> **Scarica ora**.</span><span class="sxs-lookup"><span data-stu-id="c3d20-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="c3d20-128">[![Seleziona Scarica ora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="c3d20-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="c3d20-129">Dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="c3d20-129">Once the app is installed.</span></span> <span data-ttu-id="c3d20-130">Seleziona il riquadro per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="c3d20-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="c3d20-131">Seleziona **Esplora app per** visualizzare l'app con dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="c3d20-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="c3d20-132">Scegli **Connessione** per connettere l'app ai dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3d20-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="c3d20-133">Scegliere **Connessione**, nella  schermata Connessione per Microsoft 365 analisi di utilizzo, quindi digitare l'ID tenant (senza trattini) copiato nel passaggio (1) e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c3d20-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="c3d20-134">Nella schermata successiva, selezionare **OAuth2 come** **metodo di autenticazione** \> **Accedi.**</span><span class="sxs-lookup"><span data-stu-id="c3d20-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="c3d20-135">Se scegli un altro metodo di autenticazione, la connessione all'app modello avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c3d20-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Scegliere l'account Microsoft come metodo di autenticazione](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="c3d20-137">Dopo aver creato un'istanza dell'app modello, Microsoft 365 dashboard di analisi dell'utilizzo sarà disponibile in Power BI sul Web.</span><span class="sxs-lookup"><span data-stu-id="c3d20-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="c3d20-138">Il caricamento iniziale del dashboard avrà un tempo compreso tra 2 e 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="c3d20-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="c3d20-139">Le aggregazioni a livello di tenant saranno disponibili in tutti i report dopo aver acconsentto esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="c3d20-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="c3d20-140">I dettagli a livello di utente saranno disponibili solo il **5 del mese di calendario successivo dopo aver scelto**.</span><span class="sxs-lookup"><span data-stu-id="c3d20-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="c3d20-141">Ciò inciderà su tutti i report in Attività utente (vedere Esplorare e utilizzare i report [in](navigate-and-utilize-reports.md) analisi di utilizzo di Microsoft 365 per suggerimenti su come visualizzare e usare questi report).</span><span class="sxs-lookup"><span data-stu-id="c3d20-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="c3d20-142">Rendere anonimi i dati raccolti</span><span class="sxs-lookup"><span data-stu-id="c3d20-142">Make the collected data anonymous</span></span>

<span data-ttu-id="c3d20-143">Per rendere anonimi i dati raccolti per tutti i report è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c3d20-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="c3d20-144">In questo modo si nasconderanno informazioni identificabili come i nomi di utenti, gruppi e siti nei report e nell'app modello.</span><span class="sxs-lookup"><span data-stu-id="c3d20-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="c3d20-145">Nell'interfaccia di amministrazione  passare alla Impostazioni Org Impostazioni e nella scheda Servizi \> scegliere **Report.** </span><span class="sxs-lookup"><span data-stu-id="c3d20-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="c3d20-146">Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**.</span><span class="sxs-lookup"><span data-stu-id="c3d20-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="c3d20-147">Questa impostazione viene applicata sia ai report di utilizzo che all'app modello.</span><span class="sxs-lookup"><span data-stu-id="c3d20-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="c3d20-148">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="c3d20-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="c3d20-149">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c3d20-149">Related content</span></span>

<span data-ttu-id="c3d20-150">[Informazioni sull'analisi dei dati](usage-analytics.md) di utilizzo (articolo)</span><span class="sxs-lookup"><span data-stu-id="c3d20-150">[About usage analytics](usage-analytics.md) (article)</span></span>

<span data-ttu-id="c3d20-151">[Ottenere la versione più recente dell'analisi dei dati di utilizzo](get-the-latest-version-of-usage-analytics.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c3d20-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>

<span data-ttu-id="c3d20-152">[Esplorare e utilizzare i report nell'Microsoft 365 di utilizzo](navigate-and-utilize-reports.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c3d20-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>