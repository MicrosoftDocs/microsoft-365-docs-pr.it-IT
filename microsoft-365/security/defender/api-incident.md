---
title: Microsoft 365 API per gli eventi imprevisti di Defender e il tipo di risorsa evento imprevisto
description: Informazioni sui metodi e le proprietà del tipo di risorsa Evento imprevisto in Microsoft 365 Defender
keywords: eventi imprevisti, eventi imprevisti, api
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
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 API eventi imprevisti defender e tipo di risorsa evento imprevisto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

Un [evento imprevisto](incidents-overview.md) è una raccolta di avvisi correlati che consentono di descrivere un attacco. Gli eventi di entità diverse nell'organizzazione vengono aggregati automaticamente da Microsoft 365 Defender. Puoi usare l'API eventi imprevisti per accedere a livello di programmazione agli eventi imprevisti e agli avvisi correlati dell'organizzazione.

## <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora. Ogni metodo ha anche le proprie quote. Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.

Un codice di risposta HTTP indica che hai raggiunto una quota, in base al numero di richieste inviate o al tempo `429` di esecuzione assegnato. Il corpo della risposta includerà il tempo fino a quando la quota raggiunta non verrà reimpostata.

## <a name="permissions"></a>Autorizzazioni

L'API eventi imprevisti richiede diversi tipi di autorizzazioni per ognuno dei relativi metodi. Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo relativo al rispettivo metodo.

## <a name="methods"></a>Metodi

Metodo | Tipo restituito | Descrizione
-|-|-
[Elencare incidenti](api-list-incidents.md) | [Elenco operazioni](api-incident.md) non consentite | Ottenere un elenco di eventi imprevisti.
[Aggiornare incidente](api-update-incidents.md) | [Incidente](api-incident.md) | Aggiornare un evento imprevisto specifico.

## <a name="request-body-response-and-examples"></a>Corpo, risposta ed esempi della richiesta

Per ulteriori dettagli su come creare una richiesta o analizzare una risposta, vedere gli articoli relativi ai rispettivi metodi e per esempi pratici.

## <a name="common-properties"></a>Proprietà comuni

Proprietà | Tipo | Descrizione
-|-|-
incidentId | long | ID univoco dell'evento imprevisto.
redirectIncidentId | nullable long | ID evento imprevisto a cui è stato unito l'evento imprevisto corrente.
incidentName | stringa | Nome dell'evento imprevisto.
createdTime | DateTimeOffset | Data e ora (in UTC) in cui è stato creato l'evento imprevisto.
lastUpdateTime | DateTimeOffset | Data e ora (in UTC) dell'ultimo aggiornamento dell'evento imprevisto.
assignedTo | stringa | Proprietario dell'evento imprevisto.
gravità | Enum | Gravità dell'evento imprevisto. I valori possibili sono: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Specifica lo stato corrente dell'evento imprevisto. I valori possibili sono: ```Active``` ```Resolved``` , e ```Redirected``` .
classificazione | Enum | Specifica dell'evento imprevisto. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'evento imprevisto. I valori possibili sono: ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
tag | string List | Elenco di tag Evento imprevisto.
commenti | Elenco dei commenti degli eventi imprevisti | L'oggetto Incident Comment contiene: stringa di commento, stringa createdBy e data/ora createTime.
avvisi | Elenco avvisi | Elenco di avvisi correlati. Vedi gli esempi nella [documentazione dell'API list incidents.](api-list-incidents.md)

## <a name="related-articles"></a>Articoli correlati

- [Microsoft 365 Panoramica delle API defender](api-overview.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [API elenca eventi imprevisti](api-list-incidents.md)
- [API per gli eventi imprevisti di aggiornamento](api-update-incidents.md)
