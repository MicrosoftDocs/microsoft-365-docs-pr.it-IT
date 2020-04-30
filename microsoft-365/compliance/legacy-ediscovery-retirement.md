---
title: Ritiro degli strumenti legacy di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: I eDiscovery sul posto e il blocco sul posto (e i cmdlet di PowerShell corrispondenti) in Exchange Online verranno ritirati nella prima metà del 2020. Il cmdlet Search-Mailbox e Advanced eDiscovery v 1.0 vengono anche ritirati nello stesso periodo di tempo.
ms.openlocfilehash: 48dbbd86071f8b07fa3dbf3a699f0d7e085fd50b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943345"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Ritiro degli strumenti legacy di eDiscovery

> [!IMPORTANT]
> Microsoft ha valutato la situazione dell'integrità pubblica e comprende l'impatto che questo comporta sui clienti. Vogliamo essere partner forti e responsabili dei cittadini globali. Per semplificare uno dei numerosi oneri di cui si ha a che fare, si intende posticipare il pensionamento programmato per gli strumenti di eDiscovery legacy descritti in questo articolo per tre mesi. **Le date di pensionamento aggiornate sono riportate di seguito.**

Nel corso degli anni, Microsoft ha fornito gli strumenti di eDiscovery che consentono di cercare, visualizzare in anteprima ed esportare il contenuto della posta elettronica da Exchange Online. Tuttavia, questi strumenti non offrono più una soluzione efficace per la ricerca di contenuto non Exchange in altri servizi Microsoft 365, ad esempio i gruppi di SharePoint Online e Microsoft 365. Per risolvere questo, Microsoft offre altri strumenti di eDiscovery che consentono di cercare una vasta gamma di contenuto Microsoft 365. E abbiamo lavorato duramente per incorporare la più recente e potente funzionalità di eDiscovery nel [centro conformità di Microsoft 365](https://compliance.microsoft.com). In questo modo le organizzazioni devono rispondere a richieste di documenti legali, interne e di altro tipo per i contenuti di numerosi servizi Microsoft 365, tra cui Exchange Online.

Come risultato di questa nuova e migliorata funzionalità di eDiscovery nel centro conformità di Microsoft 365, vengono ritirate le seguenti funzionalità e caratteristiche correlate a eDiscovery correlate alla ricerca di contenuto di posta elettronica in Exchange Online e Microsoft 365:

- [EDiscovery sul posto](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) e [archiviazioni sul posto](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) nell'interfaccia di amministrazione di Exchange.

- I cmdlet di PowerShell di Exchange Online che supportano le archiviazioni sul posto di eDiscovery e sul posto (questi cmdlet sono identificati collettivamente come cmdlet **-MailboxSearch* ). Sono inclusi i cmdlet seguenti:

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > I cmdlet [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch) e [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) saranno disponibili dopo che gli altri cmdlet * * * *-MailboxSearch * * * vengono ritirati in modo da poterli utilizzare per facilitare la transizione ad altri strumenti di eDiscovery e conservazione. Tuttavia, dopo una determinata data (citata in basso) il supporto tecnico Microsoft non supporterà più questi due cmdlet.

- Il cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) in Exchange Online PowerShell.

- Le operazioni seguenti nell'API dei servizi Web di Exchange:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v 1.0](office-365-advanced-ediscovery.md), che è la prima versione di Advanced eDiscovery a cui si accede tramite un case di eDiscovery core nel centro sicurezza & conformità di Office 365. La Pensione avanzata di eDiscovery v 1.0 non influisce sulla capacità di creare e gestire i casi di eDiscovery di base.

> [!NOTE]
> Le funzionalità di eDiscovery che vengono ritirate si applicano solo alle versioni basate su cloud di Microsoft 365 e Office 365. la funzionalità eDiscovery nelle versioni locali di Exchange e SharePoint continuerà a essere supportata fino a nuovo avviso.

