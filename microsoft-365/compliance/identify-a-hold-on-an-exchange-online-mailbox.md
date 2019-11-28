---
title: Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online
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
description: Informazioni su come identificare i diversi tipi di blocco che è possibile inserire in una cassetta postale di Office 365. Questi tipi di esenzioni includono il blocco per controversia legale, eDiscovery holds e i criteri di conservazione di Office 365. È anche possibile determinare se un utente è stato escluso da un criterio di conservazione a livello di organizzazione
ms.openlocfilehash: 13e7bcec4d6ce7a04b069552b599e742c8777e8a
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634013"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online

In questo articolo viene illustrato come identificare le esenzioni effettuate nelle cassette postali di Exchange online in Office 365.

Office 365 offre diversi modi in cui l'organizzazione può impedire che il contenuto delle cassette postali venga eliminato definitivamente. In questo modo l'organizzazione può conservare il contenuto per soddisfare le normative di conformità o durante le indagini legali e di altro tipo. Di seguito è indicato un elenco delle caratteristiche di conservazione (denominate anche *esenzioni*) in Office 365:

- ** [Blocco per controversia legale](create-a-litigation-hold.md):** Esenzioni applicate alle cassette postali degli utenti in Exchange Online.

- ** [eDiscovery Hold](ediscovery-cases.md#step-4-place-content-locations-on-hold):** Esenzioni associate a un caso di eDiscovery nel centro sicurezza e conformità. le esenzioni di eDiscovery possono essere applicate alle cassette postali degli utenti e alla cassetta postale corrispondente per i gruppi di Office 365 e Microsoft teams.

- ** [Blocco sul posto](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Esenzioni applicate alle cassette postali degli utenti utilizzando lo strumento di archiviazione eDiscovery sul posto & nell'interfaccia di amministrazione di Exchange in Exchange Online.

- ** [Criteri di conservazione di Office 365](retention-policies.md):** Può essere configurato per mantenere (o conservare e quindi eliminare) il contenuto nelle cassette postali degli utenti in Exchange Online e nella cassetta postale corrispondente per i gruppi di Office 365 e Microsoft teams. È inoltre possibile creare un criterio di conservazione per conservare le conversazioni di Skype for business, archiviate nelle cassette postali degli utenti.

  Sono disponibili due tipi di criteri di conservazione di Office 365 che è possibile assegnare alle cassette postali.

    - **Criteri di conservazione delle posizioni specifiche:** Si tratta di criteri che vengono assegnati ai percorsi di contenuto di utenti specifici. È possibile utilizzare il cmdlet **Get-Mailbox** in Exchange Online PowerShell per ottenere informazioni sui criteri di conservazione assegnati a cassette postali specifiche.

    - **Criteri di conservazione a livello dell'organizzazione:** Si tratta di criteri che vengono assegnati a tutti i percorsi di contenuto dell'organizzazione. È possibile utilizzare il cmdlet **Get-OrganizationConfig** in PowerShell di Exchange Online per ottenere informazioni sui criteri di conservazione a livello dell'organizzazione.
  Per ulteriori informazioni, vedere la sezione "applicazione di un criterio di conservazione a un'intera organizzazione o a percorsi specifici" in [Overview of Office 365 Retention Policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

- **[Etichette di conservazione di office 365](labels.md):** se un utente applica un'etichetta di conservazione di Office 365 (una configurata in modo da conservare il contenuto o conservare e quindi eliminare il contenuto) in *qualsiasi* cartella o elemento della propria cassetta postale, l'esenzione viene posizionata sulla cassetta postale come se la cassetta postale è stata inserita nella conservazione per controversia legale o assegnata a un criterio di archiviazione di 365 Office Per ulteriori informazioni, vedere l' [argomento relativo all'identificazione delle cassette postali in attesa perché è stata applicata un'etichetta di conservazione a una cartella o a una](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) sezione di elementi in questo articolo.

Per gestire le cassette postali in blocco, potrebbe essere necessario identificare il tipo di blocco applicato a una cassetta postale, in modo da poter eseguire attività quali la modifica della durata del blocco, la rimozione temporanea o permanente del blocco o l'esclusione di una cassetta postale da un criterio di conservazione di Office 365. In questi casi, il primo passaggio consiste nell'identificare il tipo di blocco applicato alla cassetta postale. Poiché in una singola cassetta postale è possibile applicare più blocchi (e tipi di esenzioni diversi), è necessario identificare tutti gli appigli inseriti in una cassetta postale se si desidera rimuovere o modificare un'esenzione.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Passaggio 1: ottenere il GUID per le esenzioni inserite in una cassetta postale

È possibile eseguire i due cmdlet seguenti in PowerShell di Exchange Online per ottenere il GUID delle esenzioni inserite in una cassetta postale. Dopo aver ottenuto un GUID, è possibile utilizzarlo per identificare il blocco specifico nel passaggio 2. Un blocco per controversia legale non è identificato da un GUID. Le esenzioni per controversia legale sono abilitate o disabilitate per una cassetta postale.

- **Get-Mailbox:** Utilizzare questo cmdlet per determinare se la conservazione per controversia legale è abilitata per una cassetta postale e per ottenere i GUID per eDiscovery, ovvero le esenzioni sul posto, e i criteri di ritenzione di Office 365 specificatamente assegnati a una cassetta postale. L'output di questo cmdlet indicherà anche se una cassetta postale è stata esclusa in modo esplicito da un criterio di conservazione a livello dell'organizzazione.

- **Get-OrganizationConfig:** Utilizzare questo cmdlet per ottenere i GUID per i criteri di conservazione a livello dell'organizzazione.

Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

### <a name="get-mailbox"></a>Get-Mailbox

Eseguire il seguente comando per ottenere informazioni sulle esenzioni e sui criteri di conservazione di Office 365 applicati a una cassetta postale.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Se nella proprietà InPlaceHolds sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni GUID su una riga distinta.

Nella tabella seguente viene descritto come identificare diversi tipi di esenzioni in base ai valori della proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-Mailbox** .


|Tipo di blocco  |Valore di esempio  |Come identificare il blocco  |
|---------|---------|---------|
|Conservazione in caso di dispute     |    `True`     |     Il blocco per controversia legale è abilitato per una ** cassetta postale quando la proprietà `True`LitigationHoldEnabled è impostata su.    |
|eDiscovery Hold     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *Proprietà InPlaceHolds* contiene il GUID di qualsiasi blocco associato a un caso di eDiscovery nel centro sicurezza e conformità. Si può dire che si tratta di un blocco eDiscovery perché il GUID inizia `UniH` con il prefisso (che denota una conservazione unitaria).      |
|Blocco sul posto     |     `c0ba3ce811b6432a8751430937152491` <br/> oppure <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La proprietà *InPlaceHolds* contiene il GUID del blocco sul posto applicato alla cassetta postale. Si può dire che si tratta di un blocco sul posto, perché il GUID non inizia con un prefisso o inizia con il `cld` prefisso.     |
|Criteri di conservazione di Office 365 applicati specificamente alla cassetta postale     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> oppure <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La proprietà InPlaceHolds contiene GUID di tutti i criteri di conservazione delle posizioni specifici applicati alla cassetta postale. È possibile identificare i criteri di conservazione perché il GUID inizia `mbx` con il `skp` prefisso o. Il `skp` prefisso indica che il criterio di conservazione viene applicato alle conversazioni di Skype for business nella cassetta postale dell'utente.    |
|Escluso da un criterio di conservazione di Office 365 a livello di organizzazione     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Se una cassetta postale è esclusa da un criterio di conservazione di Office 365 a livello di organizzazione, il GUID del criterio di conservazione a cui viene esclusa la cassetta postale viene visualizzato nella `-mbx` proprietà InPlaceHolds ed è identificato dal prefisso.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Se la proprietà *InPlaceHolds* è vuota quando si esegue il cmdlet **Get-Mailbox** , è possibile che siano ancora presenti uno o più criteri di conservazione di Office 365 a livello di organizzazione applicati alla cassetta postale. Eseguire il seguente comando in PowerShell di Exchange Online per ottenere un elenco di GUID per i criteri di conservazione di Office 365 a livello di organizzazione.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Se nella proprietà InPlaceHolds sono presenti troppi valori e non tutti sono visualizzati, è possibile eseguire il `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando per visualizzare ogni GUID su una riga distinta.

Nella tabella seguente vengono descritti i diversi tipi di esenzioni a livello di organizzazione e viene descritto come identificare ogni tipo in base ai GUID contenuti nella proprietà *InPlaceHolds* quando si esegue il cmdlet **Get-OrganizationConfig** .


|Tipo di blocco  |Valore di esempio  |Descrizione  |
|---------|---------|---------|
|Criteri di conservazione di Office 365 applicati alle cassette postali di Exchange, alle cartelle pubbliche di Exchange e alle chat di Teams    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   I criteri di conservazione a livello di organizzazione applicati alle cassette postali di Exchange, alle cartelle pubbliche di Exchange e alle chat di 1xN in Microsoft teams `mbx` sono identificati da GUID che iniziano con il prefisso. Note le chat di 1xN vengono archiviate nella cassetta postale dei singoli partecipanti alla chat.      |
|Criteri di conservazione di Office 365 applicati ai messaggi di gruppo di Office 365 e ai gruppi di Team     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    I criteri di conservazione a livello di organizzazione applicati ai gruppi di Office 365 e ai messaggi di canale in Microsoft teams sono identificati da GUID che iniziano con il `grp` prefisso. Note i messaggi del canale vengono archiviati nella cassetta postale di gruppo associata a un team di Microsoft.     |

Per ulteriori informazioni sui criteri di conservazione applicati a Microsoft teams, vedere la sezione "percorso team" [Panoramica dei criteri di conservazione](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Informazioni sul formato del valore InPlaceHolds per i criteri di conservazione

Oltre al prefisso (MBX, SKP o GRP) che identifica un elemento nella proprietà InPlaceHolds come criterio di conservazione di Office 365, il valore contiene anche un suffisso che identifica il tipo di azione di conservazione configurata per il criterio. Ad esempio, il suffisso Action è evidenziato in grassetto negli esempi seguenti:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

Nella tabella seguente vengono definite le tre possibili azioni di conservazione:

|Valore  |Descrizione  |
|---------|---------|
|**1**     | Indica che il criterio di conservazione è configurato per eliminare gli elementi. Il criterio non conserva gli elementi.        |
|**2**    |    Indica che il criterio di conservazione è configurato per contenere gli elementi. Il criterio non elimina gli elementi dopo la scadenza del periodo di conservazione.     |
|**3**     |   Indica che il criterio di conservazione è configurato per contenere gli elementi e quindi eliminarli dopo la scadenza del periodo di conservazione.      |

Per ulteriori informazioni sulle azioni di conservazione, vedere la sezione "conservazione del contenuto per un periodo di tempo specifico" in [Overview of Retention Policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Passaggio 2: utilizzare il GUID per identificare il blocco

Dopo aver ottenuto il GUID di un'esenzione applicato a una cassetta postale, il passaggio successivo consiste nell'utilizzare il GUID per identificare il blocco. Nelle sezioni seguenti viene illustrato come identificare il nome del blocco (e altre informazioni) utilizzando il GUID di blocco.

### <a name="ediscovery-holds"></a>eDiscovery contiene

Eseguire i seguenti comandi in PowerShell per il Centro sicurezza & Compliance per identificare un blocco di eDiscovery applicato alla cassetta postale. Utilizzare il GUID (escluso il prefisso UniH) per il blocco eDiscovery identificato nel passaggio 1. Il primo comando crea una variabile che contiene informazioni sul blocco. Questa variabile viene utilizzata negli altri comandi. Nel secondo comando viene visualizzato il nome del caso di eDiscovery a cui è associato il blocco. Il terzo comando Visualizza il nome del blocco e un elenco delle cassette postali a cui è applicato il blocco.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

Per connettersi a PowerShell per Centro sicurezza & Compliance, vedere [Connect to security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="in-place-holds"></a>Blocchi sul posto

Eseguire il seguente comando in PowerShell di Exchange Online per identificare il blocco sul posto applicato alla cassetta postale. Utilizzare il GUID per il blocco sul posto identificato nel passaggio 1. Il comando Visualizza il nome del blocco e un elenco delle cassette postali a cui è applicato il blocco.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Se il GUID per il blocco sul posto inizia con il `cld` prefisso, assicurarsi di includere il prefisso quando si esegue il comando precedente.

### <a name="office-365-retention-policies"></a>Criteri di conservazione di Office 365

Eseguire il seguente comando in PowerShell per la sicurezza & Compliance Center per identificare i criteri di conservazione di Office 365 (a livello di organizzazione o di posizione specifica) applicati alla cassetta postale. Utilizzare il GUID (che non include il prefisso MBX, SKP o GRP o il suffisso di azione) identificato nel passaggio 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificazione delle cassette postali in attesa perché è stata applicata un'etichetta di conservazione a una cartella o un elemento

Ogni volta che un utente applica un'etichetta di conservazione configurata per mantenere il contenuto o mantenere e quindi eliminare il contenuto in una cartella o un elemento della propria cassetta postale, la proprietà della cassetta postale *ComplianceTagHoldApplied* è impostata su **true**. In questo caso, la cassetta postale viene considerata attiva, come se fosse stata messa in blocco per controversia legale o assegnata a un criterio di conservazione di Office 365. Quando la proprietà *ComplianceTagHoldApplied* è impostata su **true**, è possibile che si verifichino le seguenti operazioni:

- Se la cassetta postale o l'account utente di Office 365 dell'utente viene eliminato, la cassetta postale diventa una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md).
- Non è possibile disabilitare la cassetta postale, ovvero la cassetta postale principale o la cassetta postale di archiviazione, se è abilitata.
- Gli elementi della cassetta postale possono essere mantenuti più a lungo del previsto. Ciò è dovuto al fatto che la cassetta postale è in attesa e pertanto nessun elemento viene eliminato definitivamente (eliminato).

Per visualizzare il valore della proprietà *ComplianceTagHoldApplied* , eseguire il comando seguente in PowerShell di Exchange Online:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Per ulteriori informazioni sulle etichette di conservazione, vedere [Overview of Office 365 retention labels](labels.md).

## <a name="managing-mailboxes-on-delay-hold"></a>Gestione delle cassette postali in attesa del ritardo

Dopo la rimozione di qualsiasi tipo di blocco da una cassetta postale, viene applicato un *blocco di ritardo* . Questo significa che la rimozione effettiva del blocco viene posticipata di 30 giorni per impedire che i dati vengano eliminati definitivamente (eliminati) dalla cassetta postale. In questo modo gli amministratori avranno la possibilità di cercare o recuperare gli elementi della cassetta postale che verranno eliminati dopo la rimozione di un'esenzione. Un blocco di ritardo viene inserito in una cassetta postale alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite e viene rilevato che è stata rimossa un'esenzione. In particolare, un blocco di ritardo viene applicato a una cassetta postale quando l'Assistente cartelle gestite imposta una delle seguenti proprietà della cassetta postale su **true**:

- **DelayHoldApplied:** Questa proprietà si applica al contenuto relativo alla posta elettronica (generato da utenti che utilizzano Outlook e Outlook sul Web) archiviato nella cassetta postale di un utente.

- **DelayReleaseHoldApplied:** Questa proprietà si applica ai contenuti basati sul cloud (generati da app non Outlook, ad esempio Microsoft teams, Microsoft Forms e Microsoft Yammer) archiviati nella cassetta postale di un utente. I dati del cloud generati da un'app Microsoft vengono in genere archiviati in una cartella nascosta della cassetta postale di un utente.
 
 Quando una conservazione di ritardo viene posizionata sulla cassetta postale (quando una delle proprietà precedenti è impostata su **true**), la cassetta postale è ancora considerata in attesa per una durata di conservazione illimitata, come se la cassetta postale fosse in conservazione per controversia legale. Dopo 30 giorni, la sospensione del ritardo scade e Office 365 tenterà automaticamente di rimuovere il blocco di ritardo (impostando la proprietà DelayHoldApplied o DelayReleaseHoldApplied su **false**) in modo che il blocco venga rimosso. Dopo che entrambe le proprietà sono state impostate su **false**, gli elementi corrispondenti contrassegnati per la rimozione vengono eliminati alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite.

Per visualizzare i valori per le proprietà DelayHoldApplied e DelayReleaseHoldApplied di una cassetta postale, eseguire il comando seguente in PowerShell di Exchange Online.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Per rimuovere il ritardo di attesa prima della scadenza, è possibile eseguire uno o entrambi i comandi seguenti in PowerShell di Exchange Online, a seconda della proprietà che si desidera modificare: 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Oppure
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Per utilizzare i parametri *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied* , è necessario essere assegnati al ruolo di blocco legale in Exchange Online. 

Per rimuovere il blocco di ritardo su una cassetta postale inattiva, eseguire uno dei comandi seguenti in PowerShell di Exchange Online:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Oppure

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> Il modo migliore per specificare una cassetta postale inattiva nel comando precedente consiste nell'utilizzare il nome distinto o il valore GUID di Exchange. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata. 

Per ulteriori informazioni sull'utilizzo di questi parametri per la gestione delle esenzioni di ritardo, vedere [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).

Tenere presenti le considerazioni seguenti quando si gestisce una cassetta postale in attesa di ritardo:

- Se la proprietà DelayHoldApplied o DelayReleaseHoldApplied è impostata su **true** e una cassetta postale (o l'account utente di Office 365 corrispondente) è stata eliminata, la cassetta postale diventa una cassetta postale inattiva. Questo perché una cassetta postale viene considerata attiva se la proprietà è impostata su **true**e l'eliminazione di una cassetta postale in attesa risulta in una cassetta postale inattiva. Per eliminare una cassetta postale e non renderla una cassetta postale inattiva, è necessario impostare entrambe le proprietà su **false**.

- Come indicato in precedenza, una cassetta postale viene considerata attiva per un periodo di attesa illimitato se la proprietà DelayHoldApplied o DelayReleaseHoldApplied è impostata su **true**. Tuttavia, ciò non significa che *tutto* il contenuto della cassetta postale sia conservato. Dipende dal valore impostato su ogni proprietà. Si supponga, ad esempio, che entrambe le proprietà siano impostate su **true** perché le esenzioni vengono rimosse dalla cassetta postale. Si rimuove quindi solo il blocco di ritardo applicato ai dati del cloud non Outlook (utilizzando il parametro *RemoveDelayReleaseHoldApplied* ). La volta successiva che l'Assistente cartelle gestite elabora la cassetta postale, gli elementi non di Outlook contrassegnati per la rimozione vengono eliminati. Tutti gli elementi di Outlook contrassegnati per la rimozione non verranno eliminati perché la proprietà DelayHoldApplied è ancora impostata su **true**. L'opposto sarebbe anche vero: se DelayHoldApplied è impostato su **false** e DelayReleaseHoldApplied è impostato su **true**, verranno eliminati solo gli elementi di Outlook contrassegnati per la rimozione.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver identificato le esenzioni applicate a una cassetta postale, è possibile eseguire attività quali la modifica della durata del blocco, la rimozione temporanea o permanente del blocco o l'esclusione di una cassetta postale inattiva da un criterio di conservazione di Office 365. Per ulteriori informazioni sull'esecuzione di attività correlate alle esenzioni, vedere uno dei seguenti argomenti:

- Eseguire il comando [>cassetta postale dell' \<utente set-RetentionCompliancePolicy-AddExchangeLocationException](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) in sicurezza & Compliance Center PowerShell per escludere una cassetta postale da un criterio di conservazione di Office 365 a livello di organizzazione. Questo comando può essere utilizzato solo per i criteri di conservazione in cui il ** valore della proprietà ExchangeLocation `All`è uguale a.

- Eseguire il [GUID di blocco set- \<Mailbox-ExcludeFromOrgHolds senza prefisso o suffisso>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) comando in PowerShell di Exchange Online per escludere una cassetta postale inattiva da un criterio di conservazione di Office 365 a livello di organizzazione.

- [Modificare la durata del blocco per una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md)

- [Eliminare gli elementi nella cartella Elementi recuperabili delle cassette postali basate su cloud con blocchi](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
