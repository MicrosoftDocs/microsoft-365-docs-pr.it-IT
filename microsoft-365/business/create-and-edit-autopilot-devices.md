---
title: Creare e modificare dispositivi AutoPilot
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Informazioni su come caricare dispositivi con AutoPilot in Microsoft 365 Business Premium. Puoi assegnare un profilo a un dispositivo o a un gruppo di dispositivi.
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400995"
---
# <a name="create-and-edit-autopilot-devices"></a>Creare e modificare dispositivi AutoPilot

## <a name="upload-a-list-of-devices"></a>Caricare un elenco di dispositivi

Puoi usare la guida [dettagliata per](add-autopilot-devices-and-profile.md) caricare i dispositivi, ma puoi anche caricare i dispositivi nella **scheda** Dispositivi. 
  
I dispositivi devono soddisfare questi requisiti:
  
- Windows 10 versione 1703 o successiva
    
- Nuovi dispositivi che non hanno mai avuto esperienza di Configurazione guidata di Windows

1. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Dispositivi** \> **AutoPilot.**
  
2. Nella pagina **AutoPilot** scegliere la **scheda Dispositivi** \> **Aggiungi dispositivi.**
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Nel pannello **Aggiungi dispositivi** passare a un file CSV [dell'elenco](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) di dispositivi preparato \> **salva** \> **chiudi.**
    
    È possibile ottenere queste informazioni dal fornitore dell'hardware oppure utilizzare lo [script Di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Assegnare un profilo a un dispositivo o a un gruppo di dispositivi

1. Nella pagina **Preparazione di Windows** scegliere la scheda **Dispositivi** e selezionare la casella di controllo accanto a uno o più dispositivi. 
    
2. Nel pannello **Dispositivo** selezionare un profilo dall'elenco a discesa **Profilo assegnato**. 
    
    Se non è ancora stato creato alcun profilo, per le istruzioni vedere [Creare e modificare profili AutoPilot](create-and-edit-autopilot-profiles.md). 
    