Nelle sezioni seguenti di questo articolo vengono fornite indicazioni su ogni caratteristica che si sta ritirando. Queste informazioni, incluse le sequenze temporali e gli strumenti alternativi che è possibile utilizzare al posto dello strumento in pensione.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>EDiscovery sul posto e archiviazioni sul posto nell'interfaccia di amministrazione di Exchange 

Secondo l'annuncio originale del 1 ° luglio 2017, il eDiscovery sul posto & la funzionalità di blocco nell'interfaccia di amministrazione di Exchange (EAC) è in fase di ritirata. La pagina dei & di eDiscovery sul posto nell'interfaccia di amministrazione di Exchange consentiva di cercare, conservare ed esportare il contenuto proveniente dalla rete. EDiscovery sul posto consente inoltre di copiare i risultati della ricerca in una cassetta postale di individuazione in modo che sia possibile esaminare il contenuto e renderlo disponibile per le richieste legali, normative e pubbliche da parte di altri responsabili di eDiscovery.

Poiché tutte queste funzionalità (ad eccezione della copia dei risultati di ricerca in una cassetta postale di individuazione) sono ora disponibili negli strumenti ricerca contenuto, eDiscovery e Advanced eDiscovery nel [centro conformità di microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (con funzionalità, affidabilità e supporto migliorati per una vasta gamma di servizi Microsoft 365), è consigliabile iniziare a usare questi strumenti appena possibile. Per facilitare la transizione a questi altri strumenti di eDiscovery, nella tabella seguente sono elencati gli strumenti che è possibile utilizzare invece di eDiscovery sul posto e blocco sul posto.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni coinvolte

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni per l'istruzione di Office 365 e Microsoft 365

- Organizzazioni governative di Office 365 e Microsoft 365; Questo include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Sequenza temporale per la pensione

- 1 ° luglio 2020: non è possibile creare nuove ricerche e conservazioni, ma è comunque in grado di eseguire, modificare ed eliminare le ricerche esistenti a proprio rischio. Il supporto tecnico Microsoft non eDiscovery più sul posto & conserva nell'interfaccia di amministrazione di Exchange.

- 2020 ottobre 1: la eDiscovery sul posto & mantiene la funzionalità nell'interfaccia di amministrazione di Exchange verrà messa in modalità di sola lettura. Questo significa che sarà possibile rimuovere solo le ricerche e le esenzioni esistenti.

### <a name="alternative-tools"></a>Strumenti alternativi

Nella tabella seguente vengono descritti gli altri strumenti che è possibile utilizzare per sostituire le funzionalità esistenti che vengono ritirate.

<table>
<thead>
<tr class="header">
<th><strong>Funzionalità</strong></th>
<th><strong>Strumento alternativo</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ricerca, esportazione e conservazione per scopi legali</td>
<td>Casi di eDiscovery di base nel centro conformità di Microsoft 365 </td>
<td><p>L'utilizzo delle funzionalità dei casi di eDiscovery di base garantisce la parità funzionale ai eDiscovery sul posto e alle archiviazioni sul posto. Sono incluse le attività seguenti:</p>
<ul>
<li>
<p>Scala di ricerca a milioni di posizioni</p>
</li>
<li>
<p>Maggiore affidabilità per la ricerca, l'esportazione e l'inserimento di contenuto in attesa</p>
</li>
<li>
<p>Ricerca di contenuto per Exchange Online, SharePoint Online, OneDrive for business, Skype for business, Microsoft teams, Yammer groups, Microsoft 365 Groups e altri contenuti archiviati nelle applicazioni di Office 365</p></li></ul>
<p>Per ulteriori informazioni, vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">Manage Legal Investigations in Office 365</a>.</td>
</tr>
<tr class="even">
<td>Blocco per la conservazione</td>
<td>Criteri di conservazione nel centro conformità di Microsoft 365</td>
<td><p>È possibile utilizzare i criteri di conservazione per mantenere il contenuto e, se lo si desidera, eliminarlo dopo la scadenza del periodo di conservazione. Altre funzionalità includono:</p>
<ul>
<li>
<p>Applicazione di criteri all'intera organizzazione </p>
</li><li>
<p>Applicazione dei criteri a posizioni di contenuto specifiche quali Exchange Online, SharePoint Online, OneDrive for business, Skype for business, Microsoft teams e Office 365 groups</p></li>
<li>
<p>Applicazione di criteri a utenti specifici</p></li></ul>
<p>Per ulteriori informazioni, vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">Overview of Retention Policies</a>.</td>
</tr>
<tr class="odd">
<td>Copiare i risultati della ricerca tramite posta elettronica in una cassetta postale di individuazione per la revisione</td><td>Esaminare i set in Advanced eDiscovery v 2.0</td>
<td><p>La revisione del contenuto in Microsoft 365 non è mai stata più facile. I set di revisione dispongono di numerose funzionalità che consentono di ridurre la quantità di tempo e i dati necessari per la revisione, tra cui:</p>
<ul>
<li><p>Eseguire query di ricerca veloce e filtrare i contenuti in un set di Revisione</p></li>
<li><p>Analizzare il contenuto in un set di Revisione; Questo include il threading della posta elettronica, il rilevamento quasi duplicato, l'analisi dei temi e la codifica predittiva</p></li>
<li><p>Contrassegnare i documenti in un insieme da rivedere</p></li>
<li><p>Suggerimenti per la tagging per identificare il contenuto dei privilegi dei clienti legali</p></li></ul>
<p>Per altre informazioni, vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Panoramica della soluzione Advanced eDiscovery in Microsoft 365.</a></p>
<p>
<p>In alternativa, è possibile esportare i risultati della ricerca in file PST e quindi utilizzare il servizio Microsoft 365 Import per importare il PST in una cassetta postale di individuazione. Per istruzioni dettagliate, vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">usare il caricamento di rete per importare i file PST in Office 365</a>.
</tr>
<tr class=even>
  <td>Copiare i messaggi da una cassetta postale a una cassetta postale diversa</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare le autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere l'accesso alla posta elettronica di un altro utente (ad esempio, quando un dipendente lascia l'organizzazione ed è necessario consentire a un'altra persona di accedere alla posta elettronica dell'ex dipendente), si consiglia di assegnare le autorizzazioni per l'accesso alla cassetta postale dell'ex dipendente. Pertanto, invece di copiare gli elementi delle cassette postali in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare un utente per accedere alla cassetta postale di origine.</td>
  
  </tr>
