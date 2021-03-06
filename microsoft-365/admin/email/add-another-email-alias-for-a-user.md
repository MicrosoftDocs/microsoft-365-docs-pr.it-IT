---
title: Aggiungere un altro alias di posta elettronica per un utente
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
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Scopri come puoi avere più di un indirizzo di posta elettronica, denominato alias di posta elettronica, associato al tuo account Microsoft 365 per le aziende. '
ms.openlocfilehash: ab1a7b846bb35cce4656a3a5edf941961f5398c2
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394028"
---
# <a name="add-another-email-alias-for-a-user"></a>Aggiungere un altro alias di posta elettronica per un utente
  
Questo articolo è per Microsoft 365 amministratori che dispongono di abbonamenti aziendali. Non è destinato agli utenti privati.
  
Un indirizzo di posta elettronica principale in Microsoft 365 è in genere l'indirizzo di posta elettronica assegnato a un utente al momento della creazione dell'account. Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica. Possono inoltre avere più di un indirizzo di posta elettronica associato al proprio account Microsoft 365 per le aziende. Questi indirizzi aggiuntivi sono detti alias. 
  
Ad esempio, si supponga che Jenna abbia l'indirizzo di posta elettronica jenna@contosoco.com, ma che voglia anche ricevere posta elettronica all'indirizzo jen@contosoco.com perché alcune persone fanno riferimento a lei con quel nome. Puoi creare alias per lei in modo che entrambi gli indirizzi di posta elettronica vadano nella posta in arrivo di Jenna.
  
È possibile creare fino a 400 alias per utente. Non sono previsti ulteriori costi o licenze.
  
> [!Tip]
> Se si desidera che più persone gestino la posta elettronica inviata a un singolo indirizzo di posta elettronica info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa. Per ulteriori informazioni, vedere [Create a shared mailbox](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Aggiungere alias di posta elettronica a un utente

A tale [scopo, è necessario](../add-users/about-admin-roles.md) disporre delle autorizzazioni di amministratore. 

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **Utenti attivi** selezionare l'utente che > gestisci nome utente e **posta elettronica.** Questa opzione non verrà visualizzata se alla persona non è assegnata una licenza. 
    
3. Selezionare **+ Aggiungi un alias** e immettere un nuovo alias per l'utente.   
    
    > [!Important] 
    > Se viene visualizzato il messaggio di errore " Non è possibile trovare un parametro corrispondente al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
    
  
    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, vedere [Add a domain to Microsoft 365](../setup/add-domain.md). 
  
     
5. Al termine, scegliere **Salva modifiche**.
    
6. Attendere 24 ore che i nuovi alias si popolino in Microsoft 365.
    
    L'utente avrà ora un indirizzo principale e un alias. Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, *l'indirizzo From* dipende dal suo Outlook client. Outlook sul web verrà utilizzato l'alias con cui è stato ricevuto il messaggio di posta elettronica (verrà chiamato il principio ping-pong). Outlook desktop utilizzerà il suo alias di posta elettronica principale.** Si supponga, ad esempio, che un messaggio sia stato inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio usando Outlook desktop, l'indirizzo di posta elettronica principale verrà visualizzato come Eliza@NodPublishers.com, non Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>È stato visualizzato "Impossibile trovare un parametro corrispondente al nome del parametro EmailAddresses"?

Se viene visualizzato il messaggio di errore " Impossibile trovare un parametro corrispondente al nome del parametro **EmailAddresses**", significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>L'abbonamento è stato acquistato presso GoDaddy o un altro partner?


Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.

## <a name="sending-email-from-the-proxy-address-easily"></a>Inviare facilmente messaggi di posta elettronica dall'indirizzo proxy

A luglio 2021 viene lanciata una nuova funzionalità che consente agli utenti di inviare facilmente dagli alias quando usano Outlook sul web. Quando la funzionalità viene implementazione in una tenancy in cui l'amministratore tenant utilizza il cmdlet, gli utenti all'interno della tenancy avranno accesso a un elenco di caselle di controllo in cui ogni voce corrisponde a un alias nelle impostazioni di `Set-OrganizationConfig -SendFromAliasEnabled $true` Outlook. Se si seleziona un alias, l'alias verrà visualizzato nell'elenco a discesa Da del modulo Compose.
  
## <a name="related-content"></a>Contenuto correlato

[Inviare messaggi di posta elettronica da un indirizzo diverso](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (articolo)

[Modificare un nome utente e un indirizzo di posta elettronica](../add-users/change-a-user-name-and-email-address.md) (articolo)

[Configurare l'inoltro della posta elettronica in Microsoft 365](configure-email-forwarding.md) (articolo)
