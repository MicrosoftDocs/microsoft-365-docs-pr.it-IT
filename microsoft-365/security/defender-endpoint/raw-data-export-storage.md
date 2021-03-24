---
title: Trasmettere gli eventi di Microsoft Defender for Endpoint al tuo account di archiviazione
description: Scopri come configurare Microsoft Defender ATP per trasmettere eventi di ricerca avanzata al tuo account di archiviazione.
keywords: esportazione di dati non elaborati, API di streaming, API, hub eventi, archiviazione di Azure, account di archiviazione, ricerca avanzata, condivisione di dati non elaborati
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
ms.openlocfilehash: 9f1eb79bbf617afad58b7e4d70e1f40e422f9046
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063850"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurare Microsoft Defender per Endpoint per trasmettere eventi di ricerca avanzata al tuo account di archiviazione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Informazioni preliminari:

1. Creare un [account di archiviazione](https://docs.microsoft.com/azure/storage/common/storage-account-overview) nel tenant.

2. Accedere al [tenant di Azure,](https://ms.portal.azure.com/)passare a Sottoscrizioni > La sottoscrizione > provider di risorse **> registrarsi a Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Abilita flusso di dati non elaborati:

1. Accedere a [Microsoft Defender for Endpoint Portal](https://securitycenter.windows.com) come amministratore globale _ o _* Amministratore della _sicurezza_**.

2. Vai alla [pagina Impostazioni esportazione dati](https://securitycenter.windows.com/interoperability/dataexport) in Microsoft Defender Security Center.

3. Fare clic **su Aggiungi impostazioni di esportazione dati**.

4. Scegliere un nome per le nuove impostazioni.

5. Scegliere **Inoltra eventi a Archiviazione di Azure**.

6. Digitare **l'ID risorsa dell'account di archiviazione**. Per ottenere l'ID risorsa **dell'account** di archiviazione, passare alla pagina Account di archiviazione nella scheda Proprietà > portale di [Azure](https://ms.portal.azure.com/) > copiare il testo in ID risorsa **account di archiviazione**:

   ![Immagine della risorsa hub eventi ID1](images/storage-account-resource-id.png)

7. Scegli gli eventi che vuoi trasmettere e fai clic su **Salva.**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Schema degli eventi nell'account di archiviazione:

- Verrà creato un contenitore BLOB per ogni tipo di evento: 

  ![Immagine della risorsa hub eventi ID2](images/storage-account-event-schema.png)

- Lo schema di ogni riga di un BLOB è il codice JSON seguente: 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- Ogni BLOB contiene più righe.

- Ogni riga contiene il nome dell'evento, l'ora in cui Defender per Endpoint ha ricevuto l'evento, il tenant a cui appartiene (si otterrà solo gli eventi dal tenant) e l'evento in formato JSON in una proprietà denominata "proprietà".

- Per altre informazioni sullo schema degli eventi di Microsoft Defender for Endpoint, vedi [Panoramica di Advanced Hunting.](advanced-hunting-overview.md)

- In Ricerca avanzata, la **tabella DeviceInfo** contiene una colonna denominata **MachineGroup** che contiene il gruppo del dispositivo. Anche qui ogni evento verrà decorato con questa colonna. Per [altre informazioni, vedi Gruppi](machine-groups.md) di dispositivi.

## <a name="data-types-mapping"></a>Mapping dei tipi di dati:

Per ottenere i tipi di dati per le proprietà degli eventi, eseguire le operazioni seguenti:

1. Accedi a [Microsoft Defender Security Center](https://securitycenter.windows.com) e vai alla pagina Ricerca [avanzata.](https://securitycenter.windows.com/hunting-package)

2. Eseguire la query seguente per ottenere il mapping dei tipi di dati per ogni evento: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Ecco un esempio di evento Info dispositivo: 

  ![Immagine della risorsa hub eventi ID3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [API di streaming di Microsoft Defender per endpoint](raw-data-export.md)
- [Trasmettere gli eventi di Microsoft Defender for Endpoint al tuo account di archiviazione di Azure](raw-data-export-storage.md)
- [Documentazione relativa all'account di archiviazione di Azure](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