<tr class="odd">
<td>Ripristinare gli elementi dalla cartella elementi ripristinabili</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>È possibile ripristinare gli elementi eliminati in modo definitivo (noti anche come elementi <i>eliminati temporaneamente</i> ) nelle cassette postali, purché il periodo di conservazione degli elementi eliminati per un elemento non sia scaduto. Per ulteriori informazioni, vedere <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">cartella elementi ripristinabili in Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Domande frequenti su eDiscovery sul posto e sulle archiviazioni sul posto

**Utilizzo la funzionalità di copia dei risultati di ricerca di eDiscovery sul posto & conserva nell'interfaccia di amministrazione di Exchange per copiare i risultati della ricerca in una cassetta postale di individuazione per la revisione da parte di avvocati. Quali opzioni sono disponibili adesso?**

Esistono due modi per replicare questa funzionalità oggi. Il primo consiste nell'utilizzare i [set di revisione in Advanced eDiscovery v 2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set). I set di revisione dispongono di molte delle stesse funzionalità visualizzate in uno strumento di analisi tradizionale come la ricerca rapida di documenti, tagging, threading della posta elettronica, il raggruppamento in prossimità di duplicati, l'analisi dei temi e la codifica predittiva. Se si desidera continuare a utilizzare le cassette postali di individuazione per la revisione, la seconda opzione consiste nell'esportare i risultati della ricerca in file PST e quindi importare i file PST in una cassetta postale di individuazione utilizzando la [caratteristica di importazione PST](use-network-upload-to-import-pst-files.md) nel centro conformità Microsoft.

