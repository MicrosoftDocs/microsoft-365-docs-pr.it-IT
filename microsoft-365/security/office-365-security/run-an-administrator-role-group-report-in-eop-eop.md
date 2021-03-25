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
description: Gli amministratori possono imparare a eseguire un report del gruppo di ruoli amministratore in Exchange Online Protection (EOP) autonomo. Questo report registra quando un amministratore aggiunge o rimuove membri dai gruppi di ruoli di amministratore.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206592"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="468e5-104">Eseguire un report di un gruppo di ruoli amministratore in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="468e5-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="468e5-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="468e5-105">**Applies to**</span></span>
-  [<span data-ttu-id="468e5-106">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="468e5-106">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="468e5-107">Nelle organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, quando un amministratore aggiunge o rimuove membri dai gruppi di ruoli amministrativi, il servizio registra ogni occorrenza.</span><span class="sxs-lookup"><span data-stu-id="468e5-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="468e5-108">Per ulteriori informazioni sui gruppi di ruoli in EOP autonomo, vedere [Autorizzazioni in EOP autonomo.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="468e5-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="468e5-109">Quando si esegue un report del gruppo di ruoli di amministratore nell'interfaccia di amministrazione di Exchange (EAC), le voci vengono visualizzate come risultati della ricerca e includono i gruppi di ruoli interessati, chi ha modificato l'appartenenza al gruppo di ruoli e quando e quali aggiornamenti di appartenenza sono stati eseguiti.</span><span class="sxs-lookup"><span data-stu-id="468e5-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="468e5-110">Utilizzare questo rapporto per monitorare le modifiche apportate alle autorizzazioni amministrative assegnate agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="468e5-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="468e5-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="468e5-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="468e5-112">Per aprire l'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="468e5-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="468e5-113">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="468e5-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="468e5-114">In particolare, è necessario  **il** ruolo Log di controllo o Log di controllo  di sola visualizzazione, assegnati ai gruppi di ruoli **Gestione** **organizzazione,** Gestione conformità e Amministratore sicurezza per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="468e5-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="468e5-115">Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="468e5-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="468e5-116">Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="468e5-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="468e5-117">Problemi?</span><span class="sxs-lookup"><span data-stu-id="468e5-117">Having problems?</span></span> <span data-ttu-id="468e5-118">Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="468e5-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="468e5-119">Esecuzione del report del gruppo di ruoli amministratore tramite EAC</span><span class="sxs-lookup"><span data-stu-id="468e5-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="468e5-120">Eseguire il report del gruppo di ruoli di amministratore per trovare le modifiche ai gruppi di ruoli di gestione in un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="468e5-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="468e5-121">Nell'interfaccia di amministrazione di Exchange, andare a **Gestione** conformità Controllo e quindi scegliere Esegui un report del gruppo \> di **ruoli amministratore.**</span><span class="sxs-lookup"><span data-stu-id="468e5-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="468e5-122">Nella pagina **Cerca modifiche ai gruppi di ruoli di** amministratore visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="468e5-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="468e5-123">**Data inizio** e **Data fine**: immettere un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="468e5-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="468e5-124">Per impostazione predefinita, il rapporto cerca le modifiche apportate ai gruppi di ruoli amministratore nelle ultime due settimane.</span><span class="sxs-lookup"><span data-stu-id="468e5-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="468e5-125">**Seleziona gruppi di ruoli**: per impostazione predefinita, vengono cercati tutti i gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="468e5-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="468e5-126">Per filtrare i risultati in base a gruppi di ruoli specifici, fare clic **su Seleziona gruppi di ruoli.**</span><span class="sxs-lookup"><span data-stu-id="468e5-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="468e5-127">Nella finestra di dialogo visualizzata selezionare un gruppo di ruoli e fare clic **su aggiungi ->**.</span><span class="sxs-lookup"><span data-stu-id="468e5-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="468e5-128">Ripetere questo passaggio il numero di volte necessario e quindi fare clic su **OK** al termine.</span><span class="sxs-lookup"><span data-stu-id="468e5-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="468e5-129">Al termine, fare clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="468e5-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="468e5-p108">Se utilizzando i criteri specificati vengono trovate delle modifiche, queste verranno visualizzate nel riquadro dei risultati. Fare clic su un gruppo di ruoli nei risultati della ricerca per visualizzare le modifiche nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="468e5-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="468e5-132">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="468e5-132">How do you know this worked?</span></span>

<span data-ttu-id="468e5-p109">Se è stato eseguito correttamente un report dei gruppi di ruoli di amministratore, i gruppi di ruoli modificati entro l'intervallo di date vengono visualizzati nel riquadro dei risultati della ricerca. Se non è presente alcun risultato, non è stata eseguita alcuna modifica entro l'intervallo di date specificato. Se è prevista la presenza di risultati, modificare l'intervallo di date, quindi eseguire di nuovo il report.</span><span class="sxs-lookup"><span data-stu-id="468e5-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="468e5-136">Monitorare le modifiche apportate all'appartenenza ai gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="468e5-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="468e5-p110">Quando si aggiungono o si rimuovono i membri di un gruppo di ruoli, nei risultati di ricerca visualizzati nel riquadro dei dettagli viene indicato che l'appartenenza al gruppo di ruoli è stata aggiornata e vengono elencati i membri correnti. I risultati non dichiarano in modo esplicito quale utente è stato aggiunto o rimosso.</span><span class="sxs-lookup"><span data-stu-id="468e5-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="468e5-p111">Per determinare se un utente è stato aggiunto o rimosso, è necessario confrontare due voci separate del rapporto. Ad esempio, osservare le voci di registro seguenti per il gruppo di ruoli **HelpDesk**:</span><span class="sxs-lookup"><span data-stu-id="468e5-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="468e5-141">27/01/2018 16.43</span><span class="sxs-lookup"><span data-stu-id="468e5-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="468e5-142">Amministratore</span><span class="sxs-lookup"><span data-stu-id="468e5-142">Administrator</span></span> <br> <span data-ttu-id="468e5-143">Membri aggiornati: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="468e5-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="468e5-144">06/02/2018 10:09</span><span class="sxs-lookup"><span data-stu-id="468e5-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="468e5-145">Amministratore</span><span class="sxs-lookup"><span data-stu-id="468e5-145">Administrator</span></span> <br> <span data-ttu-id="468e5-146">Membri aggiornati: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="468e5-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="468e5-147">19/02/2018 14.12</span><span class="sxs-lookup"><span data-stu-id="468e5-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="468e5-148">Amministratore</span><span class="sxs-lookup"><span data-stu-id="468e5-148">Administrator</span></span> <br> <span data-ttu-id="468e5-149">Membri aggiornati: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="468e5-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="468e5-150">In questo esempio, l'account utente Amministratore ha apportato le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="468e5-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="468e5-151">Il 06/02/2018 l'utente è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="468e5-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="468e5-152">Il 19/02/2018 l'utente pilarp è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="468e5-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="468e5-153">Utilizzare PowerShell di Exchange Online autonomo per cercare voci del registro di controllo</span><span class="sxs-lookup"><span data-stu-id="468e5-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="468e5-154">È possibile utilizzare PowerShell di Exchange Online per cercare voci del registro di controllo che soddisfano i criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="468e5-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="468e5-155">Per un elenco dei criteri di ricerca, vedere [Search-AdminAuditLog search criteria](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="468e5-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="468e5-156">Questa procedura utilizza il cmdlet **Search-AdminAuditLog** e visualizza i risultati della ricerca in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="468e5-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="468e5-157">È possibile utilizzare questo cmdlet per la restituzione di un set di risultati che supera i limiti definiti nel cmdlet **New-AdminAuditLogSearch** o nei report di controllo di Interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="468e5-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="468e5-158">Per effettuare una ricerca nel log di controllo in base ai criteri specificati, utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="468e5-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="468e5-159">Per impostazione predefinita, il cmdlet **Search-AdminAuditLog** restituisce un massimo di 1.000 voci di registro.</span><span class="sxs-lookup"><span data-stu-id="468e5-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="468e5-160">Utilizzare il _parametro ResultSize_ per specificare fino a 250.000 voci di registro.</span><span class="sxs-lookup"><span data-stu-id="468e5-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="468e5-161">In caso contrario, utilizzare `Unlimited` il valore per restituire tutte le voci.</span><span class="sxs-lookup"><span data-stu-id="468e5-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="468e5-162">In questo esempio viene eseguita la ricerca di tutte le voci del log di controllo con i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="468e5-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="468e5-163">**Data di** inizio : 04/08/2018</span><span class="sxs-lookup"><span data-stu-id="468e5-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="468e5-164">**Data di** fine : 03/10/2018</span><span class="sxs-lookup"><span data-stu-id="468e5-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="468e5-165">**ID utente**: `davids` , `chrisd` , `kima`</span><span class="sxs-lookup"><span data-stu-id="468e5-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="468e5-166">**Cmdlets**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="468e5-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="468e5-167">**Parametri**: _ProhibitSendQuota,_ _ProhibitSendReceiveQuota,_ _IssueWarningQuota,_ _MaxSendSize,_ _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="468e5-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="468e5-p114">In questo esempio vengono cercate le modifiche apportate a una cassetta postale specifica. Questa ricerca è utile per la risoluzione dei problemi o se è necessario fornire informazioni per un'analisi. Vengono utilizzati i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="468e5-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="468e5-171">**Data di** inizio : 01/05/2018</span><span class="sxs-lookup"><span data-stu-id="468e5-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="468e5-172">**Data di** fine : 03/10/2018</span><span class="sxs-lookup"><span data-stu-id="468e5-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="468e5-173">**ID oggetto**: contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="468e5-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="468e5-174">Se le ricerche restituiscono molte voci di registro, è consigliabile utilizzare la procedura descritta in **Use Exchange Online PowerShell to search for audit log e** send results to a recipient later in this article.</span><span class="sxs-lookup"><span data-stu-id="468e5-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="468e5-175">Nella procedura descritta nella sezione citata, viene inviato un file XML come allegato di posta elettronica ai destinatari specificati, consentendo di estrarre più facilmente i dati a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="468e5-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="468e5-176">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="468e5-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="468e5-177">Visualizzazione dei dettagli del log di controllo</span><span class="sxs-lookup"><span data-stu-id="468e5-177">View details of audit log entries</span></span>

<span data-ttu-id="468e5-178">Il cmdlet **Search-AdminAuditLog** restituisce i campi descritti in [Contenuto del registro di controllo.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)</span><span class="sxs-lookup"><span data-stu-id="468e5-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="468e5-179">Dei due campi restituiti dal cmdlet, due, ovvero **CmdletParameters** e **ModifiedProperties**, contengono ulteriori informazioni non visualizzabili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="468e5-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="468e5-180">Per visualizzare il contenuto dei campi **CmdletParameters** e **ModifiedProperties**, attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="468e5-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="468e5-181">In caso contrario, è possibile utilizzare la procedura descritta in Utilizzare **PowerShell** di Exchange Online per cercare voci del registro di controllo e inviare risultati a un destinatario più avanti in questo articolo per creare un file XML.</span><span class="sxs-lookup"><span data-stu-id="468e5-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="468e5-182">In questa procedura vengono utilizzati i seguenti concetti:</span><span class="sxs-lookup"><span data-stu-id="468e5-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="468e5-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="468e5-183">about_Arrays</span></span>](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="468e5-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="468e5-184">about_Variables</span></span>](/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="468e5-185">Scegliere i criteri in base ai quali eseguire la ricerca, eseguire il cmdlet **Search-AdminAuditLog** e memorizzare i risultati in una variabile utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="468e5-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="468e5-186">Ogni voce del log di controllo viene archiviata come elemento di matrice nella variabile `$Results` .</span><span class="sxs-lookup"><span data-stu-id="468e5-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="468e5-187">È possibile selezionare un elemento di matrice specificandone l'indice.</span><span class="sxs-lookup"><span data-stu-id="468e5-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="468e5-188">Gli indici degli elementi di matrice iniziano da zero (0) per il primo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="468e5-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="468e5-189">Ad esempio, per recuperare il quinto elemento della matrice, il cui indice è 4, utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="468e5-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="468e5-p119">Il comando precedente restituisce la voce di registro memorizzata nell'elemento 4 della matrice. Per visualizzare il contenuto nei campi **CmdletParameters** e **ModifiedProperties** per questa voce di registro, utilizzare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="468e5-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="468e5-192">Per visualizzare il contenuto dei campi **CmdletParameters** o **ModifiedParameters** in un'altra voce di registro, modificare l'indice degli elementi di matrice.</span><span class="sxs-lookup"><span data-stu-id="468e5-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>