---
title: Esportare, configurare e visualizzare i record del log di controllo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni su come esportare, configurare e visualizzare i record del registro di controllo di Microsoft 365.
ms.openlocfilehash: 833d42ee37722092bddf14d0ef3418fac1ab03bb
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817745"
---
# <a name="export-configure-and-view-audit-log-records"></a>Esportare, configurare e visualizzare i record del log di controllo

Dopo aver eseguito una ricerca nel registro di controllo e aver scaricato i risultati della ricerca in un file CSV, il file contiene una colonna denominata **AuditData**, che contiene informazioni aggiuntive su ogni evento. I dati contenuti in questa colonna sono formattati come un oggetto JSON, che contiene più proprietà configurate come coppie *proprietà: valore* separate da virgole. È possibile utilizzare la caratteristica di trasformazione JSON nell'editor di query di alimentazione in Excel per dividere ogni proprietà nell'oggetto JSON nella colonna **AuditData** in più colonne in modo che ogni proprietà disponga di una propria colonna. In questo modo è possibile ordinare e filtrare una o più di queste proprietà, che consentono di individuare rapidamente i dati di controllo specifici che si stanno cercando.

## <a name="step-1-export-audit-log-search-results"></a>Passaggio 1: esportare i risultati di ricerca del registro di controllo

Il primo passaggio consiste nell'eseguire una ricerca nel log di controllo e quindi esportare i risultati in un file con valori delimitati da virgole (CSV) nel computer locale.
  
1. Eseguire una [ricerca nel registro di controllo](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) e rivedere i criteri di ricerca se necessario fino a quando non si hanno i risultati desiderati.

2. Fare clic su **Esporta risultati** e selezionare **Scarica tutti i risultati**. 

   ![Fare clic su Scarica tutti i risultati](../media/ExportAuditSearchResults.png)

   Questa opzione consente di esportare tutti i record di controllo dalla ricerca del registro di controllo eseguita nel passaggio 1 e di scaricare i dati non elaborati dal registro di controllo in un file CSV. 

   Nella parte inferiore della finestra viene visualizzato un messaggio in cui viene richiesto di aprire o salvare il file CSV. 

