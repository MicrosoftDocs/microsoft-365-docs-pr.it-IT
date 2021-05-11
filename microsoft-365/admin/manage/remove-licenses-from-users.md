---
title: Annullare l'assegnazione delle licenze agli utenti
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- manage_licenses
- okr_smb
- commerce
search.appverid:
- MET150
description: Informazioni su come annullare l'assegnazione delle licenze dagli account utente.
ms.date: 07/01/2020
ms.openlocfilehash: 87bb8f6fe0e85fc4ac832f2bc4ad746e8d6386eb
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310993"
---
# <a name="unassign-licenses-from-users"></a>Annullare l'assegnazione delle licenze agli utenti

È possibile annullare l'assegnazione delle licenze dagli utenti nella **pagina Utenti** attivi o nella **pagina Licenze.** Il metodo utilizzato dipende dal fatto che si desideri annullare l'assegnazione delle licenze di prodotto da utenti specifici o annullare l'assegnazione delle licenze degli utenti da un prodotto specifico.

> [!NOTE]
> Gli amministratori non possono assegnare o annullare l'assegnazione di licenze per un abbonamento acquistato in modalità self-service da un utente dell'organizzazione. È possibile [assumere il controllo di un abbonamento acquistato in modalità self-service](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) e quindi assegnare licenze o annullarne l'assegnazione.

## <a name="before-you-begin"></a>Prima di iniziare

- Per annullare l'assegnazione delle licenze, devi essere un amministratore globale, di licenza e utente. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).
- È possibile [rimuovere licenze da account utente con PowerShell di Office 365](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- È inoltre possibile [eliminare gli account utente](../add-users/delete-a-user.md) a cui è stata assegnata una licenza per rendere disponibile la licenza ad altri utenti. Quando elimini un account utente, la relativa licenza è immediatamente disponibile per l'assegnazione a qualcun altro.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usare la pagina Licenze per annullare l'assegnazione delle licenze

Quando si utilizza la **pagina Licenze** per annullare l'assegnazione delle licenze, si annulla l'assegnazione delle licenze per un prodotto specifico per un massimo di 20 utenti.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.
::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.

::: moniker-end

2. Selezionare il prodotto per cui si desidera annullare l'assegnazione delle licenze.
3. Selezionare gli utenti per i quali si desidera annullare l'assegnazione delle licenze.
4. Selezionare **Annulla assegnazione licenze**.
5. Nella casella **Annulla assegnazione licenze** selezionare Annulla **assegnazione.**

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usare la pagina Utenti attivi per annullare l'assegnazione delle licenze

Quando si utilizza la **pagina Utenti attivi** per annullare l'assegnazione delle licenze, si annullano le licenze di prodotto dagli utenti.

### <a name="unassign-licenses-from-one-user"></a>Annullare l'assegnazione delle licenze da un utente
  
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.

::: moniker-end

2. Selezionare la riga dell'utente per cui si desidera annullare l'assegnazione di una licenza.
3. Nel riquadro destro selezionare **Licenze e app**.
4. Espandere la **sezione** Licenze, deselezionare le caselle relative alle licenze che si desidera annullare l'assegnazione, quindi selezionare **Salva modifiche.**

###  <a name="unassign-licenses-from-multiple-users"></a>Annullare l'assegnazione delle licenze da più utenti

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.

::: moniker-end

2. Selezionare i cerchi accanto ai nomi degli utenti per cui si desidera annullare l'assegnazione delle licenze.
3. Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.
4. Nel riquadro **Gestisci licenze prodotto** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.
5. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare la **casella** di controllo Rimuovi tutte le licenze di prodotto dagli utenti selezionati, quindi **selezionare Sostituisci** \> **Chiudi**.

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Cosa succede ai dati di un utente quando si rimuove la licenza?

- Quando una licenza viene rimossa da un utente, i dati associati a tale account vengono mantenuti per 30 giorni. Dopo il periodo di tolleranza di 30 giorni, i dati vengono eliminati e non possono essere ripristinati.
- I file salvati in OneDrive for Business non vengono eliminati a meno che l'utente non venga eliminato dall'interfaccia di amministrazione di Microsoft 365 o non venga rimosso tramite la sincronizzazione di Active Directory. Per ulteriori informazioni, vedere OneDrive [conservazione ed eliminazione.](/onedrive/retention-and-deletion)
- Quando la licenza viene rimossa, la cassetta postale dell'utente non è più disponibile per la ricerca utilizzando uno strumento di eDiscovery, ad esempio Ricerca contenuto o Advanced eDiscovery. Per ulteriori informazioni, vedere "Ricerca di cassette postali disconnesse o senza licenza" in [Content search reference.](../../compliance/content-search-reference.md#searching-disconnected-or-de-licensed-mailboxes)
- Se si dispone di una sottoscrizione Enterprise, come Office 365 Enterprise E3, Exchange Online consente di conservare i dati della cassetta postale di un account utente eliminato utilizzando cassette postali [inattive.](../../compliance/inactive-mailboxes-in-office-365.md) Per ulteriori informazioni, vedere [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Per informazioni su come bloccare l'accesso di un utente ai dati Microsoft 365 dopo la rimozione della licenza e su come ottenere l'accesso ai dati in un secondo momento, vedere Rimuovere un [ex dipendente.](../add-users/remove-former-employee.md)
- Se rimuovi la licenza di un utente e hanno ancora [](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) app Office installate, gli errori di attivazione e prodotto senza licenza vengono visualizzati in Office quando usano Office app.

## <a name="next-steps"></a>Passaggi successivi

Se non si desidera [riassegnare](../../managed-desktop/get-started/assign-licenses.md)le licenze non utilizzate [](../../commerce/licenses/buy-licenses.md) ad altri utenti, è consigliabile rimuovere le licenze dall'abbonamento in modo da non pagare più licenze di quelle necessarie.

## <a name="related-content"></a>Contenuti correlati

[Rimuovere licenze dall'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)\
[Assegnare licenze agli utenti](assign-licenses-to-users.md) (articolo)\
[Informazioni su abbonamenti e licenze in Microsoft 365 per le aziende](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)