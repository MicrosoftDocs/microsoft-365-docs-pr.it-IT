---
title: Configurare una cassetta postale condivisa
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
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Dopo aver creato una cassetta postale condivisa, è necessario configurare alcune impostazioni per gli utenti, ad esempio l'inoltro della posta elettronica e le risposte automatiche. Successivamente, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale o i membri.
ms.openlocfilehash: 63d3d0a5867875344ff4635071bbbad69e02eadc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629048"
---
# <a name="configure-a-shared-mailbox"></a>Configurare una cassetta postale condivisa

Dopo aver [creato una cassetta postale condivisa](create-a-shared-mailbox.md), è necessario configurare alcune impostazioni per gli utenti delle cassette postali, ad esempio l'inoltro della posta elettronica e le risposte automatiche. Successivamente, potrebbe essere necessario modificare altre impostazioni, ad esempio il nome della cassetta postale, i membri o le autorizzazioni per i membri. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Modificare il nome o l'alias di posta elettronica di una cassetta postale condivisa o modificare l'indirizzo di posta elettronica principale

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare e quindi fare clic su **modifica** accanto a **nome, posta elettronica, alias di posta elettronica**.

3. Immettere un nuovo nome o aggiungere un altro alias. Se si desidera modificare l'indirizzo di posta elettronica principale, la cassetta postale deve disporre di più di un alias di posta elettronica.

4. Selezionare **Salva**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Inoltrare messaggi di posta elettronica inviati a una cassetta postale condivisa

Non è necessario assegnare una licenza alla cassetta postale condivisa per inoltrare la posta elettronica inviata. È possibile inoltrare i messaggi a qualsiasi indirizzo di posta elettronica o elenco di distribuzione valido.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare \> **modifica** **inoltro della posta elettronica** .
    
3. Impostare l'interruttore **su**attivato e immettere un indirizzo di posta elettronica a cui inoltrare i messaggi. Può essere un qualsiasi indirizzo di posta elettronica valido. Per inoltrare a più indirizzi, è necessario [creare un gruppo di distribuzione](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) per gli indirizzi e quindi immettere il nome del gruppo in questa casella.
    
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

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare \> **modifica** **risposte automatiche** .
    
3. Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.

4. Immettere la risposta da inviare alle persone interne all'organizzazione. Non è possibile aggiungere immagini, solo testo.

5. Se si desidera inviare una risposta *anche* alle persone esterne all'organizzazione, selezionare la casella di controllo, per cui si desidera ottenere la risposta e digitare il testo. Non è possibile inviare risposte solo a persone esterne all'organizzazione, escludendo quelle interne.

6. Selezionare **Salva**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Consentire a tutti di visualizzare la posta inviata (le risposte)

Per impostazione predefinita, i messaggi inviati dalla cassetta postale condivisa non vengono salvati nella relativa cartella Posta inviata, bensì nella cartella Posta inviata della persona che ha inviato il messaggio.

Se si desidera consentire a tutti di visualizzare il messaggio di posta elettronica inviato, nell'interfaccia di amministrazione modificare le impostazioni della cassetta postale condivisa e selezionare \> **modifica** **elementi inviati** .


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Scegliere le app che possono essere utilizzate da una cassetta postale condivisa per accedere a Microsoft e-mail

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare \> **modifica** **app di posta elettronica** .

3. Impostare l'interruttore **su** attivato per tutte le app che si desidera siano in grado di utilizzare per accedere alla cassetta postale condivisa. Impostare l'interruttore su **disattivato** per tutte le applicazioni che non si desidera utilizzare. 

4. Selezionare **Salva**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Inserire una cassetta postale condivisa sul blocco per controversia legale

Per ulteriori informazioni sul blocco per controversia legale, vedere [creare un blocco per controversia legale](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si \> **desidera modificare,** quindi selezionare **blocco per controversia legale** .

3. Impostare l'interruttore **su**attivato. 

4. Facoltativamente, immettere una durata, una nota s relativa all'esenzione e un URL con ulteriori informazioni.  

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

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **membri** \> **Edit**.

3. Eseguire una delle operazioni seguenti:
   - Per aggiungere membri, selezionare **Aggiungi membri**, cercare o selezionare un membro da aggiungere e quindi fare clic su **Salva**.
   - Per rimuovere membri, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro e quindi fare clic su **Salva**. 

4. Selezionare **Salva** di nuovo.

## <a name="add-or-remove-permissions-of-members"></a>Aggiungere o rimuovere autorizzazioni per i membri

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Gruppi** > **Cassette postali condivise**. 

::: moniker-end

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **membri** \> **Customize Permissions**.

3. Selezionare **modifica** accanto all'autorizzazione che si desidera modificare per un membro. 

4. Eseguire una delle operazioni seguenti:
   - Per concedere tale autorizzazione a un membro aggiuntivo, selezionare **Aggiungi autorizzazioni**, cercare o selezionare un membro da aggiungere e quindi fare clic su **Salva**.
   - Per rimuovere l'autorizzazione da un membro, utilizzare la casella di ricerca per cercare il membro, se necessario, selezionare la **X** accanto al nome del membro, quindi selezionare **Salva**. 

4. Selezionare **Salva** di nuovo.

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

2. Selezionare la cassetta postale condivisa che si desidera modificare, quindi selezionare **Mostra in** \> **modifica**elenco indirizzi globale.

3. Impostare l'interruttore **su attivata** o **disattivata**. 

4. Selezionare **Salva**.

> [!NOTE]
> La disattivazione di una cassetta postale condivisa dall'elenco indirizzi renderà impossibile per i nuovi membri della cassetta postale condivisa aggiungere la cassetta postale nascosta al proprio profilo di Outlook fino a quando la cassetta postale condivisa non verrà nuovamente visualizzata nell'elenco indirizzi. 

## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)
