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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286189"
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

- Utilizzare l'Microsoft 365 di amministrazione per creare una nuova cassetta postale. È consigliabile un criterio di conservazione di 30 giorni. Utilizzare il nome Cortana nell'indirizzo SMTP principale della cassetta postale. Sono consigliati nomi quali "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" o "Cortana.Scheduler@yourdomain.com".
- Contatta Microsoft (scheduler_m365@microsoft.com) per abilitare la cassetta postale di Cortana. 

> [!IMPORTANT]
> È necessario contattare Microsoft per configurare la cassetta postale di Cortana per l'utilizzo del servizio Utilità di pianificazione tramite posta elettronica scheduler_m365@microsoft.com. L'abilitazione della cassetta postale di Cortana può richiedere fino a due settimane.

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
