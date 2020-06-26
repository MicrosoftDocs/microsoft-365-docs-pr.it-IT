---
title: Chiudere il proprio account
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Informazioni su come chiudere l'account con Microsoft.
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898922"
---
# <a name="close-your-account"></a>Chiudere il proprio account

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Quando si chiude l'account con Microsoft, verranno eliminate tutte le informazioni correlate all'account. Queste informazioni includono abbonamenti, licenze, modalità di pagamento, utenti e dati utente. Prima di iniziare questa procedura, verificare di eseguire il backup di tutti i dati che si desidera conservare.

## <a name="step-1-delete-users"></a>Passaggio 1: eliminare gli utenti

Eliminare tutti gli utenti ad eccezione di un amministratore globale che completa la procedura per chiudere l'account. Prima di poter eliminare la directory alla fine di questo processo, è necessario eliminare tutti gli altri utenti.

Se gli utenti vengono sincronizzati dall'ambiente locale, disattivare la sincronizzazione e quindi eliminare gli utenti nella directory cloud utilizzando il portale di Azure o i cmdlet di Azure PowerShell.

Per eliminare gli utenti, vedere <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User Management admin: Delete uno o più utenti</a>.

È inoltre possibile utilizzare il cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> di PowerShell per eliminare gli utenti in blocco.

Se nell'organizzazione viene utilizzato Active Directory che esegue la sincronizzazione con Azure AD, eliminare l'account utente da Active Directory. Per istruzioni, vedere <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">eliminare in blocco gli utenti in Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Passaggio 2: annullare tutte le sottoscrizioni attive

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .

2. Se l'elenco abbonamenti è in visualizzazione **tabella** , fare clic su **schede**sulla destra.

3. Per trovare un abbonamento attivo e nella sezione **impostazioni & azioni** , selezionare **Annulla sottoscrizione**.

4. Seguire le istruzioni visualizzate per completare il processo.

5. Ripetere i passaggi da 1 a 4 per annullare tutti gli abbonamenti attivi.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Passaggio 3: eliminare tutte le sottoscrizioni disabilitate

1. Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .

2. Se l'elenco abbonamenti è in visualizzazione **tabella** , fare clic su **schede**sulla destra.

3. Accanto a **stato sottoscrizione**, selezionare **disattivata**.

4. Trovare una sottoscrizione disabilitata e nella sezione **impostazioni & azioni** selezionare **Elimina**.

5. Nella finestra di dialogo **Elimina sottoscrizione** selezionare la casella di controllo **l'impatto** , quindi selezionare **Elimina sottoscrizione**.

6. Per ogni sottoscrizione disabilitata, ripetere i passaggi 4 e 5 finché tutte le sottoscrizioni non sono state eliminate.

## <a name="step-4-disable-multi-factor-authentication"></a>Passaggio 4: disabilitare l'autenticazione a più fattori

1. Nell'interfaccia di amministrazione, andare alla pagina **utenti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">attivi</a> .

2. Scegliere **l'autenticazione a più fattori**.

3. Nella pagina autenticazione a più fattori disabilitare tutti gli account tranne l'account di amministratore globale attualmente in uso.

È inoltre possibile <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">utilizzare PowerShell per disabilitare l'autenticazione a più fattori per più utenti</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Passaggio 5: eliminare la directory in Azure Active Directory

1. Accedere all'interfaccia di <a href="https://aad.portal.azure.com/" target="_blank">amministrazione di Azure ad</a> con un account di amministratore globale.

2. Selezionare **Azure Active Directory**.

3. Passare alla directory che si desidera eliminare.

4. Selezionare **Elimina directory**.

5. Se la directory ha esito negativo su uno o più controlli, viene visualizzato un collegamento a ulteriori informazioni su come superare i controlli. Dopo aver superato tutti i controlli, selezionare **Elimina** per completare il processo.

Dopo aver completato questo passaggio finale, l'account con Microsoft viene chiuso ed eliminato.
