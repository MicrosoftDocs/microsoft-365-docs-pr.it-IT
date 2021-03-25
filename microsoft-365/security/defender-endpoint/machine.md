---
title: Tipo di risorsa computer
description: Informazioni sui metodi e le proprietà del tipo di risorsa Computer in Microsoft Defender per Endpoint.
keywords: api, api supportate, get, computer
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
ms.technology: mde
ms.openlocfilehash: f96cfd56cb8d61bc62c34e2b1ee08d6313c6a8ad
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186642"
---
# <a name="machine-resource-type"></a>Tipo di risorsa computer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metodi

Metodo|Tipo restituito |Descrizione
:---|:---|:---
[Elencare i computer](get-machines.md) | [raccolta computer](machine.md) | Elencare il set [di](machine.md) entità computer nell'organizzazione.
[Ottenere il computer](get-machine-by-id.md) | [computer](machine.md) | Ottenere un [computer in](machine.md) base all'identità.
[Ottenere utenti connessi](get-machine-log-on-users.md) | [raccolta](user.md) utenti | Ottenere il set di [utenti](user.md) che hanno eseguito l'accesso al [computer](machine.md).
[Ottenere avvisi correlati](get-machine-related-alerts.md) | [raccolta avvisi](alerts.md) | Ottenere il set di [entità](alerts.md) di avviso generate nel [computer](machine.md).
[Ottenere il software installato](get-installed-software.md) | [raccolta software](software.md) | Recupera una raccolta di software installato correlato a un DETERMINATO ID computer.
[Individuare le vulnerabilità](get-discovered-vulnerabilities.md) | [raccolta di vulnerabilità](vulnerability.md) | Recupera una raccolta di vulnerabilità individuate correlate a un DETERMINATO ID computer.
[Ottenere suggerimenti sulla sicurezza](get-security-recommendations.md) | [raccolta suggerimenti](recommendation.md) | Recupera una raccolta di suggerimenti per la sicurezza correlati a un DETERMINATO ID computer.
[Aggiungere o rimuovere tag computer](add-or-remove-machine-tags.md) | [computer](machine.md) | Aggiungere o rimuovere tag a un computer specifico.
[Trovare i computer in base all'IP](find-machines-by-ip.md) | [raccolta computer](machine.md) | Trovare i computer visti con IP.
[Trovare i computer in base al tag](find-machines-by-tag.md) | [raccolta computer](machine.md) | Trova i computer per [Tag](machine-tags.md).
[Ottenere gli indicatori KPI mancanti](get-missing-kbs-machine.md) | Raccolta KB | Ottenere un elenco di indicatori KPI mancanti associati all'ID computer
[Impostare il valore del dispositivo](set-device-value.md)| [raccolta computer](machine.md) | Imposta il [valore di un dispositivo](tvm-assign-device-value.md).

## <a name="properties"></a>Proprietà

Proprietà |   Tipo   |   Descrizione
:---|:---|:---
id | Stringa | [identità del](machine.md) computer.
computerDnsName | Stringa | [nome](machine.md) completo del computer.
firstSeen | DateTimeOffset | Prima data e ora in cui [il computer è](machine.md) stato osservato da Microsoft Defender per Endpoint.
lastSeen | DateTimeOffset |Ora e data dell'ultimo rapporto sul dispositivo completo ricevuto. Un dispositivo in genere invia un report completo ogni 24 ore.
osPlatform | Stringa | Piattaforma del sistema operativo.
osProcessor | Stringa | Processore del sistema operativo.
Versione | Stringa | Versione del sistema operativo.
osBuild | Nullable long | Numero di build del sistema operativo.
lastIpAddress | Stringa | Last IP on local NIC on the [machine](machine.md).
lastExternalIpAddress | Stringa | Ultimo IP tramite il quale [il computer ha](machine.md) eseguito l'accesso a Internet.
healthStatus | Enum | [stato di](machine.md) integrità del computer. I valori possibili sono: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" e "Unknown". 
rbacGroupName | Stringa | Nome gruppo di computer.
riskScore | Enumerazione Nullable | Punteggio di rischio valutato da Microsoft Defender per Endpoint. I valori possibili sono: 'None', 'Informational', 'Low', 'Medium' e 'High'.
exposureScore | Enumerazione Nullable | [Punteggio di esposizione](tvm-exposure-score.md) valutato da Microsoft Defender for Endpoint. I valori possibili sono: 'None', 'Low', 'Medium' e 'High'.
aadDeviceId | Guid rappresentazione nullable | ID dispositivo AAD (quando [il computer è](machine.md) aggiunto ad AAD).
machineTags | Insieme String | Set di [tag del](machine.md) computer.
exposureLevel | Enumerazione Nullable | Livello di esposizione valutato da Microsoft Defender for Endpoint. I valori possibili sono: 'None', 'Low', 'Medium' e 'High'.
deviceValue | Enumerazione Nullable | Valore [del dispositivo](tvm-assign-device-value.md). I valori possibili sono: 'Normal', 'Low' e 'High'.
ipAddresses | Insieme IpAddress | Set di ***oggetti IpAddress.*** Vedi [Ottenere l'API per i computer](get-machines.md).


