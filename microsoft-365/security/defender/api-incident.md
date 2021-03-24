---
title: API per eventi imprevisti di Microsoft 365 Defender e tipo di risorsa evento imprevisto
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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060818"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API eventi imprevisti di Microsoft 365 Defender e tipo di risorsa evento imprevisto

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
avvisi | Elenco avvisi | Elenco di avvisi correlati. Vedi gli esempi nella [documentazione dell'API list incidents.](api-list-incidents.md)

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [API elenca eventi imprevisti](api-list-incidents.md)
- [API per gli eventi imprevisti di aggiornamento](api-update-incidents.md)
