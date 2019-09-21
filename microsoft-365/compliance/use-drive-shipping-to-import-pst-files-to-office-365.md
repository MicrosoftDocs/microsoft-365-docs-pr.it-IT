---
title: Utilizzare il servizio di spedizione delle unità per importare i file PST dell'organizzazione in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: "Per gli amministratori: informazioni su come importare in blocco i file PST dell'organizzazione nelle cassette postali di Office 365 copiando i file PST su un disco rigido e quindi inviarli a Microsoft. "
ms.openlocfilehash: 4e386dc94928b674565a1d096cdb75aad9a3e22e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084046"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>Utilizzare il servizio di spedizione delle unità per importare i file PST dell'organizzazione in Office 365

**Questo articolo è per gli amministratori. Si sta tentando di importare i file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Utilizzare il servizio di importazione di Office 365 e l'unità di spedizione per importare in blocco i file PST nelle cassette postali degli utenti. Per spedizione delle unità si intende la copia dei file PST su un'unità disco rigido e l'invio fisico dell'unità a Microsoft. Una volta ricevuto il disco rigido, il personale del data center copierà i dati dal disco rigido a un'area di archiviazione nel cloud Microsoft. Successivamente, si ha la possibilità di tagliare i dati PST effettivamente importati nelle cassette postali di destinazione impostando filtri che controllano quali dati vengono importati. Dopo aver avviato il processo di importazione, il servizio di importazione importa i dati PST dall'area di archiviazione alle cassette postali degli utenti. L'utilizzo della distribuzione delle unità per importare i file PST nelle cassette postali degli utenti è un modo per eseguire la migrazione della posta elettronica dell'organizzazione a Office 365.
  
Di seguito sono riportati i passaggi necessari per utilizzare la spedizione delle unità per importare i file PST nelle cassette postali di Office 365:
  
