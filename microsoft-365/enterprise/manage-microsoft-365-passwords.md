---
title: Gestire le password degli account utente di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Informazioni su come gestire le password degli account utente di Microsoft 365.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328510"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Gestire le password degli account utente di Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

È possibile gestire le password degli account utente di Microsoft 365 in diversi modi, a seconda della configurazione dell'identità. È possibile gestire gli account utente nell'interfaccia di [amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), in servizi di dominio Active Directory (ad DS) o nell'interfaccia di amministrazione di Azure Active Directory (Azure ad).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Pianificare la posizione e la modalità di gestione delle password degli account utente

Il percorso e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per Microsoft 365. I due modelli sono solo basati sul cloud e ibridi.
  
### <a name="cloud-only"></a>Solo cloud

È possibile gestire le password degli account utente in:

- [L'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- Interfaccia di amministrazione di Azure AD
    
### <a name="hybrid"></a>Ibrido

Con l'identità ibrida, le password vengono archiviate in servizi di dominio Active Directory, pertanto è necessario utilizzare gli strumenti di AD DS locali per gestire le password degli account utente. Anche quando si utilizza la sincronizzazione degli hash delle password (pH), in cui Azure AD archivia una versione con hash della versione già sottoposto a hash in servizi di dominio Active Directory, è necessario che gli utenti gestiscano le proprie password in servizi di dominio Active Directory.

Con il [writeback delle password](#pw_writeback), gli utenti possono modificare le password di servizi di dominio Active Directory tramite Azure ad.

## <a name="prevent-bad-passwords"></a>Impedire l'uso di password non consentite

Per creare le password degli account utente, tutti gli utenti devono attenersi alla [Guida alle password di Microsoft](https://www.microsoft.com/research/publication/password-guidance).

Per impedire agli utenti di creare password facilmente determinabili, usare la protezione password di Azure Active Directory, che usa sia un elenco di password non consentite globale che un elenco facoltativo di password non consentite personalizzato, specificato dall'utente. Ad esempio, è possibile specificare condizioni specifiche per l'organizzazione, come:

- Nomi di marchio
- Nomi di prodotto
- Posizioni, ad esempio la sede centrale aziendale
- Termini interni specifici della società
- Abbreviazioni con significato aziendale specifico

È possibile vietare le password non valide [nel cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e per il servizio di [dominio Active Directory locale](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

## <a name="simplify-user-sign-in"></a>Semplificare l'accesso utente

Azure AD seamless Single Sign-on (Azure AD seamless SSO) è compatibile con il pH e l'autenticazione pass-through (PTA), per consentire agli utenti di accedere ai servizi che utilizzano gli account utente di Azure AD senza dover digitare le password e, in molti casi, i nomi utente. In questo modo gli utenti possono facilmente accedere alle applicazioni basate su cloud come Office 365, senza aver bisogno di componenti aggiuntivi in loco quali ad esempio server federativi di identità.

L'accesso SSO facile di Azure AD viene configurato con lo strumento Azure AD Connect. Vedere le [istruzioni per configurare l'accesso SSO facile ad Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Semplificare gli aggiornamenti delle password in servizi di dominio Active Directory

Con il writeback delle password, è possibile consentire agli utenti di reimpostare le proprie password tramite Azure AD, che viene quindi replicato in servizi di dominio Active Directory. Gli utenti non devono accedere al servizio di dominio Active Directory locale per aggiornare le password. Questo risulta particolarmente utile per gli utenti remoti o mobili che non dispongono di una connessione remota alla rete locale.

Il writeback delle password è necessario per utilizzare al meglio le capacità di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.

Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Eseguire l'aggiornamento all'ultima versione di Azure AD Connect per poter usufruire della migliore esperienza possibile e delle nuove caratteristiche appena rilasciate. Per ulteriori informazioni, vedere [Istallazione personalizzata di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Semplificare le reimpostazioni delle password

La reimpostazione della password in modalità self-service (SSPR) consente agli utenti di reimpostare o sbloccare le password o gli account. Per segnalare abusi o usi impropri è possibile utilizzare la reportistica dettagliata, che tiene traccia degli accessi degli utenti al sistema, insieme alle notifiche. È necessario abilitare il [writeback delle password](#pw_writeback) prima di poter distribuire le reimpostazioni delle password.

Vedere le [istruzioni per implementare la reimpostazione della password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

