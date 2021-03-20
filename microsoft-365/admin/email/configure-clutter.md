---
title: Configurare Messaggi secondari per l'organizzazione
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: "Informazioni su come abilitare o disabilitare la funzionalità Messaggi secondari per tutti gli utenti o specifici dell'organizzazione tramite PowerShell di Exchange. "
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915903"
---
# <a name="configure-clutter-for-your-organization"></a>Configurare Messaggi secondari per l'organizzazione

> [!TIP]
> [Posta in arrivo evidenziata](../setup/configure-focused-inbox.md) sostituirà Messaggi secondari. Ulteriori informazioni: [Aggiornamento in Posta in arrivo mirata e piani per Messaggi secondari](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
In quanto amministratore, potrebbe essere necessario gestire la funzionalità Messaggi secondari in Microsoft 365. Per attivare o disattivare questa funzionalità per gli utenti dell'organizzazione, è necessario usare Exchange PowerShell. Gli utenti possono attivarlo/disattivarlo usando queste istruzioni: [Disattivare/attivare Messaggi secondari in Outlook.](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
  
Per informazioni sull'uso di Exchange PowerShell, vedere [Uso di PowerShell con Exchange Online](/powershell/exchange/exchange-online-powershell) e [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). È necessario disporre di un account con almeno il ruolo di amministratore del servizio Exchange e la possibilità di connettersi a Exchange Online con PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Attivare Messaggi secondari mediante Exchange PowerShell

È possibile abilitare Messaggi secondari manualmente per una cassetta postale eseguendo il cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter). Si possono anche visualizzare le impostazioni di Messaggi secondari per le cassette postali dell'organizzazione eseguendo il cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter). 
  
Attivare Messaggi secondari per un singolo utente di nome Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Disattivare Messaggi secondari mediante Exchange PowerShell

È possibile disabilitare Messaggi secondari manualmente per una cassetta postale eseguendo il cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter). Si possono anche visualizzare le impostazioni di **Messaggi secondari** per le cassette postali dell'organizzazione eseguendo il cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter). 
  
Disattivare Messaggi secondari per un singolo utente di nome Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Se si usa PowerShell per creare gli utenti in blocco, occorre eseguire [Set-Clutter](/powershell/module/exchange/set-clutter) su ogni cassetta postale degli utenti per gestire Messaggi secondari. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Quando viene visualizzato l'interruttore di attivazione/disattivazione di Messaggi secondari per gli utenti di Outlook sul Web?
<a name="bkmk_onoff"> </a>

In quanto amministratore, è possibile ri abilitare Messaggi secondari tramite PowerShell di Exchange. Dopo averlo fatto, la funzionalità Posta in arrivo evidenziata verrà disattivata e verrà riattivato Messaggi secondari. 
  
 **Se si utilizza Outlook sul Web con un abbonamento a Microsoft 365 Business Premium:**
  
- Se l'utente ha abilitato Messaggi secondari: 
    
  - Vengono visualizzate le impostazioni di Messaggi secondari
    
- Se l'utente ha abilitato Posta in arrivo evidenziata: 
    
  - Le impostazioni di Messaggi secondari non vengono visualizzate
    
- Se non è abilitato né Messaggi secondari né Posta in arrivo evidenziata: 
    
  - Sia Messaggi secondari che Posta in arrivo evidenziata vengono visualizzati come opzioni nelle impostazioni di posta elettronica dell'utente
    
 **Se si usa Outlook.com:**
  
- Se l'utente ha abilitato Messaggi secondari: 
    
  - Vengono visualizzate le impostazioni di Messaggi secondari
    
- Se l'utente ha abilitato Posta in arrivo evidenziata: 
    
  - Le impostazioni di Messaggi secondari non vengono visualizzate
    
- Se non è abilitato né Messaggi secondari né Posta in arrivo evidenziata: 
    
  - Sia Messaggi secondari che Posta in arrivo evidenziata vengono visualizzati come opzioni nelle impostazioni di posta elettronica dell'utente
    
- Se in passato l'utente ha abilitato la Posta in arrivo evidenziata:
    
  - Le impostazioni di Messaggi secondari non verranno mai visualizzate
    
    Altrimenti: 
    
  - Vengono visualizzate le impostazioni di Messaggi secondari
    
## <a name="related-articles"></a>Articoli correlati
<a name="bkmk_onoff"> </a>

[Usare la caratteristica Messaggi secondari per ordinare i messaggi con priorità bassa in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Utilizzare Messaggi secondari per ordinare i messaggi con priorità bassa OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[Disattivare la caratteristica Messaggi secondari in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
