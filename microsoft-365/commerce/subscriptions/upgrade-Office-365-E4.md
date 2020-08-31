---
title: Eseguire l'aggiornamento da un abbonamento a Office 365 E4
f1.keywords:
- NOCSH
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
- Adm_NonTOC
- commerce
ms.custom: customer-email
search.appverid:
- MET150
description: Informazioni su come eseguire l'aggiornamento da un abbonamento a Office 365 E4.
ms.date: 08/14/2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2587732a6c4092dcb7b53daf9493e7cee2f1987c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308006"
---
# <a name="upgrade-from-an-office-365-e4-subscription"></a>Eseguire l'aggiornamento da un abbonamento a Office 365 E4

In questo articolo vengono illustrati i passaggi del processo di aggiornamento da un Office 365 E4 a un nuovo abbonamento. Per informazioni sulle opzioni disponibili quando si effettua l'aggiornamento da Office 365 E4, vedere [informazioni importanti per i clienti di office 365 E4](important-information-e4.md).

> [!IMPORTANT]
> Questo articolo si applica agli abbonamenti di Office 365 E4 che sono stati acquistati direttamente da Microsoft tramite carta di credito o solo fattura. Se l'abbonamento è stato acquistato in un altro modo, ad esempio tramite un partner o tramite il centro servizi per contratti multilicenza, contattare il rappresentante o il partner dell'account Microsoft per agevolare l'aggiornamento dei piani.

## <a name="what-are-my-options-for-how-to-upgrade"></a>Quali sono le opzioni per l'aggiornamento?

Il modo più semplice per eseguire l'aggiornamento del piano consiste nell'utilizzare la scheda **aggiornamento** nell'interfaccia di amministrazione di Microsoft 365. Tuttavia, l'utilizzo della scheda **aggiornamento** non è supportato in tutte le situazioni. Se lo scenario non è supportato, potrebbe essere possibile eseguire l'aggiornamento manuale dei piani.

## <a name="what-is-the-upgrade-tab"></a>Che cos'è la scheda aggiornamento?

Nella scheda **aggiornamento** vengono eseguite le attività seguenti:

- Vengono illustrati i passaggi del processo di acquisto di un nuovo piano.
- Tutte le licenze utente del vecchio piano vengono assegnate a quelle nuove.
- Il vecchio piano viene annullato.

## <a name="what-does-it-mean-to-upgrade-plans-manually"></a>Cosa significa aggiornare manualmente i piani?

L'aggiornamento dei piani comporta manualmente il completamento delle procedure separate, invece di usare la scheda **upgrade** .

- Acquistare un nuovo abbonamento con il numero appropriato di licenze.
- Verificare che il nuovo abbonamento sia pronto per l'uso.
- Riassegnare le licenze agli utenti.
- Annullare l'abbonamento a Office 365 E4 originale.

## <a name="find-out-if-you-can-use-the-upgrade-tab-to-upgrade-to-a-new-plan"></a>Scoprire se è possibile utilizzare la scheda aggiornamento per eseguire l'aggiornamento a un nuovo piano

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .
2. Selezionare l'abbonamento a Office 365 E4.
3. Selezionare la scheda **aggiornamento** . Se vengono visualizzati altri piani, significa che è possibile aggiornare i piani automaticamente.
4. Se non è possibile eseguire l'aggiornamento automatico, viene visualizzato un messaggio in cui viene descritto il motivo per cui non è possibile eseguire l'aggiornamento.

