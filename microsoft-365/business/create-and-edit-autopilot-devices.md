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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Informazioni su come caricare i dispositivi tramite il pilota automatico in Microsoft 365 Business Premium. È possibile assegnare un profilo a un dispositivo o a un gruppo di dispositivi.
ms.openlocfilehash: f2a7f801ae471352595a36b355a874b2de653326
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627395"
---
# <a name="create-and-edit-autopilot-devices"></a>Creare e modificare dispositivi AutoPilot

## <a name="upload-a-list-of-devices"></a>Caricare un elenco di dispositivi

È possibile utilizzare la [Guida dettagliata](add-autopilot-devices-and-profile.md) per caricare i dispositivi, ma è anche possibile caricare i dispositivi nella scheda **dispositivi** . 
  
I dispositivi devono soddisfare i requisiti seguenti:
  
- Windows 10, versione 1703 o successiva
    
- Nuovi dispositivi che non sono stati eseguiti tramite Windows out-of-Box Experience

1. Nell'interfaccia di amministrazione di Microsoft 365, scegliere **Devices** \> **Autopilot**.
  
2. Nella pagina **Autopilot** scegliere la scheda \> **dispositivi** **Aggiungi dispositivi**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Nel pannello **Aggiungi dispositivi** , passare a un [file CSV dell'elenco dei](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) dispositivi preparato \> **Salva** \> **Chiudi**.
    
    È possibile ottenere queste informazioni dal fornitore dell'hardware oppure è possibile utilizzare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Assegnare un profilo a un dispositivo o a un gruppo di dispositivi

1. Nella pagina **prepara Windows** scegliere la scheda **dispositivi** e selezionare la casella di controllo accanto a uno o più dispositivi. 
    
2. Nel pannello **Dispositivo** selezionare un profilo dall'elenco a discesa **Profilo assegnato**. 
    
    Se non è ancora stato creato alcun profilo, per le istruzioni vedere [Creare e modificare profili AutoPilot](create-and-edit-autopilot-profiles.md). 
    