**In che modo è possibile controllare quali posizioni di contenuto (ad esempio, cassette postali o siti) in grado di eseguire la ricerca di un Manager di eDiscovery utilizzando i nuovi strumenti?**

Microsoft 365 Compliance Center utilizza inoltre i [limiti di conformità](set-up-compliance-boundaries.md) per controllare quali posizioni di contenuto possono essere cercate da un responsabile di eDiscovery. I limiti di conformità sono utili nelle entità governative che devono rimanere all'interno dei confini delle agenzie o di società multi-nazionali necessarie per rispettare i confini geografici.

**Come è possibile spostare le ricerche correnti e le esenzioni nel centro conformità di Microsoft 365?**

È possibile eseguire la migrazione delle ricerche eDiscovery sul posto e delle esenzioni dall'interfaccia di amministrazione di Exchange tramite PowerShell. Per istruzioni, vedere [eseguire la migrazione di ricerche e esenzioni dall'interfaccia di amministrazione di Exchange al centro conformità di Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2114224).

## <a name="-mailboxsearch-cmdlets"></a>\*-Cmdlet di MailboxSearch

In base all'avviso originale annunciato il 1 ° luglio 2017 nell'interfaccia di amministrazione di Exchange, le funzionalità di eDiscovery sul posto & di archiviazione e i cmdlet di ** \*MailboxSearch** corrispondenti vengono ritirati. Questi cmdlet offrono agli utenti la possibilità di cercare, conservare ed esportare il contenuto delle cassette postali per le richieste legali, normative e pubbliche.

