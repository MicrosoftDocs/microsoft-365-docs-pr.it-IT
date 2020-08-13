---
title: Interfaccia di amministrazione di Exchange Online Protection autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Informazioni sull'interfaccia di gestione Web in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: d5753f687461a5495c2431db687263d7211bcbf5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652910"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="436b4-103">Interfaccia di amministrazione di Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="436b4-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="436b4-104">Interfaccia di amministrazione di Exchange (EAC) è una console di gestione basata sul Web per Exchange Online Protection (EOP) autonomo.</span><span class="sxs-lookup"><span data-stu-id="436b4-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="436b4-105">Per informazioni sulla versione di Exchange online in questo argomento, vedere</span><span class="sxs-lookup"><span data-stu-id="436b4-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="436b4-106">Vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="436b4-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="436b4-107">Aprire l'interfaccia di amministrazione di Exchange in EOP</span><span class="sxs-lookup"><span data-stu-id="436b4-107">Open the EAC in EOP</span></span>

<span data-ttu-id="436b4-108">I clienti EOP autonomi possono accedere all'interfaccia di amministrazione di Exchange utilizzando i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="436b4-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="436b4-109">**Dall'interfaccia di amministrazione di Microsoft 365**:</span><span class="sxs-lookup"><span data-stu-id="436b4-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="436b4-110">Andare a <https://admin.microsoft.com> e fare clic su **Mostra tutto**.</span><span class="sxs-lookup"><span data-stu-id="436b4-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Fare clic su Mostra tutto nell'interfaccia di amministrazione di Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="436b4-112">Nella sezione interfaccia di **Amministrazione** visualizzata fare clic su **tutti i centri di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="436b4-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Fare clic su tutti i centri di amministrazione nell'interfaccia di amministrazione di Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="436b4-114">Nella pagina **tutti i centri di amministrazione** visualizzati fare clic su **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="436b4-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="436b4-115">Andare direttamente a `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="436b4-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="436b4-116">Elementi comuni dell'interfaccia utente in EAC in EOP</span><span class="sxs-lookup"><span data-stu-id="436b4-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="436b4-117">In questa sezione vengono illustrati gli elementi dell'interfaccia utente disponibili in EAC.</span><span class="sxs-lookup"><span data-stu-id="436b4-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="436b4-119">Riquadro delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="436b4-119">Feature Pane</span></span>

