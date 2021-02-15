---
title: Chiudere il proprio account
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Scopri come chiudere l'account con Microsoft.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376318"
---
# <a name="close-your-account"></a>Chiudere il proprio account

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Quando si chiude l'account con Microsoft, verranno eliminate tutte le informazioni correlate all'account. Queste informazioni includono abbonamenti, licenze, modalità di pagamento, utenti e dati utente.

## <a name="before-you-begin"></a>Informazioni preliminari

Prima di iniziare questo processo, assicurarsi di eseguire il backup dei dati che si vogliono conservare.

Per eseguire le attività di questo articolo, è necessario essere un amministratore globale o di fatturazione. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Passaggio 1: eliminare gli utenti

Eliminare tutti gli utenti ad eccezione di un amministratore globale. L'amministratore globale completa i passaggi per chiudere l'account. Prima di eliminare la directory al termine di questo processo, è necessario eliminare tutti gli altri utenti.

Se gli utenti vengono sincronizzati dall'ambiente locale, disattivare prima la sincronizzazione, quindi eliminare gli utenti nella directory cloud utilizzando il portale di Azure o i cmdlet di Azure PowerShell.

Per eliminare gli utenti, vedere <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Amministratore gestione utenti: Eliminare uno o più utenti.</a>

È inoltre possibile utilizzare il cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> di PowerShell per eliminare gli utenti in blocco.

Se l'organizzazione usa Active Directory che si sincronizza con Microsoft Azure Active Directory (Azure AD), elimina invece l'account utente da Active Directory. Per istruzioni, vedere <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Eliminare in blocco gli utenti in Azure Active Directory.</a>

## <a name="step-2-cancel-all-active-subscriptions"></a>Passaggio 2: Annullare tutte le sottoscrizioni attive

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** trovare un abbonamento attivo. Selezionare **Altre azioni** (tre puntini), quindi selezionare **Annulla l’abbonamento**.
3. Nel riquadro **Annulla abbonamento** scegliere un motivo per cui si vuole annullare l'abbonamento. Se si vuole, inviare un feedback.
4. Selezionare **Salva**.
5. Ripetere i passaggi da 1 a 4 per annullare tutte le sottoscrizioni attive.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Passaggio 3: Eliminare tutte le sottoscrizioni disabilitate

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** selezionare una sottoscrizione disabilitata.
3. Nella sezione Impostazioni sottoscrizione e pagamento della pagina dei dettagli **dell'abbonamento** selezionare **Elimina sottoscrizione.**
4. Nel riquadro **Elimina sottoscrizione** selezionare **Elimina sottoscrizione.**
5. Nella finestra **di dialogo Elimina** sottoscrizione selezionare **Sì.**
6. Per ogni sottoscrizione disabilitata, ripetere i passaggi da 3 a 5 fino a eliminare tutte le sottoscrizioni.

> [!NOTE]
> Se non è possibile eliminare immediatamente una sottoscrizione disabilitata, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contattare il supporto tecnico</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Passaggio 4: Disabilitare l'autenticazione a più fattori

1. Accedere all'interfaccia di amministrazione con un account amministratore globale. Per verificare i ruoli di cui si dispone, vedere [Controllare i ruoli di amministratore nell'organizzazione.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)
2. Passare alla **pagina Utenti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">attivi.</a>
3. Scegliere **Autenticazione a più fattori.**
4. Nella pagina Autenticazione a più fattori disabilitare tutti gli account ad eccezione dell'account amministratore globale attualmente in uso.

È inoltre possibile <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">utilizzare PowerShell per disabilitare l'autenticazione</a>a più fattori per più utenti.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Passaggio 5: eliminare la directory in Azure Active Directory

1. Accedere all'interfaccia <a href="https://aad.portal.azure.com/" target="_blank">di amministrazione di Azure AD</a> con un account amministratore globale.
2. Selezionare **Azure Active Directory**.
3. Passare all'organizzazione che si desidera eliminare.
4. Selezionare **Elimina tenant.**
5. Se l'organizzazione non supera uno o più controlli, viene visualizzato un collegamento a ulteriori informazioni su come superare i controlli. Dopo aver superato tutti i controlli, selezionare **Elimina** per completare il processo.

Dopo aver completato questo passaggio finale, l'account con Microsoft viene chiuso ed eliminato.