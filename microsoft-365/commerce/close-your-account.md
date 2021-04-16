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
ms.openlocfilehash: 44428654946d31ad249bfd3e7a3609da3e3634a6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860548"
---
# <a name="close-your-account"></a>Chiudere il proprio account

Quando si chiude l'account con Microsoft, verranno eliminate tutte le informazioni correlate all'account. Queste informazioni includono abbonamenti, licenze, modalità di pagamento, utenti e dati utente.

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare questo processo, assicurarsi di eseguire il backup dei dati che si vogliono conservare.

È necessario essere un amministratore globale o un amministratore di fatturazione per eseguire le procedure descritte in questo articolo. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Passaggio 1: eliminare gli utenti

Eliminare tutti gli utenti ad eccezione di un amministratore globale. L'amministratore globale completa i passaggi per chiudere l'account. Prima di poter eliminare la directory al termine di questo processo, è necessario eliminare tutti gli altri utenti.

Se gli utenti vengono sincronizzati da locale, disattivare prima la sincronizzazione, quindi eliminare gli utenti nella directory cloud utilizzando il portale di Azure o i cmdlet di Azure PowerShell.

Per eliminare gli utenti, vedere <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Amministratore gestione utenti: Eliminare uno o più utenti</a>.

È inoltre possibile utilizzare il cmdlet <a href="https://docs.microsoft.com/powershell/module/msonline/remove-msoluser">Remove-MsolUser</a> PowerShell per eliminare gli utenti in blocco.

Se l'organizzazione usa Active Directory che si sincronizza con Microsoft Azure Active Directory (Azure AD), eliminare invece l'account utente da Active Directory. Per istruzioni, vedere <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Eliminazione in blocco degli utenti in Azure Active Directory.</a>

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
4. Nel riquadro **Elimina sottoscrizione** selezionare **Elimina sottoscrizione**.
5. Nella finestra **di dialogo** Elimina sottoscrizione selezionare **Sì.**
6. Per ogni sottoscrizione disabilitata, ripetere i passaggi da 3 a 5 finché non vengono eliminate tutte le sottoscrizioni.

> [!NOTE]
> Se non è possibile eliminare immediatamente una sottoscrizione disabilitata, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contattare il supporto tecnico</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Passaggio 4: Disabilitare l'autenticazione a più fattori

1. Accedi all'interfaccia di amministrazione con un account amministratore globale. Per verificare quali ruoli si hanno, vedere [Controllare i ruoli di amministratore nell'organizzazione.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)
2. Passare alla **pagina Utenti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">utenti</a> attivi.
3. Scegliere **Autenticazione a più fattori.**
4. Nella pagina Autenticazione a più fattori disabilitare tutti gli account ad eccezione dell'account amministratore globale attualmente in uso.

È inoltre possibile <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">utilizzare PowerShell per disabilitare l'autenticazione a più fattori per più utenti.</a>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Passaggio 5: Eliminare la directory in Azure Active Directory

1. Accedere <a href="https://aad.portal.azure.com/" target="_blank">all'interfaccia di amministrazione di Azure AD</a> con un account amministratore globale.
2. Selezionare **Azure Active Directory**.
3. Passare all'organizzazione che si desidera eliminare.
4. Selezionare **Elimina tenant**.
5. Se l'organizzazione non supera uno o più controlli, viene visualizzato un collegamento a ulteriori informazioni su come superare i controlli. Dopo aver superato tutti i controlli, selezionare **Elimina** per completare il processo.

Dopo aver completato questo passaggio finale, l'account con Microsoft viene chiuso ed eliminato.