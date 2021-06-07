---
title: Metodi e proprietà di punteggio
description: Recupera il punteggio di esposizione dell'organizzazione, il punteggio di sicurezza del dispositivo e il punteggio di esposizione per gruppo di dispositivi
keywords: api, api del grafico, api supportate, punteggio, punteggio di esposizione, punteggio sicuro del dispositivo, punteggio di esposizione per gruppo di dispositivi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771430"
---
# <a name="score-resource-type"></a>Tipo di risorsa punteggio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metodi

Metodo |Tipo restituito |Descrizione
:---|:---|:---
[Ottenere punteggio di esposizione](get-exposure-score.md) | [Punteggio](score.md) | Ottenere il punteggio di esposizione dell'organizzazione.
[Ottenere punteggio di sicurezza dei dispositivi](get-device-secure-score.md) | [Punteggio](score.md) | Ottenere il punteggio di sicurezza del dispositivo dell'organizzazione.
[Elencare il punteggio di esposizione per gruppo di dispositivi](get-machine-group-exposure-score.md)| [Punteggio](score.md) | Elencare i punteggi per gruppo di dispositivi.

## <a name="properties"></a>Proprietà

Proprietà |  Tipo    |   Descrizione
:---|:---|:---
Punteggio | Double | Punteggio corrente.
Ora | DateTime | Data e ora in cui è stata effettuata la chiamata per questa API.
RbacGroupName | Stringa | Nome del gruppo di dispositivi.
