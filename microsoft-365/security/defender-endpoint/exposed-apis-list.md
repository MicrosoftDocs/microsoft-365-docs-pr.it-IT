---
title: Accedere a API di Microsoft Defender per endpoint
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
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073830"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Accedere a API di Microsoft Defender per endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>URI endpoint e controllo delle versioni

### <a name="endpoint-uri"></a>Endpoint URI

> L'URI di base del servizio è: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> I dati OData basati su query hanno il prefisso '/api'. Ad esempio, per ottenere avvisi è possibile inviare la richiesta GET a [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Controllo delle versioni

> L'API supporta il controllo delle versioni.
>
> La versione corrente è **V1.0.**
>
> Per utilizzare una versione specifica, utilizzare il formato seguente: `https://api.securitycenter.microsoft.com/api/{Version}` . Ad esempio: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Se non si specifica alcuna versione (ad esempio ) si otterrà `https://api.securitycenter.microsoft.com/api/alerts` la versione più recente.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Altre informazioni sulle singole entità supportate in cui puoi eseguire chiamate API e dettagli come i valori delle richieste HTTP, le intestazioni delle richieste e le risposte previste.

## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
:---|:---
[Rilevazione avanzata](run-advanced-query-api.md) | Eseguire query dall'API.
[Metodi e proprietà di avviso](alerts.md) | Esegui chiamate API come \- ottenere avvisi, creare avvisi, aggiornare avvisi e altro ancora.
[Metodi e proprietà dell'indagine automatizzata](investigation.md) | Esegui chiamate API, ad \- esempio ottieni raccolta di indagini.
[Ottenere avvisi correlati al dominio](get-domain-related-alerts.md) | Esegui chiamate API come \- ottenere dispositivi correlati al dominio, statistiche del dominio e altro ancora.
[Metodi e proprietà di file](files.md) | Esegui chiamate API come ottenere informazioni sui file, avvisi correlati ai file, dispositivi correlati \- ai file e statistiche sui file.
[Metodi e proprietà degli indicatori](ti-indicator.md) | Eseguire una chiamata API, ad \- esempio ottenere indicatori, creare indicatori ed eliminare indicatori.
[Ottenere avvisi correlati agli IP](get-ip-related-alerts.md) | Eseguire chiamate API, ad esempio \- ottenere avvisi relativi all'IP e ottenere statistiche IP.
[Metodi e proprietà dei computer](machine.md) | Esegui chiamate API come ottenere dispositivi, ottenere dispositivi in base all'ID, informazioni sugli utenti \- connessi, modificare tag e altro ancora.
[Metodi e proprietà di azioni dei computer](machineaction.md) | Esegui chiamata API come \- Isolamento, Esegui analisi antivirus e altro ancora.
[Metodi e proprietà di consiglio](recommendation.md) | Eseguire chiamate API, ad esempio \- ottenere consigli in base all'ID.
[Metodi e proprietà di punteggio](score.md) | Esegui chiamate API come \- ottenere il punteggio di esposizione o ottenere il punteggio di sicurezza del dispositivo.
[Metodi e proprietà di software](software.md) | Esegui chiamate API, ad esempio \- le vulnerabilità dell'elenco da parte del software.
[Metodi utente](user.md) | Esegui chiamate API come \- ottenere avvisi correlati all'utente e dispositivi correlati all'utente.
[Metodi e proprietà di vulnerabilità](vulnerability.md) | Eseguire chiamate API, ad esempio \- elencare i dispositivi per vulnerabilità.

## <a name="see-also"></a>Vedere anche

- [API di Microsoft Defender per endpoint](apis-intro.md)

- [Note sulla versione di Microsoft Defender for Endpoint API](api-release-notes.md)
