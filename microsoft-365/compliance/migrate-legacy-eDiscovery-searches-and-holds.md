---
title: Eseguire la migrazione delle ricerche e dei blocchi legacy di eDiscovery nel Centro conformità Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ef5562aa6f5c7519d19452100b55dd4bc30d4126
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926324"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>Eseguire la migrazione delle ricerche e dei blocchi legacy di eDiscovery nel Centro conformità Microsoft 365

Il Centro conformità Microsoft 365 offre un'esperienza migliorata per l'utilizzo di eDiscovery, tra cui: maggiore affidabilità, prestazioni migliori e molte funzionalità personalizzate per i flussi di lavoro di eDiscovery, tra cui casi per organizzare il contenuto in base alla materia, set di revisione per esaminare il contenuto e l'analisi per aiutare a ridurre i dati per la revisione, ad esempio il raggruppamento quasi duplicato, il threading della posta elettronica, l'analisi dei temi e la codifica predittiva.

Per aiutare i clienti a sfruttare le funzionalità nuove e migliorate, in questo articolo vengono fornite indicazioni di base su come eseguire la migrazione delle ricerche e dei blocchi di eDiscovery di In-Place dall'interfaccia di amministrazione di Exchange al Centro conformità Microsoft 365.

> [!NOTE]
> Poiché esistono molti scenari diversi, in questo articolo vengono fornite indicazioni generali per la transizione di ricerche e blocchi a un caso di eDiscovery di base nel Centro conformità Microsoft 365. L'utilizzo dei casi di eDiscovery non è sempre necessario, ma aggiunge un ulteriore livello di sicurezza consentendo di assegnare le autorizzazioni per controllare chi ha accesso ai casi di eDiscovery nell'organizzazione.

## <a name="before-you-begin"></a>Prima di iniziare

- Per eseguire i comandi di PowerShell descritti in questo articolo, è necessario essere membri del gruppo di ruoli Responsabile eDiscovery nel Centro sicurezza & conformità. È inoltre necessario essere membri del gruppo di ruoli Gestione individuazione nell'interfaccia di amministrazione di Exchange.

- In questo articolo vengono fornite indicazioni su come creare un blocco di eDiscovery. Il criterio di blocco verrà applicato alle cassette postali tramite un processo asincrono. Quando si crea un blocco di eDiscovery, è necessario creare sia caseHoldPolicy che CaseHoldRule, altrimenti il blocco non verrà creato e i percorsi del contenuto non verranno messi in attesa.

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a>Passaggio 1: Connettersi a PowerShell di Exchange Online e PowerShell & centro conformità

Il primo passaggio consiste nel connettersi a PowerShell di Exchange Online e PowerShell & Centro conformità. È possibile copiare lo script seguente, incollarlo in una finestra di PowerShell ed eseguirlo. Verranno richieste le credenziali per l'organizzazione a cui si desidera connettersi. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

È necessario eseguire i comandi nei passaggi seguenti in questa sessione di PowerShell.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Passaggio 2: Ottenere un elenco di In-Place ricerche eDiscovery tramite Get-MailboxSearch

Dopo aver eseguito l'autenticazione, è possibile ottenere un elenco delle In-Place eDiscovery eseguendo il cmdlet **Get-MailboxSearch.** Copiare e incollare il comando seguente in PowerShell ed eseguirlo. Verrà elencato un elenco di ricerche con i relativi nomi e lo stato di qualsiasi In-Place esenzioni.

```powershell
Get-MailboxSearch
```

L'output del cmdlet sarà simile al seguente:

![Esempio di PowerShell Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Passaggio 3: Ottenere informazioni sulle ricerche eDiscovery In-Place e In-Place esenzioni di cui si desidera eseguire la migrazione

Anche in questo caso si utilizzerà il cmdlet **Get-MailboxSearch,** ma questa volta per ottenere le proprietà della ricerca. È possibile archiviare queste proprietà in una variabile per utilizzarle in un secondo momento. Nell'esempio seguente i risultati del cmdlet **Get-MailboxSearch** vengono archiviati in una variabile e quindi vengono visualizzate le proprietà della ricerca.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

L'output di questi due comandi sarà simile al seguente:

![Esempio di output di PowerShell dall'Get-MailboxSearch per una singola ricerca](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> La durata del blocco In-Place in questo esempio è indefinita (*ItemHoldPeriod: Unlimited*). Questo è tipico per gli scenari di eDiscovery e indagini legali. Se la durata del blocco ha un valore diverso da quello indefinito, è probabile che il blocco venga utilizzato per conservare il contenuto in uno scenario di conservazione. Anziché utilizzare i cmdlet di eDiscovery in PowerShell del Centro sicurezza & e conformità per gli scenari di conservazione, è consigliabile utilizzare [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) e [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) per conservare il contenuto. Il risultato dell'utilizzo di questi cmdlet sarà simile all'utilizzo di **New-CaseHoldPolicy** e **New-CaseHoldRule,** ma sarà possibile specificare un periodo di conservazione e un'azione di conservazione, ad esempio l'eliminazione del contenuto dopo la scadenza del periodo di conservazione. Inoltre, l'utilizzo dei cmdlet di conservazione non richiede di associare i blocchi di conservazione a un caso di eDiscovery.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>Passaggio 4: Creare un caso nel Centro conformità Microsoft 365

Per creare un blocco di eDiscovery, è necessario creare un caso di eDiscovery a cui associare il blocco. Nell'esempio seguente viene creato un caso di eDiscovery utilizzando un nome di propria scelta. Le proprietà del nuovo caso verranno archiviate in una variabile per l'utilizzo in un secondo momento. È possibile visualizzare tali proprietà eseguendo il `$case | FL` comando dopo aver creato il caso.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Esempio di esecuzione del comando New-ComplianceCase](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Passaggio 5: Creare il blocco di eDiscovery

Dopo aver creato il caso, è possibile creare il blocco e associarlo al caso creato nel passaggio precedente. È importante ricordare che è necessario creare sia un criterio di blocco del caso che una regola di blocco del caso. Se la regola di blocco del caso non viene creata dopo la creazione del criterio di blocco del caso, il blocco di eDiscovery non verrà creato e il contenuto non verrà messo in attesa.

Eseguire i comandi seguenti per creare di nuovo il blocco di eDiscovery di cui si desidera eseguire la migrazione. In questi esempi vengono utilizzate le proprietà In-Place blocco del passaggio 3 di cui si desidera eseguire la migrazione. Il primo comando crea un nuovo criterio di blocco del caso e salva le proprietà in una variabile. Il secondo comando crea la regola di blocco del caso corrispondente.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Esempio di utilizzo dei cmdlet NewCaseHoldPolicy e NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Passaggio 6: Verificare il blocco di eDiscovery

Per assicurarsi che non si siano verificati problemi durante la creazione del blocco, è bene verificare che lo stato di distribuzione del blocco sia corretto. Distribuzione significa che il blocco è stato applicato a tutti i percorsi di contenuto specificati nel *parametro ExchangeLocation* nel passaggio precedente. A tale scopo, è possibile eseguire il cmdlet **Get-CaseHoldPolicy.** Poiché le proprietà salvate nella variabile *$policy* creata nel passaggio precedente non vengono aggiornate automaticamente nella variabile, è necessario eseguire di nuovo il cmdlet per verificare che la distribuzione sia riuscita. La corretta distribuzione dei criteri di blocco dei casi può richiedere da 5 a 24 ore.

Eseguire il comando seguente per verificare che il blocco di eDiscovery sia stato distribuito correttamente.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

Il valore **di Success** per la proprietà *DistributionStatus* indica che il blocco è stato eseguito correttamente nei percorsi del contenuto. Se la distribuzione non è ancora completata, viene visualizzato il valore **Pending.**

![Esempio Get-CaseHoldPolicy PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Passaggio 7: Creare la ricerca

L'ultimo passaggio consiste nel creare di nuovo la ricerca identificata nel passaggio 3 e associarla al caso. Dopo aver creato la ricerca, è possibile eseguirla utilizzando il cmdlet **Start-ComplianceSearch** o eseguirla in un secondo momento.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Esempio New-ComplianceSearch PowerShell](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>Passaggio 8: Verificare il caso, il blocco e la ricerca nel Centro conformità Microsoft 365

Per assicurarsi che tutto sia configurato correttamente, accedere al Centro conformità Microsoft 365 all'indirizzo e fare clic [https://compliance.microsoft.com](https://compliance.microsoft.com) su **eDiscovery > Core**.

![eDiscovery del Centro conformità Microsoft 365](../media/MigrateLegacyeDiscovery7.png)

Il caso creato nel passaggio 3 è elencato nella **pagina Core eDiscovery.** Aprire il caso e quindi notare l'esenzione creata nel passaggio 4 nell'elenco nella **scheda Esenzioni.** È possibile fare clic sul blocco per visualizzare i dettagli, incluso il numero di cassette postali a cui viene applicato il blocco e lo stato di distribuzione.

![Blocchi di eDiscovery nel Centro conformità Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

La ricerca creata nel passaggio 7 è elencata nella scheda **Ricerche** del caso di eDiscovery.

![Ricerca di casi di eDiscovery nel Centro conformità Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

Se si esegue la migrazione In-Place ricerca eDiscovery ma non la si associa a un caso di eDiscovery, verrà elencata nella pagina Ricerca contenuto nel Centro conformità Microsoft 365.

## <a name="more-information"></a>Ulteriori informazioni

- Per ulteriori informazioni sulle In-Place eDiscovery & nell'interfaccia di amministrazione di Exchange, vedere:
  
  - [eDiscovery sul posto](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [Conservazione in locale e per controversia legale](/exchange/security-and-compliance/in-place-and-litigation-holds)

- Per ulteriori informazioni sui cmdlet di PowerShell utilizzati nell'articolo, vedere:

  - [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)
  
  - [New-ComplianceCase](/powershell/module/exchange/new-compliancecase)

  - [New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy)
  
  - [New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule)

  - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
  
  - [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

  - [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

- Per ulteriori informazioni sul Centro conformità Microsoft 365, vedere Panoramica del Centro conformità [Microsoft 365.](microsoft-365-compliance-center.md)