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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Scopri come creare un profilo AutoPilot e applicarlo a un dispositivo, nonché modificare o eliminare un profilo o rimuovere un profilo da un dispositivo.
ms.openlocfilehash: e58418813ed0b4d23a5fa7e1d23aae33d8850e7f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400975"
---
# <a name="create-and-edit-autopilot-profiles"></a>Creare e modificare profili AutoPilot

## <a name="create-a-profile"></a>Creare un profilo

Un profilo si applica a un dispositivo o a un gruppo di dispositivi.
  
1. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Dispositivi** \> **AutoPilot.**
  
2. Nella pagina **AutoPilot** scegliere la **scheda Profili** \> **Crea profilo.**
    
3. Nella pagina **Crea profilo** immettere un nome per il profilo che consente di identificarlo, ad esempio Marketing. Attivare l'impostazione desiderata e quindi scegliere **Salva.** Per ulteriori informazioni sulle impostazioni del profilo AutoPilot, vedere [Informazioni sulle impostazioni del profilo AutoPilot.](autopilot-profile-settings.md)
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Assegnare il profilo a un dispositivo

Dopo aver creato un profilo, puoi applicarlo a un dispositivo o a un gruppo di dispositivi. Puoi selezionare un profilo [](add-autopilot-devices-and-profile.md) esistente nella guida dettagliata e applicarlo a nuovi dispositivi o sostituire un profilo esistente per un dispositivo o un gruppo di dispositivi. 
  
1. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**. 
    
2. Seleziona la casella di controllo accanto al  nome di un dispositivo  e nel pannello Dispositivo scegli un profilo nell'elenco a discesa Profilo assegnato \> **Salva.**
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Modificare, eliminare o rimuovere un profilo

Dopo avere assegnato un profilo a un dispositivo, è possibile aggiornarlo anche se il dispositivo è già stato consegnato a un utente. Quando il dispositivo si connette a Internet, scarica la versione più recente del profilo durante il processo di configurazione. Se l'utente ripristina le impostazioni predefinite del dispositivo, il dispositivo scaricherà nuovamente gli aggiornamenti più recenti per il profilo. 
  
### <a name="edit-a-profile"></a>Modificare un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Profili**. 
    
2. Seleziona la casella di controllo accanto al nome di un dispositivo e nel pannello **Profilo** aggiorna le impostazioni disponibili \> **Salva.**
    
    Se si esegue questa operazione prima che un utente connetta il dispositivo a Internet, il profilo viene applicato al processo di configurazione.
    
### <a name="delete-a-profile"></a>Eliminare un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Profili**. 
    
2. Seleziona la casella di controllo accanto al nome di un dispositivo e nel pannello **Profilo** seleziona **Elimina profilo** \> **Salva.**
    
    Quando si elimina un profilo, questo viene rimosso da un dispositivo o da un gruppo di dispositivi a cui è stato assegnato.
    
### <a name="remove-a-profile"></a>Rimuovere un profilo

1. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi**. 
    
2. Seleziona la casella di controllo accanto al  nome di un dispositivo  e nel pannello Dispositivo scegli **Nessuno** nell'elenco a discesa Profilo assegnato \> **Salva.**
    
