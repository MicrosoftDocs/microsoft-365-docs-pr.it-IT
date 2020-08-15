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
ms.openlocfilehash: a9c25fc4fbc2fb1f39c6e7b9e7e5de0e778fd513
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691082"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>Gestire i gruppi Microsoft 365 con PowerShell
 
*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

In questo articolo vengono illustrati i passaggi per eseguire attività di gestione comuni per i gruppi di Microsoft PowerShell. Vengono inoltre elencati i cmdlet di PowerShell per i gruppi. Per informazioni sulla gestione dei siti di SharePoint, vedere [gestire i siti di SharePoint Online tramite PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Collegamento alle linee guida per l'utilizzo dei gruppi di Microsoft 365
<a name="BK_LinkToGuideLines"> </a>

Quando gli utenti [creano o modificano un gruppo in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), è possibile mostrargli un collegamento alle linee guida per l'utilizzo dell'organizzazione. Ad esempio, se si necessita di un prefisso o di un suffisso specifico da aggiungere al nome di un gruppo.
  
Utilizzare la PowerShell di Azure Active Directory (Azure AD) per indirizzare gli utenti alle linee guida per l'utilizzo dell'organizzazione per i gruppi di Microsoft 365. Estrarre i [cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://go.microsoft.com/fwlink/?LinkID=827484) e seguire la procedura descritta in **creare le impostazioni a livello di directory** per definire il collegamento ipertestuale linee guida per l'utilizzo. Dopo aver eseguito il cmdlet AAD, il collegamento alle linee guida verrà visualizzato dall'utente quando si crea o si modifica un gruppo in Outlook. 
  
![Creare un nuovo gruppo con linee guida di utilizzo collegamento](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)
  
![Fare clic su linee guida sull'utilizzo di gruppi per visualizzare le linee guida sui gruppi di Office 365](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)
  
## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Consenti agli utenti di inviare messaggi come gruppo di Microsoft 365
<a name="BK_LinkToGuideLines"> </a>
  
Se si desidera consentire ai gruppi di Microsoft 365 di "inviare con nome", utilizzare i cmdlet [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/Add-RecipientPermission) e [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/Get-Recipient) per configurarlo. Dopo aver abilitato questa impostazione, gli utenti del gruppo Microsoft 365 possono utilizzare Outlook o Outlook sul Web per inviare e rispondere alla posta elettronica come gruppo di Microsoft 365. Gli utenti possono accedere al gruppo, creare un nuovo messaggio di posta elettronica e cambiare il campo "Invia come" all'indirizzo di posta elettronica del gruppo. 

([È possibile eseguire questa operazione anche nell'interfaccia di amministrazione di Exchange](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)).
  
Utilizzare lo script seguente, sostituendo *\<GroupAlias\>* con l'alias del gruppo che si desidera aggiornare e *\<UserAlias\>* con l'alias dell'utente a cui si desidera concedere le autorizzazioni. [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) per eseguire questo script.

```PowerShell
$groupAlias = "<GroupAlias>"

$userAlias = "<UserAlias>"


$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Dopo l'esecuzione del cmdlet, gli utenti possono accedere a Outlook o Outlook sul Web per l'invio come gruppo, aggiungendo l'indirizzo di posta elettronica del gruppo al campo **da** . 

## <a name="create-classifications-for-office-groups-in-your-organization"></a>Creare classificazioni per i gruppi di Office nell'organizzazione

È possibile creare etichette di riservatezza che possono essere impostate dagli utenti dell'organizzazione durante la creazione di un gruppo di Microsoft 365. Se si desidera classificare i gruppi, è consigliabile utilizzare le etichette di riservatezza anziché la caratteristica classificazione gruppi precedenti. Per informazioni sull'utilizzo di etichette di riservatezza, vedere [use Sensitivity labels to protect content in Microsoft teams, microsoft 365 Groups e SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!IMPORTANT]
> Se attualmente si utilizzano le etichette di classificazione, non saranno più disponibili per gli utenti che creano gruppi una volta abilitate le etichette di riservatezza.

È comunque possibile utilizzare la caratteristica classificazione gruppi precedenti. È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Office 365. Ad esempio, è possibile consentire agli utenti di impostare "standard", "segreto" e "Top Secret" sui gruppi creati. Le classificazioni di gruppo non vengono impostate per impostazione predefinita ed è necessario crearla affinché gli utenti lo configurano. Utilizzare PowerShell di Azure Active Directory per indirizzare gli utenti alle linee guida per l'utilizzo dell'organizzazione per i gruppi di Office 365.
  
Estrarre i [cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) e seguire la procedura descritta in **create settings at the directory Level** per definire la classificazione per i gruppi di Office 365. 
  
```
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Per associare una descrizione a ogni classificazione, è possibile utilizzare l'attributo Settings  *ClassificationDescriptions* per definire.
  
```
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

dove la classificazione corrisponde alle stringhe presenti nella classificazione.

Esempio:
  
```
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Dopo aver eseguito il cmdlet sopra Azure Active Directory per impostare la classificazione, eseguire il cmdlet [set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) se si desidera impostare la classificazione per un gruppo specifico. 
  
```
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact> 
```

O creare un nuovo gruppo con una classificazione.
  
```
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public> 
```

Per altri dettagli sull'uso di PowerShell di Exchange Online vedere [Uso di PowerShell con Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell) e [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). 
  
Dopo aver abilitato queste impostazioni, il proprietario del gruppo sarà in grado di scegliere una classificazione dal menu a discesa in Outlook sul Web e Outlook e salvarla dalla pagina **modifica** gruppo. 
  
![Scegliere la classificazione di gruppo di Office 365](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)
  
## <a name="hide-office-365-groups-from-gal"></a>Nascondere i gruppi di Office 365 dall'elenco indirizzi globale
<a name="BKMK_CreateClassification"> </a>

È possibile specificare se un gruppo di Office 365 viene visualizzato nell'elenco indirizzi globale (GAL) e negli altri elenchi nell'organizzazione. Ad esempio, se si dispone di un gruppo di reparto legale che non si desidera visualizzare nell'elenco degli indirizzi, è possibile impedire che il gruppo venga visualizzato in GAL. Eseguire il cmdlet Set-Unified Group per nascondere l'elenco indirizzi di gruppo in questo modo:
  
```
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-office-365-group"></a>Consenti solo agli utenti interni di inviare messaggi al gruppo di Office 365
<a name="BKMK_CreateClassification"> </a>

Se non si desidera che gli utenti di altre organizzazioni possano inviare messaggi di posta elettronica a un gruppo di Office 365, è possibile modificare le impostazioni per il gruppo. Permetterà solo agli utenti interni di inviare un messaggio di posta elettronica al gruppo. Se l'utente esterno tenta di inviare un messaggio al gruppo, verrà rifiutato.
  
Eseguire il cmdlet Set-UnifiedGroup per aggiornare questa impostazione, ad esempio:

```
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-the-office-365-groups"></a>Aggiungere suggerimenti messaggio ai gruppi di Office 365
<a name="BKMK_CreateClassification"> </a>

Ogni volta che un mittente tenta di inviare un messaggio di posta elettronica a un gruppo di Office 365, è possibile mostrargli un avviso messaggio.
  
Eseguire il cmdlet Set-Unified Group per aggiungere un avviso messaggio al gruppo:

```
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Insieme a avviso messaggio, è anche possibile impostare MailTipTranslations, che specifica altre lingue per il avviso messaggio. Si supponga di voler disporre della traduzione spagnola, quindi eseguire il comando riportato di seguito:
  
```
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-display-name-of-the-office-365-group"></a>Modificare il nome visualizzato del gruppo Office 365

Nome visualizzato consente di specificare il nome del gruppo di Office 365. È possibile visualizzare questo nome nell'interfaccia di amministrazione di Exchange o nell'interfaccia di amministrazione di Microsoft 365. È possibile modificare il nome visualizzato del gruppo o assegnare un nome visualizzato a un gruppo di Office 365 esistente eseguendo il comando set-UnifiedGroup:

```
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-office-365-groups-for-outlook-to-public-or-private"></a>Modificare l'impostazione predefinita dei gruppi di Office 365 per Outlook su pubblico o privato
<a name="BKMK_CreateClassification"> </a>

I gruppi di Office 365 in Outlook vengono creati come privati per impostazione predefinita. Se l'organizzazione desidera che i gruppi di Office 365 vengano creati come pubblici per impostazione predefinita o di nuovo su privato, utilizzare la sintassi del cmdlet di PowerShell:
  
 `Set-OrganizationConfig -DefaultGroupAccessType Public`
  
Per impostare su privato:
  
 `Set-OrganizationConfig -DefaultGroupAccessType Private`
  
Per verificare l'impostazione: 
  
 `Get-OrganizationConfig | ft DefaultGroupAccessType`
  
Per ulteriori informazioni, vedere [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) e [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/Get-OrganizationConfig).
  
## <a name="office-365-groups-cmdlets"></a>Cmdlet per i gruppi di Office 365

I cmdlet seguenti possono essere utilizzati con i gruppi di Office 365.
  
|**Nome cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |Utilizzare questo cmdlet per cercare i gruppi di Office 365 esistenti e per visualizzare le proprietà dell'oggetto Group.  <br/> |
|[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |Aggiornare le proprietà di uno specifico gruppo di Office 365  <br/> |
|[New-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |Creare un nuovo gruppo di Office 365. Questo cmdlet fornisce un set di parametri minimo, per impostare i valori per le proprietà estese, utilizzare set-UnifiedGroup dopo aver creato il nuovo gruppo.  <br/> |
|[Remove-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |Eliminare un gruppo di Office 365 esistente  <br/> |
|[Get-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |Recuperare le informazioni sull'appartenenza e sul proprietario di un gruppo di Office 365  <br/> |
|[Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |Aggiungere centinaia o migliaia di utenti o nuovi proprietari a un gruppo di Office 365 esistente  <br/> |
|[Remove-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |Rimuovere proprietari e membri da un gruppo di Office 365 esistente  <br/> |
|[Get-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |Utilizzato per visualizzare le informazioni sulla foto utente associata a un account. Le foto degli utenti vengono archiviate in Active Directory  <br/> |
|[Set-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |Utilizzato per associare una foto utente a un account. Le foto degli utenti vengono archiviate in Active Directory  <br/> |
|[Remove-UserPhoto](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |Rimuovere la foto per un gruppo di Office 365  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Aggiornare le liste di distribuzione a gruppi di Office 365](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

[Gestire gli utenti autorizzati a creare gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Gestire l'accesso degli utenti guest ai gruppi di Office 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Modificare l'appartenenza al gruppo statico in Dynamic in](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
