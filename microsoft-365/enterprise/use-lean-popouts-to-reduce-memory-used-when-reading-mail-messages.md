---
title: Utilizzo di Lean popout per ridurre la memoria utilizzata per la lettura dei messaggi di posta elettronica
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
description: In questo articolo sono contenute informazioni per l'utilizzo di Lean popout per migliorare le prestazioni di download dei messaggi in Outlook sul Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691442"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Utilizzo di Lean popout per ridurre la memoria utilizzata per la lettura dei messaggi di posta elettronica

In questo articolo sono contenute informazioni per migliorare le prestazioni di download dei messaggi in Outlook sul Web. Questo articolo fa parte del progetto di [pianificazione della rete e ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune) .
  
In qualità di amministratore globale di Office 365, è possibile configurare Outlook sul Web per la distribuzione di _Lean popout_, una versione di alcuni messaggi di posta elettronica di Microsoft Edge o Internet Explorer meno intensiva per la memoria. Quando Lean popout sono configurati per Outlook sul Web, i componenti di rendering sul fianco del server vengono caricati in modo da ottimizzare le prestazioni.
  
> [!NOTE]
> A marzo 2018, Lean popout non è disponibile per i messaggi che specificano le restrizioni relative ai diritti di utilizzo, ad esempio Information Rights Management (IRM).
  
Queste funzionalità continueranno a funzionare nella finestra principale, ma non sono disponibili in Lean popout:
  
- Componenti aggiuntivi di Outlook
  
- Presenza di Skype for business
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Per configurare Lean popout per tutti gli utenti all'interno dell'organizzazione di Office 365
  
1. [Connettersi a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).
  
2. Eseguire il cmdlet [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) con il parametro LeanPopoutEnabled, come indicato di seguito:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Ad esempio, per abilitare Lean popout per tutti gli utenti dell'organizzazione:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Per disabilitare Lean popout per tutti gli utenti dell'organizzazione:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
