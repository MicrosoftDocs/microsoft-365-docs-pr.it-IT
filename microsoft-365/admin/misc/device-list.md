---
title: File CSV elenco dispositivi
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579219"
---
# <a name="device-list-csv-file"></a>File CSV elenco dispositivi

## <a name="device-list-csv-file-format"></a>Formato di file CSV dell'elenco dispositivi

Per gestire e distribuire i dispositivi tramite Windows Autopilot, è necessario un file CSV contenente informazioni specifiche sui dispositivi.
  
Le colonne nel file elenco dispositivi devono avere le intestazioni seguenti nell'ordine specificato:
  
- Colonna A: numero di serie del dispositivo

- Colonna B: lasciare vuoto

- Colonna C: hash dell'hardware

È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV. 

Quando aggiungi dispositivi, devi anche aggiungerli a un profilo. Un profilo viene usato per applicare profili di distribuzione AutoPilot a un dispositivo o a un gruppo di dispositivi.
  
## <a name="related-articles"></a>Articoli correlati

[Documentazione e risorse di Microsoft 365 per le aziende](../../business/index.yml)
  
[Introduzione a Microsoft 365 per le aziende](../../business/microsoft-365-business-overview.md)
  
[Gestire Microsoft 365 per le aziende](../../business/manage.md)
