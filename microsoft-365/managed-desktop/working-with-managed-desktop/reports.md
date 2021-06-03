---
title: Usare i report
description: I vari report disponibili in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729969"
---
# <a name="work-with-reports"></a>Usare i report

Microsoft Managed Desktop fornisce diversi report e dashboard che gli amministratori IT dell'organizzazione possono usare per comprendere diversi aspetti della popolazione di dispositivi.I report sono disponibili in due posizioni: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) e nell'Microsoft 365 [admin center.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Report in Microsoft Endpoint Manager

La Microsoft Endpoint Manager console riunisce i report di diversi prodotti in un'unica posizione per monitorare e analizzare i problemi relativi alla configurazione e ai dispositivi dell'organizzazione di Azure AD ("tenant"). Microsoft Managed desktop include  una sezione in Report nel menu principale in cui è possibile trovare report specifici per la gestione dei dispositivi registrati da Microsoft Managed Desktop di Microsoft Managed Desktop.

Questi report includono:
- **Dispositivi gestiti**  >  **Aggiornamenti delle funzionalità**: questa visualizzazione mostra lo stato complessivo degli aggiornamenti delle funzionalità nei dispositivi Microsoft Managed Desktop dispositivi.
- **Dispositivi gestiti**  >  **Office aggiornamenti**: questa visualizzazione mostra lo stato complessivo degli aggiornamenti Office nei dispositivi Microsoft Managed Desktop dispositivi.

Inoltre, in diverse posizioni in Microsoft Endpoint Manager è possibile filtrare i report di altri gruppi di prodotti per includere o escludere in modo specifico i dispositivi gestiti da Microsoft Managed Desktop. Questi report hanno integrato questa funzionalità di filtro:

- [Tutti i dispositivi](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Conformità dispositivo](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivi non conformi](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> I Microsoft Managed Desktop personalizzati garantiscono l'accesso solo ai Microsoft Managed Desktop report. Per accedere ad altre parti di Microsoft Endpoint Manager, ad esempio **Tutti** i dispositivi, vedi Controllo dell'accesso basato sui ruoli [con](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune . 


 ## <a name="inventory-data"></a>Dati di inventario

Oltre agli altri report, puoi esportare informazioni sui dispositivi gestiti da Microsoft Managed Desktop. Nella visualizzazione **Dispositivi** dell'area **Dispositivi** di Microsoft Endpoint Manager,  usa la scheda Esporta tutto per [scaricare un report inventario dettagliato.](device-inventory-report.md)