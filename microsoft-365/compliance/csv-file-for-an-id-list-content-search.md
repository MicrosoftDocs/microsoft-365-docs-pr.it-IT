---
title: Preparare un file CSV per una ricerca di contenuto nell'elenco di ID in Office 365
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
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Utilizzare il file results. csv o unindexed Items. csv da una ricerca di contenuto esistente per creare una ricerca nell'elenco di ID che restituisca messaggi di posta elettronica specifici. Le ricerche degli elenchi di ID vengono in genere utilizzate per restituire gli elementi della cassetta postale parzialmente indicizzati.
ms.openlocfilehash: 97c69cd096e1ec2fa69082edef70cd41dfd229b0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077021"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a>Preparare un file CSV per una ricerca di contenuto nell'elenco di ID in Office 365

È possibile cercare specifici messaggi di posta elettronica della cassetta postale e altri elementi della cassetta postale utilizzando un elenco di ID di Exchange. Per creare una ricerca nell'elenco di ID (denominato formalmente ricerca mirata), è necessario inviare un file CSV (comma separated value) che identifica gli elementi specifici della cassetta postale da cercare. Per questo file CSV è possibile utilizzare il file **results. csv** o il file **unindexed Items. csv** incluso quando si esportano i risultati della ricerca di contenuto o si esporta un rapporto di ricerca contenuto e la ricerca di contenuto esistente. Successivamente, modificare uno di questi file per indicare gli elementi specifici da cercare e quindi creare un nuovo elenco di ID ricerca e inviare il file CSV.

Ecco una breve panoramica del processo per la creazione di una ricerca nell'elenco di ID.

1. Creare ed eseguire una ricerca di contenuto nuovo o guidato nel centro sicurezza & Compliance.

2. Esportare i risultati della ricerca del contenuto o esportare il rapporto di ricerca contenuto. Per altre informazioni, vedere:

    - [Esportare i risultati della Ricerca contenuto](export-search-results.md)

    - [Esportare il rapporto della Ricerca contenuto](export-a-content-search-report.md)

3. Modificare il file **results. csv** o gli **elementi non indicizzati. csv** e identificare gli elementi specifici della cassetta postale che si desidera includere nella ricerca nell'elenco di ID. Vedere le [istruzioni](#prepare-the-csv-file-for-an-id-list-search) per la preparazione di un file CSV per la ricerca di un elenco di ID.

4. Creare una nuova ricerca nell'elenco di ID (vedere le [istruzioni](#create-an-id-list-search)) e inviare il file CSV preparato. La query di ricerca creata eseguirà la ricerca solo degli elementi selezionati nel file CSV.

> [!NOTE]
> Le ricerche degli elenchi di ID sono supportate solo per gli elementi delle cassette postali. Non è possibile cercare i documenti di SharePoint e OneDrive in una ricerca nell'elenco di ID.

 **Perché creare una ricerca nell'elenco di ID?** Se non si è in grado di determinare se un elemento risponde a una richiesta di eDiscovery basata sui metadati nei file CSV **. csv o** **elementi non indicizzati** , è possibile utilizzare la ricerca di un elenco di ID per trovare, visualizzare in anteprima e quindi esportare tale elemento per determinare se è sensibile al caso in cui si sta indagando. Le ricerche degli elenchi di ID vengono in genere utilizzate per cercare e restituire un insieme specifico di elementi non indicizzati.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparare il file CSV per una ricerca nell'elenco di ID

Dopo aver esportato i risultati della ricerca o il report per una ricerca di contenuto, è possibile eseguire la procedura seguente per preparare il file CSV per la ricerca di un elenco di ID. Questo file CSV identificherà tutti gli elementi nella ricerca dell'elenco di ID.

Si noti che è possibile utilizzare un file CSV da una ricerca in cui sono inclusi i siti di SharePoint e gli account di OneDrive, ma è possibile selezionare *solo* gli elementi della cassetta postale per una ricerca nell'elenco di ID. Se si seleziona un documento in SharePoint o OneDrive, il file CSV avrà esito negativo quando si crea una ricerca nell'elenco di ID.

1. Aprire il file **results. csv** o **unindexed Items. csv** in Excel.