<span data-ttu-id="436b4-p102">È il primo livello di esplorazione per la maggior parte delle attività da eseguire in EAC. Il riquadro delle funzionalità è organizzato in aree funzionali.</span><span class="sxs-lookup"><span data-stu-id="436b4-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="436b4-122">**Destinatari**: consente di visualizzare gruppi e contatti esterni.</span><span class="sxs-lookup"><span data-stu-id="436b4-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="436b4-123">**Autorizzazioni**: consente di gestire i ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="436b4-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="436b4-124">**Gestione della conformità**: consente di trovare il rapporto del gruppo di ruoli amministratore e il report del registro di controllo di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="436b4-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="436b4-125">**Protezione**: è possibile gestire i criteri antimalware, i criteri di filtro delle connessioni predefiniti e DKIM.</span><span class="sxs-lookup"><span data-stu-id="436b4-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="436b4-126">È consigliabile gestire i criteri antimalware e i criteri di filtro delle connessioni predefiniti nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="436b4-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="436b4-127">Per ulteriori informazioni, vedere [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md) e [Configure Connection Filtering in EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="436b4-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="436b4-128">**Flusso di posta**: consente di gestire le regole del flusso di posta (note anche come regole di trasporto), i domini accettati e i connettori, nonché le posizioni in cui è possibile eseguire la traccia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="436b4-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="436b4-129">Soluzione **ibrida**: è possibile eseguire la [procedura guidata di configurazione ibrida](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)e dove è possibile installare il [modulo di PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="436b4-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="436b4-130">Schede</span><span class="sxs-lookup"><span data-stu-id="436b4-130">Tabs</span></span>

<span data-ttu-id="436b4-p104">Le schede rappresentano il secondo livello di esplorazione. Ciascuna area funzionale contiene varie schede, ognuna delle quali rappresenta una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="436b4-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="436b4-133">Barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="436b4-133">Toolbar</span></span>

<span data-ttu-id="436b4-p105">La selezione della maggior parte delle schede consente di visualizzare una barra degli strumenti. che include icone che eseguono un'azione specifica. Nella tabella seguente sono descritte le icone e le loro azioni.</span><span class="sxs-lookup"><span data-stu-id="436b4-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="436b4-137">Icona</span><span class="sxs-lookup"><span data-stu-id="436b4-137">Icon</span></span>|<span data-ttu-id="436b4-138">Nome</span><span class="sxs-lookup"><span data-stu-id="436b4-138">Name</span></span>|<span data-ttu-id="436b4-139">Azione</span><span class="sxs-lookup"><span data-stu-id="436b4-139">Action</span></span>|
|---|---|---|
|![Icona Aggiungi](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="436b4-141">Aggiungi, Nuovo</span><span class="sxs-lookup"><span data-stu-id="436b4-141">Add, New</span></span>|<span data-ttu-id="436b4-p106">Utilizzare questa icona per creare un nuovo oggetto. Ad alcune icone è associata una freccia in giù sulla quale si può fare clic per mostrare ulteriori oggetti da creare.</span><span class="sxs-lookup"><span data-stu-id="436b4-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Icona Modifica](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="436b4-145">Modifica</span><span class="sxs-lookup"><span data-stu-id="436b4-145">Edit</span></span>|<span data-ttu-id="436b4-146">Utilizzare questa icona per modificare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="436b4-146">Use this icon to edit an object.</span></span>|
|![Icona Elimina](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="436b4-148">Elimina</span><span class="sxs-lookup"><span data-stu-id="436b4-148">Delete</span></span>|<span data-ttu-id="436b4-p107">Utilizzare questa icona per eliminare un oggetto. Ad alcune icone Elimina è associata una freccia in giù su cui si può fare clic per mostrare altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="436b4-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![icona Cerca](../../media/ITPro-EAC-.gif)|<span data-ttu-id="436b4-152">Cerca</span><span class="sxs-lookup"><span data-stu-id="436b4-152">Search</span></span>|<span data-ttu-id="436b4-153">Utilizzare questa icona per aprire una casella di ricerca in cui digitare la frase di ricerca per l'oggetto che si desidera trovare.</span><span class="sxs-lookup"><span data-stu-id="436b4-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Icona Aggiorna](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="436b4-155">Aggiorna</span><span class="sxs-lookup"><span data-stu-id="436b4-155">Refresh</span></span>|<span data-ttu-id="436b4-156">Utilizzare questa icona per aggiornare la visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="436b4-156">Use this icon to refresh the list view.</span></span>|
|![Icona Ulteriori opzioni](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="436b4-158">Altre opzioni</span><span class="sxs-lookup"><span data-stu-id="436b4-158">More options</span></span>|<span data-ttu-id="436b4-p108">Utilizzare questa icona per visualizzare le altre azioni da eseguire per gli oggetti della scheda. Ad esempio in **Destinatari \> Utenti**, facendo clic sull'icona, viene visualizzata l'opzione per eseguire una **Ricerca avanzata**.  </span><span class="sxs-lookup"><span data-stu-id="436b4-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Icona Freccia in su](../../media/ITPro-EAC-UpArrowIcon.gif)![Icona Freccia in giù](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="436b4-163">Freccia su e freccia giù</span><span class="sxs-lookup"><span data-stu-id="436b4-163">Up arrow and down arrow</span></span>|<span data-ttu-id="436b4-164">Utilizzare queste icone per spostare la priorità di un oggetto verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="436b4-164">Use these icons to move an object's priority up or down.</span></span>|
|![Icona Rimuovi](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="436b4-166">Rimuovi</span><span class="sxs-lookup"><span data-stu-id="436b4-166">Remove</span></span>|<span data-ttu-id="436b4-167">Questa icona consente di rimuovere gli oggetti da un elenco.</span><span class="sxs-lookup"><span data-stu-id="436b4-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="436b4-168">Visualizzazione elenco</span><span class="sxs-lookup"><span data-stu-id="436b4-168">List View</span></span>

<span data-ttu-id="436b4-p109">Selezionando una scheda, nella maggior parte dei casi viene attivata una visualizzazione elenco. Il limite visualizzabile con l'elenco EAC è di circa 10.000 oggetti. È inoltre inclusa la funzione di paging che consente di scorrere fino ai risultati.</span><span class="sxs-lookup"><span data-stu-id="436b4-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="436b4-172">Riquadro dei dettagli</span><span class="sxs-lookup"><span data-stu-id="436b4-172">Details Pane</span></span>

<span data-ttu-id="436b4-p110">Quando si seleziona un oggetto dalla visualizzazione elenco, nel riquadro dei dettagli vengono visualizzate le informazioni relative all'oggetto in questione. In alcuni casi il riquadro dei dettagli include attività di gestione.</span><span class="sxs-lookup"><span data-stu-id="436b4-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="436b4-175">Riquadro Io e Guida</span><span class="sxs-lookup"><span data-stu-id="436b4-175">Me tile and Help</span></span>

<span data-ttu-id="436b4-p111">Il riquadro **Io** consente di disconnettersi da EAC e accedere come altro utente. Dal menu a discesa **Guida**![Icona Guida](../../media/ITPro-EAC-HelpIcon.gif), è possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="436b4-p111">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="436b4-178">**Guida**: fare clic su ![ icona Guida ](../../media/ITPro-EAC-HelpIcon.gif) per visualizzare il contenuto della Guida in linea.</span><span class="sxs-lookup"><span data-stu-id="436b4-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="436b4-179">**Commenti e suggerimenti**: lasciare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="436b4-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="436b4-180">**Community**: inviare una domanda per trovare risposte nei forum della community.</span><span class="sxs-lookup"><span data-stu-id="436b4-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="436b4-181">**Disattiva la guida del fumetto**: la Guida di bubbling Visualizza la supporto contestuale per i campi quando si crea o si modifica un oggetto.</span><span class="sxs-lookup"><span data-stu-id="436b4-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="436b4-182">È possibile disabilitare la finestra della Guida o riattivarla se era stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="436b4-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="436b4-183">**Mostra registrazione comandi**: viene visualizzata una nuova finestra in cui vengono visualizzati i comandi di PowerShell equivalenti in base alle impostazioni configurate in EAC.</span><span class="sxs-lookup"><span data-stu-id="436b4-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="436b4-184">Browser supportati</span><span class="sxs-lookup"><span data-stu-id="436b4-184">Supported Browsers</span></span>

<span data-ttu-id="436b4-185">Per la migliore esperienza nell'utilizzo di EAC, si consiglia di utilizzare sempre i browser più recenti, i client e le app di Office.</span><span class="sxs-lookup"><span data-stu-id="436b4-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="436b4-186">Si consiglia inoltre di installare gli aggiornamenti software quando disponibili.</span><span class="sxs-lookup"><span data-stu-id="436b4-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="436b4-187">Per ulteriori informazioni sui browser supportati e sui requisiti di sistema per il servizio, vedere [requisiti di sistema per Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="436b4-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="436b4-188">Lingue supportate</span><span class="sxs-lookup"><span data-stu-id="436b4-188">Supported languages</span></span>

<span data-ttu-id="436b4-189">Le lingue seguenti sono supportate e disponibili per l'interfaccia di amministrazione di Exchange in EOP autonomo.</span><span class="sxs-lookup"><span data-stu-id="436b4-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="436b4-190">Amharico</span><span class="sxs-lookup"><span data-stu-id="436b4-190">Amharic</span></span>
- <span data-ttu-id="436b4-191">Arabo</span><span class="sxs-lookup"><span data-stu-id="436b4-191">Arabic</span></span>
- <span data-ttu-id="436b4-192">Basco (Province basche)</span><span class="sxs-lookup"><span data-stu-id="436b4-192">Basque (Basque)</span></span>
- <span data-ttu-id="436b4-193">Bengali (India)</span><span class="sxs-lookup"><span data-stu-id="436b4-193">Bengali (India)</span></span>
- <span data-ttu-id="436b4-194">Bulgaro</span><span class="sxs-lookup"><span data-stu-id="436b4-194">Bulgarian</span></span>
- <span data-ttu-id="436b4-195">Catalano</span><span class="sxs-lookup"><span data-stu-id="436b4-195">Catalan</span></span>
- <span data-ttu-id="436b4-196">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="436b4-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="436b4-197">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="436b4-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="436b4-198">Croato</span><span class="sxs-lookup"><span data-stu-id="436b4-198">Croatian</span></span>
- <span data-ttu-id="436b4-199">Ceco</span><span class="sxs-lookup"><span data-stu-id="436b4-199">Czech</span></span>
- <span data-ttu-id="436b4-200">Danese</span><span class="sxs-lookup"><span data-stu-id="436b4-200">Danish</span></span>
- <span data-ttu-id="436b4-201">Olandese</span><span class="sxs-lookup"><span data-stu-id="436b4-201">Dutch</span></span>
- <span data-ttu-id="436b4-202">Inglese</span><span class="sxs-lookup"><span data-stu-id="436b4-202">English</span></span>
- <span data-ttu-id="436b4-203">Estone</span><span class="sxs-lookup"><span data-stu-id="436b4-203">Estonian</span></span>
- <span data-ttu-id="436b4-204">Filippino (Filippine)</span><span class="sxs-lookup"><span data-stu-id="436b4-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="436b4-205">Finlandese</span><span class="sxs-lookup"><span data-stu-id="436b4-205">Finnish</span></span>
- <span data-ttu-id="436b4-206">Francese</span><span class="sxs-lookup"><span data-stu-id="436b4-206">French</span></span>
- <span data-ttu-id="436b4-207">Gallego</span><span class="sxs-lookup"><span data-stu-id="436b4-207">Galician</span></span>
- <span data-ttu-id="436b4-208">Tedesco</span><span class="sxs-lookup"><span data-stu-id="436b4-208">German</span></span>
- <span data-ttu-id="436b4-209">Greco</span><span class="sxs-lookup"><span data-stu-id="436b4-209">Greek</span></span>
- <span data-ttu-id="436b4-210">Gujarati</span><span class="sxs-lookup"><span data-stu-id="436b4-210">Gujarati</span></span>
- <span data-ttu-id="436b4-211">Ebraico</span><span class="sxs-lookup"><span data-stu-id="436b4-211">Hebrew</span></span>
- <span data-ttu-id="436b4-212">Hindi</span><span class="sxs-lookup"><span data-stu-id="436b4-212">Hindi</span></span>
- <span data-ttu-id="436b4-213">Ungherese</span><span class="sxs-lookup"><span data-stu-id="436b4-213">Hungarian</span></span>
- <span data-ttu-id="436b4-214">Islandese</span><span class="sxs-lookup"><span data-stu-id="436b4-214">Icelandic</span></span>
- <span data-ttu-id="436b4-215">Indonesiano</span><span class="sxs-lookup"><span data-stu-id="436b4-215">Indonesian</span></span>
- <span data-ttu-id="436b4-216">Italiano</span><span class="sxs-lookup"><span data-stu-id="436b4-216">Italian</span></span>
- <span data-ttu-id="436b4-217">Giapponese</span><span class="sxs-lookup"><span data-stu-id="436b4-217">Japanese</span></span>
- <span data-ttu-id="436b4-218">Kannada</span><span class="sxs-lookup"><span data-stu-id="436b4-218">Kannada</span></span>
- <span data-ttu-id="436b4-219">Kazaco</span><span class="sxs-lookup"><span data-stu-id="436b4-219">Kazakh</span></span>
- <span data-ttu-id="436b4-220">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="436b4-220">Kiswahili</span></span>
- <span data-ttu-id="436b4-221">Coreano</span><span class="sxs-lookup"><span data-stu-id="436b4-221">Korean</span></span>
- <span data-ttu-id="436b4-222">Lettone</span><span class="sxs-lookup"><span data-stu-id="436b4-222">Latvian</span></span>
- <span data-ttu-id="436b4-223">Lituano</span><span class="sxs-lookup"><span data-stu-id="436b4-223">Lithuanian</span></span>
- <span data-ttu-id="436b4-224">Malese (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="436b4-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="436b4-225">Malese (Malesia)</span><span class="sxs-lookup"><span data-stu-id="436b4-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="436b4-226">Malayalam</span><span class="sxs-lookup"><span data-stu-id="436b4-226">Malayalam</span></span>
- <span data-ttu-id="436b4-227">Marathi</span><span class="sxs-lookup"><span data-stu-id="436b4-227">Marathi</span></span>
- <span data-ttu-id="436b4-228">Norvegese (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="436b4-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="436b4-229">Norvegese (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="436b4-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="436b4-230">Oriya</span><span class="sxs-lookup"><span data-stu-id="436b4-230">Oriya</span></span>
- <span data-ttu-id="436b4-231">Persiano</span><span class="sxs-lookup"><span data-stu-id="436b4-231">Persian</span></span>
- <span data-ttu-id="436b4-232">Polacco</span><span class="sxs-lookup"><span data-stu-id="436b4-232">Polish</span></span>
- <span data-ttu-id="436b4-233">Portoghese (Brasile)</span><span class="sxs-lookup"><span data-stu-id="436b4-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="436b4-234">Portoghese (Portogallo)</span><span class="sxs-lookup"><span data-stu-id="436b4-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="436b4-235">Rumeno</span><span class="sxs-lookup"><span data-stu-id="436b4-235">Romanian</span></span>
- <span data-ttu-id="436b4-236">Russo</span><span class="sxs-lookup"><span data-stu-id="436b4-236">Russian</span></span>
- <span data-ttu-id="436b4-237">Serbo (alfabeto cirillico)</span><span class="sxs-lookup"><span data-stu-id="436b4-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="436b4-238">Serbo (alfabeto latino)</span><span class="sxs-lookup"><span data-stu-id="436b4-238">Serbian (Latin)</span></span>
- <span data-ttu-id="436b4-239">Slovacco</span><span class="sxs-lookup"><span data-stu-id="436b4-239">Slovak</span></span>
- <span data-ttu-id="436b4-240">Sloveno</span><span class="sxs-lookup"><span data-stu-id="436b4-240">Slovenian</span></span>
- <span data-ttu-id="436b4-241">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="436b4-241">Spanish</span></span>
- <span data-ttu-id="436b4-242">Svedese</span><span class="sxs-lookup"><span data-stu-id="436b4-242">Swedish</span></span>
- <span data-ttu-id="436b4-243">Tamil</span><span class="sxs-lookup"><span data-stu-id="436b4-243">Tamil</span></span>
- <span data-ttu-id="436b4-244">Telugu</span><span class="sxs-lookup"><span data-stu-id="436b4-244">Telugu</span></span>
- <span data-ttu-id="436b4-245">Tailandese</span><span class="sxs-lookup"><span data-stu-id="436b4-245">Thai</span></span>
- <span data-ttu-id="436b4-246">Turco</span><span class="sxs-lookup"><span data-stu-id="436b4-246">Turkish</span></span>
- <span data-ttu-id="436b4-247">Ucraino</span><span class="sxs-lookup"><span data-stu-id="436b4-247">Ukrainian</span></span>
- <span data-ttu-id="436b4-248">Urdu</span><span class="sxs-lookup"><span data-stu-id="436b4-248">Urdu</span></span>
- <span data-ttu-id="436b4-249">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="436b4-249">Vietnamese</span></span>
- <span data-ttu-id="436b4-250">Gallese</span><span class="sxs-lookup"><span data-stu-id="436b4-250">Welsh</span></span>
