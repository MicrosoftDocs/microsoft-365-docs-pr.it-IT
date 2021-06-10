---
title: Abilitare e configurare le Antivirus Microsoft Defender di protezione dei dati
description: Abilitare la protezione basata sul comportamento, euristica e in tempo reale in Microsoft Defender AV.
keywords: euristica, machine learning, monitoraggio del comportamento, protezione in tempo reale, always-on, Antivirus Microsoft Defender, antimalware, sicurezza, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274609"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurare la protezione comportamentale, euristica e in tempo reale

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Antivirus Microsoft Defender diversi metodi per fornire la protezione dalle minacce:

- Protezione basata sul cloud per il rilevamento quasi immediato e il blocco di minacce nuove ed emergenti
- Analisi sempre attiva, con monitoraggio del comportamento di file e processi e altre euristiche (note anche come "protezione in tempo reale")
- Aggiornamenti dedicati alla protezione basati sul machine learning, sull'analisi di big data automatica o manuale e sulla ricerca approfondita delle minacce.

È possibile configurare il modo Antivirus Microsoft Defender questi metodi con Criteri di gruppo, gestione configurazione System Center, cmdlet di PowerShell e Strumentazione gestione Windows (WMI).

In questa sezione viene illustrata la configurazione per l'analisi sempre attiva, inclusa la modalità di rilevamento e blocco delle app ritenute non sicure, ma che potrebbero non essere rilevate come malware.

Vedi [Usare tecnologie di Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) di nuova generazione tramite la protezione basata sul cloud per informazioni su come abilitare e configurare Antivirus Microsoft Defender di protezione cloud.

## <a name="in-this-section"></a>Contenuto della sezione

 Argomento | Descrizione
---|---
[Rilevare e bloccare applicazioni potenzialmente indesiderate](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Rilevare e bloccare le app che potrebbero essere indesiderate nella rete, ad esempio adware, modificatori del browser e barre degli strumenti e app antivirus non autorizzate o contraffatte
[Abilitare e configurare le funzionalità Antivirus Microsoft Defender protezione dei dati](configure-real-time-protection-microsoft-defender-antivirus.md) | Abilitare e configurare la protezione in tempo reale, l'euristica e altre funzionalità di monitoraggio Antivirus Microsoft Defender always-on