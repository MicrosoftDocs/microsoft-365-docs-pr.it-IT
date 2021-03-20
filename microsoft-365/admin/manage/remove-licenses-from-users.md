---
title: Annullare l'assegnazione delle licenze agli utenti
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Informazioni su come annullare l'assegnazione delle licenze dagli account utente.
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915195"
---
# <a name="unassign-licenses-from-users"></a>Annullare l'assegnazione delle licenze agli utenti

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

È possibile annullare l'assegnazione delle licenze dagli utenti nella **pagina Utenti** attivi o nella **pagina Licenze.** Il metodo utilizzato dipende dal fatto che si desideri annullare l'assegnazione delle licenze di prodotto da utenti specifici o annullare l'assegnazione delle licenze degli utenti da un prodotto specifico.

::: moniker-end

## <a name="before-you-begin"></a>Prima di iniziare

- Per annullare l'assegnazione delle licenze, devi essere un amministratore globale, di licenza e utente. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).
- È possibile [rimuovere licenze da account utente con PowerShell di Office 365](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- È inoltre possibile [eliminare gli account utente](../add-users/delete-a-user.md) a cui è stata assegnata una licenza per rendere disponibile la licenza ad altri utenti. Quando elimini un account utente, la relativa licenza è immediatamente disponibile per l'assegnazione a qualcun altro.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usare la pagina Licenze per annullare l'assegnazione delle licenze

Quando si utilizza la **pagina Licenze** per annullare l'assegnazione delle licenze, si annulla l'assegnazione delle licenze per un prodotto specifico per un massimo di 20 utenti.

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.
2. Selezionare il prodotto per cui si desidera annullare l'assegnazione delle licenze.
3. Selezionare gli utenti per i quali si desidera annullare l'assegnazione delle licenze.
4. Selezionare **Annulla assegnazione licenze**.
5. Nella casella **Annulla assegnazione licenze** selezionare Annulla **assegnazione.**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usare la pagina Utenti attivi per annullare l'assegnazione delle licenze

Quando si utilizza la **pagina Utenti attivi** per annullare l'assegnazione delle licenze, si annullano le licenze di prodotto dagli utenti.

### <a name="unassign-licenses-from-one-user"></a>Annullare l'assegnazione delle licenze da un utente
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare la riga dell'utente per cui si desidera annullare l'assegnazione di una licenza.
3. Nel riquadro destro selezionare **Licenze e app**.
4. Espandere la **sezione** Licenze, deselezionare le caselle relative alle licenze che si desidera annullare l'assegnazione, quindi selezionare **Salva modifiche.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Annullare l'assegnazione delle licenze da un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.
2. Seleziona l'utente per cui vuoi annullare l'assegnazione della licenza.
3. A destra, nella riga **Licenze prodotto,** selezionare **Modifica**.
4. Nel riquadro **Licenze di** prodotto imposta l'interruttore sulla posizione **Disattivato** per la licenza che vuoi annullare l'assegnazione per l'utente. Ad esempio, se si disattiva la licenza di Office 365 Enterprise E3, la licenza viene disattivata e tutti i servizi in tale licenza per tale utente.
5. Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Annullare l'assegnazione delle licenze da un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.
2. Seleziona l'utente per cui vuoi annullare l'assegnazione della licenza.
3. A destra, nella riga **Licenze prodotto,** selezionare **Modifica**.
4. Nel riquadro **Licenze di** prodotto imposta l'interruttore sulla posizione **Disattivato** per la licenza che vuoi annullare l'assegnazione per l'utente. Ad esempio, se si disattiva la licenza di Office 365 Enterprise E3, la licenza viene disattivata e tutti i servizi in tale licenza per tale utente.
5. Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Annullare l'assegnazione delle licenze da più utenti

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare i cerchi accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione delle licenze.
3. Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.
4. Nel riquadro **Gestisci licenze prodotto** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.
5. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la **casella** di controllo Rimuovi tutte le licenze di prodotto dagli utenti selezionati, quindi **selezionare Sostituisci** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Annullare l'assegnazione delle licenze da più utenti

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.
2. Selezionare le caselle accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione di tutte le licenze.
3. Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.
4. Nel riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.
5. Nella parte inferiore del riquadro Sostituisci  prodotti **esistenti** selezionare la casella di controllo Rimuovi tutte le licenze di prodotto dagli utenti selezionati, quindi **selezionare Sostituisci** \> **Chiudi** \> **Chiudi.**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Annullare l'assegnazione delle licenze da più utenti
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.
2. Selezionare le caselle accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione di tutte le licenze.
3. Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.
4. Nel riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.
5. Nella parte inferiore del riquadro Sostituisci  prodotti **esistenti** selezionare la casella di controllo Rimuovi tutte le licenze di prodotto dagli utenti selezionati, quindi **selezionare Sostituisci** \> **Chiudi** \> **Chiudi.**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Cosa succede ai dati di un utente quando si rimuove la licenza?

- Quando una licenza viene rimossa da un utente, i dati associati a tale account vengono mantenuti per 30 giorni. Dopo il periodo di tolleranza di 30 giorni, i dati vengono eliminati e non possono essere ripristinati.
- I file salvati in OneDrive for Business non vengono eliminati a meno che l'utente non venga eliminato dall'interfaccia di amministrazione di Microsoft 365 o non venga rimosso tramite la sincronizzazione di Active Directory. Per ulteriori informazioni, vedere Conservazione ed eliminazione [di OneDrive.](/onedrive/retention-and-deletion)
- Quando la licenza viene rimossa, la cassetta postale dell'utente non è più disponibile per la ricerca tramite uno strumento di eDiscovery, ad esempio Ricerca contenuto o Advanced eDiscovery. Per ulteriori informazioni, vedere "Ricerca di cassette postali disconnesse o senza licenza" in [Ricerca contenuto in Microsoft 365.](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes)
- Se si dispone di un abbonamento Enterprise, come Office 365 Enterprise E3, Exchange Online consente di conservare i dati delle cassette postali di un account utente eliminato utilizzando cassette postali [inattive.](../../compliance/inactive-mailboxes-in-office-365.md) Per ulteriori informazioni, vedere [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Per informazioni su come bloccare l'accesso di un utente ai dati di Microsoft 365 dopo la rimozione della licenza e su come ottenere l'accesso ai dati in seguito, vedere Rimuovere un [ex dipendente.](../add-users/remove-former-employee.md)
- Se si rimuove la licenza di un utente e le app di Office sono ancora installate, vengono visualizzati errori di attivazione e prodotto senza licenza [in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) quando usano le app di Office.

## <a name="next-steps"></a>Passaggi successivi

Se non si desidera [riassegnare](../../managed-desktop/get-started/assign-licenses.md)le licenze non utilizzate [](../../commerce/licenses/buy-licenses.md) ad altri utenti, è consigliabile rimuovere le licenze dall'abbonamento in modo da non pagare più licenze di quelle necessarie.

## <a name="related-content"></a>Contenuto correlato

[Rimuovere licenze dall'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)\
[Assegnare licenze agli utenti](assign-licenses-to-users.md) (articolo)\
[Informazioni su abbonamenti e licenze in Microsoft 365 per le aziende](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)