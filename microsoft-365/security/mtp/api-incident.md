---
title: Tipo di risorsa Incident nell'API di Microsoft Threat Protection
description: Informazioni sui metodi e le proprietà del tipo di risorsa Incident in Microsoft Threat Protection
keywords: eventi incidentati, incidenti, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201304"
---
# <a name="incident-resource-type"></a>Tipo di risorsa Incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>Metodi

Metodo |Tipo restituito |Descrizione
:---|:---|:---
[Elencare incidenti](api-list-incidents.md) | Elenco [eventi](api-incident.md) non consentiti | Ottenere un elenco di eventi non consentiti.
[Aggiornare incidente](api-update-incidents.md) | [Operazioni non consentite](api-incident.md) | Update specific Incident.


## <a name="properties"></a>Proprietà

Proprietà |    Tipo    |    Descrizione
:---|:---|:---
incidentId | long | ID univoco per gli incidenti.
redirectIncidentId | Long Nullable | ID di incidente in cui è stato unito l'evento Incident corrente.
evento incidentname | stringa | Nome dell'evento Incident.
createdTime | DateTimeOffset | La data e l'ora (in formato UTC) dell'evento Incident è stato creato.
lastUpdateTime | DateTimeOffset | La data e l'ora (in formato UTC) dell'ultimo aggiornamento dell'evento.
AssegnatoA | stringa | Proprietario dell'evento Incident.
gravità | Enum | Gravità dell'evento Incident. I valori possibili sono: ```UnSpecified``` ,, ```Informational``` ```Low``` ```Medium``` e ```High``` .
stato | Enum | Specifica lo stato corrente dell'evento Incident. I valori possibili sono ```Active``` : ```Resolved``` e ```Redirected``` .
classificazione | Enum | Specifica dell'evento Incident. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'evento Incident. I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tag | Elenco di stringhe | Elenco dei tag Incident.
avvisi | Elenco avvisi | Elenco di avvisi correlati. Vedere esempi di documentazione sull'API degli [incidenti di elenco](api-list-incidents.md) .
