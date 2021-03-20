---
title: Scegliere il dominio da utilizzare per la creazione di gruppi di Microsoft 365
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
ms.openlocfilehash: 4908d5bd58ca6d0fbb50151983ddb459f0732284
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904685"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Scegliere il dominio da utilizzare per la creazione di gruppi di Microsoft 365

Alcune organizzazioni usano domini di posta elettronica separati per segmentare le diverse parti dell'azienda. È possibile specificare il dominio da utilizzare quando gli utenti creano gruppi di Microsoft 365.
  
Se l'organizzazione necessita che gli utenti creino i propri gruppi in domini diversi dal dominio accettato predefinito dell'azienda, è possibile consentire questa operazione configurando i criteri degli indirizzi di posta elettronica tramite PowerShell.

Prima di poter eseguire i cmdlet di PowerShell, scaricare e installare un modulo che consente di parlare con l'organizzazione. Vedere [Connettersi a Exchange Online usando una sessione remota di PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="example-scenarios"></a>Scenari di esempio

Supponiamo che il dominio principale dell'azienda sia Contoso.com. Tuttavia, il dominio accettato predefinito dell'organizzazione è service.contoso.com. Ciò significa che i gruppi verranno creati in service.contoso.com (ad esempio, jimsteam@service.contoso.com).
  
Supponiamo che nell'organizzazione siano configurati anche sottodomini. Si desidera che i gruppi siano creati anche in questi domini:
  
- students.contoso.com per gli studenti
    
- faculty.contoso.com per membri dell'istituto di istruzione
    
I due scenari seguenti illustrano come eseguire questa operazione.

> [!NOTE]
> Quando si dispone di EAP mulitple, questi vengono valutati nell'ordine di priorità. Un valore pari a 1 indica la massima priorità. Una volta che un EAP corrisponde, non viene valutato alcun altro EAP e gli indirizzi che vengono contrassegnati sul gruppo sono come in base al EAP corrispondente. > Se nessun criterio EAP corrisponde ai criteri specificati, il provisioning del gruppo viene eseguito nel dominio accettato predefinito dell'organizzazione. Per informazioni dettagliate su come aggiungere un dominio accettato, vedere [Gestire i domini accettati in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
  
### <a name="scenario-1"></a>Scenario 1

L'esempio seguente mostra come eseguire il provisioning di tutti i gruppi di Microsoft 365 nell'organizzazione nel groups.contoso.com dominio.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Scenario 2

Supponiamo che tu voglia controllare in quali sottodomini vengono creati i gruppi di Microsoft 365. Si vuole che:
  
- Gruppi creati dagli studenti (utenti con **Reparto** impostato su **Studenti)** nel students.groups.contoso.com dominio. Utilizzare questo comando:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Gruppi creati dai membri dell'istituto di docente (gli utenti che hanno department impostato su Faculty o l'indirizzo di posta elettronica **contiene faculty.contoso.com)** nel faculty.groups.contoso.com dominio.  Utilizzare questo comando:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- I gruppi creati da chiunque altro vengono creati nel groups.contoso.com dominio. Utilizzare questo comando:
    
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

Se l'organizzazione è configurata in uno scenario ibrido, vedere [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Informazioni aggiuntive sull'uso dei gruppi di criteri degli indirizzi di posta elettronica:

Ci sono alcune altre cose da sapere:
  
- La velocità di creazione dei gruppi dipende dal numero di EAP configurati nell'organizzazione.
    
- Gli amministratori e gli utenti possono anche modificare i domini quando creano gruppi.
    
- Il gruppo di utenti viene determinato usando le query standard (proprietà utente) già disponibili. Per informazioni sulle proprietà filtrabili supportate, vedere [Proprietà filtrabili per il parametro - RecipientFilter](/powershell/exchange/recipientfilter-properties). 
    
- Se si configurano criteri EAP per i gruppi, viene selezionato il dominio accettato predefinito per la creazione di gruppi.
    
- Se si rimuove un dominio accettato, è necessario aggiornare prima i criteri EAP, altrimenti ci saranno conseguenze sul provisioning dei gruppi.
    
- È possibile configurare un limite massimo di 100 criteri per gli indirizzi di posta elettronica per un'organizzazione.
    
## <a name="related-articles"></a>Articoli correlati

[Pianificazione dettagliata della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Creare un gruppo di Microsoft 365 nell'interfaccia di amministrazione](../admin/create-groups/create-groups.md)