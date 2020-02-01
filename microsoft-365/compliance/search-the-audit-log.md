---
title: Eseguire una ricerca nel registro di controllo per l'attività di utenti e amministratori in Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: "Il registro di controllo di Office 365 è un log di controllo unificato. Perché usare un log di controllo unificato? Poiché gli eventi provenienti dalla maggior parte dei servizi di Office 365 in cui si esegue la sottoscrizione dell'organizzazione vengono registrati in un singolo log di controllo che è possibile ricercare. Questo significa che è possibile cercare l'attività di utenti e amministratori in questi servizi:"
ms.openlocfilehash: 82ed3c1afd4f59136b04120982ddb1433f4dd0eb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597533"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a>Eseguire una ricerca nel registro di controllo per l'attività di utenti e amministratori in Office 365

Il registro di controllo di Office 365 è un log di controllo unificato. Perché usare un log di controllo unificato? Poiché gli eventi provenienti dalla maggior parte dei servizi di Office 365 in cui si esegue la sottoscrizione dell'organizzazione vengono registrati in un singolo log di controllo che è possibile ricercare. Questo significa che è possibile cercare l'attività di utenti e amministratori in questi servizi: 
  
- SharePoint
- OneDrive
- Exchange
- Azure Active Directory
- Microsoft Teams
- eDiscovery
- Power BI
- Yammer
- Sway
- Microsoft Stream
   
 ## <a name="set-up-auditing"></a>Configurare il controllo
  
Prima di eseguire la ricerca nel registro di controllo di Office 365, è necessario eseguire alcune operazioni.
  
- [Attivare la ricerca del registro di controllo](turn-audit-log-search-on-or-off.md) per avviare la registrazione di eventi che è possibile cercare 
    
- [Abilitare il controllo delle cassette postali](enable-mailbox-auditing.md) in modo da poter cercare gli eventi relativi alle cassette postali. ad esempio, quando un utente accede alla propria cassetta postale o Elimina gli elementi dalla cartella elementi ripristinabili 
    
 ## <a name="search-the-audit-log"></a>Eseguire ricerche nel log di controllo
  
Dopo aver attivato il controllo, è possibile eseguire la ricerca di centinaia di singoli tipi di eventi provenienti da più servizi di Office 365.
  
- [Eseguire una ricerca nel registro di controllo per le](search-the-audit-log-in-security-and-compliance.md) attività di utenti e amministratori 
    
- [Comprendere le proprietà dettagliate](detailed-properties-in-the-office-365-audit-log.md) di ogni record di controllo incluso nei risultati della ricerca 
    
- [Ricerca di attività correlate a eDiscovery](search-for-ediscovery-activities-in-the-audit-log.md) eseguite da amministratori e responsabili della conformità 
