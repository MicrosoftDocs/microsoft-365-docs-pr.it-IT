---
title: Visualizzare il registro di controllo dell'amministratore in EOP autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Gli amministratori possono ottenere informazioni su come visualizzare e cercare il log di controllo dell'amministratore in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208477"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Visualizzare il registro di controllo dell'amministratore in EOP autonomo

Nelle organizzazioni standalone di Exchange Online Protection (EOP) prive di cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell EOP autonomo per cercare e visualizzare le voci nel registro di controllo dell'amministratore.

Il registro di controllo dell'amministratore registra azioni specifiche, basate sui cmdlet di PowerShell di EOP autonomo, eseguite dagli amministratori e dagli utenti a cui sono stati assegnati privilegi amministrativi. Le voci nel registro di controllo dell'amministratore forniscono informazioni su quali cmdlet sono stati eseguiti, quali parametri sono stati utilizzati, chi ha eseguito il cmdlet e quali oggetti sono stati interessati.

> [!NOTE]
> <ul><li>La registrazione di controllo dell'amministratore è abilitata per impostazione predefinita e non è possibile disabilitarla.</li><li>Il registro di controllo dell'amministratore non registra le azioni in base ai cmdlet che iniziano con i verbi **Get**, **Search**o **test**.</li><li>Le voci del registro di controllo vengono conservate per 90 giorni. Quando una voce è più vecchia di 90 giorni, viene eliminata</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per connettersi a PowerShell di EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. In particolare, sono necessari i registri di controllo o il ruolo di controllo di sola visualizzazione, assegnati ai gruppi di ruoli ComplianceManagement, OrganizationManagement (Global Admins) e SecurityAdministrator per impostazione predefinita. Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare il registro di controllo dell'amministratore

1. Nell'interfaccia di amministrazione di Exchange, andare a controllo **della gestione della conformità** \> **Auditing**, quindi scegliere **Esegui il rapporto del log di controllo dell'amministratore**.

2. Nella pagina **Cerca le modifiche apportate ai gruppi di ruoli amministratore** che si apre, scegliere una data di **inizio** e una **Data di fine** (l'intervallo predefinito è le ultime due settimane) e quindi fare clic su **Cerca**. Tutte le modifiche apportate alla configurazione durante il periodo di tempo specificato vengono visualizzate e possono essere ordinate, utilizzando le informazioni seguenti:

   - **Data**: la data e l'ora in cui è stata apportata la modifica della configurazione. La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).

   - **Cmdlet**: il nome del cmdlet utilizzato per modificare la configurazione.

   - **Utente**: il nome dell'account utente dell'utente che ha apportato la modifica alla configurazione.

     Saranno visualizzate fino a 5000 voci su più pagine. Se si desidera limitare i risultati, specificare un intervallo di date più piccolo. Se è stato selezionato un risultato di ricerca individuale, le seguenti informazioni aggiuntive vengono visualizzate nel riquadro dei dettagli:

   - **Oggetto modificato**: l'oggetto che è stato modificato dal cmdlet.

   - **Parametri (Parameter: value)**: parametri del cmdlet utilizzati e qualsiasi valore specificato con il parametro.

3. Se si desidera stampare una voce specifica del registro di controllo, selezionare il pulsante **Stampa** nel riquadro dei dettagli.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Utilizzo di PowerShell EOP autonomo per visualizzare il registro di controllo dell'amministratore

È possibile utilizzare PowerShell EOP autonomo per cercare le voci del registro di controllo che soddisfano i criteri specificati. Utilizzare la sintassi seguente:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Note**:

- È possibile utilizzare solo il parametro _Parameters_ insieme al parametro _cmdlets_ .

- Il parametro _objectids)_ consente di filtrare i risultati in base all'oggetto modificato dal cmdlet. Un valore valido dipende dalla modalità di rappresentazione dell'oggetto nel log di controllo. Ad esempio:

  - Nome
  - Nome distinto canonico (ad esempio, contoso.com/Users/Akia al-Zuhairi)

  È probabile che sia necessario utilizzare altri parametri del filtro su questo cmdlet per limitare i risultati e identificare i tipi di oggetti interessati.

- Il parametro _userids_ consente di filtrare i risultati dall'utente che ha apportato la modifica (che ha eseguito il cmdlet).

- Per i parametri _StartDate_ ed _EndDate_ , se si specifica un valore data/ora senza un fuso orario, il valore è in formato UTC (Coordinated Universal Time). Per specificare un valore data/ora per questo parametro, utilizzare una delle opzioni seguenti:

  - Specificare il valore data/ora in UTC, ad esempio "2016-05-06 14:30:00z".

  - Specificare il valore data/ora come formula che converte la data/ora nel fuso orario locale in ora UTC: ad esempio, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Per altre informazioni, vedere [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313).

