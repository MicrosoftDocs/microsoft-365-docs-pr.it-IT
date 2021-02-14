---
title: Creare e gestire le cassette postali inattive
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come conservare il contenuto delle cassette postali eliminate utilizzando la funzionalità delle cassette postali inattive in Office 365.
ms.openlocfilehash: 286c1b363f7ceae42d7eaef13635ccf037bb4b21
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127543"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Creare e gestire le cassette postali inattive

Microsoft 365 consente di conservare il contenuto delle cassette postali eliminate. Questa funzionalità è denominata [cassette postali inattive](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. Una cassetta postale diventa inattiva quando un blocco per controversia legale o un criterio di conservazione (creato nel Centro sicurezza e conformità in Office 365 o Microsoft 365) viene applicato alla cassetta postale prima che l'account utente corrispondente venga eliminato. I contenuti di una cassetta postale inattiva vengono mantenuti per tutta la durata del blocco applicato alla cassetta postale prima che fosse resa inattiva. In questo modo gli amministratori, i responsabili della conformità e i responsabili dei record possono utilizzare Ricerca contenuto per cercare ed esportare il contenuto di una cassetta postale inattiva. Le cassette postali inattive non possono ricevere posta elettronica e non vengono visualizzate nella rubrica condivisa o in altri elenchi dell'organizzazione.
  
> [!IMPORTANT]
> Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, stiamo annunciando il ritiro delle In-Place blocchi nell'interfaccia di amministrazione di Exchange. Ciò significa che è necessario utilizzare i blocchi per controversia legale e i criteri di conservazione per creare una cassetta postale inattiva. A partire dal 1° luglio 2020 non sarà possibile creare nuovi blocchi In-Place in Exchange Online. Tuttavia, sarà comunque possibile modificare la durata del blocco di un'In-Place blocco su una cassetta postale inattiva. Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile modificare la durata del blocco. You'll only be able to delete an inactive mailbox by removing the In-Place Hold. Le cassette postali inattive esistenti In-Place conservazione verranno mantenute finché il blocco non viene rimosso. Per ulteriori informazioni sul ritiro dei blocchi In-Place, vedere [Ritiro degli strumenti legacy di eDiscovery.](legacy-ediscovery-retirement.md)
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>Preparazione prima della creazione di una cassetta postale inattiva

- Per rendere inattiva una cassetta postale, è necessario assegnare una licenza di Exchange Online Piano 2 in modo che sia possibile applicare un blocco per controversia legale o un criterio di conservazione alla cassetta postale prima che venga eliminata. Le licenze di Exchange Online Piano 2 fanno parte di un abbonamento a Office 365 Enterprise E3 ed E5. Se a una cassetta postale è assegnata una licenza di Exchange Online Piano 1 o chiosco Exchange Online (che fanno parte rispettivamente di una sottoscrizione a Office 365 E1 e F1), è necessario assegnarle una licenza Archiviazione Exchange Online separata in modo che sia possibile applicare un blocco alla cassetta postale prima che venga eliminata. Per ulteriori informazioni, vedere [Archiviazione Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).

- Le licenze associate alla cassetta postale di Exchange Online eliminata saranno disponibili dopo l'eliminazione dell'account utente corrispondente. È quindi possibile [assegnare tali licenze a un altro utente.](../admin/manage/assign-licenses-to-users.md)

- Se un blocco per controversia legale o un criterio di conservazione (configurato per conservare o conservare ed eliminare il contenuto) non viene applicato a una cassetta postale prima che venga eliminata, il contenuto della cassetta postale non verrà conservato o individuabile. Tuttavia, è possibile recuperare la cassetta postale eliminata entro 30 giorni dall'eliminazione; se non viene recuperata entro 30 giorni, la cassetta postale e il suo contenuto vengono eliminati definitivamente.

- For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). Per ulteriori informazioni sui criteri di conservazione, vedere [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](retention.md)
  
## <a name="create-an-inactive-mailbox"></a>Creare una cassetta postale inattiva

Rendere inattiva una cassetta postale implica due passaggi: 1) applicare un blocco per controversia legale o applicare un criterio di conservazione e 2) eliminare la cassetta postale o l'account utente corrispondente. Quando la cassetta postale è inattiva, il contenuto viene conservato finché non vengono rimossi i criteri di conservazione o il blocco.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>Passaggio 1: Applicare il blocco per controversia legale a una cassetta postale o applicare un criterio di conservazione

