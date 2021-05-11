---
title: Preparare un file CSV per un elenco ID Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Utilizzare un file CSV da una ricerca contenuto esistente per creare una ricerca nell'elenco ID che restituisce elementi di posta elettronica specifici.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311539"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Preparare un file CSV per un elenco ID Ricerca contenuto

È possibile cercare messaggi di posta elettronica specifici e altri elementi della cassetta postale utilizzando un elenco di ID Exchange cassetta postale. Per creare un elenco ID di ricerca, è necessario inviare un file con valori delimitati da virgole (CSV) che identifica gli elementi della cassetta postale specifici da cercare. Per questo file CSV, si utilizza il file **Results.csv** o il file **Items.csv** non indicizzato che vengono inclusi quando si esportano i risultati della ricerca contenuto o si esporta un report Ricerca contenuto da una ricerca contenuto esistente. Quindi si modifica uno di questi file per indicare gli elementi specifici da cercare, creare una nuova ricerca nell'elenco ID e inviare il file CSV.

**Perché creare una ricerca nell'elenco id?** Se non è possibile determinare se un elemento risponde a una richiesta di eDiscovery in base ai metadati nei file **Results.csv** o **Items.csvnon** indicizzati, è possibile utilizzare una ricerca nell'elenco id per trovare, visualizzare in anteprima ed esportare tale elemento per determinare se è reattivo al caso in cui si sta esaminando. Le ricerche nell'elenco ID vengono in genere utilizzate per cercare e restituire un set specifico di elementi non indicizzati.

Ecco una breve panoramica del processo di creazione di una ricerca nell'elenco id.

1. Creare ed eseguire una nuova ricerca nel Centro Microsoft 365 conformità.

2. Esportare i risultati della ricerca contenuto o il report di ricerca contenuto. Per ulteriori informazioni, vedere:

    - [Esportare i risultati della Ricerca contenuto](export-search-results.md)

    - [Esportare il rapporto della Ricerca contenuto](export-a-content-search-report.md)

3. Modificare il **fileResults.csv** o il file di **Items.csv** non indicizzato e identificare gli elementi specifici della cassetta postale da includere nella ricerca nell'elenco id. Vedere le [istruzioni per](#prepare-the-csv-file-for-an-id-list-search) la preparazione di un file CSV per una ricerca nell'elenco di ID.

4. Creare una nuova ricerca nell'elenco id (vedere le [istruzioni](#create-an-id-list-search)) e inviare il file CSV preparato. La query di ricerca creata ricercherà solo gli elementi selezionati nel file CSV.

> [!NOTE]
> Le ricerche nell'elenco id sono supportate solo per gli elementi delle cassette postali. Non è possibile cercare documenti SharePoint e OneDrive ricerca in un elenco ID.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparare il file CSV per una ricerca nell'elenco id

Dopo aver esportato i risultati della ricerca o il report per una ricerca, eseguire la procedura seguente per preparare il file CSV per una ricerca nell'elenco id. Questo file CSV identifica ogni elemento nella ricerca nell'elenco ID.

È possibile utilizzare un file CSV da una ricerca che includeva siti SharePoint e account OneDrive, ma è possibile selezionare solo gli elementi delle cassette postali per una ricerca nell'elenco id. Se si seleziona un documento in SharePoint o OneDrive, il file CSV non verrà convalidato quando si crea una ricerca nell'elenco di ID.

1. Aprire il **Results.csv** **o il** file Items.csvnon indicizzato in Excel.

2. Nella **colonna Selezionato** digitare **Sì** nella cella corrispondente all'elemento che si desidera cercare. Ripetere questo passaggio per ogni elemento che si desidera cercare.

    > [!IMPORTANT]
    > Quando si apre il file CSV in Excel, il formato dei dati per la colonna **ID** documento potrebbe essere stato modificato in **Generale.** In questo modo viene visualizzato l'ID documento di un elemento in notazione scientifica. Ad esempio, l'ID documento "481037338205" viene visualizzato come "4.81037E+11". In questo caso, è necessario eseguire i passaggi successivi per modificare il formato dei dati della colonna **ID** documento in **Numero** per ripristinare il formato corretto per l'ID documento. In caso contrario, la ricerca dell'elenco ID che utilizza il file CSV avrà esito negativo.

