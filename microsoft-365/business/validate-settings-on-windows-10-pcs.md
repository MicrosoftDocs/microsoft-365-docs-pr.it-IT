---
title: Verificare le impostazioni di protezione delle app nei PC Windows 10
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informazioni su come verificare le impostazioni di protezione di applicazioni Microsoft 365 Business nei dispositivi Windows 10.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868446"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Verificare le impostazioni di protezione nei PC Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Verificare che siano impostati i criteri per i dispositivi Windows 10

Dopo aver [configurato i criteri per i dispositivi](protection-settings-for-windows-10-pcs.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti. Per verificare che i criteri siano stati applicati, esaminare le diverse schermate delle impostazioni di Windows sui dispositivi degli utenti. Gli utenti non possono modificare le impostazioni di Windows Update e Windows Defender Antivirus nei dispositivi Windows 10, quindi molte di queste opzioni saranno disattivate.
  
1. Passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Update** \> **riavviare le opzioni** e verificare che tutte le impostazioni sono in grigio. 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Update** \> **Opzioni avanzate** e verificare che tutte le impostazioni sono in grigio. 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Update** \> **Opzioni avanzate** \> **scegliere la modalità di recapito degli aggiornamenti**.
    
    Verificare che il messaggio che indica che alcune impostazioni sono nascoste o gestite dall'organizzazione sia visibile (in rosso) e che tutte le opzioni siano disattivate.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Per aprire il Centro protezione di Windows Defender, passare a **Impostazioni** \> **aggiornamento &amp; protezione** \> **Windows Defender** \> fare clic su **Centro protezione di Apri Windows Defender** \> **Virus &amp; thread protezione** \> **Virus &amp; le impostazioni di protezione delle minacce**. 
    
5. Verificare che tutte le opzioni siano disattivate. 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Argomenti correlati

[Documentazione e risorse su Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introduzione a Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Gestire Microsoft 365 Business](manage.md)
  
[Impostare le configurazioni dei dispositivi per PC Windows 10](protection-settings-for-windows-10-pcs.md)
  

