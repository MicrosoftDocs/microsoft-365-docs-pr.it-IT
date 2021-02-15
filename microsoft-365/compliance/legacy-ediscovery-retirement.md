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
description: In-Place eDiscovery e In-Place blocco sul posto (e i cmdlet di PowerShell corrispondenti) in Exchange Online verranno ritirati nella prima metà del 2020. Il cmdlet Search-Mailbox e Advanced eDiscovery v1.0 vengono ritirati nello stesso periodo di tempo.
ms.openlocfilehash: a40cc67b29e33d61d6750792f6a773622a73f678
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750879"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Ritiro degli strumenti legacy di eDiscovery

> [!IMPORTANT]
> Microsoft sta valutando la situazione di salute pubblica e comprendiamo l'impatto che questo ha sui clienti. Vogliamo essere partner forti e cittadini globali responsabili. Per semplificare uno dei molti oneri che si devono affrontare, stiamo per ritardare di tre mesi il ritiro pianificato per gli strumenti legacy di eDiscovery descritti in questo articolo. **Le date di ritiro aggiornate sono riportate di seguito.**

Nel corso degli anni, Microsoft ha fornito strumenti di eDiscovery che consentono di cercare, visualizzare in anteprima ed esportare il contenuto della posta elettronica da Exchange Online. Tuttavia, questi strumenti non offrono più un modo efficace per cercare contenuti non Di Exchange in altri servizi di Microsoft 365, ad esempio SharePoint Online e Gruppi di Microsoft 365. Per risolvere questo problema, Microsoft offre altri strumenti di eDiscovery che consentono di cercare un'ampia gamma di contenuti di Microsoft 365. E abbiamo lavorato sodo per incorporare la funzionalità eDiscovery più attuale e potente nel Centro conformità [Microsoft 365.](https://compliance.microsoft.com) Ciò consente alle organizzazioni di rispondere alle richieste legali, interne e di altri documenti per il contenuto in molti servizi di Microsoft 365, tra cui Exchange Online.

Come risultato di questa nuova e migliorata funzionalità di eDiscovery nel Centro conformità Microsoft 365, vengono ritirate le seguenti funzionalità e funzionalità correlate a eDiscovery correlate alla ricerca di contenuto di posta elettronica in Exchange Online e Microsoft 365:

- [EDiscovery sul posto e](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) [blocchi sul posto](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) nell'interfaccia di amministrazione di Exchange.

- I cmdlet di PowerShell di Exchange Online che supportano In-Place eDiscovery e In-Place blocchi (questi cmdlet sono identificati collettivamente come cmdlet **-MailboxSearch).* Sono inclusi i cmdlet seguenti:

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > I cmdlet [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) e [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) saranno disponibili dopo il ritiro degli altri cmdlet ****-MailboxSearch**_, in modo che sia possibile utilizzarli per facilitare la transizione ad altri strumenti di eDiscovery e blocco. Tuttavia, dopo una determinata data (citata di seguito) il supporto tecnico Microsoft non supporterà più questi due cmdlet.

- Il cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) in PowerShell di Exchange Online.

- Nell'API servizi Web Exchange vengono eseguite le operazioni seguenti:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0,](office-365-advanced-ediscovery.md)che è la prima versione di Advanced eDiscovery a cui si accede tramite un caso di Core eDiscovery nel Centro sicurezza & e conformità di Office 365. Il ritiro di Advanced eDiscovery v1.0 non influisce sulla possibilità di creare e gestire i casi di eDiscovery di base.

> [!NOTE]
> La funzionalità eDiscovery ritirata si applica solo alle versioni basate su cloud di Microsoft 365 e Office 365. La funzionalità eDiscovery nelle versioni locali di Exchange e SharePoint continuerà a essere supportata fino a nuovo avviso.

Le sezioni seguenti di questo articolo forniscono indicazioni su ogni funzionalità ritirata. Queste informazioni includono sequenze temporali e strumenti alternativi che puoi usare al posto dello strumento ritirato.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery e In-Place blocchi nell'interfaccia di amministrazione di Exchange 

In base all'annuncio originale del 1° luglio 2017, la funzionalità In-Place eDiscovery & Hold nell'interfaccia di amministrazione di Exchange (EAC) viene ritirata. La In-Place eDiscovery & esenzioni nell'interfaccia di amministrazione di Exchange consente di cercare, esenzioni ed esportare contenuto da Exchange Online. In-Place eDiscovery consente inoltre di copiare i risultati della ricerca in una cassetta postale di individuazione in modo che l'utente o altri responsabili di eDiscovery possa esaminare il contenuto e renderlo disponibile per richieste legali, normative e pubbliche.