L'applicazione del blocco per controversia legale a una cassetta postale o l'applicazione di un criterio di conservazione (configurato per conservare o conservare ed eliminare il contenuto) mantiene il contenuto nella cassetta postale prima che venga eliminata. Con entrambi i tipi di blocchi viene conservato tutto il contenuto della cassetta postale, compresi gli elementi eliminati e le versioni originali degli elementi modificati. Gli elementi eliminati e modificati vengono conservati nella cassetta postale inattiva per un determinato periodo oppure finché non viene eliminata definitivamente la cassetta postale inattiva rimuovendo il blocco o i criteri di conservazione applicati alla cassetta postale inattiva.
  
Se un blocco è già applicato a una cassetta postale o se un criterio di conservazione è già applicato a una cassetta postale, è necessario eliminare l'account utente corrispondente come illustrato nel passaggio 2.
  
Per le procedure dettagliate per applicare il blocco per controversia legale a una cassetta postale o l'applicazione di un criterio di conservazione, vedere:
  
- [Applicare un blocco per controversia legale a una cassetta postale](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Informazioni sui criteri di conservazione e sulle etichette di conservazione in Office 365](retention.md)
    
> [!NOTE]
> Per i blocchi per controversia legale e i criteri di conservazione, è possibile creare un blocco indefinito o in base al tempo. In caso di un blocco indefinito, il contenuto della cassetta postale inattiva viene conservato per sempre, finché il blocco non viene rimosso o finché la durata del blocco non viene modificata. Una volta rimosso il blocco o il criterio di conservazione (presumendo che la cassetta postale sia stata eliminata più di 30 giorni prima), la cassetta postale inattiva verrà contrassegnata per l'eliminazione definitiva e il suo contenuto non sarà conservato e non potrà essere trovato. In un blocco basato sul tempo o in un criterio di conservazione, è necessario specificare la durata del blocco. La durata si applica ai singoli elementi e viene calcolata a partire dalla data in cui ciascun elemento è stato ricevuto o creato. Dopo che il blocco per un elemento della cassetta postale scade e che tale elemento viene spostato o si trova nella cartella Elementi ripristinabili nella cassetta postale inattiva, l'elemento viene definitivamente eliminato (cancellato) dalla cassetta postale inattiva dopo la scadenza del periodo di conservazione dell'elemento eliminato. 
  
### <a name="step-2-delete-the-mailbox"></a>Passaggio 2: Eliminare la cassetta postale

