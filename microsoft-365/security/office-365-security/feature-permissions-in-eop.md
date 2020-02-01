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
ms.openlocfilehash: 2129df7faaa977d59f8af8082291520d33bc9cc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599313"
---
# <a name="feature-permissions-in-eop"></a>Autorizzazioni per le funzionalità in Exchange Online Protection

Le autorizzazioni necessarie per eseguire le attività di gestione di Exchange Online Protection (EOP) variano a seconda della funzionalità che si sta gestendo.

Per impostare EOP, è necessario essere un amministratore globale di Office 365 o un amministratore di Exchange (il gruppo di ruolo di gestione dell'organizzazione).

## <a name="exchange-online-protection-permissions"></a>Autorizzazioni Exchange Online Protection

Per individuare le autorizzazioni necessarie per gestire le caratteristiche di EOP, vedere la tabella seguente. Se per una caratteristica sono elencati più gruppi di ruoli, è necessario essere assegnati a uno solo dei gruppi di ruoli per usare tale caratteristica.

|**Funzionalità**|**Autorizzazioni necessarie**|
|:-----|:-----|
|Antimalware|Gestione organizzazione <br/><br/> Gestione igiene|
|Protezione da posta indesiderata|Gestione organizzazione <br/><br/> Gestione igiene|
|Regole del flusso di posta|Gestione organizzazione <br/><br/> Gestione record|
|Domini|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione|
|Advanced Threat Protection (ATP)|Gestione organizzazione <br/><br/> Gestione igiene|
|Office 365 connettori|Gestione organizzazione|
|Traccia dei messaggi|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione|
|Configurazione organizzazione|Gestione organizzazione|
|Quarantena|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione <br/><br/> Gestione igiene|
|Utenti, contatti e gruppi di ruoli|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione <br/><br/> Gestione igiene|
|Gruppi di distribuzione e gruppi di sicurezza|Gestione organizzazione <br/><br/> Gestione organizzazione sola visualizzazione <br/><br/> Gestione igiene|
|Visualizzazione di report|Gestione dell'organizzazione: accesso ai report di protezione della posta elettronica. <br/><br/> Destinatari di sola visualizzazione: accesso ai report di protezione della posta elettronica.  <br/><br/> Gestione della conformità: accesso ai report di protezione della posta e ai report di prevenzione della perdita di dati (DLP) (se l'abbonamento ha funzionalità DLP).|