Poiché tutte queste funzionalità (ad eccezione della copia dei risultati della ricerca in una cassetta postale di individuazione) sono ora disponibili nella ricerca di contenuto, negli strumenti eDiscovery e Advanced eDiscovery nel Centro conformità [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (con funzionalità migliorate, affidabilità e supporto per un'ampia gamma di servizi di Microsoft 365), è consigliabile iniziare a usare questi strumenti il prima possibile. Per facilitare la transizione a questi altri strumenti di eDiscovery, nella tabella seguente sono elencati gli strumenti che è possibile utilizzare anziché In-Place eDiscovery e In-Place blocco.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni di Office 365 e Microsoft 365 Education

- Organizzazioni di Office 365 e Microsoft 365 Government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Sequenza temporale per il ritiro

- 1 luglio 2020: non sarà possibile creare nuove ricerche e blocchi, ma sarà comunque possibile eseguire, modificare ed eliminare le ricerche esistenti a proprio rischio. Il Supporto tecnico Microsoft non In-Place eDiscovery & blocchi nell'interfaccia di amministrazione di Exchange.

- 1 ottobre 2020: la funzionalità In-Place eDiscovery & EAC verrà posizionata in modalità di sola lettura. Ciò significa che sarà possibile rimuovere solo le ricerche e le esenzioni esistenti.

### <a name="alternative-tools"></a>Strumenti alternativi

Nella tabella seguente vengono descritti altri strumenti che è possibile utilizzare per sostituire la funzionalità esistente ritirata.

<table>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>Strumento alternativo</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ricerca, esportazione e conservazione a fini giudiziari</td>
<td>Casi di Core eDiscovery nel Centro conformità Microsoft 365 </td>
<td><p>L'utilizzo delle funzionalità dei casi principali di eDiscovery offre la parità funzionale In-Place eDiscovery e In-Place blocchi. Sono incluse le attività seguenti:</p>
<ul>
<li>
<p>La ricerca si adatta a milioni di posizioni</p>
</li>
<li>
<p>Maggiore affidabilità per la ricerca, l'esportazione e l'archiviazione del contenuto</p>
</li>
<li>
<p>Ricerca di contenuto in Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Gruppi di Yammer, Gruppi di Microsoft 365 e altri contenuti archiviati nelle applicazioni di Office 365</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Conservazione a fini di conservazione</td>
<td>Criteri di conservazione nel Centro conformità Microsoft 365</td>
<td><p>È possibile utilizzare i criteri di conservazione per conservare il contenuto ed eliminarlo, se lo si desidera, dopo la scadenza del periodo di conservazione. Altre funzionalità includono:</p>
<ul>
<li>
<p>Applicazione di criteri all'intera organizzazione </p>
</li><li>
<p>Applicazione di criteri a percorsi di contenuto specifici, ad esempio Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams e gruppi di Office 365</p></li>
<li>
<p>Applicazione di criteri a utenti specifici</p></li></ul>
<p>Per ulteriori informazioni, vedere Informazioni sui <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">criteri di conservazione e sulle etichette di conservazione.</a></td>
</tr>
<tr class="odd">
<td>Copiare i risultati della ricerca di posta elettronica in una cassetta postale di individuazione per la revisione</td><td>Rivedere i set in Advanced eDiscovery v2.0</td>
<td><p>Rivedere il contenuto in Microsoft 365 non è mai stato così semplice. I set di recensioni hanno molte funzionalità avanzate che consentono di ridurre la quantità di tempo e dati necessari per la revisione, tra cui:</p>
<ul>
<li><p>Eseguire query di ricerca veloci e filtrare il contenuto in un insieme da rivedere</p></li>
<li><p>Analizzare il contenuto in un insieme da rivedere; ciò include il threading della posta elettronica, il rilevamento quasi duplicato, l'analisi dei temi e la codifica predittiva</p></li>
<li><p>Contrassegnare i documenti in un insieme da rivedere</p></li>
<li><p>Suggerimenti di tagging per identificare il contenuto dei privilegi del cliente avvocato</p></li></ul>
<p>Per altre informazioni, vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Panoramica della soluzione Advanced eDiscovery in Microsoft 365.</a></p>
<p>
<p>In alternativa, è possibile esportare i risultati della ricerca in file PST e quindi usare il servizio di importazione di Microsoft 365 per importare i file PST in una cassetta postale di individuazione. Per istruzioni dettagliate, vedere Usare il caricamento <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">di rete per importare i file PST in Office 365.</a>
</tr>
<tr class=even>
  <td>Copiare i messaggi da una cassetta postale a un'altra cassetta postale</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere a una persona l'accesso alla posta elettronica di un altro utente (ad esempio quando un dipendente lascia l'organizzazione ed è necessario concedere a un'altra persona l'accesso alla posta elettronica dell'ex dipendente), è consigliabile assegnare a tale persona le autorizzazioni per accedere alla cassetta postale dell'ex dipendente. Pertanto, anziché copiare gli elementi della cassetta postale in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare a un utente le autorizzazioni per accedere alla cassetta postale di origine.</td>
  
  </tr>
<tr class="odd">
<td>Ripristinare elementi dalla cartella Elementi ripristinabili</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>È possibile ripristinare gli elementi eliminati <i></i> definitivamente (noti anche come elementi eliminati temporaneamente) nelle cassette postali, purché il periodo di conservazione degli elementi eliminati per un elemento non sia scaduto. Per ulteriori informazioni, vedere <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Cartella Elementi ripristinabili in Exchange Online.</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Domande frequenti su In-Place eDiscovery e In-Place blocchi

_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. Quali opzioni sono disponibili ora?**

Esistono due modi per replicare questa funzionalità oggi. Il primo è utilizzare [i set di revisioni in Advanced eDiscovery v2.0.](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set) I set di revisioni hanno molte delle stesse funzionalità disponibili in uno strumento di revisione tradizionale, come la ricerca rapida di documenti, l'aggiunta di tag, il threading della posta elettronica, il raggruppamento quasi duplicato, l'analisi dei temi e la codifica predittiva. Se si desidera ancora utilizzare le cassette postali di individuazione per la revisione, la seconda opzione è esportare i risultati della ricerca in file PST e quindi importare i file PST in una cassetta postale di individuazione utilizzando la funzionalità di importazione [PST](use-network-upload-to-import-pst-files.md) nel Centro conformità Microsoft.

**Come si controllano le posizioni di contenuto (ad esempio le cassette postali o i siti) in cui un responsabile di eDiscovery può eseguire ricerche utilizzando i nuovi strumenti?**

Il Centro conformità Microsoft 365 utilizza inoltre i limiti di conformità per controllare quali posizioni di contenuto possono essere cercate da un responsabile di eDiscovery. [](set-up-compliance-boundaries.md) I limiti di conformità sono utili nelle entità governative che devono rimanere entro i limiti dell'agenzia o nelle società multinazionali necessarie per rispettare i consiglieri geografici.

**Come posso spostare le ricerche e i blocchi correnti nel Centro conformità Microsoft 365?**

È possibile eseguire la migrazione In-Place ricerche e blocchi di eDiscovery dall'interfaccia di amministrazione di Exchange utilizzando PowerShell. Per istruzioni, vedere Eseguire la migrazione di ricerche e blocchi dall'interfaccia di amministrazione di [Exchange al Centro conformità Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=2114224)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlets

In base all'avviso originale annunciato il 1° luglio 2017 nell'interfaccia di amministrazione di Exchange, la funzionalità eDiscovery & Hold di In-Place e i cmdlet **\* -MailboxSearch** corrispondenti vengono ritirati. Questi cmdlet consentono agli utenti di cercare, contenere ed esportare il contenuto delle cassette postali per richieste legali, normative e pubbliche.

Poiché queste funzionalità sono ora disponibili nel Centro conformità [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) e in PowerShell per Centro sicurezza & e conformità di Office 365 con prestazioni e scalabilità migliorate, è consigliabile utilizzare questi cmdlet migliorati. Questi cmdlet includono [<span class="underline"> \* -ComplianceCase,</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) [<span class="underline"> \* -ComplianceSearch,</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* -CaseHoldPolicy,</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* -CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)e [<span class="underline"> \* -ComplianceSearchAction.</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni di Office 365 e Microsoft 365 Education

- Organizzazioni di Office 365 e Microsoft 365 Government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

- 1 luglio 2020: Non sarà possibile utilizzare **New-MailboxSearch** per creare nuove ricerche eDiscovery di In-Place e blocchi In-Place, ma è comunque possibile utilizzare i cmdlet per eseguire, modificare ed eliminare le ricerche e i blocchi esistenti a proprio rischio. Il Supporto tecnico Microsoft non fornirà più assistenza per questi tipi di ricerche e blocchi.

- 1 ottobre 2020: come indicato in precedenza, la funzionalità di eDiscovery & blocchi di In-Place nell'interfaccia di amministrazione di Exchange verrà posizionata in modalità di sola lettura. Ciò significa anche che non sarà possibile utilizzare i cmdlet **New-MailboxSearch,** **Start-MailboxSearch** o **Set-MailboxSearch.** Potrai solo ottenere e rimuovere ricerche e blocchi esistenti.

### <a name="alternative-tools"></a>Strumenti alternativi

Nella tabella seguente vengono descritti altri strumenti che è possibile utilizzare per sostituire la funzionalità esistente ritirata.

<table>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>Strumenti alternativi</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ricerca ed esportazione</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction funzionano insieme per facilitare la ricerca e l'esportazione di contenuto. È possibile creare una nuova ricerca e visualizzare la stima della ricerca utilizzando i cmdlet <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch.</strong> È quindi possibile utilizzare il cmdlet <strong>New-ComplianceSearchAction</strong> per esportare i risultati della ricerca. Sarà comunque necessario utilizzare lo strumento eDiscovery di base nel Centro conformità Microsoft 365 per scaricare i risultati della ricerca nel computer locale.</p>
<p>
<p><strong>Nota:</strong> Se si utilizzano questi cmdlet per creare ricerche non associate a un caso di <strong></strong> eDiscovery di base, queste ricerche si trovano nella pagina Ricerca contenuto nel Centro conformità Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Archiviazione del contenuto in una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>I blocchi nel Centro conformità Microsoft 365 devono essere associati a complianceCase. Prima di tutto, creare il caso di conformità, quindi creare un CaseHoldPolicy e un CaseHoldRule.</p>
<p><strong>Nota:</strong> La creazione di un CaseHoldPolicy senza una creazione di CaseHoldRule rende inoperabile il blocco fino a quando caseHoldRule non viene creato e associato a CaseHoldPolicy. Per ulteriori informazioni, vedere la documentazione del cmdlet.</p></td>
</tr>
<tr class="odd">
<td>Copiare i risultati della ricerca in una cassetta postale di individuazione</td>
<td>Nessuno</td>
<td>Questa funzionalità non viene sostituita direttamente perché non fornisce l'accesso a tutti i servizi di Microsoft 365. Per soluzioni alternative, vedere le seguenti domande frequenti.</td>
</tr>
  <tr class=even>
  <td>Copiare i messaggi da una cassetta postale a un'altra cassetta postale</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere a una persona l'accesso alla posta elettronica di un altro utente (ad esempio quando un dipendente lascia l'organizzazione ed è necessario concedere a un'altra persona l'accesso alla posta elettronica dell'ex dipendente), è consigliabile assegnare a tale persona le autorizzazioni per accedere alla cassetta postale dell'ex dipendente. Pertanto, anziché copiare gli elementi della cassetta postale in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare a un utente le autorizzazioni per accedere alla cassetta postale di origine.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Domande frequenti sui cmdlet ***-MailboxSearch**

**La ricerca di copia viene utilizzata per esportare i messaggi di posta elettronica o i messaggi istantanei per altri scopi di eDiscovery e indagini legali. Quali altre opzioni sono disponibili dopo il ritiro di questi cmdlet?**

Le API di [<span class="underline">Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) forniscono diversi metodi per l'estrazione dei dati per l'analisi e altri scopi molto più resilienti e scalabili rispetto all'utilizzo dei cmdlet **\* -MailboxSearch.**

**Come è possibile eseguire la migrazione delle ricerche e dei blocchi nel Centro conformità Microsoft 365?**

È possibile eseguire la migrazione In-Place ricerche e blocchi di eDiscovery dall'interfaccia di amministrazione di Exchange utilizzando uno script di PowerShell. Per ulteriori informazioni, vedere Eseguire la migrazione delle ricerche e dei blocchi legacy di eDiscovery nel Centro conformità [Microsoft 365.](migrate-legacy-eDiscovery-searches-and-holds.md)

**Dopo il ritiro dei cmdlet, sarà comunque possibile rimuovere o recuperare le ricerche?**

Sì, anche se si sta rimuovendo la possibilità di creare e modificare le ricerche, sarà comunque possibile utilizzare **Get-MailboxSearch** e **Remove-MailboxSearch** fino a nuovo avviso. Tuttavia, l'uso di questi cmdlet sarà a proprio rischio dopo le date di ritiro e il supporto tecnico Microsoft non sarà più in grado di fornire assistenza.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

Il cmdlet **Search-Mailbox** in PowerShell di Exchange Online viene ritirato come annunciato originariamente in un avviso nell'output del cmdlet a partire dal 2018. Il cmdlet **Search-Mailbox** è stato originariamente utilizzato per cercare nella cassetta postale di un utente ed eliminare contenuti dannosi. È consigliabile iniziare a usare i cmdlet **New-ComplianceSearch** e **New-ComplianceSearchAction** in PowerShell per Centro sicurezza & e conformità di Office 365 per cercare ed eliminare il contenuto. Per un'esperienza di sicurezza integrata, le funzionalità di sicurezza di [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) offrono una solida protezione dalle minacce per la posta elettronica e molti altri servizi Microsoft.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni di Office 365 e Microsoft 365 Education

- Organizzazioni di Office 365 e Microsoft 365 Government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

-  1 luglio 2020: Il cmdlet **Search-Mailbox** non sarà più disponibile e il supporto tecnico Microsoft non fornirà più assistenza.

### <a name="alternative-tools"></a>Strumenti alternativi

Nella tabella seguente vengono descritti altri strumenti che è possibile utilizzare per sostituire la funzionalità esistente ritirata.

<table>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>Strumenti alternativi</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ricerca in una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction funzionano insieme per facilitare la ricerca e l'esportazione di contenuto. È possibile creare una nuova ricerca e visualizzare la stima della ricerca utilizzando i cmdlet <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch.</strong> È quindi possibile utilizzare il <strong>comando New-ComplianceSearchAction -Export</strong> per esportare i risultati della ricerca. Sarà comunque necessario utilizzare lo strumento eDiscovery di base nel Centro conformità Microsoft 365 per scaricare i risultati della ricerca nel computer locale.</p></p>
</td>
</tr>
<tr class="even">
<td>Eliminare la posta elettronica in blocco da una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Configurare i criteri di archiviazione ed eliminazione per le cassette postali</span></a></p>
<p></p></td>
<td><p>Gli amministratori possono creare criteri di archiviazione ed eliminazione che spostano automaticamente gli elementi nella cassetta postale di archiviazione di un utente ed eliminano automaticamente gli elementi dalla cassetta postale.</p>
</td>
</tr>
<tr class="even">
<td>Copiare i risultati della ricerca in una cassetta postale di individuazione</td>
<td> </td>
<td>Questa funzionalità non viene sostituita direttamente perché non fornisce l'accesso a tutti i servizi di Microsoft 365. Per soluzioni alternative, vedere le domande frequenti nella sezione <strong>*-MailboxSearch cmdlets.</strong> </td>
</tr>
<tr class=odd>
  <td>Copiare i messaggi da una cassetta postale a un'altra cassetta postale</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere a una persona l'accesso alla posta elettronica di un altro utente (ad esempio quando un dipendente lascia l'organizzazione ed è necessario concedere a un'altra persona l'accesso alla posta elettronica dell'ex dipendente), è consigliabile assegnare a tale persona le autorizzazioni per accedere alla cassetta postale dell'ex dipendente. Pertanto, anziché copiare gli elementi della cassetta postale in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare a un utente le autorizzazioni per accedere alla cassetta postale di origine.</td>
</tr>
<tr class=even>
  <td>Eliminare i messaggi da una cassetta postale</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction funzionano insieme per facilitare la ricerca e l'eliminazione del contenuto. È possibile creare ed eseguire una ricerca con i cmdlet <strong>New-ComplianceSearch</strong> e <strong>New-ComplianceSearch</strong> e quindi eliminare il contenuto utilizzando il comando <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Per ulteriori informazioni, vedere <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Cercare ed eliminare i messaggi.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Eliminare i messaggi da una cassetta postale</td>
<td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
<td>Per eliminare i messaggi da una cassetta postale, assegnare a un amministratore le autorizzazioni per accedere alla cassetta postale del dipendente. I messaggi possono essere eliminati e riciclati in base alle esigenze sfruttando le funzionalità di ricerca e visualizzazione incorporate in Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Operazioni API dei servizi Web Exchange

Queste operazioni nell'API dei servizi Web Exchange vengono utilizzate dalla funzionalità eDiscovery & Holds di In-Place nell'interfaccia di amministrazione di Exchange e dai cmdlet **\* -MailboxSearch** corrispondenti in PowerShell di Exchange Online. Verranno ritirati anche come parte del ritiro degli altri strumenti legacy di eDiscovery.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni di Office 365 e Microsoft 365 Education

- Organizzazioni di Office 365 e Microsoft 365 Government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

- 1 luglio 2020: Le operazioni GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes e GetHoldOnMailboxes non saranno più disponibili e il supporto tecnico Microsoft non fornirà più assistenza.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, ovvero la versione di Advanced eDiscovery disponibile in un caso di eDiscovery di base facendo clic su Passa ad **Advanced eDiscovery,** viene ritirato. La funzionalità è stata sostituita dalla nuova [soluzione Advanced eDiscovery](https://aka.ms/edisco) nel Centro conformità Microsoft 365.

Per determinare se l'organizzazione utilizza Advanced eDiscovery v1.0:

1. Passare al Centro sicurezza e conformità di [Office 365 &.](https://protection.office.com)

2. Nel riquadro di spostamento sinistro del Centro sicurezza & conformità, fare clic su **eDiscovery > eDiscovery** e aprire un caso di Core eDiscovery.

3. Se viene visualizzato il pulsante Passa ad **Advanced eDiscovery,** facendo clic su di esso verrà visualizzata la versione 1.0 di Advanced eDiscovery, che verrà ritirata. La possibilità di creare e gestire i casi in Core eDiscovery non ne sarà influenzata. Viene ritirata solo la possibilità di aggiungere e analizzare i dati dei casi in Advanced eDiscovery v1.0 (facendo clic su Passa ad **Advanced eDiscovery).**

La nuova soluzione Advanced eDiscovery in Microsoft 365 (nota anche come *Advanced eDiscovery v2.0)* offre tutte le funzionalità della soluzione originale, ma ora include un approccio basato sui revisori per identificare il contenuto in altri servizi di Microsoft 365, raccoglierlo e quindi aggiungerlo a un insieme da rivedere in cui i revisori possono sfruttare le query di ricerca veloci, il tagging e le funzionalità di analisi per facilitare la rimozione di documenti pertinenti. Advanced eDiscovery ora include l'elaborazione migliorata e i visualizzatori nativi sia per [](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) i tipi di file Microsoft che per i tipi di file non Microsoft, è disponibile un elenco completo dei tipi di file e i campi dei metadati supportati sono [disponibili qui.](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery) Inoltre, la nuova soluzione Advanced eDiscovery offre una potente funzionalità di gestione dei blocchi dei depositario che consente di applicare blocchi al contenuto in servizi diversi, notificare agli utenti le esenzioni e tenere traccia delle risposte del responsabile, tutto all'interno di un caso di Advanced eDiscovery.

Per accedere ad Advanced eDiscovery v2.0:

1. Passare al [Centro conformità Microsoft 365.](https://compliance.microsoft.com)

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365 fare clic su Mostra tutto e quindi su **eDiscovery > Avanzate.**

Al momento, si consiglia di iniziare la transizione del flusso di lavoro di eDiscovery alla nuova funzionalità Advanced eDiscovery. Se necessario, è possibile archiviare i casi di Advanced eDiscovery 1.0 esportando il contenuto e archiviandoli offline. Anche se sarà comunque possibile accedere ad Advanced eDiscovery v1.0 nei casi esistenti fino al 31 dicembre 2020, il Supporto tecnico Microsoft non fornirà supporto dopo il 1° ottobre 2020. Per altri dettagli, vedi la sequenza temporale seguente.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Organizzazioni di Office 365 e Microsoft 365 Enterprise

- Organizzazioni di Office 365 e Microsoft 365 Education

- Organizzazioni di Office 365 e Microsoft 365 Government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

- 1 luglio 2020: Non sarà possibile creare nuovi casi di Advanced eDiscovery v1.0.

- 1 ottobre 2020: Non sarà possibile aggiungere nuovi dati (preparare i risultati della ricerca per Advanced eDiscovery) a tutti i casi. Sarà possibile continuare a lavorare con i dati nei casi esistenti a proprio rischio. Il Supporto tecnico Microsoft non fornirà più assistenza. 

- 31 dicembre 2020: Non sarà possibile accedere ai casi di Advanced eDiscovery v1.0.

### <a name="alternative-tools"></a>Strumenti alternativi

La [soluzione Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) nel Centro conformità Microsoft 365.
