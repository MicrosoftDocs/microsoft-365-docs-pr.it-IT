---
title: Gestire le modalità di pagamento
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
ms.reviewer: jamitche
search.appverid:
- MET150
description: Informazioni su come gestire le modalità di pagamento nell'interfaccia di amministrazione di Microsoft 365.
ms.date: 04/02/2021
ms.openlocfilehash: 82b2880eed830bd3b65cce14635c4fa10f618740
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297369"
---
# <a name="manage-payment-methods"></a>Gestire le modalità di pagamento

> [!IMPORTANT]
> A partire dal 26 gennaio 2021 i nuovi conti correnti bancari non sono più supportati per i clienti in Belgio, Francia, Italia, Lussemburgo, Portogallo, Spagna e Stati Uniti. I clienti esistenti in uno di questi paesi/aree geografiche possono continuare a pagare l'abbonamento con un conto corrente bancario esistente e aggiungervi nuovi abbonamenti, ma solo fino a quando il conto corrente bancario è in regola.

Quando si acquistano prodotti o servizi aziendali da Microsoft, è possibile usare una modalità di pagamento esistente o aggiungerne una nuova. Per pagare gli acquisti, è possibile usare una carta di credito o di debito oppure un conto corrente bancario.

Se l'account aziendale ha un profilo di fatturazione e si è il proprietario o un collaboratore del profilo di fatturazione, è possibile usare il profilo di fatturazione associato al pagamento tramite carta di credito o fattura per effettuare acquisti o pagare fatture. I responsabili della fatturazione possono usare un profilo di fatturazione solo per pagare le fatture. Per altre informazioni sui profili e sui ruoli di fatturazione, vedere [Gestire i profili di fatturazione](manage-billing-profiles.md).

Se l'account aziendale non ha un profilo di fatturazione, qualsiasi amministratore globale o di fatturazione può gestire e usare qualsiasi conto corrente bancario aggiunto all'account aziendale. È in ogni caso possibile gestire o usare solo le carte di credito aggiunte personalmente.

> [!NOTE]
> L’opzione di pagamento tramite conto corrente bancario non è disponibile in alcuni paesi o aree geografiche.
>
> È necessario usare una modalità di pagamento emessa dallo stesso paese/area geografica del tenant.

## <a name="before-you-begin"></a>Prima di iniziare

È necessario essere un amministratore globale o un amministratore di fatturazione per eseguire le procedure descritte in questo articolo. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Aggiungere una modalità di pagamento

L'aggiunta di una modalità di pagamento non associa alcun abbonamento ad essa. Per assegnare un singolo abbonamento alla modalità di pagamento, vedere [Cambiare la modalità di pagamento per un singolo abbonamento](#change-a-payment-method-for-a-single-subscription). Per sostituire tutti gli abbonamenti che usano un’altra modalità di pagamento con quella nuova, vedere [Sostituire una modalità di pagamento](#replace-a-payment-method).

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare **Aggiungere una modalità di pagamento**.
3. Nella pagina **Modalità di pagamento** scegliere una modalità di pagamento dal menu a discesa.
4. Immettere le informazioni della nuova carta o del nuovo conto corrente bancario e selezionare **Aggiungi**.

## <a name="update-payment-method-details"></a>Aggiornare i dettagli della modalità di pagamento

È possibile cambiare il nome riportato sulla carta di credito o di debito, nell'indirizzo di fatturazione o nella data di scadenza di una modalità di pagamento esistente. Tuttavia, non è possibile cambiare il numero della carta o del conto. Se il numero di conto è cambiato, [sostituirlo con una modalità di pagamento diversa](#replace-a-payment-method), quindi [eliminare quella precedente](#delete-a-payment-method).

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare la riga del metodo di pagamento da aggiornare. Nel riquadro destro, selezionare **Modifica**.
3. Aggiornare le informazioni sul metodo di pagamento, inclusi il nome sulla carta di credito o di debito, l'indirizzo di fatturazione o la data di scadenza e quindi selezionare **Salva**.

## <a name="replace-a-payment-method"></a>Sostituire una modalità di pagamento

Quando si sostituisce una modalità di pagamento, la si sostituisce per tutti gli abbonamenti e i profili di fatturazione che usano la stessa modalità di pagamento. La sostituzione di una modalità di pagamento non elimina quella esistente. È ancora possibile selezionarla e usarla per altri abbonamenti e profili di fatturazione.

