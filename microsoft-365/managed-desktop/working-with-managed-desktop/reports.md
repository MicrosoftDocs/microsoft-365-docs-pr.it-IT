---
title: Usare i report
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917683"
---
# <a name="work-with-reports"></a>Usare i report

Microsoft Managed Desktop fornisce diversi report e dashboard che gli amministratori IT dell'organizzazione possono utilizzare per comprendere vari aspetti della popolazione di dispositivi.I report sono disponibili in due posizioni: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) e nell'interfaccia di amministrazione di Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Report in Microsoft Endpoint Manager

La console di Microsoft Endpoint Manager riunisce i report di diversi prodotti in un'unica posizione per monitorare e analizzare i problemi relativi alla configurazione e ai dispositivi dell'organizzazione di Azure AD ("tenant"). Microsoft Managed desktop include una sezione in **Report** nel menu principale in cui è possibile trovare report specifici per la gestione dei dispositivi registrati da Microsoft Managed Desktop.

Questi report includono:
- **Dispositivi gestiti**  >  **Aggiornamenti delle** funzionalità : questa visualizzazione mostra lo stato complessivo degli aggiornamenti delle funzionalità nei dispositivi Microsoft Managed Desktop.
- **Dispositivi gestiti**  >  **Aggiornamenti di Office**: questa visualizzazione mostra lo stato complessivo degli aggiornamenti di Office nei dispositivi Microsoft Managed Desktop.

Inoltre, in diverse posizioni di Microsoft Endpoint Manager puoi filtrare i report di altri gruppi di prodotti per includere o escludere in modo specifico i dispositivi gestiti da Microsoft Managed Desktop. Questi report hanno integrato questa funzionalità di filtro:

- [Tutti i dispositivi](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Conformità dispositivo](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivi non conformi](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> I ruoli personalizzati di Microsoft Managed Desktop garantiscono l'accesso solo ai report di Microsoft Managed Desktop. Per accedere ad altre parti di Microsoft Endpoint Manager, ad esempio Tutti i **dispositivi,** vedere [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Report nell'interfaccia di amministrazione di Microsoft 365

Per trovare i report di Microsoft Managed Desktop Insights, aprire l'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)e quindi passare a **Report** e **selezionare Microsoft Managed Desktop.** Puoi anche seguire il collegamento diretto a questi report dalla scheda **Microsoft Managed Desktop** nella home page di Microsoft Endpoint [Manager.](https://endpoint.microsoft.com) 

Questi report includono: 

- [Informazioni dettagliate](usage-insights.md) sull'utilizzo: questa visualizzazione fornisce metriche di utilizzo per i dispositivi Microsoft Managed Desktop.
- [Informazioni dettagliate](reliability-insights.md) sull'affidabilità: questa visualizzazione fornisce un riepilogo dell'integrità dei dispositivi gestiti.
- [Informazioni dettagliate](battery-insights.md) sulla batteria: questa visualizzazione mostra informazioni sul consumo di energia delle app e sulla durata della batteria proiettata per i dispositivi nell'ambiente.
- [Informazioni dettagliate sugli aggiornamenti della](security-update-insights.md) sicurezza di Windows: questa visualizzazione mostra informazioni sullo stato degli aggiornamenti della sicurezza per i dispositivi Microsoft Managed Desktop.

 ## <a name="inventory-data"></a>Dati di inventario

Oltre agli altri report, è possibile esportare informazioni sui dispositivi gestiti da Microsoft Managed Desktop. Nella visualizzazione **Dispositivi** dell'area **Dispositivi** di Microsoft Endpoint Manager, usa **la** scheda Esporta tutto per scaricare un report inventario [dettagliato.](device-inventory-report.md)