---
title: Assegnare licenze agli utenti
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Informazioni su come assegnare licenze agli utenti.
ms.date: 08/14/2020
ms.openlocfilehash: ec2f9ae2e580987266c636343a66d7c21138e4c3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645132"
---
# <a name="assign-licenses-to-users"></a>Assegnare licenze agli utenti

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

È possibile assegnare licenze agli utenti nella pagina **Utenti attivi** o nella pagina **Licenze**. Il metodo da usare varia a seconda che si vogliano assegnare licenze di prodotto a utenti specifici o assegnare licenze utente a prodotti specifici.

::: moniker-end

[Vedere come aggiungere un utente e contemporaneamente assegnargli una licenza](../add-users/add-users.md).

## <a name="before-you-begin"></a>Prima di iniziare

- Per assegnare le licenze è necessario essere un amministratore globale, delle licenze o degli utenti. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).
- È possibile [assegnare licenze ad account utente con PowerShell di Office 365](https://go.microsoft.com/fwlink/p/?linkid=850410).
- Per usare licenze basate su gruppi, vedere [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Alcuni servizi, come Sway, vengono assegnati agli utenti automaticamente e non è necessario assegnarli singolarmente.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Usare la pagina Licenze per assegnare licenze agli utenti

Nella pagina **Licenze** si assegnano licenze di un prodotto specifico a un massimo di 20 utenti. Nella pagina **Licenze** viene visualizzato un elenco di tutti i prodotti per cui si hanno abbonamenti. Si può anche vedere il numero totale di licenze per ogni prodotto, il numero di licenze assegnate e il numero di licenze disponibili.

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.
2. Selezionare un prodotto.
3. Nella pagina dei dettagli sul prodotto selezionare **Assegna licenze**.
4. Nel riquadro **Assegna licenze agli utenti** iniziare a digitare un nome, quindi selezionarlo nei risultati per aggiungerlo all'elenco. È possibile aggiungere fino a 20 utenti per volta.
5. Selezionare **Abilita o disabilita le app e i servizi** per assegnare o rimuovere l'accesso a elementi specifici.
6. Al termine, selezionare **Assegna**, quindi fare clic su **Chiudi**.

In caso di conflitto viene visualizzato un messaggio che indica qual è il problema e come risolverlo. Se, ad esempio, sono state selezionate licenze che contengono servizi in conflitto, viene visualizzato un messaggio di errore che suggerisce di rivedere i servizi inclusi in ogni licenza e riprovare.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Modificare le app e i servizi a cui un utente ha accesso

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.
2. Nella pagina **Licenze** selezionare la riga relativa a uno specifico utente.
3. Nel riquadro destro selezionare o deselezionare le app e i servizi per i quali si desidera consentire o rimuovere l'accesso.
4. Al termine, selezionare **Salva**, quindi selezionare **Chiudi**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>Usare la pagina Utenti attivi per assegnare licenze

Nella pagina **Utenti attivi** si assegnano licenze utente ai prodotti.

### <a name="assign-licenses-to-multiple-users"></a>Assegnare licenze a più utenti

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare i cerchi accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.
3. Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.
4. Nel riquadro **Gestisci licenze prodotto** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.
5. Nel riquadro **Aggiungi a prodotti esistenti** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza che si vuole assegnare agli utenti selezionati.\
    Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti. È possibile porre limiti ai servizi disponibili agli utenti. Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.
6. Nella parte inferiore del riquadro selezionare **Aggiungi** \> **Chiudi**.  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>Assegnare licenze a più utenti

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.
2. Selezionare le caselle accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.
3. Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.
4. Nel riquadro**Assegna prodotti** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.
5. Impostare sulla posizione **Attivata** l'interruttore relativo alle licenze che si vogliono assegnare agli utenti selezionati.\
    Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti. È possibile porre limiti ai servizi disponibili agli utenti. Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.
6. Nella parte inferiore del riquadro **Aggiungi a prodotti esistenti** selezionare **Aggiungi** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>Assegnare licenze a più utenti

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.
2. Selezionare le caselle accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.
3. Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.
4. Nel riquadro**Assegna prodotti** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.
5. Impostare sulla posizione **Attivata** l'interruttore relativo alle licenze che si vogliono assegnare agli utenti selezionati.\
    Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti. È possibile porre limiti ai servizi disponibili agli utenti. Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.
6. Nella parte inferiore del riquadro **Aggiungi a prodotti esistenti** selezionare **Aggiungi** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>Assegnare licenze a un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare la riga dell'utente al quale si vuole assegnare una licenza.
3. Nel riquadro destro selezionare **Licenze e app**.
4. Espandere la sezione **Licenze**, selezionare le caselle delle licenze da assegnare, quindi selezionare **Salva modifiche**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>Assegnare licenze a un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.
2. Selezionare la casella accanto al nome dell'utente a cui si vuole assegnare una licenza.
3. Nel riquadro destro, nella riga **Licenze di prodotto** selezionare **Modifica**.
4. Nel riquadro **Licenze di prodotto** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza da assegnare all'utente.\
    Per impostazione predefinita, tutti i servizi associati alla licenza vengono automaticamente assegnati all'utente. È possibile porre limiti ai servizi disponibili all'utente. Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare all'utente.
5. Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>Assegnare licenze a un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.
2. Selezionare la casella accanto al nome dell'utente a cui si vuole assegnare una licenza.
3. Nel riquadro destro, nella riga **Licenze di prodotto** selezionare **Modifica**.
4. Nel riquadro **Licenze di prodotto** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza da assegnare all'utente.\
    Per impostazione predefinita, tutti i servizi associati alla licenza vengono automaticamente assegnati all'utente. È possibile porre limiti ai servizi disponibili all'utente. Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare all'utente.
5. Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a>Assegnare una licenza a un utente guest

È possibile invitare gli utenti guest a collaborare con l'organizzazione nell'interfaccia di amministrazione di Azure Active Directory. Per informazioni sui guest user, vedere [Cos'è l'accesso degli utenti guest in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b) Se vi sono utenti guest, vedere [Guida introduttiva: aggiungere utenti guest alla directory nel portale di Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

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

Se gli utenti non hanno ancora installato le app di Office, si può condividere con loro la [guida introduttiva per i dipendenti](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f), ricca di informazioni su come, ad esempio, [scaricare e installare Microsoft 365 o Office 2019 in un PC o un Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [configurare le app di Office e la posta elettronica in un dispositivo mobile](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenuto correlato

[Informazioni su abbonamenti e licenze](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)\
[Annullare l'assegnazione delle licenze agli utenti](remove-licenses-from-users.md) (articolo)\
[Acquistare o rimuovere licenze per l'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)\