2. Nella colonna **selezionata** digitare **Sì** nella cella corrispondente all'elemento che si desidera ricercare. Ripetere questo passaggio per ogni elemento che si desidera ricercare.

    > [!IMPORTANT]
    > Quando si apre il file CSV in Excel, il formato dei dati per la colonna **ID documento** viene modificato in **generale**. In questo modo viene visualizzato l'ID documento per un elemento nella notazione scientifica. Ad esempio, l'ID documento "481037338205" viene visualizzato come "4.81037 E + 11" è necessario eseguire i passaggi successivi per modificare il formato dei dati della colonna **ID documento** in **numero** per ripristinare il formato corretto per l'ID documento. Se non si esegue questa operazione, la ricerca dell'elenco di ID che utilizza il file CSV avrà esito negativo.

3. Fare clic con il pulsante destro del mouse sull'intera colonna **ID documento** e scegliere **Format Cells**.

4. Nella casella **categoria** fare clic su **numero**.

5. Modificare il numero di posizioni decimali su **0**, quindi fare clic su **OK** per salvare le modifiche. Si noti che i valori nella colonna ID documento vengono modificati in numeri.

    Di seguito è riportato un esempio di un file CSV che è pronto per essere inviato per la ricerca di contenuto di un elenco di ID.

    ![Esempio di un file CSV per una ricerca di contenuto mirata](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Salvare il file CSV o utilizzare **Salva** con nome per salvare il file con un file diverso. In entrambi i casi, assicurarsi di salvare il file con il formato CSV.

## <a name="create-an-id-list-search"></a>Creare una ricerca nell'elenco di ID

Il passaggio successivo consiste nel creare una nuova ricerca del contenuto dell'elenco di ID e nel inviare il file CSV preparato nel passaggio precedente.

> [!IMPORTANT]
> È consigliabile creare un elenco di ID che non superi i 2 giorni dopo l'esportazione dei risultati o del report da una ricerca di contenuto. Se i risultati della ricerca o il report in cui è stata esportata più di 2 giorni fa, è necessario riesportare i risultati della ricerca o il report per generare i file CSV aggiornati. È quindi possibile preparare uno dei file CSV aggiornati e utilizzarlo per creare una ricerca nell'elenco di ID.

1. Nel centro sicurezza & conformità, andare a ricerca **** \> **contenuto**ricerca.

2. Nella pagina **ricerca** fare clic sulla freccia accanto a Aggiungi ![](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nuova ricerca**icona, quindi fare clic su **Cerca in base all'elenco di ID**.

    ![Fare clic su Cerca in base all'elenco di ID dall'elenco a discesa nuovo ricerca](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. Nel riquadro a comparsa **ricerca in base all'elenco di ID** , denominare la ricerca e, facoltativamente, descriverla, quindi fare clic su **Sfoglia** e selezionare il file CSV preparato nel passaggio precedente.

    Office 365 tenta di convalidare il file CSV. Se la convalida non ha avuto esito positivo, verrà visualizzato un messaggio di errore che potrebbe facilitare la risoluzione dei problemi relativi agli errori di convalida. Il file CSV deve essere convalidato correttamente per creare una ricerca nell'elenco di ID.

4. Dopo aver convalidato il file CSV, fare clic su **Cerca** per creare la ricerca nell'elenco di ID.

    Di seguito è riportato un esempio dei risultati di ricerca stimati e della query generata per una ricerca nell'elenco di ID.

    ![Query di ricerca per una ricerca di contenuto mirata nel riquadro dei dettagli](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Si noti che il numero di elementi stimati visualizzati nelle statistiche per la ricerca ID deve corrispondere al numero di elementi selezionati nel file CSV.

5. Visualizzare in anteprima o esportare gli elementi restituiti dalla ricerca dell'elenco di ID.

> [!NOTE]
> Se si sposta una cassetta postale dopo aver creato una ricerca nell'elenco di ID, la query per la ricerca non restituirà gli elementi specificati. Ciò è dovuto al fatto che la proprietà **DocumentID** per gli elementi della cassetta postale viene modificata quando una cassetta postale viene spostata. Nell'istanza rara quando una cassetta postale viene spostata dopo aver creato una ricerca nell'elenco di ID, è necessario creare una nuova ricerca contenuto (o aggiornare i risultati della ricerca per la ricerca di contenuto esistente) e quindi esportare i risultati della ricerca o il report per generare i file CSV aggiornati che possono essere utilizzati  per creare una nuova ricerca nell'elenco di ID.
