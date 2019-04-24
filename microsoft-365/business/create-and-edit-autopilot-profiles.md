---
title: Creare e modificare profili AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Informazioni su come creare, modificare, eliminare o rimuovere profili Autopilot. '
ms.openlocfilehash: 85fc897b2f428afae8d55feeb577021adaa30f72
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277127"
---
# <a name="create-and-edit-autopilot-profiles"></a>Creare e modificare profili AutoPilot

## <a name="create-a-profile"></a>Creare un profilo

Un profilo si applica a un dispositivo o a un gruppo di dispositivi.
  
1. nell'interfaccia di amministrazione di Microsoft 365 Business, **** \> scegliere devices autopilot. ****
  
2. Nella pagina **Autopilot** scegliere la \> scheda **profili** **creare profilo**.
    
3. Nella pagina **Crea profilo** immettere un nome per il profilo che ne faciliti l'identificazione, ad esempio Marketing, quindi attivare l'impostazione desiderata (per altre informazioni, vedere [Informazioni sulle impostazioni del profilo AutoPilot](autopilot-profile-settings.md)) e infine scegliere **Salva**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Assegnare il profilo a un dispositivo

Dopo aver creato un profilo, è possibile applicarlo a un dispositivo o a un gruppo di dispositivi. È possibile selezionare un profilo esistente nella [guida dettagliata](add-autopilot-devices-and-profile.md), applicarlo a nuovi dispositivi oppure sostituire un profilo esistente per un dispositivo o un gruppo di dispositivi. 
  
1. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Dispositivo** scegliere un profilo nell'elenco a discesa **Profilo assegnato** \> **Salva**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Modificare, eliminare o rimuovere un profilo

Dopo avere assegnato un profilo a un dispositivo, è possibile aggiornarlo anche se il dispositivo è già stato consegnato a un utente. Quando il dispositivo si connette a Internet, scarica la versione più recente del profilo durante il processo di configurazione. Se l'utente ripristina le impostazioni predefinite del dispositivo, il dispositivo scaricherà nuovamente gli aggiornamenti più recenti per il profilo. 
  
### <a name="edit-a-profile"></a>Modificare un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Profili**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Profilo** aggiornare una qualsiasi delle impostazioni disponibili \> **Salva**.
    
    Se si esegue questa operazione prima che un utente connetta il dispositivo a Internet, il profilo viene applicato al processo di configurazione.
    
### <a name="delete-a-profile"></a>Eliminare un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Profili**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Profilo** fare clic su **Elimina profilo** \> **Salva**.
    
    Quando si elimina un profilo, questo viene rimosso da un dispositivo o da un gruppo di dispositivi a cui è stato assegnato.
    
### <a name="remove-a-profile"></a>Rimuovere un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **Dispositivo** scegliere **Nessuno** nell'elenco a discesa **Profilo assegnato** \> **Salva**.
    