Per cambiare la modalità di pagamento per un singolo abbonamento, vedere [Cambiare la modalità di pagamento per un singolo abbonamento](#change-a-payment-method-for-a-single-subscription).

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare la riga della modalità di pagamento da sostituire. Nel riquadro destro sono elencati tutti i profili di fatturazione e i singoli abbonamenti che usano la modalità di pagamento selezionata.
3. Nel riquadro destro selezionare **Sostituisci metodo di pagamento per tutti gli articoli**.
4. Per usare una modalità di pagamento esistente, sceglierne una nell'elenco a discesa, quindi selezionare **Sostituisci**.
    > [!NOTE]
    > Se si hanno abbonamenti associati a un profilo di fatturazione, si può usare solo una carta di credito o di debito per il pagamento. Se nella pagina **Modalità di pagamento** sono elencati conti bancari, non sono disponibili per la selezione nell'elenco a discesa.
5. Per aggiungere una nuova modalità di pagamento, selezionare **Aggiungi modalità di pagamento**.
6. Nel riquadro **Aggiungi un metodo di pagamento** immetti le informazioni sull'account e scegli **Salva**. È necessario usare una modalità di pagamento dello stesso paese/area geografica del tenant.
7. La nuova modalità di pagamento è già selezionata nell'elenco a discesa. Selezionare **Sostituisci**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Cambiare la modalità di pagamento per un singolo abbonamento

È possibile cambiare la modalità di pagamento usata per pagare un singolo abbonamento.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** trovare l'abbonamento che si vuole pagare con la modalità di pagamento alternativo.
3. Selezionare **Altre azioni** (tre puntini), quindi selezionare **Sostituisci metodo di pagamento**.
4. Nel riquadro **Sostituisci metodo di pagamento** scegliere una modalità di pagamento alternativa nell'elenco a discesa oppure scegliere di aggiungere una modalità di pagamento.
5. Se si aggiunge una modalità di pagamento, immettere i dettagli della carta o del conto, quindi selezionare **Salva**.
6. Verificare che la modalità di pagamento selezionata sia corretta, quindi scegliere **Sostituisci**.

## <a name="delete-a-payment-method"></a>Eliminare una modalità di pagamento

È possibile eliminare solo una modalità di pagamento non associata a un abbonamento o a un profilo di fatturazione. Questo vale per tutti gli abbonamenti, indipendentemente dal loro stato.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Eliminare una modalità di pagamento senza abbonamenti o profili di fatturazione associati

Se la modalità di pagamento non è associata ad alcun abbonamento o profilo di fatturazione, è possibile eliminarla immediatamente.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Trovare la modalità di pagamento da eliminare, selezionare i tre puntini e quindi **Elimina**.
3. Nella parte inferiore del riquadro selezionare **Elimina**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Eliminare una modalità di pagamento con abbonamenti o profili di fatturazione associati

Se a un abbonamento o un profilo di fatturazione è associata una modalità di pagamento, sostituirla prima con una modalità di pagamento esistente oppure aggiungerne una nuova, quindi eliminare la vecchia modalità di pagamento.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > **Fatture e pagamenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Modalità di pagamento</a>.
2. Selezionare la riga della modalità di pagamento da eliminare. Il riquadro destro elenca gli abbonamenti esistenti che usano questa modalità di pagamento.
3. Nel riquadro destro, selezionare **Elimina**.
4. Per usare una modalità di pagamento esistente, sceglierne una nell'elenco a discesa, selezionare **Avanti**, quindi selezionare **Elimina**.
    > [!NOTE]
    > Se si hanno abbonamenti associati a un profilo di fatturazione, si può usare solo una carta di credito per il pagamento. Se nella pagina **Modalità di pagamento** sono elencati conti bancari, non è possibile sceglierli nell'elenco a discesa.
5. Per aggiungere una nuova modalità di pagamento, selezionare **Aggiungi metodo di pagamento**.
6. Scegliere il tipo di modalità di pagamento che si vuole aggiungere, immettere le informazioni sull'account e quindi selezionare **Salva**.
7. La nuova modalità di pagamento è già selezionata nell'elenco a discesa. Selezionare **Avanti**.
8. Selezionare **Elimina**.

## <a name="troubleshoot-payment-methods"></a>Risoluzione dei problemi relativi alle modalità di pagamento

| Problema | Procedura di risoluzione dei problemi |
|:----------|:-----|
|**Viene visualizzato un messaggio di errore che avvisa che il browser è impostato per bloccare i cookie.** |Impostare il browser in modo da accettare i cookie di terze parti e riprovare. |
|**La carta di credito/debito è stata rifiutata.** |Se si paga con carta di credito o debito e questa viene rifiutata, si riceve un messaggio di posta elettronica che informa che Microsoft non è riuscita a elaborare il pagamento. Controllare che i dettagli della carta &mdash; ossia numero, data di scadenza, nome sulla carta e indirizzo comprensivo di città, stato e codice postale &mdash; corrispondano esattamente a quelli sulla carta e sul relativo estratto conto. È possibile aggiornare le informazioni della carta e inviare immediatamente il pagamento usando il collegamento per **pagare il saldo** nella sezione **Fatturazione** della pagina dei dettagli dell'abbonamento. Per altre informazioni, vedere [Cosa devo fare se il mio saldo è insoluto?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Se si continua a ricevere il messaggio di rifiuto, contattare la propria banca. È possibile che la carta di credito non sia attiva. Se di recente si è ricevuta per posta la carta con una data di scadenza aggiornata, verificare che sia stata attivata. Rivolgersi alla banca anche per sapere se la carta di credito non è approvata per transazioni online, internazionali o ricorrenti. |
|**Come aggiornare il numero della carta di credito o del conto corrente bancario?** |Non è possibile cambiare il numero di carta di credito o di conto corrente bancario in una modalità di pagamento esistente. Se il numero della carta o del conto è cambiato, [sostituirla con una modalità di pagamento diversa](#replace-a-payment-method), spostando tutti gli abbonamenti attivi dalla modalità di pagamento precedente a quella nuova, quindi [eliminare la vecchia modalità di pagamento](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**All'account è associata una sola carta di credito o un solo conto corrente bancario e si vuole rimuoverlo.** |Se si ha una sola modalità di pagamento, è necessario [sostituirla con una nuova](#replace-a-payment-method) per poterla eliminare. |
|**Non si riesce ad aggiungere la carta o il conto corrente bancario.**  |È necessario usare una modalità di pagamento emessa dallo stesso paese/area geografica del tenant. Se si riscontrano problemi durante l'immissione delle informazioni della carta o del conto corrente bancario, è possibile [contattare il supporto](../../business-video/get-help-support.md). |

## <a name="related-content"></a>Contenuti correlati

[Pagare l'abbonamento per le aziende](pay-for-your-subscription.md) (articolo)\
[Gestire i profili di fatturazione](manage-billing-profiles.md) (articolo)\
[Cambiare la frequenza di fatturazione](change-payment-frequency.md) (articolo)