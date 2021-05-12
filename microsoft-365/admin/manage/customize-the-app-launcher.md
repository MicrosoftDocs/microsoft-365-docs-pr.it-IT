---
title: Aggiungere riquadri personalizzati all'icona di avvio delle app
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: "Creare collegamenti rapidi alla posta elettronica, ai documenti, alle app, ai siti di SharePoint, ai siti esterni e ad altre risorse aggiungendo riquadri personalizzati all'icona di avvio delle app. "
ms.openlocfilehash: 598cfeb75fc811c87519c4479fa8fcab450466c3
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327211"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="de8af-103">Aggiungere riquadri personalizzati all'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="de8af-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="de8af-104">In Microsoft 365 puoi accedere rapidamente e facilmente alla posta elettronica, ai calendari, ai documenti e alle app usando l'icona di avvio delle app ([altre informazioni](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="de8af-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="de8af-105">Si tratta di app che si ottengono con Microsoft 365 e app personalizzate che si aggiungono da [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD.](/previous-versions/office/office-365-api/)</span><span class="sxs-lookup"><span data-stu-id="de8af-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="de8af-p102">Puoi aggiungere all'icona di avvio delle app riquadri personalizzati che puntano a siti di SharePoint, siti esterni, app legacy e altro ancora. Il riquadro personalizzato appare dopo tutte le app in **Tutte** nell'icona di avvio delle app, ma puoi spostarlo in **Home** e indicare agli utenti di fare lo stesso. In questo modo è più facile trovare i siti, le app e le risorse rilevanti per svolgere il tuo lavoro. Nell'esempio seguente viene usato un riquadro personalizzato, "Portale Contoso", per accedere al sito Intranet di SharePoint dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de8af-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Icona di avvio delle app](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="de8af-111">Aggiungere un riquadro personalizzato all'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="de8af-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="de8af-112">Accedere all'interfaccia di amministrazione come amministratore globale, passare a Impostazioni  >  **Impostazioni organizzazione** e scegliere la scheda Profilo **organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="de8af-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="de8af-113">Nella scheda **Profilo organizzazione** scegliere Riquadri di avvio delle **app personalizzati.**</span><span class="sxs-lookup"><span data-stu-id="de8af-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="de8af-114">Seleziona **Aggiungi un riquadro personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="de8af-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="de8af-p103">Immetti un **Nome del riquadro** per il nuovo riquadro. Il nome verrà visualizzato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="de8af-p103">Enter a **Tile name** for the new tile. The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="de8af-117">Immetti un **URL del sito Web** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="de8af-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="de8af-118">Questa è la posizione in cui vuoi che gli utenti vadano quando selezionano il riquadro nell'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="de8af-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="de8af-119">Usa HTTPS nell'URL.</span><span class="sxs-lookup"><span data-stu-id="de8af-119">Use HTTPS in the URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="de8af-120">Se vuoi creare un riquadro per un sito di SharePoint, passa a tale sito, copia l'URL e incollalo in questo campo.</span><span class="sxs-lookup"><span data-stu-id="de8af-120">If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="de8af-121">L'URL del sito del team predefinito è simile al seguente: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="de8af-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="de8af-122">Immetti un **URL dell'immagine** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="de8af-122">Enter a **URL of the image** for the tile.</span></span> <span data-ttu-id="de8af-123">L'immagine verrà visualizzata nella pagina Mie app e nell'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="de8af-123">The image appears on the My apps page and app launcher.</span></span>

    > [!TIP]
    > <span data-ttu-id="de8af-124">L'immagine deve essere di 60x60 pixel ed essere disponibile per tutti gli utenti dell'organizzazione senza richiedere l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="de8af-124">The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="de8af-125">Immetti una **Descrizione** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="de8af-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="de8af-126">Questo viene visualizzato quando si seleziona il riquadro nella pagina App personali e si seleziona Dettagli **app**.</span><span class="sxs-lookup"><span data-stu-id="de8af-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="de8af-127">Seleziona **Salva modifiche** per creare il riquadro personalizzato.</span><span class="sxs-lookup"><span data-stu-id="de8af-127">Select **Save changes** to create the custom tile.</span></span> 
    
    <span data-ttu-id="de8af-128">Il riquadro personalizzato viene ora visualizzato nella scheda **Tutte** nell'icona di avvio delle app per te e i tuoi utenti.</span><span class="sxs-lookup"><span data-stu-id="de8af-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="de8af-129">Se il riquadro personalizzato creato nei passaggi precedenti non è visualizzato, verifica di avere una cassetta postale di Exchange Online assegnata e di aver eseguito almeno una volta l'accesso alla tua cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="de8af-129">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="de8af-130">Questi passaggi sono necessari per i riquadri personalizzati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de8af-130">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="de8af-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="de8af-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="de8af-132">Nell'interfaccia di amministrazione passare alla scheda **Impostazioni**  >  **organizzazione Profilo**  >  **organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="de8af-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="de8af-133">Nella pagina **Profilo organizzazione,** accanto a **Aggiungi riquadri personalizzati per l'organizzazione,** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="de8af-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="de8af-134">Aggiorna i valori di **Nome del riquadro**, **URL**, **Descrizione** o **URL immagine** per il riquadro personalizzato (vedi la [Aggiungere un riquadro personalizzato all'icona di avvio delle app](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="de8af-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="de8af-135">Selezionare **Update** \> **Close**.</span><span class="sxs-lookup"><span data-stu-id="de8af-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="de8af-136">Per eliminare un riquadro personalizzato, nella **finestra Riquadri** personalizzati seleziona il riquadro e seleziona **Rimuovi riquadro**  >  **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="de8af-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="de8af-137">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="de8af-137">What's next?</span></span>

<span data-ttu-id="de8af-138">Oltre ad aggiungere riquadri all'icona di avvio delle app, puoi aggiungere riquadri di avvio delle app alla barra di spostamento ([altre informazioni](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="de8af-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="de8af-139">Per personalizzare l'aspetto di Microsoft 365 in base al marchio dell'organizzazione, vedere [Personalizzare il tema di Microsoft 365.](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="de8af-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