- Per impostazione predefinita, il cmdlet restituisce un massimo di 1.000 voci di log. Utilizzare il parametro _ResultSize_ per specificare fino a 250.000 voci di log. In alternativa, utilizzare il valore `Unlimited` per restituire tutte le voci.

In questo esempio viene eseguita la ricerca di tutte le voci del log di controllo con i seguenti criteri:

- **Data di inizio**: 4 agosto 2019
- **Data di fine**: 2019 ottobre 3
- **Cmdlet**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visualizzazione dei dettagli del log di controllo

Il cmdlet **Search-AdminAuditLog** restituisce i campi descritti nella sezione [contenuto dei registri di controllo](#audit-log-contents) più avanti in questo argomento. Dei campi restituiti dal cmdlet, due campi, **CmdletParameters** e **ModifiedProperties**, contengono informazioni aggiuntive che non vengono restituite per impostazione predefinita.

Per visualizzare il contenuto dei campi **CmdletParameters** e **ModifiedProperties**, attenersi alla procedura riportata di seguito.

1. Scegliere i criteri in base ai quali eseguire la ricerca, eseguire il cmdlet **Search-AdminAuditLog** e memorizzare i risultati in una variabile utilizzando il comando seguente.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Ogni voce del registro di controllo viene archiviata come un elemento di matrice nella variabile `$Results` . È possibile selezionare un elemento di matrice specificandone l'indice. Gli indici degli elementi di matrice iniziano da zero (0) per il primo elemento della matrice. Ad esempio, per recuperare il quinto elemento della matrice, il cui indice è 4, utilizzare il comando seguente.

    ```PowerShell
    $Results[4]
    ```

3. Il comando precedente restituisce la voce di registro memorizzata nell'elemento 4 della matrice. Per visualizzare il contenuto nei campi **CmdletParameters** e **ModifiedProperties** per questa voce di registro, utilizzare il comando seguente.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Per visualizzare il contenuto dei campi **CmdletParameters** o **ModifiedParameters** in un'altra voce di registro, modificare l'indice degli elementi di matrice.

## <a name="audit-log-contents"></a>Contenuto dei registri di controllo

Ciascuna voce del registro di controllo contiene le informazioni descritte nella tabella seguente. Il registro di controllo contiene una o più voci.

|||
|---|---|
|**Campo**|**Descrizione**|
|`RunspaceId`|Questo campo viene utilizzato internamente da EOP.|
|`ObjectModified`|Questo campo contiene l'oggetto modificato dal cmdlet specificato nel `CmdletName` campo.|
|`CmdletName`|Questo campo contiene il nome del cmdlet eseguito dall'utente nel `Caller` campo.|
|`CmdletParameters`|Questo campo contiene i parametri specificati quando è stato eseguito il cmdlet nel `CmdletName` campo. Sebbene non sia visibile nell'output predefinito, in questo campo viene memorizzato anche il valore specificato con il parametro (se presente).|
|`ModifiedProperties`|Questo campo contiene le proprietà che sono state modificate nell'oggetto nel `ObjectModified` campo. Sebbene non siano visibili nell'output predefinito, in questo campo sono presenti anche il precedente valore della proprietà e quello nuovo.|
|`Caller`|Questo campo contiene l'account utente dell'utente che ha eseguito il cmdlet nel `CmdletName` campo.|
|`ExternalAccess`|Questo campo viene utilizzato internamente da EOP.|
|`Succeeded`|Questo campo specifica se il cmdlet del campo è stato `CmdletName` eseguito correttamente. Il valore è `True` o `False` .|
|`Error`|Questo campo contiene il messaggio di errore generato se il cmdlet nel `CmdletName` campo non è stato completato correttamente.|
|`RunDate`|Questo campo contiene la data e l'ora in cui `CmdletName` è stato eseguito il cmdlet nel campo. La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).|
|`OriginatingServer`|Questo campo indica il server in cui è stato eseguito il cmdlet specificato nel `CmdletName` campo.|
|`ClientIP`|Questo campo viene utilizzato internamente da EOP.|
|`SessionId`|Questo campo viene utilizzato internamente da EOP.|
|`AppId`|Questo campo viene utilizzato internamente da EOP.|
|`ClientAppId`|Questo campo viene utilizzato internamente da EOP.|
|`Identity`|Questo campo viene utilizzato internamente da EOP.|
|`IsValid`|Questo campo viene utilizzato internamente da EOP.|
|`ObjectState`|Questo campo viene utilizzato internamente da EOP.|
|
