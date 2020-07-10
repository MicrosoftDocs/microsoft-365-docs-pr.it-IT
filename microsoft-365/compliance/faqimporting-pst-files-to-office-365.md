---
title: Domande frequenti sull'importazione di file PST
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
ms.custom: seo-marvel-apr2020
description: Questo articolo contiene le risposte ad alcune domande frequenti per gli amministratori sull'importazione di file PST in Microsoft 365 utilizzando il servizio di importazione di Office 365.
ms.openlocfilehash: 5ba6df2f2c6ed10edee22f58308a5e3ee5acd533
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091900"
---
# <a name="faq-about-importing-pst-files"></a>Domande frequenti sull'importazione di file PST

**Questo articolo è per gli amministratori. Si desidera importare i file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Di seguito sono riportate alcune domande frequenti sull'utilizzo del servizio di importazione di Office 365 per importare in blocco i file PST nelle cassette postali di Microsoft 365. Per ulteriori informazioni su come importare i file PST, vedere [Overview of import PST files to Office 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365).
  
## <a name="using-network-upload-to-import-pst-files"></a>Uso del caricamento tramite rete per l'importazione di file PST

Per istruzioni dettagliate, vedere [usare il caricamento di rete per importare i file PST in Office 365](use-network-upload-to-import-pst-files.md).
  
 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
Per importare i file PST nelle cassette postali di Microsoft 365, è necessario avere il ruolo di importazione/esportazione di cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione/importazione cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di importazione/esportazione di cassette postali e quindi aggiungere se stessi o altri utenti come membri. Per altre informazioni, vedere le sezioni "Aggiungere un ruolo a un gruppo di ruoli" o "Creare un gruppo di ruoli" in [Gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Inoltre, per creare processi di importazione nel Centro sicurezza e conformità, una delle seguenti condizioni deve essere vera:
  
- All'utente deve essere assegnato il ruolo Destinatari di posta in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale nell'organizzazione.
    
> [!TIP]
> Prendere in considerazione la creazione di un nuovo gruppo di ruoli in Exchange Online appositamente creato per l'importazione dei file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione/esportazione di cassette postali e Destinatari di posta al nuovo gruppo di ruoli, quindi aggiungere i membri. 
  
 **Dov'è disponibile il caricamento tramite rete?**
  
Il caricamento di rete è attualmente disponibile in queste aree: Stati Uniti, Canada, Brasile, Regno Unito, Francia, Germania, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea, Australia e Emirati Arabi Uniti (UAE). Network upload will be available in more regions soon.
  
 **Quanto costa importare file PST con il caricamento tramite rete?**
  
Using network upload to import PST files is free.
  
Significa anche che, dopo essere stati eliminati dall'area di archiviazione di Azure, i file PST non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nell'interfaccia di amministrazione di Microsoft 365. Anche se un processo di importazione potrebbe essere ancora presente nella pagina **Importa dati in Office 365**, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quale versione del formato di file PST è supportata per l'importazione in Office 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che usano il formato di file PST Unicode. Tuttavia, i file che usano il formato di file PST ANSI, ad esempio quelli per le lingue che usano un set di caratteri a due byte (DBCS), possono anche essere importati in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 in [use Network upload to import your organization ' s PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
È anche possibile importare i file PST di Outlook 2007 e versioni successive in Office 365.
  
 **Dopo il caricamento dei file PST nell'area di archiviazione di Azure, per quanto tempo vengono conservati in Azure prima dell'eliminazione?**
  
Quando si utilizza il metodo di caricamento di rete per importare i file PST, è possibile caricarli in un contenitore BLOB di Azure denominato `ingestiondata` . Se non sono presenti processi di importazione in corso nella pagina **Importa file PST** nel centro sicurezza & conformità), tutti i file pst nel `ingestiondata` contenitore in Azure vengono eliminati 30 giorni dopo che è stato creato il processo di importazione più recente nel centro sicurezza & Compliance. Significa anche che è necessario creare un nuovo processo di importazione nel Centro sicurezza e conformità, descritto nel passaggio 5 delle istruzioni di caricamento tramite rete, entro 30 giorni dal caricamento dei file PST in Azure. 
  
