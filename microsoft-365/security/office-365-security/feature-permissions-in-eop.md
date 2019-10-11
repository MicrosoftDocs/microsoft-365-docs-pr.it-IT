---
title: Autorizzazioni di funzionalità in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Le autorizzazioni necessarie per eseguire le attività di gestione di Microsoft Exchange Online Protection (EOP) variano a seconda della funzionalità che si sta gestendo.
ms.openlocfilehash: 06223b0ec11df0b5a7bedc538913a55ca5998a01
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441553"
---
# <a name="feature-permissions-in-eop"></a>Autorizzazioni per le funzionalità in Exchange Online Protection

Le autorizzazioni necessarie per eseguire le attività di gestione di Exchange Online Protection (EOP) variano a seconda della funzionalità che si sta gestendo.

Per impostare EOP, è necessario essere un amministratore globale di Office 365 o un amministratore di Exchange (il gruppo di ruolo di gestione dell'organizzazione).

## <a name="exchange-online-protection-permissions"></a>Autorizzazioni Exchange Online Protection

Per individuare le autorizzazioni necessarie per gestire le caratteristiche di EOP, vedere la tabella seguente. Se per una caratteristica sono elencati più gruppi di ruoli, è necessario essere assegnati a uno solo dei gruppi di ruoli per usare tale caratteristica.

|**Funzionalità**|**Autorizzazioni necessarie**|
|:-----|:-----|
|Antimalware|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Gestione di Hygiene](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Protezione da posta indesiderata|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Gestione di Hygiene](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Regole del flusso di posta|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](http://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx)|
|Domini|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Protezione avanzata dalle minacce (ATP, Advanced Threat Protection)|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Gestione di Hygiene](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Office 365 connettori|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Traccia dei messaggi|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Configurazione organizzazione|[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Quarantena|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Utenti, contatti e gruppi di ruoli|[Gestione organizzazione](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Gruppi di distribuzione e gruppi di sicurezza|[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](http://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](http://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Visualizzazione di report|[Organization Management](http://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) - gli utenti hanno accesso ai report di protezione della posta.  <br/> [View-Only Recipients](http://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx) - gli utenti hanno accesso ai report di protezione della posta.  <br/> [Compliance Management](http://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx) - gli utenti hanno accesso ai report di protezione della posta e ai report Prevenzione della perdita di dati (DLP) (se la loro sottoscrizione dispone della capacità DLP).|
