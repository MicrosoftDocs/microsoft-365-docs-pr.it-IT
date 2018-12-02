---
title: "Passaggio 8: monitorare l'integrità della sincronizzazione"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Capire e configurare Azure AD Connect Health.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868701"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="c6738-103">Passaggio 8: monitorare l'integrità della sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="c6738-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="c6738-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c6738-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="c6738-p101">In questo passaggio, viene installato un agente Azure AD Connect Health in ogni server delle identità locale per monitorare l'infrastruttura di gestione delle identità e i servizi di sincronizzazione forniti da Azure AD Connect. Le informazioni sul monitoraggio vengono rese disponibili nel portale di Azure AD Connect Health, dove è possibile visualizzare avvisi, il monitoraggio delle prestazioni, dati sull'utilizzo e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="c6738-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Componenti di Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="c6738-108">La decisione di progettazione chiave su come usare Azure AD Connect Health si basa sul modo in cui si utilizza Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="c6738-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="c6738-109">Se si usa l'opzione **autenticazione gestita** iniziare con [Uso di Azure AD Connect Health con la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) per comprendere e configurare Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="c6738-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="c6738-110">Se si stanno sincronizzando soli i nomi di account e gruppi tramite l'**autenticazione federata** con Active Directory Federation Services (AD FS), iniziare con [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) per comprendere e configurare Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="c6738-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="c6738-111">Dopo aver completato questo passaggio:</span><span class="sxs-lookup"><span data-stu-id="c6738-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="c6738-112">L'agente di Azure AD Connect Health è installato su ciascuno dei server del provider di identità locale.</span><span class="sxs-lookup"><span data-stu-id="c6738-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="c6738-113">Il portale di Azure AD Connect Health mostra lo stato corrente dell'infrastruttura locale e le attività di sincronizzazione con il tenant di Azure AD per gli abbonamenti a Office 365 e EMS.</span><span class="sxs-lookup"><span data-stu-id="c6738-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="c6738-114">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-sync-health) di questa fase.</span><span class="sxs-lookup"><span data-stu-id="c6738-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="c6738-115">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c6738-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="c6738-116">Semplificare gli aggiornamenti delle password</span><span class="sxs-lookup"><span data-stu-id="c6738-116">Simplify password updates</span></span>](identity-password-writeback.md) |

