---
title: Aggiornare l'API degli incidenti
description: Informazioni su come aggiornare gli eventi non consentiti tramite Microsoft 365 Defender API
keywords: Update, API, Incident
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
ms.openlocfilehash: 3f77980863b0c232166d736a6b557444df98c8ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844837"
---
# <a name="update-incidents-api"></a>Aggiornare l'API degli incidenti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Descrizione API
Aggiorna le proprietà dell'evento Incident esistente.
<br>Le proprietà aggiornabili sono: ```status``` ,, ```determination``` ```classification``` ```assignedTo``` e ```tags``` .


## <a name="limitations"></a>Limitazioni
1. Le limitazioni delle tariffe per questa API sono 50 chiamate al minuto e 1500 chiamate all'ora.
2. È possibile impostare ```determination``` solo se la classificazione è impostata su TruePositive.


## <a name="permissions"></a>Autorizzazioni
Per chiamare l'API è necessaria una delle autorizzazioni seguenti. Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Apis](api-access.md).

Tipo di autorizzazione |   Autorizzazione  |   Nome visualizzato per le autorizzazioni
:---|:---|:---
Applicazione |   Incident. ReadWrite. All |    ' Leggi e Scrivi tutti gli incidenti '
Delegati (account aziendale o dell'Istituto di istruzione) | Incident. ReadWrite | ' Operazioni di lettura e scrittura degli incidenti '

>[!NOTE]
> Quando si ottiene un token utilizzando le credenziali utente:
>- L'utente deve disporre dell'autorizzazione necessaria per aggiornare l'evento Incident nel portale.


## <a name="http-request"></a>Richiesta HTTP

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Intestazioni di richiesta

Name | Tipo | Descrizione
:---|:---|:---
Autorizzazione | Stringa | Portatore {token}. **Obbligatorio**.
Content-Type | Stringa | applicazione/JSON. **Obbligatorio**.


## <a name="request-body"></a>Corpo della richiesta
Nel corpo della richiesta fornire i valori per i campi rilevanti che devono essere aggiornati.
<br>Le proprietà esistenti che non sono incluse nel corpo della richiesta manterranno i valori precedenti o verranno ricalcolate in base alle modifiche apportate ad altri valori di proprietà. 
<br>Per prestazioni ottimali, non è necessario includere i valori esistenti che non sono cambiati.

Proprietà | Tipo | Descrizione
:---|:---|:---
stato | Enum | Specifica lo stato corrente dell'avviso. I valori possibili sono ```Active``` : ```Resolved``` e ```Redirected``` .
AssegnatoA | stringa | Proprietario dell'evento Incident.
classificazione | Enum | Specifica dell'avviso. I valori possibili sono: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
determinazione | Enum | Specifica la determinazione dell'avviso. I valori possibili sono:,,,,,, ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` .
Tag | Elenco di stringhe | Elenco dei tag Incident.



## <a name="response"></a>Risposta
Se l'operazione ha esito positivo, questo metodo restituisce 200 OK e l'entità Incident nel corpo della risposta con le proprietà aggiornate. Se non è stato trovato un problema con l'ID specificato-404 non è stato trovato.


## <a name="example"></a>Esempio

**Richiesta**

Di seguito è riportato un esempio della richiesta.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>Argomento correlato
- [Incidenti delle API](api-incident.md)
- [Elencare incidenti](api-list-incidents.md)
