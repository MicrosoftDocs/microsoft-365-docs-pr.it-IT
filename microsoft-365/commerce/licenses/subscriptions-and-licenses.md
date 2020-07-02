---
title: Informazioni su abbonamenti e licenze in Microsoft 365 for business
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Informazioni su abbonamenti e licenze in Microsoft 365 for business.
ms.date: 07/01/2020
ms.openlocfilehash: 9f8576b00b942c4b38d6192770bd2128afb4b104
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015960"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Informazioni su abbonamenti e licenze in Microsoft 365 for business

Quando si acquista un abbonamento a Microsoft 365 for business, è necessario iscriversi a una serie di app e servizi pagati su base mensile o annuale. Le applicazioni e i servizi ricevuti come parte dell'abbonamento dipendono dal prodotto acquistato, ad esempio Microsoft 365 Apps for business o Microsoft 365 business standard. È possibile vedere cosa viene fornito con ogni prodotto nella pagina [Microsoft 365 per le aziende di piccole e medie dimensioni](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) .

Quando si acquista un abbonamento, occorre specificare il numero di licenze necessario, in base al numero di utenti presenti all'interno dell'organizzazione. Dopo aver acquistato un abbonamento, è possibile creare account per gli utenti dell'organizzazione e quindi assegnare una licenza a ogni persona. Quando si modificano le esigenze dell'organizzazione, è possibile acquistare altre licenze per accogliere nuove persone o riassegnare le licenze ad altri utenti quando qualcuno lascia la propria azienda.

Se si hanno più abbonamenti, è possibile assegnare le licenze a utenti diversi per ogni abbonamento. Ad esempio, è possibile assegnare tutti gli utenti a tutte le applicazioni e i servizi di Microsoft 365 come parte di un abbonamento a Microsoft 365 business standard. È inoltre possibile assegnare un sottoinsieme di utenti a Visio online tramite una sottoscrizione di Visio distinta.

## <a name="how-many-devices-can-people-install-office-on"></a>Su quanti dispositivi è possibile installare Office?

Se l'abbonamento include uno dei prodotti seguenti, ogni persona può installare Office su un massimo di cinque PC o Mac, cinque tablet e cinque telefoni.

:::row:::
   :::column span="":::
        -Microsoft 365 Apps for Business-Microsoft 365 Apps for Enterprise-Microsoft 365 business standard-Microsoft 365 Business Premium-Microsoft 365 a3-Microsoft 365 a5
   :::column-end:::
   :::column span="":::
        -Microsoft 365 E3-Microsoft 365 E5-Office 365 a1 Plus-Office 365 a3-Office 365 a5-Office 365 E3-Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Cosa succede quando si assegna una licenza a un utente?

La tabella seguente descrive cosa accade automaticamente quando si assegna una licenza a un utente:
  
|**Se l'abbonamento include questo servizio**|**Ecco cosa accade automaticamente**|
|:-----|:-----|
|Exchange Online  <br/> |Viene creata una cassetta postale per l'utente. <br/> Per informazioni sull'SLA per il completamento di questa attività, vedere ["setting up..." messaggi nell'interfaccia di amministrazione di Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |All'utente vengono assegnate autorizzazioni di modifica per il sito del team predefinito di SharePoint Online.  <br/> |
|Skype for Business online  <br/> |La persona ha accesso alle funzionalità associate alla licenza.  <br/> |
|Microsoft 365 Apps for enterprise  <br/> |La persona può scaricare le app di Office su un massimo di cinque Mac o PC, cinque tablet e cinque smartphone.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Informazioni sulle licenze per cassette postali non di utenti

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Creare una cassetta postale condivisa](../../admin/email/create-a-shared-mailbox.md)
- [Rimuovere una licenza da una cassetta postale condivisa](../../admin/email/remove-license-from-shared-mailbox.md)
- [Cassette postali condivise in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) per tutti gli altri piani di Microsoft 365.
- [Creare e gestire cassette postali sala](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Gestire le cassette postali attrezzatura](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Chi può assegnare licenze?

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**Ruolo di amministratore**|**Assegnare una licenza**|**Annullamento dell'assegnazione di una licenza**|**Acquistare altre licenze**|**Eliminare un account**|
|:-----|:-----|:-----|:-----|:-----|
|Amministratore fatturazione  <br/> |No  <br/> |No  <br/> |Sì  <br/> |No  <br/> |
|Amministratore globale  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |
|Amministratore licenze <br/> |Sì <br/>|Sì <br/> |No <br/> |No <br/> |
|Amministratore del supporto tecnico  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Amministratore utenti  <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |Sì  <br/> |

## <a name="related-content"></a>Contenuto correlato

[Acquistare o rimuovere licenze per l'abbonamento aziendale](buy-licenses.md) (articolo) \
[Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md) (articolo) \
[Annullamento dell'assegnazione delle licenze da parte degli utenti](../../admin/manage/remove-licenses-from-users.md) (articolo) \
[Rimuovere una licenza da una cassetta postale condivisa](../../admin/email/remove-license-from-shared-mailbox.md) (articolo)