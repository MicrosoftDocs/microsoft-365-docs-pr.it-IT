---
title: Eseguire un report di un gruppo di ruoli amministratore in Exchange Online Protection autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a eseguire un rapporto del gruppo di ruoli amministratore in Exchange Online Protection (EOP) autonomo. Questo rapporto registra quando un amministratore aggiunge o rimuove membri dai gruppi di ruoli di amministratore.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 507fbe6fb6c99677cf91b6eb824bf110f1c826f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166628"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Eseguire un report di un gruppo di ruoli amministratore in Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](https://go.microsoft.com/fwlink/?linkid=2148611)

Nelle organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, quando un amministratore aggiunge o rimuove membri dai gruppi di ruoli amministrativi, il servizio registra ogni occorrenza. Per ulteriori informazioni sui gruppi di ruoli in EOP autonomo, vedere [Autorizzazioni in EOP autonomo.](feature-permissions-in-eop.md)

Quando si esegue un rapporto del gruppo di ruoli amministratore nell'interfaccia di amministrazione di Exchange (EAC), le voci vengono visualizzate come risultati della ricerca e includono i gruppi di ruoli interessati, chi ha modificato l'appartenenza al gruppo di ruoli e quando e quali aggiornamenti di appartenenza sono stati effettuati. Utilizzare questo rapporto per monitorare le modifiche apportate alle autorizzazioni amministrative assegnate agli utenti dell'organizzazione.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire l'interfaccia di amministrazione di Exchange, vedere l'interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection. In particolare, è necessario  il ruolo Registri di controllo o Registri di controllo di sola visualizzazione, che vengono assegnati ai gruppi di ruoli Gestione **organizzazione,** Gestione conformità e Amministratore sicurezza per impostazione predefinita.   Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Problemi? Chiedere assistenza nel forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Esecuzione del report del gruppo di ruoli amministratore tramite EAC

Eseguire il rapporto del gruppo di ruoli amministratore per trovare le modifiche ai gruppi di ruoli di gestione in un determinato intervallo di tempo.

1. Nell'interfaccia di amministrazione di Exchange, accedere a Controllo di **gestione** della conformità e quindi scegliere Esegui un report del gruppo \> di ruoli **amministratore.**

2. Nella pagina **Cerca modifiche ai gruppi di ruoli di** amministratore visualizzata, configurare le impostazioni seguenti:

   - **Data di inizio** **e Data di fine:** immettere un intervallo di date. Per impostazione predefinita, il rapporto cerca le modifiche apportate ai gruppi di ruoli amministratore nelle ultime due settimane.

   - **Selezionare i gruppi di ruoli:** per impostazione predefinita, vengono cercati tutti i gruppi di ruoli. Per filtrare i risultati in base a gruppi di ruoli specifici, fare clic **su Seleziona gruppi di ruoli.** Nella finestra di dialogo visualizzata, selezionare un gruppo di ruoli e fare clic **su aggiungi ->**. Ripetere questo passaggio tutte le volte necessarie e quindi fare clic su **OK** al termine.

3. Al termine, fare clic su **Cerca.**

Se utilizzando i criteri specificati vengono trovate delle modifiche, queste verranno visualizzate nel riquadro dei risultati. Fare clic su un gruppo di ruoli nei risultati della ricerca per visualizzare le modifiche nel riquadro dei dettagli.

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Se è stato eseguito correttamente un report dei gruppi di ruoli di amministratore, i gruppi di ruoli modificati entro l'intervallo di date vengono visualizzati nel riquadro dei risultati della ricerca. Se non è presente alcun risultato, non è stata eseguita alcuna modifica entro l'intervallo di date specificato. Se è prevista la presenza di risultati, modificare l'intervallo di date, quindi eseguire di nuovo il report.

## <a name="monitor-changes-to-role-group-membership"></a>Monitorare le modifiche apportate all'appartenenza ai gruppi di ruoli

Quando si aggiungono o si rimuovono i membri di un gruppo di ruoli, nei risultati di ricerca visualizzati nel riquadro dei dettagli viene indicato che l'appartenenza al gruppo di ruoli è stata aggiornata e vengono elencati i membri correnti. I risultati non dichiarano in modo esplicito quale utente è stato aggiunto o rimosso.

Per determinare se un utente è stato aggiunto o rimosso, è necessario confrontare due voci separate del rapporto. Ad esempio, osservare le voci di registro seguenti per il gruppo di ruoli **HelpDesk**:

