---
title: Usare lo strumento Raccolta PST per trovare, copiare ed eliminare i file PST
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Utilizzare lo strumento di raccolta PST di Microsoft per cercare la rete dell'organizzazione per ottenere un inventario dei file PST sparsi nell'organizzazione. Dopo aver trovato i file PST, è possibile utilizzare lo strumento di raccolta PST per copiarli in una posizione centrale in modo da poterli importare in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d388eb9cfe0a894e5ae5eed89e5d4ed35a79a1fc
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224487"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>Utilizzare lo strumento di raccolta PST per trovare, copiare ed eliminare i file PST nell'organizzazione

> [!IMPORTANT]
> Lo strumento di raccolta PST descritto in questo articolo non è supportato in alcun servizio o programma di supporto Microsoft standard. Lo strumento viene fornito come senza garanzie di alcun tipo. Inoltre Microsoft declina ogni responsabilità su garanzie implicite, senza alcuna limitazione, incluse le garanzie implicite di commerciabilità e/o adeguatezza per uno scopo specifico. L'intero rischio derivante dall'utilizzo o dalle prestazioni dello strumento e della documentazione rimane invariato. In nessun caso Microsoft, i suoi autori o chiunque altro sia coinvolto nella creazione, la produzione o la consegna dello strumento è responsabile per eventuali danni (compresi, senza limitazione, danni per perdita di profitti aziendali, interruzioni aziendali, perdita di informazioni aziendali o altre perdite pecuniarie) derivanti dall'utilizzo o dall'impossibilità di utilizzare lo strumento o la documentazione, anche se Microsoft è stato informato della possibilità di tali danni.

È possibile utilizzare lo strumento di raccolta PST di Microsoft per cercare la rete dell'organizzazione per i file PST. Lo strumento consente di ottenere un inventario dei file PST sparsi nell'organizzazione. Dopo aver trovato i file PST, è possibile utilizzare lo strumento di raccolta PST per copiarli in una posizione centrale. L'utilizzo di PST in un'unica posizione consente di importarli nelle cassette postali di Exchange Online (o in una singola cassetta postale di Exchange Online), in cui è possibile applicare il set completo di funzionalità di conformità in Office 365. Ciò include l'importazione di PST in cassette postali di archiviazione degli utenti, la ricerca di messaggi specifici nei file PST importati tramite gli strumenti di ricerca di eDiscovery, la conservazione dei messaggi tramite eDiscovery e i criteri di conservazione e la gestione del ciclo di vita di questi messaggi utilizzando le funzionalità di gestione dei record di messaggistica in Exchange Online. Quando si è certi che i file PST raccolti siano stati importati correttamente in Office 365, è possibile utilizzare lo strumento per eliminarli dal percorso originale della rete. 
  
Un'altra operazione che è possibile eseguire con lo strumento di raccolta PST è impedire agli utenti di creare nuovi file PST e modificare i file PST esistenti che si trovano nella rete. Queste funzionalità "bloccate" consentono di trovare, raccogliere e importare un insieme noto di file PST in Microsoft 365 e impedire la proliferazione futura dei file PST nell'organizzazione. 
  
## <a name="how-the-pst-collection-tool-works"></a>Come funziona lo strumento di raccolta PST

Ecco una breve panoramica del processo di utilizzo dello strumento di raccolta PST per trovare, controllare, raccogliere ed eliminare i file PST nell'organizzazione.
  
