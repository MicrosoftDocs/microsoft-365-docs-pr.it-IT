---
title: Domande frequenti sull'importazione di file PST in Office 365
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
description: "Domande frequenti per gli amministratori sull'utilizzo del servizio di importazione di Office 365 per importare i file PST di Organizaiton in cassette postali di Office 365. "
ms.openlocfilehash: 632b82a99f1be5d38db3fb50a4b2b4d7a6369186
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083633"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Domande frequenti sull'importazione di file PST in Office 365

**Questo articolo è per gli amministratori. Si desidera importare i file PST nella propria cassetta postale? Vedere [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Di seguito sono riportate alcune domande frequenti sull'utilizzo del servizio di importazione di Office 365 per importare in blocco i file PST nelle cassette postali di Office 365. Per ulteriori informazioni su come importare i file PST, vedere [Overview of import PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Utilizzo del caricamento di rete per importare i file PST

Per istruzioni dettagliate, vedere [usare il caricamento di rete per importare i file PST in Office 365](use-network-upload-to-import-pst-files.md).
  
 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnati al ruolo di esportazione delle cassette postali in Exchange Online per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Per creare processi di importazione nel centro sicurezza & conformità, è inoltre necessario che sia vero uno dei seguenti valori:
  
- È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
> [!TIP]
> Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove è disponibile il caricamento di rete?**
  
Il caricamento di rete è attualmente disponibile negli Stati Uniti, Canada, Brasile, Regno Unito, Francia, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non vengono più visualizzati nell'elenco dei file per un processo di importazione completato nell'interfaccia di amministrazione di Microsoft 365. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa dati in Office 365** , l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 4 in [use Network upload to import your organization ' s PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Dopo aver caricato i file PST nell'area di archiviazione di Azure, per quanto tempo sono conservati in Azure prima di essere eliminati?**
  
Quando si utilizza il metodo di caricamento di rete per importare i file PST, è possibile caricarli in un contenitore BLOB di Azure denominato **ingestiondata**. Se nella pagina **importazione** del centro sicurezza & conformità non sono presenti processi di importazione in corso, tutti i file pst nel contenitore **ingestiondata** in Azure vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nel & di sicurezza Centro conformità. Questo significa anche che è necessario creare un nuovo processo di importazione nel centro sicurezza & Compliance (descritto nel passaggio 5 nelle istruzioni per il caricamento di rete) entro 30 giorni dal caricamento dei file PST in Azure. 
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non sono più visualizzati nell'elenco dei file per un processo di importazione completato nel centro sicurezza & conformità. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa** del centro sicurezza & conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. Dopo aver copiato i file PST nell'area di archiviazione di Azure, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa percentuale non soddisfa le proprie esigenze, è possibile prendere in considerazione altri metodi per la migrazione dei dati di posta elettronica a Office 365. Per ulteriori informazioni, vedere [Modalità di migrazione della posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Analogamente, se più file PST vengono importati nella stessa cassetta postale, verranno importati contemporaneamente.
  
 **Is there a message size limit when importing PST files?**
  
Sì. Se un file PST contiene un elemento della cassetta postale di dimensioni superiori a 150 MB, l'elemento verrà ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco di destinatari e altre proprietà, conservate quando i file PST vengono importati in una cassetta postale di Office 365?**
  
Sì. I metadati del messaggio originale non sono cambiati durante il processo di importazione.
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **È possibile utilizzare il caricamento di rete per importare i file PST in cartelle pubbliche in Exchange Online?**
  
No, non è possibile importare i file PST nelle cartelle pubbliche.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Utilizzo di spedizione unità per importare i file PST

Per istruzioni dettagliate, vedere [Use Drive Shipping to Import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **Quali autorizzazioni sono necessarie per creare processi di importazione nel servizio di importazione di Office 365?**
  
È necessario essere assegnati al ruolo import export delle cassette postali per importare i file PST nelle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Per ulteriori informazioni, vedere la sezione "aggiungere un ruolo a un gruppo di ruoli" o "creare un gruppo di ruoli" in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Per creare processi di importazione nel centro sicurezza & conformità, è inoltre necessario che sia vero uno dei seguenti valori:
  
- È necessario essere assegnati al ruolo destinatari di posta elettronica in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oppure
    
- È necessario essere un amministratore globale dell'organizzazione di Office 365.
    
> [!TIP]
> Valutare la possibilità di creare un nuovo gruppo di ruoli in Exchange Online specificamente progettato per l'importazione di file PST in Office 365. Per il livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importazione e esportazione delle cassette postali al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
 **Dove è disponibile l'unità di spedizione?**
  
La spedizione di unità è attualmente disponibile negli Stati Uniti, Canada, Brasile, Regno Unito, Europa, India, Asia orientale, sud-est asiatico, Giappone, Repubblica di Corea e Australia. Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
L'unità di trasporto per importare i file PST in Office 365 è disponibile tramite un contratto Microsoft Enterprise (EA). La distribuzione delle unità non è disponibile tramite un contratto di prodotti e servizi Microsoft (MPSA).
  
 **Qual è il prezzo per l'utilizzo della spedizione delle unità per importare i file PST in Office 365?**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. Per informazioni su come trovare un partner, vedere [Find Your Office 365 partner or Reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **What kind of hard drives are supported for drive shipping?**
  
Solo 2,5 pollici Solid-State Drive (SSD) o 2,5 o 3,5 pollice SATA II/III unità disco rigido interne sono supportate per l'utilizzo con il servizio di importazione di Office 365. You can use hard drives up to 10 TB. Per i processi di importazione, verrà elaborato solo il primo volume di dati nel disco rigido. The data volume must be formatted with NTFS. Quando si copiano i dati su un disco rigido, è possibile collegarlo direttamente usando un connettore SATA II/III da 2,5 pollici o 2,5 o 3,5 pollice oppure è possibile collegarlo esternamente usando un adattatore USB da 2,5 pollici SSD o 2,5 o 3,5 pollici SATA II/III.
  
> [!IMPORTANT]
> Le unità disco rigido esterne che dispongono di un adattatore USB incorporato non sono supportate dal servizio di importazione di Office 365. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Dopo che il disco rigido arriva al Data Center Microsoft, quanto tempo occorre per caricare i file PST in Azure?**
  
Dopo aver ricevuto il disco rigido in Microsoft Data Center, saranno necessari tra 7 e 10 giorni lavorativi per caricare i file PST nell'area di archiviazione di Microsoft Azure per l'organizzazione. I file PST verranno caricati in un contenitore BLOB di Azure denominato **ingestiondata**. 
  
 **Quanto tempo è necessario per importare un file PST in una cassetta postale?**
  
Dopo aver caricato i file PST nell'area di archiviazione di Azure, Office 365 analizza i dati nei file PST (in modo sicuro e sicuro) per identificare l'età degli elementi e i diversi tipi di messaggi inclusi nei file PST. Al termine dell'analisi, è possibile importare tutti i dati nei file PST o impostare filtri per controllare i dati che vengono importati. Dopo aver avviato il processo di importazione, un file PST viene importato in una cassetta postale di Office 365 a una velocità di almeno 24 GB al giorno. Se questa tariffa non soddisfa le proprie esigenze, è possibile prendere in considerazione altri metodi per importare i dati della posta elettronica in Office 365. Per ulteriori informazioni, vedere [Modalità di migrazione della posta elettronica a Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Analogamente, se più file PST vengono importati nella stessa cassetta postale, verranno importati contemporaneamente.
  
 **Dopo che Microsoft carica i file PST in Azure, per quanto tempo vengono conservati in Azure prima di essere eliminati?**
  
Tutti i file PST nel percorso di archiviazione di Azure per l'organizzazione (nel contenitore BLOB denominato **ingestiondata** ) vengono eliminati 30 giorni dopo la creazione del processo di importazione più recente nella pagina **Import** del Centro sicurezza & Compliance. 
  
Questo significa anche che dopo l'eliminazione dei file PST dall'area di archiviazione di Azure, non sono più visualizzati nell'elenco dei file per un processo di importazione completato nel centro sicurezza & conformità. Anche se un processo di importazione potrebbe essere ancora elencato nella pagina **Importa** del centro sicurezza & conformità, l'elenco dei file PST potrebbe essere vuoto quando si visualizzano i dettagli dei processi di importazione meno recenti. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. Tuttavia, i file che utilizzano il formato di file PST ANSI, ad esempio quelli relativi alle lingue che utilizzano un set di caratteri a doppio byte (DBCS), possono essere importati anche in Office 365. Per ulteriori informazioni sull'importazione di file PST ANSI, vedere il passaggio 3 in [Use Drive Shipping to Import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
Sì. Se un file PST contiene un elemento della cassetta postale di dimensioni superiori a 150 MB, l'elemento verrà ignorato durante il processo di importazione.
  
 **Sono proprietà del messaggio, ad esempio quando il messaggio è stato inviato o ricevuto, l'elenco di destinatari e altre proprietà, conservate quando i file PST vengono importati in una cassetta postale di Office 365?**
  
Sì. I metadati del messaggio originale non sono cambiati durante il processo di importazione
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **È possibile utilizzare la distribuzione delle unità per importare i file PST nelle cartelle pubbliche in Exchange Online?**
  
No, non è possibile importare i file PST nelle cartelle pubbliche.
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Microsoft può tagliuzzare il disco rigido invece di rispedirlo a me?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Quali servizi di corriere sono supportati per la spedizione di andata e ritorno?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **Quali sono i costi di spedizione restituiti?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **È possibile utilizzare un servizio di spedizione corriere personalizzato, ad esempio la spedizione personalizzata FedEx, per spedire l'unità disco rigido a Microsoft?**
  
Sì.
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
