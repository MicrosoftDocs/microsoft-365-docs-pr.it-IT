---
title: Cambiare manualmente i piani di Microsoft 365 for business
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
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: eb0d0680-5677-41a0-8c46-4b9d47f1c209
ROBOTS: NOINDEX
description: Passare manualmente gli abbonamenti di Microsoft 365 per le aziende acquistando un nuovo abbonamento e assicurando che entrambe le sottoscrizioni siano elencate e attive.
ms.openlocfilehash: f06e6a5f441286cbe048187eea39889772bb4e75
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43707512"
---
# <a name="switch-microsoft-365-for-business-plans-manually"></a>Cambiare manualmente i piani di Microsoft 365 for business

::: moniker range="o365-worldwide"
> [!NOTE]
> Questo articolo si applica all'interfaccia di amministrazione precedente. Per visualizzare l'articolo relativo al nuovo interfaccia di amministrazione, vedere [modificare i piani manualmente](change-plans-manually.md). Il nuovo interfaccia di amministrazione è disponibile per tutti gli amministratori di Microsoft 365 ed è possibile optare selezionando il nuovo Toggle dell'interfaccia di **Amministrazione** che si trova nella parte superiore della Home page. Per altre informazioni, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../../admin/microsoft-365-admin-center-preview.md).
::: moniker-end

## <a name="step-1-decide-how-to-switch-plans"></a>Passaggio 1: decidere come cambiare piano

Il modo migliore per passare tutti gli utenti da un piano a un altro consiste nell'utilizzare il [pulsante utilizza il comando Cambia piano](switch-to-a-different-plan.md#use-the-switch-plans-button). A volte però questo non è possibile. Occorre eseguire un passaggio manuale quando:
  
- Il pulsante **Cambia piano** non è presente.

- Se, quando si seleziona il pulsante **Cambia** piano, la pianificazione desiderata non è presente nell'elenco.

- Se non si desidera cambiare tutti gli utenti nello stesso modo. Alcune aziende hanno la necessità di sottoscrivere piani diversi per determinati utenti. In questo caso occorre cambiare piano manualmente.

Per continuare con l'opzione manuale, leggere [passaggio 2: acquistare un nuovo abbonamento](#step-2-buy-a-new-subscription) in questo argomento.
  
