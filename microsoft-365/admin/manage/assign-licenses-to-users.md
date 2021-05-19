---
title: Assegnare licenze agli utenti
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Assegnare licenze a seconda che si vogliano assegnare licenze di prodotto a utenti specifici o assegnare licenze utente a prodotti specifici.
ms.date: 04/26/2021
ms.openlocfilehash: 707c1c952aa737f0aa91d886e9fa304eabe26321
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537536"
---
# <a name="assign-licenses-to-users"></a>Assegnare licenze agli utenti

È possibile assegnare licenze agli utenti nella pagina **Utenti attivi** o nella pagina **Licenze**. Il metodo da usare varia a seconda che si vogliano assegnare licenze di prodotto a utenti specifici o assegnare licenze utente a prodotti specifici.

> [!NOTE]
> Gli amministratori non possono assegnare o annullare l'assegnazione di licenze per un abbonamento acquistato in modalità self-service da un utente dell'organizzazione. È possibile [assumere il controllo di un abbonamento acquistato in modalità self-service](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) e quindi assegnare licenze o annullarne l'assegnazione.

[Vedere come aggiungere un utente e contemporaneamente assegnargli una licenza](../add-users/add-users.md).

## <a name="before-you-begin"></a>Prima di iniziare

- Per assegnare le licenze è necessario essere un amministratore globale, delle licenze o degli utenti. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).
- È possibile [assegnare licenze di Microsoft 365 ad account utente con PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).
- Per usare licenze basate su gruppi, vedere [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Alcuni servizi, come Sway, vengono assegnati agli utenti automaticamente e non è necessario assegnarli singolarmente.


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Usare la pagina Licenze per assegnare licenze agli utenti

Nella pagina **Licenze** si assegnano licenze di un prodotto specifico a un massimo di 20 utenti. Nella pagina **Licenze** viene visualizzato un elenco di tutti i prodotti per cui si hanno abbonamenti. Si può anche vedere il numero totale di licenze per ogni prodotto, il numero di licenze assegnate e il numero di licenze disponibili.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenze</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenze</a>.

::: moniker-end


2. Selezionare un prodotto.
3. Nella pagina dei dettagli sul prodotto selezionare **Assegna licenze**.
4. Nel riquadro **Assegna licenze agli utenti** iniziare a digitare un nome, quindi selezionarlo nei risultati per aggiungerlo all'elenco. È possibile aggiungere fino a 20 utenti per volta.
4. Selezionare **Abilita o disabilita le app e i servizi** per assegnare o rimuovere l'accesso a elementi specifici.
6. Al termine, selezionare **Assegna**, quindi fare clic su **Chiudi**.

In caso di conflitto viene visualizzato un messaggio che indica qual è il problema e come risolverlo. Se, ad esempio, sono state selezionate licenze che contengono servizi in conflitto, viene visualizzato un messaggio di errore che suggerisce di rivedere i servizi inclusi in ogni licenza e riprovare.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Modificare le app e i servizi a cui un utente ha accesso

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenze</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenze</a>.

::: moniker-end


2. Nella pagina **Licenze** selezionare la riga relativa a uno specifico utente.
3. Nel riquadro destro selezionare o deselezionare le app e i servizi per i quali si desidera consentire o rimuovere l'accesso.
4. Al termine, selezionare **Salva**, quindi selezionare **Chiudi**.

## <a name="use-the-active-users-page-to-assign-licenses"></a>Usare la pagina Utenti attivi per assegnare licenze

Nella pagina **Utenti attivi** si assegnano licenze utente ai prodotti.

### <a name="assign-licenses-to-multiple-users"></a>Assegnare licenze a più utenti

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end


2. Selezionare i cerchi accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.
3. Nella parte superiore, selezionare i tre puntini (altre azioni), quindi **Gestisci licenze prodotto**.
4. Nel riquadro **Gestisci licenze prodotto** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.
5. Nel riquadro **Aggiungi a prodotti esistenti** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza che si vuole assegnare agli utenti selezionati.\
    Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti. È possibile porre limiti ai servizi disponibili agli utenti. Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.
6. Nella parte inferiore del riquadro selezionare **Aggiungi** \> **Chiudi**.  


> [!NOTE]
> Se si vogliono assegnare licenze per un numero elevato di utenti, usare [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)

### <a name="assign-licenses-to-one-user"></a>Assegnare licenze a un utente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end


2. Selezionare la riga dell'utente al quale si vuole assegnare una licenza.
3. Nel riquadro destro selezionare **Licenze e app**.
4. Espandere la sezione **Licenze**, selezionare le caselle delle licenze da assegnare, quindi selezionare **Salva modifiche**.

## <a name="assign-a-license-to-a-guest-user"></a>Assegnare una licenza a un utente guest

È possibile invitare gli utenti guest a collaborare con l'organizzazione nell'interfaccia di amministrazione di Azure Active Directory. Per informazioni sugli utenti guest, vedere [Cos'è l'accesso degli utenti guest in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b) Se vi sono utenti guest, vedere [Guida introduttiva: aggiungere utenti guest alla directory nel portale di Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

> [!IMPORTANT]
> Per eseguire questi passaggi, è necessario essere un amministratore globale.

1. Andare sull’<a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">interfaccia di amministrazione di Azure Active Directory</a>
2. Nel riquadro di spostamento selezionare **Utenti**.
3. Nella pagina **Utenti | Tutti gli utenti (anteprima)**, selezionare **Aggiungi filtri**.
4. Nel menu **Selezionare un campo**, scegliere **Tipo di utente**, quindi selezionare **Applica**.
5. Nel menu successivo, selezionare **Guest**.
6. Nell'elenco dei risultati, selezionare l'utente che necessita di una licenza.
7. In **Gestisci**, selezionare **Licenze**.
8. Selezionare **Attività**.
9. Nella pagina **Aggiornare le assegnazioni di licenze**, selezionare il prodotto per cui si vuole assegnare una licenza.
10. Nella parte destra, deselezionare le caselle di controllo per tutti i servizi a cui non si vuole consentire l'accesso all'utente guest.
11. Selezionare **Salva**.

## <a name="next-steps"></a>Passaggi successivi

Se gli utenti non hanno ancora installato le app di Office, si può condividere con loro la [guida introduttiva per i dipendenti](../../business-video/employee-quick-setup.md), ricca di informazioni su come, ad esempio, [scaricare e installare Microsoft 365 o Office 2019 in un PC o un Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [configurare le app di Office e la posta elettronica in un dispositivo mobile](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenuto correlato

[Informazioni su abbonamenti e licenze](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)\
[Annullare l'assegnazione delle licenze agli utenti](remove-licenses-from-users.md) (articolo)\
[Acquistare o rimuovere licenze per l'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)\
