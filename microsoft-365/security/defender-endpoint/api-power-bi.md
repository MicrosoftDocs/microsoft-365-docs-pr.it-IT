---
title: Connessione delle API di Microsoft Defender ATP a Power BI
ms.reviewer: ''
description: Crea un report power business intelligence (BI) sopra le API di Microsoft Defender per endpoint.
keywords: api, api supportate, Power BI, report
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
ms.openlocfilehash: 696782ca03e5494c3fc5ca08943d1079c5d78f8a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167033"
---
# <a name="create-custom-reports-using-power-bi"></a>Creare report personalizzati con Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

In questa sezione imparerai a creare un report di Power BI in Defender per le API endpoint.

Nel primo esempio viene illustrato come connettere Power BI all'API Advanced Hunting e nel secondo esempio viene illustrata una connessione alle API OData, ad esempio azioni del computer o avvisi.

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Connettere Power BI all'API advanced hunting

- Aprire Microsoft Power BI

- Fare **clic su Ottieni query** vuota  >  **dati**

    ![Immagine della creazione di una query vuota](images/power-bi-create-blank-query.png)

- Fare clic **su Editor avanzato**

    ![Immagine dell'editor avanzato aperto](images/power-bi-open-advanced-editor.png)

- Copiare quanto segue e incollarlo nell'editor:

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- Fare clic **su Fine**

- Fare **clic su Modifica credenziali**

    ![Immagine delle credenziali di modifica0](images/power-bi-edit-credentials.png)

- Seleziona **Account organizzazione**  >  **Accedi**

    ![Immagine del set di credenziali1](images/power-bi-set-credentials-organizational.png)

- Immettere le credenziali e attendere l'accesso

- Fare clic **su Connetti**

    ![Immagine del set di credenziali2](images/power-bi-set-credentials-organizational-cont.png)

- Ora i risultati della query verranno visualizzati come tabella ed è possibile iniziare a creare visualizzazioni sopra di essa.

- È possibile duplicare la tabella, rinominarla e modificare la query ricerca avanzata all'interno per ottenere i dati che si desidera.

## <a name="connect-power-bi-to-odata-apis"></a>Connettere Power BI alle API OData

- L'unica differenza rispetto all'esempio precedente è la query all'interno dell'editor. 

- Copia quanto segue e incollalo nell'editor per estrarre tutte **le azioni del computer** dall'organizzazione:

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- È possibile eseguire la stessa operazione per **Avvisi** e **computer.**

- È inoltre possibile utilizzare query OData per filtri di query, vedere [Utilizzo di query OData](exposed-apis-odata-samples.md)


## <a name="power-bi-dashboard-samples-in-github"></a>Esempi di dashboard di Power BI in GitHub
Per ulteriori informazioni, vedere Modelli [di report di Power BI.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)

## <a name="sample-reports"></a>Report di esempio
Visualizzare gli esempi di report di Power BI di Microsoft Defender ATP. Per ulteriori informazioni, vedere [Sfogliare gli esempi di codice.](https://docs.microsoft.com/samples/browse/?products=mdatp)


## <a name="related-topic"></a>Argomento correlato
- [API defender per endpoint](apis-intro.md)
- [Rilevazione avanzata API](run-advanced-query-api.md)
- [Utilizzo di query OData](exposed-apis-odata-samples.md)
