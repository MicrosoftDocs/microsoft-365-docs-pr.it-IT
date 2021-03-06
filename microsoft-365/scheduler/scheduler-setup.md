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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362547"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configurazione del pianificatore per Microsoft 365


Per configurare l'utilità di Microsoft 365, di seguito sono riportati i prerequisiti:

| Cosa serve? | Descrizione |
|-------------------|-------------|
|Cortana cassetta postale |Gli amministratori tenant dovranno impostare una cassetta postale da utilizzare come cassetta postale "Cortana" (ovvero, cortana@yourdomain.com).         |
|Cassetta postale di Exchange Online |Gli utenti devono disporre di un Exchange Online di posta elettronica e calendario         |
|Licenza dell'utilità di pianificazione |Per informazioni sulle licenze e sui prezzi, vedere [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Creare una cassetta postale per Cortana

Una Exchange nel tenant funge da cassetta postale Cortana per il tenant per inviare e ricevere messaggi di posta elettronica da Cortana. Tutti i messaggi di posta elettronica Cortana vengono conservati nella cassetta postale Cortana tenant in base ai criteri di conservazione.

- Utilizzare il interfaccia di amministrazione di Microsoft 365 per creare una cassetta postale utente. È consigliabile un criterio di conservazione di 30 giorni. 
- Utilizzare il nome Cortana'indirizzo SMTP principale della cassetta postale. Nomi quali "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana. Scheduler@yourdomain.com' sono consigliati.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Designare la cassetta postale come Assistente utilità di pianificazione

Dopo aver creato una cassetta postale univoca Cortana'Utilità di pianificazione, è necessario designare la cassetta postale per Microsoft 365 formalmente. Dopo aver designato la Cortana dell'Utilità di pianificazione, sarà disponibile per pianificare le riunioni per conto degli utenti.

Per designare la cassetta Cortana dell'Utilità di pianificazione, un amministratore autorizzato deve eseguire un comando di PowerShell su una riga. 

1. Connessione per Microsoft 365 di esecuzione remota di PowerShell per l'organizzazione.

2. Eseguire il seguente script di PowerShell per designare la cassetta postale per l'utilità di pianificazione:

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    Dopo aver eseguito questo comando "set" sulla cassetta postale dell'utilità di pianificazione di Cortana, viene impostato un nuovo "PersistedCapability" sulla cassetta postale per notare che questa cassetta postale è "SchedulerAssistant".

> [!NOTE]
> Segui questi passaggi per connettere l'organizzazione a PowerShell se non l'hai fatto in precedenza: Connessione [a Microsoft 365 con PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).

Per individuare la cassetta postale dell'organizzazione attualmente impostata come assistente Cortana, eseguire la funzione get:

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> La cassetta postale dell'utilità di pianificazione potrebbe richiedere fino a due ore per completare il provisioning per impostare la funzionalità SchedulerAssistant.

## <a name="exchange-online-mailbox"></a>Cassetta postale di Exchange Online
Una licenza dell'utilità di pianificazione è un componente aggiuntivo Microsoft 365, che consente all'organizzatore della riunione di delegare le attività di pianificazione delle riunioni all'assistente Utilità di pianificazione. Per il funzionamento dell'Utilità di pianificazione, in genere Microsoft 365 licenza, gli organizzatori delle riunioni richiedono i componenti seguenti:

- Una cassetta postale designata come cassetta postale assistente utilità di pianificazione
- Licenza dell'utilità di pianificazione
- Exchange Online cassetta postale e calendario

I partecipanti alla riunione non richiedono l'utilità di pianificazione o Microsoft 365 licenza.

## <a name="scheduler-end-user-license-requirements"></a>Requisiti di licenza dell'utente finale dell'utilità di pianificazione

Una licenza dell'Utilità di pianificazione richiede una delle licenze seguenti:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Licenza Piano 1 o Piano 2. 

> [!Note]

> L'utilità di Microsoft 365 è disponibile solo in ambienti multi-tenant in tutto il mondo in inglese. **L'utilità Microsoft 365** non è disponibile per gli utenti di:

- Microsoft 365 gestito da 21Vianet in Cina
- Microsoft 365 cloud tedesco che usa il trustee dei dati German Telekom
- Cloud per enti pubblici GCC, consumer, GCC High o DoD

L'utilità di pianificazione supporta gli utenti in Germania la cui posizione dati non si trova nel datacenter tedesco.
