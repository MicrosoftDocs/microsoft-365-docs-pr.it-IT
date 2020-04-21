---
title: Elenco dispositivi CSV-file
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Informazioni su come creare un file CSV per il pilota automatico in Microsoft 365 for business.
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627861"
---
# <a name="device-list-csv-file"></a>Elenco dispositivi CSV-file

## <a name="device-list-csv-file-format"></a>Formato del file CSV elenco dispositivi

Per gestire e distribuire i dispositivi tramite Windows Autopilot, è necessario un file. csv contenente informazioni specifiche sui dispositivi.
  
Le colonne nel file dell'elenco dei dispositivi devono avere le seguenti intestazioni nell'ordine specificato:
  
- Colonna A: numero di serie del dispositivo

- Colonna B: lasciare vuoto

- Colonna C: hash dell'hardware

È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV. 

Quando si aggiungono dispositivi, è inoltre necessario aggiungerli a un profilo. Un profilo viene utilizzato per applicare i profili di distribuzione dei piloti automatici a un dispositivo o a un gruppo di dispositivi.
  
## <a name="related-articles"></a>Articoli correlati

[Documentazione e risorse su Microsoft 365 per le aziende](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introduzione a Microsoft 365 for business](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[Gestire Microsoft 365 for business](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
