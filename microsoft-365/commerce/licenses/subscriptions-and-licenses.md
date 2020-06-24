---
title: Informazioni su abbonamenti e licenze in Microsoft 365 for business
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7ac93507-0e38-4398-8bfe-9c1d123cb387
description: 'Informazioni su abbonamenti e licenze in Microsoft 365 for business e sapere chi può assegnare licenze e cosa succede quando si assegna una licenza a un utente. '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: f83b2069bd1b4c86e2198252a54ed2e8e5c55a04
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844681"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Informazioni su abbonamenti e licenze in Microsoft 365 for business

In questo articolo viene illustrata la relazione tra abbonamenti e licenze e vengono fornite informazioni aggiuntive su [chi può assegnare licenze](#find-out-who-can-assign-licenses), [capire cosa succede quando si assegna una licenza a un utente](#understand-what-happens-when-you-assign-a-license-to-someone)e il [numero di dispositivi in cui gli utenti possono installare Office](#how-many-devices-can-people-install-office-on). Include anche collegamenti per [la comprensione delle licenze per le cassette postali non utente](#understand-licenses-for-non-user-mailboxes)e [gli articoli sulla gestione delle licenze](#articles-about-managing-licenses).
  
Quando si acquista un abbonamento a Microsoft 365 for business, è necessario iscriversi a una serie di applicazioni e servizi pagati su base mensile o annuale. Le applicazioni e i servizi ricevuti come parte dell'abbonamento dipendono dal prodotto acquistato, ad esempio Microsoft 365 Apps for business o Microsoft 365 business standard. È possibile esaminare cosa viene fornito con ogni prodotto nella [pagina Acquista Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1). 

È possibile esaminare diverse opzioni di licenza disponibili in [Microsoft 365 per le aziende di piccole e medie dimensioni](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/licensing-microsoft-365-in-smb)

Quando si acquista un abbonamento, occorre specificare il numero di licenze necessario, in base al numero di utenti presenti all'interno dell'organizzazione. Dopo aver completato l'acquisto, è possibile creare gli account per gli utenti e assegnare una licenza a ogni persona. Quando si modificano le esigenze dell'organizzazione, è possibile acquistare altre licenze per accogliere nuove persone o riassegnare le licenze ad altri utenti quando qualcuno lascia la propria azienda. 

Se si hanno più abbonamenti, è possibile assegnare le licenze a utenti diversi per ogni abbonamento. Ad esempio, tutti gli utenti possono essere assegnati a tutte le applicazioni e i servizi di Microsoft 365 come parte di una sottoscrizione di Microsoft 365 business standard, mentre un sottoinsieme di utenti può anche essere assegnato a Visio online tramite una sottoscrizione di Visio distinta. 

  
## <a name="find-out-who-can-assign-licenses"></a>Individuare chi può assegnare licenze

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**Ruolo di amministratore**|**Assegnare una licenza**|**Rimuovere una licenza**|**Acquisto di ulteriori licenze**|**Eliminare un account**|
|:-----|:-----|:-----|:-----|:-----|
|Amministratore globale  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Amministratore fatturazione  <br/> |No  <br/> |No  <br/> |Sì  <br/> |No  <br/> |
|Amministratore Gestione utenti  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |Sì  <br/> |
|Amministratore dei servizi  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Amministratore password  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
   
## <a name="understand-what-happens-when-you-assign-a-license-to-someone"></a>Cosa accade quando si assegna una licenza a un utente

La tabella seguente descrive cosa accade automaticamente quando si assegna una licenza a un utente:
  
|**Se l'abbonamento include questo servizio**|**Ecco cosa accade automaticamente**|
|:-----|:-----|
|Exchange Online  <br/> |Viene creata una cassetta postale per l'utente.  <br/> Per informazioni sull'SLA per il completamento di questa attività, vedere ["setting up..." messaggi nell'interfaccia di amministrazione di Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |All'utente vengono assegnate autorizzazioni di modifica per il sito del team predefinito di SharePoint Online.  <br/> |
|Skype for Business online  <br/> |L'utente avrà accesso alle funzionalità associate alla licenza.  <br/> |
|Microsoft 365 Apps for enterprise  <br/> |L'utente potrà scaricare Microsoft Office su un massimo di 5 Mac o PC, 5 tablet e 5 smartphone.  <br/> |
   
## <a name="how-many-devices-can-people-install-office-on"></a>Su quanti dispositivi è possibile installare Office?

Se l'abbonamento include uno dei prodotti seguenti, ogni persona può installare Office su un massimo di 5 PC o Mac, 5 tablet e 5 telefoni.
  
- Microsoft 365 Apps for business
    
- Microsoft 365 Business Standard
    
- Microsoft 365 Apps for enterprise
    
- Office 365 Enterprise E3
    
- Office 365 Enterprise E5
    
## <a name="understand-licenses-for-non-user-mailboxes"></a>Informazioni sulle licenze per cassette postali non di utenti

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Creare una cassetta postale condivisa](../../admin/email/create-a-shared-mailbox.md)
    
- [Cassette postali condivise in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=847433) per tutti gli altri piani di Microsoft 365. 
    
- [Creare e gestire cassette postali sala](https://go.microsoft.com/fwlink/p/?linkid=847434)
    
- [Gestire le cassette postali attrezzatura](https://go.microsoft.com/fwlink/p/?linkid=847435)
    
## <a name="articles-about-managing-licenses"></a>Articoli sulla gestione delle licenze

- [Assegnazione licenze agli utenti](../../admin/manage/assign-licenses-to-users.md).
    
- [Rimuovere licenze dagli utenti](../../admin/manage/remove-licenses-from-users.md)
    
- [Acquistare le licenze per l'abbonamento](buy-licenses.md)
    
- [Acquistare un altro abbonamento](../buy-another-subscription.md)
    
- [Acquistare o modificare un componente aggiuntivo](../buy-or-edit-an-add-on.md)
    
- [Rimuovere licenze dall'abbonamento](remove-licenses-from-subscription.md)
    
- [Risolvere i conflitti di licenza](../../admin/manage/resolve-license-conflicts.md)
    
- [Gestire le licenze utente di Yammer](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
