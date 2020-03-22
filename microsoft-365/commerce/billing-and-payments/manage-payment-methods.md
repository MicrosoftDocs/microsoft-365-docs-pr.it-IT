---
title: Gestire metodi di pagamento
f1.keywords:
- CSH
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Informazioni su come gestire i metodi di pagamento nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 997b957bb28d32402e17eb855bc891ed07e5f27f
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894842"
---
# <a name="manage-payment-methods"></a>Gestire metodi di pagamento

Quando si acquistano prodotti o servizi aziendali da Microsoft, è possibile utilizzare un metodo di pagamento esistente oppure aggiungerne uno nuovo. È possibile utilizzare una carta di credito o di debito o un conto corrente bancario per pagare le operazioni acquistate. Tuttavia, è possibile gestire solo i metodi di pagamento aggiunti.

> [!NOTE]
> La possibilità di pagare con un conto corrente bancario non è disponibile in alcuni paesi o aree geografiche.
>
> È necessario utilizzare un metodo di pagamento emesso dallo stesso paese del tenant.

## <a name="add-a-payment-method"></a>Aggiungere un metodo di pagamento

L'aggiunta di un metodo di pagamento non associa gli abbonamenti. Per assegnare una singola sottoscrizione al metodo di pagamento, vedere [modificare un metodo di pagamento per una singola sottoscrizione](#change-a-payment-method-for-a-single-subscription). Per sostituire tutte le sottoscrizioni che utilizzano un altro metodo di pagamento con quello nuovo, vedere [Replace a Payment Method](#replace-a-payment-method).

1. Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">metodi di pagamento</a> per la **fatturazione** > **& pagamenti** > .
2. Selezionare **Aggiungere una modalità di pagamento**.
3. Nella pagina **Modalità di pagamento** scegliere una modalità di pagamento dal menu a discesa.
4. Immettere le informazioni per la nuova scheda o il conto corrente bancario, quindi selezionare **Aggiungi**.

## <a name="update-payment-method-details"></a>Aggiornare i dettagli del metodo di pagamento

