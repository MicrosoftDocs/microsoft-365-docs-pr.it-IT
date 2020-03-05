---
title: Creare e modificare profili AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Informazioni su come creare un profilo pilota automatico e applicarlo a un dispositivo, nonché modificare o eliminare un profilo o rimuovere un profilo da un dispositivo.
ms.openlocfilehash: 6a8057969242d839ebbb4cbef8d26dd3f1858c59
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417337"
---
# <a name="create-and-edit-autopilot-profiles"></a>Creare e modificare profili AutoPilot

## <a name="create-a-profile"></a>Creare un profilo

Un profilo si applica a un dispositivo o a un gruppo di dispositivi.
  
1. Nell'interfaccia di amministrazione di Microsoft 365 business, scegliere **Devices** \> **Autopilot**.
  
2. Nella pagina **Autopilot** scegliere la scheda \> **profili** **creare profilo**.
    
3. Nella pagina **Crea profilo** , immettere un nome per il profilo che consenta di identificarlo, ad esempio marketing. Attiva l'impostazione desiderata e quindi scegli **Salva**. Per ulteriori informazioni sulle impostazioni dei profili Autopilot, vedere [informazioni sulle impostazioni dei profili Autopilot](autopilot-profile-settings.md).
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Assegnare il profilo a un dispositivo

Dopo aver creato un profilo, è possibile applicarlo a un dispositivo o a un gruppo di dispositivi. È possibile selezionare un profilo esistente nella [Guida dettagliata](add-autopilot-devices-and-profile.md) e applicarlo ai nuovi dispositivi oppure sostituire un profilo esistente per un dispositivo o un gruppo di dispositivi. 
  
1. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **dispositivo** scegliere un profilo dall'elenco \> a discesa **profilo assegnato** **Salva**.
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Modificare, eliminare o rimuovere un profilo

Dopo avere assegnato un profilo a un dispositivo, è possibile aggiornarlo anche se il dispositivo è già stato consegnato a un utente. Quando il dispositivo si connette a Internet, scarica la versione più recente del profilo durante il processo di configurazione. Se l'utente ripristina le impostazioni predefinite del dispositivo, il dispositivo scaricherà nuovamente gli aggiornamenti più recenti per il profilo. 
  
### <a name="edit-a-profile"></a>Modificare un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Profili**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **profilo** aggiornare le impostazioni \> disponibili per il **salvataggio**.
    
    Se si esegue questa operazione prima che un utente connetta il dispositivo a Internet, il profilo viene applicato al processo di configurazione.
    
### <a name="delete-a-profile"></a>Eliminare un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Profili**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **profilo** selezionare **Delete profile** \> **Save**.
    
    Quando si elimina un profilo, questo viene rimosso da un dispositivo o da un gruppo di dispositivi a cui è stato assegnato.
    
### <a name="remove-a-profile"></a>Rimuovere un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**. 
    
2. Selezionare la casella di controllo accanto a un nome di dispositivo e nel pannello **dispositivo** scegliere **nessuno** nell'elenco \> a discesa **profilo assegnato** **Salva**.
    
