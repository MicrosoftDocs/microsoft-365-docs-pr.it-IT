---
title: Aggiungere riquadri personalizzati all'icona di avvio delle app
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: fff65c7263e40bf376f53e5f150daea7a24ff55d
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131532"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="31d5a-103">Aggiungere riquadri personalizzati all'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="31d5a-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="31d5a-p101">In Office 365 puoi accedere in modo semplice e rapido a posta elettronica, calendari, documenti e app tramite l'icona di avvio delle app di Office 365 ([altre informazioni](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Sono le app che ottieni con Office 365, oltre a quelle personalizzate aggiunte da [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) o [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="31d5a-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="31d5a-p102">Puoi aggiungere all'icona di avvio delle app riquadri personalizzati che puntano a siti di SharePoint, siti esterni, app legacy e altro ancora. Il riquadro personalizzato appare dopo tutte le app in **Tutte** nell'icona di avvio delle app, ma puoi spostarlo in **Home** e indicare agli utenti di fare lo stesso. In questo modo è più facile trovare i siti, le app e le risorse rilevanti per svolgere il tuo lavoro. Nell'esempio seguente viene usato un riquadro personalizzato, "Portale Contoso", per accedere al sito Intranet di SharePoint dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="31d5a-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Avvio app di Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="31d5a-111">Aggiungere un riquadro personalizzato all'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="31d5a-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="31d5a-112">Nell'interfaccia di amministrazione, passare**Settings**  > alla scheda **Impostazioni e**scegliere **profilo organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="31d5a-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="31d5a-113">Nella scheda **profilo organizzazione** , scegliere **tessere di avvio delle app personalizzate**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="31d5a-114">Selezionare **Aggiungi un riquadro personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="31d5a-115">Immetti un **Nome del riquadro** per il nuovo riquadro.</span><span class="sxs-lookup"><span data-stu-id="31d5a-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="31d5a-116">Il nome verrà visualizzato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="31d5a-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="31d5a-117">Immettere un **URL del sito Web** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="31d5a-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="31d5a-118">Questa è la posizione in cui si desidera consentire agli utenti di selezionare il riquadro nell'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="31d5a-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="31d5a-119">Utilizzare HTTPS nell'URL.</span><span class="sxs-lookup"><span data-stu-id="31d5a-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="31d5a-120">Suggerimento: se si sta creando un riquadro per un sito di SharePoint, passare a tale sito, copiare l'URL e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="31d5a-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="31d5a-121">L'URL del sito del team predefinito è simile al seguente:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="31d5a-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="31d5a-122">Immettere un **URL dell'immagine** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="31d5a-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="31d5a-123">L'immagine verrà visualizzata nella pagina Mie app e nell'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="31d5a-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="31d5a-124">Suggerimento: l'immagine deve essere di 60x60 pixel ed essere disponibile per tutti gli utenti dell'organizzazione senza richiedere l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="31d5a-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="31d5a-125">Immetti una **Descrizione** per il riquadro.</span><span class="sxs-lookup"><span data-stu-id="31d5a-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="31d5a-126">Questo viene visualizzato quando si seleziona il riquadro nella pagina App personali e si seleziona **Dettagli app**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="31d5a-127">Selezionare **Salva modifiche** per creare il riquadro personalizzato.</span><span class="sxs-lookup"><span data-stu-id="31d5a-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="31d5a-128">Il riquadro personalizzato viene ora visualizzato nella scheda **Tutte** nell'icona di avvio delle app per te e i tuoi utenti.</span><span class="sxs-lookup"><span data-stu-id="31d5a-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="31d5a-129">Innalzamento di livello per l'icona di avvio delle app</span><span class="sxs-lookup"><span data-stu-id="31d5a-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="31d5a-130">Seleziona l'icona di avvio delle app e seleziona **tutte le app**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="31d5a-131">Individuare il nuovo riquadro per l'app, selezionare i puntini di sospensione e scegliere **pin to Launcher**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="31d5a-p108">Se il riquadro personalizzato creato nei passaggi precedenti non è visualizzato, verifica di avere una cassetta postale di Exchange Online assegnata e di aver eseguito almeno una volta l'accesso alla tua cassetta postale. Questi passaggi sono necessari per i riquadri personalizzati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="31d5a-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="31d5a-134">Occorre eseguire questa procedura per alzare di livello i riquadri personalizzati dalla pagina Mie app all'icona di avvio delle app.</span><span class="sxs-lookup"><span data-stu-id="31d5a-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="31d5a-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="31d5a-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="31d5a-136">Nell'interfaccia di amministrazione, passare alla > **Settings** > scheda Impostazioni<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">profilo organizzazione</a> **impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="31d5a-136">In the admin center, go to the **Settings** > **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> tab.</span></span>
    
2. <span data-ttu-id="31d5a-137">Nella pagina **profilo organizzazione** , accanto a **Aggiungi riquadri personalizzati per l'organizzazione**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="31d5a-138">Aggiorna i valori di **Nome del riquadro**, **URL**, **Descrizione** o **URL immagine** per il riquadro personalizzato (vedi la [Aggiungere un riquadro personalizzato all'icona di avvio delle app](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="31d5a-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="31d5a-139">Selezionare **Aggiorna** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="31d5a-140">Per eliminare un riquadro personalizzato, selezionare il riquadro nella finestra **riquadri personalizzati** , quindi selezionare **Rimuovi riquadro** > **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="31d5a-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="31d5a-141">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="31d5a-141">What's next?</span></span>

<span data-ttu-id="31d5a-p109">Oltre ad aggiungere riquadri all'icona di avvio delle app, puoi aggiungere i riquadri dell'icona di avvio delle app alla barra di spostamento di Office 365 ([altre informazioni](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Per personalizzare l'aspetto di Office 365 in base al marchio della tua organizzazione, vedi [Personalizzare il tema di Office 365](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="31d5a-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

