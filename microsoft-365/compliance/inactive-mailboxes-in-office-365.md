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
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come conservare il contenuto della cassetta postale per i dipendenti precedenti trasformando la cassetta postale in una cassetta postale inattiva.
ms.openlocfilehash: 7a10b3327dda148c3328f53826a81464b86a7a0a
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423617"
---
# <a name="overview-of-inactive-mailboxes"></a>Panoramica delle cassette postali inattive

L'organizzazione potrebbe dover conservare l'indirizzo di posta elettronica di dipendenti precedenti dopo che lasciano l'organizzazione. In base ai requisiti di conservazione dell'organizzazione, potrebbe essere necessario conservare il contenuto della cassetta postale per pochi mesi o anni dopo il termine dell'impiego oppure potrebbe essere necessario conservare il contenuto della cassetta postale all'infinito. Indipendentemente dal tempo necessario per conservare la posta elettronica, è possibile creare cassette postali inattive per conservare la cassetta postale di ex dipendenti.

## <a name="what-are-inactive-mailboxes"></a>Cosa sono le cassette postali inattive?

Quando un dipendente lascia l'organizzazione (o va in un congedo prolungato), è possibile rimuovere il proprio account Microsoft 365. I dati della cassetta postale del dipendente vengono conservati per 30 giorni dopo la rimozione dell'account. Durante questo periodo, è comunque possibile recuperare i dati della cassetta postale annullando l'eliminazione dell'account. Dopo 30 giorni, i dati vengono rimossi definitivamente.

Tuttavia, se l'organizzazione deve conservare il contenuto della cassetta postale per i dipendenti precedenti, è possibile trasformare la cassetta postale in una cassetta postale inattiva attivando il blocco per controversia legale o applicando un criterio di conservazione di Microsoft 365 alla cassetta postale nel Centro sicurezza & conformità e quindi rimuovendo l'account di Microsoft 365 corrispondente. Il contenuto di una cassetta postale inattiva viene conservato per tutta la durata del blocco per controversia legale applicato alla cassetta postale o del periodo di conservazione del criterio di conservazione applicato prima dell'eliminazione della cassetta postale. You can still recover the corresponding user account for a 30-day period. Tuttavia, dopo 30 giorni, la cassetta postale inattiva viene conservata in Microsoft 365 fino alla rimozione del blocco o dei criteri di conservazione.

> [!IMPORTANT]
> Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, stiamo annunciando il ritiro delle In-Place blocchi nell'interfaccia di amministrazione di Exchange. Ciò significa che è necessario utilizzare i blocchi per controversia legale e i criteri di conservazione di Microsoft 365 per creare una cassetta postale inattiva. A partire dal 1° luglio 2020 non sarà possibile creare nuovi blocchi In-Place in Exchange Online. Tuttavia, sarà comunque possibile modificare la durata del blocco di un'In-Place blocco su una cassetta postale inattiva. Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile modificare la durata del blocco. You'll only be able to delete an inactive mailbox by removing the In-Place Hold. Le cassette postali inattive esistenti In-Place conservazione verranno mantenute finché il blocco non viene rimosso. Per ulteriori informazioni su quando In-Place esenzioni verranno ritirate, vedere [Ritiro degli strumenti legacy di eDiscovery.](legacy-ediscovery-retirement.md)

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Cassette postali inattive e criteri di conservazione di Microsoft 365

Oltre al blocco per controversia legale, l'uso della nuova funzionalità dei criteri di conservazione di Microsoft 365 nel Centro conformità Microsoft 365 è un altro modo per rendere inattiva una cassetta postale. To use a retention policy to make an inactive mailbox:

- Deve essere configurato per conservare o conservare ed eliminare il contenuto. Se un criterio di conservazione è configurato per eliminare solo il contenuto, una cassetta postale a cui viene applicato il criterio non diventerà inattiva quando l'account utente viene eliminato.

