---
title: Microsoft 365 Defender Incidents APIs e il tipo di risorsa Incident
description: Informazioni sui metodi e le proprietà del tipo di risorsa Incident in Microsoft 365 Defender
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719335"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API Microsoft 365 Defender Incidents e il tipo di risorsa Incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Un [evento imprevisto](incidents-overview.md) è un insieme di avvisi correlati che consentono di descrivere un attacco. Gli eventi provenienti da entità diverse nell'organizzazione vengono aggregati automaticamente da Microsoft 365 Defender. È possibile utilizzare l'API Incidents per programatically accedere agli eventi imprevisti dell'organizzazione e ai relativi avvisi.

## <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora. Ogni metodo dispone anche di quote proprie. Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.

Un `429` codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo di esecuzione assegnato. Il corpo di risposta includerà l'ora in cui la quota raggiunta verrà reimpostata.

## <a name="permissions"></a>Autorizzazioni

L'API Incidents richiede diversi tipi di autorizzazioni per ognuno dei relativi metodi. Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo relativo al metodo.

## <a name="methods"></a>Metodi

Metodo | Tipo restituito | Descrizione
-|-|-
[Elencare incidenti](api-list-incidents.md) | Elenco [eventi](api-incident.md) non consentiti | Ottenere un elenco di eventi non consentiti.
[Aggiornare incidente](api-update-incidents.md) | [Operazioni non consentite](api-incident.md) | Aggiornare un evento specifico.

## <a name="request-body-response-and-examples"></a>Corpo della richiesta, risposta ed esempi

Per ulteriori informazioni su come creare una richiesta o analizzare una risposta e per esempi pratici, vedere gli articoli relativi ai rispettivi metodi.

## <a name="common-properties"></a>Proprietà comuni

Proprietà | Tipo | Descrizione
-|-|-
incidentId | long | ID univoco per gli incidenti.
redirectIncidentId | Long Nullable | ID di incidente in cui è stato unito l'evento Incident corrente.
evento incidentname | stringa | Nome dell'evento Incident.
createdTime | DateTimeOffset | La data e l'ora (in formato UTC) dell'evento Incident è stato creato.
lastUpdateTime | DateTimeOffset | La data e l'ora (in formato UTC) dell'ultimo aggiornamento dell'evento.
AssegnatoA | stringa | Proprietario dell'evento Incident.
gravità | Enum | Gravità dell'evento Incident. I valori possibili sono:,,, ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` e ```High``` .
stato | Enum | Specifica lo stato corrente dell'evento Incident. I valori possibili sono: ```Active``` , ```Resolved``` e ```Redirected``` .
classificazione | Enum | Specifica dell'evento Incident. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'evento Incident. I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tag | Elenco di stringhe | Elenco dei tag Incident.
avvisi | Elenco avvisi | Elenco di avvisi correlati. Vedere esempi di documentazione sull'API degli [incidenti di elenco](api-list-incidents.md) .

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [API degli incidenti di elenco](api-list-incidents.md)
- [Aggiornare l'API Incident](api-update-incidents.md)
