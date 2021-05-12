---
title: Gestire le sottoscrizioni di iscrizione self-service
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Informazioni su come gestire le sottoscrizioni di iscrizione self-service gratuite per l'organizzazione.
ms.date: 03/17/2021
ms.openlocfilehash: b469515a649399c71ef64ba2567dfa376f21e9a7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333219"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Gestire le sottoscrizioni di iscrizione self-service

## <a name="what-are-self-service-sign-up-subscriptions"></a>Che cosa sono le sottoscrizioni di iscrizione self-service?

È disponibile un numero limitato di sottoscrizioni di iscrizione self-service gratuite per gli utenti dell'organizzazione a cui iscriversi. Un utente può iscriversi e usare una sottoscrizione di iscrizione self-service solo per se stesso. È possibile gestire le sottoscrizioni di iscrizione in modalità self-service bloccando la registrazione degli utenti ed eliminando le sottoscrizioni gratuite a cui gli utenti si sono registrati. Per ulteriori informazioni sull'iscrizione in modalità self-service e sulle sottoscrizioni disponibili, vedere [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Visualizzare un elenco di sottoscrizioni di iscrizione self-service

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** seleziona l'icona del filtro, quindi seleziona **Gratuito.** Viene visualizzato un elenco di tutte le sottoscrizioni di iscrizione in modalità self-service.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>In che modo queste sottoscrizioni sono diverse dalle sottoscrizioni di acquisto in modalità self-service?

Le sottoscrizioni di iscrizione self-service sono gratuite e sono disponibili per un elenco più ampio di prodotti rispetto alle sottoscrizioni di acquisto self-service. Quando un utente si i iscrizione a una sottoscrizione di acquisto self-service, è responsabile del pagamento. Le sottoscrizioni di acquisto self-service sono disponibili solo per i prodotti Power Platform (Power BI, Power Apps e Power Automate), Project e Visio. Per ulteriori informazioni, vedere [Domande frequenti sugli acquisti in self-service.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>Impedire agli utenti di iscriversi

Utilizzare il cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) con il parametro **AllowAdHocSubscriptions** per controllare se gli utenti possono iscriversi per le sottoscrizioni di iscrizione self-service. Per ulteriori informazioni, vedere [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Eliminare una sottoscrizione di iscrizione self-service

> [!IMPORTANT]
> Quando si elimina una sottoscrizione di iscrizione self-service, tutti gli utenti non possono accedere ai propri dati e alla posta elettronica ed eliminare tutti i dati e i messaggi di posta elettronica.

1. Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.
2. Nella scheda **Prodotti** seleziona l'icona del filtro, quindi seleziona **Gratuito.**
3. Selezionare la sottoscrizione di iscrizione self-service che si desidera eliminare. 
4. Nella sezione Impostazioni di pagamento e sottoscrizioni della pagina dei dettagli **dell'abbonamento** selezionare **Elimina sottoscrizione.**
5. Nel riquadro **Elimina sottoscrizione** selezionare la casella di controllo, quindi selezionare **Elimina sottoscrizione.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ho una sottoscrizione di iscrizione self-service che blocca l'eliminazione della directory

I prodotti di iscrizione self-service a cui i singoli utenti possono iscriversi possono anche creare un utente guest per l'autenticazione nella directory di Azure AD. Per evitare la perdita di dati, questi prodotti self-service bloccano le eliminazioni delle directory fino a quando non vengono completamente eliminati dalla directory. Possono essere eliminati solo dall'amministratore di Azure AD. Per ulteriori informazioni, vedere [Eliminare una directory in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-delete-howto)
