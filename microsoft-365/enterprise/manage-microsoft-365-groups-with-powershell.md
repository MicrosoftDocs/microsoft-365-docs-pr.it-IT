---
title: Gestire i gruppi Microsoft 365 con PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: In questo articolo vengono fornite informazioni su come eseguire attività di gestione comuni per i gruppi di Microsoft 365 in PowerShell.
ms.openlocfilehash: a02990b2890d9fdfd523209e1d912aafdaeac091
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547927"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="6f5c4-103">Gestire i gruppi Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f5c4-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="6f5c4-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6f5c4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6f5c4-105">In questo articolo vengono illustrati i passaggi per eseguire attività di gestione comuni per i gruppi di Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="6f5c4-106">Vengono inoltre elencati i cmdlet di PowerShell per i gruppi.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="6f5c4-107">Per informazioni sulla gestione dei siti di SharePoint, vedere [gestire i siti di SharePoint Online tramite PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="6f5c4-108">Collegamento alle linee guida per l'utilizzo dei gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="6f5c4-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="6f5c4-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="6f5c4-110">Quando gli utenti [creano o modificano un gruppo in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), è possibile mostrargli un collegamento alle linee guida per l'utilizzo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="6f5c4-111">Ad esempio, se si necessita di un prefisso o di un suffisso specifico da aggiungere al nome di un gruppo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="6f5c4-112">Utilizzare la PowerShell di Azure Active Directory (Azure AD) per indirizzare gli utenti alle linee guida per l'utilizzo dell'organizzazione per i gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="6f5c4-113">Estrarre i [cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://go.microsoft.com/fwlink/?LinkID=827484) e seguire la procedura descritta in **creare le impostazioni a livello di directory** per definire il collegamento ipertestuale linee guida per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="6f5c4-114">Dopo aver eseguito il cmdlet AAD, il collegamento alle linee guida verrà visualizzato dall'utente quando si crea o si modifica un gruppo in Outlook.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Creare un nuovo gruppo con linee guida di utilizzo collegamento](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Fare clic su linee guida sull'utilizzo di gruppi per visualizzare le linee guida sui gruppi di Office 365](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="6f5c4-117">Consenti agli utenti di inviare messaggi come gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="6f5c4-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="6f5c4-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="6f5c4-119">Se si desidera consentire ai gruppi di Microsoft 365 di "Invia come", utilizzare i cmdlet [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) e [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) per configurarlo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="6f5c4-120">Dopo aver abilitato questa impostazione, gli utenti del gruppo Microsoft 365 possono utilizzare Outlook o Outlook sul Web per inviare e rispondere alla posta elettronica come gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="6f5c4-121">Gli utenti possono accedere al gruppo, creare un nuovo messaggio di posta elettronica e cambiare il campo "Invia come" all'indirizzo di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="6f5c4-122">([È possibile eseguire questa operazione anche nell'interfaccia di amministrazione di Exchange](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="6f5c4-123">Utilizzare lo script seguente, sostituendo *\<GroupAlias\>* con l'alias del gruppo che si desidera aggiornare e *\<UserAlias\>* con l'alias dell'utente a cui si desidera concedere le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="6f5c4-124">[Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) per eseguire questo script.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="6f5c4-125">Dopo l'esecuzione del cmdlet, gli utenti possono accedere a Outlook o Outlook sul Web per l'invio come gruppo, aggiungendo l'indirizzo di posta elettronica del gruppo al campo **da** .</span><span class="sxs-lookup"><span data-stu-id="6f5c4-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-office-groups-in-your-organization"></a><span data-ttu-id="6f5c4-126">Creare classificazioni per i gruppi di Office nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6f5c4-126">Create classifications for Office groups in your organization</span></span>

