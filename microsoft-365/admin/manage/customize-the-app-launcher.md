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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: Crea collegamenti rapidi a posta elettronica, documenti, app, siti SharePoint, siti esterni e altre risorse aggiungendo riquadri personalizzati all'icona di avvio delle app.
ms.openlocfilehash: 0f4141d08811847e8e27cf35975cfa6c6b1b1192
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393680"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Aggiungere riquadri personalizzati all'icona di avvio delle app

In Microsoft 365, puoi accedere rapidamente e facilmente alla posta elettronica, ai calendari, ai documenti e alle app usando l'icona di avvio delle app ([altre informazioni](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Si tratta di app che si ottengono con Microsoft 365 e app personalizzate che si aggiungono da [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD.](/previous-versions/office/office-365-api/)
  
Puoi aggiungere all'icona di avvio delle app riquadri personalizzati che puntano a siti di SharePoint, siti esterni, app legacy e altro ancora. Il riquadro personalizzato appare dopo tutte le app in **Tutte** nell'icona di avvio delle app, ma puoi spostarlo in **Home** e indicare agli utenti di fare lo stesso. In questo modo è più facile trovare i siti, le app e le risorse rilevanti per svolgere il tuo lavoro. Nell'esempio seguente viene usato un riquadro personalizzato, "Portale Contoso", per accedere al sito Intranet di SharePoint dell'organizzazione. 
  
![Icona di avvio delle app](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Aggiungere un riquadro personalizzato all'icona di avvio delle app

1. Accedi all'interfaccia di amministrazione come amministratore globale, vai a Impostazioni  >  **Org Impostazioni** e scegli la scheda Profilo **organizzazione.**
    
2. Nella scheda **Profilo organizzazione** scegliere Riquadri di avvio delle **app personalizzati.**
  
3. Seleziona **Aggiungi un riquadro personalizzato.** 
  
4. Immetti un **Nome del riquadro** per il nuovo riquadro. Il nome verrà visualizzato nel riquadro. 
    
5. Immetti un **URL del sito Web** per il riquadro. Questa è la posizione in cui vuoi che gli utenti vadano quando selezionano il riquadro nell'icona di avvio delle app. Usa HTTPS nell'URL.

    > [!TIP]
    > Se vuoi creare un riquadro per un sito di SharePoint, passa a tale sito, copia l'URL e incollalo in questo campo. L'URL del sito del team predefinito è simile al seguente: `https://<company_name>.sharepoint.com` 
  
6. Immetti un **URL dell'immagine** per il riquadro. L'immagine verrà visualizzata nella pagina Mie app e nell'icona di avvio delle app.

    > [!TIP]
    > L'immagine deve essere di 60x60 pixel ed essere disponibile per tutti gli utenti dell'organizzazione senza richiedere l'autenticazione.

7. Immetti una **Descrizione** per il riquadro. Questo viene visualizzato quando si seleziona il riquadro nella pagina App personali e si seleziona Dettagli **app**. 
  
8. Seleziona **Salva modifiche** per creare il riquadro personalizzato. 
    
    Il riquadro personalizzato viene ora visualizzato nella scheda **Tutte** nell'icona di avvio delle app per te e i tuoi utenti. 

    > [!NOTE]
    > Se il riquadro personalizzato creato nei passaggi precedenti non è visualizzato, verifica di avere una cassetta postale di Exchange Online assegnata e di aver eseguito almeno una volta l'accesso alla tua cassetta postale. Questi passaggi sono necessari per i riquadri personalizzati in Microsoft 365. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Nell'interfaccia di amministrazione passare alla **scheda** Impostazioni  >  **Org Impostazioni**  >  **Profilo organizzazione.**
    
2. Nella pagina **Profilo organizzazione,** accanto a **Aggiungi riquadri personalizzati per l'organizzazione,** selezionare **Modifica.**

3. Aggiorna i valori di **Nome del riquadro**, **URL**, **Descrizione** o **URL immagine** per il riquadro personalizzato (vedi la [Aggiungere un riquadro personalizzato all'icona di avvio delle app](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selezionare **Update** \> **Close**. 
    
Per eliminare un riquadro personalizzato, nella **finestra Riquadri** personalizzati seleziona il riquadro e seleziona **Rimuovi riquadro**  >  **Elimina.** 
  
## <a name="next-steps"></a>Passaggi successivi

Oltre ad aggiungere riquadri all'icona di avvio delle app, puoi aggiungere riquadri di avvio delle app alla barra di spostamento ([altre informazioni](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)). Per personalizzare l'aspetto del Microsoft 365 in base al marchio dell'organizzazione, vedere Personalizzare il tema [Microsoft 365.](../setup/customize-your-organization-theme.md)

## <a name="related-content"></a>Contenuto correlato

[Aggiungere app all'icona di avvio delle app](pin-apps-to-app-launcher.md) degli utenti (articolo)\
[Aggiornare il Microsoft 365 per gli utenti aziendali al client Office](../setup/upgrade-users-to-latest-office-client.md) più recente (articolo)\
[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](../manage/manage-addins-in-the-admin-center.md) (articolo)
