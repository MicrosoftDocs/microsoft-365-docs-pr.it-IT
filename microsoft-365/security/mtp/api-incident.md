---
title: API per gli eventi imprevisti di Microsoft 365 Defender e tipo di risorsa evento imprevisto
description: Informazioni sui metodi e le proprietà del tipo di risorsa Evento imprevisto in Microsoft 365 Defender
keywords: evento imprevisto, eventi imprevisti, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928355"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API per gli eventi imprevisti di Microsoft 365 Defender e tipo di risorsa evento imprevisto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Un [evento](incidents-overview.md) imprevisto è una raccolta di avvisi correlati che consentono di descrivere un attacco. Gli eventi di entità diverse nell'organizzazione vengono aggregati automaticamente da Microsoft 365 Defender. Puoi usare l'API per gli eventi imprevisti per accedere a livello di codice agli eventi imprevisti e agli avvisi correlati dell'organizzazione.

## <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

È possibile richiedere fino a 50 chiamate al minuto o 1500 chiamate all'ora. Ogni metodo dispone inoltre di quote proprie. Per ulteriori informazioni sulle quote specifiche del metodo, vedere il rispettivo articolo relativo al metodo che si desidera utilizzare.

Un codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo `429` di esecuzione assegnato. Il corpo della risposta includerà il tempo fino al ripristino della quota raggiunta.

## <a name="permissions"></a>Autorizzazioni

L'API degli eventi imprevisti richiede diversi tipi di autorizzazioni per ognuno dei relativi metodi. Per ulteriori informazioni sulle autorizzazioni necessarie, vedere l'articolo relativo al rispettivo metodo.

## <a name="methods"></a>Metodi

Metodo | Tipo restituito | Descrizione
-|-|-
[Elencare incidenti](api-list-incidents.md) | [Elenco operazioni non](api-incident.md) consentite | Ottenere un elenco di eventi imprevisti.
[Aggiornare incidente](api-update-incidents.md) | [Evento imprevisto](api-incident.md) | Aggiornare un evento imprevisto specifico.

## <a name="request-body-response-and-examples"></a>Corpo della richiesta, risposta ed esempi

Fare riferimento ai rispettivi articoli relativi al metodo per ulteriori dettagli su come creare una richiesta o analizzare una risposta e per esempi pratici.

## <a name="common-properties"></a>Proprietà comuni

Proprietà | Tipo | Descrizione
-|-|-
incidentId | long | ID univoco dell'evento imprevisto.
redirectIncidentId | nullable long | ID evento imprevisto a cui è stato unito l'evento imprevisto corrente.
incidentName | stringa | Nome dell'evento imprevisto.
createdTime | DateTimeOffset | Data e ora (in FORMATO UTC) in cui è stato creato l'evento imprevisto.
lastUpdateTime | DateTimeOffset | Data e ora (in FORMATO UTC) dell'ultimo aggiornamento dell'evento imprevisto.
assignedTo | stringa | Proprietario dell'evento imprevisto.
gravità | Enumerazione | Gravità dell'incidente. I valori possibili sono: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enumerazione | Specifica lo stato corrente dell'evento imprevisto. I valori possibili sono: ```Active``` , ```Resolved``` , e ```Redirected``` .
classificazione | Enumerazione | Specifica dell'incidente. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enumerazione | Specifica la determinazione dell'incidente. I valori possibili sono: ```NotAvailable``` , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
tag | string List | Elenco di tag Evento imprevisto.
avvisi | Elenco avvisi | Elenco di avvisi correlati. Vedi esempi nella [documentazione dell'API per gli eventi imprevisti](api-list-incidents.md) dell'elenco.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [API per gli eventi imprevisti dell'elenco](api-list-incidents.md)
- [API per gli eventi imprevisti di aggiornamento](api-update-incidents.md)
