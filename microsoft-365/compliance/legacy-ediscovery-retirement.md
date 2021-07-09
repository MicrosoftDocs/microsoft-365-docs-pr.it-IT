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
description: In-Place eDiscovery and In-Place Hold (and the corresponding PowerShell cmdlets) in Exchange Online will be retired in the first half of 2020. Il cmdlet Search-Mailbox e Advanced eDiscovery v1.0 vengono ritirati nello stesso periodo di tempo.
ms.openlocfilehash: 77a7daf36c86cd302f774e5a4b934148d3dfd5a7
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340997"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Ritiro degli strumenti legacy di eDiscovery

> [!IMPORTANT]
> La funzionalità degli strumenti legacy di eDiscovery descritti in questo articolo è stata rimossa dal servizio Microsoft 365 o è ancora disponibile, ma non è più supportata. Qualsiasi funzionalità ancora disponibile può essere rimossa senza preavviso. Se si utilizza ancora uno di questi strumenti legacy, è consigliabile eseguire la migrazione agli strumenti di eDiscovery nel Centro conformità Microsoft 365 o in una delle alternative descritte in questo articolo.

Nel corso degli anni, Microsoft ha fornito strumenti di eDiscovery che consentono di cercare, visualizzare in anteprima ed esportare contenuto di posta elettronica da Exchange Online. Tuttavia, questi strumenti non offrono più un modo efficace per cercare contenuto non Exchange in altri servizi Microsoft 365, ad esempio SharePoint Online e gruppi Microsoft 365. Per risolvere questo problema, Microsoft offre altri strumenti di eDiscovery che consentono di cercare un'ampia gamma di Microsoft 365 contenuti. Inoltre, abbiamo lavorato sodo per incorporare la funzionalità eDiscovery più potente e attuale [nell'Centro conformità Microsoft 365](https://compliance.microsoft.com). Ciò consente alle organizzazioni di rispondere alle richieste legali, interne e di altri documenti per il contenuto in molti servizi Microsoft 365, tra cui Exchange Online.

Come risultato di questa nuova e migliorata funzionalità di eDiscovery nel Centro conformità Microsoft 365, vengono ritirate le funzionalità e le funzionalità correlate a eDiscovery seguenti correlate alla ricerca di contenuto di posta elettronica in Exchange Online e Microsoft 365:

- [EDiscovery sul posto](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) e [blocchi sul](/exchange/security-and-compliance/create-or-remove-in-place-holds) posto nell'Exchange di amministrazione.

- I cmdlet Exchange Online PowerShell che supportano In-Place eDiscovery e In-Place Holds (questi cmdlet sono identificati collettivamente come cmdlet **-MailboxSearch).* Sono inclusi i cmdlet seguenti:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > I cmdlet [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) e [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) saranno disponibili dopo che gli altri cmdlet ****-MailboxSearch*** verranno ritirati in modo da poterli utilizzare per facilitare la transizione ad altri strumenti di eDiscovery e conservazione. Tuttavia, dopo una determinata data (citata di seguito) il supporto Tecnico Microsoft non supporterà più questi due cmdlet.

- Il cmdlet [Search-Mailbox](/powershell/module/exchange/search-mailbox) in Exchange Online PowerShell.

- Le operazioni seguenti nell'API Exchange Web Services:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), che è la prima versione di Advanced eDiscovery a cui si accede tramite un caso di eDiscovery di base nel Centro sicurezza Office 365 & conformità. Il ritiro Advanced eDiscovery v1.0 non influisce sulla possibilità di creare e gestire i casi di eDiscovery di base.

> [!NOTE]
> La funzionalità eDiscovery ritirata si applica solo alle versioni basate su cloud di Microsoft 365 e Office 365. La funzionalità eDiscovery nelle versioni locali di Exchange e SharePoint sarà comunque supportata fino a nuovo avviso.

Nelle sezioni seguenti di questo articolo vengono fornite indicazioni su ogni funzionalità ritirata. Queste informazioni includono sequenze temporali e strumenti alternativi che puoi usare al posto dello strumento ritirato.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery e In-Place esenzioni nell'interfaccia Exchange di amministrazione 

In base all'annuncio originale del 1° luglio 2017, la funzionalità di blocco In-Place eDiscovery & nell'interfaccia di amministrazione di Exchange (EAC) viene ritirata. La In-Place eDiscovery & blocchi nell'interfaccia di amministrazione di Exchange consente di cercare, esenzioni ed esportare contenuto da Exchange Online. In-Place eDiscovery consente inoltre di copiare i risultati della ricerca in una cassetta postale di individuazione in modo che l'utente o altri responsabili di eDiscovery possa esaminare il contenuto e renderlo disponibile per richieste legali, normative e pubbliche.

Poiché tutte queste funzionalità (ad eccezione della copia dei risultati della ricerca in una cassetta postale di individuazione) sono ora disponibili negli strumenti di ricerca contenuto, eDiscovery e Advanced eDiscovery nel [Centro conformità Microsoft 365](./microsoft-365-compliance-center.md) (con funzionalità migliorate, affidabilità e supporto per un'ampia gamma di servizi Microsoft 365), è consigliabile iniziare a utilizzare questi strumenti il prima possibile. Per facilitare la transizione a questi altri strumenti di eDiscovery, nella tabella seguente sono elencati gli strumenti che è possibile utilizzare anziché In-Place eDiscovery e In-Place blocco.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Office 365 e Microsoft 365 Enterprise organizzazioni

- Office 365 e Microsoft 365 Education organizzazioni

- Office 365 e Microsoft 365 government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Sequenza temporale per il ritiro

- 1 luglio 2020: non sarà possibile creare nuove ricerche e blocchi, ma sarà comunque possibile eseguire, modificare ed eliminare le ricerche esistenti a proprio rischio. Il supporto Tecnico Microsoft non In-Place eDiscovery & blocchi nell'interfaccia di amministrazione di Exchange.

- 1 ottobre 2020: la funzionalità In-Place eDiscovery & blocchi nell'interfaccia di amministrazione di Exchange verrà posizionata in modalità di sola lettura. Ciò significa che sarà possibile rimuovere solo le ricerche e i blocchi esistenti.

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
<td>Ricerca, esportazione e conservazione a fini legali</td>
<td>Casi di eDiscovery di base nell'Centro conformità Microsoft 365 </td>
<td><p>L'utilizzo delle funzionalità dei casi di eDiscovery di base offre la parità funzionale per In-Place eDiscovery e In-Place blocchi. Sono incluse le attività seguenti:</p>
<ul>
<li>
<p>La ricerca si adatta a milioni di posizioni</p>
</li>
<li>
<p>Maggiore affidabilità per la ricerca, l'esportazione e l'archiviazione del contenuto</p>
</li>
<li>
<p>Ricerca di contenuto per Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups e altro contenuto archiviato in Office 365 applications</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Conservazione a fini di conservazione</td>
<td>Criteri di conservazione nella Centro conformità Microsoft 365</td>
<td><p>È possibile utilizzare i criteri di conservazione per conservare il contenuto e, se lo si desidera, eliminarlo dopo la scadenza del periodo di conservazione. Altre funzionalità includono:</p>
<ul>
<li>
<p>Applicazione di criteri all'intera organizzazione </p>
</li><li>
<p>Applicazione di criteri a percorsi di contenuto specifici, ad esempio Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams e Office 365 gruppi</p></li>
<li>
<p>Applicazione di criteri a utenti specifici</p></li></ul>
<p>Per ulteriori informazioni, vedere <a href="/microsoft-365/compliance/retention-policies">Informazioni sui criteri di conservazione e sulle etichette di conservazione.</a></td>
</tr>
<tr class="odd">
<td>Copiare i risultati della ricerca di posta elettronica in una cassetta postale di individuazione per la revisione</td><td>Rivedere i set in Advanced eDiscovery v2.0</td>
<td><p>Rivedere il contenuto in Microsoft 365 non è mai stato così facile. I set di recensioni dispongono di numerose funzionalità utili per ridurre il tempo e i dati necessari per la revisione, tra cui:</p>
<ul>
<li><p>Eseguire query di ricerca veloci e filtrare il contenuto in un set di recensioni</p></li>
<li><p>Analizzare il contenuto in un set di recensioni; ciò include il threading della posta elettronica, il rilevamento quasi duplicato, l'analisi dei temi e la codifica predittiva</p></li>
<li><p>Contrassegnare i documenti in un insieme da rivedere</p></li>
<li><p>Suggerimenti di tagging per identificare il contenuto dei privilegi del cliente avvocato</p></li></ul>
<p>Per altre informazioni, vedere <a href="/microsoft-365/compliance/overview-ediscovery-20">Panoramica della soluzione Advanced eDiscovery in Microsoft 365.</a></p>
<p>
<p>In alternativa, è possibile esportare i risultati della ricerca in file PST e quindi utilizzare Microsoft 365 importare i file PST in una cassetta postale di individuazione. Per istruzioni dettagliate, vedere <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.
</tr>
<tr class=even>
  <td>Copiare i messaggi da una cassetta postale a una cassetta postale diversa</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere a una persona l'accesso alla posta elettronica di un altro utente ,ad esempio quando un dipendente lascia l'organizzazione ed è necessario concedere a un'altra persona l'accesso alla posta elettronica dell'ex dipendente, è consigliabile assegnare a tale persona le autorizzazioni per accedere alla cassetta postale dell'ex dipendente. Pertanto, anziché copiare gli elementi della cassetta postale in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare a un utente le autorizzazioni necessarie per accedere alla cassetta postale di origine.</td>
  
  </tr>
<tr class="odd">
<td>Ripristinare elementi dalla cartella Elementi ripristinabili</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>È possibile ripristinare gli elementi eliminati <i></i> definitivamente (noti anche come elementi eliminati temporaneamente) nelle cassette postali, purché il periodo di conservazione degli elementi eliminati per un elemento non sia scaduto. Per ulteriori informazioni, vedere <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Domande frequenti su In-Place eDiscovery e In-Place blocchi

**Utilizzo la funzionalità copia risultati di ricerca di In-Place eDiscovery & blocchi nell'interfaccia di amministrazione di Exchange per copiare i risultati della ricerca in una cassetta postale di individuazione per la revisione da parte degli avvocati. Quali opzioni sono disponibili ora?**

Esistono due modi per replicare questa funzionalità oggi. Il primo è usare i [set di revisione in Advanced eDiscovery v2.0.](./view-documents-in-review-set.md) I set di revisioni dispongono di molte delle stesse funzionalità disponibili in uno strumento di revisione tradizionale, ad esempio la ricerca rapida di documenti, il tagging, il threading della posta elettronica, il raggruppamento quasi duplicato, l'analisi dei temi e la codifica predittiva. Se si desidera comunque utilizzare le cassette postali di individuazione per la revisione, la seconda opzione è esportare i risultati della ricerca in file PST e quindi importare i file PST in una cassetta postale di individuazione utilizzando la funzionalità di importazione [PST](use-network-upload-to-import-pst-files.md) nel Centro conformità Microsoft.

**Come si controllano le posizioni del contenuto (ad esempio le cassette postali o i siti) in cui un responsabile di eDiscovery può eseguire ricerche utilizzando i nuovi strumenti?**

Il Centro conformità Microsoft 365 utilizza anche i [limiti di conformità](set-up-compliance-boundaries.md) per controllare quali posizioni di contenuto possono essere cercate da un responsabile di eDiscovery. I limiti di conformità sono utili nelle entità governative che devono rimanere entro i limiti delle agenzie o nelle società multinazionali necessarie per rispettare i consigli di amministrazione geografici.

**Come posso spostare le ricerche e i blocchi correnti nel Centro conformità Microsoft 365?**

È possibile eseguire la migrazione In-Place ricerche e blocchi di eDiscovery dall'interfaccia di amministrazione di Exchange tramite PowerShell. Per istruzioni, vedere [Migrate searches and holds from the EAC to the Centro conformità Microsoft 365](./migrate-legacy-ediscovery-searches-and-holds.md).

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlets

In base all'avviso originale annunciato il 1° luglio 2017 nell'interfaccia di amministrazione di Exchange, la funzionalità di blocco di In-Place eDiscovery & e i cmdlet **\* -MailboxSearch** corrispondenti vengono ritirati. Questi cmdlet consentono agli utenti di cercare, mantenere ed esportare il contenuto delle cassette postali per richieste legali, normative e pubbliche.

Poiché queste funzionalità sono ora disponibili in [<span class="underline">PowerShell</span>](./microsoft-365-compliance-center.md) Centro conformità Microsoft 365 e Office 365 Security & Compliance Center con prestazioni e scalabilità migliorate, è consigliabile utilizzare questi cmdlet migliorati. Questi cmdlet includono [<span class="underline"> \* -ComplianceCase,</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline"> \* -ComplianceSearch,</span>](/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* -CaseHoldPolicy,</span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)e [<span class="underline"> \* -ComplianceSearchAction.</span>](/powershell/module/exchange/get-compliancesearchaction)

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Office 365 e Microsoft 365 Enterprise organizzazioni

- Office 365 e Microsoft 365 Education organizzazioni

- Office 365 e Microsoft 365 government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

- 1 luglio 2020: Non sarà possibile utilizzare **New-MailboxSearch** per creare nuove ricerche eDiscovery di In-Place e blocchi In-Place, ma è comunque possibile utilizzare i cmdlet per eseguire, modificare ed eliminare le ricerche e i blocchi esistenti a proprio rischio. Il supporto Tecnico Microsoft non fornirà più assistenza per questi tipi di ricerche e blocchi.

- 1 ottobre 2020: come indicato in precedenza, la funzionalità di eDiscovery & di In-Place nell'interfaccia di amministrazione di Exchange verrà posizionata in modalità di sola lettura. Ciò significa anche che non sarà possibile utilizzare i cmdlet **New-MailboxSearch,** **Start-MailboxSearch** o **Set-MailboxSearch.** Potrai solo ottenere e rimuovere ricerche e blocchi esistenti.

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
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction funzionano insieme per facilitare la ricerca e l'esportazione del contenuto. È possibile creare una nuova ricerca e visualizzare la stima della ricerca utilizzando i cmdlet <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch.</strong> È quindi possibile utilizzare il cmdlet <strong>New-ComplianceSearchAction</strong> per esportare i risultati della ricerca. Sarà comunque necessario utilizzare lo strumento eDiscovery di base nella Centro conformità Microsoft 365 per scaricare i risultati della ricerca nel computer locale.</p>
<p>
<p><strong>Nota:</strong> Se si utilizzano questi cmdlet per creare ricerche non associate a un caso di <strong></strong> eDiscovery di base, queste ricerche saranno disponibili nella pagina Ricerca contenuto del Centro conformità Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Archiviazione del contenuto in una cassetta postale</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>I blocchi nel Centro conformità Microsoft 365 devono essere associati a complianceCase. Prima di tutto, crea il caso di conformità e quindi crea un CaseHoldPolicy e un CaseHoldRule.</p>
<p><strong>Nota:</strong> La creazione di un Oggetto CaseHoldPolicy senza una creazione di CaseHoldRule rende il blocco inoperabile fino a quando caseHoldRule non viene creato e associato a CaseHoldPolicy. Per ulteriori informazioni, vedere la documentazione del cmdlet.</p></td>
</tr>
<tr class="odd">
<td>Copiare i risultati della ricerca in una cassetta postale di individuazione</td>
<td>Nessuno</td>
<td>Non esiste alcuna sostituzione diretta per questa funzionalità perché non fornisce l'accesso a tutti Microsoft 365 servizi. Vedi le seguenti domande frequenti per soluzioni alternative.</td>
</tr>
  <tr class=even>
  <td>Copiare i messaggi da una cassetta postale a una cassetta postale diversa</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere a una persona l'accesso alla posta elettronica di un altro utente ,ad esempio quando un dipendente lascia l'organizzazione ed è necessario concedere a un'altra persona l'accesso alla posta elettronica dell'ex dipendente, è consigliabile assegnare a tale persona le autorizzazioni per accedere alla cassetta postale dell'ex dipendente. Anziché copiare gli elementi della cassetta postale in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare a un utente le autorizzazioni per accedere alla cassetta postale di origine.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Domande frequenti sui cmdlet ***-MailboxSearch**

**Viene utilizzata la ricerca di copia per esportare i messaggi di posta elettronica o i messaggi istantanei per altri scopi eDiscovery e indagini legali. Quali altre opzioni sono disponibili dopo la ritirata di questi cmdlet?**

Le API [<span class="underline">di Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) forniscono diversi metodi per l'estrazione dei dati per l'analisi e altri scopi molto più resilienti e scalabili rispetto all'utilizzo dei cmdlet **\* -MailboxSearch.**

**Come è possibile eseguire la migrazione delle ricerche e dei blocchi nel Centro conformità Microsoft 365?**

È possibile eseguire la migrazione In-Place ricerche e blocchi di eDiscovery dall'interfaccia di amministrazione Exchange tramite uno script di PowerShell. Per ulteriori informazioni, vedere [Migrate legacy eDiscovery searches and holds to the Centro conformità Microsoft 365](migrate-legacy-eDiscovery-searches-and-holds.md).

**Dopo aver ritirato i cmdlet, sarà comunque possibile rimuovere o recuperare le ricerche?**

Sì, anche se stiamo rimuovendo la possibilità di creare e modificare le ricerche, sarà comunque possibile utilizzare **Get-MailboxSearch** e **Remove-MailboxSearch** fino a nuovo avviso. Tuttavia, l'utilizzo di questi cmdlet sarà a proprio rischio dopo le date di ritiro e il supporto Tecnico Microsoft non sarà più in grado di fornire assistenza.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

Il cmdlet **Search-Mailbox** in Exchange Online PowerShell viene ritirato come originariamente annunciato in un avviso nell'output del cmdlet a partire dal 2018. Il cmdlet **Search-Mailbox** è stato originariamente utilizzato per cercare la cassetta postale di un utente ed eliminare contenuto dannoso. È consigliabile iniziare a utilizzare i cmdlet **New-ComplianceSearch** e **New-ComplianceSearchAction** in PowerShell del Centro sicurezza & e conformità di Office 365 per cercare ed eliminare il contenuto. Per un'esperienza di sicurezza integrata, le funzionalità Microsoft 365 [<span class="underline">sicurezza</span>](../security/index.yml) forniscono una solida protezione dalle minacce per la posta elettronica e molti altri servizi Microsoft.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Office 365 e Microsoft 365 Enterprise organizzazioni

- Office 365 e Microsoft 365 Education organizzazioni

- Office 365 e Microsoft 365 government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

-  1 luglio 2020: il cmdlet **Search-Mailbox** non sarà più disponibile e il supporto tecnico Microsoft non fornirà più assistenza.

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
<td>Cercare una cassetta postale</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction funzionano insieme per facilitare la ricerca e l'esportazione del contenuto. È possibile creare una nuova ricerca e visualizzare la stima della ricerca utilizzando i cmdlet <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch.</strong> È quindi possibile utilizzare il <strong>comando New-ComplianceSearchAction -Export</strong> per esportare i risultati della ricerca. Sarà comunque necessario utilizzare lo strumento eDiscovery di base nella Centro conformità Microsoft 365 per scaricare i risultati della ricerca nel computer locale.</p></p>
</td>
</tr>
<tr class="even">
<td>Eliminare la posta elettronica in blocco da una cassetta postale</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">Configurare i criteri di archiviazione ed eliminazione per le cassette postali</span></a></p>
<p></p></td>
<td><p>Gli amministratori possono creare un criterio di archiviazione ed eliminazione che sposta automaticamente gli elementi nella cassetta postale di archiviazione di un utente ed elimina automaticamente gli elementi dalla cassetta postale.</p>
</td>
</tr>
<tr class="even">
<td>Copiare i risultati della ricerca in una cassetta postale di individuazione</td>
<td> </td>
<td>Non esiste alcuna sostituzione diretta per questa funzionalità perché non fornisce l'accesso a tutti Microsoft 365 servizi. Per soluzioni alternative, vedere le domande frequenti nella sezione <strong>*-MailboxSearch cmdlets.</strong> </td>
</tr>
<tr class=odd>
  <td>Copiare i messaggi da una cassetta postale a una cassetta postale diversa</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
  <td>Per concedere a una persona l'accesso alla posta elettronica di un altro utente ,ad esempio quando un dipendente lascia l'organizzazione ed è necessario concedere a un'altra persona l'accesso alla posta elettronica dell'ex dipendente, è consigliabile assegnare a tale persona le autorizzazioni per accedere alla cassetta postale dell'ex dipendente. Pertanto, anziché copiare gli elementi della cassetta postale in un'altra cassetta postale utente o in una cassetta postale condivisa, è sufficiente assegnare a un utente l'autorizzazione per accedere alla cassetta postale di origine.</td>
</tr>
<tr class=even>
  <td>Eliminare i messaggi da una cassetta postale</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>I cmdlet ComplianceSearch e ComplianceSearchAction funzionano insieme per facilitare la ricerca e l'eliminazione del contenuto. È possibile creare ed eseguire una ricerca con i cmdlet <strong>New-ComplianceSearch</strong> e <strong>New-ComplianceSearch</strong> e quindi eliminare il contenuto utilizzando il comando <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Per ulteriori informazioni, vedere <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</p>
</td>
</tr>
<tr class="odd"> 
<td>Eliminare i messaggi da una cassetta postale</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assegnare autorizzazioni a una cassetta postale</a></td>
<td>Per eliminare i messaggi da una cassetta postale, assegnare a un amministratore le autorizzazioni per accedere alla cassetta postale del dipendente. I messaggi possono essere eliminati e riciclati in base alle esigenze sfruttando le funzionalità di ricerca e visualizzazione incorporate in Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Operazioni API dei servizi Web

Queste operazioni nell'API dei servizi Web Exchange vengono utilizzate dalla funzionalità eDiscovery & di In-Place nell'interfaccia di amministrazione di Exchange e dai cmdlet **\* -MailboxSearch** corrispondenti in Exchange Online PowerShell. Verranno ritirati anche come parte del ritiro degli altri strumenti legacy di eDiscovery.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Office 365 e Microsoft 365 Enterprise organizzazioni

- Office 365 e Microsoft 365 Education organizzazioni

- Office 365 e Microsoft 365 government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

- 1 luglio 2020: le operazioni GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes e GetHoldOnMailboxes non saranno più disponibili e il supporto tecnico Microsoft non fornirà più assistenza.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, che è la versione di Advanced eDiscovery disponibile in un caso di eDiscovery di base facendo clic su Passa a Advanced eDiscovery **,** viene ritirato. La funzionalità è stata sostituita dalla nuova soluzione [Advanced eDiscovery nella](./ediscovery.md) Centro conformità Microsoft 365.

Per determinare se l'organizzazione utilizza Advanced eDiscovery v1.0:

1. Visitare il [Centro conformità Microsoft 365](https://compliance.microsoft.com).

2. Nel riquadro di spostamento sinistro del Centro conformità fare clic su **eDiscovery > Core** e aprire un caso di Core eDiscovery.

3. Se viene visualizzato il pulsante Passa **a Advanced eDiscovery,** facendo clic su di esso verrà visualizzata la versione 1.0 di Advanced eDiscovery, che viene ritirata. La possibilità di creare e gestire i casi in Core eDiscovery non sarà influenzata. Solo la possibilità di aggiungere e analizzare i dati del caso in Advanced eDiscovery v1.0 (facendo clic su Passa a **Advanced eDiscovery**) viene ritirata.

La nuova soluzione Advanced eDiscovery in Microsoft 365 (nota anche come *Advanced eDiscovery v2.0)* offre tutte le funzionalità della soluzione originale, ma ora include un approccio basato sul responsabile per identificare il contenuto in altri servizi Microsoft 365, raccoglierlo e quindi aggiungerlo a un set di revisione in cui i revisori possono sfruttare le funzionalità di ricerca rapida, di tagging e di analisi per facilitare l'individuazione di documenti pertinenti. Advanced eDiscovery ora include un'elaborazione migliorata e visualizzatori nativi sia per i tipi di [](./supported-filetypes-ediscovery20.md) file Microsoft che per i tipi di file non Microsoft, è disponibile un elenco completo dei tipi di file e i campi di metadati supportati sono [disponibili qui.](./document-metadata-fields-in-advanced-ediscovery.md) Inoltre, la nuova soluzione Advanced eDiscovery offre una potente funzionalità di gestione dei blocchi dei custodi che consente di applicare blocchi al contenuto in servizi diversi, notificare agli utenti le esenzioni e tenere traccia delle risposte dei custodi, tutto in un caso Advanced eDiscovery.

Per accedere ad Advanced eDiscovery v2.0:

1. Visitare il [Centro conformità Microsoft 365](https://compliance.microsoft.com).

2. Nel riquadro di spostamento sinistro del Centro conformità Microsoft 365, fare clic su **Mostra tutto**, quindi su **eDiscovery > Advanced**.

Al momento, è consigliabile iniziare a eseguire la transizione del flusso di lavoro di eDiscovery alla nuova Advanced eDiscovery funzionalità. Se necessario, è possibile archiviare i Advanced eDiscovery 1.0 esportando il contenuto e archiviandoli offline. Anche se sarà comunque possibile accedere Advanced eDiscovery v1.0 nei casi esistenti fino al 31 dicembre 2020, il Supporto Tecnico Microsoft non fornirà supporto dopo il 1° ottobre 2020. Per altri dettagli, vedi la sequenza temporale seguente.

### <a name="scope-of-affected-organizations"></a>Ambito delle organizzazioni interessate

- Office 365 e Microsoft 365 Enterprise organizzazioni

- Office 365 e Microsoft 365 Education organizzazioni

- Office 365 e Microsoft 365 government; ciò include GCC, GCC High e DoD

- Office 365 Germany

### <a name="timeline"></a>Sequenza temporale

- 1 luglio 2020: non sarà possibile creare nuovi casi Advanced eDiscovery v1.0.

- 1 ottobre 2020: non sarà possibile aggiungere nuovi dati (Preparare i risultati della ricerca per Advanced eDiscovery) a tutti i casi. Sarà possibile continuare a lavorare con i dati nei casi esistenti a proprio rischio. Il Supporto Tecnico Microsoft non fornirà più assistenza. 

- 31 dicembre 2020: non sarà possibile accedere Advanced eDiscovery casi v1.0.

### <a name="alternative-tools"></a>Strumenti alternativi

Soluzione [Advanced eDiscovery nella](./overview-ediscovery-20.md) Centro conformità Microsoft 365.