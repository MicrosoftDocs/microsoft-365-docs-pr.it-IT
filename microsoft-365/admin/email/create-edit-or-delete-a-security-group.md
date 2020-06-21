---
title: Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informazioni su come creare, modificare o eliminare un gruppo di sicurezza.
ms.openlocfilehash: c7c8d57037d972cd89dad45358dc5a7aa3fb86e8
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780242"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Nella pagina Microsoft 365 **Groups** è possibile creare gruppi di account utente che è possibile utilizzare per assegnare le stesse autorizzazioni in SharePoint Online e CRM online. Ad esempio, un amministratore può creare un gruppo di sicurezza per consentire a un determinato gruppo di utenti di accedere a un sito di SharePoint. Solo gli amministratori di gestione globale e degli utenti dispongono delle autorizzazioni per creare, modificare o eliminare gruppi di sicurezza. Per ulteriori informazioni sui ruoli di amministratore, vedere [assegnazione di ruoli](../add-users/assign-admin-roles.md)di amministratore. 
  
Sono inoltre disponibili [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che è possibile usare per inviare messaggi di posta elettronica o assegnare autorizzazioni a un gruppo di utenti e [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che consentono di concedere agli utenti i diritti e l'accesso a siti e raccolte siti. 
  
> [!IMPORTANT]
>  Pianificazione dell'utilizzo delle cassette postali del sito? Tutti gli utenti aggiunti a un sito di SharePoint tramite un gruppo di sicurezza anziché essere aggiunti singolarmente possono utilizzare solo la cassetta postale del sito di SharePoint. Questi utenti non saranno in grado di accedere alla cassetta postale del sito da Outlook. Per ulteriori informazioni, vedere [utilizzare i gruppi di Microsoft 365 anziché le cassette postali del sito](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b). 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Gestire i gruppi di sicurezza nell'interfaccia di amministrazione

### <a name="add-a-security-group"></a>Aggiungere un gruppo di sicurezza

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **gruppi**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .
  
2. Nella pagina **gruppi** selezionare **Aggiungi un gruppo**.
    
3. Nella pagina **scegliere il tipo di gruppo** scegliere **sicurezza**. 
    
4. Seguire la procedura per completare la creazione del gruppo. 
 
### <a name="add-members-to-a-security-group"></a>Aggiungere membri a un gruppo di sicurezza

::: moniker range="o365-worldwide"
    
1. Selezionare il nome del gruppo di sicurezza nella pagina **gruppi** , quindi selezionare **Visualizza tutti e Gestisci membri**nella scheda **membri** . 
    
2. Nel riquadro gruppo, selezionare **Aggiungi membri** e scegliere la persona nell'elenco oppure digitare il nome della persona che si desidera aggiungere nella casella di **ricerca** e quindi selezionare **Salva**.
    
    Per rimuovere i membri, selezionare la X accanto al nome. 
  
::: moniker-end

::: moniker range="o365-germany"

1. Selezionare il nome del gruppo di sicurezza nella pagina **gruppi** e quindi fare clic su **modifica** accanto a **membri**. 
    
2. Nel riquadro gruppo, selezionare **Aggiungi membri** e scegliere la persona nell'elenco oppure digitare il nome della persona che si desidera aggiungere nella casella di **ricerca** e quindi selezionare **Salva**.
    
    Per rimuovere i membri, selezionare la X accanto al nome. 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. Selezionare il nome del gruppo di sicurezza nella pagina **gruppi** e quindi fare clic su **modifica** accanto a **membri**. 
    
2. Nel riquadro gruppo, selezionare **Aggiungi membri** e scegliere la persona nell'elenco oppure digitare il nome della persona che si desidera aggiungere nella casella di **ricerca** e quindi selezionare **Salva**.
    
    Per rimuovere i membri, selezionare la X accanto al nome.

::: moniker-end

### <a name="edit-a-security-group"></a>Modificare un gruppo di sicurezza

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .
  
2. Nella pagina **gruppi** selezionare il nome del gruppo. 
    
3. Nel riquadro Impostazioni, selezionare la scheda **generale** o la scheda **membri** per modificare i dettagli o i membri del gruppo.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>, andare alla pagina **gruppi** \> **Groups** .  
  
2. Nella pagina **gruppi** selezionare il nome del gruppo. 
    
3. Nel riquadro gruppo di sicurezza selezionare **modifica** accanto a **nome** o scheda **membri** per modificare i dettagli o i membri del gruppo.
    
4. Dopo aver apportato le modifiche, selezionare **Salva** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>, andare alla pagina **gruppi** \> **Groups** .
  
2. Nella pagina **gruppi** selezionare il nome del gruppo. 
    
3. Nel riquadro gruppo di sicurezza selezionare **modifica** accanto a **nome** o scheda **membri** per modificare i dettagli o i membri del gruppo.
    
4. Dopo aver apportato le modifiche, selezionare **Salva** > **Chiudi**.

::: moniker-end


### <a name="delete-a-security-group"></a>Eliminare un gruppo di sicurezza

1. Nell'interfaccia di amministrazione, andare alla pagina **gruppi**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .
    
2. Nella pagina **gruppi** selezionare il nome del gruppo. 
    
3. Selezionare **Elimina gruppo** (icona di wasetbin), quindi confermare selezionando **Elimina**.
    
    Selezionare **Chiudi** dopo che il gruppo è stato eliminato. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Gruppi in Exchange Online e SharePoint Online

Se si desidera creare gruppi di utenti in modo che sia possibile inviare messaggi di posta elettronica a tutti contemporaneamente, è possibile farlo nell'interfaccia di amministrazione di Exchange accedendo ai **Admin** \> **Exchange** \> gruppi di **destinatari** di Exchange per l'amministratore \> **Groups**. Fare quindi clic su **nuovo** ![ Aggiungi ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) e selezionare il tipo di gruppo che si desidera creare: 
  
- **Gruppo di distribuzione**: viene usato per distribuire messaggi a un gruppo di utenti. Viene anche definito un *gruppo di distribuzione abilitato alla posta elettronica*o una *lista di distribuzione*. Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione](https://technet.microsoft.com/library/bb124513.aspx).
    
- **Gruppo di sicurezza**: può essere usato per distribuire messaggi a un gruppo di utenti oppure per concedere autorizzazioni di accesso alle risorse. Questo gruppo è anche denominato *gruppo di sicurezza abilitato alla posta elettronica*. Per ulteriori informazioni, vedere [Gestire gruppi di sicurezza abilitati alla posta elettronica](https://technet.microsoft.com/library/bb123521.aspx).
    
- **Gruppo di distribuzione dinamico**: un tipo di gruppo di distribuzione la cui lista di destinatari viene ricalcolata ogni volta che si invia un messaggio in base alle condizioni e ai filtri definiti dall'utente. Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione dinamici](https://technet.microsoft.com/library/bb123722.aspx).
    
Dopo aver creato i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange, i nomi e gli elenchi di utenti vengono visualizzati nella pagina **gruppi di sicurezza** . È possibile eliminare tali gruppi in entrambe le posizioni, ma è possibile modificarli solo nell'interfaccia di amministrazione di Exchange. I gruppi di distribuzione dinamici non vengono visualizzati nella pagina **gruppi di sicurezza** . 
  
 I gruppi di SharePoint vengono creati are automaticamente quando si crea una raccolta sito. I gruppi predefiniti usano i livelli di autorizzazione predefiniti di SharePoint, a volte indicati come ruoli di SharePoint, per concedere agli utenti i diritti e l'accesso. Per ulteriori informazioni, vedere [gruppi di SharePoint predefiniti in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>In che modo un gruppo di sicurezza è diverso dai gruppi di sicurezza creati in SharePoint?

I gruppi di sicurezza possono essere utilizzati con SharePoint, Exchange, MDM, Windows e altro ancora. I gruppi di sicurezza creati in SharePoint vengono riconosciuti solo dalla raccolta siti di SharePoint.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>È necessario utilizzare I gruppi di sicurezza per garantire la protezione dell'organizzazione?

No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.
  
## <a name="can-i-send-email-to-a-security-group"></a>È possibile inviare messaggi di posta elettronica a un gruppo di sicurezza?

Sì. Tuttavia, se si desidera utilizzare i gruppi per la posta elettronica e la collaborazione, è consigliabile [creare un gruppo di Microsoft 365](../create-groups/create-groups.md) . 
  
