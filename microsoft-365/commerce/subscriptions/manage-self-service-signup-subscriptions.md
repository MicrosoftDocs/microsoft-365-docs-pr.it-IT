---
title: Gestione delle sottoscrizioni di iscrizione self-service
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
- MET150
description: Informazioni su come gestire le sottoscrizioni di registrazione Self-Service gratuite per l'organizzazione.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376306"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Gestione delle sottoscrizioni di iscrizione self-service

## <a name="what-are-self-service-sign-up-subscriptions"></a>Che cosa sono le sottoscrizioni di iscrizione self-service?

È disponibile un numero limitato di sottoscrizioni di iscrizione self-service gratuite per gli utenti dell'organizzazione a cui iscriversi. Un utente può solo iscriversi e utilizzare una sottoscrizione di iscrizione self-service per se stessi. È possibile gestire le sottoscrizioni di iscrizione self-service bloccando gli utenti dall'iscrizione e eliminando gratuitamente gli abbonamenti a cui gli utenti hanno effettuato l'accesso. Per ulteriori informazioni sull'accesso self-service e le sottoscrizioni disponibili, vedere [using self-service sign up nella propria organizzazione](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Visualizzazione di un elenco di sottoscrizioni di iscrizione self-service

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **prodotti** selezionare l'icona filtro e quindi fare clic su **libera**. Viene visualizzato un elenco di tutte le sottoscrizioni di iscrizione self-service.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>In che modo queste sottoscrizioni sono diverse dagli abbonamenti all'acquisto in modalità self-service?

Le sottoscrizioni di iscrizione self-service sono gratuite e sono disponibili per un elenco di prodotti più esteso rispetto alle sottoscrizioni di acquisto self-service. Quando un utente si iscrive a un abbonamento di acquisto in modalità self-service, è responsabile del pagamento. Le sottoscrizioni di acquisto self-service sono disponibili solo per i prodotti Power Platform (Power BI, Power Apps e Power automatizzate), Project e Visio. Per ulteriori informazioni, vedere [domande frequenti sull'acquisto in modalità self-service](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Bloccare gli utenti dall'iscrizione

Utilizzare il cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) con il parametro **AllowAdHocSubscriptions** per controllare se gli utenti possono iscriversi per le sottoscrizioni di iscrizione self-service. Per ulteriori informazioni, vedere [come si controllano le impostazioni self-service?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Eliminare una sottoscrizione di iscrizione self-service

> [!IMPORTANT]
> Quando si elimina una sottoscrizione di registrazione in modalità self-service, tutti gli utenti possono accedere ai propri dati e alla posta elettronica ed eliminare tutti i dati e la posta elettronica.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **prodotti** selezionare l'icona filtro e quindi fare clic su **libera**.
3. Selezionare l'abbonamento di iscrizione self-service che si desidera eliminare. 
4. Nella sezione **abbonamenti e impostazioni di pagamento** della pagina Dettagli sottoscrizione selezionare **Elimina sottoscrizione**.
5. Nel riquadro **Elimina sottoscrizione** , selezionare la casella di controllo, quindi selezionare **Elimina sottoscrizione**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Si dispone di una sottoscrizione di iscrizione self-service che blocca l'eliminazione della directory

I prodotti di iscrizione self-service che i singoli utenti possono iscriversi per creare anche un utente Guest per l'autenticazione nella directory di Azure AD. Per evitare la perdita di dati, questi prodotti self-service bloccano l'eliminazione della directory fino a quando non vengono completamente eliminati dalla directory. Possono essere eliminati solo dall'amministratore di Azure AD. Per ulteriori informazioni, vedere [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).