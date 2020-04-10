---
title: Creazione di una cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Creare una cassetta postale condivisa consente di affidare a più utenti all'interno dell'azienda la responsabilità di leggere e rispondere ai messaggi di posta elettronica inviati a un unico indirizzo.
ms.openlocfilehash: 4469197628feb96980ec2d8b560048acba704c54
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212306"
---
# <a name="create-a-shared-mailbox"></a>Creare una cassetta postale condivisa 

> [!NOTE]
> Se l'organizzazione utilizza un ambiente Exchange ibrido, è necessario ricorrere all'interfaccia di amministrazione di Exchange per creare e gestire cassette postali condivise. Vedere [Creare cassette postali condivise nell'interfaccia di amministrazione di Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)<br><br>
> Se non si sa se creare una cassetta postale condivisa o un gruppo di Office 365 per Outlook, vedere [Confrontare gruppi](../create-groups/compare-groups.md) per indicazioni. Attualmente non è possibile eseguire la migrazione di una cassetta postale condivisa a un gruppo di Office 365. Se si vuole ottenere questa possibilità, inviare commenti e suggerimenti [votando qui](https://go.microsoft.com/fwlink/?linkid=871518).

Le cassette postali condivise consentono a un gruppo di persone di monitorare e inviare posta elettronica da un indirizzo di posta elettronica comune, come info@contoso.com. Quando un utente del gruppo risponde a un messaggio inviato alla cassetta postale condivisa, il messaggio di risposta sembrerà inviato dalla cassetta postale condivisa, non dal singolo utente.

Le cassette postali condivise includono un calendario condiviso. Sono molte le piccole aziende che trovano utile usare un calendario condiviso come posizione centralizzata in cui tutti possono inserire i propri appuntamenti. Ad esempio, se un'azienda ha 3 persone che effettuano visite presso clienti, tutte e tre possono usare il calendario condiviso per immettere gli appuntamenti. È un modo semplice per tenersi informati sulle reciproche posizioni.

Prima di creare una cassetta postale condivisa, leggere [Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) per altre informazioni.

## <a name="create-a-shared-mailbox-and-add-members"></a>Creare una cassetta postale condivisa e aggiungervi membri
  
1. Effettuare l’accesso con un account amministratore globale di Office 365 o con un account amministratore di Exchange. Se viene visualizzato il messaggio "**Non si dispone dell'autorizzazione necessaria per accedere a questa pagina o eseguire questa azione**", non si è amministratori. 

::: moniker range="o365-worldwide"

2. Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.

::: moniker-end

::: moniker range="o365-germany"

2. Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041) passare alla pagina **Gruppi** \> **Cassette postali condivise**.

::: moniker-end

::: moniker range="o365-21vianet"

2. Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627) passare alla pagina **Gruppi** \> **Cassette postali condivise**.

::: moniker-end
    
