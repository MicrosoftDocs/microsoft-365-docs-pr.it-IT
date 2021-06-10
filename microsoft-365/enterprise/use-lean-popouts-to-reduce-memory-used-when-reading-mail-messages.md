---
title: Utilizzare popout snelli per ridurre la memoria utilizzata durante la lettura dei messaggi di posta elettronica
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: In questo articolo sono contenute informazioni sull'utilizzo di popout snelli per migliorare le prestazioni di download dei messaggi Outlook sul Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925257"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Utilizzare popout snelli per ridurre la memoria utilizzata durante la lettura dei messaggi di posta elettronica

Questo articolo contiene informazioni per migliorare le prestazioni di download dei messaggi Outlook sul Web. Questo articolo fa parte di Pianificazione della rete [e ottimizzazione delle](./network-planning-and-performance.md) prestazioni per Office 365 progetto.
  
In quanto amministratore globale Office 365, è possibile configurare Outlook sul Web per fornire _popout_ snelli, una versione più piccola e con un utilizzo minore della memoria di alcuni messaggi di posta elettronica in Microsoft Edge o Internet Explorer. Quando i popup snelli sono configurati per Outlook sul Web, vengono caricati i componenti di rendering sul lato server che ottimizzano le prestazioni.
  
> [!NOTE]
> A partire da marzo 2018, i popup snelli non sono disponibili per i messaggi che specificano restrizioni per i diritti di utilizzo, ad esempio Information Rights Management (IRM).
  
Queste funzionalità continueranno a funzionare nella finestra principale, ma non sono disponibili nei popup snelli:
  
- Outlook componenti aggiuntivi
  
- Skype for Business presenza
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Per configurare i popup snelli per tutti gli utenti all'interno dell'Office 365 organizzazione
  
1. [Connessione utilizzare Exchange Online PowerShell remoto.](/powershell/exchange/connect-to-exchange-online-powershell)
  
2. Eseguire il cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) con il parametro LeanPopoutEnabled come indicato di seguito:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Ad esempio, per abilitare i popup snelli per tutti gli utenti dell'organizzazione:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Per disabilitare i popup snelli per tutti gli utenti dell'organizzazione:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```