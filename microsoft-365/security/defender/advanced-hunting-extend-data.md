---
title: Estendere la copertura di ricerca avanzata con le impostazioni giuste
description: Controllare le impostazioni di controllo Windows dispositivi e altre impostazioni per assicurarsi di ottenere i dati più completi nella ricerca avanzata
keywords: ricerca avanzata, incidente, pivot, entità, impostazioni di controllo, gestione degli account utente, gestione dei gruppi di sicurezza, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f4b1399b77583e95b109575a9577d8b1af89e6ad
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952669"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estendere la copertura di ricerca avanzata con le impostazioni giuste

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender
- Microsoft Defender per endpoint

[La ricerca](advanced-hunting-overview.md) avanzata si basa sui dati provenienti da varie origini, inclusi i dispositivi, le Office 365 di lavoro, Azure AD e Microsoft Defender for Identity. Per ottenere i dati più completi possibili, verificare di disporre delle impostazioni corrette nelle origini dati corrispondenti.

## <a name="advanced-security-auditing-on-windows-devices"></a>Controllo di sicurezza avanzato nei Windows mobili
Attiva queste impostazioni di controllo avanzate per assicurarti di ottenere dati sulle attività nei dispositivi, tra cui la gestione degli account locali, la gestione dei gruppi di sicurezza locali e la creazione dei servizi.

| Dati | Descrizione | Tabella schema | Configurazione |
| --- | --- | --- | --- |
| Gestione account | Eventi acquisiti come vari valori che indicano la creazione, l'eliminazione e altre attività `ActionType` relative all'account locale | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla gestione account utente](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Gestione dei gruppi di sicurezza | Eventi acquisiti come vari `ActionType` valori che indicano la creazione di gruppi di sicurezza locali e altre attività di gestione dei gruppi locali | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla Gestione gruppi di sicurezza](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Installazione del servizio | Eventi acquisiti con `ActionType` il valore , che indicano che è stato creato un `ServiceInstalled` servizio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla estensione del sistema di sicurezza](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Sensore Microsoft Defender for Identity nel controller di dominio
Se si esegue Active Directory in locale, è necessario installare il sensore Microsoft Defender for Identity nel controller di dominio per ottenere i dati per Microsoft Defender for Identity. Se installati e configurati correttamente, questi dati forniscono anche la ricerca avanzata tramite Microsoft Defender for Identity e forniscono un quadro più olistico delle informazioni sull'identità e degli eventi nella rete. Questi dati migliorano anche la capacità di Microsoft Defender per l'identità di generare avvisi pertinenti che sono coperti anche dalla ricerca avanzata. 

| Dati | Descrizione | Tabella schema | Configurazione |
| --- | --- | --- | --- |
| Controller di dominio | Dati da Active Directory locale inviati a Microsoft Defender per l'identità, arricchendo le informazioni relative all'identità, ad esempio i dettagli dell'account, l'attività di accesso e le query di Active Directory | Più tabelle, tra [cui IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installare il sensore Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step4)<br>- [Attivare eventi Windows pertinenti](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>Alcune tabelle di questo articolo potrebbero non essere disponibili in Microsoft Defender per Endpoint. [Attivare Microsoft 365 Defender per](m365d-enable.md) cercare minacce che usano più origini dati. Puoi spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender per Endpoint a Microsoft 365 Defender seguendo la procedura descritta in Eseguire la migrazione di query di ricerca avanzate da [Microsoft Defender per Endpoint.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)