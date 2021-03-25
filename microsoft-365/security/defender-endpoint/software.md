---
title: Proprietà e metodi software
description: Recupera gli avvisi recenti principali.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187200"
---
# <a name="software-resource-type"></a>Tipo di risorsa software

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metodi

Metodo |Tipo restituito |Descrizione
:---|:---|:---
[Software elenco](get-software.md) | Raccolta software | Elencare l'inventario software dell'organizzazione.
[Ottenere il software in base all'ID](get-software-by-id.md) | Software | Ottenere un software specifico in base al relativo ID software.
[List software version distribution](get-software-ver-distribution.md)| Raccolta di distribuzione | Elencare la distribuzione delle versioni software in base all'ID software.
[Elencare i computer in base al software](get-machines-by-software.md)| Insieme MachineRef | Recupera un elenco di dispositivi associati all'ID software.
[Elencare le vulnerabilità in base al software](get-vuln-by-software.md) | [Raccolta di vulnerabilità](vulnerability.md) | Recuperare un elenco di vulnerabilità associate all'ID software.
[Ottenere gli indicatori KPI mancanti](get-missing-kbs-software.md) | Raccolta KB | Ottenere un elenco di indicatori KPI mancanti associati all'ID software

## <a name="properties"></a>Proprietà

Proprietà |   Tipo   |   Descrizione
:---|:---|:---
id | Stringa | Software ID
Nome | Stringa | Nome software
Fornitore | Stringa | Nome fornitore software
Punti deboli | Long | Numero di vulnerabilità individuate
publicExploit | Booleano | Esiste un exploit pubblico per alcune delle vulnerabilità
activeAlert | Booleano | L'avviso attivo è associato a questo software
exposedMachines | Long | Numero di dispositivi esposti
impactScore | Double | Impatto del punteggio di esposizione di questo software
