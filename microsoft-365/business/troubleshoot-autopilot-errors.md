---
title: Eseguire la risoluzione dei problemi del dispositivo AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informazioni su come risolvere gli errori file AutoPilot dispositivo.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868459"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Eseguire la risoluzione dei problemi del dispositivo AutoPilot

## <a name="device-file-error-messages"></a>Messaggi di errore file dispositivo

Info Ecco su alcuni degli errori che potrebbero venire visualizzati durante l'utilizzo dei file dei dispositivi AutoPilot in Microsoft 365 Business. 
  
|**Codice di errore**|**Correggere i tentativi**|
|:-----|:-----|
|Corpo della richiesta non valida  <br/> |Questo errore dovrebbe avvenire raramente, se viene visualizzato questo errore, ritentare l'operazione.  <br/> |
|Il valore hash hardware per un dispositivo non è corretto.  <br/> |Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per l'hash hardware di un dispositivo non è corretto. Innanzitutto, verificare che il valore è stato digitato correttamente. Se si ritiene che il valore sia corretto, ma questo errore si verifica ancora, rivolgersi al fornitore dell'hardware del.  <br/> |
|Dispositivo assegnato a un altro tenant  <br/> |Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per il numero di serie o il codice product key di uno o più dispositivi non è corretto. Innanzitutto, verificare che il valore è stato digitato correttamente. Se si ritiene che il valore sia corretto, ma questo errore si verifica ancora, rivolgersi al fornitore dell'hardware del.  <br/> |
|Il file CSV contiene un numero di serie non valido o il codice product key  <br/> |Se viene visualizzato questo errore indica che il dispositivo che è durante il tentativo di effettuare la registrazione è già registrato da un'altra organizzazione. Per risolvere questo problema, rivolgersi al fornitore dell'hardware del.  <br/> |
|Il dispositivo non è supportato per l'installazione utilizzando AutoPilot  <br/> | Questo errore indica che il dispositivo non soddisfa i requisiti di distribuzione AutoPilot. I dispositivi devono soddisfare questi requisiti:  <br/>  Devono eseguire Windows 10 1703 o versione successiva.  <br/>  Devono essere nuovi dispositivi per i quali non è stata eseguita la Configurazione guidata di Windows.  <br/> |
|Dispositivo non trovato  <br/> |Questo errore indica che non è registrato uno o più dispositivi nel file CSV per l'organizzazione. Per risolvere questo problema, rivolgersi al fornitore dell'hardware del.  <br/> |
   
