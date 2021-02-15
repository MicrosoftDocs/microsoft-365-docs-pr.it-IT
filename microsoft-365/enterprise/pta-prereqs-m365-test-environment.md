---
title: Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente Microsoft 365 per testare l’accesso di identità e dispositivi con i prerequisiti per l'autenticazione pass-through.
ms.openlocfilehash: 71ba116ee45f031b156934e0924a0c3d460110d5
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233763"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a>Prerequisiti per l’accesso di identità e dispositivi per l’autenticazione pass-through nell’ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

[Le configurazioni di](../security/office-365-security/microsoft-365-policies-configurations.md) identità e accesso ai dispositivi sono un set di configurazioni e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi in Microsoft 365 per le aziende integrati con Azure Active Directory (Azure AD).

In questo articolo viene descritto come è possibile configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through ](../security/office-365-security/identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.

Esistono dieci fasi per configurare questo ambiente di testing:

1. Creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.
2. Configurare l’accesso unificato Single Sign-On di Azure AD
3. Configurare le posizioni specifiche
4. Configurare il writeback delle password
5. Configurare la reimpostazione self-service delle password
6. Configurare l’autenticazione a più fattori
7. Abilitare la registrazione automatica dei dispositivi di computer Windows aggiunti a un dominio
8. Configurare la protezione con password di Azure AD 
9. Abilitare Azure AD Identity Protection
10. Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a>Fase 1: creare un’organizzazione fittizia con autenticazione pass-through per l’ambiente di testing di Microsoft 365.

Seguire le istruzioni contenute in [Autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).

Di seguito è riportata la configurazione risultante.

![L'organizzazione fittizia con autenticazione pass-through per l’ambiente di testing](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Fase 2: configurare l’accesso unificato Single Sign-on di Azure AD

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per l’accesso Single Sign-on facile di Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Fase 3: configurare le posizioni specifiche

Prima di tutto determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.

Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche. 

## <a name="phase-4-configure-password-writeback"></a>Fase 4: configurare il writeback delle password

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per il writeback delle password.](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)

## <a name="phase-5-configure-self-service-password-reset"></a>Fase 5: configurare la reimpostazione delle password self-service 

Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:

- Utente 2
- Utente 3
- Utente 4
- Utente 5

Testare la reimpostazione della password solo per l'account Utente 2.

## <a name="phase-6-configure-multi-factor-authentication"></a>Fase 6: configurare l’autenticazione a più fattori

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:

- Utente 2
- Utente 3
- Utente 4
- Utente 5

Testare l'autenticazione a più fattori solo per l'account Utente 2.

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Fase 7: abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti a un dominio 

Segui [queste istruzioni per](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti a un dominio.

## <a name="phase-8-configure-azure-ad-password-protection"></a>Fase 8: configurare la protezione con password di Azure AD 

Seguire [queste istruzioni](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) per bloccare le password deboli note e le relative varianti.

## <a name="phase-9-enable-azure-ad-identity-protection"></a>Fase 9: abilitare Azure AD Identity Protection

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 10: abilitare l'autenticazione moderna per Exchange Online e Skype for Business online

Per Exchange Online, fare clic su [queste istruzioni](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Per Skype for Business Online:

1. Connettere a [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Eseguire questo comando.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Verificare che la modifica sia stata applicata con questo comando.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Il risultato è un ambiente di testing che soddisfa i requisiti di [Configurazione dei prerequisiti di autenticazione pass-through](../security/office-365-security/identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi. 

## <a name="next-step"></a>Passaggio successivo

Usare i [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test per identità aggiuntive](m365-enterprise-test-lab-guides.md#identity)

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

