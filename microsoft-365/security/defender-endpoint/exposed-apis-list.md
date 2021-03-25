---
title: API di Microsoft Defender per endpoint supportate
ms.reviewer: ''
description: Informazioni sulle entità di Microsoft Defender for Endpoint supportate specifiche a cui puoi creare chiamate API.
keywords: api, api supportate, attore, avvisi, dispositivo, utente, dominio, ip, file, query avanzate, ricerca avanzata
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198324"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>API di Microsoft Defender per endpoint supportate

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>URI endpoint e controllo delle versioni

### <a name="endpoint-uri"></a>URI endpoint:

> L'URI di base del servizio è: https://api.securitycenter.microsoft.com
> 
> I dati OData basati su query hanno il prefisso '/api'. Ad esempio, per ottenere avvisi è possibile inviare la richiesta GET a https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>Controllo delle versioni:

> L'API supporta il controllo delle versioni.
> 
> La versione corrente è **V1.0.**
> 
> Per utilizzare una versione specifica, utilizzare il formato seguente: `https://api.securitycenter.microsoft.com/api/{Version}` . Ad esempio: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> Se non si specifica alcuna versione (ad esempio ) si otterrà https://api.securitycenter.microsoft.com/api/alerts la versione più recente.


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Altre informazioni sulle singole entità supportate in cui puoi eseguire chiamate API e dettagli come i valori delle richieste HTTP, le intestazioni delle richieste e le risposte previste.

## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
:---|:---
Ricerca avanzata | Eseguire query dall'API.
Avvisi | Esegui chiamate API come ottenere avvisi, creare avvisi, aggiornare avvisi e altro ancora.
Domini | Esegui chiamate API come ottenere dispositivi correlati al dominio, statistiche del dominio e altro ancora.
File | Esegui chiamate API come ottenere informazioni sui file, avvisi correlati ai file, dispositivi correlati ai file e statistiche sui file.
IP | Eseguire chiamate API, ad esempio ottenere avvisi relativi all'IP e ottenere statistiche IP.
Computer | Esegui chiamate API come ottenere dispositivi, ottenere dispositivi in base all'ID, informazioni sugli utenti connessi, modificare tag e altro ancora.
Azioni del computer | Esegui chiamata API come Isolamento, Esegui analisi antivirus e altro ancora.
Indicatori | Esegui una chiamata API, ad esempio crea indicatore, ottieni indicatori ed elimina indicatori.
Utenti | Esegui chiamate API come ottenere avvisi correlati all'utente e dispositivi correlati all'utente.
Punteggio | Esegui chiamate API come ottenere il punteggio di esposizione o ottenere il punteggio di sicurezza del dispositivo.
Software | Esegui chiamate API, ad esempio le vulnerabilità dell'elenco da parte del software.
Vulnerabilità | Eseguire chiamate API, ad esempio elencare i dispositivi per vulnerabilità.
Consiglio | Esegui chiamate API, ad esempio Ottieni suggerimenti in base all'ID.

## <a name="see-also"></a>Vedere anche
- [API di Microsoft Defender per endpoint](apis-intro.md)
