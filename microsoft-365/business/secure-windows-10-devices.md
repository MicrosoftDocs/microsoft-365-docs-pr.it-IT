---
title: Proteggere i dispositivi Windows 10
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Informazioni sulla configurazione delle impostazioni del criterio dispositivo predefinito che qualsiasi dispositivo Windows 10 riceverà all'accesso al proprio account aziendale o dell'istituto di istruzione.
ms.openlocfilehash: 3f85549e722c9aa4196cf50fc02bee2e89506017
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925240"
---
# <a name="secure-windows-10-devices"></a>Proteggere i dispositivi Windows 10

Questo articolo si applica a Microsoft 365 Business Premium.

Le impostazioni configurate qui fanno parte dei criteri predefiniti per i dispositivi Windows 10. Tutti gli utenti che connettono un dispositivo Windows 10, inclusi dispositivi mobili e PC, accedendo con il proprio account aziendale riceveranno automaticamente queste impostazioni. È consigliabile accettare i criteri predefiniti durante l'installazione e aggiungere in un secondo momento i criteri relativi a gruppi di utenti specifici.
  
## <a name="settings-to-secure-windows-10-devices"></a>Impostazioni per la protezione di dispositivi Windows 10

Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti:
  


|Impostazione  <br/> |Descrizione  <br/> |
|:-----|:-----|
|Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus  <br/> |Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.  <br/> |
|Protegge i PC dalle minacce del Web in Microsoft Edge  <br/> |Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.  <br/> |
|Proteggi file e cartelle dei PC dall'accesso non autorizzato con BitLocker  <br/> |Bitlocker protegge i dati crittografando le unità disco rigido del computer e impedisce l'esposizione dei dati in caso di furto o smarrimento di un computer. Per altre informazioni, vedi Domande [frequenti su Bitlocker.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)  <br/> |
|Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo  <br/> |Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo disattivato.  <br/> |
|