<span data-ttu-id="6f5c4-127">È possibile creare etichette di riservatezza che possono essere impostate dagli utenti dell'organizzazione durante la creazione di un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="6f5c4-128">Se si desidera classificare i gruppi, è consigliabile utilizzare le etichette di riservatezza anziché la caratteristica classificazione gruppi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="6f5c4-129">Per informazioni sull'utilizzo di etichette di riservatezza, vedere [use Sensitivity labels to protect content in Microsoft teams, microsoft 365 Groups e SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f5c4-130">Se attualmente si utilizzano le etichette di classificazione, non saranno più disponibili per gli utenti che creano gruppi una volta abilitate le etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="6f5c4-131">È comunque possibile utilizzare la caratteristica classificazione gruppi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="6f5c4-132">È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-132">You can create classifications that the users in your organization can set when they create an Office 365 group.</span></span> <span data-ttu-id="6f5c4-133">Ad esempio, è possibile consentire agli utenti di impostare "standard", "segreto" e "Top Secret" sui gruppi creati.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="6f5c4-134">Le classificazioni di gruppo non vengono impostate per impostazione predefinita ed è necessario crearla affinché gli utenti lo configurano.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="6f5c4-135">Utilizzare PowerShell di Azure Active Directory per indirizzare gli utenti alle linee guida per l'utilizzo dell'organizzazione per i gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Office 365 groups.</span></span>

<span data-ttu-id="6f5c4-136">Estrarre i [cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) e seguire la procedura descritta in **create settings at the directory Level** per definire la classificazione per i gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Office 365 groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="6f5c4-137">Per associare una descrizione a ogni classificazione, è possibile utilizzare l'attributo Settings  *ClassificationDescriptions* per definire.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="6f5c4-138">dove la classificazione corrisponde alle stringhe presenti nella classificazione.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="6f5c4-139">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="6f5c4-140">Dopo aver eseguito il cmdlet sopra Azure Active Directory per impostare la classificazione, eseguire il cmdlet [set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) se si desidera impostare la classificazione per un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="6f5c4-141">O creare un nuovo gruppo con una classificazione.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="6f5c4-142">Per altri dettagli sull'uso di PowerShell di Exchange Online vedere [Uso di PowerShell con Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) e [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="6f5c4-143">Dopo aver abilitato queste impostazioni, il proprietario del gruppo sarà in grado di scegliere una classificazione dal menu a discesa in Outlook sul Web e Outlook e salvarla dalla pagina **modifica** gruppo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Scegliere la classificazione di gruppo di Office 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-office-365-groups-from-gal"></a><span data-ttu-id="6f5c4-145">Nascondere i gruppi di Office 365 dall'elenco indirizzi globale</span><span class="sxs-lookup"><span data-stu-id="6f5c4-145">Hide Office 365 Groups from GAL</span></span>
<span data-ttu-id="6f5c4-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="6f5c4-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="6f5c4-147">È possibile specificare se un gruppo di Office 365 viene visualizzato nell'elenco indirizzi globale (GAL) e negli altri elenchi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-147">You can specify whether an Office 365 group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="6f5c4-148">Ad esempio, se si dispone di un gruppo di reparto legale che non si desidera visualizzare nell'elenco degli indirizzi, è possibile impedire che il gruppo venga visualizzato in GAL.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in GAL.</span></span> <span data-ttu-id="6f5c4-149">Eseguire il cmdlet Set-Unified Group per nascondere l'elenco indirizzi di gruppo in questo modo:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-149">Run the Set-Unified Group cmdlet to hide the group from address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-office-365-group"></a><span data-ttu-id="6f5c4-150">Consenti solo agli utenti interni di inviare messaggi al gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-150">Allow only internal users to send message to Office 365 group</span></span>
<span data-ttu-id="6f5c4-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="6f5c4-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="6f5c4-152">Se non si desidera che gli utenti di altre organizzazioni possano inviare messaggi di posta elettronica a un gruppo di Office 365, è possibile modificare le impostazioni per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-152">If you don't want users from other organization to send email to an Office 365 group, you can change the settings for that group.</span></span> <span data-ttu-id="6f5c4-153">Permetterà solo agli utenti interni di inviare un messaggio di posta elettronica al gruppo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="6f5c4-154">Se l'utente esterno tenta di inviare un messaggio al gruppo, verrà rifiutato.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-154">If external user try to send message to that group they will be rejected.</span></span>

<span data-ttu-id="6f5c4-155">Eseguire il cmdlet Set-UnifiedGroup per aggiornare questa impostazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-the-office-365-groups"></a><span data-ttu-id="6f5c4-156">Aggiungere suggerimenti messaggio ai gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-156">Add MailTips to the Office 365 Groups</span></span>
<span data-ttu-id="6f5c4-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="6f5c4-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="6f5c4-158">Ogni volta che un mittente tenta di inviare un messaggio di posta elettronica a un gruppo di Office 365, è possibile mostrargli un avviso messaggio.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-158">Whenever a sender tries to send an email to an Office 365 group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="6f5c4-159">Eseguire il cmdlet Set-Unified Group per aggiungere un avviso messaggio al gruppo:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="6f5c4-160">Insieme a avviso messaggio, è anche possibile impostare MailTipTranslations, che specifica altre lingue per il avviso messaggio.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="6f5c4-161">Si supponga di voler disporre della traduzione spagnola, quindi eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-display-name-of-the-office-365-group"></a><span data-ttu-id="6f5c4-162">Modificare il nome visualizzato del gruppo Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-162">Change Display name of the Office 365 group</span></span>

<span data-ttu-id="6f5c4-163">Nome visualizzato consente di specificare il nome del gruppo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-163">Display name specifies the name of the Office 365 group.</span></span> <span data-ttu-id="6f5c4-164">È possibile visualizzare questo nome nell'interfaccia di amministrazione di Exchange o nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="6f5c4-165">È possibile modificare il nome visualizzato del gruppo o assegnare un nome visualizzato a un gruppo di Office 365 esistente eseguendo il comando set-UnifiedGroup:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-165">You can edit the display name of the group or assign a display name to an existing Office 365 group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-office-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="6f5c4-166">Modificare l'impostazione predefinita dei gruppi di Office 365 per Outlook su pubblico o privato</span><span class="sxs-lookup"><span data-stu-id="6f5c4-166">Change the default setting of Office 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="6f5c4-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="6f5c4-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="6f5c4-168">I gruppi di Office 365 in Outlook vengono creati come privati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-168">Office 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="6f5c4-169">Se l'organizzazione desidera che i gruppi di Office 365 vengano creati come pubblici per impostazione predefinita o di nuovo su privato, utilizzare la sintassi del cmdlet di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-169">If your organization wants Office 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="6f5c4-170">Per impostare su privato:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="6f5c4-171">Per verificare l'impostazione:</span><span class="sxs-lookup"><span data-stu-id="6f5c4-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="6f5c4-172">Per ulteriori informazioni, vedere [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="6f5c4-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="office-365-groups-cmdlets"></a><span data-ttu-id="6f5c4-173">Cmdlet per i gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-173">Office 365 Groups cmdlets</span></span>

<span data-ttu-id="6f5c4-174">I cmdlet seguenti possono essere utilizzati con i gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-174">The following cmdlets can be used with Office 365 Groups.</span></span>

|<span data-ttu-id="6f5c4-175">**Nome cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6f5c4-175">**Cmdlet name**</span></span>|<span data-ttu-id="6f5c4-176">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6f5c4-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6f5c4-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="6f5c4-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="6f5c4-178">Utilizzare questo cmdlet per cercare i gruppi di Office 365 esistenti e per visualizzare le proprietà dell'oggetto Group.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-178">Use this cmdlet to look up existing Office 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="6f5c4-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="6f5c4-180">Aggiornare le proprietà di uno specifico gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-180">Update the properties of a specific Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="6f5c4-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="6f5c4-182">Creare un nuovo gruppo di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-182">Create a new Office 365 group.</span></span> <span data-ttu-id="6f5c4-183">Questo cmdlet fornisce un set di parametri minimo, per impostare i valori per le proprietà estese, utilizzare set-UnifiedGroup dopo aver creato il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-183">This cmdlet provides a minimal set of parameters, for setting values for extended properties use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-184">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="6f5c4-184">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="6f5c4-185">Eliminare un gruppo di Office 365 esistente</span><span class="sxs-lookup"><span data-stu-id="6f5c4-185">Delete an existing Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-186">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="6f5c4-186">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="6f5c4-187">Recuperare le informazioni sull'appartenenza e sul proprietario di un gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-187">Retrieve membership and owner information for an Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-188">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="6f5c4-188">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="6f5c4-189">Aggiungere centinaia o migliaia di utenti o nuovi proprietari a un gruppo di Office 365 esistente</span><span class="sxs-lookup"><span data-stu-id="6f5c4-189">Add hundred or thousands of users, or new owners, to an existing Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-190">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="6f5c4-190">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="6f5c4-191">Rimuovere proprietari e membri da un gruppo di Office 365 esistente</span><span class="sxs-lookup"><span data-stu-id="6f5c4-191">Remove owners and members from an existing Office 365 Group</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-192">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="6f5c4-192">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="6f5c4-193">Utilizzato per visualizzare le informazioni sulla foto utente associata a un account.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-193">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="6f5c4-194">Le foto degli utenti vengono archiviate in Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f5c4-194">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-195">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="6f5c4-195">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="6f5c4-196">Utilizzato per associare una foto utente a un account.</span><span class="sxs-lookup"><span data-stu-id="6f5c4-196">Used to associate a user photo with an account.</span></span> <span data-ttu-id="6f5c4-197">Le foto degli utenti vengono archiviate in Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f5c4-197">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="6f5c4-198">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="6f5c4-198">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="6f5c4-199">Rimuovere la foto per un gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-199">Remove the photo for an Office 365 group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="6f5c4-200">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6f5c4-200">Related topics</span></span>

[<span data-ttu-id="6f5c4-201">Aggiornare le liste di distribuzione a gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-201">Upgrade distribution lists to Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="6f5c4-202">Gestire gli utenti autorizzati a creare gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-202">Manage who can create Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="6f5c4-203">Gestire l'accesso degli utenti guest ai gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="6f5c4-203">Manage guest access to Office 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="6f5c4-204">Modificare l'appartenenza al gruppo statico in Dynamic in</span><span class="sxs-lookup"><span data-stu-id="6f5c4-204">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