Sono diversi i motivi per cui non è possibile aggiornare automaticamente i piani. La maggior parte dei problemi sono quelli temporanei, ad esempio problemi di integrità dei servizi che è possibile risolvere. Per ulteriori informazioni, vedere [perché non è possibile aggiornare I piani?](upgrade-to-different-plan.md#why-cant-i-upgrade-plans) Se si ha bisogno di assistenza per l'aggiornamento, [contattare il supporto](../../admin/contact-support-for-business-products.md).

## <a name="will-a-credit-check-be-required"></a>Sarà necessaria una verifica del credito?

Se il pagamento del nuovo piano viene effettuato tramite fattura oppure se l'acquisto supera un determinato costo, può essere necessaria una verifica del credito. Se è necessaria una verifica del credito, l'aggiornamento può richiedere fino a due giorni lavorativi. Gli amministratori non hanno accesso all'interfaccia di amministrazione di Microsoft 365 finché non è stata completata la verifica del credito. Tuttavia, gli utenti hanno ancora accesso completo al piano E4 fino al termine dell'aggiornamento.

## <a name="upgrade-your-plan-by-using-the-upgrade-tab"></a>Aggiornare il piano utilizzando la scheda aggiornamento

### <a name="before-you-begin"></a>Prima di iniziare

Ecco alcuni fattori importanti da considerare prima di iniziare.

- **Pianificare il tempo di inattività amministrativo.** Gli amministratori non possono utilizzare l'interfaccia di amministrazione di Microsoft 365 mentre il piano è in fase di aggiornamento. A seconda del numero di utenti di cui si dispone, l'aggiornamento può richiedere da minuti a ore. È consigliabile pianificare l'aggiornamento quando non è necessario effettuare gli aggiornamenti utilizzando l'interfaccia di amministrazione di Microsoft 365.

    Gli utenti non subiscono interruzioni del servizio durante l'aggiornamento del piano-continuano ad avere accesso completo all'abbonamento E4 durante il processo di aggiornamento. Al termine dell'aggiornamento, gli utenti possono accedere al nuovo piano.
- **Utenti, licenze, fatturazione e domini personalizzati.** Per comprendere il modo in cui gli utenti e le licenze vengono gestiti durante l'aggiornamento, come i piani di aggiornamento influiscono sulla fatturazione e come gestire i domini personalizzati, vedere [che cosa significa aggiornare un piano per il servizio e la fatturazione?](upgrade-to-different-plan.md#what-does-upgrading-a-plan-do-to-my-service-and-billing)
- **Modificare il numero di licenze utente.** Non è possibile rimuovere le licenze come parte dei piani di aggiornamento. Tuttavia, è possibile [ridurre il numero di licenze](../licenses/buy-licenses.md) prima o dopo l'aggiornamento dei piani.

### <a name="start-the-upgrade-by-using-the-upgrade-tab"></a>Avviare l'aggiornamento utilizzando la scheda aggiornamento

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .
2. Selezionare l'abbonamento a Office 365 E4.
3. Nella pagina Dettagli sottoscrizione selezionare la scheda **aggiornamento** .
4. Individuare l'abbonamento che si desidera acquistare, quindi selezionare **Aggiorna**.
5. Nella pagina **carrello** , verificare che tutto sia corretto. Selezionare se pagare mensilmente o annualmente e verificare il numero di licenze in **quantità**.
    > [!NOTE]
    > Sono inoltre elencati tutti gli abbonamenti a componenti aggiuntivi associati all'abbonamento a Office 365 E4, ad esempio Office 365 extra file storage. Tuttavia, se sono presenti abbonamenti a componenti aggiuntivi inclusi nell'abbonamento a cui si esegue l'aggiornamento, verranno rimossi.
6. Dopo aver esaminato l'ordine, seleziona **Vai a checkout**.
7. Nella pagina **checkout** , esaminare gli elementi **venduti a**, **fatturati**e **in questo ordine**. Selezionare **Cambia** accanto a uno di questi elementi per modificare le informazioni.
    > [!NOTE]
    > L'opzione per utilizzare la fattura come metodo di pagamento è disponibile solo per gli ordini superiori a un determinato importo di costo. Se si seleziona l'opzione di pagamento della fattura, è possibile posticipare il processo di aggiornamento di fino a due giorni lavorativi Se è necessaria una verifica del credito.
8. Al termine, selezionare **Ordina ordine**.

> [!NOTE]
> L'aggiornamento dei piani richiede in genere meno di dieci minuti se non sono presenti errori o problemi. È possibile controllare lo stato dell'aggiornamento esaminando la sottoscrizione precedente o nuova.

## <a name="upgrade-your-plan-manually"></a>Aggiornare manualmente il piano

Per aggiornare manualmente gli utenti a un altro abbonamento, completare i passaggi seguenti nell'ordine indicato.

- [Passaggio 1: acquistare un nuovo abbonamento](#step-1-buy-a-new-subscription)
- [Passaggio 2: verificare che la sottoscrizione disponga del numero corretto di licenze](#step-2-verify-that-your-subscription-has-the-right-number-of-licenses)
- [Passaggio 3: riassegnare le licenze agli utenti](#step-3-reassign-licenses-to-users)
- [Passaggio 4: annullare l'abbonamento a Office 365 E4](#step-4-cancel-the-office-365-e4-subscription)

### <a name="step-1-buy-a-new-subscription"></a>Passaggio 1: acquistare un nuovo abbonamento

Se non si dispone ancora di un nuovo abbonamento, è possibile [acquistare un altro abbonamento a Microsoft 365 for business](../buy-another-subscription.md).

Se si dispone già di un abbonamento, continuare con il passaggio successivo.

### <a name="step-2-verify-that-your-subscription-has-the-right-number-of-licenses"></a>Passaggio 2: verificare che la sottoscrizione disponga del numero corretto di licenze

Prima di passare al passaggio successivo, è importante assicurarsi che tutti i servizi all'interno del nuovo abbonamento siano stati configurati. Se l'abbonamento non è pronto al primo controllo, riprovare in un secondo momento.

> [!NOTE]
> Se si è scelto di pagare il nuovo abbonamento tramite fattura, potrebbe essere necessaria una verifica del credito. È possibile richiedere fino a due giorni lavorativi prima che l'abbonamento sia disponibile.

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .
2. Nell'elenco a discesa **stato sottoscrizione** selezionare **attivo**.
3. Verificare che il nuovo abbonamento sia visualizzato e che il numero di licenze corrisponda a quello dell'utente di Office 365 E4.
4. Se è necessario acquistare altre licenze, seguire la procedura illustrata in [acquistare o rimuovere le licenze di sottoscrizione](../licenses/buy-licenses.md).

### <a name="step-3-reassign-licenses-to-users"></a>Passaggio 3: riassegnare le licenze agli utenti

È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per riassegnare le licenze per un massimo di 20 utenti alla volta. Per informazioni, vedere [spostare gli utenti in una sottoscrizione diversa](move-users-different-subscription.md).

> [!TIP]
> Se si dispone di numerosi utenti, è possibile [utilizzare Office 365 PowerShell per assegnare le licenze utente in blocco](https://docs.microsoft.com/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell).

### <a name="step-4-cancel-the-office-365-e4-subscription"></a>Passaggio 4: annullare l'abbonamento a Office 365 E4

Dopo che tutti gli utenti sono stati riassegnati al nuovo abbonamento, [annullare l'abbonamento a Office 365 E4](cancel-your-subscription.md).

## <a name="related-content"></a>Contenuto correlato

[Eseguire l'aggiornamento a un piano diverso](upgrade-to-different-plan.md) (articolo) \
[Acquistare o rimuovere licenze di sottoscrizione](../licenses/buy-licenses.md) (articolo) \
[Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md) (articolo)
