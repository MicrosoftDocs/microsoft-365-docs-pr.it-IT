---
title: Visualizzare gli errori di sincronizzazione della directory in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Informazioni su come visualizzare gli errori di sincronizzazione della directory e le possibili correzioni nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907505"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Visualizzare gli errori di sincronizzazione della directory in Microsoft 365

È possibile visualizzare gli errori di sincronizzazione della directory nell'interfaccia di amministrazione di Microsoft 365. Vengono visualizzati solo gli errori dell'oggetto User. Per visualizzare gli errori con PowerShell, vedere [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Visualizzare gli errori di sincronizzazione della directory nell'interfaccia di amministrazione di Microsoft 365

Per visualizzare eventuali errori nell'interfaccia di amministrazione di Microsoft 365:
  
1. Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con un account amministratore globale. 
    
2. Nella **home** page verrà visualizzata la **scheda Gestione** utenti. 
    
    ![Scheda Gestione utenti nell'interfaccia di amministrazione di Microsoft 365](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. Nella scheda scegliere Errori **di** sincronizzazione in **Azure AD Connect** per visualizzare gli errori nella pagina Errori di **sincronizzazione della** directory.   
    
    ![Esempio della pagina Errori di sincronizzazione della directory](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Scegliere uno degli errori per visualizzare il riquadro dei dettagli con informazioni sull'errore e suggerimenti su come risolverlo.

   ![Esempio dei dettagli di un errore di sincronizzazione della directory](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Dopo la visualizzazione, vedere risoluzione dei problemi di sincronizzazione della directory per [Microsoft 365](fix-problems-with-directory-synchronization.md) per correggere eventuali problemi identificati.