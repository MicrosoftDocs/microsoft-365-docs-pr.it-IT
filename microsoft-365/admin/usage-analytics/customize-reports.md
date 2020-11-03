---
title: Personalizzare i report nell'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- NOCSH
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
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Informazioni su come personalizzare i report nel desktop del browser e Power BI.
ms.openlocfilehash: 8baeb1a9f48d8f1ccdb591a60fefe863502344b6
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841424"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="56c5b-103">Personalizzare i report nell'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56c5b-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="56c5b-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="56c5b-104">The admin center is changing.</span></span> <span data-ttu-id="56c5b-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="56c5b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="56c5b-106">Microsoft 365 Usage Analytics fornisce un dashboard in Power BI che offre informazioni su come gli utenti adottano e utilizzano Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56c5b-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="56c5b-107">Il dashboard è solo un punto di partenza per interagire con i dati di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="56c5b-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="56c5b-108">Le informazioni contenute nei report possono essere personalizzate.</span><span class="sxs-lookup"><span data-stu-id="56c5b-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="56c5b-109">È anche possibile usare Power BI Desktop per personalizzare ulteriormente i report collegandoli ad altre origini dati per ricavare informazioni utili e più complete sull'attività aziendale.</span><span class="sxs-lookup"><span data-stu-id="56c5b-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="56c5b-110">Personalizzazione dei report nel browser</span><span class="sxs-lookup"><span data-stu-id="56c5b-110">Customizing reports in the browser</span></span>

<span data-ttu-id="56c5b-111">I due esempi seguenti illustrano come modificare un oggetto visivo esistente e come creare un nuovo oggetto visivo.</span><span class="sxs-lookup"><span data-stu-id="56c5b-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="56c5b-112">Modificare un oggetto visivo esistente</span><span class="sxs-lookup"><span data-stu-id="56c5b-112">Modify an existing visual</span></span>

<span data-ttu-id="56c5b-113">In questo esempio viene illustrato come modificare la scheda **attivazione** all'interno del rapporto di **attivazione/gestione licenze** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="56c5b-114">All'interno del rapporto di **attivazione/gestione delle licenze** selezionare la scheda **attivazione** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-114">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="56c5b-115">Immettere la modalità di modifica scegliendo il pulsante **modifica** nella parte superiore tramite il pulsante ![ altro pagina nel pulsante Power bi ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) .</span><span class="sxs-lookup"><span data-stu-id="56c5b-115">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="56c5b-117">In alto a destra, scegliere **Duplica questa pagina** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-117">On the top right, choose **Duplicate this page** .</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="56c5b-119">In basso a destra, scegliere uno qualsiasi dei grafici a barre che mostra il numero di utenti che si attivano in base al sistema operativo, ad esempio Android, iOS, Mac e così via.</span><span class="sxs-lookup"><span data-stu-id="56c5b-119">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="56c5b-120">Nell'area **visualizzazioni** a destra, per rimuovere **Mac count** dalla visualizzazione, selezionare la **X** accanto ad essa.</span><span class="sxs-lookup"><span data-stu-id="56c5b-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Rimuovi conteggio Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="56c5b-122">Creare un nuovo oggetto visivo</span><span class="sxs-lookup"><span data-stu-id="56c5b-122">Create a new visual</span></span>

<span data-ttu-id="56c5b-123">L'esempio seguente illustra come creare un nuovo oggetto visivo per tenere traccia di nuovi utenti di Yammer su base mensile.</span><span class="sxs-lookup"><span data-stu-id="56c5b-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="56c5b-124">Accedere al report **sull'utilizzo del prodotto** usando il NAV sinistro e selezionare la scheda **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-124">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="56c5b-125">Passare alla modalità di modifica scegliendo ![ il pulsante altro pagina in Power bi ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) e **modifica** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-125">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit** .</span></span> 
    
