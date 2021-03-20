---
title: Configurare le impostazioni della cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Dopo aver creato una cassetta postale condivisa, è necessario configurare alcune impostazioni per i relativi utenti, ad esempio l'inoltro della posta elettronica e le risposte automatiche. In seguito, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome o i membri della cassetta postale.
ms.openlocfilehash: 2d0998ba2bdc95a9f78f59527bd9bd6fa98b4c45
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915915"
---
# <a name="configure-shared-mailbox-settings"></a>Configurare le impostazioni della cassetta postale condivisa

Dopo aver creato [una cassetta](create-a-shared-mailbox.md)postale condivisa, è necessario configurare alcune impostazioni per gli utenti della cassetta postale, ad esempio l'inoltro della posta elettronica e le risposte automatiche. In seguito, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale, i membri o le autorizzazioni dei membri. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Modificare il nome o l'alias di posta elettronica di una cassetta postale condivisa o l'indirizzo di posta elettronica principale

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi **selezionare** Modifica accanto a **Nome, Posta elettronica, Alias di posta elettronica**.

3. Immettere un nuovo nome o aggiungere un altro alias. Se si desidera modificare l'indirizzo di posta elettronica principale, la cassetta postale deve disporre di più alias di posta elettronica.

4. Selezionare **Salva**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Inoltrare messaggi di posta elettronica inviati a una cassetta postale condivisa

Non è necessario assegnare una licenza alla cassetta postale condivisa per inoltrare la posta elettronica inviata. È possibile inoltrare i messaggi a qualsiasi indirizzo di posta elettronica o lista di distribuzione valida.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Inoltro posta elettronica** \> **Modifica**.
    
3. Impostare l'interruttore **su Attivato** e immettere un indirizzo di posta elettronica a cui inoltrare i messaggi. Può essere qualsiasi indirizzo di posta elettronica valido. Per inoltrare più indirizzi, è necessario [creare](/office365/admin/setup/create-distribution-lists) un gruppo di distribuzione per gli indirizzi e quindi immettere il nome del gruppo in questa casella.
    
4. Selezionare **Salva**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Inviare risposte automatiche da una cassetta postale condivisa

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Risposte automatiche** \> **Modifica**.
    
3. Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.

4. Immettere la risposta da inviare alle persone interne all'organizzazione. Non è possibile aggiungere immagini, solo testo.

5. Se si desidera *inviare* anche una risposta a persone esterne all'organizzazione, selezionare la casella di controllo, a chi si desidera inviare la risposta e digitare il testo. Non è possibile inviare risposte solo a persone esterne all'organizzazione, escludendo quelle interne.

6. Selezionare **Salva**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Consentire a tutti di visualizzare la posta inviata (le risposte)

Per impostazione predefinita, i messaggi inviati dalla cassetta postale condivisa non vengono salvati nella relativa cartella Posta inviata, bensì nella cartella Posta inviata della persona che ha inviato il messaggio.

Se si desidera consentire a tutti di visualizzare la posta elettronica inviata, nell'interfaccia di amministrazione modificare le impostazioni della cassetta postale condivisa e selezionare **Posta inviata** \> **Modifica**.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Scegliere le app che una cassetta postale condivisa può usare per accedere alla posta elettronica Microsoft

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **App di posta elettronica** \> **Modifica**.

3. Imposta l'interruttore **su Attivato** per tutte le app che vuoi che i membri possano usare per accedere alla cassetta postale condivisa. Imposta l'interruttore **su Disattivato** per tutte le app che non vuoi che usino. 

4. Selezionare **Salva**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Blocco per controversia legale per una cassetta postale condivisa

Per ulteriori informazioni sulla conservazione per controversia legale, vedere [Create a Litigation Hold.](../../compliance/create-a-litigation-hold.md)

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare Conservazione **per controversia legale** \> **Modifica**.

3. Impostare l'interruttore su **Attivato.** 

4. Facoltativamente, immettere una durata, una nota sul blocco e un URL con ulteriori informazioni.  

5. Selezionare **Salva**.


## <a name="add-or-remove-members"></a>Aggiungere o rimuovere membri

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Membri** \> **Modifica**.

3. Eseguire una delle operazioni seguenti:
   - Per aggiungere membri, selezionare **Aggiungi membri,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva.**
   - Per rimuovere i membri, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva**. 

4. Selezionare **di nuovo Salva.**

## <a name="add-or-remove-permissions-of-members"></a>Aggiungere o rimuovere le autorizzazioni dei membri

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Membri** \> **Personalizza autorizzazioni**.

3. Selezionare **Modifica** accanto all'autorizzazione che si desidera modificare per un membro. 

4. Eseguire una delle operazioni seguenti:
   - Per concedere l'autorizzazione a un altro membro, selezionare **Aggiungi autorizzazioni,** cercare o selezionare un membro da aggiungere e quindi selezionare **Salva**.
   - Per rimuovere l'autorizzazione da un membro, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi selezionare **Salva**. 

4. Selezionare **di nuovo Salva.**

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Mostrare o nascondere una cassetta postale condivisa nell'elenco indirizzi globale

Se si sceglie di non visualizzare la cassetta postale condivisa nell'elenco indirizzi globale, la cassetta postale non verrà visualizzata nell'elenco indirizzi dell'organizzazione, ma riceverà comunque la posta elettronica inviata. 

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Mostra nell'elenco indirizzi globale** \> **Modifica**.

3. Impostare l'interruttore **su Attivato** o **Disattivato.** 

4. Selezionare **Salva**.

> [!NOTE]
> Nascondere una cassetta postale condivisa dall'elenco indirizzi non rende impossibile per i nuovi membri della cassetta postale condivisa aggiungere la cassetta postale nascosta al proprio profilo di Outlook finché la cassetta postale condivisa non viene nuovamente visualizzata nell'elenco indirizzi. 

## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)