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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Gli amministratori possono ottenere informazioni su come visualizzare e cercare il log di controllo dell'amministratore in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: 9fe2c742083cde1ca36f6a04cd357a473a10aeac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196544"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="40ad2-103">Visualizzare un log di controllo dell'amministratore in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="40ad2-103">View the admin audit log in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="40ad2-104">Nelle organizzazioni standalone di Exchange Online Protection (EOP) prive di cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell EOP autonomo per cercare e visualizzare le voci nel registro di controllo dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="40ad2-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="40ad2-105">Il registro di controllo dell'amministratore registra azioni specifiche, basate sui cmdlet di PowerShell di EOP autonomo, eseguite dagli amministratori e dagli utenti a cui sono stati assegnati privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="40ad2-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="40ad2-106">Le voci nel registro di controllo dell'amministratore forniscono informazioni su quali cmdlet sono stati eseguiti, quali parametri sono stati utilizzati, chi ha eseguito il cmdlet e quali oggetti sono stati interessati.</span><span class="sxs-lookup"><span data-stu-id="40ad2-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="40ad2-107">La registrazione di controllo dell'amministratore è abilitata per impostazione predefinita e non è possibile disabilitarla.</span><span class="sxs-lookup"><span data-stu-id="40ad2-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="40ad2-108">Il registro di controllo dell'amministratore non registra le azioni in base ai cmdlet che iniziano con i verbi **Get**, **Search**o **test**.</span><span class="sxs-lookup"><span data-stu-id="40ad2-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="40ad2-109">Le voci del registro di controllo vengono conservate per 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="40ad2-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="40ad2-110">Quando una voce è più vecchia di 90 giorni, viene eliminata</span><span class="sxs-lookup"><span data-stu-id="40ad2-110">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="40ad2-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="40ad2-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="40ad2-112">Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="40ad2-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="40ad2-113">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="40ad2-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="40ad2-114">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="40ad2-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="40ad2-115">In particolare, sono necessari i registri di controllo o il ruolo di controllo di sola visualizzazione, assegnati ai gruppi di ruoli ComplianceManagement, OrganizationManagement (Global Admins) e SecurityAdministrator per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="40ad2-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="40ad2-116">Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="40ad2-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="40ad2-117">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="40ad2-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="40ad2-118">Problemi?</span><span class="sxs-lookup"><span data-stu-id="40ad2-118">Having problems?</span></span> <span data-ttu-id="40ad2-119">Chiedere assistenza nel forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="40ad2-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="40ad2-120">Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare il registro di controllo dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="40ad2-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="40ad2-121">Nell'interfaccia di amministrazione di Exchange, andare a controllo **della gestione della conformità** \> **Auditing**, quindi scegliere **Esegui il rapporto del log di controllo dell'amministratore**.</span><span class="sxs-lookup"><span data-stu-id="40ad2-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="40ad2-122">Nella pagina **Cerca le modifiche apportate ai gruppi di ruoli amministratore** che si apre, scegliere una data di **inizio** e una **Data di fine** (l'intervallo predefinito è le ultime due settimane) e quindi fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="40ad2-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="40ad2-123">Tutte le modifiche apportate alla configurazione durante il periodo di tempo specificato vengono visualizzate e possono essere ordinate, utilizzando le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40ad2-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="40ad2-124">**Data**: la data e l'ora in cui è stata apportata la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="40ad2-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="40ad2-125">La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="40ad2-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="40ad2-126">**Cmdlet**: il nome del cmdlet utilizzato per modificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="40ad2-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="40ad2-127">**Utente**: il nome dell'account utente dell'utente che ha apportato la modifica alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="40ad2-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="40ad2-p107">Saranno visualizzate fino a 5000 voci su più pagine. Se si desidera limitare i risultati, specificare un intervallo di date più piccolo. Se è stato selezionato un risultato di ricerca individuale, le seguenti informazioni aggiuntive vengono visualizzate nel riquadro dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="40ad2-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="40ad2-131">**Oggetto modificato**: l'oggetto che è stato modificato dal cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40ad2-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="40ad2-132">**Parametri (Parameter: value)**: parametri del cmdlet utilizzati e qualsiasi valore specificato con il parametro.</span><span class="sxs-lookup"><span data-stu-id="40ad2-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="40ad2-133">Se si desidera stampare una voce specifica del registro di controllo, selezionare il pulsante **Stampa** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="40ad2-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="40ad2-134">Utilizzo di PowerShell EOP autonomo per visualizzare il registro di controllo dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="40ad2-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="40ad2-135">È possibile utilizzare PowerShell EOP autonomo per cercare le voci del registro di controllo che soddisfano i criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="40ad2-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="40ad2-136">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="40ad2-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="40ad2-137">**Note**:</span><span class="sxs-lookup"><span data-stu-id="40ad2-137">**Notes**:</span></span>

- <span data-ttu-id="40ad2-138">È possibile utilizzare solo il parametro _Parameters_ insieme al parametro _cmdlets_ .</span><span class="sxs-lookup"><span data-stu-id="40ad2-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="40ad2-139">Il parametro _objectids)_ consente di filtrare i risultati in base all'oggetto modificato dal cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40ad2-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="40ad2-140">Un valore valido dipende dalla modalità di rappresentazione dell'oggetto nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="40ad2-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40ad2-141">For example:</span></span>

  - <span data-ttu-id="40ad2-142">Nome</span><span class="sxs-lookup"><span data-stu-id="40ad2-142">Name</span></span>
  - <span data-ttu-id="40ad2-143">Nome distinto canonico (ad esempio, contoso.com/Users/Akia al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="40ad2-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="40ad2-144">È probabile che sia necessario utilizzare altri parametri del filtro su questo cmdlet per limitare i risultati e identificare i tipi di oggetti interessati.</span><span class="sxs-lookup"><span data-stu-id="40ad2-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="40ad2-145">Il parametro _userids_ consente di filtrare i risultati dall'utente che ha apportato la modifica (che ha eseguito il cmdlet).</span><span class="sxs-lookup"><span data-stu-id="40ad2-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="40ad2-146">Per i parametri _StartDate_ ed _EndDate_ , se si specifica un valore data/ora senza un fuso orario, il valore è in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="40ad2-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="40ad2-147">Per specificare un valore data/ora per questo parametro, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40ad2-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="40ad2-148">Specificare il valore data/ora in UTC, ad esempio "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="40ad2-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="40ad2-149">Specificare il valore data/ora come formula che converte la data/ora nel fuso orario locale in ora UTC: ad esempio, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="40ad2-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="40ad2-150">Per altre informazioni, vedere [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="40ad2-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="40ad2-151">Per impostazione predefinita, il cmdlet restituisce un massimo di 1.000 voci di log.</span><span class="sxs-lookup"><span data-stu-id="40ad2-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="40ad2-152">Utilizzare il parametro _ResultSize_ per specificare fino a 250.000 voci di log.</span><span class="sxs-lookup"><span data-stu-id="40ad2-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="40ad2-153">In alternativa, utilizzare il valore `Unlimited` per restituire tutte le voci.</span><span class="sxs-lookup"><span data-stu-id="40ad2-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="40ad2-154">In questo esempio viene eseguita la ricerca di tutte le voci del log di controllo con i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="40ad2-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="40ad2-155">**Data di inizio**: 4 agosto 2019</span><span class="sxs-lookup"><span data-stu-id="40ad2-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="40ad2-156">**Data di fine**: 2019 ottobre 3</span><span class="sxs-lookup"><span data-stu-id="40ad2-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="40ad2-157">**Cmdlet**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="40ad2-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="40ad2-158">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="40ad2-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="40ad2-159">Visualizzazione dei dettagli del log di controllo</span><span class="sxs-lookup"><span data-stu-id="40ad2-159">View details of audit log entries</span></span>

<span data-ttu-id="40ad2-160">Il cmdlet **Search-AdminAuditLog** restituisce i campi descritti nella sezione [contenuto dei registri di controllo](#audit-log-contents) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="40ad2-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="40ad2-161">Dei campi restituiti dal cmdlet, due campi, **CmdletParameters** e **ModifiedProperties**, contengono informazioni aggiuntive che non vengono restituite per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="40ad2-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="40ad2-162">Per visualizzare il contenuto dei campi **CmdletParameters** e **ModifiedProperties**, attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="40ad2-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="40ad2-163">Scegliere i criteri in base ai quali eseguire la ricerca, eseguire il cmdlet **Search-AdminAuditLog** e memorizzare i risultati in una variabile utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="40ad2-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="40ad2-164">Ogni voce del registro di controllo viene archiviata come un elemento di matrice nella variabile `$Results` .</span><span class="sxs-lookup"><span data-stu-id="40ad2-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="40ad2-165">È possibile selezionare un elemento di matrice specificandone l'indice.</span><span class="sxs-lookup"><span data-stu-id="40ad2-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="40ad2-166">Gli indici degli elementi di matrice iniziano da zero (0) per il primo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="40ad2-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="40ad2-167">Ad esempio, per recuperare il quinto elemento della matrice, il cui indice è 4, utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="40ad2-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="40ad2-p115">Il comando precedente restituisce la voce di registro memorizzata nell'elemento 4 della matrice. Per visualizzare il contenuto nei campi **CmdletParameters** e **ModifiedProperties** per questa voce di registro, utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="40ad2-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="40ad2-170">Per visualizzare il contenuto dei campi **CmdletParameters** o **ModifiedParameters** in un'altra voce di registro, modificare l'indice degli elementi di matrice.</span><span class="sxs-lookup"><span data-stu-id="40ad2-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="40ad2-171">Contenuto dei registri di controllo</span><span class="sxs-lookup"><span data-stu-id="40ad2-171">Audit log contents</span></span>

<span data-ttu-id="40ad2-172">Ciascuna voce del registro di controllo contiene le informazioni descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="40ad2-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="40ad2-173">Il registro di controllo contiene una o più voci.</span><span class="sxs-lookup"><span data-stu-id="40ad2-173">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="40ad2-174">Campo</span><span class="sxs-lookup"><span data-stu-id="40ad2-174">Field</span></span>|<span data-ttu-id="40ad2-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40ad2-175">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="40ad2-176">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="40ad2-177">Questo campo contiene l'oggetto modificato dal cmdlet specificato nel `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="40ad2-178">Questo campo contiene il nome del cmdlet eseguito dall'utente nel `Caller` campo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="40ad2-179">Questo campo contiene i parametri specificati quando è stato eseguito il cmdlet nel `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="40ad2-180">Sebbene non sia visibile nell'output predefinito, in questo campo viene memorizzato anche il valore specificato con il parametro (se presente).</span><span class="sxs-lookup"><span data-stu-id="40ad2-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="40ad2-181">Questo campo contiene le proprietà che sono state modificate nell'oggetto nel `ObjectModified` campo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="40ad2-182">Sebbene non siano visibili nell'output predefinito, in questo campo sono presenti anche il precedente valore della proprietà e quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="40ad2-183">Questo campo contiene l'account utente dell'utente che ha eseguito il cmdlet nel `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="40ad2-184">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="40ad2-185">Questo campo specifica se il cmdlet del campo è stato `CmdletName` eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="40ad2-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="40ad2-186">Il valore è `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="40ad2-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="40ad2-187">Questo campo contiene il messaggio di errore generato se il cmdlet nel `CmdletName` campo non è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="40ad2-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="40ad2-188">Questo campo contiene la data e l'ora in cui `CmdletName` è stato eseguito il cmdlet nel campo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="40ad2-189">La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="40ad2-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="40ad2-190">Questo campo indica il server in cui è stato eseguito il cmdlet specificato nel `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="40ad2-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="40ad2-191">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="40ad2-192">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="40ad2-193">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="40ad2-194">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="40ad2-195">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="40ad2-196">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="40ad2-197">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="40ad2-197">This field is used internally by EOP.</span></span>|
|
