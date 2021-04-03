---
title: Estendere la copertura di ricerca avanzata con le impostazioni giuste
description: Controlla le impostazioni di controllo nei dispositivi Windows e altre impostazioni per assicurarti di ottenere i dati più completi nella ricerca avanzata
keywords: ricerca avanzata, incidente, pivot, entità, impostazioni di controllo, gestione degli account utente, gestione dei gruppi di sicurezza, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500622"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estendere la copertura di ricerca avanzata con le impostazioni giuste

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[La ricerca avanzata](advanced-hunting-overview.md) si basa sui dati provenienti da tutta l'organizzazione. Per ottenere i dati più completi possibili, verificare di disporre delle impostazioni corrette nelle origini dati corrispondenti.

## <a name="advanced-security-auditing-on-windows-devices"></a>Controllo di sicurezza avanzato nei dispositivi Windows

Attiva queste impostazioni di controllo avanzate per assicurarti di ottenere dati sulle attività nei dispositivi, tra cui la gestione degli account locali, la gestione dei gruppi di sicurezza locali e la creazione dei servizi.

Dati | Descrizione | Tabella schema | Configurazione
-|-|-|-
Gestione account | Eventi acquisiti come vari valori che indicano la creazione, l'eliminazione e altre attività `ActionType` relative all'account locale | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla gestione account utente](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Gestione dei gruppi di sicurezza | Eventi acquisiti come vari `ActionType` valori che indicano la creazione di gruppi di sicurezza locali e altre attività di gestione dei gruppi locali | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla Gestione gruppi di sicurezza](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Installazione del servizio | Eventi acquisiti con `ActionType` il valore , che indicano che è stato creato un `ServiceInstalled` servizio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Distribuire un criterio di controllo di sicurezza avanzato: [Controlla estensione del sistema di sicurezza](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprendere lo schema](advanced-hunting-schema-reference.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