3. <span data-ttu-id="56c5b-126">Nella parte inferiore della pagina, seleziona il</span><span class="sxs-lookup"><span data-stu-id="56c5b-126">At the bottom of the page, select the</span></span> ![Pulsante Aggiungi pagina in Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="56c5b-128">per creare una nuova pagina.</span><span class="sxs-lookup"><span data-stu-id="56c5b-128">to create a new page.</span></span>
  
4. <span data-ttu-id="56c5b-129">Nell'area **visualizzazioni** a destra scegliere il grafico a barre in **Pila** (riga superiore, primo da sinistra).</span><span class="sxs-lookup"><span data-stu-id="56c5b-129">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Seleziona grafico a barre](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="56c5b-131">Selezionare l'angolo inferiore destro della visualizzazione e trascinarlo per renderlo più grande.</span><span class="sxs-lookup"><span data-stu-id="56c5b-131">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="56c5b-132">Nell'area **campi** a destra espandere la tabella **Calendario** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="56c5b-133">Trascinare **MonthName** nell'area campi, direttamente sotto l'intestazione **Asse** nell'area **Visualizzazioni** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Nome del mese di trascinamento](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="56c5b-135">Nell'area **Campi** a destra espandere la tabella **TenantProductUsage** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="56c5b-136">Trascinare **FirstTimeUsers** nell'area campi, direttamente sotto l'intestazione **Valore** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="56c5b-137">Trascinare **Prodotto** nell'area **Filtri** , direttamente sotto l'intestazione **Filtri a livello di oggetto visivo** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="56c5b-138">Nell'area **Tipo di filtro** che viene visualizzata, selezionare la casella di controllo **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Selezionare la casella di controllo Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="56c5b-140">Appena sotto l'elenco delle visualizzazioni, scegliere l'icona **formato** formato icona ![ in Power bi Visualizaions ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .</span><span class="sxs-lookup"><span data-stu-id="56c5b-140">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="56c5b-141">Espandere Titolo e cambiare il valore **Testo titolo** in **Nuovi utenti di Yammer per mese** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month** .</span></span>
    
14. <span data-ttu-id="56c5b-142">Cambiare il valore **Dimensione testo** in **12** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-142">Change the **Text Size** value to **12** .</span></span>
    
15. <span data-ttu-id="56c5b-143">Modificare il titolo della nuova pagina modificando il nome della pagina in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="56c5b-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="56c5b-144">Salvare il rapporto facendo clic sulla **visualizzazione lettura** in alto e quindi su **Salva** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-144">Save out the report by Clicking on **Reading View** on top and then **Save** .</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="56c5b-145">Personalizzazione dei report in Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="56c5b-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="56c5b-p103">Per la maggior parte dei clienti è sufficiente modificare i report e gli oggetti visivi grafico in Power BI sul Web. Per alcuni, tuttavia, potrebbe essere necessario unire questi dati con altre origini dati per ricavare informazioni utili e più complete relative al contesto della propria azienda, nel qual caso è possibile personalizzare e creare report aggiuntivi con Power BI Desktop. È possibile scaricare [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) gratis.</span><span class="sxs-lookup"><span data-stu-id="56c5b-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="56c5b-149">Usare le API Reporting</span><span class="sxs-lookup"><span data-stu-id="56c5b-149">Use the reporting APIs</span></span>

<span data-ttu-id="56c5b-150">È possibile iniziare collegandosi direttamente alle API di Reporting ODATA da Microsoft 365 che alimentano questi rapporti.</span><span class="sxs-lookup"><span data-stu-id="56c5b-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="56c5b-151">Passare a **Recupera dati** \> **Altro** \> **Feed OData** \> **Connetti** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect** .</span></span>
    
2. <span data-ttu-id="56c5b-152">Nella finestra URL immettere "https:// <i></i> Reports.Office.com/PBI/V1.0/ \<tenantid\> "</span><span class="sxs-lookup"><span data-stu-id="56c5b-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="56c5b-153">**Nota:** Le API dei report sono in anteprima e sono soggette a modifiche fino a quando non entrano in produzione.</span><span class="sxs-lookup"><span data-stu-id="56c5b-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="56c5b-155">Immettere le credenziali di amministratore di Microsoft 365 (organizzazione o scuola) per l'autenticazione a Microsoft 365 quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="56c5b-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="56c5b-156">Per ulteriori informazioni su chi è autorizzato ad accedere ai report delle app modello di adozione di Microsoft 365, vedere le [domande frequenti](usage-analytics.md#faq) .</span><span class="sxs-lookup"><span data-stu-id="56c5b-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="56c5b-157">Dopo aver autorizzato la connessione, viene visualizzata la finestra Strumento di navigazione che mostra i set di dati disponibili a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="56c5b-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="56c5b-158">Seleziona tutto e scegli **carica** .</span><span class="sxs-lookup"><span data-stu-id="56c5b-158">Select all and choose **Load** .</span></span>
    
    <span data-ttu-id="56c5b-159">I dati verranno in Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="56c5b-159">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="56c5b-160">Salvare questo file per iniziare a creare i report necessari.</span><span class="sxs-lookup"><span data-stu-id="56c5b-160">Save this file and then you can start creating the reports you need.</span></span>
    
    ![Valori ODATA disponibili nell'API dei report](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="56c5b-162">Utilizzare il modello di analisi dei dati di utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56c5b-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="56c5b-163">È inoltre possibile utilizzare il file del modello Power BI che corrisponde ai report di analisi di utilizzo di Microsoft 365 come punto di partenza per la connessione ai dati.</span><span class="sxs-lookup"><span data-stu-id="56c5b-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="56c5b-164">Il vantaggio di usare il file PBIT è che ha la stringa di connessione già stabilita.</span><span class="sxs-lookup"><span data-stu-id="56c5b-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="56c5b-165">È anche possibile sfruttare tutte le misure personalizzate create, oltre ai dati che lo schema di base restituisce, usandole come base di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="56c5b-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="56c5b-166">È possibile scaricare il file del modello Power BI dall'area download Microsoft dall' [area download](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span><span class="sxs-lookup"><span data-stu-id="56c5b-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="56c5b-167">Dopo aver scaricato il file del modello di Power BI seguire questa procedura per iniziare:</span><span class="sxs-lookup"><span data-stu-id="56c5b-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="56c5b-168">Aprire il file PBIT.</span><span class="sxs-lookup"><span data-stu-id="56c5b-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="56c5b-169">Immettere il valore dell'ID tenant nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="56c5b-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="56c5b-171">Quando richiesto, immettere le credenziali di amministratore per eseguire l'autenticazione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56c5b-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="56c5b-172">Per ulteriori informazioni su chi è autorizzato ad accedere ai report di analisi di utilizzo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56c5b-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="56c5b-173">Una volta ottenuta l'autorizzazione, i dati verranno aggiornati nel file di Power BI.</span><span class="sxs-lookup"><span data-stu-id="56c5b-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="56c5b-174">Il caricamento dei dati può richiedere del tempo, ma al termine è possibile salvare il file PBIX e continuare a personalizzare i report o importare un'origine dati aggiuntiva nel report.</span><span class="sxs-lookup"><span data-stu-id="56c5b-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="56c5b-p107">Per comprendere come creare i report, pubblicarli nel servizio Power BI e condividerli con l'organizzazione, vedere [Introduzione a Power BI](https://go.microsoft.com/fwlink/?linkid=849802). Se si segue questo percorso per la personalizzazione e la condivisione potrebbero essere necessarie altre licenze di Power BI. Per altre informazioni vedere le [indicazioni sulle licenze](https://go.microsoft.com/fwlink/p/?linkid=849803).</span><span class="sxs-lookup"><span data-stu-id="56c5b-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

