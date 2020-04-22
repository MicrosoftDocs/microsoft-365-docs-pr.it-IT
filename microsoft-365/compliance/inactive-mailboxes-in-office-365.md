---
title: Panoramica delle cassette postali inattive
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
description: Informazioni su come conservare il contenuto delle cassette postali per gli ex dipendenti trasformando la cassetta postale in una cassetta postale inattiva. A tale scopo, è possibile inserire la cassetta postale su blocco per controversia legale o applicare un criterio di conservazione Microsoft 365 alla cassetta postale e quindi rimuovere l'account Microsoft 365 corrispondente.
ms.openlocfilehash: 1e6851d628af861982d0447f6b592d4b1aa8bba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637928"
---
# <a name="overview-of-inactive-mailboxes"></a>Panoramica delle cassette postali inattive

L'organizzazione potrebbe dover conservare l'indirizzo di posta elettronica di dipendenti precedenti dopo che lasciano l'organizzazione. In base ai requisiti di conservazione dell'organizzazione, potrebbe essere necessario conservare il contenuto della cassetta postale per pochi mesi o anni dopo il termine dell'impiego oppure potrebbe essere necessario conservare il contenuto della cassetta postale all'infinito. Indipendentemente dal tempo necessario per mantenere la posta elettronica, è possibile creare cassette postali inattive per mantenere la cassetta postale di ex dipendenti. 
  
## <a name="what-are-inactive-mailboxes"></a>Cosa sono le cassette postali inattive?

Quando un dipendente lascia l'organizzazione (o prosegue un congedo prolungato), è possibile rimuovere il proprio account Microsoft 365. I dati della cassetta postale del dipendente vengono conservati per 30 giorni dopo che l'account è stato rimosso. Durante questo periodo, è comunque possibile ripristinare i dati della cassetta postale eliminando l'account. Dopo 30 giorni, i dati vengono rimossi definitivamente.
  
Tuttavia, se l'organizzazione deve conservare il contenuto delle cassette postali per gli ex dipendenti, è possibile trasformare la cassetta postale in una cassetta postale inattiva posizionando la cassetta postale sul blocco per controversia legale o applicando un criterio di conservazione di Microsoft 365 alla cassetta postale nel centro sicurezza & compliance e quindi rimuovendo l'account Microsoft 365 corrispondente. I contenuti di una cassetta postale inattiva vengono conservati per la durata del blocco per controversia legale posto sulla cassetta postale o il periodo di conservazione del criterio di conservazione applicato all'oggetto prima che la cassetta postale sia stata eliminata. You can still recover the corresponding user account for a 30-day period. Tuttavia, dopo 30 giorni, la cassetta postale inattiva viene conservata in Microsoft 365 fino a quando non viene rimosso il blocco o il criterio di conservazione. 
  
> [!IMPORTANT]
> Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, si annuncia la prepensionamento delle archiviazioni sul posto nell'interfaccia di amministrazione di Exchange. Questo significa che è necessario utilizzare i criteri di conservazione per controversia legale e Microsoft 365 per creare una cassetta postale inattiva. A partire dal 1 ° luglio 2020 non è possibile creare nuove archiviazioni sul posto in Exchange Online. Tuttavia, sarà comunque possibile modificare la durata del blocco di un blocco sul posto posto in una cassetta postale inattiva. Tuttavia, a partire dal 1 ° ottobre 2020, non sarà possibile modificare la durata del blocco. È possibile eliminare una cassetta postale inattiva solo rimuovendo il blocco sul posto. Le cassette postali inattive esistenti che si trovano sul blocco sul posto continueranno a essere conservate finché il blocco non viene rimosso. Per ulteriori informazioni sulla ritirata delle archiviazioni sul posto, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md).
  
## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Cassette postali inattive e criteri di conservazione Microsoft 365

Oltre alla conservazione per controversia legale, l'utilizzo della nuova caratteristica criteri di ritenzione di Microsoft 365 nel centro sicurezza & conformità è un altro modo per rendere inattiva una cassetta postale. To use a retention policy to make an inactive mailbox: 
  
- Deve essere configurato in modo da conservare il contenuto o conservarlo e quindi eliminarlo. Se un criterio di conservazione è configurato per eliminare solo il contenuto, una cassetta postale a cui viene applicato il criterio non diverrà inattiva quando la cassetta postale viene eliminata.

