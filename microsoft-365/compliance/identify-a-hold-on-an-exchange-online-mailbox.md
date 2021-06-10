---
title: Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come identificare i diversi tipi di blocco che possono essere inseriti in una Exchange Online cassetta postale in Microsoft 365.
ms.openlocfilehash: 0fdfbd4503a4ddffd2ce2dd97c6af42684aea293
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917536"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online

In questo articolo viene illustrato come identificare i blocchi Exchange Online cassette postali in Microsoft 365.

Microsoft 365 diversi modi in cui l'organizzazione può impedire l'eliminazione definitiva del contenuto delle cassette postali. In questo modo l'organizzazione può conservare i contenuti per soddisfare le normative di conformità o durante indagini legali e di altro tipo. Ecco un elenco delle funzionalità di conservazione (denominate anche *esenzioni)* in Office 365:

- **[Conservazione per controversia legale](create-a-litigation-hold.md):** Blocchi applicati alle cassette postali degli utenti in Exchange Online.

- **[Blocco di eDiscovery](create-ediscovery-holds.md):** Blocchi associati a un caso di eDiscovery di base nel Centro sicurezza e conformità. I blocchi di eDiscovery possono essere applicati alle cassette postali degli utenti e alla cassetta postale corrispondente per Microsoft 365 gruppi e Microsoft Teams.