- Deve essere applicato alle cassette postali di Exchange o a percorsi di Skype for Business (perché i contenuti correlati di Skype vengono archiviati nella cassetta postale dell'utente).

- Può essere basato su query affinché conservi quindi solo elementi corrispondenti a una query di ricerca.

Per ulteriori informazioni sui criteri di conservazione, vedere [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](retention.md)

Se si utilizza un criterio di conservazione per rendere inattiva una cassetta postale, Microsoft 365 continua a elaborare i criteri di conservazione nella cassetta postale inattiva. Questo significa che se i criteri di conservazione sono configurato per mantenere ed eliminare contenuto, gli elementi verranno spostati nella cartella Elementi ripristinabili alla scadenza del periodo di conservazione e verranno alla fine eliminati dalla cassetta postale inattiva. Se il criterio di conservazione non è configurato per gli elementi eliminati, gli elementi che non sono stati eliminati definitivamente dall'utente (prima che la cassetta postale fosse resa inattiva) non verranno spostati nella cartella Elementi ripristinabili e verranno conservati a tempo indeterminato dopo che la cassetta postale diventa inattiva.

È consigliabile creare un criterio di conservazione di Microsoft 365 specifico per le cassette postali inattive. Vengono elencati di seguito alcuni motivi di tale operazione e considerazioni importanti da valutare:

- È possibile configurare i criteri di conservazione per conservare il contenuto della cassetta postale solo purché necessari per soddisfare i requisiti dell'organizzazione per ex dipendenti.

- È un buon modo per identificare le cassette postali inattive perché i criteri di conservazione verranno applicati solo alle cassette postali inattive.

- È possibile identificare rapidamente il criterio di conservazione assegnato alle cassette postali inattive nell'organizzazione. In questo modo è più semplice modificare le impostazioni di conservazione (o eliminazione), se necessario. Sarà inoltre più semplice eliminare definitivamente una cassetta postale inattiva perché è possibile rimuoverla dal criterio utilizzando il Centro sicurezza & conformità. In caso contrario, è necessario utilizzare PowerShell di Exchange Online per rimuovere un blocco per controversia legale da una cassetta postale inattiva o utilizzare PowerShell per Centro sicurezza & e conformità per escludere una cassetta postale inattiva dai criteri di conservazione di Microsoft 365 a livello di organizzazione.

- Se si crea un criterio di conservazione di Microsoft 365 specifico per le cassette postali inattive, è possibile aggiungere un massimo di 1.000 cassette postali al criterio. Se si è un'organizzazione di grandi dimensioni, potrebbe essere necessario creare più criteri di conservazione di Microsoft 365 da usare per le cassette postali inattive.

> [!CAUTION]
> Se si utilizza un criterio di conservazione per rendere inattiva una cassetta postale, non modificare o rimuovere il nome dell'entità utente (UPN) per la cassetta postale prima di eliminare l'account utente corrispondente. Inoltre, non modificare l'indirizzo SMTP primario (derivato dall'UPN) o rimuovere questo indirizzo di posta elettronica dall'elenco degli indirizzi SMTP secondari associati alla cassetta postale prima di rendere inattiva la cassetta postale. Se si modifica l'UPN o gli indirizzi di posta elettronica (assegnati alla cassetta postale nel momento in cui è stato applicato il criterio di conservazione) e quindi si elimina l'account utente per rendere inattiva la cassetta postale, non sarà possibile eliminare la cassetta postale inattiva quando non sarà più necessario conservarla. Ciò è dovuto al fatto che non è possibile rimuovere la cassetta postale inattiva dal criterio di conservazione utilizzando un UPN o un indirizzo di posta elettronica (per identificare la cassetta postale inattiva) diverso da quello esistente quando il criterio di conservazione è stato inizialmente applicato alla cassetta postale. Per ulteriori informazioni sull'eliminazione delle cassette postali inattive, vedere Eliminare una cassetta postale [inattiva in Office 365.](delete-an-inactive-mailbox.md)

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Le cassette postali inattive e i blocchi dei casi di eDiscovery

Se un blocco associato a un caso di eDiscovery nel Centro sicurezza & conformità viene posizionato su una cassetta postale e quindi la cassetta postale o l'account dell'utente viene eliminato, la cassetta postale diventa una cassetta postale inattiva. However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Inoltre, non è possibile creare un blocco eDiscovery basato sul tempo. Ciò significa che il contenuto di una cassetta postale inattiva viene conservato per sempre o finché il blocco non viene rimosso e la cassetta postale inattiva viene eliminata. Pertanto, si consiglia di utilizzare un blocco per controversia legale o un criterio di conservazione per le cassette postali inattive.

Per ulteriori informazioni sui casi e sui blocchi di eDiscovery, vedere [casi di eDiscovery.](ediscovery-cases.md)

## <a name="inactive-mailboxes-and-labels"></a>Cassette postali ed etichette inattive

Le etichette di conservazione consentono di classificare i dati di posta elettronica nell'organizzazione per la governance e di applicare le regole di conservazione in base a tale classificazione. Un'etichetta di conservazione può essere applicata a un elemento di posta elettronica manualmente dagli utenti o automaticamente dagli amministratori e a un elemento di posta elettronica può essere assegnata una sola etichetta. Se a un singolo elemento di posta elettronica nella cassetta postale di un utente è assegnata un'etichetta (ed è configurato per conservare o conservare ed eliminare l'elemento) e la cassetta postale o l'account dell'utente viene eliminata, la cassetta postale diventa una cassetta postale inattiva. Analogamente ai blocchi dei casi di eDiscovery, non è consigliabile usare le etichette di conservazione per rendere inattiva una cassetta postale. È invece consigliabile utilizzare un blocco per controversia legale o un criterio di conservazione. Nel caso delle etichette di conservazione, potrebbe non rendersi conto che un'etichetta di conservazione è stata applicata a un elemento di posta elettronica e quindi creare inavvertitamente una cassetta postale inattiva quando si elimina l'account dell'utente.

