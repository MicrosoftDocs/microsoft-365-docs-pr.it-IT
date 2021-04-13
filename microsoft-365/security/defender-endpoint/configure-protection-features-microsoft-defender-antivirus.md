---
title: Abilitare e configurare le funzionalità di protezione di Microsoft Defender Antivirus
description: Abilitare la protezione basata sul comportamento, euristica e in tempo reale in Microsoft Defender AV.
keywords: euristica, machine learning, monitoraggio del comportamento, protezione in tempo reale, always-on, Microsoft Defender Antivirus, antimalware, sicurezza, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7a0e0571445e8ec753c3813a81dbcca9c698e7df
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690331"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurare la protezione comportamentale, euristica e in tempo reale

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus usa diversi metodi per fornire la protezione dalle minacce:

- Protezione basata sul cloud per il rilevamento quasi immediato e il blocco di minacce nuove ed emergenti
- Analisi sempre attiva, con monitoraggio del comportamento di file e processi e altre euristiche (note anche come "protezione in tempo reale")
- Aggiornamenti dedicati alla protezione basati sul machine learning, sull'analisi di big data automatica o manuale e sulla ricerca approfondita delle minacce.

È possibile configurare il modo in cui Microsoft Defender Antivirus usa questi metodi con Criteri di gruppo, System Center Configuration Manage, cmdlet di PowerShell e Strumentazione gestione Windows (WMI).

In questa sezione viene illustrata la configurazione per l'analisi sempre attiva, inclusa la modalità di rilevamento e blocco delle app ritenute non sicure, ma che potrebbero non essere rilevate come malware.

Vedi [Usare tecnologie Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md) di nuova generazione tramite la protezione basata sul cloud per informazioni su come abilitare e configurare la protezione basata sul cloud di Microsoft Defender Antivirus.

## <a name="in-this-section"></a>Contenuto della sezione

 Argomento | Descrizione
---|---
[Rilevare e bloccare applicazioni potenzialmente indesiderate](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Rilevare e bloccare le app che potrebbero essere indesiderate nella rete, ad esempio adware, modificatori del browser e barre degli strumenti e app antivirus non autorizzate o contraffatte
[Abilitare e configurare le funzionalità di protezione di Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md) | Abilitare e configurare la protezione in tempo reale, l'euristica e altre funzionalità di monitoraggio di Microsoft Defender Antivirus sempre disponibili