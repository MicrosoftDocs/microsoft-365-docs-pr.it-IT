---
title: Metodi e proprietà delle attività correttive
description: La risposta API contiene le & gestione delle vulnerabilità di correzione create nel tenant. Puoi richiedere tutte le attività di correzione, una sola attività di correzione o informazioni sui dispositivi esposti per un'attività di correzione selezionata.
keywords: api, correzione, api di correzione, ottenere, attività di correzione, metodi di correzione, proprietà di correzione,
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
ms.openlocfilehash: 67009961ecc3755b5af21b2e773bc817ea46bec0
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769235"
---
# <a name="remediation-activity-methods-and-properties"></a>Metodi e proprietà delle attività correttive

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

La risposta API contiene [le & gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)di correzione delle minacce create   nel tenant.  

## <a name="methods"></a>Metodi

Metodo | Tipo di dati | Descrizione
:---|:---|:---
[Elencare tutte le attività correttive](get-remediation-all-activities.md) | Raccolta di indagini | Restituisce informazioni su tutte le attività di correzione.
[Elencare i dispositivi esposti a un'attività correttiva](get-remediation-exposed-devices-activities.md) | Entità di indagine | Restituisce informazioni sui dispositivi esposti per l'attività di correzione specificata.
[Ottenere un'attività correttiva per ID](get-remediation-one-activity.md) | Entità di indagine | Restituisce informazioni per l'attività di correzione specificata.

Ulteriori informazioni sulle [attività di correzione.](tvm-remediation.md)

## <a name="properties"></a>Proprietà

ID proprietà | Tipo di dati | Descrizione
:---|:---|:---
category | Stringa | Categoria dell'attività di correzione (configurazione software/sicurezza)
completerEmail | Stringa | Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene il messaggio di posta elettronica
completerId | Stringa | Se l'attività di correzione è stata completata manualmente da un utente, questa colonna contiene l'ID oggetto
completionMethod | Stringa | Un'attività di correzione può essere completata "automaticamente" (se tutti i dispositivi sono patchati) o "manualmente" da una persona che seleziona "contrassegna come completata".
createdOn | DateTime | Ora in cui è stata creata questa attività di correzione
descrizione | Stringa | Descrizione di questa attività di correzione
dueOn | DateTime | Data di scadenza impostata dal creatore per questa attività di correzione
fixedDevices |  | Il numero di dispositivi che sono stati corretti
id | Stringa | ID di questa attività di correzione
nameId | Stringa | Nome prodotto correlato
priority | Stringa | Priorità impostata dal creatore per questa attività di correzione (High\Medium\Low)
productId | Stringa | ID prodotto correlato
productivityImpactRemediationType | Stringa | Alcune modifiche alla configurazione potrebbero essere richieste solo per i dispositivi senza alcun impatto sull'utente. Questo valore indica la selezione tra "tutti i dispositivi esposti" o "solo i dispositivi senza impatto sull'utente".
rbacGroupNames | Stringa | Nomi dei gruppi di dispositivi correlati
recommendedProgram | Stringa | Programma consigliato a cui eseguire l'aggiornamento
recommendedVendor | Stringa | Fornitore consigliato a cui eseguire l'aggiornamento
recommendedVersion | Stringa | Versione consigliata per l'aggiornamento/aggiornamento
relatedComponent | Stringa | Componente correlato di questa attività di correzione (simile al componente correlato per una raccomandazione sulla sicurezza)
requesterEmail | Stringa | Indirizzo di posta elettronica creatore
requesterId | Stringa | ID oggetto creatore
requesterNotes | Stringa | Note (testo libero) aggiunte dall'autore per questa attività di correzione
scid | Stringa | SCID della raccomandazione relativa alla sicurezza
status | Stringa | Stato attività di correzione (Attivo/Completato)
statusLastModifiedOn | DateTime | Data in cui il campo stato è stato aggiornato
targetDevices | Long | Numero di dispositivi esposti a cui è applicabile questa correzione
title | Stringa | Titolo di questa attività di correzione
type | Stringa | Tipo di correzione
vendorId | Stringa | Nome fornitore correlato

## <a name="see-also"></a>Vedere anche

- [Ottenere un'attività correttiva per ID](get-remediation-one-activity.md)

- [Elencare tutte le attività correttive](get-remediation-all-activities.md)

- [Elencare i dispositivi esposti a un'attività correttiva](get-remediation-exposed-devices-activities.md)

- [Rischio basato sulle minacce & gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