3. Fare clic su **salva > Salva con nome** e salvare il file CSV nel computer locale. Per scaricare molti risultati della ricerca, è necessario un po' di tempo. Si tratta in genere del caso in cui si esegue la ricerca di tutte le attività o di un intervallo di date esteso. Quando il file CSV ha terminato il download, viene visualizzato un messaggio nella parte inferiore della finestra.

   ![Messaggio visualizzato quando è stato completato il download del file CSV](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > È possibile scaricare al massimo 50.000 voci in un file CSV da una singola ricerca nel log di controllo. Se vengono scaricate 50.000 voci nel file CSV, è probabile che ci siano più di 50.000 eventi che soddisfano i criteri di ricerca. Per esportare più di questo limite, provare a utilizzare un intervallo di date per ridurre il numero di record del registro di controllo. Potrebbe essere necessario eseguire più ricerche con intervalli di date più piccoli per esportare più di 50.000 voci.

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>Passaggio 2: formattare il log di controllo esportato utilizzando l'editor di query di alimentazione

Il passaggio successivo consiste nell'utilizzare la caratteristica di trasformazione JSON nell'editor di query di alimentazione in Excel per dividere ogni proprietà nell'oggetto JSON nella colonna **AuditData** nella relativa colonna. Vengono quindi filtrate le colonne per visualizzare i record in base ai valori delle proprietà specifiche. In questo modo è possibile individuare rapidamente i dati di controllo specifici che si stanno cercando.

1. Aprire una cartella di lavoro vuota in Excel per Office 365, Excel 2019 o Excel 2016.

2. Nella scheda **dati** fare clic su **testo/CSV**nel gruppo della barra multifunzione **Get & Transform Data** .

    ![Nella scheda dati fare clic su da testo/CSV](../media/JSONTransformOpenCSVFile.png)

3. Aprire il file CSV scaricato nel passaggio 1.

4. Nella finestra visualizzata fare clic su **trasforma dati**.

   ![Fare clic su trasforma dati](../media/JSONOpenPowerQuery.png)

   Il file CSV viene aperto nell' **editor di query**. Sono disponibili quattro colonne: **CreationDate**, **userids**, **Operations**e **AuditData**. La colonna **AuditData** è un oggetto JSON che contiene più proprietà. Il passaggio successivo consiste nel creare una colonna per ogni proprietà nell'oggetto JSON.

5. Fare clic con il pulsante destro del mouse sul titolo nella colonna **AuditData** , scegliere **Transform**e quindi fare clic su **JSON**. 

   ![Fare clic con il pulsante destro del mouse sulla colonna AuditData, scegliere Transform e quindi JSON](../media/JSONTransform.png)

6. Nell'angolo in alto a destra della colonna **AuditData** fare clic sull'icona Espandi.

   ![Nella colonna AuditData, fare clic sull'icona Espandi](../media/JSONTransformExpandIcon.png)

   Viene visualizzato un elenco parziale delle proprietà degli oggetti JSON nella colonna **AuditData** .

7. Fare clic su **carica altro** per visualizzare tutte le proprietà degli oggetti JSON nella colonna **AuditData** .

   ![Fare clic su carica altro per visualizzare tutte le proprietà nell'oggetto JSON](../media/JSONTransformLoadJSONProperties.png)

   È possibile deselezionare la casella di controllo accanto a qualsiasi proprietà che non si desidera includere. L'eliminazione delle colonne che non sono utili per l'analisi è un ottimo metodo per ridurre la quantità di dati visualizzati nel registro di controllo. 

   > [!NOTE]
   > Le proprietà JSON visualizzate nello screenshot precedente (dopo aver fatto clic su **carica altro**) si basano sulle proprietà rilevate nella colonna **AuditData** dalle prime 1.000 righe del file CSV. Se nei record sono presenti proprietà JSON diverse dopo le prime 1.000 righe, queste proprietà (e una colonna corrispondente) non verranno incluse quando la colonna **AuditData** viene divisa in più colonne. Per evitare questo, valutare la possibilità di rieseguire la ricerca del registro di controllo e limitare i criteri di ricerca in modo che vengano restituiti meno record. Un'altra soluzione alternativa consiste nel filtrare gli elementi nella colonna **Operations** per ridurre il numero di righe, prima di eseguire il passaggio 5 precedente, prima di trasformare l'oggetto JSON nella colonna **AuditData** .

8. Per formattare il titolo delle colonne aggiunte per ogni proprietà JSON selezionata, eseguire una delle operazioni seguenti.

    - Deselezionare la casella di controllo **Usa nome colonna originale come prefisso** per utilizzare il nome della proprietà JSON come nomi di colonna. ad esempio, **RecordType** o **sourceFileName**.

    - Lasciare selezionata la casella di controllo **Usa nome di colonna originale come prefisso** per aggiungere il prefisso AuditData ai nomi delle colonne. ad esempio, **AuditData. RecordType** o **AuditData. sourceFileName**.

9. Fare clic su **OK**.

    La colonna **AuditData** è suddivisa in più colonne. Ogni nuova colonna corrisponde a una proprietà dell'oggetto JSON AuditData. Ogni riga della colonna contiene il valore della proprietà. Se la proprietà non contiene un valore, verrà visualizzato il valore *null* . In Excel, le celle con valori null sono vuote.
  
10. Nella scheda **Home** fare clic su **Chiudi & caricamento** per chiudere l'editor di query di alimentazione e aprire il file CSV trasformato in una cartella di lavoro di Excel.

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>Utilizzo di PowerShell per la ricerca e l'esportazione dei record del registro di controllo

Invece di utilizzare lo strumento di ricerca del registro di controllo nel centro sicurezza & conformità, è possibile utilizzare il cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell per esportare i risultati di una ricerca nel registro di controllo in un file CSV. È quindi possibile eseguire la stessa procedura descritta nel passaggio 2 per formattare il log di controllo utilizzando l'editor di query di alimentazione. Un vantaggio dell'utilizzo del cmdlet di PowerShell è che è possibile cercare gli eventi da un servizio specifico utilizzando il parametro *RecordType* . Di seguito sono riportati alcuni esempi di utilizzo di PowerShell per esportare i record di controllo in un file CSV, in modo che sia possibile utilizzare l'editor di query di alimentazione per trasformare l'oggetto JSON nella colonna **AuditData** come descritto nel passaggio 2.

In questo esempio, eseguire i comandi seguenti per restituire tutti i record relativi alle operazioni di condivisione di SharePoint.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

I risultati della ricerca vengono esportati in un file CSV denominato *PowerShellAuditlog* che contiene quattro colonne: CreationDate, userids, RecordType, AuditData).

È inoltre possibile utilizzare il nome o il valore enum per il tipo di record come valore per il parametro *RecordType* . Per un elenco di nomi di tipi di record e relativi valori enum corrispondenti, vedere la tabella *AuditLogRecordType* in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).

È possibile includere solo un valore singolo per il parametro *RecordType* . Per cercare i record di controllo per altri tipi di record, è necessario eseguire di nuovo i due comandi precedenti per specificare un tipo di record diverso e accodare tali risultati al file CSV originale. Ad esempio, è necessario eseguire i due comandi seguenti per aggiungere le attività dei file di SharePoint dallo stesso intervallo di date al file PowerShellAuditlog.csv.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>Suggerimenti per l'esportazione e la visualizzazione del registro di controllo

Di seguito sono riportati alcuni suggerimenti ed esempi relativi all'esportazione e alla visualizzazione del registro di controllo prima e dopo l'utilizzo della caratteristica di trasformazione JSON per dividere la colonna **AuditData** in più colonne.

- Filtrare la colonna **RecordType** per visualizzare solo i record di un servizio o di un'area funzionale specifica. Ad esempio, per visualizzare gli eventi relativi alla condivisione di SharePoint, è necessario selezionare **14** (il valore enum per i record attivati dalle attività di condivisione di SharePoint). Per un elenco dei servizi che corrispondono ai valori enum visualizzati nella colonna **RecordType** , vedere [proprietà dettagliate nel log di controllo](detailed-properties-in-the-office-365-audit-log.md).

- Filtrare la colonna **Operations** per visualizzare i record per attività specifiche. Per un elenco della maggior parte delle operazioni che corrispondono a un'attività ricercabile nello strumento di ricerca del registro di controllo nel centro sicurezza & conformità, vedere la sezione "attività controllate" in [Search the audit log in the security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).