[Passaggio 1: scaricare la chiave di archiviazione sicura e lo strumento di importazione PST](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[Passaggio 2: copiare i file PST nell'unità disco rigido](#step-2-copy-the-pst-files-to-the-hard-drive)

[Passaggio 3: creare il file di mapping di importazione PST](#step-3-create-the-pst-import-mapping-file)

[Passaggio 4: creare un processo di Importazione PST in Office 365](#step-4-create-a-pst-import-job-in-office-365)

[Passaggio 5: inviare l'unità disco rigido a Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[Passaggio 6: filtrare i dati e avviare il processo di importazione PST](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> È necessario eseguire il passaggio 1 una volta per caricare la chiave di archiviazione sicura e lo strumento di importazione. Dopo aver eseguito questa procedura, eseguire il passaggio 2 del passaggio 6 ogni volta che si desidera inviare un'unità disco rigido a Microsoft. 
  
Per le domande frequenti sull'utilizzo della spedizione delle unità per importare i file PST in Office 365, vedere le domande [frequenti su come utilizzare la spedizione delle unità per importare i file PST](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files). 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere assegnati al ruolo di esportazione delle cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in [Manage Role](https://go.microsoft.com/fwlink/p/?LinkId=730688)groups.
    
    Per creare processi di importazione nel centro sicurezza & conformità, è inoltre necessario che sia vero uno dei seguenti valori:
    
  - È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oppure
    
  - È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
    > [!TIP]
    > Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
- È necessario archiviare i file PST che si desidera copiare in un'unità disco rigido su un file server o in una cartella condivisa dell'organizzazione. Nel passaggio 2 verrà eseguito lo strumento di esportazione di importazione di Azure (WAImportExport. exe) che copierà i file PST archiviati nel file server o nella cartella condivisa sul disco rigido.
    
- Solo 2,5 pollici Solid-State Drive (SSD) o 2,5 o 3,5 pollice SATA II/III unità disco rigido interne sono supportate per l'utilizzo con il servizio di importazione di Office 365. You can use hard drives up to 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati nel disco rigido. The data volume must be formatted with NTFS. Quando si copiano i dati su un disco rigido, è possibile collegarlo direttamente usando un connettore SATA II/III da 2,5 pollici o 2,5 o 3,5 pollice oppure è possibile collegarlo esternamente usando un adattatore USB da 2,5 pollici SSD o 2,5 o 3,5 pollici SATA II/III.
    
    > [!IMPORTANT]
    > Le unità disco rigido esterne che dispongono di un adattatore USB incorporato non sono supportate dal servizio di importazione di Office 365. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
- L'unità disco rigido in cui vengono copiati i file PST deve essere prima crittografata con BitLocker. Lo strumento WAImportExport.exe eseguito nel passaggio 2 consente di configurare BitLocker. Genera anche una chiave di crittografia BitLocker che il personale del Data Center di Microsoft utilizzerà per accedere all'unità per caricare i file PST nell'area di archiviazione di Azure nel cloud Microsoft.
    
- La spedizione delle unità è disponibile tramite un contratto Microsoft Enterprise (EA). La distribuzione delle unità non è disponibile tramite un contratto di prodotti e servizi Microsoft (MPSA).
    
- Il costo per importare i file PST nelle cassette postali di Office 365 tramite la distribuzione di unità è $2 USD per GB di dati. Ad esempio, se si spedisce un disco rigido che contiene 1.000 GB (1 TB) di file PST, il costo è $2.000 USD. You can work with a partner to pay the import fee. Per informazioni su come trovare un partner, vedere [Find Your Office 365 partner or Reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).
    
- L'utente o la relativa organizzazione deve disporre di un account FedEx o DHL. 
    
  - Le organizzazioni degli Stati Uniti, del Brasile e dell'Europa devono disporre di account FedEx.
    
  - Le organizzazioni dell'Asia orientale, del sud-est asiatico, del Giappone, della Repubblica di Corea e dell'Australia devono disporre di account DHL.
    
    Microsoft farà ricorso (e addebiterà le spese) a tali account per la restituzione delle unità disco rigido agli utenti. 
    
- L'unità disco rigido inviata a Microsoft potrebbe dover attraversare i confini nazionali. In tal caso, l'utente è tenuto ad accertarsi che l'unità disco rigido e i dati in essa contenuti vengano importati e/o esportati in conformità alle leggi applicabili. Prima dell'invio di un'unità disco rigido, verificare con i propri consulenti che sia legalmente possibile inviare l'unità e i dati al data center Microsoft identificato. Ciò contribuirà a garantire che i supporti raggiungano Microsoft in tempo utile.
    
- Questa procedura comporta la copia e il salvataggio di una chiave di archiviazione protetta e di una chiave di crittografia BitLocker. Adottare le dovute precauzioni per proteggere tali chiavi nello stesso modo in cui vengono protette password o altre informazioni di sicurezza. Ad esempio, potrebbe essere necessario salvarle in un documento di Microsoft Word protetto da password oppure su un'unità USB crittografata. Per un esempio di queste chiavi, vedere la sezione [ulteriori informazioni](#more-information) . 
    
- Dopo aver importato i file PST in una cassetta postale di Office 365, l'impostazione di conservazione per la cassetta postale è attivata per una durata indefinita. Questo significa che i criteri di conservazione assegnati alla cassetta postale non verranno elaborati fino a quando non si disattiva il blocco di conservazione o si imposta una data per disattivare il blocco. Perché eseguire questa operazione? Se i messaggi importati in una cassetta postale sono obsoleti, potrebbero essere eliminati definitivamente (eliminati) perché il periodo di conservazione è scaduto in base alle impostazioni di conservazione configurate per la cassetta postale. Se si posiziona la cassetta postale su conservazione, il proprietario della cassetta postale consentirà di gestire i messaggi appena importati o di modificare le impostazioni di conservazione per la cassetta postale. Vedere la sezione [ulteriori informazioni](#more-information) per suggerimenti sulla gestione del blocco di conservazione. 
    
- Per impostazione predefinita, le dimensioni massime dei messaggi che possono essere ricevute da una cassetta postale di Office 365 sono 35 MB. Ciò è dovuto al fatto che il valore predefinito per la proprietà *MaxReceiveSize* di una cassetta postale è impostato su 35 MB. Tuttavia, il limite per la dimensione massima di ricezione dei messaggi in Office 365 è 150 MB. Pertanto, se si importa un file PST che contiene un elemento di dimensioni superiori a 35 MB, il servizio di importazione di Office 365 modificherà automaticamente il valore della proprietà *MaxReceiveSize* nella cassetta postale di destinazione a 150 MB. In questo modo i messaggi fino a 150 MB verranno importati nelle cassette postali degli utenti. 
    
    > [!TIP]
    > Per identificare le dimensioni di ricezione dei messaggi per una cassetta postale, è possibile eseguire questo comando in PowerShell `Get-Mailbox <user mailbox> | FL MaxReceiveSize`di Exchange Online:. 
  
- È possibile importare i file PST in una cassetta postale inattiva in Office 365. A tale scopo, specificare il GUID della cassetta postale inattiva nel `Mailbox` parametro nel file di mapping di importazione PST. Per ulteriori informazioni, vedere [passaggio 3: creare il file di mapping di importazione PST](#step-3-create-the-pst-import-mapping-file) . 
    
- In una distribuzione ibrida di Exchange, è possibile importare i file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è in locale. A tale scopo, eseguire le operazioni seguenti nel file di mapping di importazione PST:
    
  - Specificare l'indirizzo di posta elettronica per la cassetta postale locale dell'utente nel `Mailbox` parametro. 
    
  - Specificare il valore **true** nel `IsArchive` parametro. 
    
    Per ulteriori informazioni, vedere [passaggio 3: creare il file di mapping di importazione PST](#step-3-create-the-pst-import-mapping-file) . 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>Passaggio 1: scaricare la chiave di archiviazione sicura e lo strumento di importazione PST

Il primo passaggio consiste nel scaricare la chiave di archiviazione sicura e lo strumento e che verrà utilizzato nel passaggio 2 per copiare i file PST nell'unità disco rigido.
  
> [!IMPORTANT]
> È necessario utilizzare Azure Import/Export Tool versione 1 (WAimportExportV1) per importare correttamente i file PST utilizzando il metodo di spedizione dell'unità. La versione 2 dello strumento di importazione/esportazione di Azure non è supportata e utilizzarla provocherà la preparazione erronea del disco rigido per il processo di importazione. Assicurarsi di scaricare lo strumento di importazione/esportazione di Azure dal centro sicurezza & conformità attenendosi alle procedure descritte in questo passaggio. 
  
1. Passare a [https://protection.office.com/](https://protection.office.com/) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro del Centro sicurezza & conformità fare clic su \> **importazione**di **governance dei dati** .
    
    > [!NOTE]
    > Come indicato in precedenza, è necessario assegnare le autorizzazioni appropriate per accedere alla pagina di **importazione** nel centro sicurezza & conformità. 
  
3. Nella pagina **Importa** , fare clic ![su Aggiungi](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
4. Nella procedura guidata di importazione digitare un nome per il processo di importazione PST e quindi fare clic su **Avanti**. Utilizzare lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **scegliere il tipo di processo di importazione** fare clic su **spedire unità disco rigido in una delle posizioni fisiche** e quindi fare clic su **Avanti**.
    
    ![Fare clic su spedire unità disco rigido in una delle nostre posizioni fisiche per creare un processo di importazione delle unità di spedizione](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Nella pagina **Importa dati** eseguire le due operazioni seguenti: 
    
    ![Copiare la chiave di archiviazione sicura e scaricare lo strumento di esportazione di importazione di Azure nella pagina Importa dati](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    un. Nel passaggio 2, fare clic su **copia la chiave di archiviazione sicura**. Dopo aver visualizzato il codice di archiviazione, fare clic su **copia negli Appunti** e quindi incollarlo e salvarlo in un file in modo che sia possibile accedervi in un secondo momento.
    
    b. Nel passaggio 3 **scaricare lo strumento di importazione/esportazione di Azure** per scaricare e installare lo strumento di importazione/esportazione di Azure (versione 1).
    
    - Nella finestra popup, fare clic su **Salva** \> con **nome** per salvare il file WaImportExportV1. zip in una cartella del computer locale. 
    
    - Estrarre il file WaImportExportV1. zip.
    
7. Fare clic su **Annulla** per chiudere la procedura guidata. 
    
    È possibile tornare alla pagina di **importazione** nel centro sicurezza & conformità quando si crea il processo di importazione nel passaggio 4. 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>Passaggio 2: copiare i file PST nell'unità disco rigido

Il passaggio successivo consiste nell'utilizzo dello strumento WAImportExport.exe per copiare i file PST nell'unità disco rigido. Questo strumento consente di crittografare l'unità disco rigido con BitLocker, copiare i file PST nell'unità disco rigido e creare un file journal in cui vengono archiviate le informazioni sulla procedura di copia. Per completare questo passaggio, è necessario che i file PST siano posizionati in una condivisione file o in un file server dell'organizzazione. In questa procedura, tale posizione viene definita anche come directory di origine. 
  
> [!IMPORTANT]
> Dopo aver eseguito lo strumento WAImportExport.exe per la prima volta per un'unità disco rigido, in futuro sarà necessario utilizzare una sintassi diversa ogni volta. Questa sintassi è illustrata nel passaggio 4 di questa procedura per copiare i file PST nell'unità disco rigido. 
  
1. Aprire un prompt dei comandi nel computer locale.
    
    > [!TIP]
    > Se si esegue il prompt dei comandi come amministratore (selezionando "Esegui come amministratore" al momento dell’apertura), verranno visualizzati dei messaggi di errore nella finestra del prompt dei comandi. Ciò consente di risolvere i problemi durante l'esecuzione dello strumento WAImportExport.exe. 
  
2. Accedere alla directory nella quale è stato installato lo strumento WAImportExport.exe durante il primo passaggio.
    
3. Eseguire il comando riportato di seguito la prima volta che si utilizza lo strumento WAImportExport.exe per copiare i file PST in un'unità disco rigido.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |Specifica il nome del file journal. Questo file viene salvato nella stessa cartella in cui si trova lo strumento WAImportExport.exe. È necessario che ogni unità disco rigido inviata a Microsoft disponga di un file journal. Ogni volta che si esegue lo strumento WAImportTool.exe per copiare i file PST in un'unità disco rigido, le informazioni verranno aggiunte al file journal per tale unità.  <br/> Il personale del Data Center Microsoft utilizzerà le informazioni contenute nel file del journal per associare l'unità disco rigido al processo di importazione creato nel passaggio 4 e per caricare i file PST nell'area di archiviazione di Azure nel cloud Microsoft.  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |Specifica la lettera di unità del disco rigido quando è connesso al computer locale.  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |Specifica il nome della sessione di copia. Per sessione si intende ogni singola esecuzione dello strumento WAImportExport.exe per copiare i file nell'unità disco rigido. I file PST vengono copiati in una cartella con il nome di sessione specificato da questo parametro.   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |Specifica la directory di origine dell'organizzazione contenente i file PST che verranno copiati durante la sessione. Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Specifica la directory di destinazione nell'area di archiviazione di Azure nel cloud Microsoft in cui verrà caricato il PST. È necessario utilizzare il valore `ingestiondata/`. Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> A scelta, è anche possibile aggiungere un percorso file aggiuntivo al valore di questo parametro. Ad esempio, è possibile utilizzare il percorso del file della directory di origine sul disco rigido (convertito in un formato URL), specificato nel `/srcdir:` parametro. Ad esempio, `\\FILESERVER01\PSTs` viene modificato in `FILESERVER01/PSTs`. In questo caso, è comunque necessario includere `ingestiondata` nel percorso del file. Pertanto, in questo esempio, il valore del `/dstdir:` parametro è `"ingestiondata/FILESERVER01/PSTs"`.  <br/> L'aggiunta di un ulteriore percorso file è motivata nel caso in cui si disponga di file PST con lo stesso nome file.  <br/> > [!NOTE]> se si include il percorso facoltativo, lo spazio dei nomi per un file PST dopo essere stato caricato nell'area di archiviazione di Azure includerà il percorso e il nome del file PST. ad esempio, `FILESERVER01/PSTs/annb.pst`. Se non si include un percorso, lo spazio dei nomi è solo il nome del file PST. ad esempio `annb.pst`.           | `/dstdir:"ingestiondata/"` <br/> Oppure  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |Specifica la chiave dell'account di archiviazione ottenuta nel passaggio 1. Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |Questa opzione attiva BitLocker per l'unità disco rigido. Il parametro è obbligatorio la prima volta che si esegue lo strumento WAImportExport.exe.  <br/> La chiave di crittografia BitLocker viene copiata nel file del journal e nel file di registro creato se si utilizza `/logfile:` il parametro. Come illustrato in precedenza, il file journal viene salvato nella stessa cartella in cui si trova lo strumento WAImportExport.exe.  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |Questo parametro facoltativo specifica una cartella in cui salvare i file di log. Se non specificato, i file di log vengono salvati nella stessa cartella in cui si trova lo strumento WAImportExport.exe. Racchiudere il valore di questo parametro tra virgolette doppie (" ").  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    Di seguito è riportato un esempio di sintassi dello strumento WAImportExport.exe nella quale vengono utilizzati i valori effettivi di ogni parametro:
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    Una volta eseguito il comando, i messaggi di stato visualizzati riportano informazioni sull'avanzamento della copia dei file PST nell'unità disco rigido. Nel messaggio finale viene riportato il numero complessivo di file che sono stati copiati. 
    
4. Eseguire questo comando ogni volta che verrà eseguito lo strumento WAImportExport.ext per copiare i file PST nella stessa unità disco rigido.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    Di seguito è riportato un esempio della sintassi necessaria per le sessioni successive per copiare i file PST nella stessa unità disco rigido.  

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>Passaggio 3: creare il file di mapping di importazione PST

Dopo che il personale dei Data Center di Microsoft ha caricato i file PST dall'unità disco rigido nell'area di archiviazione di Azure, il servizio di importazione utilizzerà le informazioni contenute nel file di mapping di importazione PST, che è un file CSV (comma separated value), che specifica quali cassette postali dell'utente PST i file verranno importati in. È necessario inviare il file CSV nel passaggio successivo a quello di creazione del processo di importazione PST.
  
1. [Scaricare una copia del file di mapping di importazione PST](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Aprire o salvare il file CSV nel computer locale. Nell'esempio seguente viene visualizzato un file di mapping di importazione PST completo (aperto nel Blocco note). È molto più facile usare Microsoft Excel per modificare il file CSV.

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    Nella prima riga o in quella dell'intestazione del file CSV vengono elencati i parametri che verranno usati dal servizio di importazione PST per importare i file PST nelle cassette postali dell'utente. Ogni nome di parametro è separato da una virgola. Ogni riga al di sotto di quella dell'intestazione riporta i valori del parametro per l’importazione di un file PST in una cassetta postale specifica. Sarà necessaria una riga per ciascun file PST copiato nell'unità disco rigido. Assicurarsi di sostituire i dati segnaposto nel file di mapping con i dati effettivi.

    > [!NOTE]
    > Non apportare modifiche nella riga di intestazione, compresi i parametri SharePoint. Questi verranno ignorati durante il processo di impostazione PST. 
  
3. Utilizzare le informazioni della tabella per popolare il file CSV con i dati necessari.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Specifica il servizio Office 365 in cui verranno importati i dati. Per importare i file PST nelle cassette postali `Exchange`degli utenti, utilizzare.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | Specifica il percorso della cartella nell'area di archiviazione di Azure in cui verranno copiati i file PST quando l'unità disco rigido viene spedita a Microsoft.  <br/>  Gli elementi aggiunti in questa colonna nel file CSV dipendono dall'elemento specificato per il `/dstdir:` parametro nel passaggio precedente. Se si dispone di sottocartelle nel percorso di origine, il valore del `FilePath` parametro deve contenere il percorso relativo per la sottocartella. ad esempio,/Folder1/User1/.  <br/>  Se è stato `/dstdir:"ingestiondata/"`utilizzato, lasciare vuoto questo parametro nel file CSV.  <br/>  Se è stato incluso un percorso facoltativo per il valore del `/dstdir:` parametro, ad esempio `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, utilizzare il nome del percorso (escluso "ingestiondata") per questo parametro nel file CSV. Il valore di questo parametro è distinzione tra maiuscole e minuscole.  <br/>  In entrambi i casi, *non* includere "ingestiondata" nel valore del `FilePath` parametro. Lasciare vuoto questo parametro oppure specificare solo il percorso facoltativo.  <br/> > [!IMPORTANT]> la distinzione tra maiuscole e minuscole per il nome del percorso del file deve essere `/dstdir:` lo stesso che è stato specificato nel parametro nel passaggio precedente. Ad esempio, se è stato `"ingestiondata/FILESERVER01/PSTs"` utilizzato per il nome della sottocartella nel passaggio precedente, ma viene `fileserver01/psts` utilizzato nel `FilePath` parametro nel file CSV, l'importazione per il file PST avrà esito negativo. Assicurarsi di utilizzare lo stesso caso in entrambe le istanze.           |(lasciare vuoto)  <br/> Oppure  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |Specifica il nome del file PST che verrà importato nella cassetta postale.  Il valore di questo parametro è distinzione tra maiuscole e minuscole.  <br/> > [!IMPORTANT]> il caso per il nome del file PST nel file CSV deve corrispondere al file PST caricato nel percorso di archiviazione di Azure nel passaggio 2. Ad esempio, se si utilizza `annb.pst` il `Name` parametro nel file CSV, ma il nome del file pst effettivo è `AnnB.pst`, l'importazione per il file PST avrà esito negativo. Assicurarsi che il nome del file PST nel documento CSV utilizzi lo stesso caso del file PST effettivo.           | `annb.pst` <br/> |
    | `Mailbox` <br/> |Specifica l'indirizzo di posta elettronica della cassetta postale nella quale verrà importato il file PST.  Non è possibile specificare una cartella pubblica perché il servizio di importazione PST non supporta l'importazione di file PST nelle cartelle pubbliche.  <br/> Per importare un file PST in una cassetta postale inattiva, è necessario specificare il GUID della cassetta postale per questo parametro. Per ottenere questo GUID, eseguire il seguente comando di PowerShell in Exchange Online:`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> in alcuni casi, è possibile disporre di più cassette postali con lo stesso indirizzo di posta elettronica, in cui una cassetta postale è una cassetta postale attiva e l'altra è in uno stato di eliminazione temporanea (o inattivo). In questi casi, è necessario specificare il GUID della cassetta postale per identificare in modo univoco la cassetta postale in cui importare il file PST. Per ottenere questo GUID per le cassette postali attive, eseguire il seguente `Get-Mailbox <identity of active mailbox> | FL Guid`comando di PowerShell:. Per ottenere il GUID per le cassette postali eliminate temporaneamente (o inattive), eseguire `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`il comando seguente:.           | `annb@contoso.onmicrosoft.com` <br/> Oppure  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Specifica se importare o meno il file PST nella cassetta postale di archiviazione dell'utente. Esistono due opzioni:  <br/> Valore **false** Importa il file PST nella cassetta postale principale dell'utente.  <br/> **Vero** Importa il file PST nella cassetta postale di archiviazione dell'utente. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). Se si imposta questo parametro su `TRUE` e la cassetta postale di archiviazione dell'utente non è abilitata, l'importazione per tale utente avrà esito negativo. Si noti che se un'importazione ha esito negativo per un utente (perché l'archivio non è abilitato e `TRUE`la proprietà è impostata su), gli altri utenti nel processo di importazione non saranno coinvolti.  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> **Nota:** Per importare un file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è in locale `TRUE` , specificare solo per questo parametro e specificare l'indirizzo di posta elettronica per la cassetta postale locale `Mailbox` dell'utente per il parametro.  <br/> | `FALSE` <br/> Oppure  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Specifica la cartella delle cassette postali a cui è stato importato il file PST.  <br/>  Se si omette questo parametro, il file PST verrà importato in una nuova cartella denominata **importata** che si trova a livello di radice della cassetta postale (allo stesso livello della cartella posta in arrivo e delle altre cartelle di cassette postali predefinite).  <br/>  Se si specifica `/`, gli elementi del file pst verranno importati direttamente nella cartella posta in arrivo dell'utente.  <br/>  Se si specifica `/<foldername>`, gli elementi del file pst verranno importati in una cartella denominata * \<FolderName\> * . Ad esempio, se si utilizza `/ImportedPst`, gli elementi verrebbero importati in una cartella denominata **ImportedPst**. Questa cartella si trova nella cassetta postale dell'utente allo stesso livello della cartella posta in arrivo.  <br/> |(lasciare vuoto)  <br/> Oppure  <br/>  `/` <br/> Oppure  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Questo parametro facoltativo consente di specificare un valore numerico per la tabella codici da utilizzare per l'importazione dei file PST nel formato di file ANSI. Questo parametro viene utilizzato per l'importazione di file PST dalle organizzazioni cinesi, giapponesi e coreane (CJK), in quanto generalmente utilizzano un set di caratteri a doppio byte (DBCS) per la codifica dei caratteri. Se questo parametro non viene utilizzato per importare i file PST per le lingue che utilizzano i caratteri DBCS per i nomi delle cartelle delle cassette postali, i nomi delle cartelle vengono spesso alterati dopo l'importazione.  <br/> Per un elenco dei valori supportati da utilizzare per questo parametro, vedere [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> > [!NOTE]> come indicato in precedenza, si tratta di un parametro facoltativo e non è necessario includerlo nel file CSV. In alternativa, è possibile includerla e lasciare il valore vuoto per una o più righe.           |(lasciare vuoto)  <br/> Oppure  <br/>  `932`(ovvero l'identificatore di tabella codici per ANSI/OEM giapponese)  <br/> |
    | `SPFileContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPManifestContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPSiteUrl` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>Passaggio 4: creare un processo di Importazione PST in Office 365

Il passaggio successivo consiste nel creare il processo di importazione PST nel servizio di importazione di Office 365. Come descritto in precedenza, verrà inviato il file di mapping di importazione PST creato al passaggio 3. Dopo aver creato il nuovo processo, il servizio di importazione utilizzerà le informazioni contenute nel file di mapping per importare i file PST nella cassetta postale utente specificata dopo che i file PST vengono copiati dall'unità disco rigido nell'area di archiviazione di Azure e si crea e si avvia il processo di importazione.
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro del Centro sicurezza & conformità fare clic su **governance dei dati** e quindi su **Importa**.
    
3. Nella pagina **Importa** , fare clic ![su Aggiungi](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
    > [!NOTE]
    > Come indicato in precedenza, è necessario assegnare le autorizzazioni appropriate per accedere alla pagina di **importazione** nel centro sicurezza & conformità. 
  
4. Digitare un nome per il processo di importazione PST e quindi fare clic su **Avanti**. Utilizzare lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **scegliere il tipo di processo di importazione** fare clic su **spedire unità disco rigido in una delle posizioni fisiche** e quindi fare clic su **Avanti**.
    
    ![Fare clic su spedire unità disco rigido in una delle nostre posizioni fisiche per creare un processo di importazione delle unità di spedizione](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Nel passaggio 6, fare clic sul pulsante i **' ho preparato i miei dischi rigidi e avere accesso ai file del Journal unità necessari** e **ho accesso alle caselle di controllo file di mapping** e quindi fare clic su **Avanti**.
    
    ![Fare clic sulle due caselle di controllo nel passaggio 6](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. Nella pagina **selezionare il file di unità** , fare clic su **Seleziona file di unità**, quindi passare alla stessa cartella in cui si trova lo strumento waimportexport. exe. Il file journal creato nel passaggio 2 è stato copiato in questa cartella.
    
    ![Fare clic su Seleziona file di unità per inviare il file del Journal creato quando è stato eseguito lo strumento WAImportExport. exe](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. Selezionare il file del journal. ad esempio, `PSTHDD1.jrn`.
    
    > [!TIP]
    > Quando è stato eseguito lo strumento WAImportExport. exe nel passaggio 2, il nome del file del journal è stato specificato `/j:` dal parametro. 
  
9. Dopo che il nome del file dell'unità è visualizzato in **nome file di unità**, fare clic su **convalida** per verificare se il file dell'unità ha avuto degli errori. 
    
    ![Fare clic su convalida per convalidare il file di unità selezionato](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    Il file di unità deve essere convalidato correttamente per creare un processo di importazione PST. Nota il nome del file viene modificato in verde dopo che è stato convalidato correttamente. Se la convalida ha esito negativo, fare clic sul collegamento **Visualizza log** . Viene aperta una segnalazione errori di convalida, con un messaggio di errore contenente informazioni sul motivo per cui il file non è riuscito. 
    
    > [!NOTE]
    > È necessario aggiungere e convalidare un file del journal per ogni disco rigido che si desidera inviare a Microsoft. 
  
10. Dopo aver aggiunto e convalidato un file del journal per ogni disco rigido da inviare a Microsoft, fare clic su **Avanti**.
    
11. Fare ![clic su](media/ITPro-EAC-AddIcon.gif) Aggiungi **file di mapping seleziona** icona per inviare il file di mapping di importazione PST creato nel passaggio 3. 
    
    ![Fare clic su Seleziona file di mapping per inviare il file CSV creato per il processo di importazione](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. Dopo che il nome del file CSV viene visualizzato in **mapping file name**, fare clic su **Validate** per controllare il file CSV per individuare eventuali errori. 
    
    ![Fare clic su convalida per controllare il file CSV per individuare eventuali errori](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Il file CSV deve essere convalidato per creare un processo di importazione PST. Nota il nome del file viene modificato in verde dopo che è stato convalidato correttamente. Se la convalida ha esito negativo, fare clic sul collegamento **Visualizza log** . Viene aperta una segnalazione errori di convalida, con un messaggio di errore per ogni riga del file che ha avuto esito negativo. 
    
13. Dopo aver convalidato il file di mapping PST, fare clic su **Avanti**.
    
14. Nella pagina **fornire le informazioni di contatto** , digitare le informazioni di contatto nelle caselle applicabili. 
    
    Tenere presente che viene visualizzato l'indirizzo del percorso Microsoft per il quale verranno spedite le unità disco rigido. Questo indirizzo viene generato automaticamente in base alla posizione del Data Center di Office 365. Copiare l’indirizzo in un file oppure eseguire una screenshot.
    
15. Leggere il documento termini e condizioni, fare clic sulla casella di controllo e quindi fare clic su **Salva** per inviare il processo di importazione. 
    
    Quando il processo di importazione viene creato correttamente, viene visualizzata una pagina di stato che spiega i passaggi successivi della procedura di spedizione dell'unità.
    
16. Nella pagina **Importa** , fare clic ![su Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) **icona Aggiorna** per visualizzare il nuovo processo di importazione delle unità di spedizione nell'elenco dei processi di importazione. Si noti che lo stato è impostato su **in attesa del numero di tracciabilità**. È inoltre possibile fare clic sul processo di importazione per visualizzare la pagina del riquadro a comparsa di stato, che contiene informazioni più dettagliate sul processo di importazione.
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>Passaggio 5: inviare l'unità disco rigido a Microsoft

Il passaggio successivo consiste nel spedire l'unità disco rigido a Microsoft e quindi fornire il numero di tracciabilità per la spedizione e restituire le informazioni relative alla spedizione per il processo di spedizione delle unità. Dopo che l'unità è stata ricevuta da Microsoft, saranno necessari tra 7 e 10 giorni lavorativi per il personale del Data Center per caricare i file PST nell'area di archiviazione di Azure per l'organizzazione.
  
> [!NOTE]
> Se non si fornisce il numero di tracciabilità e si restituiscono le informazioni sulla spedizione entro 14 giorni dalla creazione del processo di importazione, il processo di importazione verrà scaduto. In questo caso, sarà necessario creare un nuovo processo di importazione della spedizione delle unità (vedere il [passaggio 4: creare un processo di importazione PST in Office 365](#step-4-create-a-pst-import-job-in-office-365)) e inviare nuovamente il file di unità e il file di mapping di importazione PST. 
  
### <a name="ship-the-hard-drive"></a>Spedire l'unità disco rigido

Tenere presente quanto segue in fase di spedizione delle unità a Microsoft:
  
- Non inviare la scheda SATA a USB; è sufficiente spedire l'unità disco rigido.
    
- Assicurarsi che l'unità sia imballata correttamente, ad esempio, utilizzare una busta antistatica o pluriball.
    
- Utilizzare un corriere di propria scelta per spedire l'unità disco rigido a Microsoft.
    
- Spedire l'unità disco rigido all'indirizzo della sede Microsoft visualizzato quando è stato creato il processo di importazione al passaggio 4. Assicurarsi di includere "Office 365 Import Service" nell'indirizzo di spedizione.
    
- Dopo aver inviato l'unità disco rigido, verificare di aver scritto il nome del corriere e il numero di tracciabilità. Tali informazioni verranno fornite nel prossimo passaggio.
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>Immettere il numero di tracciabilità e altre informazioni sulla spedizione

Dopo aver inviato l'unità disco rigido a Microsoft, completare la procedura seguente nella pagina del servizio di importazione.
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro fare clic su **governance dei dati** e quindi fare clic su **Importa**.
    
3. Nella pagina **Importa** , fare clic sul processo per la spedizione dell'unità per la quale si desidera immettere il numero di tracciabilità. 
    
4. Nella pagina riquadro a comparsa stato, fare clic su **Immetti numero di tracciabilità**.
    
5. Fornire le seguenti informazioni sulla spedizione:
    
1. **Corriere di recapito** Digitare il nome del corriere utilizzato per spedire l'unità disco rigido a Microsoft. 
    
2. **Numero di tracciabilità** Digitare il numero di tracciabilità per la spedizione del disco rigido. 
    
3. **Numero dell'account del corriere restituito** Digitare il numero di conto dell'organizzazione per il vettore elencato in **return Carrier**. Microsoft farà ricorso (e addebiterà le spese) a tale account per la spedizione delle unità disco rigido agli utenti. È necessario che le organizzazioni negli Stati Uniti e in Europa dispongano di un account con FedEx. È necessario che le organizzazioni in Asia e nel resto del mondo dispongano di un account con DHL.
    
6. Fare clic su **Salva** per salvare queste informazioni per il processo di importazione. 
    
    Nella pagina **Importa** , fare clic ![su Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) **icona Aggiorna** per aggiornare le informazioni relative al processo di importazione delle unità di spedizione. Lo stato è ora impostato su **Unità in transito**.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Passaggio 6: filtrare i dati e avviare il processo di importazione PST

Dopo che l'unità disco rigido è stata ricevuta da Microsoft, lo stato del processo di importazione nella pagina **Importa** verrà modificato in **unità ricevute**. Il personale del Data Center utilizzerà le informazioni contenute nel file del journal per caricare i file PST nell'area di archiviazione di Azure per l'organizzazione. A questo punto, lo stato diventa **Importazione in corso**. Come indicato in precedenza, saranno necessari tra 7 e 10 giorni lavorativi dopo la ricezione del disco rigido per caricare i file PST.
  
Dopo aver caricato i file PST in Azure, lo stato viene modificato in **analisi in corso**. Ciò indica che Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) per identificare l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi e i dati sono pronti per l'importazione, lo stato del processo di importazione viene modificato in **analisi completata**. A questo punto, si ha la possibilità di importare tutti i dati contenuti nei file PST oppure è possibile tagliare i dati importati impostando filtri che controllano quali dati vengono importati.
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro fare clic su > **importazione**di **governance dei dati**.
    
3. Nella pagina **Importa** , fare clic su **pronto per l'importazione in Office 365** per il processo di importazione creato nel passaggio 4. 
    
    ![Fare clic su pronto per l'importazione in Office 365 accanto al processo di importazione creato](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Viene visualizzata una pagina di volo con informazioni sui file PST e altre informazioni sul processo di importazione.
    
4. Fare clic su **Importa in Office 365**.
    
5. Viene visualizzata la pagina filtro per i **dati** . Contiene i dati relativi alle informazioni risultanti dall'analisi eseguita sui file PST da Office 365, incluse quelle relative all'età dei dati. A questo punto, si ha la possibilità di filtrare i dati che verranno importati o importare tutti i dati così come sono. 
    
    ![È possibile tagliare i dati nei file PST o importarli tutti](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. Eseguire una delle operazioni seguenti:
    
    un. Per tagliare i dati importati, fare clic su **Sì, voglio filtrarlo prima**di eseguire l'importazione.
    
    Per istruzioni dettagliate su come filtrare i dati nei file PST e avviare il processo di importazione, vedere [filtrare i dati quando si importano i file PST in Office 365](filter-data-when-importing-pst-files.md).
    
    Oppure
    
    b. Per importare tutti i dati nei file PST, fare clic su **No, voglio importare tutto** e fare clic su **Avanti**.
    
7. Se si è scelto di importare tutti i dati, fare clic su **Importa dati** per avviare il processo di importazione. 
    
    Lo stato del processo di importazione viene visualizzato nella pagina **Importa** . Fare ![](media/O365-MDM-Policy-RefreshIcon.gif) **clic su Aggiorna icona Aggiorna** per aggiornare le informazioni sullo stato visualizzate nella colonna **stato** . Fare clic sul processo di importazione per visualizzare la pagina del riquadro a comparsa di stato, in cui vengono visualizzate le informazioni sullo stato di ogni file PST da importare. Quando l'importazione viene completata e i file PST sono stati importati nelle cassette postali utente, lo stato diventa **Completato**.

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Visualizzare un elenco dei file PST caricati in Office 365

Per visualizzare l'elenco dei file PST caricati (dal personale di Microsoft Data Center) nell'area di archiviazione di Azure per l'organizzazione, è possibile installare e utilizzare Microsoft Azure Storage Explorer (uno strumento gratuito open source). È possibile eseguire questa operazione per verificare che i file PST dei dischi rigidi inviati a Microsoft siano stati caricati correttamente nell'area di archiviazione di Azure.
  
Microsoft Azure Storage Explorer è in anteprima.
  
 **Importante:** Non è possibile utilizzare l'esploratore di archiviazione di Azure per caricare o modificare i file PST. L'unico metodo supportato per l'importazione di file PST in Office 365 è l'utilizzo di AzCopy. Inoltre, non è possibile eliminare i file PST caricati nel BLOB di Azure. Se si tenta di eliminare un file PST, si riceve un errore relativo all'assenza delle autorizzazioni necessarie. Tenere presente che tutti i file PST vengono eliminati automaticamente dall'area di archiviazione di Azure. Se non sono presenti processi di importazione in corso, tutti i file PST nel contenitore * * ingestiondata * * vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente. 
  
Per installare Azure Storage Explorer e connettersi all'area di archiviazione di Azure:
  
1. Eseguire la procedura seguente per ottenere l'URL della firma di accesso condiviso (SAS) per l'organizzazione. Questo URL è una combinazione dell'URL di rete per la posizione di archiviazione di Azure nel cloud Microsoft per l'organizzazione e una chiave SAS. Questa chiave fornisce le autorizzazioni necessarie per accedere alla posizione di archiviazione di Azure dell'organizzazione.
    
1. Passare a [https://protection.office.com/](https://protection.office.com/) e accedere con le credenziali di un account amministratore nell'organizzazione di Office 365. 
    
2. Nel riquadro sinistro del Centro sicurezza & conformità fare clic su \> **importazione**di **governance dei dati** .
    
3. Nella pagina **Importa** , fare clic ![su Aggiungi](media/ITPro-EAC-AddIcon.gif) **nuovo processo di importazione**.
    
4. Nella procedura guidata di importazione digitare un nome per il processo di importazione PST e quindi fare clic su **Avanti**. Utilizzare lettere minuscole, numeri, trattini e caratteri di sottolineatura. Non è possibile utilizzare lettere maiuscole o includere spazi nel nome.
    
5. Nella pagina **scegliere il tipo di processo di importazione** fare clic su **carica i dati** e quindi su **Avanti**.
    
6. Nel passaggio 2, fare clic su **Mostra URL SAS caricamento di rete**.
    
7. Dopo aver visualizzato l'URL, copiarlo e salvarlo in un file. Assicurarsi di copiare l'URL completo.
    
    > [!IMPORTANT]
    > Assicurarsi di prendere precauzioni per proteggere l'URL SAS. Questo può essere utilizzato da chiunque per accedere all'area di archiviazione di Azure per l'organizzazione. 
  
8. Fare clic su **Annulla** per chiudere la procedura guidata di importazione. 
    
2. Scaricare e installare lo [strumento Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
3. Avviare Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **account di archiviazione** nel riquadro sinistro, quindi fare clic su **Connetti a spazio di archiviazione di Azure**.
    
    ![Fare clic con il pulsante destro del mouse su account di archiviazione e quindi scegliere Connetti a archiviazione](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. Fare clic su **Usa una stringa di connessione o un URI di accesso condiviso** e fare clic su **Avanti**.
    
5. Fare clic su **Usa un URI SAS**, incollare l'URL SAS ottenuto nel passaggio 1 nella casella in **URI**, quindi fare clic su **Avanti**.
    
6. Nella pagina **Riepilogo connessione** è possibile esaminare le informazioni sulla connessione e quindi fare clic su **Connetti**.
    
    Il contenitore **ingestiondata** viene aperto. contiene i file PST dall'unità disco rigido. Il contenitore di **ingestiondata** si trova in **contenitori BLOB**degli **account** \> di archiviazione **(SAS-Attached Services)** \> .
    
    ![Esplora archivi di Azure mostra un elenco di file con estensione PST caricati](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. Al termine dell'utilizzo di Microsoft Azure Storage Explorer, fare clic con il pulsante destro del mouse su **ingestiondata**e quindi scegliere Disconnetti per disconnettersi dall' **area di archiviazione** di Azure. In caso contrario, verrà visualizzato un errore al successivo tentativo di associazione. 
    
    ![Fare clic con il pulsante destro del mouse sull’inserimento e su Disconnetti per disconnettersi dall'area di archiviazione Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a>Suggerimenti per la risoluzione dei problemi
<a name="troubleshootingtips"> </a>

- **Cosa succede se il processo di importazione ha esito negativo a causa di errori nel file di mapping CSV di importazione PST?** Se un processo di importazione ha esito negativo a causa di errori nel file di mapping, non è necessario rispedire l'unità disco rigido a Microsoft per creare un nuovo processo di importazione. Ciò è dovuto al fatto che i file PST del disco rigido inviato per il processo di importazione delle unità di spedizione sono già stati caricati nell'area di archiviazione di Azure per l'organizzazione. In questo caso, è sufficiente correggere gli errori nel file di mapping CSV Import PST e quindi creare un nuovo processo di importazione "caricamento di rete" e inviare il file di mapping CSV riveduto. Per creare e avviare un nuovo processo di importazione del caricamento di rete, vedere [passaggio 5: creare un processo di importazione PST in office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) e [passaggio 6: filtrare i dati e avviare il processo di importazione PST](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) nell'argomento "usare il caricamento di rete per importare i file PST in Office 365". 
    
    > [!NOTE]
    > Per risolvere i problemi relativi al file di mapping CSV di importazione PST, utilizzare lo strumento [Esplora risorse di Azure](#view-a-list-of-the-pst-files-uploaded-to-office-365) per visualizzare la struttura delle cartelle nel contenitore **ingestiondata** per i file PST dall'unità disco rigido che sono stati caricati nell'area di archiviazione di Azure. Gli errori dei file di mapping in genere sono causati da un valore non corretto nel parametro FilePath. Questo parametro consente di specificare il percorso di un file PST nell'area di archiviazione di Azure. Per ulteriori informazioni, vedere la descrizione del parametro FilePath nella tabella del [passaggio 3](#step-3-create-the-pst-import-mapping-file). Come spiegato in precedenza, il percorso dei file PST nell'area di archiviazione di Azure è stato `/dstdir:` specificato dal parametro quando è stato eseguito lo strumento waimportexport. exe nel [passaggio 2](#step-2-copy-the-pst-files-to-the-hard-drive). 
  

  
## <a name="more-information"></a>Ulteriori informazioni

- La distribuzione di unità è un modo efficace per importare grandi quantità di dati di messaggistica di archiviazione in Office 365 per sfruttare le funzionalità di conformità disponibili per l'organizzazione. Dopo aver importato i dati di archiviazione nelle cassette postali degli utenti, è possibile:
    
  - Abilitare le [cassette postali](enable-archive-mailboxes.md) di archiviazione e l' [archiviazione automatica](enable-unlimited-archiving.md) per consentire agli utenti un ulteriore spazio di archiviazione delle cassette postali per i dati. 
    
  - Posizionare le cassette postali sul [blocco per controversia legale](https://go.microsoft.com/fwlink/?linkid=856286) per conservare i dati. 
    
  - Utilizzare [gli strumenti](search-for-content.md) di Microsoft eDiscovery per cercare i dati. 
    
  - Applicare i [criteri di conservazione di Office 365](retention-policies.md) per controllare la durata di conservazione dei dati e l'azione da intraprendere dopo la scadenza del periodo di mantenimento. 
    
  - Eseguire una ricerca nel [Registro di controllo di Office 365](search-the-audit-log-in-security-and-compliance.md) per gli eventi relativi a questi dati. 
    
  - Importare i dati in [cassette postali inattive](create-and-manage-inactive-mailboxes.md) per archiviare i dati ai fini della conformità. 
    
  - Proteggere l'organizzazione dalla [perdita di dati](data-loss-prevention-policies.md) di informazioni riservate. 
    
- Di seguito viene riportato un esempio di una chiave dell'account di archiviazione protetta e una chiave di crittografia BitLocker. In questo esempio è riportata la sintassi per il comando WAImportExport.exe da eseguire per copiare i file PST in un'unità disco rigido. Adottare le dovute precauzioni per proteggere tali file nello stesso in modo in cui vengono protette password o altre informazioni di sicurezza.
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```
   
- Come spiegato in precedenza, il servizio di importazione di Office 365 attiva l'impostazione di conservazione (per una durata indefinita) dopo l'importazione dei file PST in una cassetta postale. Questo significa che la proprietà *RentionHoldEnabled* è impostata `True` in modo che il criterio di conservazione assegnato alla cassetta postale non venga elaborato. In questo modo il proprietario della cassetta postale è in grado di gestire i messaggi appena importati impedendo l'eliminazione o l'archiviazione dei messaggi meno recenti. Di seguito sono riportati alcuni passaggi che è possibile eseguire per gestire questo blocco di conservazione: 
    
  - Dopo un determinato periodo di tempo, è possibile disattivare il blocco di conservazione eseguendo il `Set-Mailbox -RetentionHoldEnabled $false` comando. Per le istruzioni, vedere [posizionare una cassetta postale sul blocco di conservazione](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - È possibile configurare il blocco di conservazione in modo che sia disattivata in futuro. A tale scopo, eseguire il `Set-Mailbox -EndDateForRetentionHold <date>` comando. Ad esempio, presupponendo che la data odierna sia il 1 ° giugno 2016 e che si desideri disattivare il blocco di conservazione in 30 giorni, è necessario `Set-Mailbox -EndDateForRetentionHold 7/1/2016`eseguire il comando seguente:. In questo scenario, si lascerà la proprietà *RentionHoldEnabled* impostata su *true*. Per ulteriori informazioni, vedere [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - È possibile modificare le impostazioni per i criteri di conservazione assegnati alla cassetta postale, in modo che gli elementi meno recenti importati non vengano immediatamente eliminati o spostati nella cassetta postale di archiviazione dell'utente. Ad esempio, è possibile estendere l'età di conservazione per un criterio di eliminazione o di archiviazione assegnato alla cassetta postale. In questo scenario, è necessario disattivare il blocco di conservazione sulla cassetta postale dopo aver modificato le impostazioni del criterio di conservazione. Per ulteriori informazioni, vedere [configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione di Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    

  