3. Nella pagina **Cassette postali condivise** selezionare **+ Aggiungi cassetta postale**. Immettere un nome per la cassetta postale condivisa. La procedura guidata sceglie l'indirizzo di posta elettronica, ma è possibile cambiarlo.
    
    ![Assegnare un nome alla cassetta postale condivisa.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Selezionare **Aggiungi**. Potrebbero trascorrere alcuni minuti prima che si possa iniziare ad aggiungere membri.

5. In **Passaggi successivi** scegliere **Aggiungere membri a questa cassetta postale**. I membri sono le persone che potranno visualizzare la posta in entrata in questa cassetta postale condivisa e le risposte in uscita.

   ![Selezionare Aggiungi membri](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Selezionare il pulsante **+ Aggiungi membri**. Inserire un segno di spunta accanto alle persone a cui si vuole consentire di usare la cassetta postale condivisa, quindi selezionare **Salva**.

   ![Assegnare membri alla cassetta postale condivisa](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Selezionare **Chiudi**.

Si dispone di una cassetta postale condivisa che include un calendario condiviso. Procedere con il passaggio successivo: bloccare l'accesso per l'account della cassetta postale condivisa.

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Bloccare l'accesso per l'account della cassetta postale condivisa

Ogni cassetta postale condivisa ha un account utente corrispondente. Anche se non è stata richiesta una password al momento della creazione della cassetta postale condivisa, l'account dispone di una password, ma è generata dal sistema (sconosciuta). Non è necessario usare l'account per accedere alla cassetta postale condivisa.

Ma cosa succede se un amministratore reimposta semplicemente la password dell'account utente della cassetta postale condivisa, o se un utente malintenzionato accede alle credenziali dell'account della cassetta postale condivisa? In questo modo l'account utente potrebbe accedere alla cassetta postale condivisa e inviare messaggi di posta elettronica. Per evitare questo problema, è necessario bloccare l'accesso per l'account associato alla cassetta postale condivisa.

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nell'elenco di account utente individuare l'account della cassetta postale condivisa (ad esempio, impostare il filtro su **Utenti senza licenza**).

3. Selezionare l'utente per aprire il riquadro proprietà e quindi selezionare l'icona **Bloccare l’utente** ![Schermata dell'icona Bloccare l'utente](../../media/block-user-icon.png).

   **Nota**: se l'account è già bloccato, verrà visualizzato **Accesso bloccato** nella parte superiore e sull'icona sarà scritto **Sbloccare l’utente**.

4. Nel riquadro **Bloccare l'utente?**, selezionare **Blocca l'accesso dell'utente** e quindi selezionare **Salva modifiche**.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Nell'elenco di account utente individuare l'account della cassetta postale condivisa (ad esempio, impostare la visualizzazione su **Utenti senza licenza**) e selezionare l’account.

3. Nel riquadro a comparsa Proprietà, selezionare **Blocca l’accesso**.

    **Nota:** se l'account fosse già bloccato, il pulsante riporterebbe la scritta **Sblocca l’accesso**.

4. Nel riquadro a comparsa **Modifica stato di accesso**, verificare che l'opzione Blocca l'accesso dell'utente sia selezionata, selezionare **Salva** e quindi **Chiudi**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Nell'elenco di account utente individuare l'account della cassetta postale condivisa (ad esempio, impostare la visualizzazione su **Utenti senza licenza**) e selezionare l’account.

3. Nel riquadro a comparsa Proprietà, selezionare **Blocca l’accesso**.

    **Nota:** se l'account fosse già bloccato, il pulsante riporterebbe la scritta **Sblocca l’accesso**.

4. Nel riquadro a comparsa **Modifica stato di accesso**, verificare che l'opzione Blocca l'accesso dell'utente sia selezionata, selezionare **Salva** e quindi **Chiudi**.
::: moniker-end

Per istruzioni su come bloccare l'accesso per gli account con Azure AD PowerShell (anche per molti account contemporaneamente), vedere [Bloccare gli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).

## <a name="add-the-shared-mailbox-to-outlook"></a>Aggiungere la cassetta postale condivisa in Outlook

Se nell'azienda è abilitata l'impostazione AutoMapping (per impostazione predefinita, è abilitata nella maggior parte dei casi), la cassetta postale condivisa verrà visualizzata nell'app Outlook degli utenti automaticamente dopo la chiusura e il riavvio di Outlook. 

L'opzione AutoMapping viene impostata sulla cassetta postale dell'utente, non su quella condivisa.   Questo significa che se si cerca di usare un gruppo di sicurezza per gestire le autorizzazioni di accesso alla cassetta postale condivisa, AutoMapping non funziona. Se quindi si vuole usare questa impostazione, occorre assegnare le autorizzazioni in modo esplicito. L’opzione AutoMapping è attivata per impostazione predefinita. Per informazioni su come disattivarla, vedere [Rimuovere AutoMapping per una cassetta postale condivisa](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Per ulteriori informazioni sulle cassette postali condivise in Outlook, vedere:

- <a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Aprire e usare cassette postali condivise in Outlook</a>

- <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Aggiungere una cassetta postale condivisa in Outlook sul Web</a>

- <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Aggiungere una cassetta postale condivisa in Outlook per dispositivi mobili</a>

- <a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Aprire una cartella o una cassetta postale condivisa in Outlook per Mac</a>

- <a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Aggiungere regole a una cassetta postale condivisa</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Usare una cassetta postale condivisa in un dispositivo mobile (telefono o tablet)

È possibile accedere a una cassetta postale condivisa in un dispositivo mobile in due modi:
- Aggiungere la cassetta postale condivisa nell'<a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">app Outlook per iOS</a> o nell'<a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">app Outlook per Android per dispositivi mobili</a>. 
    
    Per le istruzioni, vedere <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Aggiungere una cassetta postale condivisa in Outlook per dispositivi mobili</a>.

- Aprire il browser, accedere a Office 365 e quindi passare a Outlook sul Web. Da Outlook sul web sarà possibile accedere alla cassetta postale condivisa.

    Per le istruzioni, vedere <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Aggiungere una cassetta postale condivisa in Outlook sul web</a>.

## <a name="use-the-shared-calendar"></a>Usare il calendario condiviso

Dopo aver creato la cassetta postale condivisa, viene creato automaticamente un calendario condiviso. Il calendario della cassetta postale condivisa viene in genere preferito a un calendario di SharePoint per tenere traccia degli appuntamenti e della posizione delle persone. Un calendario condiviso è integrato in Outlook ed è molto più facile da usare rispetto a un calendario di SharePoint.

1. Nell'app Outlook passare alla visualizzazione Calendario e selezionare la cassetta postale condivisa.

2. Quando si immette un appuntamento, ogni membro della cassetta postale condivisa potrà vederlo. 

3. Qualsiasi membro della cassetta postale condivisa può creare, visualizzare e gestire gli appuntamenti nel calendario, come gli appuntamenti personali. Tutti i membri della cassetta postale condivisa possono vedere le modifiche apportate al calendario condiviso.

## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)





