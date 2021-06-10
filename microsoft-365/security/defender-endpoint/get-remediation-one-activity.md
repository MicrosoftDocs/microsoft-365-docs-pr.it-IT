---
title: Ottenere un'attività di correzione in base all'ID
description: Restituisce informazioni per l'attività di correzione specificata.
keywords: api, correzione, api di correzione, ottenere, attività di correzione, correzione per ID,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772150"
---
# <a name="get-one-remediation-activity-by-id"></a>Ottenere un'attività di correzione in base all'ID

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrizione API

Restituisce informazioni per l'attività di correzione specificata. Presenta le stesse colonne di [Get all remediation activity](get-remediation-all-activities.md), ma restituisce i risultati solo per l'attività di correzione _specificata._

[Ulteriori informazioni sulle attività di correzione.](tvm-remediation.md)

## <a name="list-a-specified-remediation-activity-for-id"></a>Elencare un'attività di correzione specificata per (id)

**URL:** GET: /api/remediationTasks/ \{ id\}

## <a name="permissions"></a>Autorizzazioni

Per chiamare questa API è necessaria una delle autorizzazioni seguenti. Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)

Tipo di autorizzazione | Autorizzazione | Nome visualizzato autorizzazione
:---|:---|:---
Applicazione | RemediationTask.Read.All | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'
Delegato (account aziendale o dell'istituto di istruzione) | RemediationTask.Read.Read | \'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'

## <a name="properties"></a>Proprietà

Proprietà (id) | Tipo di dati | Descrizione | Esempio di valore restituito
:---|:---|:---|:---
category | Stringa | Categoria dell'attività di correzione (configurazione software/sicurezza) | Software
completerEmail | Stringa | Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene il messaggio di posta elettronica | null
completerId | Stringa | Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene l'ID oggetto | null
completionMethod | Stringa | Un'attività di correzione può essere completata "automaticamente" (se tutti i dispositivi sono patchati) o "manualmente" da una persona che seleziona "contrassegna come completata" | Automatica
createdOn | DateTime | Ora in cui è stata creata questa attività di correzione | 2021-01-12T18:54:11.5499478Z
descrizione | Stringa | Descrizione di questa attività di correzione | Aggiornare Microsoft Silverlight a una versione successiva per ridurre le vulnerabilità note che interessano i dispositivi.
dueOn | DateTime | Data di scadenza impostata dal creatore per questa attività di correzione | 2021-01-13T00:00:00Z
fixedDevices |  | Il numero di dispositivi che sono stati corretti | 2
id | Stringa | ID di questa attività di correzione | 097d9735-5479-4899-b1b7-77398899df92
nameId | Stringa | Nome prodotto correlato | Microsoft Silverlight
priority | Stringa | Priorità impostata dal creatore per questa attività di correzione (High\Medium\Low) | Fortemente
productId | Stringa | ID prodotto correlato | microsoft-_-silverlight
productivityImpactRemediationType | Stringa | Alcune modifiche alla configurazione potrebbero essere richieste solo per i dispositivi senza alcun impatto sull'utente. Questo valore indica la selezione tra "tutti i dispositivi esposti" o "solo i dispositivi senza impatto sull'utente". | AllExposedAssets
rbacGroupNames | Stringa | Nomi dei gruppi di dispositivi correlati | [ "Windows Servers", "Windows 10" ]
recommendedProgram | Stringa | Programma consigliato a cui eseguire l'aggiornamento | null
recommendedVendor | Stringa | Fornitore consigliato a cui eseguire l'aggiornamento | null
recommendedVersion | Stringa | Versione consigliata per l'aggiornamento/aggiornamento | null
relatedComponent | Stringa | Componente correlato di questa attività di correzione (simile al componente correlato per una raccomandazione sulla sicurezza) | Microsoft Microsoft Silverlight
requesterEmail | Stringa | Indirizzo di posta elettronica creatore | globaladmin@UserName.contoso.com
requesterId | Stringa | ID oggetto creatore | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | Stringa | Note (testo libero) aggiunte dall'autore per questa attività di correzione | null
scid | Stringa | SCID della raccomandazione relativa alla sicurezza | null
status | Stringa | Stato attività di correzione (Attivo/Completato) | Attivazione
statusLastModifiedOn | DateTime | Data in cui il campo stato è stato aggiornato | 2021-01-12T18:54:11.5499487Z
targetDevices | Long | Numero di dispositivi esposti a cui è applicabile questa correzione | 43
title | Stringa | Titolo di questa attività di correzione | Microsoft Silverlight
type | Stringa | Tipo di correzione | Update
vendorId | Stringa | Nome fornitore correlato | Microsoft

## <a name="example"></a>Esempio

### <a name="request-example"></a>Esempio di richiesta

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>Esempio di risposta

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a>Vedere anche

- [Metodi e proprietà di correzione](get-remediation-methods-properties.md)

- [Elencare tutte le attività correttive](get-remediation-all-activities.md)

- [Elencare i dispositivi esposti a un'attività correttiva](get-remediation-exposed-devices-activities.md)

- [Rischio basato sulle minacce & gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