- Deve essere applicato alle cassette postali di Exchange o a percorsi di Skype for Business (perché i contenuti correlati di Skype vengono archiviati nella cassetta postale dell'utente). 
    
- Può essere basato su query affinché conservi quindi solo elementi corrispondenti a una query di ricerca. 
    
Per ulteriori informazioni sulla configurazione dei criteri di conservazione, vedere [Overview of Retention Policies](retention-policies.md).
  
Se si utilizza un criterio di conservazione per creare una cassetta postale inattiva, Microsoft 365 continua a elaborare il criterio di conservazione nella cassetta postale inattiva. Questo significa che se i criteri di conservazione sono configurato per mantenere ed eliminare contenuto, gli elementi verranno spostati nella cartella Elementi ripristinabili alla scadenza del periodo di conservazione e verranno alla fine eliminati dalla cassetta postale inattiva. Se i criteri di conservazione non sono configurati per gli elementi eliminati, gli elementi che non sono stati eliminati definitivamente dall'utente (prima che la cassetta postale è stata resa inattiva) non verranno spostati nella cartella elementi ripristinabili e verranno mantenuti indefinitamente dopo che la cassetta postale diventa inattiva. 
  
È possibile prendere in considerazione la creazione di un criterio di conservazione Microsoft 365 specifico per le cassette postali inattive. Vengono elencati di seguito alcuni motivi di tale operazione e considerazioni importanti da valutare:
  
- È possibile configurare i criteri di conservazione per conservare il contenuto della cassetta postale solo purché necessari per soddisfare i requisiti dell'organizzazione per ex dipendenti.
    
- È un ottimo metodo per identificare le cassette postali inattive perché il criterio di conservazione viene applicato solo alle cassette postali inattive.
    
- È possibile identificare rapidamente i criteri di conservazione assegnati alle cassette postali inattive nell'organizzazione. In questo modo è più facile modificare le impostazioni di conservazione (o eliminazione), se necessario. Sarà inoltre più facile eliminare definitivamente una cassetta postale inattiva perché è possibile rimuoverla dal criterio utilizzando il Centro sicurezza & conformità. In caso contrario, è necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva o utilizzare la sicurezza & Compliance Center PowerShell per escludere una cassetta postale inattiva da un criterio di conservazione Microsoft 365 a livello di organizzazione.
    
- Se si crea un criterio di conservazione Microsoft 365 specifico per le cassette postali inattive, è possibile aggiungere un massimo di 1.000 cassette postali al criterio. Se si è un'organizzazione di grandi dimensioni, potrebbe essere necessario creare più criteri di conservazione di Microsoft 365 da utilizzare per le cassette postali inattive.

> [!CAUTION]
> Se si utilizza un criterio di conservazione per rendere inattiva una cassetta postale, non modificare o rimuovere il nome dell'entità utente (UPN) per la cassetta postale prima di eliminare l'account utente corrispondente. Inoltre, non modificare l'indirizzo SMTP principale (derivato dall'UPN) oppure rimuovere l'indirizzo di posta elettronica dall'elenco degli indirizzi SMTP secondari associati alla cassetta postale prima di rendere inattiva la cassetta postale. Se si modifica l'UPN o gli indirizzi di posta elettronica (che sono stati assegnati alla cassetta postale nel momento in cui è stato applicato il criterio di conservazione) e quindi si elimina l'account utente per rendere la cassetta postale inattiva, non sarà possibile eliminare la cassetta postale inattiva quando non è più necessario conservarla. Ciò è dovuto al fatto che non è possibile rimuovere la cassetta postale inattiva dal criterio di conservazione utilizzando un UPN o un indirizzo di posta elettronica (per identificare la cassetta postale inattiva) diversa da quella esistente quando il criterio di conservazione è stato inizialmente applicato alla cassetta postale. Per ulteriori informazioni sull'eliminazione di cassette postali inattive, vedere [eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md).
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Le cassette postali inattive e i blocchi dei casi di eDiscovery

Se una conservazione associata a un caso di eDiscovery nel centro sicurezza & conformità è posizionata su una cassetta postale e quindi viene eliminata la cassetta postale o l'account dell'utente, la cassetta postale diventa una cassetta postale inattiva. However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Inoltre, non è possibile creare un blocco di eDiscovery basato sul tempo. Questo significa che il contenuto di una cassetta postale inattiva viene conservato per sempre o fino a quando il blocco non viene rimosso e la cassetta postale inattiva viene eliminata. Pertanto, si consiglia di utilizzare un blocco per controversia legale o un criterio di conservazione per le cassette postali inattive.
  
Per ulteriori informazioni sui casi di eDiscovery e sulle esenzioni, vedere [eDiscovery Cases](ediscovery-cases.md).