Significa anche che, dopo essere stati eliminati dall'area di archiviazione di Azure, i file PST non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nel Centro sicurezza e conformità. Anche se un processo di importazione potrebbe essere ancora presente nella pagina **Importa file PST** del Centro sicurezza e conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dipende dalla capacità della rete, ma in genere sono necessarie diverse ore per ogni terabyte (TB) di dati da caricare nell'area di archiviazione di Azure per l'organizzazione. Una volta copiati i file PST nell'area di Archiviazione di Azure, un file PST viene importato in una cassetta postale di Microsoft 365 a una velocità di almeno 24 GB al giorno. Se questa velocità non soddisfa le proprie esigenze, è consigliabile ricorrere ad altri metodi per la migrazione dei dati di posta elettronica a Office 365. Per altre informazioni, vedere [Modalità di migrazione di più account di posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Se si importano file PST diversi in cassette postali di destinazione diverse, il processo di importazione verrà eseguito in parallelo, ovvero ogni coppia di file PST e cassetta postale verrà importata contemporaneamente. Analogamente, se si importano più file PST nella stessa cassetta postale, questi vengono importati contemporaneamente.
  
 **In che modo il processo di importazione PST gestisce gli elementi di posta elettronica duplicati?**

Durante il processo di importazione PST viene controllata la presenza di elementi duplicati; gli elementi dei file PST non vengono copiati nella cassetta postale o nell'archivio di destinazione se è già presente un elemento corrispondente nella cartella di destinazione. Se si reimporta lo stesso file PST e si specifica una cartella di destinazione diversa (utilizzando la proprietà TargetRootFolder nel file di mapping di importazione PST) rispetto a quella specificata in un processo di importazione precedente, tutti gli elementi del file PST verranno reimportati.

 **È previsto un limite alle dimensioni del messaggio durante l'importazione dei file PST?**
  
Sì. Se un file PST contiene un elemento della cassetta postale con dimensioni maggiori di 150 MB, questo elemento viene ignorato durante il processo di importazione.
  
 **Le proprietà del messaggio, ad esempio la data/ora di invio o ricezione del messaggio, l'elenco dei destinatari e altre proprietà, vengono conservate quando i file PST vengono importati in una cassetta postale di Microsoft 365?**
  
Sì. I metadati del messaggio originale non vengono modificati durante il processo di importazione.
  
 **È previsto un limite al numero di livelli in una gerarchia di cartelle per un file PST da importare in una cassetta postale?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **È possibile usare il caricamento tramite rete per importare file PST in una cassetta postale inattiva in Office 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile usare il caricamento tramite rete per importare file PST in una cassetta postale di archiviazione online di una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile. 
  
 **Si può usare il caricamento di rete per importare file PST in cartelle pubbliche in Exchange Online?**
  
No. Non è possibile importare file PST nelle cartelle pubbliche.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Uso della spedizione unità per l'importazione di file PST

Per istruzioni dettagliate, vedere [Use Drive Shipping to Import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
Per importare i file PST nelle cassette postali di Microsoft 365, l'utente deve avere il ruolo importazione/esportazione di cassette postali. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione/importazione cassette postali al gruppo di ruoli Gestione organizzazione. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di importazione/esportazione di cassette postali e quindi aggiungere se stessi o altri utenti come membri. Per altre informazioni, vedere le sezioni "Aggiungere un ruolo a un gruppo di ruoli" o "Creare un gruppo di ruoli" in [Gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Inoltre, per creare processi di importazione nel Centro sicurezza e conformità, una delle seguenti condizioni deve essere vera:
  
- All'utente deve essere assegnato il ruolo Destinatari di posta in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Gestione destinatari.
    
    Oppure
    
- È necessario essere un amministratore globale nell'organizzazione.
    
> [!TIP]
> Prendere in considerazione la creazione di un nuovo gruppo di ruoli in Exchange Online appositamente creato per l'importazione dei file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione/esportazione di cassette postali e Destinatari di posta al nuovo gruppo di ruoli, quindi aggiungere i membri. 
  
 **Dov'è disponibile la spedizione unità?**
  
La spedizione unità è attualmente disponibile negli Stati Uniti, nonché in Canada, Brasile, Regno Unito, Europa, India, Asia orientale, Asia sud-orientale, Giappone, Repubblica di Corea e Australia. Questa funzionalità sarà presto disponibile in altre aree geografiche.

> [!NOTE]
> Al momento, la spedizione unità per importare file PST non è disponibile in Germania e Svizzera. Le domande frequenti verranno aggiornate quando la spedizione unità sarà disponibile in questi paesi.
  
 **Quali contratti di licenza commerciali supportano la spedizione unità?**
  
La spedizione unità per importare i file PST in Microsoft 365 è disponibile con un contratto Microsoft Enterprise Agreement (EA). La spedizione unità non è disponibile con un contratto Microsoft Products and Services Agreement (MPSA).
  
 **Quanto costa usare la spedizione unità per importare i file PST in Microsoft 365?**
  
Il costo della spedizione unità per importare i file PST in cassette postali di Microsoft 365 è pari a 2 dollari USA per GB di dati. Se ad esempio si spedisce un'unità disco rigido contenente 1000 GB (1 TB) di file PST, il costo sarà 2000 dollari USA. È possibile collaborare con un partner per il pagamento delle spese di importazione. Per informazioni su come trovare un partner, vedere [Trovare un partner o rivenditore di Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Quali tipi di dischi rigidi sono supportati per la spedizione unità?**
  
Per l'utilizzo con il servizio di importazione di Office 365, sono supportate solo unità SSD da 2,5 pollici a stato solido o 2,5 pollice o 3,5 pollici SATA II/III. È possibile utilizzare unità disco rigido fino a 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati del disco rigido. Il volume di dati deve essere in formato NTFS. Quando si copiano i dati su un disco rigido, è possibile collegarlo direttamente usando un connettore SSD da 2,5 pollici o SATA II/III da 2,5 o 3,5 pollici oppure collegarlo esternamente usando una scheda SSD da 2,5 pollici o SATA II/III da 2,5 o 3,5 pollici.
  
> [!IMPORTANT]
> I dischi rigidi esterni che vengono installati con un adattatore USB incorporato non sono supportati dal servizio Importa di Office 365. Inoltre, il disco all'interno della scocca di un disco rigido esterno non può essere utilizzato. Non spedire unità disco rigido esterne. 
  
 **Quante unità disco rigido è possibile spedire per un singolo processo di importazione?**
  
Per ogni processo di importazione è possibile spedire un massimo di 10 unità disco rigido.
  
 **Quanto tempo occorre affinché l'unità disco rigido spedita arrivi al data center Microsoft?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Dopo la consegna dell'unità disco rigido al datacenter Microsoft, quanto tempo è necessario per caricare i file PST in Azure?**
  
Dopo aver ricevuto il disco rigido in Microsoft Data Center, saranno necessari tra 7 e 10 giorni lavorativi per caricare i file PST nell'area di archiviazione di Azure per l'organizzazione. I file PST verranno caricati in un contenitore BLOB di Azure denominato `ingestiondata`. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo aver caricato i file PST nell'area di Archiviazione di Azure, Microsoft 365 analizza i dati nei file PST in modo sicuro per identificare la data di creazione degli elementi e i diversi tipi di messaggio inclusi nei file PST. Una volta completata questa analisi, si potranno importare tutti i dati nei file PST o impostare filtri per controllare quali dati vengono importati. Dopo aver avviato il processo di importazione, un file PST viene importato in una cassetta postale di Microsoft 365 a una velocità di almeno 24 GB al giorno. Se questa velocità non soddisfa le proprie esigenze, è consigliabile ricorrere ad altri metodi per l'importazione dei dati di posta elettronica in Office 365. Per altre informazioni, vedere [Modalità di migrazione di più account di posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Se si importano file PST diversi in cassette postali di destinazione diverse, il processo di importazione verrà eseguito in parallelo, ovvero ogni coppia di file PST e cassetta postale verrà importata contemporaneamente. Analogamente, se si importano più file PST nella stessa cassetta postale, questi vengono importati contemporaneamente.
  
 **Dopo il caricamento dei file PST in Azure da parte di Microsoft, per quanto tempo vengono conservati in Azure prima dell'eliminazione?**
  
Tutti i file PST nel percorso di archiviazione di Azure dell'organizzazione, ovvero il contenitore BLOB denominato `ingestiondata`, vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nella pagina **Importa file PST** del Centro sicurezza e conformità. 
  
Significa anche che, dopo essere stati eliminati dall'area di archiviazione di Azure, i file PST non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nel Centro sicurezza e conformità. Anche se un processo di importazione potrebbe essere ancora presente nella pagina **Importa file PST** del Centro sicurezza e conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione precedenti. 
  
 **Quale versione del formato di file PST è supportata per l'importazione in Microsoft 365?**
  
Sono disponibili due versioni del formato di file PST: ANSI e Unicode. Si consiglia di importare i file che usano il formato di file PST Unicode. Tuttavia, i file PST che usano il formato ANSI, ad esempio quelli per le lingue con un set di caratteri DBCS (Double Byte Character Set), possono essere importati anche in Microsoft 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 in [Use Drive Shipping to Import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
È anche possibile importare i file PST di Outlook 2007 e versioni successive in Office 365.
  
 **È previsto un limite alle dimensioni del messaggio durante l'importazione dei file PST?**
  
Sì. Se un file PST contiene un elemento della cassetta postale con dimensioni maggiori di 150 MB, questo elemento viene ignorato durante il processo di importazione.
  
  **In che modo il processo di importazione PST gestisce gli elementi di posta elettronica duplicati?**

Durante il processo di importazione PST viene controllata la presenza di elementi duplicati; gli elementi dei file PST non vengono copiati nella cassetta postale o nell'archivio di destinazione se è già presente un elemento corrispondente nella cartella di destinazione. Se si reimporta lo stesso file PST e si specifica una cartella di destinazione diversa (utilizzando la proprietà TargetRootFolder nel file di mapping di importazione PST) rispetto a quella specificata in un processo di importazione precedente, tutti gli elementi del file PST verranno reimportati.
 
 **Le proprietà del messaggio, ad esempio la data/ora di invio o ricezione del messaggio, l'elenco dei destinatari e altre proprietà, vengono conservate quando i file PST vengono importati in una cassetta postale di Microsoft 365?**
  
Sì. I metadati del messaggio originale non vengono modificati durante il processo di importazione
  
 **È previsto un limite al numero di livelli in una gerarchia di cartelle per un file PST da importare in una cassetta postale?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **È possibile usare la spedizione unità per importare i file PST in una cassetta postale inattiva di Microsoft 365?**
  
Sì, questa funzionalità è ora disponibile.
  
 **È possibile usare la spedizione unità per importare file PST in una cassetta postale di archiviazione online di una distribuzione ibrida di Exchange?**
  
Sì, questa funzionalità è ora disponibile. 
  
 **Si può usare la spedizione unità per importare file PST in cartelle pubbliche di Exchange Online?**
  
No. Non è possibile importare file PST nelle cartelle pubbliche.
  
 **Microsoft può cancellare i dati presenti nell'unità disco rigido prima di rispedirla al cliente?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Microsoft può distruggere l'unità disco rigido invece di rispedirla al cliente?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Quali sono gli spedizionieri supportati per la restituzione delle unità?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **Quali sono i costi di spedizione per la restituzione?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **È possibile scegliere un altro servizio di spedizione, come FedEx Custom Shipping, per spedire l'unità disco rigido a Microsoft?**
  
Sì.
  
 **Per spedire l'unità disco rigido in un altro paese sono previste particolari incombenze?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
