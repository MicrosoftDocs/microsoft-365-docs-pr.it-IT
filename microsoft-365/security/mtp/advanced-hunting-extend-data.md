---
title: Estendere la copertura di ricerca avanzata con le impostazioni corrette
description: Controllare le impostazioni di controllo nei dispositivi Windows e altre impostazioni per garantire la massima completezza dei dati in Advanced Hunting
keywords: caccia avanzata, incidenti, pivot, entità, impostazioni di controllo, gestione degli account utente, gestione dei gruppi di sicurezza, caccia alle minacce, caccia alla minaccia cibernetica, ricerca, query, telemetria, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 82faff2599cd61fa1a4deb3129e1e6780d3f529c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842477"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estendere la copertura di ricerca avanzata con le impostazioni corrette

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La [ricerca avanzata](advanced-hunting-overview.md) si basa su dati provenienti da diverse fonti, tra cui i dispositivi, le aree di lavoro di Office 365, Azure ad e Microsoft Defender per Identity. Per ottenere i dati più completi possibili, verificare di disporre delle impostazioni corrette nelle origini dati corrispondenti.

## <a name="advanced-security-auditing-on-windows-devices"></a>Controllo di sicurezza avanzato nei dispositivi Windows
Abilitare le impostazioni di controllo avanzate per ottenere i dati relativi alle attività nei dispositivi, tra cui la gestione degli account locali, la gestione dei gruppi di sicurezza locali e la creazione di servizi.

| Dati | Descrizione | Tabella schema | Configurazione |
| --- | --- | --- | --- |
| Gestione account | Eventi acquisiti come vari `ActionType` valori che indicano la creazione, l'eliminazione e altre attività relative agli account locali | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuire un criterio di controllo di sicurezza avanzato: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Gestione dei gruppi di sicurezza | Eventi acquisiti come vari `ActionType` valori che indicano la creazione di gruppi di sicurezza locali e altre attività di gestione di gruppi locali | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuire un criterio di controllo di sicurezza avanzato: [gestione del gruppo di sicurezza di controllo](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Installazione del servizio | Eventi acquisiti con il `ActionType` valore `ServiceInstalled` che indica che è stato creato un servizio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Distribuire un criterio di controllo di sicurezza avanzato: [estensione del sistema di sicurezza di controllo](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender per il sensore di identità nel controller di dominio
Se si sta eseguendo Active Directory in locale, è necessario installare Microsoft Defender per il sensore di identità nel controller di dominio per ottenere i dati per Microsoft Defender per Identity. Dopo aver installato e configurato correttamente, questi dati vengono alimentati anche in una ricerca avanzata tramite Microsoft Defender per Identity e fornisce un'immagine più olistica delle informazioni sull'identità e degli eventi nella rete. Questi dati migliorano anche la capacità di Microsoft Defender per Identity di generare avvisi rilevanti che sono coperti anche dalla ricerca avanzata. 

| Dati | Descrizione | Tabella schema | Configurazione |
| --- | --- | --- | --- |
| Controller di dominio | Dati provenienti da Active Directory locale inviati a Microsoft Defender per l'identità, arricchendo le informazioni relative all'identità, ad esempio dettagli account, attività di accesso e query di Active Directory | Più tabelle, tra cui [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Installare Microsoft Defender per il sensore di identità](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Attiva gli eventi di Windows rilevanti](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