Dopo l'archiviazione della cassetta postale o l'applicazione di un criterio di conservazione, il passaggio successivo consiste nell'eliminare la cassetta postale. Il modo migliore per eliminare una cassetta postale è eliminare l'account utente corrispondente nell'interfaccia di amministrazione di Microsoft 365. Per informazioni sull'eliminazione di account utente, vedere [Eliminare un utente dall'organizzazione.](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)
  
> [!NOTE]
> È inoltre possibile eliminare la cassetta postale utilizzando il cmdlet **Remove-Mailbox** in PowerShell di Exchange Online. Per ulteriori informazioni, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Visualizzare un elenco di cassette postali inattive

Per visualizzare un elenco delle cassette postali inattive nell'organizzazione:
  
1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali di un account amministratore dell'organizzazione. 
    
2. Fare clic **su Conservazione governance** delle  >  **informazioni.**
    
3. Nella pagina **Conservazione fare** clic su **Altri** puntini di sospensione della barra di spostamento e quindi su Cassette ![ postali ](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) **inattive.**
    
    ![Nella pagina Conservazione, fare clic su Altro e quindi su Cassette postali inattive per visualizzare un elenco delle cassette postali inattive](../media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    Viene **visualizzata la pagina** Cassette postali inattive. Si noti il numero totale di cassette postali inattive nell'organizzazione. 
    
    ![Viene visualizzato un elenco di tutte le cassette postali inattive nell'organizzazione](../media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
In alternativa, è possibile eseguire il seguente comando in PowerShell di Exchange Online per visualizzare l'elenco delle cassette postali inattive.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

È possibile fare clic sull'icona Esporta risultati di ricerca per visualizzare o scaricare un file CSV contenente informazioni aggiuntive sulle cassette postali ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)  inattive nell'organizzazione. 
  
È inoltre possibile eseguire il comando seguente per esportare l'elenco delle cassette postali inattive e altre informazioni in un file CSV. In questo esempio, il file CSV viene creato nella directory corrente.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> È possibile che una cassetta postale inattiva abbia lo stesso indirizzo SMTP di una cassetta postale utente attiva. In questo caso, il valore della proprietà **DistinguishedName** o **ExchangeGuid** può essere utilizzato per identificare in modo univoco una cassetta postale inattiva. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Ricerca ed esportazione del contenuto di una cassetta postale inattiva

È possibile accedere al contenuto della cassetta postale inattiva utilizzando lo strumento Ricerca contenuto nel Centro sicurezza & conformità. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:
  
- [Ricerca contenuto in Office 365](content-search.md)
    
- [Esportare i risultati della Ricerca contenuto](export-search-results.md)
    
Ecco alcuni aspetti da tenere presenti quando si eseguono ricerche nelle cassette postali inattive.
  
- Se una ricerca di contenuto include una cassetta postale utente e tale cassetta postale viene resa inattiva, la ricerca di contenuto continuerà a cercare nella cassetta postale inattiva quando si esegue nuovamente la ricerca dopo che diventa inattiva.
    
- In alcuni casi, un utente può avere una cassetta postale attiva e una cassetta postale inattiva con lo stesso indirizzo SMTP. In questo caso, verrà cercata solo la cassetta postale specifica selezionata come posizione per una ricerca di contenuto. In altre parole, se si aggiunge la cassetta postale di un utente a una ricerca, non è possibile presupporre che verranno cercate sia le cassette postali attive che quelle inattive. verrà cercata solo la cassetta postale aggiunta esplicitamente alla ricerca.
    
- È consigliabile evitare di avere una cassetta postale attiva e una cassetta postale inattiva con lo stesso indirizzo SMTP. Se è necessario riutilizzare l'indirizzo SMTP attualmente assegnato a una cassetta postale inattiva, è consigliabile recuperare la cassetta postale inattiva o ripristinare il contenuto di una cassetta postale inattiva in una cassetta postale attiva (o l'archivio di una cassetta postale attiva), quindi eliminare la cassetta postale inattiva.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Modificare la durata del blocco per una cassetta postale inattiva

Dopo aver reso inattiva una cassetta postale, è possibile modificare la durata del blocco o il criterio di conservazione applicato alla cassetta postale inattiva. Per le procedure dettagliate, vedere Modificare la durata del blocco per una cassetta postale [inattiva in Office 365.](change-the-hold-duration-for-an-inactive-mailbox.md)
  
## <a name="recover-an-inactive-mailbox"></a>Recuperare una cassetta postale inattiva

Se l'ex dipendente torna nell'organizzazione oppure se un nuovo dipendente viene assunto per ricoprire il ruolo del dipendente rimosso, è possibile recuperare i contenuti della cassetta postale inattiva. Quando si recupera una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura della cassetta postale vengono conservati e la cassetta postale viene collegata a un nuovo account utente. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Per procedure dettagliate e ulteriori informazioni su come eseguire il ripristino di una cassetta postale inattiva, vedere Recuperare una cassetta postale [inattiva in Office 365.](recover-an-inactive-mailbox.md)
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Ripristinare il contenuto di una cassetta postale inattiva in un'altra cassetta postale

Se un altro dipendente assume le responsabilità di un ex dipendente o se un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando eDiscovery, i suoi contenuti possono essere ripristinati in un'altra cassetta postale oppure può essere recuperata o eliminata in un secondo momento. Per procedure dettagliate, vedere Ripristinare una cassetta postale [inattiva in Office 365.](restore-an-inactive-mailbox.md)
  
## <a name="delete-an-inactive-mailbox"></a>Eliminare una cassetta postale inattiva

Se non è più necessario conservare il contenuto di una cassetta postale inattiva, è possibile eliminare definitivamente la cassetta postale inattiva rimuovendo il blocco o rimuovendo il criterio di conservazione applicato alla cassetta postale inattiva. Se la cassetta postale è stata eliminata più di 30 giorni prima, verrà contrassegnata per l'eliminazione definitiva dopo la rimozione del blocco e non sarà più recuperabile. Se la cassetta postale è stata eliminata negli ultimi 30 giorni, è ancora possibile recuperarla dopo aver rimosso il blocco o il criterio di conservazione. Per le procedure dettagliate per la rimozione di un blocco o di un criterio di conservazione per eliminare definitivamente una cassetta postale inattiva, vedere Eliminare una cassetta postale [inattiva.](delete-an-inactive-mailbox.md)
