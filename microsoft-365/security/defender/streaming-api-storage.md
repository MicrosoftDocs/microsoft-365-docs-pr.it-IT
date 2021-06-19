---
title: Trasmettere Microsoft 365 Defender eventi al tuo account Archiviazione utente
description: Scopri come configurare Microsoft 365 Defender trasmettere eventi di ricerca avanzata al tuo account Archiviazione.
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029658"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurare Microsoft 365 Defender per trasmettere eventi di ricerca avanzata al tuo account Archiviazione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Prima di iniziare

1. Creare un [Archiviazione nel](/azure/storage/common/storage-account-overview) tenant.

2. Accedere al [tenant di Azure,](https://ms.portal.azure.com/)passare a Sottoscrizioni > La sottoscrizione > provider di risorse **> registrarsi a Microsoft.Insights**.

## <a name="enable-raw-data-streaming"></a>Abilitare lo streaming di dati non elaborati

1. Accedere al portale di Microsoft 365 Defender ( <https://security.microsoft.com> ) come ***Amministratore** globale _ o _*_Amministratore della sicurezza_**.

2. Vai a **Impostazioni** \> **Microsoft 365 Defender** \> **Streaming API**. Per passare direttamente alla pagina **API di streaming,** usa <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .

3. Fare clic su **Aggiungi**.

4. Nel riquadro **a comparsa Aggiungi nuove impostazioni API** di streaming visualizzato configura le impostazioni seguenti:
   1. **Nome**: scegliere un nome per le nuove impostazioni.
   2. Selezionare **Inoltra eventi a Archiviazione di Azure**.
   3. Nella casella **Archiviazione ID** risorsa account che viene visualizzato digitare l Archiviazione ID **risorsa account.** Per ottenere **l'ID** risorsa account Archiviazione , aprire il portale di Azure in , fare clic su account Archiviazione passare alla scheda proprietà copiare il testo in ID risorsa account Archiviazione <https://portal.azure.com>  \> \> . 

      ![Immagine della risorsa hub eventi ID1](../defender-endpoint/images/storage-account-resource-id.png)

   4. Torna al riquadro a comparsa **Aggiungi nuove impostazioni API** di streaming, scegli i tipi **di** evento che vuoi trasmettere.

   Al termine, fare clic su **Invia.**

## <a name="the-schema-of-the-events-in-the-storage-account"></a>Schema degli eventi nell'account Archiviazione account

- Verrà creato un contenitore BLOB per ogni tipo di evento:

  ![Immagine della risorsa hub eventi ID2](../defender-endpoint/images/storage-account-event-schema.png)

- Lo schema di ogni riga di un BLOB è il codice JSON seguente:

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- Ogni BLOB contiene più righe.

- Ogni riga contiene il nome dell'evento, l'ora in cui Defender per Endpoint ha ricevuto l'evento, il tenant a cui appartiene (si otterrà solo gli eventi dal tenant) e l'evento in formato JSON in una proprietà denominata "proprietà".

- Per ulteriori informazioni sullo schema degli eventi Microsoft 365 Defender, vedere [Advanced Hunting overview.](../defender/advanced-hunting-overview.md)

## <a name="data-types-mapping"></a>Mapping dei tipi di dati

Per ottenere i tipi di dati per le proprietà degli eventi, eseguire le operazioni seguenti:

1. Accedi al portale di Microsoft 365 Defender ( <https://security.microsoft.com> ) e vai a Ricerca **avanzata** \> **ricerca**. Per passare direttamente alla **pagina Ricerca avanzata,** utilizzare <security.microsoft.com/advanced-hunting>.

2. Nella scheda **Query** eseguire la query seguente per ottenere il mapping dei tipi di dati per ogni evento:

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Ecco un esempio di evento Info dispositivo:

  ![Immagine della risorsa hub eventi ID3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della ricerca avanzata](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](streaming-api.md)
- [Trasmettere Microsoft 365 Defender eventi all'account di archiviazione di Azure](streaming-api-storage.md)
- [Archiviazione di Azure Documentazione dell'account](/azure/storage/common/storage-account-overview)
