---
title: Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365
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
description: Creare un ambiente Microsoft 365 per testare l'accesso di identità e dispositivi per l'autenticazione solo per cloud.
ms.openlocfilehash: 537718eb0efcffc296162a4458158efcbdad9986
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051545"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365

*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

[Le configurazioni di identità e](../security/defender-365-security/microsoft-365-policies-configurations.md) accesso ai dispositivi sono un set di configurazioni consigliate e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD).

In questo articolo viene descritto come configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti della [configurazione dei prerequisiti solo per cloud](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.

Le fasi principali della configurazione dell'ambiente di testing sono otto:

1. Creare l'ambiente di testing semplificato
2. Configurare le posizioni specifiche
3. Configurare la reimpostazione self-service delle password
4. Configurare l’autenticazione a più fattori
5. Abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti al dominio
6. Configurare la protezione con password di Azure AD 
7. Abilitare Azure AD Identity Protection
8. Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fase 1: creare l'ambiente di testing semplificato di Microsoft 365 

Seguire le istruzioni riportate in [Configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
Di seguito è riportata la configurazione risultante.

![Ambiente di testing semplificato di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a>Fase 2: configurare le posizioni specifiche

Prima di tutto è necessario determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.

Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche. 

## <a name="phase-3-configure-self-service-password-reset"></a>Fase 3: configurare la reimpostazione della password in modalità self-service

Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:

- Utente 2
- Utente 3
- Utente 4
- Utente 5

Testare la reimpostazione della password solo per l'account Utente 2.

## <a name="phase-4-configure-multi-factor-authentication"></a>Fase 4: configurare l'autenticazione a più fattori

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:

- Utente 2
- Utente 3
- Utente 4
- Utente 5

Testare l'autenticazione a più fattori solo per l'account Utente 2.

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Fase 5: abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti al dominio 

Segui [queste istruzioni per](/azure/active-directory/devices/hybrid-azuread-join-plan) abilitare la registrazione automatica dei dispositivi dei computer Windows aggiunti al dominio.

## <a name="phase-6-configure-azure-ad-password-protection"></a>Fase 6: configurare la protezione con password di Azure AD 

Seguire [queste istruzioni](/azure/active-directory/authentication/concept-password-ban-bad) per bloccare le password deboli note e le relative varianti.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Fase 7: abilitare Azure AD Identity Protection

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 8: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online

Per Exchange Online, fare clic su [queste istruzioni](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Per Skype for Business Online:

1. Connettere a [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Eseguire questo comando.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Verificare che la modifica sia stata applicata con questo comando.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Il risultato è un ambiente di testing che soddisfa i requisiti della configurazione dei prerequisiti solo [cloud](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) per l'identità e l'accesso ai dispositivi. 

## <a name="next-step"></a>Passaggio successivo

Usare i [criteri comuni di identità e accesso ai dispositivi](../security/defender-365-security/identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test per identità aggiuntive](m365-enterprise-test-lab-guides.md#identity)

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)