> 27/01/2018 16.43 <br> Amministratore <br> Membri aggiornati: Administrator;annb,florencef;pilarp <br> 06/02/2018 10:09 <br> Amministratore <br> Membri aggiornati: Administrator;annb;florencef;pilarp;tonip <br> 19/02/2018 14.12 <br> Amministratore <br> Membri aggiornati: Administrator;annb;florencef;tonip

In questo esempio, l'account utente Amministratore ha apportato le modifiche seguenti:

- Il 06/02/2018, l'utente è stato aggiunto.
- Il 19/02/2018, l'utente pilarp è stato rimosso.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Utilizzare PowerShell di Exchange Online autonomo per cercare voci del log di controllo

È possibile utilizzare PowerShell di Exchange Online per cercare le voci del log di controllo che soddisfano i criteri specificati. Per un elenco dei criteri di ricerca, vedere [Search-AdminAuditLog search criteria.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet) Questa procedura utilizza il cmdlet **Search-AdminAuditLog** e visualizza i risultati della ricerca in PowerShell di Exchange Online. È possibile utilizzare questo cmdlet per la restituzione di un set di risultati che supera i limiti definiti nel cmdlet **New-AdminAuditLogSearch** o nei report di controllo di Interfaccia di amministrazione di Exchange.

Per effettuare una ricerca nel log di controllo in base ai criteri specificati, utilizzare la sintassi seguente.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Per impostazione predefinita, il cmdlet **Search-AdminAuditLog** restituisce un massimo di 1.000 voci di registro. Utilizzare il _parametro ResultSize_ per specificare fino a 250.000 voci di registro. In caso contrario, utilizzare `Unlimited` il valore per restituire tutte le voci.

In questo esempio viene eseguita la ricerca di tutte le voci del log di controllo con i seguenti criteri:

- **Data di** inizio : 04/08/2018
- **Data di** fine : 03/10/2018
- **ID utente**: `davids` , `chrisd` , `kima`
- **Cmdlet :** **Set-Mailbox**
- **Parametri**: _ProhibitSendQuota,_ _ProhibitSendReceiveQuota,_ _IssueWarningQuota,_ _MaxSendSize,_ _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In questo esempio vengono cercate le modifiche apportate a una cassetta postale specifica. Questa ricerca è utile per la risoluzione dei problemi o se è necessario fornire informazioni per un'analisi. Vengono utilizzati i seguenti criteri:

- **Data di** inizio : 01/05/2018
- **Data di** fine : 03/10/2018
- **ID oggetto**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Se le ricerche restituiscono molte voci di registro, si consiglia di utilizzare la procedura descritta in **Utilizzare PowerShell** di Exchange Online per cercare le voci del log di controllo e inviare i risultati a un destinatario più avanti in questo articolo. Nella procedura descritta nella sezione citata, viene inviato un file XML come allegato di posta elettronica ai destinatari specificati, consentendo di estrarre più facilmente i dati a cui si è interessati.

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visualizzazione dei dettagli del log di controllo

Il cmdlet **Search-AdminAuditLog** restituisce i campi descritti nel [contenuto del registro di controllo.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Dei due campi restituiti dal cmdlet, due, ovvero **CmdletParameters** e **ModifiedProperties**, contengono ulteriori informazioni non visualizzabili per impostazione predefinita.

Per visualizzare il contenuto dei campi **CmdletParameters** e **ModifiedProperties**, attenersi alla procedura riportata di seguito. In or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log e send results to a recipient** later in this article to create an XML file.

In questa procedura vengono utilizzati i seguenti concetti:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. Scegliere i criteri in base ai quali eseguire la ricerca, eseguire il cmdlet **Search-AdminAuditLog** e memorizzare i risultati in una variabile utilizzando il comando seguente.

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. Ogni voce del log di controllo viene archiviata come elemento matrice nella variabile `$Results` . È possibile selezionare un elemento di matrice specificandone l'indice. Gli indici degli elementi di matrice iniziano da zero (0) per il primo elemento della matrice. Ad esempio, per recuperare il quinto elemento della matrice, il cui indice è 4, utilizzare il comando seguente.

   ```PowerShell
   $Results[4]
   ```

3. Il comando precedente restituisce la voce di registro memorizzata nell'elemento 4 della matrice. Per visualizzare il contenuto nei campi **CmdletParameters** e **ModifiedProperties** per questa voce di registro, utilizzare il comando seguente.

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. Per visualizzare il contenuto dei campi **CmdletParameters** o **ModifiedParameters** in un'altra voce di registro, modificare l'indice degli elementi di matrice.
