---
title: Modificare manualmente i piani di Microsoft 365 per le aziende
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
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Modificare le sottoscrizioni manualmente acquistando una nuova sottoscrizione e verificando che entrambe le sottoscrizioni siano elencate e attive.
ms.openlocfilehash: d6b0c822f9d3ceeb6c50a6ec872682d1db5decb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907905"
---
# <a name="change-plans-manually"></a>Modificare manualmente i piani

## <a name="step-1-decide-how-to-change-plans"></a>Passaggio 1: decidere come modificare i piani

Il modo migliore per modificare tutti gli utenti da un piano a un altro è usare [la scheda Aggiornamento](upgrade-to-different-plan.md). A volte questo non è possibile. Modificare i piani manualmente:

- Se la **scheda** Aggiornamento indica che non è possibile aggiornare il piano corrente.

- Se, quando si seleziona la **scheda Aggiornamento,** il piano desiderato non è elencato.

- Se non si desidera aggiornare tutti gli utenti nello stesso modo. Alcune aziende hanno la necessità di sottoscrivere piani diversi per determinati utenti. A tale scopo, utilizzare una modifica manuale.

Per continuare con una modifica manuale, leggere [Passaggio 2: Acquistare una nuova sottoscrizione](#step-2-buy-a-new-subscription) in questo argomento.

> [!IMPORTANT]
> Se si sta modificando un piano con un numero minore di servizi correlati ai dati rispetto al piano corrente (downgrade), è necessario eseguire manualmente il backup dei dati che si desidera conservare. Per ulteriori informazioni, vedere [Eseguire il backup dei dati prima di modificare i piani.](back-up-data-before-switching-plans.md)

## <a name="step-2-buy-a-new-subscription"></a>Passaggio 2: Acquistare un nuovo abbonamento

**Si è già acquistato un piano?** Se si dispone già di un abbonamento in cui si desidera spostare gli utenti, ignorare questo passaggio e andare a [Passaggio 3: Verificare](#step-3-check-your-new-subscription-and-licenses) la nuova sottoscrizione e le nuove licenze in questo argomento.

OPPURE

**Acquistare una nuova sottoscrizione e licenze:** Seguire i passaggi descritti in Acquistare un altro abbonamento [a Microsoft 365 per le](../try-or-buy-microsoft-365.md) aziende per acquistare un nuovo abbonamento.

Assicurarsi di acquistare un abbonamento per la stessa organizzazione in cui si trovano gli utenti. Ad esempio, controllare gli indirizzi di posta elettronica degli utenti che si desidera spostare. Se gli indirizzi di posta \@ elettronica includono contoso.com, è necessario acquistare un nuovo abbonamento per contoso.com.
Includere una licenza per ogni utente da spostare.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Passaggio 3: controllare la nuova sottoscrizione e le nuove licenze

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.

2. **Verificare che entrambe le sottoscrizioni siano elencate e attive** La sottoscrizione da cui si stanno spostando gli utenti e la sottoscrizione in cui si stanno spostando gli utenti devono essere elencate insieme. Se il nuovo abbonamento non compare ancora al primo controllo, controllare di nuovo più tardi. Verificare che entrambe le sottoscrizioni siano attive. [Il nuovo abbonamento non è elencato o non è attivo](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Verificare di disporre di licenze sufficienti per ogni utente** Ogni utente ha bisogno di una licenza corrispondente all'abbonamento. Pertanto, se si desidera spostare dieci utenti in Microsoft 365 Business Premium, è necessario assicurarsi che siano disponibili dieci licenze.

4. **Servono altre licenze per il nuovo abbonamento?**
   Vai alla **pagina I tuoi prodotti** e acquista altre [licenze.](../licenses/buy-licenses.md)

> [Cosa accade alle vecchie licenze](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Il nuovo abbonamento non è elencato o non è attivo

- **Se sono stati acquistati due abbonamenti e non sono entrambi elencati qui**, è possibile che siano stati acquistati per organizzazioni diverse (per domini diversi). Gli abbonamenti devono rimanere nei limiti di un'organizzazione.

- **Se sai di avere un abbonamento aggiuntivo** e non è elencato qui o non è attivo, chiama il supporto Tecnico [Microsoft.](../../admin/contact-support-for-business-products.md)

### <a name="what-about-the-old-licenses"></a>Cosa accade alle vecchie licenze

Le licenze per l'abbonamento corrente verranno rimosse successivamente e da quel momento in poi si pagherà solo per le nuove licenze utente.

## <a name="step-4-reassign-licenses"></a>Passaggio 4: Riassegnare le licenze

### <a name="reassign-a-license-for-one-user"></a>Riassegnare una licenza per un solo utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **Utenti attivi** selezionare l'utente a cui si desidera assegnare una licenza.

3. Nella scheda **Licenze e app** espandi **Licenze,** seleziona le caselle per le licenze che vuoi assegnare, quindi seleziona **Salva modifiche.**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Riassegnare licenze a più utenti contemporaneamente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare i cerchi accanto ai nomi degli utenti per i quali si desidera sostituire le licenze esistenti.

3. Nella parte superiore selezionare **Altre opzioni** (**...**) e quindi scegliere Gestisci **licenze prodotto**.

4. Selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.

5. Impostare sulla posizione **Attivato** l'interruttore relativo ai prodotti da assegnare agli utenti.

    > [!TIP]
    > - Per limitare i servizi disponibili per l'utente, impostare sulla posizione **Disattivato** l'interruttore relativo ai servizi da rimuovere per l'utente. Ad esempio, se si vuole che l'utente abbia accesso a tutti i servizi disponibili tranne Skype for Business online, è possibile impostare l'interruttore relativo al servizio Skype for Business online sulla posizione **Disattivato**.
    > - Le eventuali licenze precedentemente assegnate agli utenti selezionati verranno rimosse.

6. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci** \> **Chiudi**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Passaggio 5: annullare le sottoscrizioni o rimuovere le licenze non più necessarie (Facoltativo)

Se tutti gli utenti sono stati spostati su un altro abbonamento e l'abbonamento originale non è più necessario, è possibile [annullarlo](cancel-your-subscription.md).

Se sono stati spostati solo alcuni utenti, [rimuovere le licenze](../licenses/buy-licenses.md) non più necessarie.

## <a name="call-support-to-help-you-change-plans"></a>Chiamare il supporto tecnico per modificare i piani
[Chiamare il supporto Tecnico Microsoft](../../admin/contact-support-for-business-products.md)