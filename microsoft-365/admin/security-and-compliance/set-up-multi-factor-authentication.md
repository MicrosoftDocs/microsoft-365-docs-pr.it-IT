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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Scopri come configurare l'autenticazione a più fattori per l'organizzazione.
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083539"
---
# <a name="set-up-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori
  
Basandosi sulla conoscenza dell'[autenticazione a più fattori (MFA) e del relativo supporto in Microsoft 365](multi-factor-authentication-microsoft-365.md), è ora di configurarla e implementarla nell'organizzazione.

Prima di iniziare, determinare se queste condizioni speciali sono valide per la propria situazione ed eseguire l'azione appropriata:

- Se si hanno client di Office 2013 su dispositivi Windows, [abilitare Autenticazione moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Se si hanno servizi directory di terze parti con Active Directory Federation Services (ADFS), configurare il server Azure MFA. Per altre informazioni, vedere [Scenari avanzati con server di autenticazione a più fattori di Azure e soluzioni VPN di terze parti](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario. Per altre informazioni, vedere [Metodo e impostazioni di verifica a due fattori](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Passaggio 1: scegliere il metodo per richiedere agli utenti di usare la MFA

> [!NOTE]
> Per eseguire questi passaggi, è necessario essere un amministratore globale o modificare MFA. Sono disponibili tre modi per richiedere agli utenti di usare la MFA per gli accessi. Per informazioni dettagliate, vedere [Supporto all’autenticazione a più fattori in Microsoft 365](multi-factor-authentication-microsoft-365.md).

- Impostazioni predefinite di sicurezza (consigliate per le piccole imprese)

  Se è stato acquistato un abbonamento o una versione di valutazione dopo il 21 ottobre 2019 e in modo imprevisto viene richiesta la MFA, le [impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) sono state abilitate automaticamente per l'abbonamento.
  
  Nei nuovi abbonamenti a Microsoft 365 le impostazioni predefinite per la sicurezza sono attivate automaticamente. Ciò significa che ogni utente dovrà configurare l'autenticazione a più fattori e installare l'app Microsoft Authenticator nel proprio dispositivo mobile.

  Tutti gli utenti devono usare l'app Microsoft Authenticator come metodo di verifica aggiuntivo e l'autenticazione legacy è bloccata. 

- Criteri di accesso condizionale (consigliati per le aziende)

  Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione della MFA.

- Account per utente (scelta non consigliata)

  Gli utenti scelgono il metodo di verifica aggiuntivo durante la registrazione della MFA.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Passaggio 2. Testare la MFA con gli utenti del programma pilota

Se si usano criteri di Accesso condizionale o MFA per utente (scelta non consigliata), selezionare gli utenti del programma pilota nell'azienda o nell'organizzazione per testare la registrazione e gli accessi della MFA. Per esempio:

- Per i criteri di Accesso condizionale, creare un gruppo di utenti del programma pilota e un criterio che richieda la MFA per i membri del gruppo e per tutte le app. Quindi, aggiungere gli account degli utenti del programma pilota al gruppo.

- Per la MFA per utente, abilitare la MFA per gli account degli utenti del programma pilota, uno alla volta.

Collaborare con gli utenti del programma pilota per risolvere le domande e i problemi e predisporre una distribuzione fluida nell'organizzazione.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Passaggio 3. Informare l'organizzazione della futura implementazione della MFA

Usare le notifiche tramite posta elettronica, manifesti nei corridoi, riunioni del team o corsi di formazione per garantire che i dipendenti comprendano:

- Perché è necessaria la MFA per gli accessi
- [Come registrarsi per il metodo di verifica aggiuntivo](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Come eseguire l'accesso dopo la registrazione](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Come cambiare il metodo di verifica aggiuntivo](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [Come gestire situazioni come un nuovo smartphone](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

Soprattutto, accertarsi che i dipendenti comprendano ***quando verrà imposto il requisito della MFA*** in modo da non coglierli di sorpresa.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Passaggio 4. Implementare il requisito della MFA nell'organizzazione o agli utenti

In base al metodo del requisito della MFA scelto, distribuire l'autenticazione MFA ai dipendenti oltre che agli utenti del programma pilota.

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro **Proprietà** di Azure Active Directory (Azure AD) nel portale di Azure.

1.  Accedere al [portale di amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.
2.  Passare alla [pagina Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.
4.  Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.

Se sono stati usati [criteri di accesso condizionale di base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), ecco come passare all'uso delle impostazioni predefinite di sicurezza.

1.  Passare alla pagina [Accesso condizionale - Criteri](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Scegliere ciascun criterio di base che è **Attivato** e impostare **Abilitare il criterio** su **Disattivato**.
2.  Passare alla [pagina Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.
5.  Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.

### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

Creare, configurare e abilitare i criteri appropriati che includono il gruppo di utenti che richiedono la MFA per l'accesso.

### <a name="per-user-mfa-not-recommended"></a>MFA per utente (scelta non consigliata)

Abilitare gli account utente per la MFA in base all'implementazione.

### <a name="supporting-your-employees"></a>Supporto dei dipendenti

Quando i dipendenti si registrano e iniziano a eseguire l'accesso con la MFA, assicurarsi che gli specialisti IT, il reparto IT o il supporto tecnico possano rispondere rapidamente alle domande e risolvere i problemi.

Vedere questo articolo per [informazioni sulla risoluzione dei problemi di accesso con la MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2). 


