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
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908127"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="07947-103">Visualizzare un log di controllo dell'amministratore in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="07947-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="07947-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="07947-104">**Applies to**</span></span>
- [<span data-ttu-id="07947-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="07947-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="07947-106">Nelle organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell EOP autonomo per cercare e visualizzare le voci nel registro di controllo dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="07947-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="07947-107">Il log di controllo dell'amministratore registra azioni specifiche, basate sui cmdlet di PowerShell EOP autonomi, eseguite da amministratori e utenti a cui sono stati assegnati privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="07947-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="07947-108">Le voci nel log di controllo dell'amministratore forniscono informazioni sul cmdlet eseguito, sui parametri utilizzati, sull'utente che ha eseguito il cmdlet e sugli oggetti interessati.</span><span class="sxs-lookup"><span data-stu-id="07947-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="07947-109">La registrazione di controllo dell'amministratore è abilitata per impostazione predefinita e non è possibile disabilitarla.</span><span class="sxs-lookup"><span data-stu-id="07947-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="07947-110">Il log di controllo dell'amministratore non registra le azioni in base ai cmdlet che iniziano con i verbi **Get,** **Search** o **Test.**</span><span class="sxs-lookup"><span data-stu-id="07947-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="07947-111">Le voci del registro di controllo vengono conservate per 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="07947-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="07947-112">Quando una voce è precedente a 90 giorni, viene eliminata</span><span class="sxs-lookup"><span data-stu-id="07947-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="07947-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="07947-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="07947-114">Per aprire l'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="07947-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="07947-115">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="07947-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="07947-116">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="07947-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="07947-117">In particolare, è necessario  **il** ruolo Log di controllo o Log di controllo  di sola visualizzazione, assegnati ai gruppi di ruoli **Gestione** **organizzazione,** Gestione conformità e Amministratore sicurezza per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="07947-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="07947-118">Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="07947-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="07947-119">Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="07947-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="07947-120">Problemi?</span><span class="sxs-lookup"><span data-stu-id="07947-120">Having problems?</span></span> <span data-ttu-id="07947-121">Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="07947-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="07947-122">Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare il log di controllo dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="07947-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="07947-123">Nell'interfaccia di amministrazione di Exchange, andare a **Gestione conformità** \> **Controllo** e quindi scegliere **Esegui il report del log di controllo dell'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="07947-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="07947-124">Nella pagina Cerca modifiche **ai** gruppi di ruoli di amministratore visualizzata scegliere una **data** di inizio e una data di fine (l'intervallo predefinito è le ultime due settimane), quindi scegliere **Cerca**. </span><span class="sxs-lookup"><span data-stu-id="07947-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="07947-125">Tutte le modifiche alla configurazione apportate durante il periodo di tempo specificato vengono visualizzate e possono essere ordinate utilizzando le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07947-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="07947-126">**Date**: data e ora in cui è stata apportata la modifica alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="07947-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="07947-127">La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="07947-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="07947-128">**Cmdlet**: nome del cmdlet utilizzato per apportare la modifica alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="07947-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="07947-129">**User**: nome dell'account utente dell'utente che ha apportato la modifica alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="07947-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="07947-p107">Saranno visualizzate fino a 5000 voci su più pagine. Se si desidera limitare i risultati, specificare un intervallo di date più piccolo. Se è stato selezionato un risultato di ricerca individuale, le seguenti informazioni aggiuntive vengono visualizzate nel riquadro dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="07947-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="07947-133">**Oggetto modificato**: Oggetto modificato dal cmdlet.</span><span class="sxs-lookup"><span data-stu-id="07947-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="07947-134">**Parameters (Parameter:Value):** parametri del cmdlet utilizzati e qualsiasi valore specificato con il parametro.</span><span class="sxs-lookup"><span data-stu-id="07947-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="07947-135">Se si desidera stampare una voce specifica del registro di controllo, selezionare il pulsante **Stampa** nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="07947-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="07947-136">Usare PowerShell EOP autonomo per visualizzare il log di controllo dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="07947-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="07947-137">È possibile utilizzare PowerShell EOP autonomo per cercare voci del log di controllo che soddisfano i criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="07947-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="07947-138">Usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="07947-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="07947-139">**Note**:</span><span class="sxs-lookup"><span data-stu-id="07947-139">**Notes**:</span></span>

- <span data-ttu-id="07947-140">È possibile utilizzare solo il _parametro Parameters_ insieme al _parametro Cmdlets._</span><span class="sxs-lookup"><span data-stu-id="07947-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="07947-141">Il _parametro ObjectIds_ consente di filtrare i risultati in base all'oggetto modificato dal cmdlet.</span><span class="sxs-lookup"><span data-stu-id="07947-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="07947-142">Un valore valido dipende dal modo in cui l'oggetto viene rappresentato nel log di controllo.</span><span class="sxs-lookup"><span data-stu-id="07947-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="07947-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="07947-143">For example:</span></span>

  - <span data-ttu-id="07947-144">Nome</span><span class="sxs-lookup"><span data-stu-id="07947-144">Name</span></span>
  - <span data-ttu-id="07947-145">Nome distinto canonico (ad esempio, contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="07947-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="07947-146">È probabile che sia necessario utilizzare altri parametri di filtro su questo cmdlet per limitare i risultati e identificare i tipi di oggetti a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="07947-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="07947-147">Il _parametro UserIds_ consente di filtrare i risultati in base all'utente che ha apportato la modifica (che ha eseguito il cmdlet).</span><span class="sxs-lookup"><span data-stu-id="07947-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="07947-148">Per i _parametri StartDate_ e _EndDate,_ se si specifica un valore di data/ora senza un fuso orario, il valore è espresso nel formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="07947-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="07947-149">Per specificare un valore data/ora per questo parametro, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07947-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="07947-150">Specificare il valore data/ora in UTC, ad esempio "2016-05-06 14:30:00z".</span><span class="sxs-lookup"><span data-stu-id="07947-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="07947-151">Specificare il valore di data/ora come formula che converte la data/ora nel fuso orario locale in UTC, ad esempio `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="07947-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="07947-152">Per altre informazioni, vedere [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="07947-152">For more information, see [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="07947-153">Il cmdlet restituisce un massimo di 1.000 voci di registro per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="07947-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="07947-154">Utilizzare il _parametro ResultSize_ per specificare fino a 250.000 voci di registro.</span><span class="sxs-lookup"><span data-stu-id="07947-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="07947-155">In caso contrario, utilizzare `Unlimited` il valore per restituire tutte le voci.</span><span class="sxs-lookup"><span data-stu-id="07947-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="07947-156">In questo esempio viene eseguita la ricerca di tutte le voci del log di controllo con i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="07947-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="07947-157">**Data di** inizio : 4 agosto 2019</span><span class="sxs-lookup"><span data-stu-id="07947-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="07947-158">**Data di** fine : 3 ottobre 2019</span><span class="sxs-lookup"><span data-stu-id="07947-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="07947-159">**Cmdlet :** Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="07947-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="07947-160">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="07947-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="07947-161">Visualizzazione dei dettagli del log di controllo</span><span class="sxs-lookup"><span data-stu-id="07947-161">View details of audit log entries</span></span>

<span data-ttu-id="07947-162">Il cmdlet **Search-AdminAuditLog** restituisce i campi descritti nella sezione [Contenuto del registro](#audit-log-contents) di controllo più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="07947-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="07947-163">Tra i campi restituiti dal cmdlet, due campi, **CmdletParameters** e **ModifiedProperties,** contengono informazioni aggiuntive che non vengono restituite per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="07947-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="07947-164">Per visualizzare il contenuto dei campi **CmdletParameters** e **ModifiedProperties**, attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="07947-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="07947-165">Scegliere i criteri in base ai quali eseguire la ricerca, eseguire il cmdlet **Search-AdminAuditLog** e memorizzare i risultati in una variabile utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="07947-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="07947-166">Ogni voce del log di controllo viene archiviata come elemento di matrice nella variabile `$Results` .</span><span class="sxs-lookup"><span data-stu-id="07947-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="07947-167">È possibile selezionare un elemento di matrice specificandone l'indice.</span><span class="sxs-lookup"><span data-stu-id="07947-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="07947-168">Gli indici degli elementi di matrice iniziano da zero (0) per il primo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="07947-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="07947-169">Ad esempio, per recuperare il quinto elemento della matrice, il cui indice è 4, utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="07947-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="07947-p115">Il comando precedente restituisce la voce di registro memorizzata nell'elemento 4 della matrice. Per visualizzare il contenuto nei campi **CmdletParameters** e **ModifiedProperties** per questa voce di registro, utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="07947-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="07947-172">Per visualizzare il contenuto dei campi **CmdletParameters** o **ModifiedParameters** in un'altra voce di registro, modificare l'indice degli elementi di matrice.</span><span class="sxs-lookup"><span data-stu-id="07947-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="07947-173">Contenuto dei registri di controllo</span><span class="sxs-lookup"><span data-stu-id="07947-173">Audit log contents</span></span>

<span data-ttu-id="07947-174">Ciascuna voce del registro di controllo contiene le informazioni descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="07947-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="07947-175">Il registro di controllo contiene una o più voci.</span><span class="sxs-lookup"><span data-stu-id="07947-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="07947-176">Campo</span><span class="sxs-lookup"><span data-stu-id="07947-176">Field</span></span>|<span data-ttu-id="07947-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07947-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="07947-178">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="07947-179">Questo campo contiene l'oggetto modificato dal cmdlet specificato nel `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="07947-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="07947-180">Questo campo contiene il nome del cmdlet eseguito dall'utente nel `Caller` campo.</span><span class="sxs-lookup"><span data-stu-id="07947-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="07947-181">Questo campo contiene i parametri specificati durante l'esecuzione del cmdlet `CmdletName` nel campo.</span><span class="sxs-lookup"><span data-stu-id="07947-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="07947-182">Sebbene non sia visibile nell'output predefinito, in questo campo viene memorizzato anche il valore specificato con il parametro (se presente).</span><span class="sxs-lookup"><span data-stu-id="07947-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="07947-183">Questo campo contiene le proprietà modificate nell'oggetto nel `ObjectModified` campo.</span><span class="sxs-lookup"><span data-stu-id="07947-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="07947-184">Sebbene non siano visibili nell'output predefinito, in questo campo sono presenti anche il precedente valore della proprietà e quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="07947-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="07947-185">Questo campo contiene l'account utente dell'utente che ha eseguito il cmdlet nel `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="07947-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="07947-186">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="07947-187">Questo campo specifica se il cmdlet nel `CmdletName` campo è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="07947-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="07947-188">Il valore è `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="07947-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="07947-189">Questo campo contiene il messaggio di errore generato se il cmdlet nel `CmdletName` campo non è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="07947-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="07947-190">Questo campo contiene la data e l'ora di esecuzione del cmdlet `CmdletName` nel campo.</span><span class="sxs-lookup"><span data-stu-id="07947-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="07947-191">La data e l'ora vengono memorizzati in formato UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="07947-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="07947-192">Questo campo indica il server in cui è stato eseguito il cmdlet `CmdletName` specificato nel campo.</span><span class="sxs-lookup"><span data-stu-id="07947-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="07947-193">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="07947-194">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="07947-195">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="07947-196">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="07947-197">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="07947-198">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="07947-199">Questo campo viene utilizzato internamente da EOP.</span><span class="sxs-lookup"><span data-stu-id="07947-199">This field is used internally by EOP.</span></span>|
|