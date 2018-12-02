---
title: 'Passaggio 7: sincronizzazione delle identità'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere le opzioni di identità e configurare Azure AD Connect per sincronizzare il Windows Server AD locale con Azure AD.
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868353"
---
# <a name="step-7-synchronize-identities"></a>Passaggio 7: sincronizzazione delle identità

*Questo passaggio è obbligatorio per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Questo passaggio consente di sincronizzare l'ambiente Windows Server Active Directory (AD) con il tenant Azure Active Directory (AD) utilizzato per gli abbonamenti a Office 365 Enterprise Mobility + Security (EMS).

Azure AD Connect è lo strumento Microsoft che guida gli amministratori nel processo di sincronizzazione di quelle identità degli ambienti Windows Server AD con una o più foreste che sono necessarie per il proprio tenant Azure AD.

![Modalità di Azure AD Connect per sincronizzare la directory locale con Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

*Modalità di Azure AD Connect per sincronizzare la directory locale con Azure AD*

La prima decisione relativa alla soluzione delle identità ibride, riguarda i requisiti di autenticazione. Le opzioni sono le seguenti:

- Con l'**autenticazione gestita**, Azure AD gestisce il processo di autenticazione per l'accesso utente. Esistono due metodi di autenticazione gestita: 
    - **Sincronizzazione degli hash delle password (PHS)**[Opzione consigliata e obbligatoria per alcune funzionalità premium]. Questo è il modo più semplice per abilitare l'autenticazione per gli oggetti directory locali in Azure AD. Azure AD Connect estrae l'hash delle password da Windows Server AD, esegue ulteriori procedure di sicurezza sulla password e la salva in Azure AD. Per ulteriori informazioni, vedere [Implementare la sincronizzazione degli hash delle password con la sincronizzazione Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - L'**autenticazione pass-through (PTA)** offre una soluzione semplice di convalida della password per i servizi basati su Azure AD. La PTA utilizza un agente su uno o più server locali per convalidare le autenticazioni utente direttamente da Windows Server AD locale. Per ulteriori informazioni, vedere [Accesso utente con autenticazione pass-through di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Con l'**autenticazione federata**, il processo di autenticazione viene reindirizzato a un altro provider di identità tramite un server federativo di identità, come Active Directory Federation Services (ADFS), per l'accesso utente. Il provider di identità può fornire altri metodi di autenticazione, ad esempio l'autenticazione basata su una smart card. Per ulteriori informazioni, vedere [Scegliere il giusto metodo di autenticazione per la soluzione delle identità ibride di Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Una volta determinata la soluzione delle identità ibride, scaricare ed eseguire lo [Strumento IdFix DirSync Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) per analizzare Windows Server AD e cercare eventuali problemi.

Dopo aver risolto tutti i problemi identificati tramite lo strumento IdFix, vedere [Implementazione della sincronizzazione hash delle password](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) per installare lo strumento Azure AD Connect e configurare la sincronizzazione di directory tra Windows Server AD locale e il tenant Azure AD per Office 365 e gli abbonamenti EMS. Dopo l'inizio della sincronizzazione, sarà possibile mantenere gli account e i gruppi utente con il provider di identità locale, come Windows Server AD.

Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. 
- Per i requisiti consigliati per gli ambienti ibridi, vedere la colonna **Active Directory con sincronizzazione delle password hash** in [Prerequisiti](identity-access-prerequisites.md#prerequisites). 

- Per i requisiti consigliati per gli ambienti solo cloud, vedere la colonna **Solo cloud** in [Prerequisiti](identity-access-prerequisites.md#prerequisites).

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md)<br> [Guida del laboratorio di testing: autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md) |
|||

Come checkpoint provvisorio, vedere i [criteri di completamento](identity-exit-criteria.md#crit-identity-sync) relativi a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [Monitorare l'integrità della sincronizzazione](identity-azure-ad-connect-health.md) |

