---
title: Gestire Microsoft 365 gruppi con PowerShell
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
description: In questo articolo viene illustrato come eseguire attività di gestione comuni per Microsoft 365 gruppi in PowerShell.In this article, learn how to do common management tasks for Microsoft 365 groups in PowerShell.
ms.openlocfilehash: 22bf4d1f3187746483d8d904378e675562a62142
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730559"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Gestire Microsoft 365 gruppi con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

In questo articolo vengono descritti i passaggi per eseguire attività di gestione comuni per i gruppi in Microsoft PowerShell. Vengono inoltre elencati i cmdlet di PowerShell per i gruppi. Per info sulla gestione dei SharePoint, vedi [Gestire i siti SharePoint Online tramite PowerShell.](/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Collegamento alle linee guida per l'utilizzo Microsoft 365 gruppi di lavoro
<a name="BK_LinkToGuideLines"> </a>

Quando gli [utenti creano o modificano un gruppo in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), è possibile visualizzare un collegamento alle linee guida di utilizzo dell'organizzazione. Ad esempio, se è necessario aggiungere un prefisso o un suffisso specifico a un nome di gruppo.

Usare PowerShell Azure Active Directory (Azure AD) per puntare gli utenti alle linee guida di utilizzo dell'organizzazione per Microsoft 365 gruppi. Consultare i [Azure Active Directory per](/azure/active-directory/enterprise-users/groups-settings-cmdlets) la configurazione delle impostazioni di gruppo e seguire i passaggi descritti in Creare impostazioni a livello **di directory** per definire il collegamento ipertestuale alla linea guida per l'utilizzo. Dopo aver eseguito il cmdlet AAD, gli utenti visualizzano il collegamento alle linee guida quando creano o modificano un gruppo in Outlook.

![Creare un nuovo gruppo con il collegamento linee guida per l'uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Fai clic su Linee guida per l'uso dei gruppi per visualizzare le linee guida per Office 365 gruppi di lavoro](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Consenti agli utenti di inviare come Microsoft 365 gruppo
<a name="BK_LinkToGuideLines"> </a>

Se si desidera abilitare i gruppi di Microsoft 365 a "Invia come", utilizzare i cmdlet [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) e [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) per configurarlo. Dopo aver abilitato questa impostazione, gli utenti Microsoft 365 gruppo possono usare Outlook o Outlook sul Web per inviare e rispondere alla posta elettronica come Microsoft 365 gruppo. Gli utenti possono passare al gruppo, creare un nuovo messaggio di posta elettronica e modificare il campo "Invia come" nell'indirizzo di posta elettronica del gruppo.

È[anche possibile eseguire questa operazione nell'Exchange di amministrazione.](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

Utilizzare lo script seguente, sostituendo con l'alias del gruppo che si desidera aggiornare e con l'alias dell'utente a cui si desidera *\<GroupAlias\>* *\<UserAlias\>* concedere le autorizzazioni. [Connessione per Exchange Online PowerShell per](/powershell/exchange/connect-to-exchange-online-powershell) eseguire questo script.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Dopo l'esecuzione del cmdlet, gli utenti possono accedere a Outlook o Outlook sul Web da inviare come gruppo, aggiungendo l'indirizzo di posta elettronica del gruppo al **campo** Da.

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Creare classificazioni per Microsoft 365 gruppi nell'organizzazione

È possibile creare etichette di riservatezza che gli utenti dell'organizzazione possono impostare quando creano un Microsoft 365 gruppo. Se si desidera classificare i gruppi, è consigliabile usare le etichette di riservatezza anziché la funzionalità di classificazione dei gruppi precedente. Per informazioni sull'utilizzo delle etichette di riservatezza, vedere [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).

> [!IMPORTANT]
> Se attualmente si utilizzano etichette di classificazione, non saranno più disponibili per gli utenti che creano gruppi dopo aver abilitato le etichette di riservatezza.

È comunque possibile utilizzare la funzionalità di classificazione dei gruppi precedente. È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un Microsoft 365 gruppo. Ad esempio, è possibile consentire agli utenti di impostare "Standard", "Secret" e "Top Secret" nei gruppi che creano. Le classificazioni di gruppo non sono impostate per impostazione predefinita ed è necessario crearla per consentire agli utenti di impostarla. Usare Azure Active Directory PowerShell per puntare gli utenti alle linee guida di utilizzo dell'organizzazione per Microsoft 365 gruppi.

Consultare i [Azure Active Directory per](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) la configurazione delle impostazioni di gruppo e seguire i passaggi descritti in Creare impostazioni a livello **di directory** per definire la classificazione per Microsoft 365 gruppi.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Per associare una descrizione a ogni classificazione, è possibile utilizzare l'attributo delle impostazioni  *ClassificationDescriptions* per definire.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

dove Classification corrisponde alle stringhe in ClassificationList.

Esempio:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Dopo aver eseguito il cmdlet Azure Active Directory per impostare la classificazione, eseguire il cmdlet [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) se si desidera impostare la classificazione per un gruppo specifico.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Oppure crea un nuovo gruppo con una classificazione.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Per altri dettagli sull'uso di PowerShell di Exchange Online vedere [Uso di PowerShell con Exchange Online](/powershell/exchange/exchange-online-powershell) e [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Dopo aver abilitato queste impostazioni, il proprietario del gruppo potrà scegliere una classificazione dal menu a discesa in Outlook  sul Web e Outlook e salvarla dalla pagina Modifica gruppo.

![Scegliere Microsoft 365 di gruppo](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Nascondere Microsoft 365 gruppi dall'elenco indirizzi globale.
<a name="BKMK_CreateClassification"> </a>

È possibile specificare se un Microsoft 365 globale viene visualizzato nell'elenco indirizzi globale (GAL) e in altri elenchi dell'organizzazione. Ad esempio, se si dispone di un gruppo di reparti legali che non si desidera visualizzare nell'elenco indirizzi, è possibile impedire che tale gruppo venga visualizzato nell'elenco indirizzi globale. Eseguire il cmdlet Set-Unified Group per nascondere il gruppo dall'elenco di indirizzi in questo modo:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Consenti solo agli utenti interni di inviare messaggi Microsoft 365 gruppi
<a name="BKMK_CreateClassification"> </a>

Se non si desidera che gli utenti di altre organizzazioni inviino messaggi di posta elettronica a un Microsoft 365 gruppo, è possibile modificare le impostazioni per tale gruppo. Consentirà solo agli utenti interni di inviare un messaggio di posta elettronica al gruppo. Se un utente esterno tenta di inviare un messaggio a tale gruppo, verrà rifiutato.

Eseguire il cmdlet Set-UnifiedGroup per aggiornare questa impostazione, in questo modo:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Aggiungere suggerimenti messaggio a Microsoft 365 gruppi
<a name="BKMK_CreateClassification"> </a>

Ogni volta che un mittente tenta di inviare un messaggio di posta elettronica a Microsoft 365 gruppo, è possibile visualizzare un suggerimento messaggio.

Eseguire il cmdlet Set-Unified Group per aggiungere un avviso messaggio al gruppo:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Insieme a Suggerimento messaggio, è anche possibile impostare MailTipTranslations, che specifica lingue aggiuntive per l'avviso messaggio. Si supponga di voler disporre della traduzione in spagnolo, quindi eseguire il comando seguente:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Modificare il nome visualizzato del Microsoft 365 gruppo

Il nome visualizzato specifica il nome del Microsoft 365 gruppo. È possibile visualizzare questo nome nell'interfaccia di amministrazione di Exchange o Microsoft 365 di amministrazione. È possibile modificare il nome visualizzato del gruppo o assegnare un nome visualizzato a un gruppo di Microsoft 365 esistente eseguendo il comando Set-UnifiedGroup:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Modificare l'impostazione predefinita Microsoft 365 gruppi per Outlook in Pubblico o Privato
<a name="BKMK_CreateClassification"> </a>

Microsoft 365 I gruppi in Outlook vengono creati come Privati per impostazione predefinita. Se l'organizzazione desidera Microsoft 365 gruppi come pubblici per impostazione predefinita (o tornare a Privato), utilizzare la sintassi del cmdlet PowerShell seguente:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Per impostare private:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Per verificare l'impostazione:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Per ulteriori informazioni, vedere [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig.](/powershell/module/exchange/get-organizationconfig)

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 Cmdlet per i gruppi

I cmdlet seguenti possono essere utilizzati con Microsoft 365 gruppi.

|**Nome cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |Utilizzare questo cmdlet per cercare gruppi Microsoft 365 esistenti e per visualizzare le proprietà dell'oggetto gruppo  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |Aggiornare le proprietà di un gruppo Microsoft 365 specifico  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |Creare un nuovo Microsoft 365 gruppo. Questo cmdlet fornisce un set minimo di parametri. Per impostare i valori per le proprietà estese, utilizzare Set-UnifiedGroup dopo aver creato il nuovo gruppo  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |Eliminare un gruppo Microsoft 365 esistente  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Recuperare le informazioni sull'appartenenza e sul proprietario per un Microsoft 365 gruppo  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |Aggiungere membri, proprietari e sottoscrittori a un gruppo Microsoft 365 esistente <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |Rimuovere proprietari e membri da un gruppo Microsoft 365 esistente  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |Usato per visualizzare le informazioni sulla foto dell'utente associata a un account. Le foto degli utenti sono archiviate in Active Directory  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |Usato per associare una foto utente a un account. Le foto degli utenti sono archiviate in Active Directory  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |Rimuovere la foto per un Microsoft 365 gruppo  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Aggiornare le liste di distribuzione Microsoft 365 gruppi](/office365/admin/manage/upgrade-distribution-lists)

[Gestire chi può creare gruppi in Microsoft 365](/office365/admin/create-groups/manage-creation-of-groups)

[Gestire l'accesso guest Microsoft 365 gruppi](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Modificare l'appartenenza a un gruppo statico in dinamico](/azure/active-directory/users-groups-roles/groups-change-type)
