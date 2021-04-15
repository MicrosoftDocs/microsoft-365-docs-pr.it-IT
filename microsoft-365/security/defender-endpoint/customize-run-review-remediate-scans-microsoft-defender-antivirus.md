---
title: Eseguire e personalizzare analisi pianificate e su richiesta
description: Personalizzare e avviare le analisi di Microsoft Defender Antivirus sugli endpoint della rete.
keywords: analizzare, pianificare, personalizzare, esclusioni, escludere file, correzione, risultati dell'analisi, quarantena, rimuovere minacce, analisi rapida, analisi completa, Microsoft Defender Antivirus
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
ms.openlocfilehash: 115a8ee56ca5e9768b3aba11c37f8423ef31a67b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765696"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile utilizzare Criteri di gruppo, PowerShell e Strumentazione gestione Windows (WMI) per configurare le analisi di Microsoft Defender Antivirus. 

## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
---|---
[Configurare e convalidare le esclusioni di file, cartelle e file aperti dal processo nelle analisi di Microsoft Defender Antivirus](configure-exclusions-microsoft-defender-antivirus.md) | È possibile escludere file (inclusi file modificati da processi specificati) e cartelle da analisi su richiesta, analisi pianificate e monitoraggio e analisi della protezione in tempo reale sempre attiva
[Configurare le opzioni di analisi di Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Puoi configurare Microsoft Defender Antivirus per includere determinati tipi di file di archiviazione della posta elettronica, punti di backup o di analisi e file archiviati (ad esempio file ZIP) nelle analisi. È inoltre possibile abilitare l'analisi dei file di rete
[Configurare la correzione per le analisi](configure-remediation-microsoft-defender-antivirus.md) | Configurare l'operazione che Microsoft Defender Antivirus deve eseguire quando rileva una minaccia e per quanto tempo i file in quarantena devono essere conservati nella cartella di quarantena
[Configurare le analisi pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide
[Configurare ed eseguire analisi](run-scan-microsoft-defender-antivirus.md) | Eseguire e configurare analisi su richiesta tramite PowerShell, Strumentazione gestione Windows o singolarmente sugli endpoint con l'app Sicurezza di Windows
[Esaminare i risultati dell'analisi](review-scan-results-microsoft-defender-antivirus.md) | Esaminare i risultati delle analisi tramite Microsoft Endpoint Configuration Manager, Microsoft Intune o l'app Sicurezza di Windows