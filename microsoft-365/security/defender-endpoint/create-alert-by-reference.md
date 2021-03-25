---
title: Creare un avviso dall'API dell'evento
description: Scopri come usare l'API Crea avviso per creare un nuovo avviso sopra Evento in Microsoft Defender per endpoint.
keywords: api, api del grafico, api supportate, ottenere, avviso, informazioni, id
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
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167069"
---
# <a name="create-alert-api"></a>API per la creazione di avvisi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrizione API
Crea un [nuovo avviso](alerts.md) sopra **l'evento**.
<br>**Microsoft Defender for Endpoint Event** è necessario per la creazione dell'avviso.
<br>Dovrai fornire 3 parametri dall'evento nella richiesta: **Event Time,** **Machine ID** e **Report ID.** Vedere l'esempio che segue.
<br>Puoi usare un evento disponibile in Advanced Hunting API o Portal.
<br>Se nello stesso dispositivo è presente un avviso aperto con lo stesso titolo, il nuovo avviso creato verrà unito ad esso.
<br>Un'indagine automatica viene avviata automaticamente sugli avvisi creati tramite l'API.


## <a name="limitations"></a>Limitazioni
1. I limiti di frequenza per questa API sono 15 chiamate al minuto.


## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato autorizzazione
:---|:---|:---
Applicazione |   Alerts.ReadWrite.All |  "Lettura e scrittura di tutti gli avvisi"
Delegato (account aziendale o dell'istituto di istruzione) | Alert.ReadWrite | "Avvisi di lettura e scrittura"

>[!Note]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Analisi degli avvisi" (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)
>- L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)

## <a name="http-request"></a>Richiesta HTTP

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Bearer {token}. **Obbligatorio**.
Content-Type | Stringa | application/json. **Obbligatorio**.

## <a name="request-body"></a>Corpo della richiesta

Nel corpo della richiesta specificare i valori seguenti (sono necessari tutti):

Proprietà | Tipo | Descrizione
:---|:---|:---
eventTime | DateTime(UTC) | Ora precisa dell'evento come stringa, ottenuta dalla ricerca avanzata. Ad esempio, ```2018-08-03T16:45:21.7115183Z``` **Obbligatorio**.
reportId | Stringa | ReportId dell'evento, ottenuto dalla ricerca avanzata. **Obbligatorio**.
machineId | Stringa | ID del dispositivo in cui è stato identificato l'evento. **Obbligatorio**.
gravità | Stringa | Gravità dell'avviso. I valori della proprietà sono: 'Low', 'Medium' e 'High'. **Obbligatorio**.
title | Stringa | Titolo dell'avviso. **Obbligatorio**.
descrizione | Stringa | Descrizione dell'avviso. **Obbligatorio**.
recommendedAction| Stringa | Azione consigliata da parte del responsabile della sicurezza durante l'analisi dell'avviso. **Obbligatorio**.
category| Stringa | Categoria dell'avviso. I valori delle proprietà sono: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Risposta

Se ha esito positivo, questo metodo restituisce 200 OK e un nuovo oggetto [avviso](alerts.md) nel corpo della risposta. Se l'evento con le proprietà specificate (_reportId_, _eventTime_ e _machineId_) non è stato trovato - 404 Not Found.

## <a name="example"></a>Esempio

**Richiesta**

Ecco un esempio della richiesta.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
