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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: "Informazioni su come abilitare o disabilitare la funzionalità di disordine per tutti gli utenti o specifici dell'organizzazione, tramite Exchange PowerShell. "
ms.openlocfilehash: 6ba1e3f2b6a8a516a2b55267ab22fb43613350e0
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053837"
---
# <a name="configure-clutter-for-your-organization"></a>Configurare Messaggi secondari per l'organizzazione

> [!TIP]
> [Posta in arrivo evidenziata](../setup/configure-focused-inbox.md) sostituirà Messaggi secondari. Per ulteriori informazioni, vedere [aggiornamento sulla posta in arrivo evidenziata e sui piani per il disordine](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Come amministratore, potrebbe essere necessario gestire la funzionalità di disordine in Microsoft 365. Per attivare o disattivare questa funzionalità per gli utenti dell'organizzazione, è necessario usare Exchange PowerShell. I singoli utenti la possono attivare/disattivare seguendo queste istruzioni: [Disattivare o attivare la funzionalità Messaggi secondari in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx). 
  
Per informazioni sull'uso di Exchange PowerShell, vedere [Uso di PowerShell con Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) e [Connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/?LinkID=722415). È necessario disporre di un account che disponga almeno del ruolo di amministratore del servizio di Exchange e la possibilità di connettersi a Exchange Online con PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Attivare Messaggi secondari mediante Exchange PowerShell

È possibile abilitare Messaggi secondari manualmente per una cassetta postale eseguendo il cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Si possono anche visualizzare le impostazioni di Messaggi secondari per le cassette postali dell'organizzazione eseguendo il cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759). 
  
Attivare Messaggi secondari per un singolo utente di nome Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Disattivare Messaggi secondari mediante Exchange PowerShell

È possibile disabilitare Messaggi secondari manualmente per una cassetta postale eseguendo il cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Si possono anche visualizzare le impostazioni di **Messaggi secondari** per le cassette postali dell'organizzazione eseguendo il cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759). 
  
Disattivare Messaggi secondari per un singolo utente di nome Allie Bellew:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Se si usa PowerShell per creare gli utenti in blocco, occorre eseguire [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) su ogni cassetta postale degli utenti per gestire Messaggi secondari. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>Quando viene visualizzato l'interruttore di attivazione/disattivazione di Messaggi secondari per gli utenti di Outlook sul Web?
<a name="bkmk_onoff"> </a>

Come amministratore, è possibile riattivare l'ingombro utilizzando Exchange PowerShell. Dopo averlo fatto, la funzionalità Posta in arrivo evidenziata verrà disattivata e verrà riattivato Messaggi secondari. 
  
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

[Usare la caratteristica Messaggi secondari per ordinare i messaggi con priorità bassa in Outlook](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[Utilizzo dell'ingombro per ordinare i messaggi con priorità bassa in OWA](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[Disattivare la caratteristica Messaggi secondari in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