3. Fare clic con il pulsante destro **del mouse sull'intera colonna ID** documento e scegliere Formato **celle.**

4. Nella casella **Categoria** fare clic su **Numero**.

5. Impostare il numero di posizioni decimali su **0** e quindi fare clic su **OK** per salvare le modifiche. Si noti che i valori nella colonna ID documento vengono modificati in numeri.

    Ecco un esempio di un file CSV pronto per l'invio per una ricerca di contenuto elenco ID.

    ![Esempio di file CSV per una ricerca di contenuto mirata](../media/SearchIDListCSVFile.png)

6. Salvare il file CSV o usare **Salva con nome** per salvare il file con un nome di file diverso. In entrambi i casi, assicurarsi di salvare il file con il formato CSV.

## <a name="create-an-id-list-search"></a>Creare una ricerca elenco ID

Il passaggio successivo consiste nel creare una nuova ricerca nell'elenco di ID e nell'inviare il file CSV preparato nel passaggio precedente.

> [!IMPORTANT]
> È consigliabile creare una ricerca elenco ID non più di 2 giorni dopo l'esportazione dei risultati o del report di ricerca. Se i risultati della ricerca o il report sono stati esportati più di 2 giorni fa, è consigliabile esportare di nuovo i risultati o il report di ricerca per generare file CSV aggiornati. Puoi quindi preparare uno dei file CSV aggiornati e usarlo per creare una ricerca nell'elenco id.

1. Andare su <https://compliance.microsoft.com> ed eseguire l'accesso.

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365, fare clic su **Mostra tutto**, quindi su **Ricerca contenuto**.

3. Nella pagina **Ricerca contenuto** fare clic su Cerca per **ID elenco.**

4. Nel riquadro a comparsa Cerca per **ID,** assegnare un nome  alla ricerca e facoltativamente descriverla, quindi fare clic su Sfoglia e selezionare il file CSV preparato nel passaggio precedente.

    Microsoft 365 tenta di convalidare il file CSV. Se la convalida non riesce, viene visualizzato un messaggio di errore che può essere utile per risolvere gli errori di convalida. Il file CSV deve essere convalidato correttamente per creare una ricerca nell'elenco id.

5. Dopo aver convalidato correttamente il file CSV, fare clic **su Cerca** per creare la ricerca nell'elenco ID.

    Ecco un esempio della pagina a comparsa di una ricerca nell'elenco ID che mostra la query generata e il numero stimato di risultati della ricerca.

    ![Query di ricerca per la ricerca nell'elenco ID](../media/SearchIDListFlyout.png)

    Il numero di elementi stimati visualizzati nelle statistiche per la ricerca id deve corrispondere al numero di elementi selezionati nel file CSV.

6. Visualizzare in anteprima o esportare gli elementi restituiti dalla ricerca nell'elenco ID.

## <a name="more-information"></a>Ulteriori informazioni

Se si sposta una cassetta postale dopo aver creato una ricerca nell'elenco id, la query per la ricerca non restituirà gli elementi specificati. Questo perché la proprietà **DocumentId** per gli elementi della cassetta postale viene modificata quando una cassetta postale viene spostata. Nella rara istanza in cui una cassetta postale viene spostata dopo aver creato una ricerca elenco ID, è consigliabile creare una nuova ricerca contenuto (o aggiornare i risultati della ricerca per una ricerca esistente) e quindi esportare i risultati della ricerca o il report per generare file CSV aggiornati che possono essere utilizzati per creare una nuova ricerca nell'elenco di ID.
