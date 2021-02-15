---
title: Estendere la copertura di ricerca avanzata con le impostazioni giuste
description: Controllare le impostazioni di controllo nei dispositivi Windows e altre impostazioni per assicurarsi di ottenere i dati più completi nella ricerca avanzata
keywords: ricerca avanzata, incidente, pivot, entità, impostazioni di controllo, gestione degli account utente, gestione dei gruppi di sicurezza, ricerca delle minacce informatiche, ricerca, ricerca, query, telemetria, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929587"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estendere la copertura di ricerca avanzata con le impostazioni giuste

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[La ricerca avanzata](advanced-hunting-overview.md) si basa sui dati provenienti da varie origini, tra cui i dispositivi, le aree di lavoro di Office 365, Azure AD e Microsoft Defender for Identity. Per ottenere i dati più completi possibili, verificare di disporre delle impostazioni corrette nelle origini dati corrispondenti.

## <a name="advanced-security-auditing-on-windows-devices"></a>Controllo di sicurezza avanzato nei dispositivi Windows
Attiva queste impostazioni di controllo avanzate per assicurarti di ottenere dati sulle attività nei dispositivi, tra cui la gestione degli account locali, la gestione dei gruppi di sicurezza locali e la creazione di servizi.

| Dati | Descrizione | Tabella schema | Configurazione |
| --- | --- | --- | --- |
| Gestione account | Eventi acquisiti come vari valori che indicano la creazione, l'eliminazione e altre attività `ActionType` relative all'account locale | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla gestione account utente](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Gestione dei gruppi di sicurezza | Eventi acquisiti come vari valori che indicano la creazione di gruppi di sicurezza locali `ActionType` e altre attività di gestione dei gruppi locali | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla Gestione gruppi di sicurezza](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Installazione del servizio | Eventi acquisiti con il `ActionType` valore , che indicano che è stato creato un `ServiceInstalled` servizio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [controlla l'estensione del sistema di sicurezza](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Sensore Microsoft Defender for Identity nel controller di dominio
Se si esegue Active Directory in locale, è necessario installare il sensore Microsoft Defender for Identity nel controller di dominio per ottenere i dati per Microsoft Defender for Identity. Se installati e configurati correttamente, questi dati forniscono anche la ricerca avanzata tramite Microsoft Defender for Identity e forniscono un quadro più olistico delle informazioni sull'identità e degli eventi nella rete. Questi dati migliorano anche la capacità di Microsoft Defender for Identity di generare avvisi pertinenti che sono coperti anche dalla ricerca avanzata. 

| Dati | Descrizione | Tabella schema | Configurazione |
| --- | --- | --- | --- |
| Controller di dominio | Dati da Active Directory locale inviati a Microsoft Defender per l'identità, che arricchiscono le informazioni relative all'identità, ad esempio i dettagli dell'account, l'attività di accesso e le query di Active Directory | Più tabelle, tra [cui IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installare il sensore Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Attivare gli eventi di Windows pertinenti](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