Per ulteriori informazioni sui criteri di conservazione e sulle etichette di conservazione, vedere Informazioni sui criteri di conservazione e sulle [etichette di conservazione in Office 365.](retention.md)

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Cassette postali inattive e archivi con espansione automatica

Una cassetta postale inattiva configurata con un archivio con espansione automatica non può essere recuperata o ripristinata. Nelle situazioni in cui è necessario recuperare i dati da una cassetta postale inattiva con un archivio con espansione automatica, è consigliabile utilizzare lo strumento di ricerca contenuto per esportare i dati dalla cassetta postale e quindi importare in un'altra cassetta postale. Per istruzioni dettagliate per cercare una cassetta postale inattiva ed esportare i risultati della ricerca, vedere:

- [Ricerca contenuto](content-search.md)

- [Esportare i risultati della ricerca di contenuto](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Le cassette postali inattive e i criteri di conservazione di Exchange MRM

Se un criterio di conservazione di Exchange (la funzionalità Gestione record di messaggistica o Gestione record di messaggistica in Exchange Online) è stato applicato alla cassetta postale quando è stata resa inattiva, tutti i criteri di eliminazione (che sono tag di conservazione configurati con un'azione di conservazione Delete) continueranno **a** essere elaborati nella cassetta postale inattiva. Questo significa che gli elementi che sono contrassegnati con un criterio di eliminazione verranno spostati nella cartella Elementi ripristinabili quando scade il periodo di conservazione. Questi elementi vengono eliminati dalla cassetta postale inattiva quando scade la durata di attesa. Se la durata di attesa non è specificata per la cassetta postale inattiva, gli elementi della cartella Recupera elementi verranno conservati all'infinito.

Al contrario, qualsiasi criterio di archiviazione (vale a dire tag di conservazione configurati con un'azione conservazione **MoveToArchive** ) incluso in un criterio di conservazione assegnato a una cassetta postale inattiva viene ignorato. Questo significa che gli elementi in una cassetta postale inattiva contrassegnati con un criterio di archiviazione rimarranno nella cassetta postale principale quando scade il periodo di conservazione. Non vengono spostati nella cassetta postale di archiviazione o nella cartella Elementi ripristinabili nella cassetta postale di archiviazione. Verranno conservati a tempo indeterminato.

## <a name="creating-an-inactive-mailbox"></a>Creazione di una cassetta postale inattiva

Per rendere inattiva una cassetta postale, è necessario assegnare una licenza di Exchange Online Piano 2 (o una licenza di Exchange Online Piano 1 con una licenza del componente aggiuntivo Archiviazione Exchange Online) in modo che un blocco per controversia legale o i criteri di conservazione di Microsoft 365 possano essere applicati alla cassetta postale prima che venga eliminata. Dopo l'eliminazione dell'account utente, tutte le licenze di Exchange Online associate all'account utente saranno disponibili per l'assegnazione a un nuovo utente.

Nella tabella seguente viene riepilogato il processo di creazione di una cassetta postale inattiva per diversi scenari di conservazione. Per ulteriori informazioni, vedere [Gestire le cassette postali inattive.](create-and-manage-inactive-mailboxes.md)

****

|A...|Eseguire questa operazione...|Risultato|
|---|---|---|
|Conservare il contenuto della cassetta postale a tempo indeterminato dopo che un impiegato lascia l'organizzazione|Applicare alla cassetta postale il blocco per controversia legale o applicare un criterio di conservazione di Microsoft 365 (configurato per conservare il contenuto) alla cassetta postale. <br/> Non specificare una durata del blocco per il blocco per controversia legale o non configurare i criteri di conservazione per eliminare gli elementi. In alternativa, è possibile utilizzare un criterio di conservazione che conserva gli elementi per sempre. <br/> Rimuovere l'account di Microsoft 365 dell'utente.|Tutto il contenuto della cassetta postale inattiva, inclusi gli elementi nella cartella Elementi ripristinabili, viene conservato a tempo indeterminato.|
|Conservare il contenuto della cassetta postale per un periodo specifico dopo che un impiegato lascia l'organizzazione e quindi eliminarlo|Applicare un criterio di conservazione di Microsoft 365 alla cassetta postale. <br/> Configurare i criteri di conservazione per conservare ed eliminare gli elementi alla scadenza del periodo di conservazione. <br/> Rimuovere l'account di Microsoft 365 dell'utente.|Quando il periodo di conservazione per un elemento della cassetta postale scade, l'elemento viene spostato nella cartella Elementi ripristinabili e quindi viene eliminato definitivamente (eliminato) dalla cassetta postale inattiva alla scadenza del periodo di conservazione degli elementi eliminati (per le cassette postali di Exchange). Il periodo di conservazione dei criteri di conservazione di Microsoft 365 può essere configurato in base alla data originale di ricezione o creazione di un elemento della cassetta postale o alla data dell'ultima modifica.|
|

**NOTA:** Se un blocco per controversia legale è già applicato a una cassetta postale o se un criterio di conservazione di Microsoft 365 (configurato per conservare o conservare ed eliminare il contenuto) è già applicato alla cassetta postale, è necessario eliminare l'account utente corrispondente per creare una cassetta postale inattiva.

## <a name="managing-inactive-mailboxes"></a>Gestione di una cassetta postale inattiva

Dopo aver reso inattiva una cassetta postale, è possibile eseguire varie attività di gestione nelle cassette postali inattive.

- **Modificare la durata del blocco per una cassetta postale inattiva.** Dopo aver reso inattiva una cassetta postale, è possibile modificare la durata del blocco del blocco per controversia legale o dei criteri di conservazione di Microsoft 365 applicati alla cassetta postale inattiva. Per le procedure dettagliate, vedere Modificare la durata del blocco per una cassetta postale [inattiva.](change-the-hold-duration-for-an-inactive-mailbox.md)

  > [!NOTE]
  > Non è possibile applicare altri criteri di conservazione a una cassetta postale inattiva. È possibile modificare solo la durata di conservazione di un criterio di conservazione esistente applicato alla cassetta postale inattiva.

- **Recuperare una cassetta postale inattiva.** Se un ex dipendente (o un dipendente in congedo) torna nell'organizzazione o se un nuovo dipendente viene assunto per assumersi le responsabilità di lavoro dell'ex dipendente, è possibile recuperare il contenuto della cassetta postale inattiva. Quando si recupera una cassetta postale inattiva, la cassetta postale viene convertita in una nuova cassetta postale, il contenuto e la struttura di cartelle della cassetta postale inattiva vengono mantenuti e la cassetta postale viene collegata a un nuovo account utente. Dopo essere stata recuperata, la cassetta postale inattiva non esiste più. Per procedure dettagliate e informazioni su cosa accade quando si recupera una cassetta postale inattiva, vedere Recuperare una cassetta postale [inattiva.](recover-an-inactive-mailbox.md)

  > [!NOTE]
  > Se si recupera una cassetta postale inattiva assegnata a un criterio di conservazione con protezione dell'archiviazione (denominata criterio di conservazione *bloccato),* la cassetta postale recuperata viene assegnata allo stesso criterio di conservazione bloccato. Se si recupera una cassetta postale inattiva assegnata a un criterio di conservazione senza protezione dell'archiviazione, la cassetta postale recuperata viene rimossa dal criterio di conservazione sbloccato. Tuttavia, il blocco per controversia legale è abilitato sulla cassetta postale recuperata per impedire l'eliminazione del contenuto delle cassette postali in base a criteri di conservazione a livello di organizzazione che eliminano contenuti precedenti a una data di validità specifica.

- **Ripristinare una cassetta postale inattiva.** Se un altro dipendente assume le responsabilità di un ex dipendente o se un'altra persona deve accedere al contenuto della cassetta postale inattiva, è possibile ripristinare (o unire) il contenuto della cassetta postale inattiva in una cassetta postale esistente. Quando si ripristina una cassetta postale inattiva, il contenuto viene copiato in un'altra cassetta postale. La cassetta postale inattiva viene conservata e rimane inattiva. La cassetta postale inattiva può ancora essere cercata utilizzando gli strumenti di eDiscovery, il suo contenuto può essere ripristinato in un'altra cassetta postale e può essere recuperato o eliminato in un secondo momento. Per le procedure dettagliate, vedere [Ripristinare una cassetta postale inattiva.](restore-an-inactive-mailbox.md)

- **Eliminare una cassetta postale inattiva.** Quando non è più necessario conservare il contenuto di una cassetta postale inattiva, è possibile eliminarla definitivamente rimuovendo tutti i blocchi o i criteri di conservazione di Microsoft 365 applicati alla cassetta postale inattiva. Se una cassetta postale è stata resa inattiva da più di 30 giorni, verrà contrassegnata per l'eliminazione definitiva dopo aver rimosso il blocco. Se la cassetta postale è stata resa inattiva negli ultimi 30 giorni, è possibile attivarla di nuovo dopo aver rimosso il blocco o il criterio di conservazione. Per le procedure dettagliate, vedere [Eliminare una cassetta postale inattiva.](delete-an-inactive-mailbox.md)
