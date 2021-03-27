---
title: Attivare le impostazioni predefinite di sicurezza
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come le impostazioni predefinite di sicurezza consentono di proteggere l'organizzazione da attacchi correlati all'identità fornendo impostazioni di sicurezza preconfigurate.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398292"
---
# <a name="turn-on-security-defaults"></a>Attivare le impostazioni predefinite di sicurezza

Le impostazioni predefinite di sicurezza consentono di proteggere l'organizzazione da attacchi correlati all'identità fornendo impostazioni di sicurezza preconfigurate gestite da Microsoft per conto dell'organizzazione. Queste impostazioni includono l'abilitazione dell'autenticazione a più fattori (MFA) per tutti gli amministratori e gli account utente. Per la maggior parte delle organizzazioni, le impostazioni predefinite di sicurezza offrono un buon livello di sicurezza aggiuntiva per l'accesso.

Per ulteriori informazioni sulle impostazioni predefinite di sicurezza e sui criteri applicati, vedere [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Se l'abbonamento è stato creato il 22 ottobre 2019 o dopo il 22 ottobre 2019, è possibile che siano state abilitate automaticamente le impostazioni per verificare &mdash; le impostazioni.

Per abilitare le impostazioni predefinite di sicurezza in Azure Active Directory (Azure AD) o per verificare se sono già abilitate:

1. Accedere all'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> con le credenziali di amministratore globale.

2. Nel riquadro sinistro selezionare **Mostra tutto e quindi** in Interfaccia di **amministrazione** selezionare Azure **Active Directory.**

3. Nel riquadro sinistro dell'interfaccia **di amministrazione di Azure Active Directory selezionare** Azure Active **Directory.**

4. Nel menu a sinistra del  dashboard seleziona Proprietà nella sezione **Gestisci.**

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Screenshot dell'interfaccia di amministrazione di Azure Active Directory che mostra il percorso della voce di menu Proprietà.":::

5. Nella parte inferiore della **pagina Proprietà** selezionare Gestisci impostazioni **predefinite sicurezza.**

6. Nel riquadro destro verrà visualizzata l'impostazione Abilita impostazioni **predefinite di** sicurezza. Se **si seleziona** Sì, le impostazioni predefinite di sicurezza sono già abilitate e non sono necessarie ulteriori azioni. Se le impostazioni predefinite di sicurezza non sono attualmente abilitate, selezionare **Sì** per abilitarle e quindi selezionare **Salva**.

> [!NOTE]
> Se si usano criteri di accesso condizionale, è necessario disattivarli prima di utilizzare le impostazioni predefinite di sicurezza.
>
> È possibile utilizzare impostazioni predefinite di sicurezza o criteri di accesso condizionale, ma non è possibile utilizzare entrambe le impostazioni contemporaneamente.

## <a name="consider-using-conditional-access"></a>Prendere in considerazione l'uso dell'accesso condizionale

Se l'organizzazione ha requisiti di sicurezza complessi o se è necessario un controllo più granulare sui criteri di sicurezza, è consigliabile utilizzare l'accesso condizionale anziché le impostazioni predefinite di sicurezza per ottenere una posizione di sicurezza simile o superiore. 

L'accesso condizionale consente di creare e definire criteri che reagiscono agli eventi di accesso e richiedono azioni aggiuntive prima che a un utente venga concesso l'accesso a un'applicazione o a un servizio. I criteri di accesso condizionale possono essere granulari e specifici, per consentire agli utenti di essere produttivi ovunque e in qualsiasi momento, ma anche di proteggere l'organizzazione.

Le impostazioni predefinite di sicurezza sono disponibili per tutti i clienti, mentre l'accesso condizionale richiede una licenza per uno dei piani seguenti:

- Azure Active Directory Premium P1 o P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 o E5
- Enterprise Mobility & Security E3 o E5

Se si desidera utilizzare l'accesso condizionale per configurare criteri equivalenti a quelli abilitati per le impostazioni predefinite di sicurezza, vedere le guide dettagliate seguenti:

- [Richiedere la MFA per amministratori](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Richiedi MFA per la gestione di Azure](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [Bloccare l'autenticazione legacy](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [Richiedere la MFA per tutti gli utenti](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Richiedi registrazione MFA di Azure AD](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Richiede Azure AD Identity Protection, che fa parte di Azure Active Directory Premium P2

Per ulteriori informazioni sull'accesso condizionale, vedere [Che cos'è l'accesso condizionale?](/azure/active-directory/conditional-access/overview) Per ulteriori informazioni sulla creazione di criteri di accesso condizionale, vedere [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).

> [!NOTE]
> Se si dispone di un piano o di una licenza che fornisce l'accesso condizionale ma non sono stati ancora creati criteri di accesso condizionale, è possibile utilizzare le impostazioni predefinite di sicurezza. Tuttavia, è necessario disattivare le impostazioni predefinite di sicurezza prima di poter utilizzare i criteri di accesso condizionale.
