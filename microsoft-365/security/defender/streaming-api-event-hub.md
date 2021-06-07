---
title: Trasmettere Microsoft 365 defender agli hub eventi di Azure
description: Scopri come configurare Microsoft 365 Defender per trasmettere eventi di ricerca avanzata al tuo Hub eventi.
keywords: esportazione di dati non elaborati, API di streaming, API, Hub eventi di Azure, archiviazione di Azure, account di archiviazione, Ricerca avanzata, condivisione di dati non elaborati
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: b96ae78b0f2decfe7b2c6f695a4456ac93919c35
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772508"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Configurare Microsoft 365 Defender per trasmettere gli eventi di ricerca avanzata agli hub eventi di Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Informazioni preliminari:

1. Creare un [hub eventi](/azure/event-hubs/) nel tenant.

2. Accedere al [tenant di Azure,](https://ms.portal.azure.com/)passare a Sottoscrizioni > La sottoscrizione > provider di risorse **> registrarsi a Microsoft.Insights**.

3. Crea uno spazio dei nomi hub eventi, vai a Hub eventi **> Aggiungi** e seleziona il livello di prezzi, le unità di velocità effettiva e l'gonfiazione automatica appropriata per il carico previsto. Per altre informazioni, vedi [Prezzi - Hub eventi | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

4. Dopo aver creato lo spazio dei nomi dell'hub eventi, dovrai aggiungere l'entità servizio di registrazione app come lettore, il ricevitore di dati hub eventi di Azure e l'utente che accederà Microsoft 365 Defender come collaboratore (questa operazione può essere eseguita anche a livello di gruppo di risorse o di sottoscrizione). Vai a Hub eventi dello spazio dei nomi > controllo di accesso **(IAM) > Aggiungi** e verifica in **Assegnazioni di ruolo**.

## <a name="enable-raw-data-streaming"></a>Abilita flusso di dati non elaborati:

1. Accedere al Centro sicurezza [Microsoft 365 Defender](https://security.microsoft.com) come ***Amministratore** globale _ o _* Amministratore _della sicurezza_**.

2. Passare alla [pagina Impostazioni esportazione dati](https://security.microsoft.com/settings/mtp_settings/raw_data_export).

3. Fare clic su **Aggiungi**.

4. Scegliere un nome per le nuove impostazioni.

5. Scegliere **Inoltra eventi a Hub eventi di Azure**.

6. Puoi scegliere se esportare i dati dell'evento in un singolo hub eventi o per esportare ogni tabella di eventi in un hub pari diverso nello spazio dei nomi dell'hub eventi. 

7. Per esportare i dati dell'evento in un singolo hub eventi, immetti il nome **dell'hub eventi** e l'ID **risorsa Hub eventi.**

   Per ottenere **l'ID** risorsa Hub eventi, passare alla pagina dello spazio dei nomi Hub eventi di [Azure](https://ms.portal.azure.com/)nella scheda Proprietà di Azure > copiare il testo in  >   ID **risorsa**:

   ![Immagine della risorsa hub eventi ID1](../defender-endpoint/images/event-hub-resource-id.png)

8. Scegli gli eventi che vuoi trasmettere e fai clic su **Salva.**

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Schema degli eventi negli hub eventi di Azure:

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Ogni messaggio dell'hub eventi in Hub eventi di Azure contiene un elenco di record.

- Ogni record contiene il nome dell'evento, l'ora in cui Microsoft 365 Defender ha ricevuto l'evento, il tenant a cui appartiene (si otterrà solo gli eventi dal tenant) e l'evento in formato JSON in una proprietà denominata "**properties**".

- Per altre informazioni sullo schema degli eventi Microsoft 365 Defender, vedi [Panoramica di Advanced Hunting.](advanced-hunting-overview.md)

- In Ricerca avanzata, la **tabella DeviceInfo** contiene una colonna denominata **MachineGroup** che contiene il gruppo del dispositivo. Anche qui ogni evento verrà decorato con questa colonna. 

9. Per esportare ogni tabella di eventi in un hub eventi diverso, lascia semplicemente vuoto il nome **dell'hub** eventi e Microsoft 365 Defender farà il resto.


## <a name="data-types-mapping"></a>Mapping dei tipi di dati:

Per ottenere i tipi di dati per le proprietà dell'evento, eseguire le operazioni seguenti:

1. Accedi al centro [Microsoft 365 sicurezza](https://security.microsoft.com) e vai alla pagina [Ricerca avanzata.](https://security.microsoft.com/hunting-package)

2. Eseguire la query seguente per ottenere il mapping dei tipi di dati per ogni evento:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Ecco un esempio di evento Info dispositivo: 

  ![Immagine della risorsa hub eventi ID2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Microsoft 365 Defender streaming API](streaming-api.md)
- [Trasmettere Microsoft 365 eventi di Defender all'account di archiviazione di Azure](streaming-api-storage.md)
- [Documentazione di Azure Event Hubs](/azure/event-hubs/)
- [Risolvere i problemi di connettività - Hub eventi di Azure](/azure/event-hubs/troubleshooting-guide)
