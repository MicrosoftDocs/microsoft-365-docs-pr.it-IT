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
# <a name="step-7-synchronize-identities"></a><span data-ttu-id="ad4a1-103">Passaggio 7: sincronizzazione delle identità</span><span class="sxs-lookup"><span data-stu-id="ad4a1-103">Step 7: Synchronize identities</span></span>

<span data-ttu-id="ad4a1-104">*Questo passaggio è obbligatorio per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ad4a1-104">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="ad4a1-105">Questo passaggio consente di sincronizzare l'ambiente Windows Server Active Directory (AD) con il tenant Azure Active Directory (AD) utilizzato per gli abbonamenti a Office 365 Enterprise Mobility + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="ad4a1-105">In this step, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="ad4a1-106">Azure AD Connect è lo strumento Microsoft che guida gli amministratori nel processo di sincronizzazione di quelle identità degli ambienti Windows Server AD con una o più foreste che sono necessarie per il proprio tenant Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ad4a1-106">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span>

![Modalità di Azure AD Connect per sincronizzare la directory locale con Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

<span data-ttu-id="ad4a1-108">*Modalità di Azure AD Connect per sincronizzare la directory locale con Azure AD*</span><span class="sxs-lookup"><span data-stu-id="ad4a1-108">*How Azure AD Connect synchronizes your on-premises directory with Azure AD*</span></span>

<span data-ttu-id="ad4a1-p101">La prima decisione relativa alla soluzione delle identità ibride, riguarda i requisiti di autenticazione. Le opzioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad4a1-p101">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="ad4a1-p102">Con l'**autenticazione gestita**, Azure AD gestisce il processo di autenticazione per l'accesso utente. Esistono due metodi di autenticazione gestita:</span><span class="sxs-lookup"><span data-stu-id="ad4a1-p102">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="ad4a1-p103">**Sincronizzazione degli hash delle password (PHS)**[Opzione consigliata e obbligatoria per alcune funzionalità premium]. Questo è il modo più semplice per abilitare l'autenticazione per gli oggetti directory locali in Azure AD. Azure AD Connect estrae l'hash delle password da Windows Server AD, esegue ulteriori procedure di sicurezza sulla password e la salva in Azure AD. Per ulteriori informazioni, vedere [Implementare la sincronizzazione degli hash delle password con la sincronizzazione Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span><span class="sxs-lookup"><span data-stu-id="ad4a1-p103">**Password Hash Sync (PHS)** [Recommended and required for some premium features]. This is the simplest way to enable authentication for on-premises directory objects in Azure AD. Azure AD Connect extracts the hashed password from Windows Server AD, does extra security processing on the password, and saves it in Azure AD. For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="ad4a1-p104">L'**autenticazione pass-through (PTA)** offre una soluzione semplice di convalida della password per i servizi basati su Azure AD. La PTA utilizza un agente su uno o più server locali per convalidare le autenticazioni utente direttamente da Windows Server AD locale. Per ulteriori informazioni, vedere [Accesso utente con autenticazione pass-through di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="ad4a1-p104">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services. PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises Windows Server AD. For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="ad4a1-p105">Con l'**autenticazione federata**, il processo di autenticazione viene reindirizzato a un altro provider di identità tramite un server federativo di identità, come Active Directory Federation Services (ADFS), per l'accesso utente. Il provider di identità può fornire altri metodi di autenticazione, ad esempio l'autenticazione basata su una smart card. Per ulteriori informazioni, vedere [Scegliere il giusto metodo di autenticazione per la soluzione delle identità ibride di Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="ad4a1-p105">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="ad4a1-123">Una volta determinata la soluzione delle identità ibride, scaricare ed eseguire lo [Strumento IdFix DirSync Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) per analizzare Windows Server AD e cercare eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="ad4a1-123">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="ad4a1-p106">Dopo aver risolto tutti i problemi identificati tramite lo strumento IdFix, vedere [Implementazione della sincronizzazione hash delle password](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) per installare lo strumento Azure AD Connect e configurare la sincronizzazione di directory tra Windows Server AD locale e il tenant Azure AD per Office 365 e gli abbonamenti EMS. Dopo l'inizio della sincronizzazione, sarà possibile mantenere gli account e i gruppi utente con il provider di identità locale, come Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="ad4a1-p106">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span>

<span data-ttu-id="ad4a1-126">Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo.</span><span class="sxs-lookup"><span data-stu-id="ad4a1-126">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 
- <span data-ttu-id="ad4a1-127">Per i requisiti consigliati per gli ambienti ibridi, vedere la colonna **Active Directory con sincronizzazione delle password hash** in [Prerequisiti](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="ad4a1-127">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="ad4a1-128">Per i requisiti consigliati per gli ambienti solo cloud, vedere la colonna **Solo cloud** in [Prerequisiti](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="ad4a1-128">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="ad4a1-130">Guida del laboratorio di testing: sincronizzazione hash delle password</span><span class="sxs-lookup"><span data-stu-id="ad4a1-130">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="ad4a1-131">Guida del laboratorio di testing: autenticazione pass-through</span><span class="sxs-lookup"><span data-stu-id="ad4a1-131">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="ad4a1-132">Come checkpoint provvisorio, vedere i [criteri di completamento](identity-exit-criteria.md#crit-identity-sync) relativi a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="ad4a1-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ad4a1-133">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ad4a1-133">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="ad4a1-134">Monitorare l'integrità della sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="ad4a1-134">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |

