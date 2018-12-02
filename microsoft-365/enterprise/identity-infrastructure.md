---
title: 'Fase 2: identità'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868684"
---
# <a name="phase-2-identity"></a>Fase 2: identità

![](./media/deploy-foundation-infrastructure/identity_icon.png)

In Microsoft 365 Enterprise, un'infrastruttura di gestione delle identità ben pianificata ed eseguita permette una maggiore sicurezza e l'accesso ai carichi di lavoro di produttività e ai relativi dati solo da parte di utenti e dispositivi autenticati.

>[!Note]
>Se è stata già implementata un'infrastruttura di gestione delle identità, vedere i [criteri uscita delle identità](identity-exit-criteria.md) per assicurarsi che soddisfino le condizioni facoltative e obbligatorie di Microsoft 365 Enterprise.
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Pianificare e distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise 

Utilizzare la seguente procedura per pianificare e distribuire la nuova infrastruttura di gestione delle identità nel cloud. È inoltre possibile usare tale procedura per adattare l'infrastruttura di gestione delle identità ibrida o locale esistente da utilizzare con Microsoft 365 Enterprise. 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Pianificare utenti e gruppi](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [Proteggere gli account amministratore globale](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [Configurare gli amministratori globali su richiesta](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [Semplificare le reimpostazioni delle password](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [Configurare l'autenticazione a più fattori](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [Proteggere dalla compromissione delle credenziali](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [Sincronizzazione delle directory](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [Monitorare l'integrità della sincronizzazione](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [Semplificare gli aggiornamenti delle password](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [Semplificare l'accesso utente](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [Personalizzare la pagina di accesso a Office 365](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [Configurare l'assegnazione automatica delle licenze](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [Monitorare l'attività di tenant e di accesso](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [Consentire agli utenti di creare e gestire i propri gruppi](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [Configurare l'appartenenza a gruppi dinamici](identity-automatic-group-membership.md) |

Dopo aver completato questi passaggi, passare ai [criteri uscita](identity-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.

## <a name="identity-and-device-access-recommendations"></a>Consigli sull’identità e sull’accesso dei dispositivi

Microsoft offre un set di consigli per [l’identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l’identità, usare i suggerimenti e le impostazioni degli articoli seguenti insieme alla procedura descritta in questa fase:

- [Prerequisiti](identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni su come gli esperti IT di Microsoft hanno pianificato e implementato le funzionalità di identità di Microsoft 365 Enterprise con queste risorse:

- [Gestione delle identità degli utenti e accesso protetto a Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [Utilizzo di Azure AD Privileged Identity Management per l'accesso con privilegi](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito un’infrastruttura di identità ibrida](contoso-identity.md) per i servizi cloud Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Pianificare utenti e gruppi](identity-plan-users-groups.md) |
