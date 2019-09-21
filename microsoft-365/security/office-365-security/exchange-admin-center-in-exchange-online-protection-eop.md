---
title: 'Interfaccia di amministrazione di Exchange in Exchange Online Protection '
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: L'Interfaccia di amministrazione di Exchange (EAC) è la console di gestione basata sul Web per Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: a32302c8f18502453ff8cd57f9fc11cc2be4d9e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083527"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="a27f4-103">Interfaccia di amministrazione di Exchange in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a27f4-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="a27f4-104">L'Interfaccia di amministrazione di Exchange (EAC) è la console di gestione basata sul Web per Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a27f4-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="a27f4-p101">Per informazioni sulla versione di Exchange 2013 in questo argomento, vedere [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span><span class="sxs-lookup"><span data-stu-id="a27f4-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="a27f4-p102">Per informazioni sulla versione di Exchange Online in questo argomento, vedere [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a27f4-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="a27f4-109">Accesso a EAC</span><span class="sxs-lookup"><span data-stu-id="a27f4-109">Accessing the EAC</span></span>

<span data-ttu-id="a27f4-110">Nella maggior parte dei casi, i clienti di EOP accederanno a EAC tramite l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a27f4-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="a27f4-111">È possibile trovare un collegamento a EOP nel menu a discesa nel riquadro **Amministratore**, accanto al riquadro **Io**.</span><span class="sxs-lookup"><span data-stu-id="a27f4-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="a27f4-112">Fare clic sul riquadro **Amministratore** e selezionare **Exchange Online Protection** dal menu a discesa per l'esecuzione in EAC.</span><span class="sxs-lookup"><span data-stu-id="a27f4-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="a27f4-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="a27f4-116">Elementi comuni dell'interfaccia utente in EAC</span><span class="sxs-lookup"><span data-stu-id="a27f4-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="a27f4-117">In questa sezione vengono illustrati gli elementi dell'interfaccia utente disponibili in EAC.</span><span class="sxs-lookup"><span data-stu-id="a27f4-117">This section describes the user interface elements that are found in the EAC.</span></span>
  
![EOP-AdminCenter](../media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="a27f4-119">Riquadro delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="a27f4-119">Feature Pane</span></span>

<span data-ttu-id="a27f4-p105">È il primo livello di esplorazione per la maggior parte delle attività da eseguire in EAC. Il riquadro delle funzionalità è organizzato in aree funzionali.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="a27f4-122">**Destinatari** Consente di visualizzare gli utenti interni e i contatti esterni.</span><span class="sxs-lookup"><span data-stu-id="a27f4-122">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="a27f4-123">**Autorizzazioni** Consente di gestire i ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="a27f4-123">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="a27f4-124">**Gestione della conformità** Consente di individuare i registri di controllo e i rapporti, ad esempio il rapporto di un gruppo di ruoli amministratore.</span><span class="sxs-lookup"><span data-stu-id="a27f4-124">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="a27f4-125">**Protezione** Consente di gestire la protezione anti-malware e dalla posta indesiderata per l'organizzazione e consente di gestire i messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="a27f4-125">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="a27f4-126">**Flusso di posta** Consente di gestire regole, domini accettati e connettori e di eseguire l'analisi dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a27f4-126">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="a27f4-127">Schede</span><span class="sxs-lookup"><span data-stu-id="a27f4-127">Tabs</span></span>

<span data-ttu-id="a27f4-p106">Le schede rappresentano il secondo livello di esplorazione. Ciascuna area funzionale contiene varie schede, ognuna delle quali rappresenta una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="a27f4-130">Barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="a27f4-130">Toolbar</span></span>

<span data-ttu-id="a27f4-p107">La selezione della maggior parte delle schede consente di visualizzare una barra degli strumenti. che include icone che eseguono un'azione specifica. Nella tabella seguente sono descritte le icone e le loro azioni.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="a27f4-134">**Icona**</span><span class="sxs-lookup"><span data-stu-id="a27f4-134">**Icon**</span></span>|<span data-ttu-id="a27f4-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a27f4-135">**Name**</span></span>|<span data-ttu-id="a27f4-136">**Azione**</span><span class="sxs-lookup"><span data-stu-id="a27f4-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif)           <br/> |<span data-ttu-id="a27f4-138">Aggiungi, Nuovo</span><span class="sxs-lookup"><span data-stu-id="a27f4-138">Add, New</span></span>  <br/> |<span data-ttu-id="a27f4-p108">Utilizzare questa icona per creare un nuovo oggetto. Ad alcune icone è associata una freccia in giù sulla quale si può fare clic per mostrare ulteriori oggetti da creare.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![Icona Modifica](../media/ITPro-EAC-EditIcon.gif)           <br/> |<span data-ttu-id="a27f4-142">Modifica</span><span class="sxs-lookup"><span data-stu-id="a27f4-142">Edit</span></span>  <br/> |<span data-ttu-id="a27f4-143">Utilizzare questa icona per modificare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a27f4-143">Use this icon to edit an object.</span></span>  <br/> |
|![Icona Elimina](../media/ITPro-EAC-DeleteIcon.gif)           <br/> |<span data-ttu-id="a27f4-145">Elimina</span><span class="sxs-lookup"><span data-stu-id="a27f4-145">Delete</span></span>  <br/> |<span data-ttu-id="a27f4-p109">Utilizzare questa icona per eliminare un oggetto. Ad alcune icone Elimina è associata una freccia in giù su cui si può fare clic per mostrare altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![icona Cerca](../media/ITPro-EAC-.gif)           <br/> |<span data-ttu-id="a27f4-149">Cerca</span><span class="sxs-lookup"><span data-stu-id="a27f4-149">Search</span></span>  <br/> |<span data-ttu-id="a27f4-150">Utilizzare questa icona per aprire una casella di ricerca in cui digitare la frase di ricerca per l'oggetto che si desidera trovare.</span><span class="sxs-lookup"><span data-stu-id="a27f4-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![Icona Aggiorna](../media/ITPro-EAC-RefreshIcon.gif)           <br/> |<span data-ttu-id="a27f4-152">Aggiorna</span><span class="sxs-lookup"><span data-stu-id="a27f4-152">Refresh</span></span>  <br/> |<span data-ttu-id="a27f4-153">Utilizzare questa icona per aggiornare la visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="a27f4-153">Use this icon to refresh the list view.</span></span>  <br/> |
|![Icona Ulteriori opzioni](../media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |<span data-ttu-id="a27f4-155">Altre opzioni</span><span class="sxs-lookup"><span data-stu-id="a27f4-155">More options</span></span>  <br/> |<span data-ttu-id="a27f4-p110">Utilizzare questa icona per visualizzare le altre azioni da eseguire per gli oggetti della scheda. Ad esempio in **Destinatari \> Utenti**, facendo clic sull'icona, viene visualizzata l'opzione per eseguire una **Ricerca avanzata**.  </span><span class="sxs-lookup"><span data-stu-id="a27f4-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.  </span></span><br/> |
|![Icona Freccia in su](../media/ITPro-EAC-UpArrowIcon.gif)![Icona Freccia in giù](../media/ITPro-EAC-DownArrowIcon.gif)           <br/> |<span data-ttu-id="a27f4-160">Freccia su e freccia giù</span><span class="sxs-lookup"><span data-stu-id="a27f4-160">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="a27f4-161">Utilizzare queste icone per spostare la priorità di un oggetto verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="a27f4-161">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.gif)           <br/> |<span data-ttu-id="a27f4-163">Rimuovi</span><span class="sxs-lookup"><span data-stu-id="a27f4-163">Remove</span></span>  <br/> |<span data-ttu-id="a27f4-164">Questa icona consente di rimuovere gli oggetti da un elenco.</span><span class="sxs-lookup"><span data-stu-id="a27f4-164">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="a27f4-165">Visualizzazione elenco</span><span class="sxs-lookup"><span data-stu-id="a27f4-165">List View</span></span>

<span data-ttu-id="a27f4-p111">Selezionando una scheda, nella maggior parte dei casi viene attivata una visualizzazione elenco. Il limite visualizzabile con l'elenco EAC è di circa 10.000 oggetti. È inoltre inclusa la funzione di paging che consente di scorrere fino ai risultati.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="a27f4-169">Riquadro dei dettagli</span><span class="sxs-lookup"><span data-stu-id="a27f4-169">Details Pane</span></span>

<span data-ttu-id="a27f4-p112">Quando si seleziona un oggetto dalla visualizzazione elenco, nel riquadro dei dettagli vengono visualizzate le informazioni relative all'oggetto in questione. In alcuni casi il riquadro dei dettagli include attività di gestione.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="a27f4-172">Riquadro Io e Guida</span><span class="sxs-lookup"><span data-stu-id="a27f4-172">Me tile and Help</span></span>

<span data-ttu-id="a27f4-p113">Il riquadro **Io** consente di disconnettersi da EAC e accedere come altro utente. Dal menu a discesa **Guida**![Icona Guida](../media/ITPro-EAC-HelpIcon.gif), è possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="a27f4-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="a27f4-175">**Guida** Fare clic su ![Icona Guida](../media/ITPro-EAC-HelpIcon.gif) per visualizzare il contenuto della Guida.</span><span class="sxs-lookup"><span data-stu-id="a27f4-175">**Help** Click ![Help Icon](../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span> 
    
2. <span data-ttu-id="a27f4-p114">**Disabilita finestra della Guida** La finestra della Guida visualizza una guida contestuale per i campi relativi alla creazione o alla modifica di un oggetto. È possibile disabilitare la finestra della Guida o riattivarla se era stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="a27f4-p114">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object. You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="a27f4-178">**Copyright** Fare clic su questo collegamento per leggere le informazioni sul copyright per Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="a27f4-178">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="a27f4-179">**Privacy** Fare clic per leggere l'informativa sulla privacy per Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="a27f4-179">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="a27f4-180">Browser supportati</span><span class="sxs-lookup"><span data-stu-id="a27f4-180">Supported Browsers</span></span>

<span data-ttu-id="a27f4-p115">Per la migliore esperienza nell'utilizzo di EAC, si consiglia di utilizzare sempre i browser più recenti, i client e le app di Office. Si consiglia inoltre di installare gli aggiornamenti software quando disponibili. Per ulteriori informazioni sui browser supportati e requisiti di sistema per il servizio, vedere [Requisiti di sistema per Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span><span class="sxs-lookup"><span data-stu-id="a27f4-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="a27f4-184">Lingue supportate in EOP</span><span class="sxs-lookup"><span data-stu-id="a27f4-184">Supported languages in EOP</span></span>

<span data-ttu-id="a27f4-185">Per Exchange Online Protection sono disponibili e supportate le seguenti lingue server:</span><span class="sxs-lookup"><span data-stu-id="a27f4-185">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="a27f4-186">Amharico</span><span class="sxs-lookup"><span data-stu-id="a27f4-186">Amharic</span></span>
    
- <span data-ttu-id="a27f4-187">Arabo</span><span class="sxs-lookup"><span data-stu-id="a27f4-187">Arabic</span></span>
    
- <span data-ttu-id="a27f4-188">Basco (Province basche)</span><span class="sxs-lookup"><span data-stu-id="a27f4-188">Basque (Basque)</span></span>
    
- <span data-ttu-id="a27f4-189">Bengali (India)</span><span class="sxs-lookup"><span data-stu-id="a27f4-189">Bengali (India)</span></span>
    
- <span data-ttu-id="a27f4-190">Bulgaro</span><span class="sxs-lookup"><span data-stu-id="a27f4-190">Bulgarian</span></span>
    
- <span data-ttu-id="a27f4-191">Catalano</span><span class="sxs-lookup"><span data-stu-id="a27f4-191">Catalan</span></span>
    
- <span data-ttu-id="a27f4-192">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="a27f4-192">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="a27f4-193">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="a27f4-193">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="a27f4-194">Croato</span><span class="sxs-lookup"><span data-stu-id="a27f4-194">Croatian</span></span>
    
- <span data-ttu-id="a27f4-195">Ceco</span><span class="sxs-lookup"><span data-stu-id="a27f4-195">Czech</span></span>
    
- <span data-ttu-id="a27f4-196">Danese</span><span class="sxs-lookup"><span data-stu-id="a27f4-196">Danish</span></span>
    
- <span data-ttu-id="a27f4-197">Olandese</span><span class="sxs-lookup"><span data-stu-id="a27f4-197">Dutch</span></span>
    
- <span data-ttu-id="a27f4-198">Olandese</span><span class="sxs-lookup"><span data-stu-id="a27f4-198">Dutch</span></span>
    
- <span data-ttu-id="a27f4-199">Inglese</span><span class="sxs-lookup"><span data-stu-id="a27f4-199">English</span></span>
    
- <span data-ttu-id="a27f4-200">Estone</span><span class="sxs-lookup"><span data-stu-id="a27f4-200">Estonian</span></span>
    
- <span data-ttu-id="a27f4-201">Filippino (Filippine)</span><span class="sxs-lookup"><span data-stu-id="a27f4-201">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="a27f4-202">Finlandese</span><span class="sxs-lookup"><span data-stu-id="a27f4-202">Finnish</span></span>
    
- <span data-ttu-id="a27f4-203">Francese</span><span class="sxs-lookup"><span data-stu-id="a27f4-203">French</span></span>
    
- <span data-ttu-id="a27f4-204">Gallego</span><span class="sxs-lookup"><span data-stu-id="a27f4-204">Galician</span></span>
    
- <span data-ttu-id="a27f4-205">Tedesco</span><span class="sxs-lookup"><span data-stu-id="a27f4-205">German</span></span>
    
- <span data-ttu-id="a27f4-206">Greco</span><span class="sxs-lookup"><span data-stu-id="a27f4-206">Greek</span></span>
    
- <span data-ttu-id="a27f4-207">Gujarati</span><span class="sxs-lookup"><span data-stu-id="a27f4-207">Gujarati</span></span>
    
- <span data-ttu-id="a27f4-208">Ebraico</span><span class="sxs-lookup"><span data-stu-id="a27f4-208">Hebrew</span></span>
    
- <span data-ttu-id="a27f4-209">Hindi</span><span class="sxs-lookup"><span data-stu-id="a27f4-209">Hindi</span></span>
    
- <span data-ttu-id="a27f4-210">Ungherese</span><span class="sxs-lookup"><span data-stu-id="a27f4-210">Hungarian</span></span>
    
- <span data-ttu-id="a27f4-211">Islandese</span><span class="sxs-lookup"><span data-stu-id="a27f4-211">Icelandic</span></span>
    
- <span data-ttu-id="a27f4-212">Indonesiano</span><span class="sxs-lookup"><span data-stu-id="a27f4-212">Indonesian</span></span>
    
- <span data-ttu-id="a27f4-213">Italiano</span><span class="sxs-lookup"><span data-stu-id="a27f4-213">Italian</span></span>
    
- <span data-ttu-id="a27f4-214">Giapponese</span><span class="sxs-lookup"><span data-stu-id="a27f4-214">Japanese</span></span>
    
- <span data-ttu-id="a27f4-215">Kannada</span><span class="sxs-lookup"><span data-stu-id="a27f4-215">Kannada</span></span>
    
- <span data-ttu-id="a27f4-216">Kazaco</span><span class="sxs-lookup"><span data-stu-id="a27f4-216">Kazakh</span></span>
    
- <span data-ttu-id="a27f4-217">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="a27f4-217">Kiswahili</span></span>
    
- <span data-ttu-id="a27f4-218">Coreano</span><span class="sxs-lookup"><span data-stu-id="a27f4-218">Korean</span></span>
    
- <span data-ttu-id="a27f4-219">Lettone</span><span class="sxs-lookup"><span data-stu-id="a27f4-219">Latvian</span></span>
    
- <span data-ttu-id="a27f4-220">Lituano</span><span class="sxs-lookup"><span data-stu-id="a27f4-220">Lithuanian</span></span>
    
- <span data-ttu-id="a27f4-221">Malese (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="a27f4-221">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="a27f4-222">Malese (Malesia)</span><span class="sxs-lookup"><span data-stu-id="a27f4-222">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="a27f4-223">Malayalam</span><span class="sxs-lookup"><span data-stu-id="a27f4-223">Malayalam</span></span>
    
- <span data-ttu-id="a27f4-224">Marathi</span><span class="sxs-lookup"><span data-stu-id="a27f4-224">Marathi</span></span>
    
- <span data-ttu-id="a27f4-225">Norvegese (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="a27f4-225">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="a27f4-226">Norvegese (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="a27f4-226">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="a27f4-227">Oriya</span><span class="sxs-lookup"><span data-stu-id="a27f4-227">Oriya</span></span>
    
- <span data-ttu-id="a27f4-228">Persiano</span><span class="sxs-lookup"><span data-stu-id="a27f4-228">Persian</span></span>
    
- <span data-ttu-id="a27f4-229">Polacco</span><span class="sxs-lookup"><span data-stu-id="a27f4-229">Polish</span></span>
    
- <span data-ttu-id="a27f4-230">Portoghese (Brasile)</span><span class="sxs-lookup"><span data-stu-id="a27f4-230">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="a27f4-231">Portoghese (Portogallo)</span><span class="sxs-lookup"><span data-stu-id="a27f4-231">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="a27f4-232">Rumeno</span><span class="sxs-lookup"><span data-stu-id="a27f4-232">Romanian</span></span>
    
- <span data-ttu-id="a27f4-233">Russo</span><span class="sxs-lookup"><span data-stu-id="a27f4-233">Russian</span></span>
    
- <span data-ttu-id="a27f4-234">Serbo (alfabeto cirillico)</span><span class="sxs-lookup"><span data-stu-id="a27f4-234">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="a27f4-235">Serbo (alfabeto latino)</span><span class="sxs-lookup"><span data-stu-id="a27f4-235">Serbian (Latin)</span></span>
    
- <span data-ttu-id="a27f4-236">Slovacco</span><span class="sxs-lookup"><span data-stu-id="a27f4-236">Slovak</span></span>
    
- <span data-ttu-id="a27f4-237">Sloveno</span><span class="sxs-lookup"><span data-stu-id="a27f4-237">Slovenian</span></span>
    
- <span data-ttu-id="a27f4-238">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="a27f4-238">Spanish</span></span>
    
- <span data-ttu-id="a27f4-239">Svedese</span><span class="sxs-lookup"><span data-stu-id="a27f4-239">Swedish</span></span>
    
- <span data-ttu-id="a27f4-240">Tamil</span><span class="sxs-lookup"><span data-stu-id="a27f4-240">Tamil</span></span>
    
- <span data-ttu-id="a27f4-241">Telugu</span><span class="sxs-lookup"><span data-stu-id="a27f4-241">Telugu</span></span>
    
- <span data-ttu-id="a27f4-242">Tailandese</span><span class="sxs-lookup"><span data-stu-id="a27f4-242">Thai</span></span>
    
- <span data-ttu-id="a27f4-243">Turco</span><span class="sxs-lookup"><span data-stu-id="a27f4-243">Turkish</span></span>
    
- <span data-ttu-id="a27f4-244">Ucraino</span><span class="sxs-lookup"><span data-stu-id="a27f4-244">Ukrainian</span></span>
    
- <span data-ttu-id="a27f4-245">Urdu</span><span class="sxs-lookup"><span data-stu-id="a27f4-245">Urdu</span></span>
    
- <span data-ttu-id="a27f4-246">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="a27f4-246">Vietnamese</span></span>
    
- <span data-ttu-id="a27f4-247">Gallese</span><span class="sxs-lookup"><span data-stu-id="a27f4-247">Welsh</span></span>
    

