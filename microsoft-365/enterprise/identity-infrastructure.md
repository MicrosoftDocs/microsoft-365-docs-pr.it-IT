---
title: 'Fase 2: identità'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise.
ms.openlocfilehash: 6acd462a0fcd4169a42a0b1d0e1738ffcba597f5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073896"
---
# <a name="phase-2-identity"></a>Fase 2: identità

![](./media/deploy-foundation-infrastructure/identity_icon.png)

In Microsoft 365 Enterprise, un'infrastruttura di gestione delle identità ben pianificata ed eseguita permette una maggiore sicurezza e l'accesso ai carichi di lavoro di produttività e ai relativi dati solo da parte di utenti e dispositivi autenticati.

>[!Note]
>Se è stata già implementata un'infrastruttura di gestione delle identità, vedere i [criteri uscita delle identità](identity-exit-criteria.md) per assicurarsi che soddisfino le condizioni facoltative e obbligatorie di Microsoft 365 Enterprise.
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>Pianificare e distribuire l'infrastruttura di gestione delle identità di Microsoft 365 Enterprise 

Prima di iniziare, guardare questo video che illustra i modelli di identità e l'autenticazione per Microsoft 365.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Utilizzare la seguente procedura per pianificare e distribuire la nuova infrastruttura di gestione delle identità nel cloud. È inoltre possibile usare tale procedura per adattare l'infrastruttura di gestione delle identità ibrida o locale esistente da utilizzare con Microsoft 365 Enterprise. 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Pianificare utenti e gruppi](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [Protezione delle identità con privilegi](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [Configurare identità ibrida](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [Configurare autenticazione utente protetto](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [Semplificare l'accesso per gli utenti](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [Usare i gruppi per facilitare la gestione](identity-self-service-group-management.md) |

Dopo aver completato questi passaggi, passare ai [criteri uscita](identity-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.

## <a name="identity-and-device-access-recommendations"></a>Consigli sull’identità e sull’accesso dei dispositivi

Microsoft offre un set di consigli per [l’identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l’identità, usare i suggerimenti e le impostazioni degli articoli seguenti insieme alla procedura descritta in questa fase:

- [Prerequisiti](identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni su come gli esperti IT di Microsoft [gestiscono le identità e l'accesso sicuro](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito un’infrastruttura di identità ibrida](contoso-identity.md) per i servizi cloud Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Pianificare utenti e gruppi](identity-plan-users-groups.md) |
