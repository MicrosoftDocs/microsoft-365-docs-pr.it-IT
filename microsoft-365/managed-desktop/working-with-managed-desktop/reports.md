---
title: Usare i report
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921351"
---
# <a name="work-with-reports"></a>Usare i report

Microsoft Managed Desktop fornisce diversi report e dashboard che gli amministratori IT dell'organizzazione possono usare per comprendere vari aspetti della popolazione di dispositivi.I report sono disponibili in due posizioni: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) e nell'interfaccia di amministrazione di Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Report in Microsoft Endpoint Manager

La console di Microsoft Endpoint Manager riunisce i report di diversi prodotti in un'unica posizione per aiutarti a monitorare e analizzare i problemi relativi alla configurazione e ai dispositivi dell'organizzazione Azure AD ("tenant"). Microsoft Managed Desktop include  una sezione in Report nel menu principale in cui è possibile trovare report specifici per la gestione dei dispositivi registrati da Microsoft Managed Desktop.

Questi report includono:
- **Dispositivi gestiti**  >  **Aggiornamenti delle** funzionalità: questa visualizzazione mostra lo stato generale degli aggiornamenti delle funzionalità nei dispositivi Microsoft Managed Desktop.
- **Dispositivi gestiti**  >  **Aggiornamenti di Office:** questa visualizzazione mostra lo stato complessivo degli aggiornamenti di Office nei dispositivi Microsoft Managed Desktop.

Inoltre, in diverse posizioni di Microsoft Endpoint Manager puoi filtrare i report di altri gruppi di prodotti per includere o escludere in modo specifico i dispositivi gestiti da Microsoft Managed Desktop. Questi report hanno integrato questa funzionalità di filtro:

- [Tutti i dispositivi](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Conformità dispositivo](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivi non conformi](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> I ruoli personalizzati di Microsoft Managed Desktop garantiscono l'accesso solo ai report di Microsoft Managed Desktop. Per accedere ad altre parti di Microsoft Endpoint Manager, ad esempio **Tutti** i dispositivi, vedere Controllo dell'accesso basato [sui ruoli con Microsoft Intune.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Report nell'interfaccia di amministrazione di Microsoft 365

È possibile trovare i report di Microsoft Managed Desktop Insights aprendo l'interfaccia di amministrazione di [Microsoft 365,](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)quindi passando a **Report** e selezionando **Microsoft Managed Desktop.** Puoi anche seguire il collegamento diretto a questi report dalla scheda **Microsoft Managed Desktop** nella home page di Microsoft Endpoint [Manager.](https://endpoint.microsoft.com) 

Questi report includono: 

- [Dati di utilizzo:](usage-insights.md) questa visualizzazione fornisce metriche di utilizzo per i dispositivi Microsoft Managed Desktop.
- [Informazioni dettagliate](reliability-insights.md) sull'affidabilità: questa visualizzazione fornisce un riepilogo dell'integrità dei dispositivi gestiti.
- [Informazioni dettagliate](battery-insights.md) sulla batteria: questa visualizzazione mostra informazioni sul consumo di energia delle app e sulla durata della batteria proiettata per i dispositivi nel tuo ambiente.
- [Informazioni dettagliate sugli aggiornamenti della](security-update-insights.md) sicurezza di Windows: questa visualizzazione mostra informazioni sullo stato degli aggiornamenti della sicurezza per i dispositivi Microsoft Managed Desktop.

 ## <a name="inventory-data"></a>Dati di inventario

Oltre agli altri report, è possibile esportare informazioni sui dispositivi gestiti da Microsoft Managed Desktop. Nella visualizzazione **Dispositivi** dell'area **Dispositivi** di Microsoft  Endpoint Manager, usa la scheda Esporta tutto per [scaricare un report inventario dettagliato.](device-inventory-report.md)
