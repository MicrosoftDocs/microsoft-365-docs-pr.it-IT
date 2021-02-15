---
title: Gestire le sottoscrizioni di iscrizione self-service
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
description: Informazioni su come gestire le sottoscrizioni di iscrizione self-service gratuite per l'organizzazione.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376306"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Gestire le sottoscrizioni di iscrizione self-service

## <a name="what-are-self-service-sign-up-subscriptions"></a>Che cosa sono le sottoscrizioni di iscrizione self-service?

Per gli utenti dell'organizzazione è disponibile un numero limitato di sottoscrizioni di iscrizione self-service gratuite. Un utente può iscriversi e usare una sottoscrizione di iscrizione self-service solo per se stesso. Puoi gestire le sottoscrizioni di iscrizione self-service bloccando la registrazione degli utenti ed eliminando le sottoscrizioni gratuite a cui gli utenti hanno effettuato l'iscrizione. Per ulteriori informazioni sull'iscrizione self-service e sulle sottoscrizioni disponibili, vedere [Using self-service sign up in your organization.](../../admin/misc/self-service-sign-up.md)

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Visualizzare un elenco di sottoscrizioni di iscrizione self-service

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Libero.** Viene visualizzato un elenco di tutte le sottoscrizioni di iscrizione self-service.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>In che modo queste sottoscrizioni sono diverse da quelle per gli acquisti in modalità self-service?

Le sottoscrizioni di iscrizione self-service sono gratuite e sono disponibili per un elenco di prodotti più ampio rispetto alle sottoscrizioni di acquisto self-service. Quando un utente si i iscrizione a una sottoscrizione di acquisto self-service, è responsabile del pagamento. Le sottoscrizioni per gli acquisti self-service sono disponibili solo per i prodotti Power Platform (Power BI, Power Apps e Power Automate), Project e Visio. Per ulteriori informazioni, vedere [Domande frequenti sugli acquisti self-service.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>Impedire agli utenti di registrarsi

Utilizzare il cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) con il parametro **AllowAdHocSubscriptions** per controllare se gli utenti possono iscriversi per le sottoscrizioni di iscrizione self-service. Per ulteriori informazioni, vedere [Come si controllano le impostazioni self-service?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Eliminare una sottoscrizione di iscrizione self-service

> [!IMPORTANT]
> Quando si elimina una sottoscrizione di iscrizione self-service, tutti gli utenti non possono accedere ai propri dati e messaggi di posta elettronica ed eliminare tutti i dati e i messaggi di posta elettronica.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** selezionare l'icona del filtro, quindi **selezionare Libero.**
3. Selezionare la sottoscrizione di iscrizione self-service che si desidera eliminare. 
4. Nella sezione Sottoscrizioni e impostazioni di pagamento della pagina dei dettagli **dell'abbonamento** selezionare **Elimina sottoscrizione.**
5. Nel riquadro **Elimina sottoscrizione** selezionare la casella di controllo, quindi selezionare **Elimina sottoscrizione.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ho una sottoscrizione di iscrizione self-service che blocca l'eliminazione della directory

I prodotti di iscrizione self-service a cui i singoli utenti possono iscriversi possono anche creare un utente guest per l'autenticazione nella directory di Azure AD. Per evitare la perdita di dati, questi prodotti self-service bloccano le eliminazioni della directory fino a quando non vengono eliminati completamente dalla directory. Possono essere eliminati solo dall'amministratore di Azure AD. Per ulteriori informazioni, vedere [Eliminare una directory in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)