Poiché queste funzionalità sono ora disponibili nel [<span class="underline">centro conformità Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) e in Office 365 Security & Compliance Center PowerShell con prestazioni e scalabilità migliorate, è consigliabile utilizzare questi cmdlet migliorati. Tra questi cmdlet sono inclusi [<span class="underline"> \*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase), [<span class="underline"> \*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch), [<span class="underline"> \*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy), [<span class="underline"> \*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)e [<span class="underline"> \*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni coinvolte

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni per l'istruzione di Office 365 e Microsoft 365

- Organizzazioni governative di Office 365 e Microsoft 365; Questo include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Tempistica

- 1 luglio 2020: non è possibile utilizzare **New-MailboxSearch** per creare nuove ricerche eDiscovery sul posto e archiviazioni sul posto, ma è comunque possibile utilizzare i cmdlet per l'esecuzione, la modifica e l'eliminazione di ricerche esistenti e conserva a proprio rischio. Il supporto tecnico Microsoft non fornirà più assistenza per questi tipi di ricerche e esenzioni.

- 2020 ottobre 1: come indicato in precedenza, il eDiscovery sul posto & conserva la funzionalità nell'interfaccia di amministrazione di Exchange verrà messa in modalità di sola lettura. Questo significa anche che non è possibile utilizzare i cmdlet **New-MailboxSearch**, **Start-MailboxSearch**o **Set-MailboxSearch** . È possibile ottenere e rimuovere solo le ricerche e le esenzioni esistenti.

### <a name="alternative-tools"></a>Strumenti alternativi

Nella tabella seguente vengono descritti gli altri strumenti che è possibile utilizzare per sostituire le funzionalità esistenti che vengono ritirate.

<table>
<thead>
<tr class="header">
<th><strong>Funzionalità</strong></th>
<th><strong>Strumenti alternativi</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ricerca ed esportazione</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction interagiscono per facilitare la ricerca e l'esportazione di contenuto. È possibile creare una nuova ricerca e visualizzare la stima della ricerca utilizzando i cmdlet <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch</strong> . Successivamente, è possibile utilizzare il cmdlet <strong>New-ComplianceSearchAction</strong> per esportare i risultati della ricerca. È comunque necessario utilizzare lo strumento eDiscovery di base nel centro conformità di Microsoft 365 per scaricare i risultati della ricerca nel computer locale.</p>
<p>
<p><strong>Nota:</strong> Se si utilizzano questi cmdlet per creare ricerche che non sono associate a un caso di eDiscovery di base, tali ricerche saranno disponibili nella pagina <strong>Ricerca contenuto</strong> del centro conformità di Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Conservare il contenuto in una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Le conservazioni nel centro conformità di Microsoft 365 devono essere associate a un ComplianceCase. In primo luogo, creare il caso di conformità e quindi creare un CaseHoldPolicy e un CaseHoldRule.</p>
<p><strong>Nota:</strong> La creazione di un CaseHoldPolicy senza creare CaseHoldRule renderà l'archiviazione inutilizzabile fino a quando non viene creata la CaseHoldRule e associata a CaseHoldPolicy. Per ulteriori informazioni, vedere la documentazione relativa al cmdlet.</p></td>
</tr>
<tr class="odd">
<td>Copiare i risultati della ricerca in una cassetta postale di individuazione</td>
<td>Nessuno</td>
<td>Non è disponibile una sostituzione diretta per questa funzionalità poiché non fornisce l'accesso a tutti i servizi di Microsoft 365. Vedere le domande frequenti seguenti per soluzioni alternative.</td>
</tr>
  <tr class=even>
  <td>Copiare i messaggi da una cassetta postale a una cassetta postale diversa</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare le autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere l'accesso alla posta elettronica di un altro utente (ad esempio, quando un dipendente lascia l'organizzazione ed è necessario consentire a un'altra persona di accedere alla posta elettronica dell'ex dipendente), si consiglia di assegnare le autorizzazioni per l'accesso alla cassetta postale dell'ex dipendente. Pertanto, invece di copiare gli elementi delle cassette postali in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare un utente per accedere alla cassetta postale di origine.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Domande frequenti sui cmdlet ***-MailboxSearch**

**Per esportare i messaggi di posta elettronica o i messaggi istantanei, è possibile utilizzare la ricerca di copia per scopi di altre eDiscovery e indagini legali. Quali altre opzioni sono disponibili dopo che questi cmdlet sono stati ritirati?**

Le [<span class="underline">API di Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) forniscono numerosi metodi per l'estrazione dei dati per l'analisi e per altri scopi molto più resistenti e scalabili rispetto all'utilizzo dei ** \*cmdlet-MailboxSearch** .

**Come è possibile eseguire la migrazione delle ricerche e delle conservazioni al centro conformità di Microsoft 365?**

È possibile eseguire la migrazione di ricerche eDiscovery sul posto e conserva dall'interfaccia di amministrazione di Exchange utilizzando uno script di PowerShell. Per ulteriori informazioni, vedere [migrate legacy eDiscovery searchs and holds to the Microsoft 365 Compliance Center](migrate-legacy-eDiscovery-searches-and-holds.md).

**Dopo che i cmdlet sono stati ritirati, sarà comunque possibile rimuovere o recuperare le ricerche?**

Sì, anche se si sta rimuovendo la possibilità di creare e modificare le ricerche, sarà comunque possibile utilizzare **Get-MailboxSearch** e **Remove-MailboxSearch** fino a un ulteriore avviso. Tuttavia, l'uso di questi cmdlet sarà a proprio rischio dopo le date di pensionamento e il supporto tecnico Microsoft non sarà più in grado di fornire assistenza.

## <a name="search-mailbox-cmdlet"></a>Cmdlet Search-Mailbox

