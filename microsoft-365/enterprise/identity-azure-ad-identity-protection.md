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
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="93cf5-103">Passaggio 6: protezione dalla compromissione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="93cf5-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="93cf5-104">*Questo passaggio è facoltativo e si applica solo alla versione E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="93cf5-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="93cf5-p101">In questo passaggio, si impara a configurare i criteri di protezione dalla compromissione delle credenziali, per cui l'autore di un attacco scopre nome e password dell'account di un utente per ottenere l'accesso ai servizi e ai dati cloud di un'organizzazione. Azure AD Identity Protection offre una serie di modi per impedire all'autore di un attacco di entrare in account e gruppi e, di conseguenza, alla maggior parte dei dati importanti.</span><span class="sxs-lookup"><span data-stu-id="93cf5-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="93cf5-107">Con Azure AD Identity Protection, è possibile:</span><span class="sxs-lookup"><span data-stu-id="93cf5-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="93cf5-108">Determinare e affrontare possibili vulnerabilità relative alle identità dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="93cf5-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="93cf5-p102">Azure AD usa l'apprendimento automatico per rilevare anomalie e attività sospette, come ad esempio attività di accesso e conseguenti all'accesso. Usando questi dati, Identity Protection genera report e avvisi che permettono di valutare i problemi e intervenire.</span><span class="sxs-lookup"><span data-stu-id="93cf5-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="93cf5-111">Rilevare azioni sospette correlate alle identità dell'organizzazione e intervenire automaticamente</span><span class="sxs-lookup"><span data-stu-id="93cf5-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="93cf5-p103">È possibile configurare criteri basati sul rischio che rispondono automaticamente a problemi rilevati quando un livello di rischio specificato è stato raggiunto. Tali criteri, in aggiunta ad altri controlli sull'accesso condizionale forniti da Azure Active Directory ed Enterprise Mobility + Security (EMS), possono bloccare l'accesso o attuare azioni correttive, come le reimpostazioni della password e richiedere l'autenticazione a più fattori per gli accessi successivi.</span><span class="sxs-lookup"><span data-stu-id="93cf5-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="93cf5-114">Esaminare gli incidenti sospetti e risolverli con azioni amministrative</span><span class="sxs-lookup"><span data-stu-id="93cf5-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="93cf5-p104">È possibile esaminare gli eventi di rischio usando le informazioni sugli incidenti di sicurezza. I flussi di lavoro di base sono disponibili per tenere traccia delle analisi e per attuare azioni correttive, come le reimpostazioni delle password.</span><span class="sxs-lookup"><span data-stu-id="93cf5-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="93cf5-117">Vedere [altre informazioni su Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="93cf5-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="93cf5-118">Vedere i [passaggi per abilitare Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="93cf5-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="93cf5-119">Al termine della procedura Azure AD Identity Protection è stato abilitato e può essere usato per:</span><span class="sxs-lookup"><span data-stu-id="93cf5-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="93cf5-120">Far fronte a potenziali vulnerabilità relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="93cf5-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="93cf5-121">Rilevare possibili tentativi di violazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="93cf5-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="93cf5-122">Ricercare le cause e risolvere attività sospette relative alle identità.</span><span class="sxs-lookup"><span data-stu-id="93cf5-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="93cf5-124">Guida al lab di test: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="93cf5-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="93cf5-125">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-ident-prot) di questa fase.</span><span class="sxs-lookup"><span data-stu-id="93cf5-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="93cf5-126">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="93cf5-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="93cf5-127">Sincronizzazione delle directory</span><span class="sxs-lookup"><span data-stu-id="93cf5-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


