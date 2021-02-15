---
title: Gestire i gruppi di Microsoft 365 con PowerShell
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
description: In questo articolo viene illustrato come eseguire attività di gestione comuni per i gruppi di Microsoft 365 in PowerShell.
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830616"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Gestire i gruppi di Microsoft 365 con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

In questo articolo vengono descritti i passaggi per eseguire attività di gestione comuni per i gruppi in Microsoft PowerShell. Vengono inoltre elencati i cmdlet di PowerShell per i gruppi. Per informazioni sulla gestione dei siti di SharePoint, vedere [Gestire i siti di SharePoint Online tramite PowerShell.](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Collegamento alle linee guida per l'utilizzo dei gruppi di Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Quando gli [utenti creano o modificano un gruppo in Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)è possibile mostrare loro un collegamento alle linee guida sull'utilizzo dell'organizzazione. Ad esempio, se è necessario aggiungere un prefisso o un suffisso specifico a un nome di gruppo.

Usare Azure Active Directory (Azure AD) PowerShell per puntare gli utenti alle linee guida di utilizzo dell'organizzazione per i gruppi di Microsoft 365. Consultare i [cmdlet di Azure Active Directory](https://go.microsoft.com/fwlink/?LinkID=827484) per la configurazione delle impostazioni di gruppo e seguire i passaggi descritti in Creare impostazioni a livello di **directory** per definire il collegamento ipertestuale delle linee guida sull'utilizzo. Dopo aver eseguito il cmdlet AAD, gli utenti visualizzano il collegamento alle linee guida quando creano o modificano un gruppo in Outlook.

![Creare un nuovo gruppo con il collegamento alle linee guida per l'uso](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Fare clic sulle linee guida per l'utilizzo dei gruppi per visualizzare le linee guida per i gruppi di Office 365 delle organizzazioni](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Consentire agli utenti di inviare come gruppo di Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Se si desidera abilitare i gruppi di Microsoft 365 a "Invia come", utilizzare i cmdlet [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) e [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) per configurarlo. Dopo aver abilitato questa impostazione, gli utenti del gruppo di Microsoft 365 possono usare Outlook o Outlook sul Web per inviare e rispondere alla posta elettronica come gruppo di Microsoft 365. Gli utenti possono passare al gruppo, creare un nuovo messaggio di posta elettronica e modificare il campo "Invia come" con l'indirizzo di posta elettronica del gruppo.

([È possibile eseguire questa operazione anche nell'interfaccia di amministrazione di Exchange.](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)

Utilizzare lo script seguente, sostituendolo con l'alias del gruppo che si desidera aggiornare e con l'alias dell'utente a cui si desidera *\<GroupAlias\>* *\<UserAlias\>* concedere le autorizzazioni. [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) per eseguire questo script.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Dopo l'esecuzione del cmdlet, gli utenti possono passare a Outlook o Outlook sul Web per inviarlo come gruppo, aggiungendo l'indirizzo di posta elettronica del gruppo al **campo Da.**

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Creare classificazioni per i gruppi di Microsoft 365 nell'organizzazione

È possibile creare etichette di riservatezza che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Microsoft 365. Se si desidera classificare i gruppi, è consigliabile usare le etichette di riservatezza anziché la funzionalità di classificazione dei gruppi precedente. Per informazioni sull'uso delle etichette di riservatezza, vedere Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di [Microsoft 365 e siti di SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

> [!IMPORTANT]
> Se attualmente si usano etichette di classificazione, non saranno più disponibili per gli utenti che creano gruppi dopo aver abilitato le etichette di riservatezza.

È comunque possibile utilizzare la funzionalità di classificazione dei gruppi precedente. È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Microsoft 365. Ad esempio, è possibile consentire agli utenti di impostare "Standard", "Secret" e "Top Secret" nei gruppi che creano. Le classificazioni di gruppo non vengono impostate per impostazione predefinita ed è necessario crearla per consentire agli utenti di impostarla. Usare Azure Active Directory PowerShell per puntare gli utenti alle linee guida di utilizzo dell'organizzazione per i gruppi di Microsoft 365.

Vedere i [cmdlet di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) per la configurazione delle impostazioni di gruppo e seguire i passaggi descritti in Creare impostazioni a livello di **directory** per definire la classificazione per i gruppi di Microsoft 365.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Per associare una descrizione a ogni classificazione, è possibile utilizzare l'attributo  *delle impostazioni ClassificationDescriptions* per definire.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

dove Classificazione corrisponde alle stringhe in ClassificationList.

Esempio:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Dopo aver eseguito il cmdlet di Azure Active Directory precedente per impostare la classificazione, eseguire il cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) se si desidera impostare la classificazione per un gruppo specifico.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Oppure creare un nuovo gruppo con una classificazione.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Per altri dettagli sull'uso di PowerShell di Exchange Online vedere [Uso di PowerShell con Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) e [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Una volta abilitate queste impostazioni, il proprietario del gruppo potrà scegliere una classificazione dal menu a  discesa in Outlook sul Web e Outlook e salvarla dalla pagina Modifica gruppo.

![Scegliere la classificazione dei gruppi di Microsoft 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Nascondere i gruppi di Microsoft 365 dall'elenco indirizzi globale.
<a name="BKMK_CreateClassification"> </a>

È possibile specificare se un gruppo di Microsoft 365 viene visualizzato nell'elenco indirizzi globale e in altri elenchi dell'organizzazione. Ad esempio, se si dispone di un gruppo di reparti legali che non si desidera visualizzare nell'elenco indirizzi, è possibile impedire che tale gruppo venga visualizzato nell'elenco indirizzi globale. Eseguire il cmdlet Set-Unified Gruppo di indirizzi per nascondere il gruppo dall'elenco di indirizzi nel modo seguente:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Consentire solo agli utenti interni di inviare messaggi ai gruppi di Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Se non si desidera che gli utenti di altre organizzazioni inviino messaggi di posta elettronica a un gruppo di Microsoft 365, è possibile modificare le impostazioni per tale gruppo. Consentirà solo agli utenti interni di inviare un messaggio di posta elettronica al gruppo. Se un utente esterno tenta di inviare un messaggio a tale gruppo, verrà rifiutato.

Eseguire il cmdlet Set-UnifiedGroup per aggiornare questa impostazione, come nell'esempio seguente:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Aggiungere suggerimenti messaggio ai gruppi di Microsoft 365
<a name="BKMK_CreateClassification"> </a>

Ogni volta che un mittente tenta di inviare un messaggio di posta elettronica a un gruppo di Microsoft 365, è possibile visualizzare un avviso messaggio.

Eseguire il cmdlet Set-Unified Group per aggiungere un avviso messaggio al gruppo:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Insieme a Suggerimento messaggio, è anche possibile impostare MailTipTranslations, che specifica lingue aggiuntive per l'avviso messaggio. Si supponga di voler utilizzare la traduzione spagnola, quindi eseguire il comando seguente:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Modificare il nome visualizzato del gruppo di Microsoft 365

Il nome visualizzato specifica il nome del gruppo di Microsoft 365. È possibile visualizzare questo nome nell'interfaccia di amministrazione di Exchange o nell'interfaccia di amministrazione di Microsoft 365. È possibile modificare il nome visualizzato del gruppo o assegnare un nome visualizzato a un gruppo di Microsoft 365 esistente eseguendo il comando Set-UnifiedGroup seguente:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Modificare l'impostazione predefinita dei gruppi di Microsoft 365 per Outlook su Pubblica o Privata
<a name="BKMK_CreateClassification"> </a>

I gruppi di Microsoft 365 in Outlook vengono creati come privati per impostazione predefinita. Se l'organizzazione desidera che i gruppi di Microsoft 365 siano creati come pubblici per impostazione predefinita (o tornare a Privato), utilizzare la sintassi del cmdlet di PowerShell seguente:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Per impostare su Privato:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

Per verificare l'impostazione:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Per ulteriori informazioni, vedere [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig.](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)

## <a name="microsoft-365-groups-cmdlets"></a>Cmdlet per i gruppi di Microsoft 365

I cmdlet seguenti possono essere utilizzati con i gruppi di Microsoft 365.

|**Nome cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Utilizzare questo cmdlet per cercare i gruppi di Microsoft 365 esistenti e per visualizzare le proprietà dell'oggetto gruppo  <br/> |
|[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Aggiornare le proprietà di un gruppo di Microsoft 365 specifico  <br/> |
|[New-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Creare un nuovo gruppo di Microsoft 365. Questo cmdlet fornisce un set minimo di parametri. Per impostare i valori per le proprietà estese, utilizzare Set-UnifiedGroup dopo aver creato il nuovo gruppo  <br/> |
|[Remove-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Eliminare un gruppo di Microsoft 365 esistente  <br/> |
|[Get-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Recuperare informazioni sull'appartenenza e sul proprietario per un gruppo di Microsoft 365  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Aggiungere membri, proprietari e sottoscrittori a un gruppo di Microsoft 365 esistente <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Rimuovere proprietari e membri da un gruppo di Microsoft 365 esistente  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Usato per visualizzare informazioni sulla foto dell'utente associata a un account. Le foto degli utenti vengono archiviate in Active Directory  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Usato per associare una foto utente a un account. Le foto degli utenti vengono archiviate in Active Directory  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Rimuovere la foto per un gruppo di Microsoft 365  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Aggiornare le liste di distribuzione ai gruppi di Microsoft 365](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Gestire chi può creare gruppi di Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Gestire l'accesso guest ai gruppi di Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Modificare l'appartenenza a gruppi statici in dinamico](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
