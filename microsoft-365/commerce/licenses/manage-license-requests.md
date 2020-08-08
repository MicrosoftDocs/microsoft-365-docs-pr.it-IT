---
title: Gestire le richieste di licenza
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Informazioni su come rivedere e approvare o negare le richieste di licenza da parte degli utenti per l'abbonamento a Microsoft 365 for business.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597655"
---
# <a name="manage-license-requests"></a>Gestire le richieste di licenza

> [!NOTE]
> Le informazioni contenute in questo articolo si applicano solo ai prodotti acquistati in modalità self-service. Per ulteriori informazioni, vedere [domande frequenti sull'acquisto in modalità self-service](../subscriptions/self-service-purchase-faq.md).

Se si disabilitano gli acquisti in modalità self-service nell'organizzazione, è possibile utilizzare le richieste di licenze per gestire il processo di richiesta di licenza per gli utenti. Quando un utente tenta di effettuare un acquisto in modalità self-service per un prodotto bloccato, può inviare una richiesta di licenza all'amministratore. Quando eseguono una richiesta, possono aggiungere i nomi di altri utenti che hanno anche bisogno di licenze per il prodotto.

> [!NOTE]
> Se si bloccano gli utenti dall'effettuare acquisti in modalità self-service, Microsoft non invia loro messaggi di posta elettronica di marketing. Inoltre, se si sta utilizzando una versione di valutazione di un prodotto, non vengono visualizzati messaggi di richiesta per l'acquisto. Per ulteriori informazioni, vedere [Manage self-service purchases (admin)](../subscriptions/manage-self-service-purchases-admins.md).

Per visualizzare e gestire le richieste di licenza, l'amministratore utilizza la scheda **richieste** nella pagina **licenze** . Nell'elenco viene visualizzato il nome del prodotto richiesto, il nome della persona che richiede una licenza, la data richiesta e lo stato della richiesta. Gli amministratori possono filtrare l'elenco per visualizzare le richieste in sospeso o completate. Le richieste vengono conservate per 30 giorni.

## <a name="before-you-begin"></a>Prima di iniziare

Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Utilizzare il proprio processo di richiesta

Se l'organizzazione ha il proprio processo di richiesta, è possibile utilizzarlo. È possibile creare un messaggio visualizzato agli utenti quando richiedono una licenza.

> [!IMPORTANT]
> Se si utilizza un processo di richiesta personalizzato, non vengono visualizzate richieste nella scheda **richieste** . le richieste esistenti da prima di aggiungere il messaggio continuano a essere visualizzate fino a quando non vengono approvate o rifiutate.

1. Nell'interfaccia di amministrazione, andare alla pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione, quindi selezionare la scheda **richieste** .
2. Selezionare **utilizza invece il processo di richiesta esistente**.
3. Nel riquadro a destra, nella finestra di **messaggio** , digitare il messaggio che si desidera venga visualizzato dagli utenti quando richiedono una licenza. Se si desidera includere anche un collegamento ai criteri delle organizzazioni o altra documentazione, immettere l'URL nella casella **di testo collegamento alla documentazione (facoltativa)** .
4. Seleziona **Salva**.

Quando si torna all'elenco delle **richieste** , viene visualizzato il messaggio **che si sta utilizzando il proprio processo di richiesta di licenza**. Per apportare modifiche al messaggio inviato agli utenti, selezionare **utilizza invece il processo di richiesta esistente**.

## <a name="stop-using-your-own-request-process"></a>Interrompere l'utilizzo del processo di richiesta personalizzato

1. Nell'interfaccia di amministrazione, andare alla pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione, quindi selezionare la scheda **richieste** .
2. Selezionare **utilizza invece il processo di richiesta esistente**.
3. Nel riquadro a destra deselezionare la casella **di controllo utilizza il processo di richiesta dell'organizzazione** .
4. Seleziona **Salva**.

## <a name="approve-or-deny-a-license-request"></a>Approvare o rifiutare una richiesta di licenza

1. Nell'interfaccia di amministrazione, andare alla pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione, quindi selezionare la scheda **richieste** .
2. Selezionare la riga che contiene la richiesta che si desidera esaminare. Nel riquadro destro vengono visualizzati i dettagli relativi agli utenti che desiderano le licenze per il prodotto.
3. Per negare l'intera richiesta, selezionare **non approva**e nella finestra di dialogo selezionare **non approva**.
4. Per negare ad alcuni utenti la richiesta, ma approvarne altri, selezionare la X in base al nome degli utenti che si desidera rimuovere. I nomi vengono spostati in non **assegnare a questi utenti**.
5. Se si dispone di più di un prodotto, in **selezionare un prodotto**selezionare quello che si desidera utilizzare per assegnare le licenze.
6. Per impedire agli utenti di accedere a determinate app e servizi, espandere **attiva o disattiva le app e i servizi**, quindi deselezionare le caselle di controllo per quelle che si desidera escludere.
7. Nella parte inferiore del riquadro digitare un messaggio facoltativo nella casella di testo.
8. Al termine, selezionare **approva**. Nel riquadro a destra vengono visualizzati i dettagli della richiesta.
9. Chiudere il riquadro destro.
    Gli utenti ricevono un messaggio di posta elettronica in cui la richiesta è stata approvata o negata.

## <a name="related-content"></a>Contenuto correlato

[Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md) (articolo) \
[Spostare gli utenti in una sottoscrizione diversa](../subscriptions/move-users-different-subscription.md) (articolo) \
[Acquistare o rimuovere licenze di sottoscrizione](buy-licenses.md) (articolo)