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
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585329"
---
# <a name="work-with-reports"></a>Usare i report

Microsoft Managed Desktop fornisce diversi rapporti e dashboard che gli amministratori IT dell'organizzazione possono utilizzare per comprendere vari aspetti della popolazione dei dispositivi.I report sono disponibili in due posizioni: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) e nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporti in Microsoft Endpoint Manager

Microsoft Endpoint Manager Console riunisce i report provenienti da diversi prodotti in un'unica posizione per facilitare il monitoraggio e l'analisi dei problemi relativi alla configurazione e ai dispositivi di Azure AD Organization ("tenant"). Microsoft Managed Desktop contiene una sezione di **report** nel menu principale, in cui è possibile trovare report specifici per la gestione dei dispositivi che sono stati registrati da Microsoft Managed Desktop.

Inoltre, in diverse posizioni in Microsoft Endpoint Manager è possibile filtrare i report da altri gruppi di prodotti per includere o escludere in modo specifico i dispositivi gestiti da Microsoft Managed Desktop. Questi rapporti hanno integrato questa funzionalità di filtro:

- **Tutti i dispositivi**
- **Conformità dispositivo**
- **Dispositivi non conformi**

> [!NOTE]
> I ruoli personalizzati di Microsoft Managed Desktop garantiscono l'accesso solo ai report di Microsoft Managed Desktop. Per accedere ad altre parti di Microsoft Endpoint Manager, ad esempio **tutti i dispositivi**, vedere [Role-Based Access Control with Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Rapporti nell'interfaccia di amministrazione di Microsoft 365

È possibile trovare i report Microsoft Managed Desktop Insights aprendo l'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop), quindi passando a **report** e selezionando **Microsoft Managed Desktop**. È inoltre possibile seguire il collegamento diretto a questi rapporti dalla scheda **Microsoft Managed Desktop** nella Home page di [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

Questi rapporti includono: 

- [Insights Usage](usage-insights.md) -questa visualizzazione fornisce metriche di utilizzo per i dispositivi Microsoft Managed Desktop.
- [Insights sull'affidabilità](reliability-insights.md) -questa visualizzazione fornisce un riepilogo di integrità dei dispositivi gestiti.
- [Battery Insights](battery-insights.md) -questa visualizzazione Mostra informazioni sul consumo di energia delle app e sulla durata della batteria proiettata per i dispositivi nell'ambiente in uso.
- [Insights](security-update-insights.md) per l'aggiornamento della sicurezza di Windows-questa visualizzazione Mostra informazioni sullo stato degli aggiornamenti della sicurezza per i dispositivi Microsoft Managed Desktop.

 ## <a name="inventory-data"></a>Dati di inventario

Oltre agli altri report, è possibile esportare le informazioni sui dispositivi gestiti da Microsoft Managed Desktop. Nella visualizzazione **dispositivi** dell'area **dispositivi** di Microsoft Endpoint Manager, utilizzare la scheda **Esporta tutto** per [scaricare un report dettagliato sull'inventario](device-inventory-report.md).