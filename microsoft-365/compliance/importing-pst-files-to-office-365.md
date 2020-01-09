---
title: Panoramica dell'importazione di file PST dell'organizzazione in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: "Per gli amministratori: informazioni sull'uso del servizio di importazione nel Centro sicurezza e conformità per importare dati di posta elettronica (file PST) nelle cassette postali degli utenti in Exchange Online. Questo argomento include le domande frequenti e spiega il funzionamento del processo di importazione PST."
ms.openlocfilehash: 4e58be4e90429c2d39bbcf4c5ef362e659764d63
ms.sourcegitcommit: cf7b0fd80ecfb7a216111a801269c5322794795e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "40995286"
---
# <a name="overview-of-importing-your-organizations-pst-files-to-office-365"></a>Panoramica dell'importazione di file PST dell'organizzazione in Office 365

> [!NOTE]
> Questo articolo è rivolto agli amministratori. L'utente sta tentando di importare file PST nella propria cassetta postale? Vedere [Importare posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

È possibile usare il servizio di importazione nel Centro sicurezza e conformità per importare rapidamente in blocco i file PST nelle cassette postali di Exchange Online nell'organizzazione di Office 365. Per importare file PST in Office 365 sono disponibili due procedure:

- **Caricamento tramite rete** ![Caricamento cloud](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Carica i file PST tramite rete in un percorso di archiviazione di Azure nel cloud Microsoft. Si usa quindi il servizio di importazione di Office 365 per importare i dati PST nelle cassette postali o nei siti dell'organizzazione di Office 365. 

- **Spedizione unità** ![Hard disk](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - I file PST vengono copiati in un disco rigido con crittografia Bitlocker, quindi spediti fisicamente a Microsoft. Quando Microsoft riceve il disco rigido, il personale del datacenter copia i dati in un percorso di archiviazione temporaneo di Azure nel cloud Microsoft. Si usa quindi il servizio di importazione di Office 365 per importare i dati nelle cassette postali o nei siti dell'organizzazione di Office 365.

## <a name="step-by-step-instructions"></a>Istruzioni dettagliate
  
Per istruzioni dettagliate sull'importazione in blocco dei file PST dell'organizzazione in Office 365, vedere uno dei seguenti argomenti. 

- [Usare il caricamento tramite rete per importare file PST in Office 365](use-network-upload-to-import-pst-files.md)

- [Usare la spedizione unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Come funziona l'importazione dei file PST

Ecco un'illustrazione e una descrizione del processo di importazione PST completo. La figura mostra il flusso di lavoro principale ed evidenzia le differenze tra i metodi di caricamento tramite rete e di spedizione unità.
  
![Flusso di lavoro del processo di importazione PST](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Scaricare la chiave e gli strumenti di importazione PST in un percorso di archiviazione privato di Azure** - Il primo passaggio consiste nello scaricare la chiave di accesso e lo strumento usati per caricare i file PST o nel copiarli in un disco rigido. Per ottenerli, usare la pagina di **importazione** nel Centro sicurezza e conformità. La chiave fornisce all'utente o, nel caso di una spedizione unità, al personale del datacenter Microsoft le autorizzazioni necessarie per caricare i file PST in un percorso di archiviazione di Azure privato e sicuro. Questa chiave di accesso è univoca per l'organizzazione e consente di impedire l'accesso non autorizzato ai file PST dopo il caricamento nel cloud Microsoft. L'importazione di file PST in Office 365 non richiede all'organizzazione di avere un altra sottoscrizione di Azure. 
    
2. **Caricare o copiare i file PST** - Il passaggio successivo è diverso a seconda che si usi il caricamento tramite rete o la spedizione unità per importare i file PST. In entrambi i casi si userà lo strumento e la chiave di archiviazione sicura ottenuti nel passaggio precedente.
    
    - **Caricamento tramite rete:** Lo strumento AzCopy.exe, scaricato nel passaggio 1, viene usato per caricare e archiviare i file PST in un percorso di archiviazione di Azure nel cloud Microsoft. Il percorso di archiviazione di Azure in cui si caricano i file PST si trova nello stesso datacenter Microsoft locale in cui si trova l'organizzazione di Office 365.
    
      Per caricarli, i file PST da importare in Office 365 devono trovarsi in una condivisione file o in un file server dell'organizzazione.
    
    - **Spedizione unità:** Lo strumento WAImportExport.exe, scaricato nel passaggio 1, viene usato per copiare i file PST sul disco rigido. Questo strumento crittografa il disco rigido con BitLocker e copia i file PST nel disco rigido. Come per il caricamento tramite rete, i file PST da copiare nel disco rigido devono trovarsi in una condivisione file o in un file server dell'organizzazione.
    
3. **Creare un file di mapping di importazione PST** - Dopo aver caricato i file PST nel percorso di archiviazione di Azure o averli copiati in un disco rigido, il passaggio successivo consiste nel creare un file con valori separati da virgola (CSV) che specifica in quali cassette postali degli utenti verranno importati i file PST. I file PST possono essere importanti nella cassetta postale principale dell'utente o nella cassetta postale di archiviazione. Il servizio di importazione di Office 365 userà le informazioni per importare i file PST. 
    
4. **Creare un processo di importazione PST** - Il passaggio successivo consiste nel creare un processo di importazione PST nella pagina **Importa file PST** del Centro sicurezza e conformità e nell'inviare il file di mapping dell'importazione PST creato nel passaggio precedente. Poiché i file PST sono stati caricati in Azure, per il caricamento tramite rete Office 365 analizza i dati nei file PST e offre la possibilità di impostare filtri per controllare i dati effettivamente importati nelle cassette postali specificate nel file di mapping dell'importazione PST. 
    
    Per la spedizione unità, a questo punto del processo vanno considerati altri fattori.
    
    - Il disco rigido viene spedito fisicamente al datacenter Microsoft (l'indirizzo di spedizione per il datacenter Microsoft viene visualizzato quando viene creato il processo di importazione).
    
    - Quando Microsoft riceve il disco rigido, il personale del datacenter carica i file PST del disco rigido nel percorso di archiviazione di Azure per l'organizzazione. Come spiegato in precedenza, i file PST vengono caricati in un percorso di archiviazione di Azure che si trova nello stesso datacenter Microsoft locale in cui si trova l'organizzazione di Office 365.
    
      > [!NOTE]
      > I file PST sul disco rigido vengono caricati in Azure entro 7 - 10 giorni lavorativi da quando Microsoft riceve il disco rigido.

      Come nel processo di caricamento in rete, Office 365 analizza i dati nei file PST e offre la possibilità di impostare filtri per controllare i dati effettivamente importati nelle cassette postali specificate nel file di mapping dell'importazione PST.
    
    - Microsoft rispedisce il disco rigido al mittente.
    
5. **Filtrare i dati PST che verranno importati nelle cassette postali** - Dopo la creazione del processo di importazione (e dopo che i file PST su un disco spedito vengono caricati nel percorso di archiviazione di Azure) Office 365 analizza i dati nei file PST (in modo sicuro) identificando l'età degli elementi e i diversi tipi di messaggio inclusi nei file PST. Quando l'analisi è completa e i dati sono pronti per l'importazione, si può scegliere di importare tutti i dati nei file PST così come sono oppure filtrare i dati da importare impostando dei filtri. 
    
6. **Avviare il processo di importazione PST** - Dopo l'avvio del processo di importazione, Office 365 usa le informazioni nel file di mapping dell'importazione PST per importare i file PST dal percorso di archiviazione di Azure alle cassette postali degli utenti. Le informazioni sullo stato del processo di importazione, incluse quelle relative a ogni file PST da importare, vengono visualizzate nella pagina **Importa file PST** nel Centro sicurezza e conformità. Al termine del processo di importazione, lo stato del processo è impostato su **Completato**.
  
## <a name="why-import-email-data-to-office-365"></a>Perché importare dati di posta elettronica in Office 365?

- È un modo efficace per importare i dati di archiviazione della messaggistica dell'organizzazione in Office 365.
    
- Con la funzionalità [Importazione intelligente](filter-data-when-importing-pst-files.md) è possibile filtrare gli elementi nei file PST effettivamente importati nelle cassette postali di destinazione. Questo consente di ridurre i dati importati impostando filtri che controllano quali dati vengono inclusi nell'importazione. 
    
- L'importazione dei dati di posta elettronica in Office 365 consente di soddisfare le esigenze di conformità dell'organizzazione perché permette di:
    
  - Abilitare le [cassette postali di archiviazione](enable-archive-mailboxes.md) e l'[archiviazione illimitata](unlimited-archiving.md) per offrire agli utenti altro spazio di archiviazione delle cassette postali. 
    
  - Impostare le cassette postali su [Blocco per controversia legale](https://go.microsoft.com/fwlink/?linkid=841243) per conservare il contenuto. 
    
  - Usare lo [strumento Ricerca contenuto](content-search.md) per cercare il contenuto della cassetta postale. 
    
  - Usare i [casi eDiscovery](ediscovery-cases.md) per gestire le indagini legali dell'organizzazione 
    
  - Usare i [criteri di conservazione](retention-policies.md) nel Centro sicurezza e conformità per determinare il periodo di conservazione del contenuto delle cassette postali, allo scadere del quale il contenuto viene eliminato. 

  - Usare i [criteri di conformità della comunicazione](communication-compliance.md) per esaminare i messaggi assicurandosi che siano conformi agli standard dei messaggi e aggiungere un tipo di classificazione.
    
- L'importazione di dati in Office365 consente di evitare la perdita di dati. I dati di posta elettronica importati in Office 365 ereditano le funzionalità ad alta disponibilità di Exchange Online.
    
- I dati di posta elettronica in Office 365 sono archiviati nel cloud, di conseguenza gli utenti possono accedervi da tutti i dispositivi.
    
## <a name="importing-sharepoint-data-to-office-365"></a>Importazione dei dati di SharePoint in Office 365

Si possono anche importare file e documenti nei siti di SharePoint e negli account di OneDrive dell'organizzazione di Office 365. Per ulteriori informazioni, vedere gli articoli seguenti:

- [Eseguire la migrazione a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [Introduzione allo Strumento di migrazione di SharePoint](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Eseguire la migrazione a SharePoint Online con PowerShell](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [Eseguire la migrazione del contenuto condiviso dei file a SharePoint Online con Azure Data Box](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a>Domande frequenti sull’importazione di file PST in Office 365
  
Ecco alcune domande frequenti relative all'uso del servizio di importazione di Office 365 per importare in blocco i file PST nelle cassette postali di Office 365. 
  
- [Uso del caricamento tramite rete per l'importazione di file PST](#using-network-upload-to-import-pst-files)
  
- [Uso della spedizione unità per l'importazione di file PST](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Uso del caricamento tramite rete per l'importazione di file PST

 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
All'utente deve essere assegnato il ruolo di importazione/esportazione di cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione/importazione cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di importazione/esportazione di cassette postali e quindi aggiungere se stessi o altri utenti come membri. Per altre informazioni, vedere le sezioni "Aggiungere un ruolo a un gruppo di ruoli" o "Creare un gruppo di ruoli" in [Gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Inoltre, per creare processi di importazione nel Centro sicurezza e conformità, una delle seguenti condizioni deve essere vera:
  
- All'utente deve essere assegnato il ruolo Destinatari di posta in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari.

    Oppure
    
- L'utente deve essere un amministratore globale nell'organizzazione di Office 365.

> [!TIP]
> Prendere in considerazione la creazione di un nuovo gruppo di ruoli in Exchange Online appositamente creato per l'importazione dei file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione/esportazione di cassette postali e Destinatari di posta al nuovo gruppo di ruoli, quindi aggiungere i membri. 
  
 **Dov'è disponibile il caricamento tramite rete?**
  
Il caricamento tramite rete è attualmente disponibile negli Stati Uniti, nonché in Canada, Brasile, Regno Unito, Europa, India, Asia orientale, Asia sud-orientale, Giappone, Repubblica di Corea e Australia. Questa caratteristica sarà presto disponibile in altre aree geografiche.
  
 **Quanto costa importare file PST con il caricamento tramite rete?**
  
Using network upload to import PST files is free.
  
Significa anche che, dopo essere stati eliminati dall'area di archiviazione di Azure, i file PST non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nell'interfaccia di amministrazione di Microsoft 365. Anche se un processo di importazione potrebbe essere ancora presente nella pagina **Importa dati in Office 365**, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione precedenti.
  
 **Quale versione del formato di file PST è supportata per l'importazione in Office 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che usano il formato di file PST Unicode. Tuttavia, i file che usano il formato di file PST ANSI, ad esempio quelli per le lingue che usano un set di caratteri a due byte (DBCS), possono anche essere importati in Office 365. Per altre informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 in [Usare il caricamento tramite rete per importare file PST in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
È anche possibile importare i file PST di Outlook 2007 e versioni successive in Office 365.
  
 **Dopo il caricamento dei file PST nell'area di archiviazione di Azure, per quanto tempo vengono conservati in Azure prima dell'eliminazione?**
  
Quando si usa il metodo di caricamento tramite rete per importare i file PST, i file vengono caricati in un contenitore BLOB di Azure denominato **ingestiondata**. Se non ci sono processi di importazione in corso nella pagina **Importa file PST** del Centro sicurezza e conformità, tutti i file PST nel contenitore **ingestiondata** in Azure vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nel Centro sicurezza e conformità. Significa anche che è necessario creare un nuovo processo di importazione nel Centro sicurezza e conformità, descritto nel passaggio 5 delle istruzioni di caricamento tramite rete, entro 30 giorni dal caricamento dei file PST in Azure.
  
Significa anche che, dopo essere stati eliminati dall'area di archiviazione di Azure, i file PST non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nel Centro sicurezza e conformità. Anche se un processo di importazione potrebbe essere ancora presente nella pagina **Importa file PST** del Centro sicurezza e conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione precedenti.
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dipende dalla capacità della rete, ma in genere sono necessarie diverse ore per ogni terabyte (TB) di dati da caricare nell'area di archiviazione di Azure per l'organizzazione. Una volta copiati i file PST nell'area di archiviazione di Azure, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa velocità non soddisfa le proprie esigenze, è consigliabile ricorrere ad altri metodi per ottenere i dati di posta elettronica in Office 365. Per altre informazioni, vedere [Modalità di migrazione di più account di posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Se si importano file PST diversi in cassette postali di destinazione diverse, il processo di importazione verrà eseguito in parallelo, ovvero ogni coppia di file PST e cassetta postale verrà importata contemporaneamente. Analogamente, se si importano più file PST nella stessa cassetta postale, questi vengono importati contemporaneamente.
  
 **È previsto un limite alle dimensioni del messaggio durante l'importazione dei file PST?**
  
Sì. Se un file PST contiene un elemento della cassetta postale con dimensioni maggiori di 150 MB, questo elemento viene ignorato durante il processo di importazione.
  
 **Le proprietà del messaggio, ad esempio la data/ora di invio o ricezione del messaggio, l'elenco dei destinatari e altre proprietà, vengono mantenute quando i file PST vengono importati in una cassetta postale di Office365?**
  
Sì. I metadati del messaggio originale non vengono modificati durante il processo di importazione.
  
 **È previsto un limite al numero di livelli in una gerarchia di cartelle per un file PST da importare in una cassetta postale?**
  
Sì. Non è possibile importare un file PST che contiene più di 300 livelli di cartelle annidate.
  
 **È possibile usare il caricamento tramite rete per importare file PST in una cassetta postale inattiva in Office 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile usare il caricamento tramite rete per importare file PST in una cassetta postale di archiviazione online di una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile. 
  
 **Si può usare il caricamento di rete per importare file PST in cartelle pubbliche in Exchange Online?**
  
No. Non è possibile importare file PST nelle cartelle pubbliche.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Uso della spedizione unità per l'importazione di file PST

 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
Per importare i file PST nelle cassette postali di Office 365, all'utente deve essere assegnato il ruolo Importazione/Esportazione cassette postali. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione/importazione cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di importazione/esportazione di cassette postali e quindi aggiungere se stessi o altri utenti come membri. Per altre informazioni, vedere le sezioni "Aggiungere un ruolo a un gruppo di ruoli" o "Creare un gruppo di ruoli" in [Gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Inoltre, per creare processi di importazione nel Centro sicurezza e conformità, una delle seguenti condizioni deve essere vera:
  
- All'utente deve essere assegnato il ruolo Destinatari di posta in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari.
    
    Oppure
    
- L'utente deve essere un amministratore globale nell'organizzazione di Office 365.
    
> [!TIP]
> Prendere in considerazione la creazione di un nuovo gruppo di ruoli in Exchange Online appositamente creato per l'importazione dei file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione/esportazione di cassette postali e Destinatari di posta al nuovo gruppo di ruoli, quindi aggiungere i membri. 
  
 **Dov'è disponibile la spedizione unità?**
  
La spedizione unità è attualmente disponibile negli Stati Uniti, nonché in Canada, Brasile, Regno Unito, Europa, India, Asia orientale, Asia sud-orientale, Giappone, Repubblica di Corea e Australia. Questa funzionalità sarà presto disponibile in altre aree geografiche.
  
 **Quali contratti di licenza commerciali supportano la spedizione unità?**
  
La spedizione unità per importare i file PST in Office 365 è disponibile con un contratto Microsoft Enterprise Agreement (EA). La spedizione unità non è disponibile con un contratto Microsoft Products and Services Agreement (MPSA).
  
 **Quanto costa usare la spedizione unità per importare file PST in Office 365?**
  
Il costo della spedizione unità per importare file PST in cassette postali di Office 365 è pari a 2 dollari USA per GB di dati. Se ad esempio si spedisce un'unità disco rigido contenente 1000 GB (1 TB) di file PST, il costo sarà 2000 dollari USA. È possibile collaborare con un partner per il pagamento delle spese di importazione. Per informazioni su come trovare un partner, vedere [Trovare il partner o il rivenditore di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Quali tipi di dischi rigidi sono supportati per la spedizione unità?**
  
Solo le unità SSD da 2,5 pollici o le unità disco rigido interno SATA II/III da 2,5 o 3,5 pollici sono supportate per l'utilizzo con il servizio Importa di Office 365. È possibile utilizzare unità disco rigido fino a 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati del disco rigido. Il volume di dati deve essere in formato NTFS. Quando si copiano i dati su un disco rigido, è possibile collegarlo direttamente usando un connettore SSD da 2,5 pollici o SATA II/III da 2,5 o 3,5 pollici oppure collegarlo esternamente usando una scheda SSD da 2,5 pollici o SATA II/III da 2,5 o 3,5 pollici.
  
> [!IMPORTANT]
> I dischi rigidi esterni che vengono installati con un adattatore USB incorporato non sono supportati dal servizio Importa di Office 365. Inoltre, il disco all'interno della scocca di un disco rigido esterno non può essere utilizzato. Non spedire unità disco rigido esterne. 
  
 **Quante unità disco rigido è possibile spedire per un singolo processo di importazione?**
  
Per ogni processo di importazione è possibile spedire un massimo di 10 unità disco rigido.
  
 **Quanto tempo occorre affinché l'unità disco rigido spedita arrivi al data center Microsoft?**
  
Dipende da vari fattori, tra cui la vicinanza al data center Microsoft e il tipo di opzione di spedizione scelta per spedire l'unità, come la consegna entro il giorno successivo, la consegna entro due giorni o quella standard. La maggior parte degli spedizionieri fornisce un apposito codice per tenere traccia dello stato della consegna.
  
 **Dopo la consegna dell'unità disco rigido al datacenter Microsoft, quanto tempo è necessario per caricare i file PST in Azure?**
  
Dopo che il disco rigido viene consegnato al datacenter Microsoft, saranno necessari tra i 7 e i 10 giorni lavorativi per caricare i file PST nel percorso di archiviazione di Azure dell'organizzazione. I file PST verranno caricati in un contenitore BLOB di Azure denominato `ingestiondata`. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo aver caricato i file PST nell'area di archiviazione di Azure, Office 365 analizza i dati nei file PST in modo sicuro per identificare l'età degli elementi e i diversi tipi di messaggio inclusi nei file PST. Una volta completata questa analisi, si potranno importare tutti i dati nei file PST o impostare filtri per controllare quali dati vengono importati. Dopo aver avviato il processo di importazione, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa velocità non soddisfa le proprie esigenze, è consigliabile ricorrere ad altri metodi per ottenere i dati di posta elettronica in Office 365. Per altre informazioni, vedere [Modalità di migrazione di più account di posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Se si importano file PST diversi in cassette postali di destinazione diverse, il processo di importazione verrà eseguito in parallelo, ovvero ogni coppia di file PST e cassetta postale verrà importata contemporaneamente. Analogamente, se si importano più file PST nella stessa cassetta postale, questi vengono importati contemporaneamente.
  
 **Dopo il caricamento dei file PST in Azure da parte di Microsoft, per quanto tempo vengono conservati in Azure prima dell'eliminazione?**
  
Tutti i file PST nel percorso di archiviazione di Azure dell'organizzazione, ovvero il contenitore BLOB denominato `ingestiondata`, vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nella pagina **Importa file PST** del Centro sicurezza e conformità. 
  
Significa anche che, dopo essere stati eliminati dall'area di archiviazione di Azure, i file PST non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nel Centro sicurezza e conformità. Anche se un processo di importazione potrebbe essere ancora presente nella pagina **Importa file PST** del Centro sicurezza e conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quale versione del formato di file PST è supportata per l'importazione in Office 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che usano il formato di file PST Unicode. Tuttavia, i file che usano il formato di file PST ANSI, ad esempio quelli per le lingue che usano un set di caratteri a due byte (DBCS), possono anche essere importati in Office 365. Per altre informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 in [Usare la spedizione unità per importare i file PST dell'organizzazione in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
È anche possibile importare i file PST di Outlook 2007 e versioni successive in Office 365.
  
 **È previsto un limite alle dimensioni del messaggio durante l'importazione dei file PST?**
  
Sì. Se un file PST contiene un elemento della cassetta postale con dimensioni maggiori di 150 MB, questo elemento viene ignorato durante il processo di importazione.
  
 **Le proprietà del messaggio, ad esempio la data/ora di invio o ricezione del messaggio, l'elenco dei destinatari e altre proprietà, vengono mantenute quando i file PST vengono importati in una cassetta postale di Office365?**
  
Sì. I metadati del messaggio originale non vengono modificati durante il processo di importazione
  
 **È previsto un limite al numero di livelli in una gerarchia di cartelle per un file PST da importare in una cassetta postale?**
  
Sì. Non è possibile importare un file PST che contiene più di 300 livelli di cartelle annidate.
  
 **È possibile usare la spedizione unità per importare file PST in una cassetta postale inattiva in Office 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile usare la spedizione unità per importare file PST in una cassetta postale di archiviazione online di una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile. 
  
 **Si può usare la spedizione unità per importare file PST in cartelle pubbliche di Exchange Online?**
  
No. Non è possibile importare file PST nelle cartelle pubbliche.
  
 **Microsoft può cancellare i dati presenti nell'unità disco rigido prima di rispedirla al cliente?**
  
No. Microsoft non può cancellare i dati presenti nelle unità disco rigido prima di rispedirle ai clienti. Le unità disco rigido vengono restituite nello stato in cui si trovavano quando sono state ricevute da Microsoft.
  
 **Microsoft può distruggere l'unità disco rigido invece di rispedirla al cliente?**
  
No. Microsoft non può distruggere le unità disco rigido. Le unità disco rigido vengono restituite nello stato in cui si trovavano quando sono state ricevute da Microsoft.
  
 **Quali sono gli spedizionieri supportati per la restituzione delle unità?**
  
Per restituire le unità disco rigido ai clienti negli Stati Uniti, Microsoft si affida a FedEx. In tutte le altre aree geografiche Microsoft si rivolge a DHL.
  
 **Quali sono i costi di spedizione per la restituzione?**
  
I costi di spedizione per la restituzione variano in funzione della vicinanza al data center Microsoft a cui è stata spedita l'unità disco rigido. Microsoft fatturerà i costi di spedizione dell'unità disco rigido all'account FedEx o DHL del cliente. I costi di spedizione per la restituzione dell'unità disco rigido sono a carico del cliente.
  
 **È possibile scegliere un altro servizio di spedizione, come FedEx Custom Shipping, per spedire l'unità disco rigido a Microsoft?**
  
Sì.
  
 **Per spedire l'unità disco rigido in un altro paese sono previste particolari incombenze?**
  
È possibile che l'unità disco rigido spedita a Microsoft debba varcare i confini internazionali. In tal caso il cliente deve assicurarsi che l'unità disco rigido e i dati in essa contenuti vengano importati e/o esportati in conformità alle leggi vigenti. Prima di spedire un'unità disco rigido, verificare con i propri consulenti che l'unità e i dati possano essere spediti al data center Microsoft specificato senza incorrere in problemi legali. Queste precauzioni consentiranno di evitare ritardi nella spedizione a Microsoft.
