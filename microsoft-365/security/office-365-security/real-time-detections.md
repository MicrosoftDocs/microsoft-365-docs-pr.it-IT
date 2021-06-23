---
title: Informazioni di base su Esplora minacce e rilevamento in tempo reale in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Usa Explorer o i rilevamenti in tempo reale per analizzare e rispondere alle minacce in modo efficiente.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083189"
---
# <a name="explorer-and-real-time-detections-basics"></a>Nozioni di base su Esplora risorse e rilevamento in tempo reale

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Contenuto dell'articolo:

- [Differenze tra Esplora risorse e rilevamenti in tempo reale](#differences-between-explorer-and-real-time-detections)
- [Licenze e autorizzazioni obbligatorie](#required-licenses-and-permissions)

> [!NOTE]
> Questo articolo fa parte di una serie di **3** articoli su Explorer (noto anche come **Threat Explorer),** sicurezza della posta elettronica e informazioni di base su **Esplora** risorse e rilevamenti in tempo reale (ad esempio differenze tra gli strumenti e autorizzazioni necessarie per operare). Gli altri due articoli di questa serie sono Ricerca delle [minacce in Esplora](threat-hunting-in-threat-explorer.md) risorse e Sicurezza della posta elettronica con Esplora [risorse.](email-security-in-microsoft-defender.md)

In questo articolo viene illustrata la differenza tra Explorer e la segnalazione dei rilevamenti in tempo reale e le licenze e le autorizzazioni necessarie.

Se l'organizzazione dispone di [Microsoft Defender per Office 365](defender-for-office-365.md)e si dispone delle autorizzazioni ,  è possibile utilizzare **Esplora** risorse (noto anche come **Esplora** minacce) o rilevamenti in tempo reale per rilevare e correggere le minacce. [](#required-licenses-and-permissions)

Nel portale Microsoft 365 Defender ( ), passare a Posta elettronica & collaborazione e quindi scegliere Esplora risorse o <https://security.microsoft.com>   **Rilevamenti in tempo reale**. 

Con questi strumenti è possibile:

- Vedi malware rilevato dalle Microsoft 365 sicurezza.
- Visualizzare l'URL di phishing e fare clic su Dati verdetto.
- Avvia un processo di indagine e risposta automatizzato da una visualizzazione in Esplora risorse.
- Analizzare la posta elettronica dannosa e altro ancora.

Per altre informazioni, vedi [Sicurezza della posta elettronica con Explorer.](email-security-in-microsoft-defender.md)

## <a name="differences-between-explorer-and-real-time-detections"></a>Differenze tra Esplora risorse e rilevamenti in tempo reale

- *I rilevamenti in tempo reale* sono uno strumento di reporting disponibile in Defender per Office 365 Piano 1. *Threat Explorer* è uno strumento di ricerca e correzione delle minacce disponibile in Defender per Office 365 Piano 2.
- Il report Rilevamenti in tempo reale consente di visualizzare i rilevamenti in tempo reale. Threat Explorer esegue anche questa operazione, ma fornisce ulteriori dettagli per un determinato attacco, ad esempio l'evidenziazione delle campagne di attacco, e offre ai team delle operazioni di sicurezza la possibilità di correggere le minacce (inclusa l'attivazione di un'indagine automatizzata e un'indagine di [risposta).](automated-investigation-response-office.md)
- Una *visualizzazione Tutti i* messaggi di posta elettronica è disponibile in Esplora minacce, ma non è inclusa nel report Rilevamenti in tempo reale.
- Le funzionalità di filtro avanzate e le azioni di correzione sono incluse in Esplora minacce. Per altre informazioni, vedi [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

Devi disporre di [Microsoft Defender per Office 365](defender-for-office-365.md) usare uno dei rilevamenti di Explorer o in tempo reale:

- Explorer è incluso solo in Defender per Office 365 Piano 2.
- Il report rilevamenti in tempo reale è incluso in Defender per Office 365 piano 1.

I team delle operazioni di sicurezza devono assegnare licenze a tutti gli utenti che devono essere protetti da Defender per Office 365 e tenere presente che i rilevamenti di Esplora risorse e in tempo reale mostrano i dati di rilevamento per gli utenti con licenza.

Per visualizzare e usare Esplora *risorse o* rilevamenti in tempo reale, sono necessarie le autorizzazioni seguenti:

- In Defender per Office 365:
  - Gestione dell'organizzazione
  - Amministratore della sicurezza (può essere assegnato nell'Azure Active Directory di amministrazione ( <https://aad.portal.azure.com> )
  - Ruolo con autorizzazioni di lettura per la sicurezza
- In Exchange Online:
  - Gestione organizzazione
  - Gestione organizzazione sola visualizzazione
  - Destinatari solo visualizzazione
  - Gestione della conformità

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere gli articoli seguenti:

- [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
- [Autorizzazioni in Exchange Online](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>Ulteriori informazioni

- [Threat Explorer raccoglie i dettagli della posta elettronica nella pagina dell'entità di posta elettronica](mdo-email-entity-page.md)
- [Identificare e analizzare i messaggi di posta elettronica dannosi recapitati](investigate-malicious-email-that-was-delivered.md)
- [Visualizzare i file dannosi rilevati in SharePoint Online, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
- [Indagine e reazione automatizzate in Microsoft Threat Protection](automated-investigation-response-office.md)
