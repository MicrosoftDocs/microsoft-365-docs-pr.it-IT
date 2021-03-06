---
title: Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informazioni su come creare, modificare o eliminare un gruppo di sicurezza.
ms.openlocfilehash: 525acc45b293563f58bb9aa12c40bec1438cb055
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393956"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365

Nella pagina Microsoft 365 **gruppi** è possibile creare gruppi di account utente che è possibile utilizzare per assegnare le stesse autorizzazioni in SharePoint Online e CRM Online. Ad esempio, un amministratore può creare un gruppo di sicurezza per concedere a un determinato gruppo di utenti l'accesso a un SharePoint sito. Solo gli amministratori globali e di gestione degli utenti dispongono delle autorizzazioni per creare, modificare o eliminare gruppi di sicurezza. per ulteriori informazioni sui ruoli di amministratore, vedere [Assigning admin roles](../add-users/assign-admin-roles.md). 
  
Sono inoltre disponibili [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che è possibile usare per inviare messaggi di posta elettronica o assegnare autorizzazioni a un gruppo di utenti e [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che consentono di concedere agli utenti i diritti e l'accesso a siti e raccolte siti. 
  
> [!IMPORTANT]
>  Pianificazione dell'utilizzo delle cassette postali del sito Tutti gli utenti aggiunti a un sito SharePoint tramite un gruppo di sicurezza anziché essere aggiunti singolarmente possono utilizzare solo la cassetta postale del sito da SharePoint. Questi utenti non saranno in grado di accedere alla cassetta postale del sito da Outlook. Per ulteriori informazioni, vedere [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b). 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Gestire i gruppi di sicurezza nell'interfaccia di amministrazione

### <a name="add-a-security-group"></a>Aggiungere un gruppo di sicurezza

1. Nella pagina interfaccia di amministrazione di Microsoft 365 gruppi passare alla **pagina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi.</a>
  
2. Nella pagina **Gruppi** selezionare **Aggiungi un gruppo.**
    
3. Nella pagina **Scegliere un tipo di gruppo** scegliere **Sicurezza**. 
    
4. Seguire i passaggi per completare la creazione del gruppo. 
 
### <a name="add-members-to-a-security-group"></a>Aggiungere membri a un gruppo di sicurezza
    
1. Selezionare il nome del gruppo di sicurezza **nella** pagina Gruppi e nella **scheda** Membri selezionare Visualizza tutti e **gestisci membri**. 
    
2. Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona dall'elenco o digitare il nome della persona che si desidera aggiungere nella casella Di **ricerca** e quindi selezionare **Salva.**
    
    Per rimuovere i membri, selezionare la X accanto al nome. 
  
### <a name="edit-a-security-group"></a>Modificare un gruppo di sicurezza

1. Nell'interfaccia di amministrazione passare alla **pagina** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.
  
2. Nella pagina **Gruppi** selezionare il nome del gruppo. 
    
3. Nel riquadro delle impostazioni selezionare la **scheda Generale** o **Membri** per modificare i dettagli del gruppo o i membri.

### <a name="delete-a-security-group"></a>Eliminare un gruppo di sicurezza

1. Nell'interfaccia di amministrazione passare alla **pagina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.
    
2. Nella pagina **Gruppi** selezionare il nome del gruppo. 
    
3. Selezionare **Elimina gruppo** (icona wasetbin), quindi confermare selezionando **Elimina**.
    
    Selezionare **Chiudi** dopo l'eliminazione del gruppo. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Gruppi in Exchange Online e SharePoint Online

Se si desidera creare gruppi di utenti in modo da poter inviare messaggi di posta elettronica contemporaneamente, è possibile farlo nell'interfaccia di amministrazione di Exchange andando a **Admin** \> **Exchange** \> **Recipients** \> **Groups**. Quindi, selezionare **Nuovo** ![ aggiungi e selezionare il tipo di gruppo che si ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) desidera creare: 
  
- **Gruppo di distribuzione**: viene usato per distribuire messaggi a un gruppo di utenti. È anche denominato gruppo di distribuzione abilitato *alla* posta o lista *di distribuzione.* Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).
    
- **Gruppo di sicurezza**: può essere usato per distribuire messaggi a un gruppo di utenti oppure per concedere autorizzazioni di accesso alle risorse. Questo gruppo è anche denominato gruppo *di sicurezza abilitato alla posta .* Per ulteriori informazioni, vedere [Gestire gruppi di sicurezza abilitati alla posta elettronica](/Exchange/recipients/mail-enabled-security-groups).
    
- **Gruppo di distribuzione dinamico**: un tipo di gruppo di distribuzione la cui lista di destinatari viene ricalcolata ogni volta che si invia un messaggio in base alle condizioni e ai filtri definiti dall'utente. Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione dinamici](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).
    
Dopo aver creato i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange, i relativi nomi e gli elenchi di utenti vengono visualizzati nella **pagina Gruppi di** sicurezza. È possibile eliminare tali gruppi in entrambe le posizioni, ma è possibile modificarli solo nell'interfaccia di amministrazione di Exchange. I gruppi di distribuzione dinamici non vengono visualizzati nella **pagina Gruppi di** sicurezza. 
  
 I gruppi di SharePoint vengono creati are automaticamente quando si crea una raccolta sito. I gruppi predefiniti usano i livelli di autorizzazione predefiniti di SharePoint, a volte indicati come ruoli di SharePoint, per concedere agli utenti i diritti e l'accesso. Per ulteriori informazioni, vedere [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>In che modo un gruppo di sicurezza è diverso dai gruppi di sicurezza creati in SharePoint?

I gruppi di sicurezza possono essere usati con SharePoint, Exchange, MDM, Windows e altro ancora. I gruppi di sicurezza creati in SharePoint vengono riconosciuti solo dalla raccolta siti di SharePoint.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>È necessario utilizzare i gruppi di sicurezza per garantire la protezione dell'organizzazione?

No. È solo un altro modo di gestire la sicurezza dell'organizzazione. È sempre possibile concedere le autorizzazioni e l'accesso ai siti ai singoli utenti, ma con i gruppi di sicurezza si possono gestire più facilmente gruppi di utenti di dimensioni maggiori.
  
## <a name="can-i-send-email-to-a-security-group"></a>È possibile inviare messaggi di posta elettronica a un gruppo di sicurezza?

Sì. Tuttavia, se si desidera utilizzare i gruppi per la posta elettronica e la collaborazione, è consigliabile creare un Microsoft 365 [gruppo.](../create-groups/create-groups.md) 

## <a name="related-content"></a>Contenuto correlato

[Creare un gruppo nel interfaccia di amministrazione di Microsoft 365](../create-groups/create-groups.md) (articolo)\
[Spiegazione di Microsoft 365 gruppi agli utenti](../create-groups/explain-groups-knowledge-worker.md) (articolo)\
[Gestire un gruppo nell'interfaccia di amministrazione di Microsoft 365](../create-groups/manage-groups.md) (articolo)