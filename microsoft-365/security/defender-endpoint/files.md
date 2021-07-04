---
title: Tipo di risorsa file
description: Recuperare gli avvisi recenti di Microsoft Defender for Endpoint relativi ai file.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 83a011e649a7289f62acd6a8d985f020b27b1e10
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290016"
---
# <a name="file-resource-type"></a>Tipo di risorsa file

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Rappresenta un'entità file in Defender for Endpoint.

## <a name="methods"></a>Metodi

Metodo|Tipo restituito |Descrizione
:---|:---|:---
[Ottenere il file](get-file-information.md) | [file](files.md) | Ottenere un singolo file 
[Avvisi correlati ai file di elenco](get-file-related-alerts.md) | [raccolta avvisi](alerts.md) | Ottenere [le entità](alerts.md) di avviso associate al file.
[Elencare i computer correlati ai file](get-file-related-machines.md) | [raccolta computer](machine.md) | Ottenere le [entità](machine.md) computer associate all'avviso.
[statistiche file](get-file-statistics.md) | Riepilogo statistiche | Recupera la diffusione per il file specificato.


## <a name="properties"></a>Proprietà

|Proprietà | Tipo | Descrizione |
|:---|:---|:---|
|sha1 | Stringa | Hash Sha1 del contenuto del file |
|sha256 | Stringa | Hash Sha256 del contenuto del file |
|globalPrevalence | Nullable long | Diffusione dei file nell'organizzazione |
|globalFirstObserved | DateTimeOffset | Prima osservazione del file |
|globalLastObserved | DateTimeOffset | Data e ora dell'ultima osservazione del file |
|size | Nullable long | Dimensioni del file |
|fileType | Stringa | Tipo di file |
|isPeFile | Booleano | true se il file è eseguibile portabile ,ad esempio "DLL", "EXE" e così via. |
|filePublisher | Stringa | Autore file |
|fileProductName | Stringa | Nome del prodotto |
|firmatario | Stringa | Firmatario file |
|autorità emittente | Stringa | Autorità emittente file |
|signerHash | Stringa | Hash del certificato di firma |
|isValidCertificate | Booleano | La firma del certificato è stata verificata correttamente da Microsoft Defender per l'agente endpoint |
|determinationType | Stringa | Tipo di determinazione del file |
|determinationValue | Stringa | Valore di determinazione |

## <a name="json-representation"></a>Rappresentazione Json

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
