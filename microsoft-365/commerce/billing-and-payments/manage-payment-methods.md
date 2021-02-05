---
title: Gestire metodi di pagamento
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Informazioni su come gestire i metodi di pagamento nell'interfaccia di amministrazione di Microsoft 365.
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114850"
---
# <a name="manage-payment-methods"></a>Gestire metodi di pagamento

::: moniker range="o365-21vianet"
> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).
::: moniker-end

Quando si acquistano prodotti o servizi aziendali da Microsoft, è possibile utilizzare una modalità di pagamento esistente o aggiungerne una nuova. Puoi usare una carta di credito o di debito o un conto corrente bancario per pagare gli elementi acquistati.

Se l'account aziendale ha un profilo di fatturazione e sei il proprietario o il collaboratore del profilo di fatturazione, puoi usare il profilo di fatturazione supportato da una carta di credito o un pagamento tramite fattura per effettuare acquisti o pagare fatture. Se sei un responsabile delle fatture, puoi usare solo un profilo di fatturazione per pagare le fatture. Per ulteriori informazioni sui profili di fatturazione e sui ruoli, vedere [Gestire i profili di fatturazione.](manage-billing-profiles.md)

Se l'account aziendale non dispone di un profilo di fatturazione, qualsiasi amministratore globale o di fatturazione può gestire e usare qualsiasi conto bancario aggiunto al conto aziendale. Tuttavia, è possibile gestire o utilizzare solo le carte di credito che si aggiungono.

> [!NOTE]
> L'opzione per pagare con un conto corrente bancario non è disponibile in alcuni paesi o aree geografiche.
>
> È necessario utilizzare una modalità di pagamento emessa dallo stesso paese del tenant.

## <a name="before-you-begin"></a>Prima di iniziare

Per eseguire le attività in questo articolo, è necessario essere un amministratore globale o di fatturazione. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Aggiungere una modalità di pagamento

