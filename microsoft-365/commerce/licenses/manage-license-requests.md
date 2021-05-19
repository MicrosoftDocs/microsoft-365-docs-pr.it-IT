---
title: Gestire le richieste di licenza
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Informazioni su come esaminare e approvare o rifiutare le richieste di licenza degli utenti per l'abbonamento Microsoft 365 per le aziende.
ms.date: 08/07/2020
ms.openlocfilehash: 6cbfd81f4f6deba642729f1fef0b826b07a99f56
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535675"
---
# <a name="manage-license-requests"></a>Gestire le richieste di licenza

> [!NOTE]
> Le informazioni contenute in questo articolo si applicano solo ai prodotti acquistati in modalità self-service. Per ulteriori informazioni, vedere [Domande frequenti sugli acquisti in self-service.](../subscriptions/self-service-purchase-faq.yml)

Se si disabilitano gli acquisti in modalità self-service nell'organizzazione, è possibile utilizzare le richieste di licenze per gestire il processo di richiesta di licenza per gli utenti. Quando un utente tenta di effettuare un acquisto in modalità self-service per un prodotto bloccato, può inviare una richiesta di licenza all'amministratore. Quando effettua una richiesta, può aggiungere i nomi di altri utenti che necessitano anche di licenze per il prodotto.

> [!NOTE]
> Se si bloccano gli utenti dall'effettuare acquisti self-service, Microsoft non invia loro messaggi di posta elettronica di marketing. Inoltre, se usano una versione di valutazione di un prodotto, non visualizzano istruzioni per acquistarlo. Per ulteriori informazioni, vedere [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).

Per visualizzare e gestire le richieste di licenza, l'amministratore usa la **scheda Richieste** nella **pagina Licenze.** L'elenco mostra il nome del prodotto richiesto, il nome della persona che richiede una licenza, la data richiesta e lo stato della richiesta. Gli amministratori possono filtrare l'elenco per visualizzare le richieste in sospeso o completate. Le richieste vengono mantenute per 30 giorni.

## <a name="before-you-begin"></a>Prima di iniziare

Per eseguire le attività in questo articolo, è necessario essere un amministratore globale. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Usare il proprio processo di richiesta

Se l'organizzazione dispone di un proprio processo di richiesta, è possibile utilizzarlo. Si crea un messaggio che viene visualizzato agli utenti quando richiedono una licenza.

> [!IMPORTANT]
> Se si utilizza il proprio processo di richiesta, nella **scheda** Richieste non viene visualizzata alcuna richiesta. Le richieste esistenti prima di aggiungere il messaggio continuano a essere visualizzate fino a quando non vengono approvate o rifiutate.

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione, quindi selezionare la **scheda** Richieste.
2. Selezionare **Usa invece il processo di richiesta esistente.**
3. Nella casella Messaggio del  riquadro destro digitare il messaggio che si desidera visualizzare quando gli utenti richiedono una licenza. Se si desidera includere anche un collegamento ai criteri dell'organizzazione o ad altra documentazione, immettere l'URL nella casella di testo Collegamento alla **documentazione (facoltativo).**
4. Selezionare **Salva**.

Quando si torna **all'elenco Richieste,** viene visualizzato il messaggio **You're using your own license request process**. Per apportare modifiche al messaggio inviato agli utenti, selezionare **Usa il processo di richiesta esistente.**

## <a name="stop-using-your-own-request-process"></a>Interrompere l'uso del proprio processo di richiesta

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione, quindi selezionare la **scheda** Richieste.
2. Selezionare **Usa invece il processo di richiesta esistente.**
3. Nel riquadro destro deselezionare la casella di controllo Usa processo di richiesta **dell'organizzazione.**
4. Selezionare **Salva**.

## <a name="approve-or-deny-a-license-request"></a>Approvare o rifiutare una richiesta di licenza

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione, quindi selezionare la **scheda** Richieste.
2. Selezionare la riga contenente la richiesta che si desidera esaminare. Il riquadro destro mostra i dettagli sugli utenti che desiderano licenze per il prodotto.
3. Per rifiutare **l'intera** richiesta, selezionare Non approvare e nella finestra di dialogo selezionare **Non approvare**.
4. Per rifiutare alcuni utenti per la richiesta, ma approvarli, selezionare la X in base al nome degli utenti che si desidera rimuovere. I nomi vengono spostati in **Non assegnare a questi utenti**.
5. Se si dispone di più di un prodotto, in Selezionare un **prodotto** selezionare quello che si desidera utilizzare per assegnare le licenze.
6. Per negare agli utenti l'accesso a determinate app e servizi, espandi Attiva o disattiva app e **servizi,** quindi deseleziona le caselle di controllo per quelle che vuoi escludere.
7. Nella parte inferiore del riquadro digitare un messaggio facoltativo nella casella di testo.
8. Al termine, selezionare **Approva**. Il riquadro destro mostra i dettagli della richiesta.
9. Chiudere il riquadro destro.
    Gli utenti ricevono un messaggio di posta elettronica che indica che la richiesta è stata approvata o rifiutata.

## <a name="related-content"></a>Contenuto correlato

[Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md) (articolo)\
[Spostare gli utenti in un abbonamento diverso](../subscriptions/move-users-different-subscription.md) (articolo)\
[Acquistare o rimuovere licenze di sottoscrizione](buy-licenses.md) (articolo)
