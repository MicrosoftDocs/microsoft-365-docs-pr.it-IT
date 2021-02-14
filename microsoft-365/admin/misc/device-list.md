---
title: File CSV dell'elenco di dispositivi
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Informazioni su come creare un file CSV per AutoPilot in Microsoft 365 per le aziende.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399363"
---
# <a name="device-list-csv-file"></a>File CSV dell'elenco di dispositivi

## <a name="device-list-csv-file-format"></a>Formato di file CSV dell'elenco di dispositivi

Per gestire e distribuire i dispositivi tramite Windows Autopilot, è necessario un file CSV contenente informazioni specifiche sui dispositivi.
  
Le colonne nel file dell'elenco dei dispositivi devono avere le intestazioni seguenti nell'ordine specificato:
  
- Colonna A: numero di serie del dispositivo

- Colonna B: lasciare vuoto

- Colonna C: hash dell'hardware

È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV. 

Quando aggiungi dispositivi, devi anche aggiungerli a un profilo. Un profilo viene usato per applicare profili di distribuzione AutoPilot a un dispositivo o a un gruppo di dispositivi.
  
## <a name="related-articles"></a>Articoli correlati

[Documentazione e risorse di Microsoft 365 per le aziende](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introduzione a Microsoft 365 per le aziende](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[Gestire Microsoft 365 per le aziende](https://docs.microsoft.com/microsoft-365/business/manage)
  
