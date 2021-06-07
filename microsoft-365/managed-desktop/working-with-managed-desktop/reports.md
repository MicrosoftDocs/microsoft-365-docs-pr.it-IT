---
title: Usare i report
description: I vari report disponibili in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771886"
---
# <a name="work-with-reports"></a>Usare i report

Microsoft Managed Desktop fornisce diversi report e dashboard che gli amministratori IT dell'organizzazione possono usare per comprendere diversi aspetti della popolazione di dispositivi. 

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

## <a name="endpoint-analytics"></a>Endpoint analytics
Microsoft Managed Desktop è ora integrato con [Endpoint Analytics.](/mem/analytics/overview) Questi report offrono informazioni dettagliate per la misurazione del funzionamento dell'organizzazione e della qualità dell'esperienza consegnata agli utenti. Endpoint Analytics è disponibile nel menu **Report** di [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Per eseguire il pivot di un punteggio per includere solo i  dispositivi gestiti da Microsoft Managed Desktop passare a qualsiasi report, selezionare l'elenco a discesa Filtro e quindi selezionare Microsoft Managed Desktop **dispositivi**.

Se Endpoint Analytics non è stato configurato automaticamente per l'organizzazione di Azure AD ("tenant") durante la registrazione, è possibile farlo manualmente. Per altre informazioni, vedi [Onboard nel portale di endpoint analytics.](/mem/analytics/enroll-intune#bkmk_onboard) Puoi registrare tutti i dispositivi o, se vuoi includere solo  i dispositivi Microsoft Managed Desktop, seleziona i gruppi moderni di dispositivi aziendali per Test, First, Fast e Broad. Questi report potrebbero richiedere autorizzazioni diverse. Per ulteriori informazioni, vedere [Autorizzazioni per](/mem/analytics/overview#permissions) assicurarsi che i ruoli siano assegnati in modo appropriato.

> [!NOTE]
> Per rispettare meglio la privacy degli utenti, devono essere presenti più di 10 Microsoft Managed Desktop registrati con Endpoint Analytics per usare questo filtro.

 ## <a name="inventory-data"></a>Dati di inventario

Oltre agli altri report, puoi esportare informazioni sui dispositivi gestiti da Microsoft Managed Desktop. Nella visualizzazione **Dispositivi** dell'area **Dispositivi** di Microsoft Endpoint Manager,  usa la scheda Esporta tutto per [scaricare un report inventario dettagliato.](device-inventory-report.md)
