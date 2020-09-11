---
title: Gestire gli acquisti in modalità self-service (amministratori)
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Gli amministratori possono imparare a gestire gli acquisti in modalità self-service effettuati dagli utenti dell'organizzazione.
ms.openlocfilehash: f10f525f8efc6bc63e2fa042c299a6d03c77d0cb
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429999"
---
# <a name="manage-self-service-purchases-admin"></a>Gestire acquisti in modalità self-service (amministratore)

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Come amministratore, è possibile visualizzare gli acquisti in modalità self-service effettuati dagli utenti dell'organizzazione. È possibile visualizzare il nome del prodotto, il nome dell'acquirente, le sottoscrizioni acquistate, la data di scadenza, il prezzo di acquisto e gli utenti assegnati per ogni acquisto in modalità self-service. Se richiesto dall'organizzazione, è possibile disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell. Si dispone degli stessi criteri di gestione dei dati e di accesso rispetto ai prodotti acquistati tramite l'acquisto in modalità self-service o in modo centralizzato.

È inoltre possibile controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service. Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Visualizzare le sottoscrizioni in modalità self-service

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .
2. Accanto a **risultati di affinamento**, dall'elenco a discesa **tipo di account** scegliere **self-service**.
3. Per visualizzare ulteriori dettagli su un abbonamento, selezionarne uno dall'elenco.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Visualizzazione delle licenze per un abbonamento all'acquisto in modalità self-service

1. Nell'interfaccia di amministrazione, andare alla **Billing**  >  pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.
2. Scegliere l'icona filtro e quindi fare clic su **self-service**.
3. Selezionare un prodotto per visualizzare le licenze assegnate agli utenti.
    > [!NOTE]
    > Se per un prodotto sono presenti più acquisti, tale prodotto è elencato solo una volta e la colonna **quantità disponibile** indica il totale di tutte le sottoscrizioni acquistate per il prodotto.
4. L'elenco **utenti** è raggruppato in base ai nomi delle persone che hanno effettuato acquisti in modalità self-service.
5. Per esportare un elenco di utenti con licenze per le sottoscrizioni, scegliere gli abbonamenti che si desidera esportare, quindi scegliere **Esporta utenti**.

## <a name="disable-or-enable-self-service-purchases"></a>Disabilitare o abilitare gli acquisti in modalità self-service

È possibile disabilitare o abilitare l'acquisto in modalità self-service per gli utenti dell'organizzazione. Il modulo di **MSCommerce** PowerShell include un valore del parametro **PolicyId** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service e per quali prodotti.

È possibile utilizzare il modulo di **MSCommerce** PowerShell per:

- Visualizzare lo stato predefinito del valore del parametro **AllowSelfServicePurchase** , ovvero se è abilitato o disabilitato per prodotto
- Visualizzare un elenco di prodotti applicabili e se l'acquisto in modalità self-service è abilitato o disabilitato
- Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarlo o disabilitarlo

Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizzare le licenze in un singolo abbonamento

