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
ms.openlocfilehash: 34133f4204c1ee305b0a249a0ff8e0e9edaf5599
ms.sourcegitcommit: e891c7c25f351f10f250af3f483f68594976ddc9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "45153678"
---
# <a name="set-up-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori
  
Basandosi sulla conoscenza dell'[autenticazione a più fattori (MFA) e del relativo supporto in Microsoft 365](multi-factor-authentication-microsoft-365.md), è ora di configurarla e implementarla nell'organizzazione.

> [!IMPORTANT]
> Se è stato acquistato un abbonamento o una versione di valutazione dopo il 21 ottobre 2019 e viene richiesto di eseguire l'autenticazione MFA quando si accede, le [impostazioni di sicurezza predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) sono state abilitate automaticamente per l'abbonamento.


## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere un ammistratore globale per gestire l-autenticazione MFA. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../add-users/about-admin-roles.md).
- Se l'autenticazione MFA per persona è abilitata, è necessario [Disabilitare l'autenticazione MFA per persona ereditata](#turn-off-legacy-per-person-mfa).
- Se si hanno client di Office 2013 su dispositivi Windows, [attivare Autenticazione moderna per i client Office 2013](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).
- Avanzato: se si hanno servizi directory di terze parti con Active Directory Federation Services (ADFS), configurare il server Azure MFA. Per altre informazioni, vedere [Scenari avanzati con server di autenticazione a più fattori di Azure e soluzioni VPN di terze parti](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

## <a name="turn-security-defaults-on-or-off"></a>Attivare o disattivare le impostazioni di sicurezza predefinite

Per gran parte delle organizzazioni, le impostazioni di sicurezza predefinite offrono un buon livello di sicurezza aggiuntiva. Per altre informazioni, vedere [Che cosa sono le impostazioni predefinite per la sicurezza?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Se l'abbonamento è nuovo, l'impostazione predefinita della sicurezza potrebbe essere già attivata automaticamente.

È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro **Proprietà** di Azure Active Directory (Azure AD) nel portale di Azure.

1.  Accedere al [portale di amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.
2.  Nel riquadro di spostamento sinistro scegliere **Mostra tutto**, e in **Interfacce di amministrazione**scegliere **Azure Active Directory**.
3. In **Interfaccia di amministrazione di Azure Active Directory** scegliere **Azure Active Directory** > **Proprietà**.
3.  Nella parte inferiore della pagina scegliere **Gestire le impostazioni di sicurezza predefinite**.
4.  Scegliere **Sì** per abilitare le impostazioni di sicurezza predefinite o **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.

Se i [criteri di accesso condizionale di base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) sono stati usati, sarà richiesto di disattivarli prima di iniziare a usare le impostazioni di sicurezza predefinite.

1.  Passare alla pagina [Accesso condizionale - Criteri](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Scegliere ciascun criterio di base che è **Attivato** e impostare **Abilitare il criterio** su **Disattivato**.
2.  Passare alla [pagina Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.
5.  Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.

## <a name="use-conditional-access-policies"></a>È possibile utilizzare i criteri di accesso condizionale

Se l'organizzazione ha esigenze di sicurezza di accesso più granulare, i criteri di accesso condizionale possono offrire un maggiore controllo. L'accesso condizionale consente di creare e definire criteri che reagiscono agli eventi di autenticazione e richiedono altre azioni prima che un utente sia autorizzato ad accedere a un'applicazione o un servizio.

> [!IMPORTANT]
> Disabilitare sia la MFA per persona che le impostazioni di sicurezza prima di abilitare i criteri di accesso condizionale. 

L'accesso condizionale è disponibile per i clienti che hanno acquistato Azure AD Premium P1 o licenze che lo includono, come Microsoft 365 Business Premium e Microsoft 365 E3. Per altre informazioni, vedere [Creare un criterio di accesso condizionale](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).

L'accesso condizionale basato sul rischio è disponibile con la licenza P2 di Azure AD Premium o con licenze che lo includono, come Microsoft 365 E5. Per altre informazioni, vedere [Accesso condizionale basato sul rischio](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).

Per altre informazioni su Azure AD P1 e P2, vedere [Prezzi di Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="turn-on-modern-authentication-for-your-organization"></a>Attivare l'autenticazione moderna per la propria organizzazione

Per la maggior parte degli abbonamenti l'autenticazione moderna è attivata automaticamente, ma se l'abbonamento è stato acquistato molto tempo fa, potrebbe non essere disponibile. Deve essere attivato prima che la MFA funzioni correttamente con le app di Office.

1. Nell'interfaccia di amministrazione di Microsoft 365, ne riquadro di spostamento sinistro, scegliere **Impostazioni** > **Impostazioni organizzazione**.
1. Nella scheda **Servizi** tab, scegliere **Autenticazione moderna**, e nel riquadro **Autenticazione moderna**, verificare che **Abilita autenticazione moderna** sia selezionato. Selezionare **Salva modifiche**.

### <a name="turn-off-legacy-per-person-mfa"></a>Disabilitare l'autenticazione MFA per persona ereditata

Se l'autenticazione MFA per persona è stata attivata in precedenza, è necessario disattivarla prima di abilitare le impostazioni di sicurezza.

1. Nell'interfaccia di amministrazione di Microsoft 365, ne riquadro di spostamento sinistro, scegliere **Utenti** > **Utenti attivi**. 
1. Nella pagina **Utenti attivi**, scegliere **Autenticazione a più fattori**.
1. Nella pagina Autenticazione a più fattori, selezionare ogni utente e impostare il loro stato Autenticazione a più fattori su **Disabilitato**.

## <a name="next-steps"></a>Passaggi successivi

- [Come registrarsi per il metodo di verifica aggiuntivo](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Come eseguire l'accesso dopo la registrazione](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Come cambiare il metodo di verifica aggiuntivo](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [Come gestire situazioni come un nuovo smartphone](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)
- [Risolvere i problemi di autenticazione MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)




