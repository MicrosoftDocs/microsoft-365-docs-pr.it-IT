---
title: Microsoft 365 API degli incidenti di Defender e tipo di risorsa incidente
description: Informazioni sui metodi e le proprietà del tipo di risorsa Incidente in Microsoft 365 Defender
keywords: incidente, incidenti, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572586"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 API degli incidenti di Defender e tipo di risorsa incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

Un [incidente](incidents-overview.md) è una raccolta di avvisi correlati che aiutano a descrivere un attacco. Gli eventi di entità diverse nell'organizzazione vengono aggregati automaticamente Microsoft 365 Defender. È possibile utilizzare l'API degli incidenti per accedere programmaticamente agli incidenti e agli avvisi correlati dell'organizzazione.

## <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora. Ogni metodo ha anche le proprie quote. Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.

Un `429` codice di risposta HTTP indica che hai raggiunto una quota, in base al numero di richieste inviate o al tempo di esecuzione assegnato. Il corpo di risposta includerà il tempo fino a quando la quota raggiunta non verrà reimpostata.

## <a name="permissions"></a>Autorizzazioni

L'API degli incidenti richiede diversi tipi di autorizzazioni per ciascuno dei relativi metodi. Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo del rispettivo metodo.

## <a name="methods"></a>Metodi

Metodo | Tipo restituito | Descrizione
-|-|-
[Elencare incidenti](api-list-incidents.md) | [Elenco](api-incident.md) incidenti | Ottieni un elenco di incidenti.
[Aggiornare incidente](api-update-incidents.md) | [Incidente](api-incident.md) | Aggiornare un incidente specifico.

## <a name="request-body-response-and-examples"></a>Corpo della richiesta, risposta ed esempi

Fare riferimento ai rispettivi articoli del metodo per ulteriori dettagli su come costruire una richiesta o analizzare una risposta e per esempi pratici.

## <a name="common-properties"></a>Proprietà comuni

Proprietà | Tipo | Descrizione
-|-|-
id incidente | long | ID univoco incidente.
redirectIncidentId | nullable lungo | ID incidente a cui è stato unito l'incidente corrente.
incidentName | stringa | Nome dell'incidente.
tempo creato | DateTimeOffset | Data e ora (in UTC) in cui è stato creato l'incidente.
lastUpdateTime | DateTimeOffset | Data e ora (in UTC) dell'ultimo aggiornamento dell'incidente.
assegnatoA | stringa | Proprietario dell'incidente.
severità | Enum | Gravità dell'incidente. I valori possibili sono: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .
stato | Enum | Specifica lo stato corrente dell'incidente. I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .
classificazione | Enum | Specifica dell'incidente. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'incidente. I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tag | elenco di stringhe | Elenco di tag Incidente.
Commenti | Elenco dei commenti sugli incidenti | L'oggetto Incident Comment contiene: stringa di commento, stringa createdBy e ora di data createTime.
Avvisi | Elenco avvisi | Elenco degli avvisi correlati. Vedere esempi nella [documentazione dell'API degli](api-list-incidents.md) incidenti elenco.

## <a name="related-articles"></a>Articoli correlati

- [Microsoft 365 Panoramica delle API defender](api-overview.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [API elenco incidenti](api-list-incidents.md)
- [Aggiornare l'API degli incidenti](api-update-incidents.md)