## <a name="inactive-mailboxes-and-labels"></a>Cassette postali inattive ed etichette

Le etichette consentono di classificare i dati della posta elettronica nell'organizzazione per la governance e di applicare le regole di conservazione in base alla classificazione. Un'etichetta può essere applicata a un elemento di posta elettronica manualmente dagli utenti o automaticamente dagli amministratori e a un elemento di posta elettronica può essere assegnata una sola etichetta. Se a un singolo elemento di posta elettronica della cassetta postale di un utente è assegnata un'etichetta (ed è configurata per conservare o conservare e quindi eliminare l'elemento) e la cassetta postale o l'account dell'utente viene eliminato, la cassetta postale diventa una cassetta postale inattiva. Come per i blocchi dei casi di eDiscovery, non è consigliabile utilizzare le etichette per rendere inattiva una cassetta postale. Al contrario, si consiglia di utilizzare un blocco per controversia legale o un criterio di conservazione. Nel caso di etichette, è possibile che non si renda conto che è stata applicata un'etichetta a un elemento di posta elettronica e quindi si rende involontariamente una cassetta postale inattiva quando si elimina l'account dell'utente. 
  
Per ulteriori informazioni, vedere [Panoramica delle etichette in Office 365](labels.md).
  
## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Cassette postali inattive e archivi in espansione automatica

Non è possibile ripristinare o ripristinare una cassetta postale inattiva configurata con un archivio in espansione automatica. Nei casi in cui è necessario ripristinare i dati da una cassetta postale inattiva con un archivio in espansione automatica, si consiglia di utilizzare lo strumento di ricerca contenuto per esportare i dati dalla cassetta postale e quindi importarli in un'altra cassetta postale. Per istruzioni dettagliate su come eseguire la ricerca in una cassetta postale inattiva ed esportare i risultati della ricerca, vedere:

- [Ricerca contenuto in Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search)

