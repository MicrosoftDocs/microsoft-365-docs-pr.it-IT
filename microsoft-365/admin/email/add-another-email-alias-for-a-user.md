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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: "Informazioni su come avere più di un indirizzo di posta elettronica, denominato alias di posta elettronica, associato al Microsoft 365 per l'account aziendale. "
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572106"
---
# <a name="add-another-email-alias-for-a-user"></a>Aggiungere un altro alias di posta elettronica per un utente
  
Questo articolo è per Microsoft 365 amministratori che hanno abbonamenti aziendali. Non è destinato agli utenti privati.
  
Un indirizzo di posta elettronica principale in Microsoft 365 è in genere l'indirizzo di posta elettronica a cui è stato assegnato un utente al momento della creazione del proprio account. Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica. Possono anche avere più di un indirizzo e-mail associato al loro Microsoft 365 per l'account aziendale. Questi indirizzi aggiuntivi sono detti alias. 
  
Ad esempio, supponiamo che Jenna abbia l'indirizzo e-mail jenna@contosoco.com, ma vuole anche ricevere e-mail su jen@contosoco.com perché alcune persone si riferiscono a lei con quel nome. Puoi creare alias per lei in modo che entrambi gli indirizzi e-mail vadano nella posta in arrivo di Jenna.
  
È possibile creare fino a 400 alias per utente. Non sono previsti ulteriori costi o licenze.
  
> [!Tip]
> Se si desidera che più persone managee la posta elettronica inviata a un singolo indirizzo di posta elettronica info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa. Per ulteriori informazioni, vedere Creare [una cassetta postale condivisa](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Aggiungere alias di posta elettronica a un utente

Per eseguire questa [questa attività è necessario](../add-users/about-admin-roles.md) avere le autorizzazioni di amministratore. 

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **Utenti attivi selezionare** l'utente per > nome utente e la posta **elettronica**. Questa opzione non viene visualizzato se alla persona non è assegnata una licenza. 
    
3. Selezionare **+ Aggiungi alias e** immettere un nuovo alias per l'utente.   
    
    > [!Important] 
    > Se viene visualizzato il messaggio di errore "**Impossibile trovare un parametro che corrisponda al nome del parametro 'EmailAddresses**'", significa che ci vuole un po' più di tempo per completare la configurazione del tenant o del dominio personalizzato se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
    
  
    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, [vedere Aggiungere un dominio a Microsoft 365](../setup/add-domain.md). 
  
     
5. Al termine, scegliere Salva **modifiche**.
    
6. Attendere 24 ore affinché i nuovi alias si popolano in tutta Microsoft 365.
    
    L'utente avrà ora un indirizzo primario e un alias. Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla Posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, *l'indirizzo* Da dipenderà dal Outlook client. Outlook sul web utilizzerà l'alias in cui è stata ricevuta l'e-mail (lo chiameremo il principio del ping-pong). Outlook desktop utilizzerà il suo alias di posta elettronica principale.** Ad esempio, supponiamo che un messaggio sia inviato a Sales@NodPublishers.com e arrivi nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio utilizzando Outlook desktop, il suo indirizzo e-mail principale apparirà come Eliza@NodPublishers.com, non Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>È stato visualizzato "Impossibile trovare un parametro che corrisponda al nome del parametro EmailAddresses"?

Se viene visualizzato il messaggio di errore " Impossibile trovare un parametro che corrisponda al **nome del parametro EmailAddresses**", significa che ci vuole un po ' più di tempo per completare la configurazione del tenant o del dominio personalizzato se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>L'abbonamento è stato acquistato presso GoDaddy o un altro partner?


Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.

## <a name="sending-email-from-the-proxy-address-easily"></a>Inviare facilmente e-mail dall'indirizzo proxy

Una nuova funzionalità sarà disponibile ad aprile 2021 che consente agli utenti di inviare facilmente dai propri alias quando utilizzano Outlook sul Web. Quando la funzionalità viene eseguito a una tenancy in cui l'amministratore tenant utilizza il cmdlet, gli `Set-OrganizationConfig -SendFromAliasEnabled $true` utenti all'interno della tenancy avranno accesso a un elenco di caselle di controllo in cui ogni voce corrisponde a un alias nelle impostazioni Outlook. Selezionando un alias, questo verrà visualizzato nell'elenco a discesa Da del modulo Componi.
  
## <a name="related-content"></a>Contenuti correlati

[Inviare messaggi di posta elettronica da un indirizzo](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) diverso (articolo)

[Modificare un nome utente e un indirizzo di posta](../add-users/change-a-user-name-and-email-address.md) elettronica (articolo)

[Configurare l'inoltro della posta elettronica Microsoft 365](configure-email-forwarding.md) (articolo)