## <a name="step-2-buy-a-new-subscription"></a>Passaggio 2: acquistare un nuovo abbonamento

 **Si è già acquistato un piano?** Se si dispone già di un abbonamento a cui si desidera spostare gli utenti, saltare questo passaggio e andare al [passaggio 3: verificare il nuovo abbonamento e le licenze](#step-3-check-your-new-subscription-and-licenses) in questo argomento.
  
- OPPURE -
  
 **Acquistare un nuovo abbonamento e licenze:** Per acquistare un nuovo abbonamento, seguire la procedura illustrata in [acquistare un altro abbonamento a Microsoft 365 for business](../buy-another-subscription.md) .
  
Assicurarsi di acquistare un abbonamento per la stessa organizzazione in cui si trovano gli utenti. Ad esempio, controllare gli indirizzi di posta elettronica per gli utenti che si desidera spostare. Se includono @contoso.com, occorre acquistare un nuovo abbonamento per contoso.com. Includere una licenza per ogni utente da spostare.
  
 **Se si ha bisogno di assistenza nella scelta di un piano**, vedere la pagina [di confronto dei prodotti Microsoft 365 per le aziende](https://go.microsoft.com/fwlink/p/?linkid=842056) o [contattare il supporto tecnico](../../admin/contact-support-for-business-products.md).
  
## <a name="step-3-check-your-new-subscription-and-licenses"></a>Passaggio 3: controllare il nuovo abbonamento e le licenze

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Abbonamenti</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abbonamenti</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abbonamenti</a>.

::: moniker-end

2. **Verificare che entrambi gli abbonamenti siano elencati e attivi**

    L'abbonamento da cui si stanno spostando gli utenti e quello in cui li si stanno spostando devono essere elencati insieme. Se il nuovo abbonamento non compare ancora al primo controllo, controllare di nuovo più tardi. Verificare che entrambi gli abbonamenti siano elencati in **ATTIVI**. [Il nuovo abbonamento non è elencato o non è attivo](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Verificare di avere licenze sufficienti per ogni utente**

    Ogni utente deve avere una licenza corrispondente al proprio abbonamento. Pertanto, se si desidera spostare dieci utenti in Microsoft 365 Business Premium, è necessario assicurarsi che siano disponibili dieci licenze. 

4. **Servono altre licenze per il nuovo abbonamento?** Passare alla pagina **abbonamenti** e [acquistare le licenze per l'abbonamento a Microsoft 365 for business](../licenses/buy-licenses.md).
  
    [Cosa accade alle vecchie licenze](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Il nuovo abbonamento non è elencato o non è attivo

- **Se l'abbonamento è stato acquistato tramite fattura** ed è necessaria una verifica del credito, potrebbero trascorrere fino a due giorni lavorativi prima che l'abbonamento sia disponibile.

- **Se sono stati acquistati due abbonamenti e non sono entrambi elencati qui**, è possibile che siano stati acquistati per organizzazioni diverse (per domini diversi). Gli abbonamenti devono rimanere nei limiti di un'organizzazione.

- **Se si è sicuri di avere un abbonamento aggiuntivo**, ma non è elencato qui o in **ATTIVI**, [chiamare il supporto](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>Cosa accade alle vecchie licenze

Le licenze per l'abbonamento corrente verranno rimosse successivamente e da quel momento in poi si pagherà solo per le nuove licenze utente.
  
## <a name="step-4-reassign-licenses"></a>Passaggio 4: riassegnazione delle licenze

### <a name="reassign-a-license-for-one-user"></a>Riassegnare una licenza per un solo utente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end

2. Nella pagina **Utenti attivi** selezionare la casella accanto al nome dell'utente a cui si vuole assegnare una licenza.

3. A destra, nella riga **licenze di prodotto** , selezionare **modifica**.

4. Nel riquadro **Licenze di prodotto** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza da assegnare all'utente. Per impostazione predefinita, tutti i servizi associati alla licenza vengono automaticamente assegnati all'utente.

    > [!TIP]
    > Per limitare i servizi disponibili per l'utente, impostare sulla posizione **Disattivato** l'interruttore relativo ai servizi da rimuovere per l'utente. Ad esempio, se si vuole che l'utente abbia accesso a tutti i servizi disponibili tranne Skype for Business online, è possibile impostare l'interruttore relativo al servizio Skype for Business online sulla posizione **Disattivato**.
  
5. Impostare l'interruttore sulla posizione **disattivata** per le licenze di cui l'utente non ha più bisogno.

6. Nella parte inferiore del riquadro **licenze di prodotto** , selezionare **assegna** \> **Close** \> **Close**chiudere Chiudi.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Riassegnare licenze a più utenti contemporaneamente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione, andare alla \> pagina **utenti** <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">attivi</a> .

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end

2. Selezionare le caselle accanto ai nomi degli utenti per i quali si vogliono sostituire le licenze esistenti.

3. Nel riquadro **Azioni in blocco** scegliere **Modifica licenze di prodotto**.

4. Nel riquadro **Assegna prodotti** selezionare **Sostituisci assegnazioni licenze di prodotto esistenti** \> **Avanti**.

5. Impostare sulla posizione **Attivato** l'interruttore relativo ai prodotti da assegnare agli utenti.

    > [!TIP]
    > - Per limitare i servizi disponibili per l'utente, impostare sulla posizione **Disattivato** l'interruttore relativo ai servizi da rimuovere per l'utente. Ad esempio, se si vuole che l'utente abbia accesso a tutti i servizi disponibili tranne Skype for Business online, è possibile impostare l'interruttore relativo al servizio Skype for Business online sulla posizione **Disattivato**.
    > - Le eventuali licenze precedentemente assegnate agli utenti selezionati verranno rimosse.
  
6. Nella parte inferiore del riquadro **Sostituisci prodotti esistenti** selezionare **Sostituisci** \> **Chiudi**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Passaggio 5: annullare le sottoscrizioni o rimuovere le licenze non più necessarie (facoltativo)

Se tutti gli utenti sono stati spostati su un altro abbonamento e l'abbonamento originale non è più necessario, è possibile [annullarlo](cancel-your-subscription.md).
  
Se sono stati spostati solo alcuni utenti, [rimuovere le licenze](../licenses/remove-licenses-from-subscription.md) non più necessarie.
  
## <a name="call-support-to-help-you-switch-plans"></a>Chiamare il supporto tecnico per assistenza con il cambio di piano

[Chiamare il supporto](../../admin/contact-support-for-business-products.md)