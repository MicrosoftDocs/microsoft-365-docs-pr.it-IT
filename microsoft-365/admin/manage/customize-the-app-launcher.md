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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: "Creare collegamenti rapidi per la posta elettronica, i documenti, le app, i siti di SharePoint, i siti esterni e altre risorse mediante l'aggiunta di sezioni personalizzate all'icona di avvio delle app. "
ms.openlocfilehash: cebb4385e40f2cef68d3ee26dca1cb905c8d91c5
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552495"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Aggiungere riquadri personalizzati all'icona di avvio delle app

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

In Microsoft 365 è possibile accedere rapidamente e facilmente alla posta elettronica, ai calendari, ai documenti e alle app utilizzando l'icona di avvio delle app ([altre informazioni](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Queste sono le app che si ottengono con Microsoft 365, nonché le app personalizzate che si aggiungono da [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure ad](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).
  
Puoi aggiungere all'icona di avvio delle app riquadri personalizzati che puntano a siti di SharePoint, siti esterni, app legacy e altro ancora. Il riquadro personalizzato appare dopo tutte le app in **Tutte** nell'icona di avvio delle app, ma puoi spostarlo in **Home** e indicare agli utenti di fare lo stesso. In questo modo è più facile trovare i siti, le app e le risorse rilevanti per svolgere il tuo lavoro. Nell'esempio seguente viene usato un riquadro personalizzato, "Portale Contoso", per accedere al sito Intranet di SharePoint dell'organizzazione. 
  
![Icona di avvio delle app](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Aggiungere un riquadro personalizzato all'icona di avvio delle app

1. Accedere all'interfaccia di amministrazione come amministratore globale, passare a impostazioni org delle **Impostazioni**  >  **Org Settings**e scegliere la scheda **profilo organizzazione** .
    
2. Nella scheda **profilo organizzazione** , scegliere **tessere di avvio delle app personalizzate**.
  
3. Selezionare **Aggiungi un riquadro personalizzato**. 
  
4. Immetti un **Nome del riquadro** per il nuovo riquadro. Il nome verrà visualizzato nel riquadro. 
    
5. Immettere un **URL del sito Web** per il riquadro. Questa è la posizione in cui si desidera consentire agli utenti di selezionare il riquadro nell'icona di avvio delle app. Utilizzare HTTPS nell'URL.<br/>Suggerimento: se si sta creando un riquadro per un sito di SharePoint, passare a tale sito, copiare l'URL e incollarlo qui. L'URL del sito del team predefinito è simile al seguente:`https://<company_name>.sharepoint.com` 
  
6. Immettere un **URL dell'immagine** per il riquadro. L'immagine verrà visualizzata nella pagina Mie app e nell'icona di avvio delle app.<br/>Suggerimento: l'immagine deve essere di 60x60 pixel ed essere disponibile per tutti gli utenti dell'organizzazione senza richiedere l'autenticazione.

7. Immetti una **Descrizione** per il riquadro. Questo viene visualizzato quando si seleziona il riquadro nella pagina App personali e si seleziona **Dettagli app**. 
  
8. Selezionare **Salva modifiche** per creare il riquadro personalizzato. 
    
Il riquadro personalizzato viene ora visualizzato nella scheda **Tutte** nell'icona di avvio delle app per te e i tuoi utenti. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Innalzamento di livello per l'icona di avvio delle app

1. Seleziona l'icona di avvio delle app e seleziona **tutte le app**. 
    
2. Individuare il nuovo riquadro per l'app, selezionare i puntini di sospensione e scegliere **pin to Launcher**.
  
    > [!NOTE]
    > Se il riquadro personalizzato creato nei passaggi precedenti non è visualizzato, verifica di avere una cassetta postale di Exchange Online assegnata e di aver eseguito almeno una volta l'accesso alla tua cassetta postale. Questi passaggi sono necessari per i riquadri personalizzati in Microsoft 365. 
  
> [!IMPORTANT]
> Occorre eseguire questa procedura per alzare di livello i riquadri personalizzati dalla pagina Mie app all'icona di avvio delle app. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Nell'interfaccia di amministrazione, passare alla scheda **Impostazioni**  >  **organizzazione impostazioni org**  >  **Organization profile** </a> .
    
2. Nella pagina **profilo organizzazione** , accanto a **Aggiungi riquadri personalizzati per l'organizzazione**, selezionare **modifica**.

3. Aggiorna i valori di **Nome del riquadro**, **URL**, **Descrizione** o **URL immagine** per il riquadro personalizzato (vedi la [Aggiungere un riquadro personalizzato all'icona di avvio delle app](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selezionare **Aggiorna** \> **Chiudi**. 
    
Per eliminare un riquadro personalizzato, selezionare il riquadro nella finestra **riquadri personalizzati** , quindi selezionare **Rimuovi riquadro**  >  **Elimina**. 
  
## <a name="whats-next"></a>Operazioni successive

Oltre all'aggiunta di riquadri all'icona di avvio delle app, è possibile aggiungere riquadri di avvio delle app alla barra di spostamento (ulteriori[informazioni](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)). Per personalizzare l'aspetto di Microsoft 365 in modo che corrisponda al marchio dell'organizzazione, vedere [Customize the Microsoft 365 Theme](../setup/customize-your-organization-theme.md).
  