Il cmdlet **Search-Mailbox** in Exchange Online PowerShell viene ritirato come annunciato in un messaggio di avviso nell'output del cmdlet a partire da 2018. Il cmdlet **Search-Mailbox** è stato originariamente utilizzato per eseguire la ricerca nella cassetta postale di un utente ed eliminare i contenuti dannosi. Si consiglia di iniziare a utilizzare i cmdlet **New-ComplianceSearch** e **New-ComplianceSearchAction** in Office 365 Security & Compliance Center PowerShell per cercare ed eliminare il contenuto. Per un'esperienza di sicurezza integrata, le [<span class="underline">funzionalità di sicurezza di microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) offrono una robusta protezione dalle minacce per la posta elettronica e molti altri servizi Microsoft.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni coinvolte

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni per l'istruzione di Office 365 e Microsoft 365

- Organizzazioni governative di Office 365 e Microsoft 365; Questo include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Tempistica

-  1 luglio 2020: il cmdlet **Search-Mailbox** non sarà più disponibile e il supporto tecnico Microsoft non fornirà più assistenza.

### <a name="alternative-tools"></a>Strumenti alternativi

Nella tabella seguente vengono descritti gli altri strumenti che è possibile utilizzare per sostituire le funzionalità esistenti che vengono ritirate.

<table>
<thead>
<tr class="header">
<th><strong>Funzionalità</strong></th>
<th><strong>Strumenti alternativi</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ricerca di una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction interagiscono per facilitare la ricerca e l'esportazione di contenuto. È possibile creare una nuova ricerca e visualizzare la stima della ricerca utilizzando i cmdlet <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch</strong> . Successivamente, è possibile utilizzare il comando <strong>New-ComplianceSearchAction-Export</strong> per esportare i risultati della ricerca. È comunque necessario utilizzare lo strumento eDiscovery di base nel centro conformità di Microsoft 365 per scaricare i risultati della ricerca nel computer locale.</p></p>
</td>
</tr>
<tr class="even">
<td>Eliminare i messaggi da una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction interagiscono per facilitare la ricerca e l'eliminazione del contenuto. È possibile creare ed eseguire una ricerca con cmdlet <strong>New-ComplianceSearch</strong> e <strong>New-ComplianceSearch</strong> , quindi è possibile eliminare il contenuto utilizzando il comando <strong>New-ComplianceSearchAction-Purge-PurgeType</strong> . Per ulteriori informazioni, vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">cercare ed eliminare i messaggi</span></a>.</p>
</td>
</tr>
<tr class="odd">
<td>Eliminare messaggi di posta elettronica in blocco da una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Configurare i criteri di archiviazione ed eliminazione per le cassette postali</span></a></p>
<p></p></td>
<td><p>Gli amministratori possono creare un criterio di eliminazione e archiviazione che sposta automaticamente gli elementi nella cassetta postale di archiviazione di un utente ed Elimina automaticamente gli elementi dalla cassetta postale.</p>
</td>
</tr>
<tr class="even">
<td>Copiare i risultati della ricerca in una cassetta postale di individuazione</td>
<td> </td>
<td>Non è disponibile una sostituzione diretta per questa funzionalità poiché non fornisce l'accesso a tutti i servizi di Microsoft 365. Vedere le domande frequenti nella sezione <strong>cmdlet *-MailboxSearch</strong> per soluzioni alternative. </td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Operazioni API di servizi Web Exchange

Queste operazioni nell'API dei servizi Web di Exchange vengono utilizzate dalla funzionalità eDiscovery sul posto & contiene l'interfaccia di amministrazione di Exchange e i cmdlet di ** \*MailboxSearch** corrispondenti in Exchange Online PowerShell. Essi saranno anche ritirati nell'ambito del ritiro degli altri strumenti legacy di eDiscovery.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni coinvolte

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni per l'istruzione di Office 365 e Microsoft 365

- Organizzazioni governative di Office 365 e Microsoft 365; Questo include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Tempistica

