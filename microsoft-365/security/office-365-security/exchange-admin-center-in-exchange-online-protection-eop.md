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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Informazioni sull'interfaccia di gestione Web in Exchange Online Protection (EOP) autonomo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec9dcbccbee734ea7c475b1ac0a5f9a92a0b401b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286958"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="ecd16-103">Interfaccia di amministrazione di Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="ecd16-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ecd16-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="ecd16-104">**Applies to**</span></span>
-  [<span data-ttu-id="ecd16-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="ecd16-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="ecd16-106">L'interfaccia di amministrazione di Exchange è una console di gestione basata sul Web per Exchange Online Protection (EOP) autonomo.</span><span class="sxs-lookup"><span data-stu-id="ecd16-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="ecd16-107">Per informazioni sulla versione Exchange Online di questo argomento, vedere</span><span class="sxs-lookup"><span data-stu-id="ecd16-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="ecd16-108">Vedere [Interfaccia di amministrazione di Exchange in Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="ecd16-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="ecd16-109">Aprire l'interfaccia di amministrazione di Exchange in EOP</span><span class="sxs-lookup"><span data-stu-id="ecd16-109">Open the EAC in EOP</span></span>

<span data-ttu-id="ecd16-110">I clienti EOP autonomi possono accedere all'interfaccia di amministrazione di Exchange utilizzando i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecd16-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="ecd16-111">**Dall'interfaccia di amministrazione di Microsoft 365:**</span><span class="sxs-lookup"><span data-stu-id="ecd16-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="ecd16-112">Passare a <https://admin.microsoft.com> e fare clic su Mostra **tutto.**</span><span class="sxs-lookup"><span data-stu-id="ecd16-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Fare clic su Mostra tutto nell'interfaccia di amministrazione di Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="ecd16-114">Nella sezione **Admin center** visualizzata, fare clic su Tutte le centri **di amministrazione.**</span><span class="sxs-lookup"><span data-stu-id="ecd16-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Fare clic su Tutte le centri di amministrazione nell'interfaccia di amministrazione di Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="ecd16-116">Nella pagina **Tutte le centri di** amministrazione visualizzata fare clic su Exchange Online **Protection.**</span><span class="sxs-lookup"><span data-stu-id="ecd16-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="ecd16-117">Passare direttamente a `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="ecd16-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="ecd16-118">Elementi comuni dell'interfaccia utente in EAC in EOP</span><span class="sxs-lookup"><span data-stu-id="ecd16-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="ecd16-119">In questa sezione vengono illustrati gli elementi dell'interfaccia utente disponibili in EAC.</span><span class="sxs-lookup"><span data-stu-id="ecd16-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Interfaccia di amministrazione di Exchange in Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="ecd16-121">Riquadro delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="ecd16-121">Feature Pane</span></span>

<span data-ttu-id="ecd16-p102">È il primo livello di esplorazione per la maggior parte delle attività da eseguire in EAC. Il riquadro delle funzionalità è organizzato in aree funzionali.</span><span class="sxs-lookup"><span data-stu-id="ecd16-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="ecd16-124">**Destinatari**: consente di visualizzare i gruppi e i contatti esterni.</span><span class="sxs-lookup"><span data-stu-id="ecd16-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="ecd16-125">**Autorizzazioni:** qui è possibile gestire i ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ecd16-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="ecd16-126">**Gestione della conformità:** qui è possibile trovare il report del gruppo di ruoli amministratore e il report del log di controllo dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="ecd16-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="ecd16-127">**Protezione:** qui è possibile gestire i criteri antimalware, i criteri di filtro delle connessioni predefiniti e DKIM.</span><span class="sxs-lookup"><span data-stu-id="ecd16-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ecd16-128">È consigliabile gestire i criteri antimalware e i criteri di filtro delle connessioni predefiniti nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="ecd16-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="ecd16-129">Per ulteriori informazioni, vedere [Configurare i criteri antimalware in EOP](configure-anti-malware-policies.md) e Configurare il filtro [connessioni in EOP.](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="ecd16-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="ecd16-130">**Flusso di posta**: consente di gestire le regole del flusso di posta (note anche come regole di trasporto), i domini accettati e i connettori, nonché dove è possibile eseguire la traccia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ecd16-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="ecd16-131">**Ibrido:** qui è possibile eseguire la procedura guidata [di](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)configurazione ibrida e dove è possibile installare il modulo [PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ecd16-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="ecd16-132">Schede</span><span class="sxs-lookup"><span data-stu-id="ecd16-132">Tabs</span></span>

<span data-ttu-id="ecd16-p104">Le schede rappresentano il secondo livello di esplorazione. Ciascuna area funzionale contiene varie schede, ognuna delle quali rappresenta una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ecd16-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="ecd16-135">Barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="ecd16-135">Toolbar</span></span>

<span data-ttu-id="ecd16-p105">La selezione della maggior parte delle schede consente di visualizzare una barra degli strumenti. che include icone che eseguono un'azione specifica. Nella tabella seguente sono descritte le icone e le loro azioni.</span><span class="sxs-lookup"><span data-stu-id="ecd16-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="ecd16-139">Icona</span><span class="sxs-lookup"><span data-stu-id="ecd16-139">Icon</span></span>|<span data-ttu-id="ecd16-140">Nome</span><span class="sxs-lookup"><span data-stu-id="ecd16-140">Name</span></span>|<span data-ttu-id="ecd16-141">Azione</span><span class="sxs-lookup"><span data-stu-id="ecd16-141">Action</span></span>|
|---|---|---|
|![Icona Aggiungi](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="ecd16-143">Aggiungi, Nuovo</span><span class="sxs-lookup"><span data-stu-id="ecd16-143">Add, New</span></span>|<span data-ttu-id="ecd16-p106">Utilizzare questa icona per creare un nuovo oggetto. Ad alcune icone è associata una freccia in giù sulla quale si può fare clic per mostrare ulteriori oggetti da creare.</span><span class="sxs-lookup"><span data-stu-id="ecd16-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Icona Modifica](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="ecd16-147">Modifica</span><span class="sxs-lookup"><span data-stu-id="ecd16-147">Edit</span></span>|<span data-ttu-id="ecd16-148">Utilizzare questa icona per modificare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ecd16-148">Use this icon to edit an object.</span></span>|
|![Icona Elimina](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="ecd16-150">Elimina</span><span class="sxs-lookup"><span data-stu-id="ecd16-150">Delete</span></span>|<span data-ttu-id="ecd16-p107">Utilizzare questa icona per eliminare un oggetto. Ad alcune icone Elimina è associata una freccia in giù su cui si può fare clic per mostrare altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="ecd16-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![icona Cerca](../../media/ITPro-EAC-.gif)|<span data-ttu-id="ecd16-154">Cerca</span><span class="sxs-lookup"><span data-stu-id="ecd16-154">Search</span></span>|<span data-ttu-id="ecd16-155">Utilizzare questa icona per aprire una casella di ricerca in cui digitare la frase di ricerca per l'oggetto che si desidera trovare.</span><span class="sxs-lookup"><span data-stu-id="ecd16-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Icona Aggiorna](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="ecd16-157">Aggiorna</span><span class="sxs-lookup"><span data-stu-id="ecd16-157">Refresh</span></span>|<span data-ttu-id="ecd16-158">Utilizzare questa icona per aggiornare la visualizzazione elenco.</span><span class="sxs-lookup"><span data-stu-id="ecd16-158">Use this icon to refresh the list view.</span></span>|
|![Icona Ulteriori opzioni](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="ecd16-160">Altre opzioni</span><span class="sxs-lookup"><span data-stu-id="ecd16-160">More options</span></span>|<span data-ttu-id="ecd16-p108">Utilizzare questa icona per visualizzare le altre azioni da eseguire per gli oggetti della scheda. Ad esempio in **Destinatari \> Utenti**, facendo clic sull'icona, viene visualizzata l'opzione per eseguire una **Ricerca avanzata**.  </span><span class="sxs-lookup"><span data-stu-id="ecd16-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Icona Freccia in su](../../media/ITPro-EAC-UpArrowIcon.gif)![Icona Freccia in giù](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="ecd16-165">Freccia su e freccia giù</span><span class="sxs-lookup"><span data-stu-id="ecd16-165">Up arrow and down arrow</span></span>|<span data-ttu-id="ecd16-166">Utilizzare queste icone per spostare la priorità di un oggetto verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="ecd16-166">Use these icons to move an object's priority up or down.</span></span>|
|![Icona Rimuovi](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="ecd16-168">Rimuovi</span><span class="sxs-lookup"><span data-stu-id="ecd16-168">Remove</span></span>|<span data-ttu-id="ecd16-169">Questa icona consente di rimuovere gli oggetti da un elenco.</span><span class="sxs-lookup"><span data-stu-id="ecd16-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="ecd16-170">Visualizzazione elenco</span><span class="sxs-lookup"><span data-stu-id="ecd16-170">List View</span></span>

<span data-ttu-id="ecd16-p109">Selezionando una scheda, nella maggior parte dei casi viene attivata una visualizzazione elenco. Il limite visualizzabile con l'elenco EAC è di circa 10.000 oggetti. È inoltre inclusa la funzione di paging che consente di scorrere fino ai risultati.</span><span class="sxs-lookup"><span data-stu-id="ecd16-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="ecd16-174">Riquadro dei dettagli</span><span class="sxs-lookup"><span data-stu-id="ecd16-174">Details Pane</span></span>

<span data-ttu-id="ecd16-p110">Quando si seleziona un oggetto dalla visualizzazione elenco, nel riquadro dei dettagli vengono visualizzate le informazioni relative all'oggetto in questione. In alcuni casi il riquadro dei dettagli include attività di gestione.</span><span class="sxs-lookup"><span data-stu-id="ecd16-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="ecd16-177">Riquadro Io e Guida</span><span class="sxs-lookup"><span data-stu-id="ecd16-177">Me tile and Help</span></span>

<span data-ttu-id="ecd16-178">Il riquadro **Io** consente di disconnettersi da EAC e accedere come altro utente.</span><span class="sxs-lookup"><span data-stu-id="ecd16-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="ecd16-179">Dal menu **a** ![ discesa Help Icon è possibile eseguire le operazioni ](../../media/ITPro-EAC-HelpIcon.gif) seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecd16-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="ecd16-180">**Guida**: fare clic ![ sull'icona ](../../media/ITPro-EAC-HelpIcon.gif) della Guida per visualizzare il contenuto della Guida online.</span><span class="sxs-lookup"><span data-stu-id="ecd16-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="ecd16-181">**Feedback:** lasciare il feedback.</span><span class="sxs-lookup"><span data-stu-id="ecd16-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="ecd16-182">**Community:** pubblicare una domanda per trovare risposte nei forum della community.</span><span class="sxs-lookup"><span data-stu-id="ecd16-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="ecd16-183">**Disattiva finestra della** Guida : nella finestra della Guida viene visualizzata la Guida contestuale per i campi quando si crea o si modifica un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ecd16-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="ecd16-184">È possibile disabilitare la finestra della Guida o riattivarla se era stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="ecd16-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="ecd16-185">**Mostra registrazione comandi**: viene visualizzata una nuova finestra che mostra i comandi di PowerShell equivalenti in base a quanto configurato in EAC.</span><span class="sxs-lookup"><span data-stu-id="ecd16-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="ecd16-186">Browser supportati</span><span class="sxs-lookup"><span data-stu-id="ecd16-186">Supported Browsers</span></span>

<span data-ttu-id="ecd16-187">Per la migliore esperienza nell'utilizzo di EAC, si consiglia di utilizzare sempre i browser più recenti, i client e le app di Office.</span><span class="sxs-lookup"><span data-stu-id="ecd16-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="ecd16-188">Si consiglia inoltre di installare gli aggiornamenti software quando disponibili.</span><span class="sxs-lookup"><span data-stu-id="ecd16-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="ecd16-189">Per ulteriori informazioni sui browser supportati e sui requisiti di sistema per il servizio, vedere [Requisiti di sistema per Office.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="ecd16-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="ecd16-190">Lingue supportate</span><span class="sxs-lookup"><span data-stu-id="ecd16-190">Supported languages</span></span>

<span data-ttu-id="ecd16-191">Le lingue seguenti sono supportate e disponibili per L'interfaccia di amministrazione di Exchange in EOP autonomo.</span><span class="sxs-lookup"><span data-stu-id="ecd16-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="ecd16-192">Amharico</span><span class="sxs-lookup"><span data-stu-id="ecd16-192">Amharic</span></span>
- <span data-ttu-id="ecd16-193">Arabo</span><span class="sxs-lookup"><span data-stu-id="ecd16-193">Arabic</span></span>
- <span data-ttu-id="ecd16-194">Basco (Province basche)</span><span class="sxs-lookup"><span data-stu-id="ecd16-194">Basque (Basque)</span></span>
- <span data-ttu-id="ecd16-195">Bengali (India)</span><span class="sxs-lookup"><span data-stu-id="ecd16-195">Bengali (India)</span></span>
- <span data-ttu-id="ecd16-196">Bulgaro</span><span class="sxs-lookup"><span data-stu-id="ecd16-196">Bulgarian</span></span>
- <span data-ttu-id="ecd16-197">Catalano</span><span class="sxs-lookup"><span data-stu-id="ecd16-197">Catalan</span></span>
- <span data-ttu-id="ecd16-198">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="ecd16-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="ecd16-199">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="ecd16-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="ecd16-200">Croato</span><span class="sxs-lookup"><span data-stu-id="ecd16-200">Croatian</span></span>
- <span data-ttu-id="ecd16-201">Ceco</span><span class="sxs-lookup"><span data-stu-id="ecd16-201">Czech</span></span>
- <span data-ttu-id="ecd16-202">Danese</span><span class="sxs-lookup"><span data-stu-id="ecd16-202">Danish</span></span>
- <span data-ttu-id="ecd16-203">Olandese</span><span class="sxs-lookup"><span data-stu-id="ecd16-203">Dutch</span></span>
- <span data-ttu-id="ecd16-204">Inglese</span><span class="sxs-lookup"><span data-stu-id="ecd16-204">English</span></span>
- <span data-ttu-id="ecd16-205">Estone</span><span class="sxs-lookup"><span data-stu-id="ecd16-205">Estonian</span></span>
- <span data-ttu-id="ecd16-206">Filippino (Filippine)</span><span class="sxs-lookup"><span data-stu-id="ecd16-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="ecd16-207">Finlandese</span><span class="sxs-lookup"><span data-stu-id="ecd16-207">Finnish</span></span>
- <span data-ttu-id="ecd16-208">Francese</span><span class="sxs-lookup"><span data-stu-id="ecd16-208">French</span></span>
- <span data-ttu-id="ecd16-209">Gallego</span><span class="sxs-lookup"><span data-stu-id="ecd16-209">Galician</span></span>
- <span data-ttu-id="ecd16-210">Tedesco</span><span class="sxs-lookup"><span data-stu-id="ecd16-210">German</span></span>
- <span data-ttu-id="ecd16-211">Greco</span><span class="sxs-lookup"><span data-stu-id="ecd16-211">Greek</span></span>
- <span data-ttu-id="ecd16-212">Gujarati</span><span class="sxs-lookup"><span data-stu-id="ecd16-212">Gujarati</span></span>
- <span data-ttu-id="ecd16-213">Ebraico</span><span class="sxs-lookup"><span data-stu-id="ecd16-213">Hebrew</span></span>
- <span data-ttu-id="ecd16-214">Hindi</span><span class="sxs-lookup"><span data-stu-id="ecd16-214">Hindi</span></span>
- <span data-ttu-id="ecd16-215">Ungherese</span><span class="sxs-lookup"><span data-stu-id="ecd16-215">Hungarian</span></span>
- <span data-ttu-id="ecd16-216">Islandese</span><span class="sxs-lookup"><span data-stu-id="ecd16-216">Icelandic</span></span>
- <span data-ttu-id="ecd16-217">Indonesiano</span><span class="sxs-lookup"><span data-stu-id="ecd16-217">Indonesian</span></span>
- <span data-ttu-id="ecd16-218">Italiano</span><span class="sxs-lookup"><span data-stu-id="ecd16-218">Italian</span></span>
- <span data-ttu-id="ecd16-219">Giapponese</span><span class="sxs-lookup"><span data-stu-id="ecd16-219">Japanese</span></span>
- <span data-ttu-id="ecd16-220">Kannada</span><span class="sxs-lookup"><span data-stu-id="ecd16-220">Kannada</span></span>
- <span data-ttu-id="ecd16-221">Kazaco</span><span class="sxs-lookup"><span data-stu-id="ecd16-221">Kazakh</span></span>
- <span data-ttu-id="ecd16-222">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="ecd16-222">Kiswahili</span></span>
- <span data-ttu-id="ecd16-223">Coreano</span><span class="sxs-lookup"><span data-stu-id="ecd16-223">Korean</span></span>
- <span data-ttu-id="ecd16-224">Lettone</span><span class="sxs-lookup"><span data-stu-id="ecd16-224">Latvian</span></span>
- <span data-ttu-id="ecd16-225">Lituano</span><span class="sxs-lookup"><span data-stu-id="ecd16-225">Lithuanian</span></span>
- <span data-ttu-id="ecd16-226">Malese (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="ecd16-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="ecd16-227">Malese (Malesia)</span><span class="sxs-lookup"><span data-stu-id="ecd16-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="ecd16-228">Malayalam</span><span class="sxs-lookup"><span data-stu-id="ecd16-228">Malayalam</span></span>
- <span data-ttu-id="ecd16-229">Marathi</span><span class="sxs-lookup"><span data-stu-id="ecd16-229">Marathi</span></span>
- <span data-ttu-id="ecd16-230">Norvegese (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="ecd16-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="ecd16-231">Norvegese (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="ecd16-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="ecd16-232">Oriya</span><span class="sxs-lookup"><span data-stu-id="ecd16-232">Oriya</span></span>
- <span data-ttu-id="ecd16-233">Persiano</span><span class="sxs-lookup"><span data-stu-id="ecd16-233">Persian</span></span>
- <span data-ttu-id="ecd16-234">Polacco</span><span class="sxs-lookup"><span data-stu-id="ecd16-234">Polish</span></span>
- <span data-ttu-id="ecd16-235">Portoghese (Brasile)</span><span class="sxs-lookup"><span data-stu-id="ecd16-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="ecd16-236">Portoghese (Portogallo)</span><span class="sxs-lookup"><span data-stu-id="ecd16-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="ecd16-237">Rumeno</span><span class="sxs-lookup"><span data-stu-id="ecd16-237">Romanian</span></span>
- <span data-ttu-id="ecd16-238">Russo</span><span class="sxs-lookup"><span data-stu-id="ecd16-238">Russian</span></span>
- <span data-ttu-id="ecd16-239">Serbo (alfabeto cirillico)</span><span class="sxs-lookup"><span data-stu-id="ecd16-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="ecd16-240">Serbo (alfabeto latino)</span><span class="sxs-lookup"><span data-stu-id="ecd16-240">Serbian (Latin)</span></span>
- <span data-ttu-id="ecd16-241">Slovacco</span><span class="sxs-lookup"><span data-stu-id="ecd16-241">Slovak</span></span>
- <span data-ttu-id="ecd16-242">Sloveno</span><span class="sxs-lookup"><span data-stu-id="ecd16-242">Slovenian</span></span>
- <span data-ttu-id="ecd16-243">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="ecd16-243">Spanish</span></span>
- <span data-ttu-id="ecd16-244">Svedese</span><span class="sxs-lookup"><span data-stu-id="ecd16-244">Swedish</span></span>
- <span data-ttu-id="ecd16-245">Tamil</span><span class="sxs-lookup"><span data-stu-id="ecd16-245">Tamil</span></span>
- <span data-ttu-id="ecd16-246">Telugu</span><span class="sxs-lookup"><span data-stu-id="ecd16-246">Telugu</span></span>
- <span data-ttu-id="ecd16-247">Tailandese</span><span class="sxs-lookup"><span data-stu-id="ecd16-247">Thai</span></span>
- <span data-ttu-id="ecd16-248">Turco</span><span class="sxs-lookup"><span data-stu-id="ecd16-248">Turkish</span></span>
- <span data-ttu-id="ecd16-249">Ucraino</span><span class="sxs-lookup"><span data-stu-id="ecd16-249">Ukrainian</span></span>
- <span data-ttu-id="ecd16-250">Urdu</span><span class="sxs-lookup"><span data-stu-id="ecd16-250">Urdu</span></span>
- <span data-ttu-id="ecd16-251">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="ecd16-251">Vietnamese</span></span>
- <span data-ttu-id="ecd16-252">Gallese</span><span class="sxs-lookup"><span data-stu-id="ecd16-252">Welsh</span></span>