È possibile assegnare licenze esistenti o acquistare abbonamenti aggiuntivi mediante contratti esistenti per gli utenti assegnati agli acquisti in modalità self-service. Dopo aver assegnato le licenze acquistate in modo centralizzato, è possibile richiedere che gli acquirenti cancellino le sottoscrizioni esistenti.

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a> con l'account di amministratore globale o amministratore di fatturazione.
2. Passare alla pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servizi di acquisto</a> per la fatturazione.
3. Trovare e scegliere il prodotto che si desidera acquistare, quindi scegliere **buy**.
4. Completare i passaggi rimanenti per completare l'acquisto.
5. Seguire la procedura illustrata [per l'](#view-who-has-licenses-for-a-self-service-purchase-subscription) esportazione di un elenco di utenti a cui fare riferimento nel passaggio 6.
6. Assegnare le licenze a tutti gli utenti che dispongono di una licenza nell'altra sottoscrizione. Per i passaggi completi, vedere [assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md).
7. Contattare la persona che ha acquistato l'abbonamento all'acquisto in modalità self-service e chiedergli di annullarla.

## <a name="take-over-a-self-service-purchase-subscription"></a>Acquisizione di un abbonamento all'acquisto in modalità self-service

È possibile eseguire una sottoscrizione di acquisto in modalità self-service effettuata da un utente dell'organizzazione. Quando si utilizza un abbonamento all'acquisto in modalità self-service, sono disponibili due opzioni:

1. Spostare gli utenti in un abbonamento diverso e annullare la sottoscrizione originale.
2. Annullare la sottoscrizione di acquisto in modalità self-service e rimuovere le licenze dagli utenti assegnati.

### <a name="move-users-to-a-different-subscription"></a>Trasferire gli utenti a un abbonamento diverso

Quando si spostano gli utenti in una sottoscrizione diversa, la sottoscrizione precedente viene annullata automaticamente. L'utente che ha acquistato originariamente la sottoscrizione di acquisto self-service riceve un messaggio di posta elettronica che indica che la sottoscrizione è stata annullata.

> [!NOTE]
> È necessario disporre di una licenza disponibile per ogni utente che si sta spostando nell'abbonamento a cui si sta spostando gli utenti.

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .
2. Nella scheda **prodotti** selezionare l'icona filtro e quindi fare clic su **self-service**.
3. Selezionare l'abbonamento che si desidera sottoporre.
4. Nella sezione **abbonamenti e impostazioni** della pagina Dettagli sottoscrizione selezionare **Assumi il controllo della sottoscrizione**.
5. Nel riquadro a destra, selezionare **Sposta utenti**.
6. Selezionare il prodotto in cui si desidera spostare gli utenti, quindi selezionare **Sposta utenti**.
7. Nella casella **Move users to** selezionare **Move users**. Il processo di spostamento potrebbe richiedere alcuni minuti. Non chiudere il browser durante l'esecuzione del processo.
8. Al termine del processo di spostamento, chiudere il **riquadro Sposta completato**.
9. Nella pagina Dettagli sottoscrizione, lo **stato della sottoscrizione** per la sottoscrizione acquistata in modalità self-service viene visualizzato come **eliminato**.

### <a name="cancel-a-self-service-purchase-subscription"></a>Annullamento di una sottoscrizione di acquisto in modalità self-service

Quando si sceglie di annullare una sottoscrizione di acquisto in modalità self-service, gli utenti che dispongono di licenze perdono l'accesso al prodotto. L'utente che ha acquistato originariamente la sottoscrizione di acquisto self-service riceve un messaggio di posta elettronica che indica che la sottoscrizione è stata annullata.

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .
2. Nella scheda **prodotti** selezionare l'icona filtro e quindi fare clic su **self-service**.
3. Selezionare l'abbonamento che si desidera annullare.
4. Nella sezione **abbonamenti e impostazioni** della pagina Dettagli sottoscrizione selezionare **Assumi il controllo della sottoscrizione**.
5. Nel riquadro a destra, selezionare **Annulla sottoscrizione**.
6. Seleziona un motivo per l'annullamento dall'elenco a discesa, quindi seleziona **Annulla sottoscrizione**.
7. Nella casella **si è sicuri di voler annullare?** , selezionare **Annulla sottoscrizione**.
8. Chiudere il riquadro destro.
9. Nella pagina Dettagli sottoscrizione lo stato della **sottoscrizione** viene visualizzato come **eliminato**.

## <a name="need-help-contact-us"></a>Hai bisogno di assistenza? Contattaci.

Per domande comuni sugli acquisti in modalità self-service, vedere domande [frequenti sugli acquisti in modalità self-service](self-service-purchase-faq.md).

Se hai domande o hai bisogno di assistenza per gli acquisti in modalità self-service, [Contatta il supporto](../../admin/contact-support-for-business-products.md).