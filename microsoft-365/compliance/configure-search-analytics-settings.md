---
title: Configurare le impostazioni di ricerca e analisi-indagini sui dati
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come configurare le impostazioni di ricerca e analisi, come quasi duplicati, Threading di posta elettronica e temi durante la gestione delle indagini sui dati.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3100c83fc027e793f7937a4d27e059ce7e3038a0
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527352"
---
# <a name="configure-search-and-analytics-settings"></a>Configurare le impostazioni di ricerca e analisi

## <a name="near-duplicates-and-email-threading"></a>Quasi duplicati e threading della posta elettronica

In questa sezione, è possibile impostare parametri per il rilevamento duplicati, vicino al rilevamento duplicati e al threading tramite posta elettronica.

- Attiva/disattiva: Includi rilevamento duplicato, vicino al rilevamento duplicato e threading della posta elettronica come parte del flusso di analisi se abilitato. Poiché si basano sull'uno dall'altro, è necessario abilitarli o disabilitarli tutti.

- Soglia: se il livello di somiglianza di due documenti si trova al di sopra della soglia, verranno inseriti nello stesso set di duplicati vicino.

- Nascondi i duplicati per impostazione predefinita: se questa impostazione è attivata, per impostazione predefinita verrà applicato un filtro per nascondere i documenti duplicati nel working set. Il filtro può essere rimosso manualmente nel working set, se necessario.

- Numero minimo/massimo di parole: quasi duplicati e il threading della posta elettronica verrà eseguito solo sui documenti che hanno almeno il numero minimo di parole e il numero massimo di parole.

Per ulteriori informazioni, vedere [near duplicate detection](near-duplicates.md) and [email Threading](email-threading.md).

## <a name="themes"></a>Temi

In questa sezione, è possibile impostare parametri per i temi.

- Abilita/Disabilita: Includi temi il clustering come parte del flusso di analisi se abilitato.

- Regola dinamicamente il numero massimo di temi: in alcuni casi, non sono disponibili documenti sufficienti per produrre il numero di temi desiderato. Se questa impostazione è attivata, anziché tentare di forzare il numero massimo di temi desiderato, il sistema regola in modo dinamico il numero massimo di temi.

- Numero massimo di temi: numero desiderato di temi.

- Includere numeri nei temi: quando è abilitata, includerà i numeri durante la generazione di temi.  

## <a name="optical-character-recognition-ocr"></a>Riconoscimento ottico caratteri (OCR)

Quando questa impostazione è attivata, l'OCR verrà eseguito su immagini che vengono ingerite in gruppi di lavoro in modo che possano essere ricercate.

## <a name="ignore-text"></a>Ignora testo

Esistono casi in cui alcuni testi diminuiscono la qualità dell'analisi, ad esempio le dichiarazioni di non responsabilità lunghe che vengono aggiunte a determinati messaggi di posta elettronica, indipendentemente dal contenuto del messaggio. Se si è a conoscenza di tali casi, è possibile escludere questo testo da analisi specificando il testo (RegEx è supportato) e quali moduli devono essere esclusi per il testo.
