---
title: Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un ambiente Microsoft 365 per testare l'accesso di identità e dispositivi per l'autenticazione solo per cloud.
ms.openlocfilehash: aa18e1a9943ec12465737f6c3f2e12c1fa49e2a3
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398878"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Prerequisiti di accesso di identità e dispositivi solo per cloud nell’ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

[Le configurazioni di identità e accesso](../security/office-365-security/microsoft-365-policies-configurations.md) ai dispositivi sono un set di configurazioni e criteri di accesso condizionale per proteggere l'accesso a tutti i servizi integrati con Azure Active Directory (Azure AD).

In questo articolo viene descritto come configurare un ambiente di testing di Microsoft 365 che soddisfi i requisiti della [configurazione dei prerequisiti solo per cloud](../security/office-365-security/identity-access-prerequisites.md#prerequisites) per l’accesso di identità e dispositivi.

Le fasi principali della configurazione dell'ambiente di testing sono sette:

1.  Creare l'ambiente di testing semplificato
2.  Configurare le posizioni specifiche
3.  Configurare il writeback delle password
4.  Configurare la reimpostazione self-service delle password
5.  Configurare l’autenticazione a più fattori
6.  Abilitare Azure AD Identity Protection
7.  Abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fase 1: creare l'ambiente di testing semplificato di Microsoft 365 

Seguire le istruzioni riportate in [Configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
Di seguito è riportata la configurazione risultante.

![Ambiente di testing semplificato di Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a>Fase 2: configurare le posizioni specifiche

Prima di tutto è necessario determinare gli indirizzi IP pubblici o gli intervalli di indirizzi usati all'interno dell'organizzazione.

Quindi, seguire le istruzioni contenute in [Configurare le posizioni specifiche in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) per aggiungere gli indirizzi o gli intervalli di indirizzi come posizioni specifiche. 

## <a name="phase-3-configure-password-writeback"></a>Fase 3: configurare il writeback delle password

Seguire le istruzioni contenute in[Fase 2 della guida al lab di test sul writeback delle password](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-4-configure-self-service-password-reset"></a>Fase 4: configurare la reimpostazione delle password self-service

Seguire le istruzioni contenute nella [Fase 3 della guida al lab di test per la reimpostazione della password](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Quando si abilita la reimpostazione della password degli account in un determinato gruppo di Azure AD, aggiungere gli account al gruppo **Reimpostazione della password**:

- Utente 2
- Utente 3
- Utente 4
- Utente 5

Testare la reimpostazione della password solo per l'account Utente 2.

## <a name="phase-5-configure-multi-factor-authentication"></a>Fase 5: configurare l’autenticazione a più fattori

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) per gli account utente seguenti:

- Utente 2
- Utente 3
- Utente 4
- Utente 5

Testare l'autenticazione a più fattori solo per l'account Utente 2.

## <a name="phase-6-enable-azure-ad-identity-protection"></a>Fase 6: abilitare Azure AD Identity Protection

Seguire le istruzioni contenute nella [Fase 2 della guida al lab di test per Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 7: abilitare l'autenticazione moderna per Exchange Online e Skype for Business Online

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

Il risultato è un ambiente di testing che soddisfa i requisiti di [Configurazione dei prerequisiti solo per cloud](../security/office-365-security/identity-access-prerequisites.md#prerequisites) per l’identità e l’accesso dei dispositivi. 

## <a name="next-step"></a>Passaggio successivo

Usare i [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md) per configurare i criteri basati sui prerequisiti e proteggere identità e dispositivi.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test per identità aggiuntive](m365-enterprise-test-lab-guides.md#identity)

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