- **[Blocco sul posto](/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Blocchi applicati alle cassette postali degli utenti utilizzando lo strumento In-Place eDiscovery & blocco nell'interfaccia di amministrazione di Exchange in Exchange Online. 

   > [!NOTE]
   > In-Place le esenzioni sono state ritirate e non è più possibile creare In-Place esenzioni o applicarle alle cassette postali. Tuttavia, In-Place le esenzioni potrebbero ancora essere applicate alle cassette postali dell'organizzazione, motivo per cui sono incluse in questo articolo. Per ulteriori informazioni, vedere [Ritiro degli strumenti legacy di eDiscovery.](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)

- **[Microsoft 365 criteri di conservazione](retention.md):** Può essere configurato per conservare (o conservare ed eliminare) il contenuto nelle cassette postali degli utenti in Exchange Online e nella cassetta postale corrispondente per Microsoft 365 Gruppi e Microsoft Teams. È inoltre possibile creare criteri di conservazione per conservare Skype for Business conversazioni, archiviate nelle cassette postali degli utenti.

  Esistono due tipi di criteri Microsoft 365 di conservazione che possono essere assegnati alle cassette postali.

    - **Criteri di conservazione percorso specifici:** Si tratta di criteri assegnati ai percorsi di contenuto di utenti specifici. Utilizzare il cmdlet **Get-Mailbox** in Exchange Online PowerShell per ottenere informazioni sui criteri di conservazione assegnati a cassette postali specifiche. Per ulteriori informazioni su questo tipo di criteri di conservazione, vedere la sezione [Criteri](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) con inclusioni o esclusioni specifiche nella documentazione relativa ai criteri di conservazione.

    - **Criteri di conservazione a livello di organizzazione:** Si tratta di criteri assegnati a tutti i percorsi di contenuto dell'organizzazione. Utilizzare il cmdlet **Get-OrganizationConfig** in Exchange Online PowerShell per ottenere informazioni sui criteri di conservazione a livello di organizzazione. Per ulteriori informazioni su questo tipo di criteri di conservazione, vedere la sezione Criteri applicabili [a](create-retention-policies.md#a-policy-that-applies-to-entire-locations) intere posizioni nella documentazione relativa ai criteri di conservazione.

- **[Microsoft 365](retention.md)** etichette di conservazione: se un utente applica un'etichetta di conservazione Microsoft 365 (configurata per conservare  il contenuto o conservare ed eliminare il contenuto) a qualsiasi cartella o elemento nella cassetta postale, viene applicato un blocco alla cassetta postale come se la cassetta postale fosse stata messa in conservazione per controversia legale o assegnata a un criterio di conservazione di Microsoft 365. Per ulteriori informazioni, vedere la sezione Identificazione delle cassette postali in attesa perché è stata applicata un'etichetta di conservazione a una cartella o [a un elemento](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) in questo articolo.

Per gestire le cassette postali in attesa, potrebbe essere necessario identificare il tipo di blocco che viene effettuato su una cassetta postale in modo che sia possibile eseguire attività quali la modifica della durata del blocco, la rimozione temporanea o definitiva del blocco o l'esclusione di una cassetta postale da un criterio di conservazione di Microsoft 365. In questi casi, il primo passaggio consiste nell'identificare il tipo di blocco sulla cassetta postale. Poiché è possibile inserire più blocchi (e diversi tipi di esenzioni) in una singola cassetta postale, è necessario identificare tutti i blocchi inseriti in una cassetta postale se si desidera rimuovere o modificare un blocco.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Passaggio 1: Ottenere il GUID per i blocchi effettuati su una cassetta postale

È possibile eseguire i due cmdlet seguenti in Exchange Online PowerShell per ottenere il GUID dei blocchi che vengono inseriti in una cassetta postale. Dopo aver ottenuto un GUID, è possibile utilizzarlo per identificare il blocco specifico nel passaggio 2. Un blocco per controversia legale non è identificato da un GUID. I blocchi per controversia legale sono abilitati o disabilitati per una cassetta postale.

- **Get-Mailbox:** Utilizzare questo cmdlet per determinare se il blocco per controversia legale è abilitato per una cassetta postale e per ottenere i GUID per i blocchi di eDiscovery, i blocchi di In-Place e i criteri di conservazione Microsoft 365 assegnati in modo specifico a una cassetta postale. L'output di questo cmdlet indicherà anche se una cassetta postale è stata esplicitamente esclusa da un criterio di conservazione a livello di organizzazione.

- **Get-OrganizationConfig:** Utilizzare questo cmdlet per ottenere i GUID per i criteri di conservazione a livello di organizzazione.

Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Eseguire il comando seguente per ottenere informazioni sui blocchi e sui criteri Microsoft 365 di conservazione applicati a una cassetta postale.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Se nella proprietà InPlaceHolds sono presenti troppi valori e non vengono visualizzati tutti, è possibile eseguire il comando per visualizzare ogni GUID su `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` una riga separata.

Nella tabella seguente viene descritto come identificare diversi tipi di blocchi in base ai valori della proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-Mailbox.**

|Tipo di blocco  |Valore di esempio  |Come identificare il blocco  |
|---------|---------|---------|
|Conservazione in caso di dispute     |    `True`     |     Il blocco per controversia legale è abilitato per una cassetta postale quando la *proprietà LitigationHoldEnabled* è impostata su `True` .    |
|Blocco di eDiscovery     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *proprietà InPlaceHolds* contiene il GUID di qualsiasi blocco associato a un caso di eDiscovery nel Centro sicurezza e conformità. È possibile indicare che si tratta di un blocco di eDiscovery perché il GUID inizia con il prefisso (che indica un `UniH` blocco unificato).      |
|Blocco sul posto     |     `c0ba3ce811b6432a8751430937152491` <br/> oppure <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La *proprietà InPlaceHolds* contiene il GUID del In-Place blocco che viene posizionato sulla cassetta postale. È possibile indicare che si tratta di In-Place blocco perché il GUID non inizia con un prefisso o inizia con il `cld` prefisso.     |
|Microsoft 365 criteri di conservazione applicati in modo specifico alla cassetta postale     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> oppure <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La proprietà InPlaceHolds contiene i GUID di qualsiasi criterio di conservazione percorso specifico applicato alla cassetta postale. È possibile identificare i criteri di conservazione perché il GUID inizia con `mbx` il prefisso o `skp` . Il prefisso indica che il criterio di conservazione viene applicato Skype for Business conversazioni nella cassetta postale `skp` dell'utente.    |
|Escluso da un criterio di conservazione Microsoft 365 a livello di organizzazione     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Se una cassetta postale viene esclusa da un criterio di conservazione Microsoft 365 a livello di organizzazione, il GUID del criterio di conservazione da cui è esclusa la cassetta postale viene visualizzato nella proprietà InPlaceHolds ed è identificato dal `-mbx` prefisso.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Se la *proprietà InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox,** è possibile che alla cassetta postale siano ancora applicati uno o più criteri di conservazione Microsoft 365 a livello di organizzazione. Eseguire il comando seguente in Exchange Online PowerShell per ottenere un elenco di GUID per i criteri di conservazione Microsoft 365 a livello di organizzazione.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Se nella proprietà InPlaceHolds sono presenti troppi valori e non vengono visualizzati tutti, è possibile eseguire il comando per visualizzare ogni GUID su `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` una riga separata.

Nella tabella seguente vengono descritti i diversi tipi di blocchi a livello di organizzazione e come identificare ogni tipo in base ai GUID contenuti nella proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-OrganizationConfig.**

|Tipo di blocco  |Valore di esempio  |Descrizione  |
|---------|---------|---------|
|Microsoft 365 criteri di conservazione applicati Exchange cassette postali, Exchange pubbliche e Teams chat    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   I criteri di conservazione a livello di organizzazione applicati Exchange cassette postali, Exchange cartelle pubbliche e chat 1xN in Microsoft Teams sono identificati dai GUID che iniziano con il `mbx` prefisso. Nota Le chat 1xN vengono archiviate nella cassetta postale dei singoli partecipanti alla chat.      |
|Microsoft 365 criteri di conservazione applicati ai Microsoft 365 e ai Teams del canale     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    I criteri di conservazione a livello di organizzazione applicati ai Microsoft 365 e ai messaggi di canale Microsoft Teams sono identificati dai GUID che iniziano con il `grp` prefisso. Nota I messaggi del canale vengono archiviati nella cassetta postale del gruppo associata a un team Microsoft.     |

Per ulteriori informazioni sui criteri di conservazione applicati Microsoft Teams, vedere [Informazioni sui criteri di conservazione per Microsoft Teams](retention-policies-teams.md).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Informazioni sul formato del valore InPlaceHolds per i criteri di conservazione

Oltre al prefisso (mbx, skp o grp) che identifica un elemento nella proprietà InPlaceHolds come criterio di conservazione di Microsoft 365, il valore contiene anche un suffisso che identifica il tipo di azione di conservazione configurata per il criterio. Ad esempio, il suffisso di azione è evidenziato in grassetto negli esempi seguenti:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

Nella tabella seguente vengono definite le tre possibili azioni di conservazione:

|Valore  |Descrizione  |
|---------|---------|
|**1**     | Indica che il criterio di conservazione è configurato per eliminare gli elementi. Il criterio non conserva gli elementi.        |
|**2**    |    Indica che il criterio di conservazione è configurato per contenere gli elementi. Il criterio non elimina gli elementi dopo la scadenza del periodo di conservazione.     |
|**3**     |   Indica che il criterio di conservazione è configurato per contenere gli elementi ed eliminarli dopo la scadenza del periodo di conservazione.      |

Per ulteriori informazioni sulle azioni di conservazione, vedere la [sezione Conservazione del contenuto per un periodo di tempo](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) specifico.
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Passaggio 2: Usare il GUID per identificare il blocco

Dopo aver ottenuto il GUID per un blocco applicato a una cassetta postale, il passaggio successivo consiste nell'utilizzare tale GUID per identificare il blocco. Nelle sezioni seguenti viene illustrato come identificare il nome dell'esenzione (e altre informazioni) utilizzando il GUID del blocco.

### <a name="ediscovery-holds"></a>Blocchi di eDiscovery

Eseguire i comandi seguenti in PowerShell & Centro sicurezza e conformità per identificare un blocco eDiscovery applicato alla cassetta postale. Utilizzare il GUID (senza includere il prefisso UniH) per il blocco di eDiscovery identificato nel passaggio 1. 

Per connettersi a PowerShell & Centro sicurezza e conformità, vedere Connessione [a PowerShell](/powershell/exchange/connect-to-scc-powershell)& Centro sicurezza e conformità .

Il primo comando crea una variabile che contiene informazioni sull'esenzione. Questa variabile viene utilizzata negli altri comandi. Nel secondo comando viene visualizzato il nome del caso di eDiscovery a cui è associato il blocco. Il terzo comando visualizza il nome del blocco e un elenco delle cassette postali a cui si applica il blocco.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>Blocchi sul posto

Eseguire il comando seguente in Exchange Online PowerShell per identificare il In-Place blocco applicato alla cassetta postale. Usa il GUID per il In-Place blocco che hai identificato nel passaggio 1. Il comando visualizza il nome del blocco e un elenco delle cassette postali a cui si applica il blocco.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Se il GUID dell'In-Place blocco inizia con il prefisso, assicurarsi di includere il prefisso quando si `cld` esegue il comando precedente.

> [!IMPORTANT]
> Mentre continuiamo a investire in modi diversi per conservare il contenuto delle cassette postali, annunciamo il ritiro delle esenzioni In-Place nell'interfaccia di amministrazione di Exchange (EAC). A partire dal 1° luglio 2020 non sarà possibile creare nuove esenzioni In-Place in Exchange Online. Tuttavia, sarà comunque possibile gestire In-Place blocchi nell'interfaccia di amministrazione di Exchange o utilizzando il cmdlet **Set-MailboxSearch** in Exchange Online PowerShell. Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile gestire le In-Place esenzioni. Sarà possibile rimuoverli solo nell'interfaccia di amministrazione di Exchange o utilizzando il cmdlet **Remove-MailboxSearch.** Per ulteriori informazioni sul ritiro delle In-Place, vedere [Ritiro degli strumenti di eDiscovery legacy.](legacy-ediscovery-retirement.md)

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 di conservazione

Eseguire il comando seguente in & PowerShell del Centro sicurezza e conformità per l'identità dei criteri di conservazione di Microsoft 365 (a livello di organizzazione o percorso specifico) applicati alla cassetta postale. Usa il GUID (senza includere il prefisso mbx, skp o grp o il suffisso di azione) identificato nel passaggio 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificazione delle cassette postali in attesa perché è stata applicata un'etichetta di conservazione a una cartella o a un elemento

Ogni volta che un utente applica un'etichetta di conservazione configurata per conservare o conservare il contenuto e quindi eliminare il contenuto in qualsiasi cartella o elemento della cassetta postale, la proprietà della cassetta postale *ComplianceTagHoldApplied* viene impostata su **True.** In questo caso, la cassetta postale viene considerata in attesa, come se fosse stata messa in conservazione per controversia legale o assegnata a un criterio Microsoft 365 conservazione. Quando la *proprietà ComplianceTagHoldApplied* è impostata su **True,** possono verificarsi le operazioni seguenti:

- Se la cassetta postale o l'account utente dell'utente viene eliminato, la cassetta postale diventa una cassetta postale [inattiva.](inactive-mailboxes-in-office-365.md)
- Non è possibile disabilitare la cassetta postale (la cassetta postale principale o la cassetta postale di archiviazione, se abilitata).
- Gli elementi nella cassetta postale possono essere conservati più a lungo del previsto. Ciò è dovuto al fatto che la cassetta postale è in attesa e pertanto nessun elemento viene eliminato definitivamente (eliminato).

Per visualizzare il valore della *proprietà ComplianceTagHoldApplied,* eseguire il comando seguente in Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Per ulteriori informazioni sulle etichette di conservazione, vedere [retention labels](retention.md#retention-labels).

## <a name="managing-mailboxes-on-delay-hold"></a>Gestione delle cassette postali in attesa di ritardo

Dopo la rimozione di qualsiasi tipo di blocco da una cassetta postale, viene applicato un *blocco di* ritardo. Ciò significa che la rimozione effettiva del blocco viene ritardata di 30 giorni per evitare che i dati vengano eliminati definitivamente (eliminati) dalla cassetta postale. In questo modo gli amministratori possono cercare o recuperare gli elementi della cassetta postale che verranno eliminati dopo la rimozione di un blocco. Un blocco di ritardo viene posizionato su una cassetta postale la volta successiva che l'Assistente cartelle gestite elabora la cassetta postale e rileva che un blocco è stato rimosso. In particolare, un blocco di ritardo viene applicato a una cassetta postale quando l'Assistente cartelle gestite imposta una delle seguenti proprietà della cassetta postale su **True:**

- **DelayHoldApplied:** Questa proprietà si applica al contenuto correlato alla posta elettronica (generato da utenti che utilizzano Outlook e Outlook sul Web) archiviato nella cassetta postale di un utente.

- **DelayReleaseHoldApplied:** Questa proprietà si applica al contenuto basato sul cloud (generato da app non Outlook come Microsoft Teams, Microsoft Forms e Microsoft Yammer) archiviato nella cassetta postale di un utente. I dati cloud generati da un'app Microsoft vengono in genere archiviati in una cartella nascosta nella cassetta postale di un utente.

Quando viene effettuato un blocco di ritardo sulla cassetta postale (quando una delle proprietà precedenti è impostata su **True),** la cassetta postale viene ancora considerata in attesa per una durata di conservazione illimitata, come se la cassetta postale fosse in attesa per controversia legale. Dopo 30 giorni, il blocco di ritardo scade e Microsoft 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà DelayHoldApplied o DelayReleaseHoldApplied su **False)** in modo che il blocco venga rimosso. Dopo aver impostato una di queste proprietà su **False,** gli elementi corrispondenti contrassegnati per la rimozione vengono eliminati alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite.

Per visualizzare i valori per le proprietà DelayHoldApplied e DelayReleaseHoldApplied per una cassetta postale, eseguire il comando seguente in Exchange Online PowerShell.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Per rimuovere il blocco di ritardo prima della scadenza, è possibile eseguire uno o entrambi i comandi seguenti in Exchange Online PowerShell, a seconda della proprietà che si desidera modificare:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oppure

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Per utilizzare i parametri *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied,* è necessario disporre del ruolo di blocco legale in Exchange Online per utilizzare i parametri RemoveDelayHoldApplied o RemoveDelayReleaseHoldApplied. 

Per rimuovere il blocco di ritardo su una cassetta postale inattiva, eseguire uno dei comandi seguenti in Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Oppure

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> Il modo migliore per specificare una cassetta postale inattiva nel comando precedente è utilizzare il relativo nome distinto o Exchange VALORE GUID. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata. 

Per ulteriori informazioni sull'utilizzo di questi parametri per la gestione dei blocchi di ritardo, [vedere Set-Mailbox](/powershell/module/exchange/set-mailbox).

Quando si gestisce una cassetta postale in attesa di ritardo, tenere presente quanto segue:

- Se la proprietà DelayHoldApplied o DelayReleaseHoldApplied è impostata su **True** e viene eliminata una cassetta postale (o l'account utente corrispondente), la cassetta postale diventa una cassetta postale inattiva. Ciò è dovuto al fatto che una cassetta postale viene considerata in attesa se una delle due proprietà è impostata su **True** e l'eliminazione di una cassetta postale in attesa comporta una cassetta postale inattiva. Per eliminare una cassetta postale e non renderla inattiva, è necessario impostare entrambe le proprietà su **False.**

- Come indicato in precedenza, una cassetta postale viene considerata in attesa per una durata di conservazione illimitata se la proprietà DelayHoldApplied o DelayReleaseHoldApplied è impostata su **True.** Tuttavia, ciò non significa che tutto *il* contenuto della cassetta postale sia conservato. Dipende dal valore impostato su ogni proprietà. Si supponga ad esempio che entrambe le proprietà siano impostate su **True** perché i blocchi vengono rimossi dalla cassetta postale. Quindi rimuovi solo il blocco di ritardo applicato ai dati non Outlook cloud (usando il *parametro RemoveDelayReleaseHoldApplied).* Alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite, gli elementi non Outlook contrassegnati per la rimozione vengono eliminati. Tutti Outlook elementi contrassegnati per la rimozione non verranno eliminati perché la proprietà DelayHoldApplied è ancora impostata su **True.** Anche il contrario sarebbe vero: se DelayHoldApplied è impostato su **False** e DelayReleaseHoldApplied è impostato su **True,** verranno eliminati solo gli elementi Outlook contrassegnati per la rimozione.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver identificato i blocchi applicati a una cassetta postale, è possibile eseguire attività quali la modifica della durata del blocco, la rimozione temporanea o definitiva del blocco o l'esclusione di una cassetta postale inattiva da un criterio di conservazione Microsoft 365. Per ulteriori informazioni sull'esecuzione di attività correlate alle esenzioni, vedere uno dei seguenti argomenti:

- Eseguire il [comando Set-RetentionCompliancePolicy \<Policy Name> -Identity \<user mailbox> -AddExchangeLocationException](/powershell/module/exchange/set-retentioncompliancepolicy) in PowerShell del Centro sicurezza & conformità per escludere una cassetta postale da un criterio di conservazione Microsoft 365 a livello di organizzazione. Questo comando può essere utilizzato solo per i criteri di conservazione in cui il valore della *proprietà ExchangeLocation* è uguale a `All` .

- [Cambiare la durata del blocco per una cassetta postale inattiva](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md)

- [Eliminare gli elementi nella cartella Elementi recuperabili delle cassette postali basate su cloud con blocchi](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)