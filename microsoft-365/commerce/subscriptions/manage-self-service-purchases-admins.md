---
title: Gestire gli acquisti in modalità self-service (amministratori)
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Gli amministratori possono imparare a gestire gli acquisti self-service effettuati dagli utenti nell'organizzazione.
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920181"
---
# <a name="manage-self-service-purchases-admin"></a>Gestire acquisti in modalità self-service (amministratore)

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Gli amministratori possono visualizzare gli acquisti in modalità self-service effettuati da persone dell'organizzazione. Vengono visualizzati il nome del prodotto, il nome dell'acquirente, le sottoscrizioni acquistate, la data di scadenza, il prezzo di acquisto e gli utenti assegnati per ogni acquisto self-service. Se richiesto dall'organizzazione, è possibile disattivare gli acquisti self-service in base al prodotto tramite PowerShell. Si dispone degli stessi criteri di gestione dei dati e di accesso sui prodotti acquistati tramite acquisto self-service o centralmente.

È inoltre possibile controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service. Per ulteriori informazioni, vedere [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Visualizzare le sottoscrizioni self-service

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Self-service**.
3. Per visualizzare altri dettagli su una sottoscrizione, selezionarne uno dall'elenco.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Visualizzare chi dispone di licenze per una sottoscrizione di acquisto self-service

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione.
2. Seleziona l'icona del filtro, quindi scegli **Self-service.**
3. Selezionare un prodotto per visualizzare le licenze assegnate agli utenti.
    > [!NOTE]
    > Se sono presenti più acquisti per un prodotto, tale prodotto viene elencato una sola volta e nella colonna **Quantità** disponibile viene visualizzato il totale di tutte le sottoscrizioni acquistate per tale prodotto.
4. **L'elenco** Utenti è raggruppato in base ai nomi delle persone che hanno effettuato acquisti self-service.
5. Per esportare un elenco di utenti con licenze per queste sottoscrizioni, scegliere le sottoscrizioni che si desidera esportare, quindi scegliere **Esporta utenti**.

## <a name="disable-or-enable-self-service-purchases"></a>Disabilitare o abilitare gli acquisti in modalità self-service

È possibile disabilitare o abilitare gli acquisti in modalità self-service per gli utenti dell'organizzazione. Il **modulo MSCommerce** PowerShell include un valore del parametro **PolicyID** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service e per quali prodotti.

È possibile utilizzare il **modulo ms-Commerce** PowerShell per:

- Visualizzare lo stato predefinito del **valore del parametro AllowSelfServicePurchase,** indipendentemente dal fatto che sia abilitato o disabilitato dal prodotto
- Visualizzare un elenco dei prodotti applicabili e se l'acquisto in self-service è abilitato o disabilitato
- Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarla o disabilitarla

Per ulteriori informazioni, vedere [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizzare le licenze con un singolo abbonamento

È possibile assegnare licenze esistenti o acquistare abbonamenti aggiuntivi tramite contratti esistenti per gli utenti assegnati agli acquisti self-service. Dopo aver assegnato queste licenze acquistate centralmente, è possibile richiedere agli acquirenti di annullare le sottoscrizioni esistenti.

1. Nell'interfaccia di amministrazione passare alla **pagina Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Acquisto servizi.</a>
2. Trova e scegli il prodotto che vuoi acquistare, quindi scegli **Acquista**.
3. Completa i passaggi rimanenti per completare l'acquisto.
4. Seguire i passaggi descritti in Visualizzare chi ha licenze per una sottoscrizione acquistata [in modalità self-service](#view-who-has-licenses-for-a-self-service-purchase-subscription) per esportare un elenco di utenti a cui fare riferimento nel passaggio successivo.
5. Assegnare licenze a tutti gli utenti che hanno una licenza nell'altro abbonamento. Per la procedura completa, vedere [Assegnare licenze agli utenti.](../../admin/manage/assign-licenses-to-users.md)
6. Contattare la persona che ha acquistato la sottoscrizione di acquisto self-service e chiedere di [annullarla.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Assumere una sottoscrizione di acquisto self-service

È possibile assumere una sottoscrizione di acquisto self-service effettuata da un utente dell'organizzazione. Quando si acquista una sottoscrizione self-service, sono disponibili due opzioni:

1. Spostare gli utenti in un'altra sottoscrizione e annullare la sottoscrizione originale.
2. Annullare la sottoscrizione di acquisto self-service e rimuovere le licenze dagli utenti assegnati.

### <a name="move-users-to-a-different-subscription"></a>Trasferire gli utenti a un abbonamento diverso

Quando si spostano gli utenti in un abbonamento diverso, la sottoscrizione precedente viene automaticamente annullata. L'utente che ha acquistato in origine la sottoscrizione di acquisto self-service riceve un messaggio di posta elettronica che indica che l'abbonamento è stato annullato.

> [!NOTE]
> È necessario disporre di una licenza disponibile per ogni utente in cui si sta spostando l'abbonamento in cui si stanno spostando gli utenti.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Self-service**.
3. Selezionare l'abbonamento che si desidera assumere.
4. Nella sezione Sottoscrizioni e  impostazioni della pagina dei dettagli dell'abbonamento selezionare Prendi **il controllo della sottoscrizione.**
5. Nel riquadro destro selezionare **Sposta utenti**.
6. Selezionare il prodotto in cui si desidera spostare gli utenti, quindi selezionare **Sposta utenti**.
7. Nella casella **Sposta utenti in** selezionare Sposta **utenti**. Il processo di spostamento potrebbe richiedere alcuni minuti. Non chiudere il browser durante l'esecuzione del processo.
8. Al termine del processo di spostamento, chiudere il **riquadro Sposta completato.**
9. Nella pagina dei dettagli della sottoscrizione, lo **stato della** sottoscrizione per la sottoscrizione acquistata in self-service viene visualizzato come **Eliminato.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Annullare una sottoscrizione di acquisto self-service

Quando si sceglie di annullare una sottoscrizione di acquisto self-service, gli utenti con licenze perdono l'accesso al prodotto. L'utente che ha acquistato in origine la sottoscrizione di acquisto self-service riceve un messaggio di posta elettronica che indica che l'abbonamento è stato annullato.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Self-service**.
3. Selezionare l'abbonamento che si desidera annullare.
4. Nella sezione Sottoscrizioni e  impostazioni della pagina dei dettagli dell'abbonamento selezionare Prendi **il controllo della sottoscrizione.**
5. Nel riquadro destro selezionare **Annulla sottoscrizione**.
6. Selezionare un motivo per l'annullamento dall'elenco a discesa, quindi selezionare **Annulla sottoscrizione.**
7. Nella casella **Si è certi di voler annullare?** selezionare Annulla **sottoscrizione.**
8. Chiudere il riquadro destro.
9. Nella pagina dei dettagli della sottoscrizione lo **stato della sottoscrizione** viene visualizzato come **Eliminato.**

## <a name="need-help-contact-us"></a>Hai bisogno di assistenza? Contattaci.

Per domande frequenti sugli acquisti self-service, vedere Domande frequenti [sugli acquisti in self-service.](self-service-purchase-faq.md)

Se hai domande o hai bisogno di assistenza per gli acquisti self-service, [contatta il supporto](../../admin/contact-support-for-business-products.md).