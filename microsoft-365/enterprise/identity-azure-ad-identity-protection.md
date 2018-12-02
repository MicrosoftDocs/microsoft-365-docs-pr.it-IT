---
title: 'Passaggio 6: protezione dalla compromissione delle credenziali'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su e configurazione di Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868923"
---
# <a name="step-6-protect-against-credential-compromise"></a>Passaggio 6: protezione dalla compromissione delle credenziali

*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In questo passaggio, si impara a configurare i criteri di protezione dalla compromissione delle credenziali, per cui l'autore di un attacco scopre nome e password dell'account di un utente per ottenere l'accesso ai servizi e ai dati cloud di un'organizzazione. Azure AD Identity Protection offre una serie di modi per impedire all'autore di un attacco di entrare in account e gruppi e, di conseguenza, alla maggior parte dei dati importanti.

Con Azure AD Identity Protection, è possibile:

|||
|:---------|:---------|
|Determinare e affrontare possibili vulnerabilità relative alle identità dell'organizzazione|Azure AD usa l'apprendimento automatico per rilevare anomalie e attività sospette, come ad esempio attività di accesso e conseguenti all'accesso. Usando questi dati, Identity Protection genera report e avvisi che permettono di valutare i problemi e intervenire.|
|Rilevare azioni sospette correlate alle identità dell'organizzazione e intervenire automaticamente|È possibile configurare criteri basati sul rischio che rispondono automaticamente a problemi rilevati quando un livello di rischio specificato è stato raggiunto. Tali criteri, in aggiunta ad altri controlli sull'accesso condizionale forniti da Azure Active Directory ed Enterprise Mobility + Security (EMS), possono bloccare l'accesso o attuare azioni correttive, come le reimpostazioni della password e richiedere l'autenticazione a più fattori per gli accessi successivi.|
|Esaminare gli incidenti sospetti e risolverli con azioni amministrative|È possibile esaminare gli eventi di rischio usando le informazioni sugli incidenti di sicurezza. I flussi di lavoro di base sono disponibili per tenere traccia delle analisi e per attuare azioni correttive, come le reimpostazioni delle password.|

Vedere [altre informazioni su Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Vedere i [passaggi per abilitare Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Al termine della procedura Azure AD Identity Protection è stato abilitato e può essere usato per:

- Far fronte a potenziali vulnerabilità relative alle identità.
- Rilevare possibili tentativi di violazione delle credenziali.
- Ricercare le cause e risolvere attività sospette relative alle identità.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-ident-prot) di questa fase.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [Sincronizzazione delle directory](identity-azure-ad-connect.md) |


