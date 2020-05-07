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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: "Creare collegamenti rapidi per la posta elettronica, i documenti, le app, i siti di SharePoint, i siti esterni e altre risorse mediante l'aggiunta di sezioni personalizzate all'icona di avvio delle app. "
ms.openlocfilehash: 44a8af104f6f39bd6b095a08f8ad9b2750d86d11
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053777"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="c9148-103">Aggiungere riquadri personalizzati all'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="c9148-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="c9148-104">In Microsoft 365 è possibile accedere rapidamente e facilmente alla posta elettronica, ai calendari, ai documenti e alle app utilizzando l'icona di avvio delle app ([altre informazioni](https://support.microsoft.com/en-us/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="c9148-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/en-us/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="c9148-105">Queste sono le app che si ottengono con Microsoft 365, nonché le app personalizzate che si aggiungono da [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) o [Azure ad](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="c9148-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="c9148-p102">Puoi aggiungere all'icona di avvio delle app riquadri personalizzati che puntano a siti di SharePoint, siti esterni, app legacy e altro ancora. Il riquadro personalizzato appare dopo tutte le app in **Tutte** nell'icona di avvio delle app, ma puoi spostarlo in **Home** e indicare agli utenti di fare lo stesso. In questo modo è più facile trovare i siti, le app e le risorse rilevanti per svolgere il tuo lavoro. Nell'esempio seguente viene usato un riquadro personalizzato, "Portale Contoso", per accedere al sito Intranet di SharePoint dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9148-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Icona di avvio delle app](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="c9148-111">Aggiungere un riquadro personalizzato all'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="c9148-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="c9148-112">Nell'interfaccia di amministrazione, passare**Settings**  > alla scheda **Impostazioni e**scegliere **profilo organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="c9148-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="c9148-113">Nella scheda **profilo organizzazione** , scegliere **tessere di avvio delle app personalizzate**.</span><span class="sxs-lookup"><span data-stu-id="c9148-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="c9148-114">Selezionare **Aggiungi un riquadro personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="c9148-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="c9148-115">Immetti un **Nome del riquadro** per il nuovo riquadro.</span><span class="sxs-lookup"><span data-stu-id="c9148-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="c9148-116">Il nome verrà visualizzato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="c9148-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="c9148-117">Immettere un **URL del sito Web** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="c9148-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="c9148-118">Questa è la posizione in cui si desidera consentire agli utenti di selezionare il riquadro nell'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="c9148-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="c9148-119">Utilizzare HTTPS nell'URL.</span><span class="sxs-lookup"><span data-stu-id="c9148-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="c9148-120">Suggerimento: se si sta creando un riquadro per un sito di SharePoint, passare a tale sito, copiare l'URL e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="c9148-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="c9148-121">L'URL del sito del team predefinito è simile al seguente:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="c9148-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="c9148-122">Immettere un **URL dell'immagine** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="c9148-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="c9148-123">L'immagine verrà visualizzata nella pagina Mie app e nell'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="c9148-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="c9148-124">Suggerimento: l'immagine deve essere di 60x60 pixel ed essere disponibile per tutti gli utenti dell'organizzazione senza richiedere l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c9148-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="c9148-125">Immetti una **Descrizione** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="c9148-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="c9148-126">Questo viene visualizzato quando si seleziona il riquadro nella pagina App personali e si seleziona **Dettagli app**.</span><span class="sxs-lookup"><span data-stu-id="c9148-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="c9148-127">Selezionare **Salva modifiche** per creare il riquadro personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c9148-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="c9148-128">Il riquadro personalizzato viene ora visualizzato nella scheda **Tutte** nell'icona di avvio delle app per te e i tuoi utenti.</span><span class="sxs-lookup"><span data-stu-id="c9148-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="c9148-129">Innalzamento di livello per l'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="c9148-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="c9148-130">Seleziona l'icona di avvio delle app e seleziona **tutte le app**.</span><span class="sxs-lookup"><span data-stu-id="c9148-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="c9148-131">Individuare il nuovo riquadro per l'app, selezionare i puntini di sospensione e scegliere **pin to Launcher**.</span><span class="sxs-lookup"><span data-stu-id="c9148-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="c9148-132">Se il riquadro personalizzato creato nei passaggi precedenti non è visualizzato, verifica di avere una cassetta postale di Exchange Online assegnata e di aver eseguito almeno una volta l'accesso alla tua cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="c9148-132">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="c9148-133">Questi passaggi sono necessari per i riquadri personalizzati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9148-133">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c9148-134">Occorre eseguire questa procedura per alzare di livello i riquadri personalizzati dalla pagina Mie app all'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="c9148-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="c9148-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="c9148-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="c9148-136">Nell'interfaccia di amministrazione, passare alla > **Settings** > scheda Impostazioni<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">profilo organizzazione</a> **impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="c9148-136">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="c9148-137">Nella pagina **profilo organizzazione** , accanto a **Aggiungi riquadri personalizzati per l'organizzazione**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="c9148-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="c9148-138">Aggiorna i valori di **Nome del riquadro**, **URL**, **Descrizione** o **URL immagine** per il riquadro personalizzato (vedi la [Aggiungere un riquadro personalizzato all'icona di avvio delle app](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="c9148-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="c9148-139">Selezionare **Aggiorna** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c9148-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="c9148-140">Per eliminare un riquadro personalizzato, selezionare il riquadro nella finestra **riquadri personalizzati** , quindi selezionare **Rimuovi riquadro** > **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c9148-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="c9148-141">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="c9148-141">What's next?</span></span>

<span data-ttu-id="c9148-142">Oltre all'aggiunta di riquadri all'icona di avvio delle app, è possibile aggiungere riquadri di avvio delle app alla barra di spostamento (ulteriori[informazioni](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="c9148-142">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="c9148-143">Per personalizzare l'aspetto di Microsoft 365 in modo che corrisponda al marchio dell'organizzazione, vedere [Customize the Microsoft 365 Theme](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="c9148-143">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