- 1 luglio 2020: le operazioni GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes e GetHoldOnMailboxes non saranno più disponibili e il supporto tecnico Microsoft non fornirà più assistenza.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v 1.0

Advanced eDiscovery v 1.0, che è la versione avanzata di eDiscovery disponibile in un caso di eDiscovery Core facendo clic **su passa a eDiscovery avanzato**, è in fase di ritirata. La sua funzionalità è stata sostituita dalla nuova [soluzione avanzata di eDiscovery](https://aka.ms/edisco) nel centro conformità di Microsoft 365.

Per determinare se l'organizzazione utilizza Advanced eDiscovery v 1.0:

1. Accedere al [Centro sicurezza & conformità di Office 365](https://protection.office.com).

2. Nel riquadro di spostamento a sinistra del Centro sicurezza & conformità fare clic su **eDiscovery > eDiscovery**e quindi aprire un caso di eDiscovery di base.

3. Se viene visualizzato il pulsante **passa a Advanced eDiscovery** , fare clic su di esso per passare alla versione 1,0 di Advanced eDiscovery, che verrà ritirata. La possibilità di creare e gestire i casi in eDiscovery di base non sarà intaccata. Solo la possibilità di aggiungere e analizzare i dati del caso in Advanced eDiscovery v 1.0 (facendo clic **su passa a Advanced eDiscovery**) è in fase di ritirata.

La nuova soluzione avanzata di eDiscovery in Microsoft 365 (nota anche come *Advanced eDiscovery v 2.0*) fornisce tutte le funzionalità della soluzione originale. ma ora include un approccio basato su un custode per identificare il contenuto di altri servizi Microsoft 365, raccogliere tale contenuto e quindi aggiungerlo a un set di revisione in cui i revisori possono trarre vantaggio dalle funzionalità di query di ricerca, tagging e analisi veloce per facilitare l'eliminazione dei documenti rilevanti. Advanced eDiscovery ora include un miglioramento dell'elaborazione e dei visualizzatori nativi per i tipi di file Microsoft e non Microsoft, un elenco completo di tipi di file è [qui](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) e i campi dei metadati supportati sono [qui](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery). Inoltre, la nuova soluzione avanzata di eDiscovery offre una potente funzionalità di gestione delle esenzioni dei depositari che consente di applicare le esenzioni ai contenuti in diversi servizi, informare gli utenti delle stive e tenere conto delle risposte dei depositari, tutto all'interno di un caso di eDiscovery avanzato.

Per accedere a Advanced eDiscovery v 2.0:

1. Accedere al [centro conformità Microsoft 365](https://compliance.microsoft.com).

2. Nel riquadro di spostamento a sinistra del centro conformità di Microsoft 365 fare clic su **Mostra tutto**, quindi fare clic su **eDiscovery > avanzate**.

A questo punto, si consiglia di iniziare a eseguire la transizione del flusso di lavoro di eDiscovery alla nuova funzionalità Advanced eDiscovery. Anche se si è ancora in grado di accedere a Advanced eDiscovery v 1.0 nei casi esistenti, il supporto tecnico Microsoft non fornirà supporto dopo il 1 ° ottobre 2020. Per ulteriori informazioni, vedere la sequenza temporale seguente.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni coinvolte

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni per l'istruzione di Office 365 e Microsoft 365

- Office 365 Germany

### <a name="timeline"></a>Tempistica

- 1 ° luglio 2020: non è possibile creare nuovi casi avanzati di eDiscovery v 1.0.

- 2020 ottobre 1: non è possibile aggiungere nuovi dati (preparare i risultati della ricerca per Advanced eDiscovery) a tutti i casi. È possibile continuare a utilizzare i dati nei casi esistenti a proprio rischio e pericolo. Il supporto tecnico Microsoft non offrirà più assistenza. 

### <a name="alternative-tools"></a>Strumenti alternativi

La [soluzione avanzata di eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) nel centro conformità di Microsoft 365.