L'aggiunta di una modalità di pagamento non ne associa alcuna sottoscrizione. Per assegnare una singola sottoscrizione alla modalità di pagamento, vedere [Modificare una modalità di pagamento per una singola sottoscrizione.](#change-a-payment-method-for-a-single-subscription) Per sostituire tutte le sottoscrizioni che usano un'altra modalità di pagamento con quella nuova, vedere [Sostituire una modalità di pagamento.](#replace-a-payment-method)

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare **Aggiungere una modalità di pagamento**.
3. Nella pagina **Modalità di pagamento** scegliere una modalità di pagamento dal menu a discesa.
4. Immetti le informazioni per la nuova carta o il nuovo conto corrente bancario, quindi seleziona **Aggiungi.**

## <a name="update-payment-method-details"></a>Aggiornare i dettagli della modalità di pagamento

Puoi modificare il nome sulla carta di credito o di debito, sull'indirizzo di fatturazione o sulla data di scadenza per una modalità di pagamento esistente. Tuttavia, non è possibile modificare il numero della carta o dell'account. Se il numero di conto è stato modificato, [sostituirlo con un metodo di](#replace-a-payment-method)pagamento diverso e quindi eliminare quello [precedente.](#delete-a-payment-method)

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare la riga del metodo di pagamento da aggiornare. Nel riquadro destro, selezionare **Modifica**.
3. Aggiornare le informazioni sul metodo di pagamento, inclusi il nome sulla carta di credito o di debito, l'indirizzo di fatturazione o la data di scadenza e quindi selezionare **Salva**.

## <a name="replace-a-payment-method"></a>Sostituire una modalità di pagamento

Quando si sostituisce una modalità di pagamento, questa viene sostituita per tutte le sottoscrizioni e i profili di fatturazione che utilizzano la stessa modalità di pagamento. La sostituzione di una modalità di pagamento non elimina la modalità di pagamento esistente. È ancora disponibile per la selezione e l'uso per altri abbonamenti e profili di fatturazione.

Per modificare la modalità di pagamento per un singolo abbonamento, vedere [Modificare una modalità di pagamento per una singola sottoscrizione.](#change-a-payment-method-for-a-single-subscription)

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare la riga della modalità di pagamento da sostituire. Nel riquadro destro sono elencati tutti i profili di fatturazione e i singoli abbonamenti che usano la modalità di pagamento selezionata.
3. Nel riquadro destro selezionare **Sostituisci metodo di pagamento per tutti gli articoli**.
4. Per usare una modalità di pagamento esistente, sceglierne una nell'elenco a discesa, quindi selezionare **Sostituisci**.
    > [!NOTE]
    > Se si hanno abbonamenti associati a un profilo di fatturazione, si può usare solo una carta di credito o di debito per il pagamento. Se nella pagina **Modalità di pagamento** sono elencati conti bancari, non sono disponibili per la selezione nell'elenco a discesa.
5. Per aggiungere una nuova modalità di pagamento, selezionare **Aggiungi modalità di pagamento**.
6. Nel riquadro **Aggiungi un metodo di pagamento** immetti le informazioni sull'account e scegli **Salva**. È necessario usare una modalità di pagamento dello stesso paese/area geografica del tenant.
7. La nuova modalità di pagamento è già selezionata nell'elenco a discesa. Selezionare **Sostituisci**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Modificare una modalità di pagamento per un singolo abbonamento

È possibile modificare la modalità di pagamento utilizzata per pagare un singolo abbonamento.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** individuare l'abbonamento che si desidera pagare con la modalità di pagamento alternativa.
3. Seleziona **Altre azioni** (tre puntini), quindi seleziona Sostituisci metodo di **pagamento.**
4. Nel riquadro **Sostituisci metodo di pagamento,** nell'elenco a discesa, scegliere una modalità di pagamento alternativa oppure scegliere di aggiungere una modalità di pagamento.
5. Se aggiungi una modalità di pagamento, immetti i dettagli della carta o dell'account, quindi seleziona **Salva.**
6. Verifica che la modalità di pagamento selezionata sia corretta, quindi seleziona **Sostituisci.**

## <a name="delete-a-payment-method"></a>Eliminare una modalità di pagamento

Puoi eliminare solo una modalità di pagamento non collegata a un abbonamento o a un profilo di fatturazione. Questo vale per tutte le sottoscrizioni, indipendentemente dal loro stato.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Eliminare una modalità di pagamento senza sottoscrizioni o profili di fatturazione collegati

Se una modalità di pagamento non è associata ad alcun abbonamento o profilo di fatturazione, puoi eliminarla immediatamente.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Trova la modalità di pagamento da eliminare, seleziona i tre puntini, quindi seleziona **Elimina.**
3. Nella parte inferiore del riquadro destro selezionare **Elimina.**

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Eliminare una modalità di pagamento con sottoscrizioni o profili di fatturazione collegati

Se una modalità di pagamento è collegata a qualsiasi sottoscrizione o profilo di fatturazione, è necessario innanzitutto sostituirla con una modalità di pagamento esistente o aggiungerne una nuova, quindi eliminare la modalità di pagamento precedente.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare la riga per la modalità di pagamento da eliminare. Nel riquadro destro sono elencate le sottoscrizioni esistenti che utilizzano tale modalità di pagamento.
3. Nel riquadro destro selezionare **Elimina.**
4. Per usare una modalità di pagamento esistente, selezionarne una nell'elenco a discesa, selezionare **Avanti** e quindi **Elimina.**
    > [!NOTE]
    > Se sono state associate sottoscrizioni a un profilo di fatturazione, è possibile utilizzare solo una carta di credito per il pagamento. Se nella pagina Modalità  di pagamento sono elencati conti bancari, non sono disponibili per la scelta nell'elenco a discesa.
5. Per aggiungere una nuova modalità di pagamento, selezionare **Aggiungi modalità di pagamento**.
6. Scegliere il tipo di metodo di pagamento che si desidera aggiungere, immettere le informazioni sull'account e quindi selezionare **Salva.**
7. La nuova modalità di pagamento è già selezionata nell'elenco a discesa. Selezionare **Avanti**.
8. Selezionare **Elimina**.

## <a name="troubleshoot-payment-methods"></a>Risoluzione dei problemi relativi alle modalità di pagamento

| Problema | Procedura di risoluzione dei problemi |
|:----------|:-----|
|**Viene visualizzato un messaggio di errore che indica che il browser è attualmente impostato per bloccare i cookie.** |Impostare il browser in modo da accettare i cookie di terze parti e riprovare. |
|**La carta di credito o di debito è stata rifiutata.** |Se si paga con carta di credito o di debito e la carta viene rifiutata, si riceve un messaggio di posta elettronica che indica che Microsoft non è stato in grado di elaborare il pagamento. Verifica che il numero della scheda dei dettagli della carta, la data di scadenza, il nome sulla scheda e l'indirizzo, tra cui città, stato e CAP, vengano visualizzati esattamente come nella scheda e &mdash; &mdash; nell'estratto conto. È possibile aggiornare le informazioni della carta e inviare immediatamente il pagamento utilizzando il **collegamento** Liquidazione saldo nella **sezione Fatturazione** della pagina dei dettagli dell'abbonamento. Per ulteriori informazioni, vedere [Cosa succede se si dispone di un saldo in sospeso?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  If you continue to see the "declined" message, contact your bank. È possibile che la carta non sia attiva. Se la scheda è stata ricevuta di recente nel messaggio di posta elettronica con una data di scadenza aggiornata, assicurarsi che sia attivata. La tua banca può anche indicare se la carta non è approvata per transazioni online, internazionali o ricorrenti. |
|**Si desidera aggiornare un numero di carta o di conto corrente bancario.** |Non è possibile modificare il numero di carta o di conto in una modalità di pagamento esistente. Se il numero di carta o di conto è [cambiato,](#replace-a-payment-method)sostituirlo con un metodo di pagamento diverso, che sposta tutte le sottoscrizioni attive dalla modalità di pagamento a quella nuova, quindi eliminare la vecchia [modalità di pagamento.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached) |
|**Ho solo una carta o un conto corrente bancario sul mio account e voglio rimuoverlo.** |Se hai un solo metodo di pagamento, devi [sostituirlo](#replace-a-payment-method) con un nuovo metodo di pagamento prima di poterlo eliminare. |
|**Non è possibile aggiungere la carta di credito o il conto corrente bancario.**  |È necessario utilizzare una modalità di pagamento emessa dallo stesso paese del tenant. In caso di problemi durante l'immissione delle informazioni sulla carta o sul conto corrente bancario, è possibile [contattare il supporto tecnico.](../../admin/contact-support-for-business-products.md) |

## <a name="related-content"></a>Contenuti correlati

[Pagare l'abbonamento aziendale](pay-for-your-subscription.md) (articolo)\
[Gestire i profili di fatturazione](manage-billing-profiles.md) (articolo)\
[Modificare la frequenza di fatturazione](change-payment-frequency.md) (articolo)
