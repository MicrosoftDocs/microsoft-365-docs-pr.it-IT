---
title: Scegliere il dominio da utilizzare per la creazione dei gruppi di Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Informazioni su come scegliere il dominio da utilizzare per la creazione di gruppi di Microsoft 365 configurando i criteri degli indirizzi di posta elettronica tramite PowerShell.
ms.openlocfilehash: bb6137a3dfce17bc9c94648e5ea9e12ec2776195
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377438"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Scegliere il dominio da utilizzare per la creazione dei gruppi di Microsoft 365

Alcune organizzazioni usano domini di posta elettronica separati per segmentare le diverse parti dell'azienda. È possibile specificare il dominio da usare quando gli utenti creano gruppi di Microsoft 365.
  
Se l'organizzazione richiede agli utenti di creare i propri gruppi in domini diversi dal dominio accettato predefinito per la propria azienda, è possibile configurarli tramite la configurazione dei criteri degli indirizzi di posta elettronica (criteri EAP) tramite PowerShell.

Prima di poter eseguire i cmdlet di PowerShell, scaricare e installare un modulo che consentirà di parlare con l'organizzazione. Vedere [Connettersi a Exchange Online usando una sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).

## <a name="example-scenarios"></a>Scenari di esempio

Si supponga che il dominio principale dell'azienda sia Contoso.com. Tuttavia, il dominio accettato predefinito dell'organizzazione è service.contoso.com. Questo significa che i gruppi verranno creati in service.contoso.com (ad esempio, jimsteam@service.contoso.com).
  
Si supponga di disporre anche di sottodomini configurati nell'organizzazione. Si desidera che i gruppi vengano creati anche in questi domini:
  
- students.contoso.com per gli studenti
    
- faculty.contoso.com per membri dell'istituto di istruzione
    
I due scenari seguenti illustrano come eseguire questa operazione.

> [!NOTE]
> Quando si dispone di più criteri EAP, vengono valutati in base all'ordine di priorità. Un valore pari a 1 indica la massima priorità. Una volta che un EAP corrisponde, non viene valutato un ulteriore EAP e gli indirizzi che vengono timbrati sul gruppo sono secondo il protocollo EAP corrispondente. > se non criteri EAP soddisfano i criteri specificati, il gruppo viene sottoposto a provisioning nel dominio accettato predefinito dell'organizzazione. Per informazioni dettagliate su come aggiungere un dominio accettato, vedere [Gestire i domini accettati in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428).
  
### <a name="scenario-1"></a>Scenario 1

Nell'esempio seguente viene illustrato come eseguire il provisioning di tutti i gruppi di Microsoft 365 nell'organizzazione nel dominio groups.contoso.com.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Si supponga di voler controllare quali gruppi di sottodomini vengono creati in Microsoft 365. Si vuole che:
  
- Gruppi creati dagli studenti (gli utenti che hanno un **reparto** impostato su **studenti**) nel dominio students.groups.contoso.com. Utilizzare questo comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- I gruppi creati dai membri della facoltà (gli utenti che hanno un **reparto** impostato su **docenti o indirizzo di posta elettronica contiene Faculty.contoso.com)**) nel dominio Faculty.groups.contoso.com. Utilizzare questo comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- I gruppi creati da chiunque altro vengono creati nel dominio groups.contoso.com. Utilizzare questo comando:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Cambiare i criteri per gli indirizzi di posta elettronica

Per modificare la priorità o i modelli dell'indirizzo di posta elettronica per un criterio EAP esistente, usare il cmdlet Set-EmailAddressPolicy.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.
  
## <a name="delete-email-address-policies"></a>Eliminare i criteri per gli indirizzi di posta elettronica

Per eliminare un criterio EAP, usare il cmdlet Remove-EmailAddressPolicy.
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

La modifica di un criterio EAP non influisce sui gruppi di cui è già stato eseguito il provisioning.
  
## <a name="hybrid-requirements"></a>Requisiti ibridi

Se l'organizzazione è configurata in uno scenario ibrido, vedere [Configure microsoft 365 groups with on-premises Exchange Hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) per assicurarsi che l'organizzazione soddisfi i requisiti per la creazione di gruppi di Microsoft 365. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Ulteriori informazioni sull'utilizzo dei gruppi di criteri degli indirizzi di posta elettronica:

Sono disponibili alcune altre informazioni:
  
- La velocità con cui vengono creati i gruppi dipendono dal numero di criteri EAP configurati nell'organizzazione.
    
- Gli amministratori e gli utenti possono modificare i domini anche quando creano gruppi.
    
- Il gruppo di utenti viene determinato usando le query standard (proprietà utente) già disponibili. Per informazioni sulle proprietà filtrabili supportate, vedere [Proprietà filtrabili per il parametro - RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties). 
    
- Se si configurano criteri EAP per i gruppi, viene selezionato il dominio accettato predefinito per la creazione di gruppi.
    
- Se si rimuove un dominio accettato, è necessario aggiornare prima i criteri EAP, altrimenti ci saranno conseguenze sul provisioning dei gruppi.
    
- È possibile configurare un limite massimo di 100 criteri per gli indirizzi di posta elettronica per un'organizzazione.
    
## <a name="related-articles"></a>Articoli correlati

[Creare un gruppo di Microsoft 365 nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
