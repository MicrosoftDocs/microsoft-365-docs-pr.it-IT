---
title: Autorizzazioni di funzionalità in EOP
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638119"
---
# <a name="feature-permissions-in-eop"></a>Autorizzazioni per le funzionalità in Exchange Online Protection

Le autorizzazioni necessarie per eseguire le attività di gestione di Exchange Online Protection (EOP) variano a seconda della funzionalità che si sta gestendo.

Per impostare EOP, è necessario essere un amministratore globale o un responsabile di Exchange Company (gruppo di ruoli Gestione organizzazione).

## <a name="exchange-online-protection-permissions"></a>Autorizzazioni Exchange Online Protection

Per individuare le autorizzazioni necessarie per gestire le caratteristiche di EOP, vedere la tabella seguente. Se per una caratteristica sono elencati più gruppi di ruoli, è necessario essere assegnati a uno solo dei gruppi di ruoli per usare tale caratteristica.

|**Funzionalità**|**Autorizzazioni necessarie**|
|:-----|:-----|
|Antimalware|Gestione organizzazione <br/><br/> Gestione igiene|
|Protezione da posta indesiderata|Gestione organizzazione <br/><br/> Gestione igiene|
|Regole del flusso di posta|Gestione organizzazione <br/><br/> Gestione record|
|Domini|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione|
|Advanced Threat Protection (ATP)|Gestione organizzazione <br/><br/> Gestione igiene|
|Connettori Microsoft 365|Gestione organizzazione|
|Traccia dei messaggi|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione|
|Configurazione organizzazione|Gestione organizzazione|
|Quarantena|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione <br/><br/> Gestione igiene|
|Utenti, contatti e gruppi di ruoli|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione <br/><br/> Gestione igiene|
|Gruppi di distribuzione e gruppi di sicurezza|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione <br/><br/> Gestione igiene|
|Visualizzazione di report|Gestione dell'organizzazione: accesso ai report di protezione della posta elettronica. <br/><br/> Destinatari di sola visualizzazione: accesso ai report di protezione della posta elettronica.  <br/><br/> Gestione della conformità: accesso ai report di protezione della posta e ai report di prevenzione della perdita di dati (DLP) (se l'abbonamento ha funzionalità DLP).|
