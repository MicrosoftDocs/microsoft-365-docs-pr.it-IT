---
title: Creare e modificare dispositivi AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Informazioni su come caricare dispositivi tramite AutoPilot in Microsoft 365 Business. È possibile assegnare un profilo per un dispositivo o un gruppo di dispositivi.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868528"
---
# <a name="create-and-edit-autopilot-devices"></a>Creare e modificare dispositivi AutoPilot

## <a name="upload-a-list-of-devices"></a>Caricare un elenco di dispositivi

Per caricare i dispositivi, è possibile usare la [Guida dettagliata](add-autopilot-devices-and-profile.md) oppure usare la scheda **Dispositivi**. 
  
I dispositivi devono soddisfare questi requisiti:
  
- Devono eseguire Windows 10 1703 o versione successiva.
    
- Devono essere nuovi dispositivi per i quali non è stata eseguita la Configurazione guidata di Windows.
    
1. Nell'interfaccia di amministrazione di Microsoft 365 Business scegliere **Distribuisci Windows con AutoPilot** nella scheda **Azioni dispositivo**. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi** \> **Aggiungi dispositivi**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Nel Pannello di **dispositivi Add** , passare a un [elenco dei dispositivi di file CSV](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) preparato \> **salvare** \> **Close**.
    
    È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Assegnare un profilo a un dispositivo o a un gruppo di dispositivi

1. Nella pagina **Prepara Windows** scegliere la scheda **Dispositivi** e selezionare la casella di controllo accanto a uno o più dispositivi. 
    
2. Nel pannello **Dispositivo** selezionare un profilo dall'elenco a discesa **Profilo assegnato**. 
    
    Se non è ancora stato creato alcun profilo, per le istruzioni vedere [Creare e modificare profili AutoPilot](create-and-edit-autopilot-profiles.md). 
    
