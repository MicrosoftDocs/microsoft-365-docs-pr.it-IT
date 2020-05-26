---
title: Configurare l'autenticazione a più fattori per gli utenti
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Informazioni su come configurare l'autenticazione a più fattori per l'organizzazione.
monikerRange: o365-worldwide
ms.openlocfilehash: ca1a8bd47e2fa5bbd7b7aed396debefaad10ea5e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351716"
---
# <a name="set-up-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori
  
In base alla comprensione dell' [autenticazione a più fattori e del relativo supporto in Microsoft 365](multi-factor-authentication-microsoft-365.md), è necessario configurarlo e distribuirlo all'organizzazione.

Prima di iniziare, determinare se queste condizioni speciali si applicano all'utente e intraprendere le azioni appropriate:

- Se si dispone di client di Office 2013 nei dispositivi Windows, [abilitare l'autenticazione moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Se si dispone di servizi directory di terze parti con Active Directory Federation Services (AD FS), configurare il server Azure Mae. Per ulteriori informazioni, vedere [scenari avanzati con autenticazione a più fattori di Azure e soluzioni VPN di terze parti](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) .

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Passaggio 1: decidere il metodo per richiedere agli utenti di utilizzare il Master

Esistono tre modi per richiedere agli utenti di utilizzare il servizio di autenticazione utente per gli accessi. Per i dettagli, vedere [supporto di AMF in Microsoft 365](multi-factor-authentication-microsoft-365.md) .

- Impostazioni predefinite per la sicurezza (consigliata per le aziende di piccole dimensioni)

  Se si è acquistato l'abbonamento o la versione di valutazione dopo il 21 ottobre 2019 e si è inaspettatamente richiesto l'AMF, le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza sono state abilitate automaticamente per l'abbonamento.
  
  Ogni nuova sottoscrizione Microsoft 365 avrà automaticamente le impostazioni predefinite per la sicurezza attivate. Questo significa che ogni utente dovrà configurare il master e installare l'app Microsoft Authenticator sul proprio dispositivo mobile.

  Tutti gli utenti devono utilizzare l'app Microsoft Authenticator come metodo di verifica aggiuntivo e l'autenticazione legacy è bloccata. 

- Criteri di accesso condizionale (consigliato per le aziende)

  Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione dell'AMF.

- Account per utente (non consigliato)

  Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione dell'AMF.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Passaggio 2. Test dell'AMF per gli utenti pilota

Se si utilizzano criteri di accesso condizionale o AMF per utente (scelta non consigliata), selezionare gli utenti pilota nell'azienda o nell'organizzazione per testare la registrazione e gli accessi dell'AMF. Per esempio:

- Per i criteri di accesso condizionale, creare un gruppo di utenti pilota e un criterio che richiede l'AMF per i membri del gruppo e per tutte le app. Aggiungere quindi gli account dell'utente pilota al gruppo.

- Per l'autenticazione a livello di utente, abilitare l'AMF per gli account utente degli utenti pilota una volta.

Collaborare con gli utenti pilota per risolvere i problemi e le domande da preparare per una distribuzione uniforme all'organizzazione.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Passaggio 3: Informare l'organizzazione dell'arrivo dell'AMF

Utilizzare le notifiche di posta elettronica, i poster dei corridoi, le riunioni del team o la formazione formale per garantire che i dipendenti comprendano:

- Perché è necessario disporre dell'AMF per gli accessi
- [Come effettuare la registrazione per il metodo di verifica aggiuntivo](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [Come effettuare l'accesso dopo la registrazione](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [Come modificare il metodo di verifica aggiuntivo](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [Come gestire situazioni come un nuovo smartphone](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

Soprattutto, assicurarsi che i dipendenti comprendano ***quando il requisito dell'AMF verrà imposto in*** modo che non li sorprenda.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Passaggio 4. Implementazione del requisito AMF per l'organizzazione o gli utenti

In base al metodo di requisiti di AMF prescelto, distribuire l'autenticazione dell'AMF ai dipendenti oltre i tester pilota.

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro delle **Proprietà** di Azure Active Directory (Azure ad) nel portale di Azure.

1.  Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.
2.  Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.
4.  Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.

Se sono stati utilizzati i [criteri di accesso condizionale di base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), ecco come passare a utilizzo delle impostazioni predefinite di sicurezza.

1.  Passare alla [pagina Criteri di accesso condizionale](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Scegliere tutti i criteri di base che **sono attivi** e impostare **Attiva criterio** su **disattivato**.
2.  Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.
5.  Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.

### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

Creare, configurare e abilitare i criteri corretti che includono il gruppo di utenti che richiedono l'autenticazione a più fattori per l'accesso.

### <a name="per-user-mfa-not-recommended"></a>AMF per utente (non consigliata)

Abilitare gli account utente per l'AMF corrispondente all'implementazione.

### <a name="supporting-your-employees"></a>Supporto dei dipendenti

Quando i dipendenti si iscrivono e iniziano a eseguire l'accesso con l'AMF, assicurarsi che gli specialisti IT, il reparto IT o il supporto tecnico possano rispondere rapidamente a domande e risolvere i problemi.

Vedere questo articolo per [informazioni sulla risoluzione dei problemi relativi agli accessi dell'AMF](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2). 