È possibile modificare il nome sulla carta di credito o di debito, l'indirizzo di fatturazione o la data di scadenza di un metodo di pagamento esistente. Tuttavia, non è possibile modificare il numero di carta o di account. Se il numero dell'account è stato modificato, [sostituirlo con un metodo di pagamento diverso](#replace-a-payment-method), quindi [eliminare quello precedente](#delete-a-payment-method).

1. Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">metodi di pagamento</a> per la **fatturazione** > **& pagamenti** > .
2. Selezionare la riga del metodo di pagamento da aggiornare. Nel riquadro a destra, selezionare **modifica**.
3. Aggiornare le informazioni sul metodo di pagamento (nome sulla carta di credito o di debito, l'indirizzo di fatturazione o la data di scadenza), quindi selezionare **Salva**.

## <a name="replace-a-payment-method"></a>Sostituire un metodo di pagamento

Quando si sostituisce un metodo di pagamento, è necessario sostituirlo per tutte le sottoscrizioni e i profili di fatturazione che utilizzano lo stesso metodo di pagamento. La sostituzione di un metodo di pagamento non comporta l'eliminazione del metodo di pagamento esistente. È ancora disponibile per la selezione e l'utilizzo di altri abbonamenti e profili di fatturazione.

Per modificare il metodo di pagamento per una singola sottoscrizione, vedere [modificare un metodo di pagamento per una singola sottoscrizione](#change-a-payment-method-for-a-single-subscription).

1. Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">metodi di pagamento</a> per la **fatturazione** > **& pagamenti** > .
2. Selezionare la riga del metodo di pagamento da sostituire. Nel riquadro destro sono elencati tutti i profili di fatturazione e i singoli abbonamenti che utilizzano il metodo di pagamento selezionato.
3. Nel riquadro a destra, selezionare **Sostituisci metodo di pagamento per tutti gli elementi**.
4. Per utilizzare un metodo di pagamento esistente, sceglierne uno dall'elenco a discesa, quindi selezionare **Sostituisci**.
    > [!NOTE]
    > Se si dispone di abbonamenti associati a un profilo di fatturazione, è possibile utilizzare solo una carta di credito o di debito per pagarli. Se si dispone di account bancari elencati nella pagina **metodi di pagamento** , non sono disponibili per la selezione nell'elenco a discesa.
5. Per aggiungere un nuovo metodo di pagamento, selezionare **Aggiungi metodo di pagamento**.
6. Nel riquadro **Aggiungi un metodo di pagamento** , immettere le informazioni sull'account, quindi selezionare **Salva**. È necessario utilizzare un metodo di pagamento proveniente dallo stesso paese del tenant.
7. Il nuovo metodo di pagamento è già selezionato nell'elenco a discesa. Selezionare **Sostituisci**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Modificare un metodo di pagamento per un singolo abbonamento

È possibile modificare il metodo di pagamento utilizzato per pagare un singolo abbonamento.

1. Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">servizi di &</a> di **fatturazione** > .
2. Nella scheda **abbonamenti** selezionare l'abbonamento che si desidera pagare con il metodo di pagamento alternativo. 
3. In **fatturazione**, fare clic su **modifica**accanto al metodo di pagamento.
4. Accanto al metodo di pagamento esistente, selezionare **Cambia**.
5. Nell'elenco a discesa scegliere un metodo di pagamento alternativo oppure scegliere di aggiungere un metodo di pagamento.
6. Se si aggiunge un metodo di pagamento, immettere la scheda o i dettagli dell'account, quindi fare clic su **Salva**.
7. Verificare che il metodo di pagamento selezionato sia corretto, quindi selezionare **Salva**.

## <a name="delete-a-payment-method"></a>Eliminare un metodo di pagamento

È possibile eliminare solo un metodo di pagamento che non è collegato a un abbonamento o a un profilo di fatturazione. Questo vale per tutte le sottoscrizioni, indipendentemente dallo stato.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Eliminare un metodo di pagamento senza abbonamenti o profili di fatturazione associati

Se un metodo di pagamento non è associato ad alcun abbonamento o profilo di fatturazione, è possibile eliminarlo immediatamente.

1. Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">metodi di pagamento</a> per la **fatturazione** > **& pagamenti** > .
2. Trovare il metodo di pagamento da eliminare, selezionare i tre punti, quindi selezionare **Elimina**.
3. Nella parte inferiore del riquadro destro fare clic su **Elimina**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Eliminare un metodo di pagamento con abbonamenti o profili di fatturazione associati

Se un metodo di pagamento è collegato a qualsiasi sottoscrizione o profilo di fatturazione, sostituirlo con un metodo di pagamento esistente oppure aggiungerne uno nuovo, quindi eliminare il vecchio metodo di pagamento.

1. Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">metodi di pagamento</a> per la **fatturazione** > **& pagamenti** > .
2. Selezionare la riga per il metodo di pagamento da eliminare. Nel riquadro destro sono elencate le sottoscrizioni esistenti che utilizzano il metodo di pagamento.
3. Nel riquadro a destra, selezionare **Elimina**.
4. Per utilizzare un metodo di pagamento esistente, selezionarlo nell'elenco a discesa, selezionare **Avanti**, quindi selezionare **Elimina**.
    > [!NOTE]
    > Se si dispone di abbonamenti associati a un profilo di fatturazione, è possibile utilizzare solo una carta di credito per pagarli. Se si dispone di account bancari elencati nella pagina **metodi di pagamento** , non sono disponibili per la scelta nell'elenco a discesa.
5. Per aggiungere un nuovo metodo di pagamento, selezionare **Aggiungi metodo di pagamento**.
6. Scegliere il tipo di metodo di pagamento che si desidera aggiungere, immettere le informazioni dell'account e quindi fare clic su **Salva**.
7. Il nuovo metodo di pagamento è già selezionato nell'elenco a discesa. Selezionare **Avanti**.
8. Selezionare **Elimina**.

## <a name="troubleshoot-payment-methods"></a>Risoluzione dei problemi relativi ai metodi di pagamento

|**Problema**|**Procedure per la risoluzione dei problemi**|
|:----------|:-----|
|**Viene visualizzato un messaggio di errore che indica che il browser è attualmente impostato per bloccare i cookie.** |Impostare il browser in modo da accettare i cookie di terze parti e riprovare. |
|**La carta di credito o di debito è stata rifiutata.** |Se si paga con carta di credito o di debito e la scheda viene rifiutata, viene visualizzato un messaggio di posta elettronica che indica che Microsoft non è stato in grado di elaborare il pagamento. Verificare che il numero di carta dei &mdash; dettagli della scheda, la data di scadenza, il nome della scheda e l'indirizzo, tra cui la città, lo stato e il codice postale, vengano visualizzati esattamente come nella scheda e nell'istruzione. È possibile aggiornare le informazioni sulla scheda e inoltrare immediatamente il pagamento utilizzando il collegamento **Risolvi saldo** nella sezione **fatturazione** della pagina Dettagli sottoscrizione. Per ulteriori informazioni, vedere [cosa succede se la carta di credito è stata rifiutata e il pagamento è scaduto?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  Se si continua a visualizzare il messaggio "rifiutato", contattare la propria banca. È possibile che la scheda non sia attiva. Se la scheda è stata ricevuta di recente nella posta con una data di scadenza aggiornata, assicurarsi che sia attivata. La banca può anche indicare se la scheda non è stata approvata per transazioni online, internazionali o ricorrenti. |
|**Si desidera aggiornare una scheda o un numero di conto corrente bancario.** |Non è possibile modificare il numero di carta o di account su un metodo di pagamento esistente. Se la scheda o il numero di account è stato modificato, [sostituirlo con un metodo di pagamento diverso](#replace-a-payment-method), che sposta tutti gli abbonamenti attivi dal metodo di pagamento a quello nuovo, quindi [eliminare il vecchio metodo di pagamento](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Ho solo una carta o un conto corrente bancario sul mio account e lo si desidera rimuovere.** |Se si dispone di un solo metodo di pagamento, è necessario [sostituirlo con un nuovo metodo di pagamento prima di](#replace-a-payment-method) eliminarlo. |
|**Non è possibile aggiungere la scheda o il conto corrente bancario.**  |È necessario utilizzare un metodo di pagamento emesso dallo stesso paese del tenant. In caso di problemi nell'immissione delle informazioni sulla carta o sul conto corrente bancario, è possibile [contattare il supporto tecnico](../../admin/contact-support-for-business-products.md). |

## <a name="related-articles"></a>Articoli correlati

[Pagare l'abbonamento per le aziende](pay-for-your-subscription.md)

[Gestire profili di fatturazione](manage-billing-profiles.md)

[Modificare la frequenza di pagamento](change-payment-frequency.md)