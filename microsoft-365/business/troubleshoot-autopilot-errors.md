---
title: Risolvere i problemi relativi ai dispositivi AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informazioni su come risolvere gli errori che potrebbero verificarsi durante l'utilizzo dei file del dispositivo AutoPilot in Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578088"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Risolvere i problemi relativi ai dispositivi AutoPilot

## <a name="device-file-error-messages"></a>Messaggi di errore del file del dispositivo

Ecco informazioni su alcuni degli errori che potresti visualizzare quando lavori con i file del dispositivo AutoPilot in Microsoft 365 Business Premium. 
  
|**Codice di errore**|**Correzione da provare**|
|:-----|:-----|
|Corpo della richiesta non valido  <br/> |Questo errore dovrebbe verificarsi raramente, se viene visualizzato questo errore, provare di nuovo l'operazione.  <br/> |
|Il valore hash hardware per un dispositivo non è corretto.  <br/> |Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per l'hash hardware di un dispositivo non è corretto. Verificare innanzitutto che il valore sia stato digitato correttamente. Se si pensa che il valore sia corretto, ma l'errore continua a verificarsi, chiedere assistenza al fornitore dell'hardware.  <br/> |
|Dispositivo assegnato a un altro tenant  <br/> |Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per il numero di serie o il codice Product Key di uno o più dispositivi non è corretto. Verificare innanzitutto che il valore sia stato digitato correttamente. Se si pensa che il valore sia corretto, ma l'errore continua a verificarsi, chiedere assistenza al fornitore dell'hardware.  <br/> |
|Il file CSV contiene un numero di serie o un codice Product Key non valido  <br/> |Se viene visualizzato questo errore, significa che il dispositivo che si sta tentando di registrare è già registrato da un'altra organizzazione. Per correggere l'errore, chiedere assistenza al fornitore dell'hardware.  <br/> |
|Questo dispositivo non è supportato per la configurazione tramite AutoPilot  <br/> | Questo errore indica che il dispositivo non soddisfa i requisiti di distribuzione di AutoPilot. I dispositivi devono soddisfare questi requisiti:  <br/>  Devono eseguire Windows 10 1703 o versione successiva.  <br/>  Nuovi dispositivi che non hanno mai visto l'esperienza di Windows.  <br/> |
|Dispositivo non trovato  <br/> |Questo errore indica che uno o più dispositivi nel file CSV non sono registrati nell'organizzazione. Per risolvere il problema, chiedere assistenza al fornitore dell'hardware.  <br/> |
