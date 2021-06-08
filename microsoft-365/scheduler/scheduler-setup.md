---
title: Configurazione dell'utilità di Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Configurazione dell'utilità di Microsoft 365.
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809192"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configurazione dell'utilità di pianificazione per Microsoft 365

Per configurare l'utilità di Microsoft 365, di seguito sono riportati i prerequisiti:

|**Cosa serve?** |**Descrizione** |
|-------------------|-------------|
|Cassetta postale di Cortana |Gli amministratori tenant dovranno impostare una cassetta postale da utilizzare come cassetta postale "Cortana" (ovvero, cortana@yourdomain.com).         |
|Cassetta postale di Exchange Online |Gli utenti devono disporre di un Exchange Online di posta elettronica e calendario         |
|Licenza dell'utilità di pianificazione |Per informazioni sulle licenze e sui prezzi, vedere [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Creare una cassetta postale per Cortana
Una Exchange nel tenant funge da cassetta postale di Cortana per il tenant per inviare e ricevere messaggi di posta elettronica da e verso Cortana. Tutti i messaggi di posta elettronica inviati a Cortana vengono conservati nella cassetta postale Cortana del tenant in base ai criteri di conservazione.

- Utilizzare l'Microsoft 365 di amministrazione per creare una cassetta postale utente. È consigliabile un criterio di conservazione di 30 giorni. 
- Utilizzare il nome Cortana nell'indirizzo SMTP principale della cassetta postale. Sono consigliati nomi quali "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana.Scheduler@yourdomain.com".

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Designare la cassetta postale come Assistente utilità di pianificazione

Dopo aver creato una cassetta postale univoca per L'utilità di pianificazione di Cortana, è necessario designare la cassetta postale per Microsoft 365 formalmente. Dopo aver designato la cassetta postale di Cortana Scheduler, sarà disponibile per pianificare le riunioni per conto degli utenti.

Per designare la cassetta postale dell'utilità di pianificazione di Cortana, un amministratore autorizzato deve eseguire un comando di PowerShell su una riga. 

1. Connessione per Microsoft 365 di esecuzione remota di PowerShell per l'organizzazione.
2. Eseguire il seguente script di PowerShell per designare la cassetta postale per l'utilità di pianificazione:

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

Dopo aver eseguito questo comando "set" sulla cassetta postale dell'utilità di pianificazione di Cortana, viene impostato un nuovo "PersistedCapability" sulla cassetta postale per notare che questa cassetta postale è "SchedulerAssistant".

> [!NOTE]
> Segui questi passaggi per connettere l'organizzazione a PowerShell se non l'hai fatto in precedenza: Connessione [a Microsoft 365 con PowerShell - Microsoft 365 Enterprise | Documenti Microsoft](../enterprise/connect-to-microsoft-365-powershell.md)

Per individuare la cassetta postale dell'organizzazione attualmente impostata come assistente utilità di pianificazione di Cortana, esegui la funzione get:
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> La cassetta postale dell'utilità di pianificazione potrebbe richiedere fino a due ore per completare il provisioning per impostare la funzionalità SchedulerAssistant.

## <a name="exchange-online-mailbox"></a>Cassetta postale di Exchange Online
L'utilità di pianificazione è un componente aggiuntivo Microsoft 365. Gli organizzatori della riunione devono disporre di una Exchange Online e di un calendario per il funzionamento dell'Utilità di pianificazione.

## <a name="exchange-requirements"></a>Requisiti di Exchange

Oltre all'Utilità di pianificazione delle licenze, è necessario disporre di una delle licenze seguenti:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Licenza Piano 1 o Piano 2. 

> [!Note]
> **L'utilità Microsoft 365** non è disponibile per gli utenti di Office 365 gestiti da 21Vianet in Cina. Inoltre, non è disponibile per gli utenti di Microsoft 365 con il cloud tedesco che usa il trustee dei dati German Telekom. È supportato per gli utenti in Germania il cui percorso dati non è incluso nel datacenter tedesco.
>
>Questa caratteristica non è supportata per gli utenti di Government Cloud, inclusi GCC, Consumer, GCC High o DoD.
