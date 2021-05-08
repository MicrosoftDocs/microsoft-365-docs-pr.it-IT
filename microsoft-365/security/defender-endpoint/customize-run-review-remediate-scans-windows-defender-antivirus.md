---
title: Eseguire e personalizzare analisi pianificate e su richiesta
description: Personalizzare e avviare Antivirus Microsoft Defender di analisi sugli endpoint della rete.
keywords: analisi, pianificazione, personalizzazione, esclusioni, esclusione di file, correzione, risultati dell'analisi, quarantena, rimozione delle minacce, analisi rapida, analisi completa, Antivirus Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3e0cc7ffccf02e24b9746d539a44d3a72810ead
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286186"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>Personalizzare, avviare ed esaminare i risultati di Antivirus Microsoft Defender analisi & correzione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile utilizzare Criteri di gruppo, PowerShell e Strumentazione gestione Windows (WMI) per configurare Antivirus Microsoft Defender analisi. 

## <a name="in-this-section"></a>Contenuto della sezione

| Articolo | Descrizione |
|:---|:---|
|[Configurare e convalidare le esclusioni di file, cartelle e file aperti Antivirus Microsoft Defender processi](configure-exclusions-microsoft-defender-antivirus.md) | È possibile escludere file (inclusi file modificati da processi specificati) e cartelle da analisi su richiesta, analisi pianificate e monitoraggio e analisi della protezione in tempo reale sempre attiva |
|[Configurare le opzioni di analisi di Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) | È possibile configurare Antivirus Microsoft Defender per includere determinati tipi di file di archiviazione della posta elettronica, punti di backup o di analisi e file archiviati (ad esempio file .zip) nelle analisi. È inoltre possibile abilitare l'analisi dei file di rete |
|[Configurare la correzione per le analisi](configure-remediation-microsoft-defender-antivirus.md) | Configurare le Antivirus Microsoft Defender quando rileva una minaccia e per quanto tempo i file in quarantena devono essere conservati nella cartella di quarantena |
|[Configurare le analisi pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide |
|[Configurare ed eseguire analisi](run-scan-microsoft-defender-antivirus.md) | Eseguire e configurare analisi su richiesta tramite PowerShell, Windows Management Instrumentation o singolarmente sugli endpoint con l'app Sicurezza di Windows |
|[Esaminare i risultati dell'analisi](review-scan-results-microsoft-defender-antivirus.md) | Esaminare i risultati delle analisi usando Microsoft Endpoint Configuration Manager, Microsoft Intune o l Sicurezza di Windows app |