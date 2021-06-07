---
title: Metodi e proprietà di software
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771406"
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
[Elencare il software](get-software.md) | Raccolta software | Elencare l'inventario software dell'organizzazione.
[Ottenere il software per Id](get-software-by-id.md) | Software | Ottenere un software specifico in base al relativo ID software.
[Elencare distribuzione versione software](get-software-ver-distribution.md)| Raccolta di distribuzione | Elencare la distribuzione delle versioni software in base all'ID software.
[Elencare i computer per software](get-machines-by-software.md)| Insieme MachineRef | Recupera un elenco di dispositivi associati all'ID software.
[Elencare le vulnerabilità per software](get-vuln-by-software.md) | [Raccolta di vulnerabilità](vulnerability.md) | Recuperare un elenco di vulnerabilità associate all'ID software.
[Recuperare i KB mancanti](get-missing-kbs-software.md) | Raccolta KB | Ottenere un elenco di indicatori KPI mancanti associati all'ID software

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
