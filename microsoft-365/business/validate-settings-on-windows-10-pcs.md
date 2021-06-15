---
title: Convalidare le impostazioni di protezione delle app Windows 10 PC
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Scopri come verificare che le impostazioni di Microsoft 365 per le app aziendali siano applicate ai dispositivi Windows 10 degli utenti.
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925260"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>Convalidare le impostazioni di protezione dei Windows 10 PC

## <a name="verify-that-windows-10-device-policies-are-set"></a>Verificare che siano impostati i criteri per i dispositivi Windows 10

Dopo aver [configurato i criteri per i dispositivi](protection-settings-for-windows-10-pcs.md), possono essere necessarie alcune ore prima che i criteri siano applicati ai dispositivi degli utenti. Per verificare che i criteri siano stati applicati, esaminare le diverse schermate delle impostazioni di Windows sui dispositivi degli utenti. Poiché gli utenti non saranno in grado di modificare le impostazioni di Windows Update e Windows Defender Antivirus nei dispositivi Windows 10, molte opzioni saranno disattivate.
  
1. Vai **a** Impostazioni aggiorna la sicurezza Windows opzioni di riavvio dell'aggiornamento e verifica che tutte le impostazioni \> **&amp;** \>  \>  siano disattivate. 
    
    ![Tutte le opzioni di riavvio sono disattivate.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vai a **Impostazioni** aggiornamento della sicurezza Windows Opzioni avanzate di aggiornamento e verifica che tutte le impostazioni \> **&amp;** \>  \>  siano disattivate. 
    
    ![Windows Le opzioni degli aggiornamenti avanzati sono tutte disattivate.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Verificare che sia possibile visualizzare il messaggio (in rosso) che alcune impostazioni sono nascoste o gestite dall'organizzazione e che tutte le opzioni sono in grigio.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Verificare che tutte le opzioni siano disattivate. 
    
    ![Le impostazioni di Protezione da virus e minacce sono disattivate.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Argomenti correlati

[Microsoft 365 documentazione e risorse per le aziende](./index.yml)
  
[Introduzione a Microsoft 365 per le aziende](microsoft-365-business-overview.md)
  
[Gestire Microsoft 365 per le aziende](manage.md)
  
[Impostare le configurazioni dei dispositivi per PC Windows 10](protection-settings-for-windows-10-pcs.md)