![Panoramica del processo dello strumento di raccolta PST](../media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[Passaggio 1: trovare i file PST sulla rete](#step-1-find-pst-files-on-your-network)** : quando si esegue lo strumento per trovare i file PST, è necessario specificare un percorso, ad esempio un'unità organizzativa che contiene oggetti di Active Directory per i computer client e server. È inoltre possibile cercare specifiche macchine o condivisioni file di rete. Quando si esegue lo strumento, un agente di raccolta "Lightweight" viene installato nei computer di destinazione. Questo agente Cerca nel computer di destinazione i file PST e quindi invia informazioni allo strumento di raccolta PST su qualsiasi file PST trovato. Lo strumento consente di creare file di registro che contengono informazioni sui file PST trovati nei percorsi specificati. Questi file vengono utilizzati quando si esegue lo strumento nei passaggi successivi. 
    
2. **[(Facoltativo) passaggio 2: controllare l'accesso ai file PST](#optional-step-2-control-access-to-pst-files)** -lo strumento crea un oggetto Criteri di gruppo con impostazioni che impediscono agli utenti di creare o modificare i file PST. Questo oggetto Criteri di gruppo viene applicato a tutti gli utenti del dominio. Questo passaggio facoltativo consente di "bloccare" i file PST che sono stati individuati nel passaggio 1, in modo da poterli raccogliere, importare ed eliminare senza che siano stati creati nuovi file PST o che siano stati modificati i file PST esistenti. 
    
3. **[Passaggio 3: copiare i file PST in una posizione di raccolta](#step-3-copy-the-pst-files-to-a-collection-location)** -consente di raccogliere i file PST in una posizione tale da poterli importare nelle cassette postali di Exchange Online utilizzando il servizio di importazione di Office 365 nel passaggio 4. Quando si esegue lo strumento nella modalità "raccolta", ogni agente di raccolta copia i file PST dal computer di destinazione in cui è installato l'agente nel percorso di raccolta. 
    
4. **[Passaggio 4: importare i file PST in Office 365](#step-4-import-the-pst-files-to-office-365)** -dopo aver copiato i file PST in un'unica posizione, è possibile importarli nelle cassette postali di Exchange Online. 
    
5. **[Passaggio 5: eliminare i file PST trovati nella rete](#step-5-delete-the-pst-files-found-on-your-network)** -dopo che i file PST trovati e raccolti sono stati importati nelle cassette postali di Exchange online in Office 365, è possibile utilizzare lo strumento di raccolta PST per eliminare i file PST dai percorsi originali in cui sono stati trovati nel passaggio 1. 

## <a name="before-you-begin"></a>Informazioni preliminari

- Eseguire la procedura seguente per scaricare lo strumento di raccolta PST nel computer locale. 
    
    1. [Scaricare lo strumento di raccolta PST](https://aka.ms/pstcollectiontool).
    
    2. Nella finestra popup, fare clic su **Salva** con \> **nome** per salvare il file PSTCollectionTool. zip in una cartella del computer locale. 
    
    3. Estrarre il file PSTCollectionTool. zip in una cartella del computer locale. il nome predefinito della cartella è PSTCollectionTool.
    
- Per eseguire lo strumento di raccolta PST in qualsiasi modalità (trova, blocca, copia o Elimina), è necessario essere membri del gruppo Domain Administrators nel dominio di Active Directory. 

## <a name="step-1-find-pst-files-on-your-network"></a>Passaggio 1: trovare i file PST sulla rete

Il primo passaggio consiste nell'eseguire lo strumento di raccolta PST per trovare i file PST nell'organizzazione. È possibile utilizzare lo strumento per eseguire ricerche nei seguenti tipi di percorsi. 
  
- Unità organizzative (OU) in un dominio di Active Directory locale. Lo strumento Cerca tutti i computer contenuti nell'unità organizzativa specificata. 
    
- Computer client e server. Lo strumento esegue la ricerca nei computer specificati. 
    
- Condivisioni file di rete. Lo strumento esegue la ricerca nelle condivisioni file di rete specificate. 
    
Per `Locations` esempi di sintassi da utilizzare per ognuno di questi tipi di percorso, vedere la descrizione del parametro nella tabella seguente. 
  
> [!IMPORTANT]
> È necessario eseguire lo strumento di raccolta PST nella modalità trova prima di poter eseguire altre operazioni, ad esempio il blocco, la raccolta o l'eliminazione di file PST. 
  
1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla cartella PSTCollectionTool (o alla cartella in cui è stato estratto il file PSTCollectionTool. zip).
    
3. Passare alla directory DataCollectorMaster
    
4. Eseguire il seguente comando per trovare i file PST in un percorso specificato.
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    Nella tabella seguente vengono descritti i parametri e i valori necessari quando si esegue il comando DataCollectorMaster. exe per trovare i file PST. 
    
    |Parametro * * * *|****Descrizione****|Esempi * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento di raccolta PST per cercare i file PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione che verrà eseguito dallo strumento. Utilizzare il valore `Find` per individuare i file pst nei percorsi specificati. Si noti che lo strumento può trovare e ottenere informazioni sui file PST che sono aperti nei file di Outlook e PST che sono connessi ai profili di Outlook.  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |Specifica il nome del processo di raccolta PST. Si utilizzerà questo stesso nome del processo quando si esegue lo strumento di raccolta PST per bloccare, raccogliere ed eliminare i file PST che si trovano quando si esegue lo strumento per trovare i file PST. Il nome del processo verrà aggiunto anche ai nomi dei file di configurazione e di registro.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | Specifica una o più posizioni per la ricerca dei file PST. Se si specifica più di una posizione, utilizzare un punto e virgola (;) per separare singoli percorsi. Tenere presente che i singoli valori di questo parametro sono racchiusi tra virgolette doppie ("").  <br/><br/>   Di seguito è indicato il formato del valore di identità necessario per i tipi di percorsi che è possibile cercare.  <br/><br/>        **Unità organizzative** : utilizzare il nome distinto (DN) per identificare le unità organizzative. Per esempio:`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> non è possibile specificare il contenitore dei computer incorporati (ad esempio, CN = Computers, DC = contoso, DC = com ") perché non è un'unità organizzativa.<br/> <br/> **Macchine** : utilizzare il DN o il nome di dominio completo (FQDN) per identificare i computer client e server della rete. Per esempio:  <br/>  DN`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  Oppure  <br/>  FQDN`"FILESERVER01.contoso.com"` <br/><br/>  **Condivisioni file di rete** -utilizzare un nome UNC per identificare le condivisioni di file di rete; Per esempio`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |Specifica la cartella in cui verranno copiati i file di registro. Se la cartella non esiste, verrà creata durante l'esecuzione dello strumento.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |Specifica la cartella in cui verrà copiato il file di configurazione. XML. Questo file contiene informazioni su ogni file PST individuato quando si esegue lo strumento. Questo file verrà utilizzato quando si esegue lo strumento nel passaggio 3 per copiare i file PST trovati.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |Questo parametro facoltativo consente di specificare le posizioni da ignorare durante un'operazione di ricerca. È possibile escludere specifiche unità organizzative, computer e condivisioni file di rete. Ad esempio, è possibile escludere i computer, come il computer configurato come SQL Server (o altri tipi di server applicazioni), a cui gli utenti non hanno accesso. Se si specifica più di una posizione da escludere, utilizzare un punto e virgola (;) per separare singoli percorsi. Tenere presente che i singoli valori di questo parametro sono racchiusi tra virgolette doppie ("").  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |Questa opzione opzionale consente di eseguire lo strumento nella modalità di ricerca per un processo di raccolta PST esistente. Quando si utilizza l' `ForceRestart` opzione, i risultati dell'operazione di ricerca precedente per il processo verranno eliminati e lo strumento analizzerà di nuovo i percorsi specificati e creerà nuovi file di configurazione e di registro.  <br/> | `-ForceRestart` <br/> |
   
    Di seguito è riportato un esempio della sintassi per il comando DataCollectorMaster. exe che utilizza i valori effettivi per ogni parametro:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    Dopo aver eseguito il comando, vengono visualizzati messaggi di stato dettagliati che mostrano lo stato di avanzamento della ricerca dei file PST nei percorsi specificati. Dopo un po', un messaggio di stato finale Visualizza il numero totale di file PST che sono stati trovati, se il processo è stato completato e se sono stati riscontrati errori. Gli stessi messaggi di stato vengono copiati nel file. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>Risultati dell'esecuzione di DataCollectorMaster. exe nella modalità di ricerca

Dopo aver eseguito correttamente lo strumento di raccolta PST la modalità di ricerca, i file seguenti vengono creati e archiviati nelle cartelle specificate dai `LogLocation` `ConfigurationLocation` parametri e. 
  
- ** \< JobName \> _Find_ \< DateTimeStamp \> . log** : il file di log contiene i messaggi di stato che sono stati visualizzati. Questo file viene creato nella cartella specificata dal `LogLocation` parametro. 
    
- ** \< JobName \> _Find_ \< DATETIMESTAMP \> . csv** : il file CSV contiene una riga per ogni file PST trovato. Le informazioni per ogni PST includono il computer in cui è stato trovato il file PST, il percorso completo del file PST, il proprietario del file PST e la dimensione (in kilobyte, KB) del file PST. Questo file viene creato nella cartella specificata dal `LogLocation` parametro. 
    
    > [!TIP]
    > Utilizzare lo strumento Somma automatica in Excel per calcolare la dimensione totale (in KB) di tutti i file PST elencati nel file CSV. È quindi possibile utilizzare un calcolatore di conversione per convertire le dimensioni totali in megabyte (MB) o gigabyte (GB). 
  
- ** \< JobName \> _Find_ \< DATETIMESTAMP \> . XML** -il file XML contiene informazioni sui valori dei parametri utilizzati per l'esecuzione dello strumento nella modalità di ricerca. Questo file contiene anche informazioni su ogni file PST trovato. I dati contenuti in questo file vengono utilizzati quando si esegue di nuovo lo strumento per bloccare, raccogliere o eliminare i file PST che sono stati trovati. Questo file viene creato nella cartella specificata dal `ConfigurationLocation` parametro. 
    
    > [!IMPORTANT]
    > Non rinominare, modificare o spostare questo file. Viene utilizzato dallo strumento di raccolta PST quando si riesegue lo strumento nella modalità blocca, copia o Elimina per lo stesso processo. 

## <a name="optional-step-2-control-access-to-pst-files"></a>Optional Passaggio 2: controllare l'accesso ai file PST

Questo passaggio facoltativo consente di "bloccare" i file PST che sono stati individuati nel passaggio 1 in modo da poter raccogliere e importare un insieme noto di file PST in Office 365. Quando si esegue lo strumento di raccolta PST nella modalità blocca, si verificano le operazioni seguenti: 
  
- Lo strumento crea un oggetto Criteri di gruppo (GPO) denominato *controlli di utilizzo PST* . Questo oggetto Criteri di gruppo è collegato al dominio e si applica a tutti gli utenti autenticati nell'organizzazione. 
    
- L'oggetto Criteri di gruppo dei controlli di utilizzo PST crea le impostazioni del registro di sistema nei computer dell'organizzazione. A seconda del parametro utilizzato, è possibile creare un'impostazione del registro di sistema per impedire agli utenti di creare nuovi file PST e un'impostazione del registro di sistema che impedisca agli utenti di modificare i file PST esistenti.
    
> [!NOTE]
> Se il controllo dell'accesso ai file PST è troppo dirompente per l'organizzazione, è consigliabile ignorare questo passaggio ed eseguire il passaggio 3 per copiare i file PST in una posizione centrale. È quindi possibile ripetere il passaggio 1 per lo stesso processo (utilizzando il `ForceRestart` parametro) per trovare ulteriori file di PST creati dopo la copia dei file di PST nel percorso dell'insieme. Se vengono trovati nuovi file PST, è possibile copiarli nel percorso dell'insieme. Quando si utilizza il `ForceRestart` parametro quando si esegue di nuovo lo strumento nella modalità di ricerca, i risultati dell'operazione di ricerca precedente per un processo verranno eliminati e lo strumento analizzerà di nuovo i percorsi specificati. 

Per bloccare l'accesso ai file PST:

1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla directory in cui è stato scaricato lo strumento di raccolta PST.
    
3. Eseguire il seguente comando per bloccare l'accesso ai file PST trovati nel passaggio 1.

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    Nella tabella seguente vengono descritti i parametri e i valori necessari quando si esegue il comando DataCollectorMaster. exe per bloccare la creazione e la modifica dei file PST. 
    
    |Parametro * * * *|****Descrizione****|Esempi * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento di raccolta PST per cercare i file PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione che verrà eseguito dallo strumento. Utilizzare il valore `Block` per impedire agli utenti di creare nuovi file PST e apportare modifiche ai file PST esistenti.  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |Specifica il nome di un processo di raccolta PST esistente. È necessario utilizzare lo stesso nome del processo utilizzato per l'esecuzione dello strumento nella modalità di ricerca nel passaggio 1. Il nome del processo viene inoltre aggiunto al nome del file di registro creato quando si esegue lo strumento in modalità di blocco.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Specifica che la cartella contiene il file di configurazione XML creato quando è stato eseguito lo strumento nella modalità di ricerca. Utilizzare lo stesso valore utilizzato per questo parametro nel passaggio 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Specifica la cartella in cui verrà copiato il file di registro per l'operazione di blocco. Si tratta di un parametro facoltativo. Se non è incluso, il file di registro viene copiato nella cartella in cui è stato scaricato lo strumento di raccolta PST. È consigliabile utilizzare la stessa posizione del log utilizzata per l'esecuzione dello strumento nella modalità di ricerca nel passaggio 1, in modo che tutti i file di registro vengano salvati nella stessa cartella.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |Utilizzare questa opzione per impedire agli utenti di modificare un file PST. Quando si utilizza questa opzione, viene creata la voce del registro di sistema seguente: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` e il valore dei dati è impostato su 1. Questa impostazione del registro di sistema viene creata nei computer dell'organizzazione dall'oggetto Criteri di gruppo creato quando si esegue lo strumento di raccolta PST in modalità di blocco.  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |Utilizzare questa opzione per impedire agli utenti di creare nuovi file PST, aprire e importare file PST in Outlook ed esportare i file PST da Outlook. Quando si utilizza questa opzione, viene creata la voce del registro di sistema seguente: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` e il valore dei dati è impostato su 1. Questa impostazione del registro di sistema viene creata nei computer dell'organizzazione dall'oggetto Criteri di gruppo creato quando si esegue lo strumento di raccolta PST in modalità di blocco.  <br/> | `-BlockNewFiles` <br/> |
   
    Di seguito è riportato un esempio della sintassi per il comando DataCollectorMaster. exe che utilizza i valori effettivi per ogni parametro:

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```

    Viene richiesto di confermare che si desidera bloccare nuovi file PST o modifiche ai file PST esistenti. Dopo aver verificato che si desidera continuare e che il comando venga eseguito correttamente, viene visualizzato un messaggio in cui viene indicato che è stato creato un nuovo oggetto Criteri di gruppo denominato "PST Usage Controls".
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>Passaggio 3: copiare i file PST in una posizione di raccolta

Il passaggio successivo consiste nel copiare i file PST che sono stati trovati quando è stato eseguito lo strumento di raccolta PST nella modalità trova. In questo modo è possibile raccogliere i file PST in un'unica posizione per poterli importare in un secondo momento in Office 365. Prima di copiare i file PST in una posizione di raccolta, valutare la possibilità di determinare la quantità totale di spazio di archiviazione necessario. È possibile eseguire questa operazione utilizzando il file CSV creato nel passaggio 1 per calcolare la dimensione totale di tutti i file PST.
  
> [!NOTE]
> Dopo aver importato i file PST in Microsoft 365 e averli eliminati dal percorso originale, è possibile eliminarli dalla posizione dell'insieme in cui sono stati copiati in questo passaggio. 
  
1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla directory in cui è stato scaricato lo strumento di raccolta PST.
    
3. Eseguire il seguente comando per copiare i file PST in un percorso specificato.
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    Nella tabella seguente vengono descritti i parametri e i valori necessari quando si esegue il comando DataCollectorMaster. exe per copiare i file PST. 
    
    |Parametro * * * *|****Descrizione****|Esempi * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento di raccolta PST per cercare i file PST.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione che verrà eseguito dallo strumento. Utilizzare il valore `Collect` per copiare i file PST che sono stati trovati quando è stato eseguito lo strumento nella modalità di ricerca. Si noti che lo strumento è in grado di copiare i file PST che sono aperti in Outlook e copiare i file PST che sono connessi ai profili di Outlook.  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |Specifica il nome di un processo di raccolta PST esistente. È necessario utilizzare lo stesso nome del processo utilizzato per l'esecuzione dello strumento nella modalità di ricerca nel passaggio 1. Il nome del processo viene inoltre aggiunto al nome del file di registro creato quando si esegue lo strumento nella modalità raccolta.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |Utilizzare lo stesso valore utilizzato per il `Locations` parametro nel passaggio 1. Se si desidera rieseguire lo strumento per eliminare i file PST dal percorso di origine nel passaggio 5, è necessario includere questo parametro quando si esegue lo strumento nella modalità raccolta.  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |Specifica la cartella che contiene il file di configurazione XML che è stato creato quando è stato eseguito lo strumento nella modalità di ricerca. Utilizzare lo stesso valore utilizzato per questo parametro nel passaggio 1.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |Specifica la posizione dell'insieme in cui si desidera copiare i file PST. È possibile copiare i file in un file server, in una condivisione file di rete o in un'unità disco rigido. La posizione deve esistere prima di eseguire lo strumento nella modalità raccolta. Lo strumento non crea la posizione e restituirà un messaggio di errore che indica che non esiste.  <br/> Inoltre, è necessario scrivere le autorizzazioni per la posizione dell'insieme specificata da questo parametro.  <br/><br/>Se il dispositivo in cui si desidera copiare i file PST non è visibile utilizzando la `\\SERVER\SHARE` sintassi, quindi mappare una lettera di unità al dispositivo e utilizzare la lettera di unità mappata per il valore di questo parametro. | `-CopyLocation "\\FILESERVER03\PSTs"` <br/>Oppure<br/>`-CopyLocation "z:\"`|
    | `LogLocation` <br/> |Specifica la cartella in cui verrà copiato il file di registro per la modalità di raccolta. Si tratta di un parametro facoltativo. Se non è incluso, il file di registro viene copiato nella cartella in cui è stato scaricato lo strumento di raccolta PST. È consigliabile utilizzare la stessa posizione del log utilizzata per l'esecuzione dello strumento nella modalità di ricerca nel passaggio 1, in modo che tutti i file di registro vengano salvati nella stessa cartella.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Questa opzione opzionale consente di rieseguire lo strumento nella modalità raccolta per un processo di raccolta PST esistente. Se in precedenza è stato eseguito lo strumento nella modalità raccolta, ma è stato eseguito di nuovo lo strumento nella modalità di ricerca con l' `ForceRestart` opzione per rieseguire l'analisi delle posizioni per i file PST, è possibile utilizzare questa opzione per ripetere l'esecuzione dello strumento in modalità insieme e ricopiare i file PST che sono stati trovati quando i percorsi sono stati rianalizzati. Quando si utilizza l' `ForceRestart` opzione in modalità raccolta, lo strumento ignora tutte le operazioni di raccolta precedenti e tenta di copiare i file PST da zero.  <br/> | `-ForceRestart` <br/> |
   
    Di seguito è riportato un esempio della sintassi dello strumento DataCollectorMaster. exe che utilizza i valori effettivi di ogni parametro:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Dopo aver eseguito il comando, vengono visualizzati messaggi di stato dettagliati che mostrano lo stato di avanzamento della raccolta dei file PST che sono stati individuati nel passaggio 1. Dopo un po', un messaggio di stato finale indica se si sono verificati errori e la posizione in cui viene copiato il log. Gli stessi messaggi di stato vengono copiati nel file. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>Risultati dell'esecuzione di DataCollectorMaster. exe nella modalità raccolta

Dopo aver eseguito correttamente DataCollectorMaster. exe nella modalità Collect, i file seguenti vengono creati e archiviati nelle cartelle specificate dai `LogLocation` `ConfigurationLocation` parametri e. 
  
- ** \< JobName \> _Collect_ \< DateTimeStamp \> . log** : il file di log contiene i messaggi di stato che sono stati visualizzati. Questo file viene creato nella cartella specificata dal `LogLocation` parametro. 
    
- ** \< JobName \> _Collect_ \< DATETIMESTAMP \> . XML** -il file XML contiene solo informazioni sui valori dei parametri utilizzati dallo strumento in modalità raccolta. I dati contenuti in questo file vengono utilizzati quando si esegue nuovamente lo strumento DataCollectorMaster. exe per eliminare i file PST; vedere il [passaggio 5](#step-5-delete-the-pst-files-found-on-your-network).
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>Passaggio 4: importare i file PST in Office 365

Dopo aver raccolto i file PST trovati nel passaggio 1, il passaggio successivo consiste nell'importarli in cassette postali in Office 365. Come parte o il processo di importazione, è necessario creare un file di mapping CSV che contiene una riga di ogni file PST che si desidera importare. Informazioni in ogni riga specifica il nome del file PST, l'indirizzo di posta elettronica dell'utente e se si desidera importare il file PST nella cassetta postale principale o di archiviazione dell'utente. Utilizzare le informazioni contenute nel **file \> _Find_ \< DateTimeStamp. CSV di JobName Find** (creato nel passaggio) 1 per semplificare la creazione del file di mapping CSV. 
  
Per istruzioni dettagliate sull'importazione di file PST in Office 365, vedere uno dei seguenti argomenti:
  
- [Usare il caricamento tramite rete per importare file PST in Office 365](use-network-upload-to-import-pst-files.md)
    
- [Usare la spedizione unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>Passaggio 5: eliminare i file PST trovati sulla rete

Dopo che i file PST trovati e raccolti sono stati importati nelle cassette postali di Exchange online in Office 365, è possibile utilizzare lo strumento di raccolta PST per eliminare i file PST dai percorsi di origine originali in cui sono stati rilevati nel passaggio 1. 
  
1. Aprire un prompt dei comandi (Esegui come amministratore) nel computer locale.
    
2. Passare alla directory in cui è stato scaricato lo strumento di raccolta PST.
    
3. Eseguire il seguente comando per eliminare i file PST.

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    Nella tabella seguente vengono descritti i parametri e i valori necessari quando si esegue il comando DataCollectorMaster. exe per eliminare i file PST. 
    
    |Parametro * * * *|****Descrizione****|Esempi * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Specifica il tipo di dati da cercare. Attualmente, è possibile utilizzare lo strumento di raccolta PST per cercare i file PST. ![spaziatore](../media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Specifica il tipo di operazione che verrà eseguito dallo strumento. Utilizzare il valore `Delete` per eliminare i file PST che sono stati trovati quando è stato eseguito lo strumento nella modalità di ricerca.  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |Specifica il nome di un processo di raccolta PST esistente. È necessario utilizzare lo stesso nome del processo utilizzato per l'esecuzione dello strumento nella modalità di ricerca e nella modalità raccolta del passaggio 1 e del passaggio 3. Il nome del processo viene inoltre aggiunto al nome del file di registro creato quando si esegue lo strumento in modalità di eliminazione.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Specifica la cartella che contiene il file di configurazione XML che è stato creato quando è stato eseguito lo strumento nella modalità raccolta. Utilizzare lo stesso valore utilizzato per questo parametro nel passaggio 3.  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Specifica la cartella in cui verrà copiato il file di registro per la modalità di eliminazione. Si tratta di un parametro facoltativo. Se non è incluso, il file di registro viene copiato nella cartella in cui è stato scaricato lo strumento di raccolta PST. È consigliabile utilizzare la stessa posizione del log utilizzata per l'esecuzione dello strumento nelle modalità di ricerca e raccolta del passaggio 1 e del passaggio 3, in modo che tutti i file di registro vengano salvati nella stessa cartella.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Questa opzione opzionale consente di rieseguire lo strumento in modalità di eliminazione per un processo di raccolta PST esistente. Se in precedenza è stato eseguito lo strumento in modalità di eliminazione, ma in seguito è stato eseguito nuovamente lo strumento nella modalità di ricerca con l' `ForceRestart` opzione per eseguire di nuovo l'analisi delle posizioni per i file PST, è possibile utilizzare questa opzione per rieseguire lo strumento in modalità di eliminazione ed eliminare i file PST che sono stati trovati quando i percorsi sono stati rianalizzati. Quando si utilizza l' `ForceRestart` opzione in modalità di eliminazione, lo strumento ignora le operazioni di eliminazione precedenti e tenta di eliminare di nuovo i file PST.  <br/> | `-ForceRestart` <br/> 

    Di seguito è riportato un esempio della sintassi dello strumento DataCollectorMaster. exe che utilizza i valori effettivi di ogni parametro:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Dopo aver eseguito il comando, vengono visualizzati messaggi di stato dettagliati che mostrano lo stato di avanzamento dell'eliminazione dei file PST che sono stati rilevati nel passaggio 1 e raccolti nel passaggio 3. Dopo un po', un messaggio di stato finale indica se si sono verificati errori e la posizione in cui viene copiato il log. Gli stessi messaggi di stato vengono copiati nel file. log.
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>Risultati dell'esecuzione di DataCollectorMaster. exe in modalità di eliminazione

Dopo aver eseguito correttamente DataCollectorMaster. exe in modalità di eliminazione, i file seguenti vengono creati e archiviati nella cartella specificata dai `LogLocation` `ConfigurationLocation` parametri e. 
  
- ** \< JobName \> _Delete_ \< DateTimeStamp \> . log** : il file di log contiene i messaggi di stato che sono stati visualizzati. Questo file viene creato nella cartella specificata dal `LogLocation` parametro. 
    
- ** \< JobName \> _Delete_ \< DATETIMESTAMP \> . XML** -il file XML contiene solo informazioni sui valori dei parametri utilizzati dallo strumento in modalità di eliminazione. Vengono inoltre elencati il nome e il percorso del file di ogni file PST che è stato eliminato. Questo file viene creato nella cartella specificata dal `ConfigurationLocation` parametro. 
