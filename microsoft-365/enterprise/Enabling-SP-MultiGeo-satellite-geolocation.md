---
title: Abilitazione di SharePoint Multi-Geo in una posizione geografica satellite
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Questo articolo fornisce informazioni agli amministratori globali o SharePoint sull'abilitazione SharePoint Multi-Geo nelle posizioni geografiche satellite.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691524"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>Abilitazione di SharePoint Multi-Geo in una posizione geografica satellite

Questo articolo è diretto agli amministratori globali o di SharePoint che hanno creato una posizione satellite Multi-Geo **prima** che la funzionalità di SharePoint diventasse disponibile il 27 marzo 2019 e che non hanno abilitato SharePoint Multi-Geo nella posizione o nelle posizioni satellite. 

>[!Note]
>Se è stata aggiunta una nuova posizione geografica **dopo il 27 marzo**, non è necessario seguire queste istruzioni, poiché la nuova posizione sarà stata già attivata per Multi-Geo di OneDrive e SharePoint.

Queste istruzioni consentono di abilitare SharePoint nella posizione satellite, per consentire agli utenti di Multi-Geo di usufruire della funzionalità di OneDrive e SharePoint in O365. 

>[!IMPORTANT]
>Si tenga presente che si tratta di un processo non reversibile in modo autonomo. Dopo aver impostato la modalità SPO, non sarà più possibile ripristinare il tenant in modalità Multi-Geo solo per OneDrive senza richiedere assistenza. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>Impostare una posizione geografica in modalità SPO

Per impostare una posizione geografica in modalità SPO, connettersi alla posizione geografica scelta:

1.    Aprire SharePoint Online Management Shell. 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com"-Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    Questa operazione in genere richiede circa un'ora. Durante questo intervallo di tempo eseguiamo alcune operazioni in background nel servizio e nel tenant. Dopo circa 1 ora, eseguire il comando Get-SPOMultiGeoExperience.  Servirà per visualizzare se la posizione geografica è in modalità di SharePoint Online.</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>Alcune cache del servizio eseguono aggiornamenti ogni 24 ore, quindi è possibile durante questo periodo di 24 ore che la posizione geografica satellite occasionalmente si comporti come se fosse ancora in modalità ODB. Questo non causa problemi tecnici. 
 
Per ulteriori informazioni su SharePoint Multi-Geo visitare [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


