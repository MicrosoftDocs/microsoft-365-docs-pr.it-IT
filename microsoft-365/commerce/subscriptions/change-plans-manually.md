---
title: Modificare manualmente i piani di Microsoft 365 for business
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Modificare manualmente le sottoscrizioni acquistando un nuovo abbonamento e assicurando che entrambe le sottoscrizioni siano elencate e attive.
ms.openlocfilehash: bcd9a129ef1597469ef9bbf93841b5db4f919f1e
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43707632"
---
# <a name="change-plans-manually"></a>Modificare i piani manualmente

## <a name="step-1-decide-how-to-change-plans"></a>Passaggio 1: decidere come modificare i piani

Il modo migliore per modificare tutti gli utenti da un piano all'altro consiste nell' [utilizzare la scheda aggiornamento](upgrade-to-different-plan.md). A volte questo non è possibile. Modificare manualmente i piani invece:

- Se la scheda **aggiornamento** indica che non è possibile aggiornare il piano corrente.

- Se, quando si seleziona la scheda **aggiornamento** , il piano desiderato non è elencato.

- Se non si desidera aggiornare tutti gli utenti allo stesso modo. Alcune aziende hanno la necessità di sottoscrivere piani diversi per determinati utenti. Utilizzare una modifica manuale per questo.

Per continuare con una modifica manuale, leggere [passaggio 2: acquistare un nuovo abbonamento](#step-2-buy-a-new-subscription) in questo argomento.

> [!IMPORTANT]
> Se si passa a un piano con meno servizi correlati ai dati rispetto al piano corrente (downgrade), è necessario eseguire manualmente il backup di tutti i dati che si desidera mantenere. Per ulteriori informazioni, vedere [eseguire il backup dei dati prima di modificare i piani](back-up-data-before-switching-plans.md).

## <a name="step-2-buy-a-new-subscription"></a>Passaggio 2: acquistare un nuovo abbonamento

**Si è già acquistato un piano?** Se si dispone già di un abbonamento a cui si desidera spostare gli utenti, saltare questo passaggio e andare al [passaggio 3: verificare il nuovo abbonamento e le licenze](#step-3-check-your-new-subscription-and-licenses) in questo argomento.

OPPURE

**Acquistare un nuovo abbonamento e licenze:** Per acquistare un nuovo abbonamento, seguire la procedura illustrata in [acquistare un altro abbonamento a Microsoft 365 for business](../buy-another-subscription.md) .

Assicurarsi di acquistare un abbonamento per la stessa organizzazione in cui si trovano gli utenti. Ad esempio, controllare gli indirizzi di posta elettronica per gli utenti che si desidera spostare. Se gli indirizzi di posta \@elettronica includono contoso.com, è necessario acquistare un nuovo abbonamento per contoso.com.
Includere una licenza per ogni utente da spostare.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Passaggio 3: controllare il nuovo abbonamento e le licenze

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Prodotti e servizi</a>.

2. **Verificare che entrambe le sottoscrizioni siano elencate e attive** La sottoscrizione da cui si sta spostando gli utenti e l'abbonamento a cui si sta spostando gli utenti devono essere elencati insieme. Se il nuovo abbonamento non compare ancora al primo controllo, controllare di nuovo più tardi. Verificare che entrambe le sottoscrizioni siano attive. [Il nuovo abbonamento non è elencato o non è attivo](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Verificare di disporre di licenze sufficienti per ogni utente** Ogni utente ha bisogno di una licenza che corrisponda alla propria sottoscrizione. Pertanto, se si desidera spostare dieci utenti in Microsoft 365 Business Premium, è necessario assicurarsi che siano disponibili dieci licenze.

4. **Servono altre licenze per il nuovo abbonamento?**
   Passare alla pagina **prodotti & Servizi** e [acquistare altre licenze](../licenses/buy-licenses.md).

> [Cosa accade alle vecchie licenze](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Il nuovo abbonamento non è elencato o non è attivo

- **Se sono stati acquistati due abbonamenti e non sono entrambi elencati qui**, è possibile che siano stati acquistati per organizzazioni diverse (per domini diversi). Gli abbonamenti devono rimanere nei limiti di un'organizzazione.

- **Se si è certi di avere un abbonamento aggiuntivo**, ma non è elencato qui o non è attivo, [contattare il supporto tecnico Microsoft](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>Cosa accade alle vecchie licenze

Le licenze per l'abbonamento corrente verranno rimosse successivamente e da quel momento in poi si pagherà solo per le nuove licenze utente.

## <a name="step-4-reassign-licenses"></a>Passaggio 4: riassegnazione delle licenze

### <a name="reassign-a-license-for-one-user"></a>Riassegnare una licenza per un solo utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **utenti attivi** selezionare l'utente a cui si desidera assegnare una licenza.

3. Nella scheda **licenze e app** di te, espandere **licenze**, selezionare le caselle per le licenze che si desidera assegnare, quindi selezionare **Salva modifiche**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Riassegnare licenze a più utenti contemporaneamente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare i cerchi accanto ai nomi degli utenti per i quali si desidera sostituire le licenze esistenti.

3. Nella parte superiore, selezionare **altre opzioni** (**...**) e quindi fare clic su **Gestisci licenze di prodotto**.

4. Selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.

5. Impostare sulla posizione **Attivato** l'interruttore relativo ai prodotti da assegnare agli utenti.

    > [!TIP]
    > - Per limitare i servizi disponibili per l'utente, impostare sulla posizione **Disattivato** l'interruttore relativo ai servizi da rimuovere per l'utente. Ad esempio, se si vuole che l'utente abbia accesso a tutti i servizi disponibili tranne Skype for Business online, è possibile impostare l'interruttore relativo al servizio Skype for Business online sulla posizione **Disattivato**.
    > - Le eventuali licenze precedentemente assegnate agli utenti selezionati verranno rimosse.

6. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci** \> **Chiudi**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Passaggio 5: annullare le sottoscrizioni o rimuovere le licenze non più necessarie (facoltativo)

Se tutti gli utenti sono stati spostati su un altro abbonamento e l'abbonamento originale non è più necessario, è possibile [annullarlo](cancel-your-subscription.md).

Se sono stati spostati solo alcuni utenti, [rimuovere le licenze](../licenses/remove-licenses-from-subscription.md) non più necessarie.

## <a name="call-support-to-help-you-change-plans"></a>Supporto per la chiamata per la modifica di piani
[Chiamare il supporto tecnico Microsoft](../../admin/contact-support-for-business-products.md)