- [Esportare i risultati della ricerca contenuto](https://docs.microsoft.com/microsoft-365/compliance/export-search-results)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Exchange MRM

Se un criterio di conservazione di Exchange (la funzionalità di gestione dei record di messaggistica, o di messaggistica istantanea in Exchange Online) è stato applicato alla cassetta postale quando è stato reso inattivo, tutti i criteri di eliminazione (ovvero i tag di conservazione configurati con un'azione di conservazione **Delete** ) continueranno a essere elaborati nella cassetta postale inattiva. Questo significa che gli elementi che sono contrassegnati con un criterio di eliminazione verranno spostati nella cartella Elementi ripristinabili quando scade il periodo di conservazione. Questi elementi vengono eliminati dalla cassetta postale inattiva quando scade la durata di attesa. Se la durata di attesa non è specificata per la cassetta postale inattiva, gli elementi della cartella Recupera elementi verranno conservati all'infinito. 
  
Al contrario, qualsiasi criterio di archiviazione (vale a dire tag di conservazione configurati con un'azione conservazione **MoveToArchive** ) incluso in un criterio di conservazione assegnato a una cassetta postale inattiva viene ignorato. Questo significa che gli elementi in una cassetta postale inattiva contrassegnati con un criterio di archiviazione rimarranno nella cassetta postale principale quando scade il periodo di conservazione. Non vengono spostati nella cassetta postale di archiviazione o nella cartella Elementi ripristinabili nella cassetta postale di archiviazione. Verranno conservati a tempo indeterminato. 
  
## <a name="creating-an-inactive-mailbox"></a>Creazione di una cassetta postale inattiva

Per rendere inattiva una cassetta postale, deve essere assegnata una licenza di Exchange Online piano 2 (o una licenza di Exchange Online piano 1 con una licenza per il componente aggiuntivo di archiviazione Exchange Online), in modo che sia possibile applicare un blocco per controversia legale o un criterio di conservazione Microsoft 365 alla cassetta postale prima che venga eliminata. Dopo che la cassetta postale è stata eliminata, qualsiasi licenza di Exchange Online associata sarà disponibile per l'assegnazione a un nuovo utente.
  
Nella tabella seguente viene riepilogato il processo di creazione di una cassetta postale inattiva per diversi scenari di conservazione. Per ulteriori informazioni, vedere [gestire le cassette postali inattive](create-and-manage-inactive-mailboxes.md).
  
|**Per...**|**Eseguire questa operazione...**|**Risultato**|
|:-----|:-----|:-----|
|Conservare il contenuto della cassetta postale a tempo indeterminato dopo che un impiegato lascia l'organizzazione  <br/> | Inserire la cassetta postale sul blocco per controversia legale o applicare un criterio di conservazione Microsoft 365 (configurato per conservare il contenuto) alla cassetta postale.  <br/>  Non specificare la durata di un blocco per il blocco per controversia legale oppure non configurare il criterio di conservazione per eliminare gli elementi. In alternativa, è possibile utilizzare un criterio di conservazione che conserva gli elementi per sempre.  <br/>  Rimuovere l'account Microsoft 365 dell'utente.  <br/> |Tutto il contenuto della cassetta postale inattiva, inclusi gli elementi nella cartella elementi ripristinabili, viene mantenuto a tempo indeterminato.  <br/> |
|Conservare il contenuto della cassetta postale per un periodo specifico dopo che un impiegato lascia l'organizzazione e quindi eliminarlo  <br/> | Applicare un criterio di conservazione Microsoft 365 alla cassetta postale.  <br/>  Configurare il criterio di conservazione per mantenere e quindi eliminare gli elementi al termine della scadenza del periodo di conservazione.  <br/>  Rimuovere l'account Microsoft 365 dell'utente.  <br/> |Quando il periodo di conservazione per un elemento della cassetta postale scade, l'elemento viene spostato nella cartella elementi ripristinabili e quindi viene eliminato definitivamente (eliminato) dalla cassetta postale inattiva quando scade il periodo di conservazione degli elementi eliminati (per le cassette postali di Exchange). Il periodo di conservazione del criterio di conservazione di Microsoft 365 può essere configurato in base alla data originale di ricezione o creazione di un elemento della cassetta postale o al momento dell'Ultima modifica.  <br/> |
   
**Nota:** Se un blocco per controversia legale è già stato inserito in una cassetta postale o se un criterio di conservazione Microsoft 365 (configurato per conservare o conservare e quindi eliminare il contenuto) è già applicato alla cassetta postale, è necessario eliminare l'account utente corrispondente per creare una cassetta postale inattiva. 
  
## <a name="managing-inactive-mailboxes"></a>Gestione di una cassetta postale inattiva

Dopo aver reso inattiva una cassetta postale, è possibile eseguire varie attività di gestione nelle cassette postali inattive.
  
- **Modificare la durata del blocco per una cassetta postale inattiva** Dopo aver reso inattiva una cassetta postale, è possibile modificare la durata del blocco per controversia legale o il criterio di conservazione Microsoft 365 applicato alla cassetta postale inattiva. Per le procedure dettagliate, vedere [modificare la durata del blocco per una cassetta postale inattiva](change-the-hold-duration-for-an-inactive-mailbox.md).

  > [!NOTE]
  > Non è possibile applicare altri criteri di conservazione a una cassetta postale inattiva. È possibile modificare la durata di conservazione di un criterio di conservazione esistente applicato alla cassetta postale inattiva.
    
- **Recuperare una cassetta postale inattiva** Se un ex dipendente (o un dipendente in congedo) torna nell'organizzazione oppure se un nuovo dipendente viene assunto per ricoprire il ruolo del precedente dipendente, è possibile recuperare i contenuti della cassetta postale inattiva. Quando si ripristina una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura delle cartelle della cassetta postale inattiva vengono mantenuti e la cassetta postale è collegata a un nuovo account utente. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Per le procedure dettagliate e le informazioni su ciò che accade quando si recupera una cassetta postale inattiva, vedere [recuperare una cassetta postale inattiva](recover-an-inactive-mailbox.md).
    
- **Ripristinare una cassetta postale inattiva** Se un altro dipendente assume le responsabilità di un ex dipendente o se un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane inattiva. La cassetta postale inattiva può comunque essere cercata utilizzando gli strumenti di eDiscovery, i suoi contenuti possono essere ripristinati in un'altra cassetta postale e può essere recuperata o eliminata in un secondo momento. Per le procedure dettagliate, vedere [ripristinare una cassetta postale inattiva](restore-an-inactive-mailbox.md).
    
- **Eliminare una cassetta postale inattiva** Quando non è più necessario conservare il contenuto di una cassetta postale inattiva, è possibile eliminarlo definitivamente rimuovendo tutti i criteri di conservazione o Microsoft 365 che sono stati applicati alla cassetta postale inattiva. Se una cassetta postale è stata resa inattiva da più di 30 giorni, verrà contrassegnata per l'eliminazione definitiva dopo aver rimosso il blocco. Se la cassetta postale è stata resa inattiva negli ultimi 30 giorni, è possibile attivarla di nuovo dopo aver rimosso il blocco o il criterio di conservazione. Per le procedure dettagliate, vedere [eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md).
