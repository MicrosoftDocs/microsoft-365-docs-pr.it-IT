---
title: Visualizzare un log di controllo dell'amministratore in Exchange Online Protection autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Gli amministratori possono imparare a visualizzare ed eseguire ricerche nel log di controllo dell'amministratore in Exchange Online Protection (EOP) autonomo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286478"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Visualizzare un log di controllo dell'amministratore in Exchange Online Protection autonomo

**Si applica a**
- [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell EOP autonomo per cercare e visualizzare le voci nel log di controllo dell'amministratore.

Il log di controllo dell'amministratore registra azioni specifiche, basate su cmdlet di PowerShell EOP autonomi, eseguite da amministratori e utenti a cui sono stati assegnati privilegi amministrativi. Le voci nel log di controllo dell'amministratore forniscono informazioni sul cmdlet eseguito, sui parametri utilizzati, sull'utente che ha eseguito il cmdlet e sugli oggetti interessati.

> [!NOTE]
>
> - La registrazione di controllo dell'amministratore è abilitata per impostazione predefinita e non è possibile disabilitarla.
>
> - Il log di controllo dell'amministratore non registra le azioni basate sui cmdlet che iniziano con i verbi **Get,** **Search** o **Test.**
>
> - Le voci del registro di controllo vengono conservate per 90 giorni. Quando una voce ha più di 90 giorni, viene eliminata

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire l'interfaccia di amministrazione di Exchange, vedere l'interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection. In particolare, è necessario  il ruolo Registri di controllo o Registri di controllo di sola visualizzazione, che vengono assegnati ai gruppi di ruoli Gestione **organizzazione,** Gestione conformità e Amministratore sicurezza per impostazione predefinita.   Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Problemi? Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare il registro di controllo dell'amministratore

1. Nell'interfaccia di amministrazione di Exchange, accedere **a Controllo** di gestione della conformità e quindi scegliere Esegui il report del log di \> controllo **dell'amministratore.**

2. Nella pagina **Cerca** modifiche ai gruppi di ruoli di amministratore visualizzata scegliere una **data** di inizio e una di fine (l'intervallo predefinito è le ultime due settimane), quindi scegliere **Cerca.**  Tutte le modifiche alla configurazione apportate durante il periodo di tempo specificato vengono visualizzate e possono essere ordinate utilizzando le informazioni seguenti:

   - **Data**: data e ora in cui è stata apportata la modifica alla configurazione. La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).

   - **Cmdlet**: nome del cmdlet utilizzato per apportare la modifica alla configurazione.

   - **User**: nome dell'account utente dell'utente che ha apportato la modifica alla configurazione.

     Saranno visualizzate fino a 5000 voci su più pagine. Se si desidera limitare i risultati, specificare un intervallo di date più piccolo. Se è stato selezionato un risultato di ricerca individuale, le seguenti informazioni aggiuntive vengono visualizzate nel riquadro dei dettagli:

   - **Oggetto modificato:** l'oggetto modificato dal cmdlet.

   - **Parametri (Parametro:Valore):** i parametri del cmdlet utilizzati e qualsiasi valore specificato con il parametro.

3. Se si desidera stampare una voce specifica del registro di controllo, selezionare il pulsante **Stampa** nel riquadro dei dettagli.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Utilizzare PowerShell EOP autonomo per visualizzare il log di controllo dell'amministratore

È possibile utilizzare PowerShell EOP autonomo per cercare le voci del log di controllo che soddisfano i criteri specificati. Utilizzare la sintassi seguente:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Note**:

- È possibile utilizzare solo il _parametro Parameters_ insieme al _parametro Cmdlets._

- Il _parametro ObjectIds_ consente di filtrare i risultati in base all'oggetto modificato dal cmdlet. Un valore valido dipende dal modo in cui l'oggetto viene rappresentato nel registro di controllo. Ad esempio:

  - Nome
  - Nome distinto canonico (ad esempio, contoso.com/Users/Akia Al-Zuhairi)

  È probabile che sia necessario utilizzare altri parametri di filtro su questo cmdlet per restringere i risultati e identificare i tipi di oggetti a cui si è interessati.

- Il _parametro UserIds_ consente di filtrare i risultati in base all'utente che ha apportato la modifica (chi ha eseguito il cmdlet).

- Per i _parametri StartDate_ ed _EndDate,_ se si specifica un valore di data/ora senza un fuso orario, il valore è in formato UTC (Coordinated Universal Time). Per specificare un valore data/ora per questo parametro, utilizzare una delle opzioni seguenti:

  - Specificare il valore data/ora in UTC, ad esempio "2016-05-06 14:30:00z".

  - Specificare il valore di data/ora come formula che converte la data/ora nel fuso orario locale in UTC, ad esempio `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Per altre informazioni, vedere [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).

- Il cmdlet restituisce un massimo di 1.000 voci di registro per impostazione predefinita. Utilizzare il _parametro ResultSize_ per specificare fino a 250.000 voci di registro. In caso contrario, utilizzare `Unlimited` il valore per restituire tutte le voci.

In questo esempio viene eseguita la ricerca di tutte le voci del log di controllo con i seguenti criteri:

- **Data di** inizio : 4 agosto 2019
- **Data di** fine : 3 ottobre 2019
- **Cmdlet :** Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visualizzazione dei dettagli del log di controllo

Il cmdlet **Search-AdminAuditLog** restituisce i campi descritti nella sezione Contenuto del [registro](#audit-log-contents) di controllo più avanti in questo articolo. Dei campi restituiti dal cmdlet, due campi, **CmdletParameters** e **ModifiedProperties,** contengono informazioni aggiuntive che non vengono restituite per impostazione predefinita.

Per visualizzare il contenuto dei campi **CmdletParameters** e **ModifiedProperties**, attenersi alla procedura riportata di seguito.

1. Scegliere i criteri in base ai quali eseguire la ricerca, eseguire il cmdlet **Search-AdminAuditLog** e memorizzare i risultati in una variabile utilizzando il comando seguente.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Ogni voce del registro di controllo viene archiviata come elemento matrice nella variabile `$Results` . È possibile selezionare un elemento di matrice specificandone l'indice. Gli indici degli elementi di matrice iniziano da zero (0) per il primo elemento della matrice. Ad esempio, per recuperare il quinto elemento della matrice, il cui indice è 4, utilizzare il comando seguente.

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

****

|Campo|Descrizione|
|---|---|
|`RunspaceId`|Questo campo viene utilizzato internamente da EOP.|
|`ObjectModified`|Questo campo contiene l'oggetto modificato dal cmdlet specificato nel `CmdletName` campo.|
|`CmdletName`|Questo campo contiene il nome del cmdlet eseguito dall'utente nel `Caller` campo.|
|`CmdletParameters`|Questo campo contiene i parametri specificati durante l'esecuzione del cmdlet `CmdletName` nel campo. Sebbene non sia visibile nell'output predefinito, in questo campo viene memorizzato anche il valore specificato con il parametro (se presente).|
|`ModifiedProperties`|Questo campo contiene le proprietà modificate nell'oggetto nel `ObjectModified` campo. Sebbene non siano visibili nell'output predefinito, in questo campo sono presenti anche il precedente valore della proprietà e quello nuovo.|
|`Caller`|Questo campo contiene l'account utente dell'utente che ha eseguito il cmdlet nel `CmdletName` campo.|
|`ExternalAccess`|Questo campo viene utilizzato internamente da EOP.|
|`Succeeded`|Questo campo consente di specificare se il cmdlet nel `CmdletName` campo è stato eseguito correttamente. Il valore è `True` o `False` .|
|`Error`|Questo campo contiene il messaggio di errore generato se il cmdlet nel `CmdletName` campo non è stato completato correttamente.|
|`RunDate`|Questo campo contiene la data e l'ora di esecuzione del cmdlet `CmdletName` nel campo. La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).|
|`OriginatingServer`|Questo campo indica il server in cui è stato eseguito il cmdlet `CmdletName` specificato nel campo.|
|`ClientIP`|Questo campo viene utilizzato internamente da EOP.|
|`SessionId`|Questo campo viene utilizzato internamente da EOP.|
|`AppId`|Questo campo viene utilizzato internamente da EOP.|
|`ClientAppId`|Questo campo viene utilizzato internamente da EOP.|
|`Identity`|Questo campo viene utilizzato internamente da EOP.|
|`IsValid`|Questo campo viene utilizzato internamente da EOP.|
|`ObjectState`|Questo campo viene utilizzato internamente da EOP.|
|
