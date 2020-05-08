---
title: Gestire le licenze di sottoscrizione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- SaRA
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 36081d8d-b3fa-4948-8c34-e217bba825e1
description: Informazioni su come aggiungere e rimuovere licenze per l'abbonamento a Microsoft 365 for business.
ms.openlocfilehash: f8ae177052be325673af96d9535f25dfcdc93180
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141234"
---
# <a name="manage-subscription-licenses"></a>Gestire le licenze di sottoscrizione

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione cambia. Se l'esperienza non corrisponde ai dettagli presentati, vedere [About The New Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

È possibile aggiungere o rimuovere licenze dagli abbonamenti utilizzando questi passaggi.

Non è possibile rimuovere una licenza da un abbonamento se è assegnata a un utente. Se si desidera rimuovere una licenza che è attualmente assegnata a un utente, è necessario [rimuovere le licenze dagli utenti](../../admin/manage/remove-licenses-from-users.md) prima di poter rimuovere la licenza dall'abbonamento.

## <a name="add-or-remove-licenses-for-your-business-subscription"></a>Aggiungere o rimuovere licenze per l'abbonamento aziendale

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione** \> dei <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .

2. Nella pagina i **prodotti** individuare la sottoscrizione a cui si desidera aggiungere o rimuovere le licenze, quindi selezionare **Aggiungi/Rimuovi licenze**.

    [Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Nella casella **Totale licenze** immettere il numero totale di licenze necessarie per l'abbonamento e quindi selezionare **Invia modifica**. Se, ad esempio, si hanno 100 licenze e occorre aggiungerne altre 5, immettere 105. Se si desidera rimuoverne 5, immettere 95.

Dopo aver acquistato nuove licenze, assicurarsi di [assegnare le licenze agli utenti](../../admin/manage/assign-licenses-to-users.md).

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.

2. Nella pagina **abbonamenti** selezionare l'abbonamento a cui si desidera aggiungere o rimuovere le licenze, quindi selezionare **Aggiungi/Rimuovi licenze**.

    [Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Nella casella **Totale licenze** immettere il numero totale di licenze necessarie per l'abbonamento e quindi fare clic su **Invia** \> **Chiudi**. Se, ad esempio, si hanno 100 licenze e occorre aggiungerne altre 5, immettere 105. Se si desidera rimuoverne 5, immettere 95.

Dopo aver acquistato nuove licenze, assicurarsi di [assegnare le licenze agli utenti](../../admin/manage/assign-licenses-to-users.md).

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.

2. Nella pagina **abbonamenti** selezionare l'abbonamento a cui si desidera aggiungere o rimuovere le licenze, quindi selezionare **Aggiungi/Rimuovi licenze**.

    [Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Nella casella **Totale licenze** immettere il numero totale di licenze necessarie per l'abbonamento e quindi fare clic su **Invia** \> **Chiudi**. Se, ad esempio, si hanno 100 licenze e occorre aggiungerne altre 5, immettere 105. Se si desidera rimuoverne 5, immettere 95.

Dopo aver acquistato nuove licenze, assicurarsi di [assegnare le licenze agli utenti](../../admin/manage/assign-licenses-to-users.md).

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>Cosa fare se il collegamento Aggiungi/rimuovi licenze non è presente?

In questa tabella vengono illustrati i motivi per cui il collegamento **Aggiungi/Rimuovi licenze** potrebbe non essere disponibile e cosa è possibile fare. 

|Motivo  |Descrizione  |Soluzione  |
|---------|---------|---------|
|La verifica del credito è in sospeso. |Se è in sospeso una verifica del credito, verrà visualizzato il messaggio "Verifica del credito in sospes"o e non sarà possibile acquistare licenze finché non viene completata.  | Tornare in seguito per verificare se la verifica del credito è stata completata. In genere sono necessari fino a due giorni lavorativi.<br>Una volta completata la verifica del credito, il collegamento **Aggiungi/rimuovi licenze** dovrebbe comparire nella sezione **Utenti**. In caso affermativo, andare a [gestire le licenze di sottoscrizione](#manage-subscription-licenses). |
|La sottoscrizione è stata attivata utilizzando un codice "Product Key".| Se l'abbonamento è stato acquistato e attivato usando un codice Product Key di 25 caratteri, verrà visualizzato il messaggio "Prepagato".  |Vedere [aggiungere licenze a un abbonamento pagato per l'utilizzo di un codice Product Key](add-licenses-using-product-key.md). |
|L'abbonamento è stato acquistato tramite un partner. | Se l'abbonamento è stato acquistato tramite un partner, verrà visualizzato il collegamento Volume Licensing Service Center (VLSC). | Vedere [aggiungere licenze a un abbonamento acquistato tramite il centro servizi per contratti multilicenza](add-licenses-bought-through-vlsc.md). |
|L'abbonamento è stato acquistato tramite un rivenditore.|| Se l'abbonamento è stato acquistato tramite un partner Cloud Solution Provider (CSP), per acquistare altre licenze è necessario rivolgersi al partner CSP.        |
|Si dispone di un abbonamento di valutazione. |Una versione di valutazione di Microsoft 365 visualizzerà il testo "Trial". | È necessario prima acquistare la sottoscrizione di valutazione, quindi è possibile aggiungere altre licenze. Vedere [acquistare un abbonamento a Microsoft 365 for business dalla versione di valutazione gratuita](../buy-a-subscription-from-your-free-trial.md).|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>Cosa è necessario sapere sull'acquisto di licenze per l'abbonamento aziendale

### <a name="buying-licenses"></a>Acquisto di licenze

- È necessario essere un amministratore globale o un amministratore di fatturazione per acquistare le licenze. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
- Per acquistare una licenza e aggiungere un nuovo utente all'abbonamento contemporaneamente, vedere [aggiungere utenti singolarmente o in blocco Microsoft 365-Guida per gli amministratori](../../admin/add-users/add-users.md).

### <a name="license-availability"></a>Disponibilità delle licenze

- Se il pagamento dell'abbonamento viene effettuato con carta di credito o conto corrente bancario, le nuove licenze acquistate sono disponibili subito dopo la ricezione della conferma dell'ordine. Se si sceglie il pagamento con fattura, potrebbe essere necessario attendere la verifica del credito prima che le nuove licenze siano disponibili.

  > [!NOTE]
  > Il pagamento tramite conto corrente bancario non è disponibile in alcuni paesi o aree geografiche.

- Se l'abbonamento è stato prepagato con un codice "Product Key", è possibile aggiungere altre licenze aggiungendo una carta di credito o un conto corrente bancario per coprire il costo aggiuntivo delle nuove licenze. Dopo avere acquistato le nuove licenze, viene aggiunto un secondo abbonamento con il numero di nuove licenze appena aggiunte. Ad esempio, se si ha un abbonamento prepagato con 5 licenze e se ne comprano altre 10, vengono elencati due abbonamenti: uno con cinque licenze prepagate e l'altro con le nuove 10 licenze.

### <a name="billing-statements"></a>Rendiconti di fatturazione

- Se si paga con carta di credito o conto corrente bancario, l'addebito per l'acquisto delle nuove licenze comparirà nella modalità di pagamento scelta in due giorni.
- Se si paga tramite fattura, l'addebito per l'acquisto delle nuove licenze comparirà nell'estratto conto successivo.
- Se si acquistano nuove licenze a metà del periodo di fatturazione, il primo estratto conto potrebbe mostrare un addebito parziale. L'importo rimanente verrà incluso nell'estratto conto successivo.

## <a name="related-articles"></a>Articoli correlati

[Informazioni su abbonamenti e licenze](subscriptions-and-licenses.md)

[Acquistare le licenze per l'abbonamento](buy-licenses.md)

[Acquistare un altro abbonamento](../buy-another-subscription.md)

[Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md)

[Gestire le licenze utente di Yammer](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)
