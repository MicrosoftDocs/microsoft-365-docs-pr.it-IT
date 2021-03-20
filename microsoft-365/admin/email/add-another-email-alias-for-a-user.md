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
description: "Informazioni su come è possibile associare più di un indirizzo di posta elettronica, denominato alias di posta elettronica, all'account di Microsoft 365 per le aziende. "
ms.openlocfilehash: 590782f7b22b1d26abef83f884d45da567f0425c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915951"
---
# <a name="add-another-email-alias-for-a-user"></a>Aggiungere un altro alias di posta elettronica per un utente

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end
  
Questo articolo è per gli amministratori di Microsoft 365 che hanno abbonamenti aziendali. Non è destinato agli utenti privati.
  
Un indirizzo di posta elettronica principale in Microsoft 365 è in genere l'indirizzo di posta elettronica assegnato a un utente al momento della creazione dell'account. Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica. Possono inoltre avere più di un indirizzo di posta elettronica associato al proprio account Microsoft 365 per le aziende. Questi indirizzi aggiuntivi sono detti alias. 
  
Ad esempio, si supponga che Jenna abbia l'indirizzo di posta elettronica jenna@contosoco.com, ma che voglia anche ricevere posta elettronica all'indirizzo jen@contosoco.com perché alcune persone fanno riferimento a lei con quel nome. Puoi creare alias per lei in modo che entrambi gli indirizzi di posta elettronica vadano nella posta in arrivo di Jenna.
<br><br>  
  
È possibile creare fino a 400 alias per utente. Non sono previsti ulteriori costi o licenze.
  
> [!Tip]
> Se si desidera che più persone gestino la posta elettronica inviata a un singolo indirizzo di posta elettronica info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa. Per ulteriori informazioni, vedere [Create a shared mailbox](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Aggiungere alias di posta elettronica a un utente
<a name="AddEmailPreview"> </a>

A tale [scopo, è necessario](../add-users/about-admin-roles.md) disporre delle autorizzazioni di amministratore. 

  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **Utenti attivi** selezionare l'utente > Gestisci alias di **posta elettronica**. Questa opzione non verrà visualizzata se alla persona non è assegnata una licenza. 
    
3. Selezionare **+ Aggiungi un alias** e immettere un nuovo alias per l'utente.   
    
    > [!Important] 
    > Se viene visualizzato il messaggio di errore " Non è possibile trovare un parametro corrispondente al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
    
  
    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](../setup/add-domain.md) 
  
     
5. Al termine, scegliere **Salva modifiche**.
    
6. Attendere 24 ore prima che i nuovi alias si popolino in Microsoft 365.
    
    L'utente avrà ora un indirizzo principale e un alias. Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, l'indirizzo *mittente*  sarà il suo alias di posta elettronica principale.** Si supponga, ad esempio, che un messaggio sia stato inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non come Sales@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>. 
    
    
2. Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.

3. Accanto a **Nome utente/Alias di posta elettronica** selezionare **Modifica.**

    > [!Important] 
    > Se viene visualizzato il messaggio di errore " Non è possibile trovare un parametro corrispondente al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.

4. Nella casella di testo in **Alias** digitare la prima parte del nuovo alias di posta elettronica. Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa. Selezionare **Aggiungi**.

    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](../setup/add-domain.md) 

5. Al termine, scegliere **Salva**.

6. Attendere 24 ore prima che i nuovi alias si popolino in Microsoft 365. 
    
    L'utente avrà ora un indirizzo principale e un alias. Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, l'indirizzo *mittente*  sarà il suo alias di posta elettronica principale.** Si supponga, ad esempio, che un messaggio sia stato inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non come Sales@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

    
2. Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.

3. Accanto a **Nome utente/Alias di posta elettronica** selezionare **Modifica.**

    > [!Important] 
    > Se viene visualizzato il messaggio di errore " Non è possibile trovare un parametro corrispondente al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.

4. Nella casella di testo in **Alias** digitare la prima parte del nuovo alias di posta elettronica. Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa. Selezionare **Aggiungi**.

    > [!IMPORTANT]
    > Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner. 
  
    > [!TIP]
    > L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa. Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](../setup/add-domain.md) 

5. Al termine, scegliere **Salva**.

6. Attendere 24 ore prima che i nuovi alias si popolino in Microsoft 365. 
    
    L'utente avrà ora un indirizzo principale e un alias. Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla posta in arrivo di Eliza.
    
  
7. **Quando l'utente risponde, l'indirizzo *mittente*  sarà il suo alias di posta elettronica principale.** Si supponga, ad esempio, che un messaggio sia stato inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza. Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non come Sales@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>È stato visualizzato "Impossibile trovare un parametro corrispondente al nome del parametro EmailAddresses"?


Se viene visualizzato il messaggio di errore " Impossibile trovare un parametro corrispondente al nome del parametro **EmailAddresses**", significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente. Per completare la configurazione possono essere necessarie fino a 4 ore. Attendere il tempo necessario per il completamento della procedura e quindi riprovare. Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>L'abbonamento è stato acquistato presso GoDaddy o un altro partner?


Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.
  
## <a name="related-articles"></a>Articoli correlati

[Inviare un messaggio di posta elettronica da un indirizzo diverso](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Cambiare un nome utente e un indirizzo di posta elettronica](../add-users/change-a-user-name-and-email-address.md)
