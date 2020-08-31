---
title: Annullare l'assegnazione delle licenze agli utenti
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.openlocfilehash: 4441fd253c4cf5304562900bf31869eb4e0f21ff
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306540"
---
# <a name="unassign-licenses-from-users"></a>Annullare l'assegnazione delle licenze agli utenti

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

È possibile annullare l'assegnazione delle licenze agli utenti nella pagina **utenti attivi** o nella pagina **licenze** . Il metodo utilizzato varia a seconda che si desideri annullare l'assegnazione delle licenze di prodotto da utenti specifici o annullare l'assegnazione di licenze agli utenti da un prodotto specifico.

::: moniker-end

## <a name="before-you-begin"></a>Prima di iniziare

- Per annullare l'assegnazione delle licenze, è necessario essere un amministratore globale, una licenza per l'utente. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).
- È possibile [rimuovere licenze da account utente con PowerShell di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- È inoltre possibile [eliminare gli account utente](../add-users/delete-a-user.md) a cui è stata assegnata una licenza per rendere disponibile la propria licenza ad altri utenti. Quando si elimina un account utente, la propria licenza è immediatamente disponibile per l'assegnazione a qualcun altro.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Utilizzare la pagina licenze per annullare l'assegnazione delle licenze

Quando si utilizza la pagina **licenze** per annullare l'assegnazione delle licenze, è necessario annullare l'assegnazione delle licenze per un prodotto specifico per un massimo di 20 utenti.

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.
2. Selezionare il prodotto per il quale si desidera annullare l'assegnazione delle licenze.
3. Selezionare gli utenti per i quali si desidera annullare l'assegnazione delle licenze.
4. Selezionare **Annulla assegnazione licenze**.
5. Nella casella **Annulla assegnazione licenze** selezionare **Annulla assegnazione**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Utilizzo della pagina utenti attivi per annullare l'assegnazione delle licenze

Quando si utilizza la pagina **utenti attivi** per annullare l'assegnazione delle licenze, è necessario annullare l'assegnazione delle licenze di prodotto dagli utenti.

### <a name="unassign-licenses-from-one-user"></a>Annullamento dell'assegnazione delle licenze da un utente
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare la riga dell'utente per cui si desidera annullare l'assegnazione di una licenza.
3. Nel riquadro destro selezionare **Licenze e app**.
4. Espandere la sezione **licenze** , deselezionare le caselle per le licenze che si desidera annullare l'assegnazione, quindi selezionare **Salva modifiche**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Annullamento dell'assegnazione delle licenze da un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.
2. Selezionare l'utente per il quale si desidera annullare l'assegnazione della licenza.
3. A destra, nella riga **licenze di prodotto** , selezionare **modifica**.
4. Nel riquadro **licenze di prodotto** , impostare l'interruttore sulla posizione **disattivata** per la licenza che si desidera annullare l'assegnazione per l'utente. Ad esempio, se si disattiva la licenza di Office 365 Enterprise E3, la licenza verrà annienteta e tutti i servizi previsti dalla licenza per tale utente.
5. Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Annullamento dell'assegnazione delle licenze da un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.
2. Selezionare l'utente per il quale si desidera annullare l'assegnazione della licenza.
3. A destra, nella riga **licenze di prodotto** , selezionare **modifica**.
4. Nel riquadro **licenze di prodotto** , impostare l'interruttore sulla posizione **disattivata** per la licenza che si desidera annullare l'assegnazione per l'utente. Ad esempio, se si disattiva la licenza di Office 365 Enterprise E3, la licenza verrà annienteta e tutti i servizi previsti dalla licenza per tale utente.
5. Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Annullamento dell'assegnazione delle licenze da più utenti

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare i cerchi accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione delle licenze.
3. Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.
4. Nel riquadro **Gestisci licenze prodotto** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.
5. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la casella di controllo **Rimuovi tutte le licenze di prodotto dagli utenti selezionati** e quindi fare clic su **Sostituisci** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Annullamento dell'assegnazione delle licenze da più utenti

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.
2. Selezionare le caselle accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione di tutte le licenze.
3. Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.
4. Nel riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.
5. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la casella di controllo **Rimuovi tutte le licenze di prodotto dagli utenti selezionati** , quindi selezionare **Sostituisci** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Annullamento dell'assegnazione delle licenze da più utenti
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.
2. Selezionare le caselle accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione di tutte le licenze.
3. Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.
4. Nel riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.
5. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la casella di controllo **Rimuovi tutte le licenze di prodotto dagli utenti selezionati** , quindi selezionare **Sostituisci** \> **Chiudi** \> **Chiudi**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Cosa succede ai dati di un utente quando si rimuove la licenza?

- Quando una licenza viene rimossa da un utente, i dati associati a quell'account vengono conservati per 30 giorni. Dopo il periodo di tolleranza di 30 giorni, i dati vengono eliminati e non possono essere ripristinati.
- I file salvati in OneDrive for business non vengono eliminati, a meno che l'utente non venga eliminato dall'interfaccia di amministrazione di Microsoft 365 o venga rimosso tramite la sincronizzazione di Active Directory. Per ulteriori informazioni, vedere [OneDrive retention and Deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).
- Quando la licenza è stata rimossa, la cassetta postale dell'utente non è più disponibile per la ricerca tramite uno strumento di eDiscovery, ad esempio ricerca contenuto o Advanced eDiscovery. Per ulteriori informazioni, vedere la sezione relativa alla ricerca di cassette postali disconnesse o concessi in licenza in [Ricerca contenuto in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Se si dispone di un abbonamento Enterprise, ad esempio Office 365 Enterprise E3, Exchange Online consente di mantenere i dati della cassetta postale di un account utente eliminato utilizzando le [cassette postali inattive](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Per ulteriori informazioni, vedere [creare e gestire le cassette postali inattive in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
- Per informazioni su come bloccare l'accesso di un utente ai dati di Microsoft 365 dopo che la licenza è stata rimossa e come ottenere l'accesso ai dati successivamente, vedere [Remove an ex Employee](../add-users/remove-former-employee.md).
- Se si rimuove la licenza di un utente e le app di Office sono ancora installate, vedranno gli [errori di attivazione e di prodotto senza licenza in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) quando utilizzano le app di Office.

## <a name="next-steps"></a>Passaggi successivi

Se non si intende [riassegnare le licenze inutilizzate ad altri utenti](../../managed-desktop/get-started/assign-licenses.md), prendere in considerazione la possibilità di [rimuovere le licenze dall'abbonamento](../../commerce/licenses/buy-licenses.md) in modo che non vengano pagate più licenze di quante ne siano necessarie.

## <a name="related-content"></a>Contenuto correlato

[Rimuovere le licenze dall'abbonamento](../../commerce/licenses/remove-licenses-from-subscription.md) (articolo) \
[Assegnare licenze agli utenti](assign-licenses-to-users.md) (articolo) \
[Informazioni su abbonamenti e licenze in Microsoft 365 for business](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)