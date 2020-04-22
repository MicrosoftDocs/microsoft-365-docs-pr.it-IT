---
title: 'Passaggio 7: configurare la gestione degli accessi con privilegi'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprendere e configurare la gestione degli accessi con privilegi.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636989"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="69415-103">Passaggio 7: configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="69415-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="69415-104">*Questo passaggio è facoltativo e si applica solo alle versioni E5 e Advanced Compliance di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="69415-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="69415-106">La gestione degli accessi con privilegi è abilitata configurando i criteri che specificano l'accesso just-in-time per le attività basate sulle attività nel tenant.</span><span class="sxs-lookup"><span data-stu-id="69415-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="69415-107">Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare gli account amministratore privilegiati esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="69415-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="69415-108">Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant.</span><span class="sxs-lookup"><span data-stu-id="69415-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="69415-109">In questo passaggio, è possibile abilitare la gestione degli accessi con privilegi nel tenant e configurare i criteri di accesso privilegiato che forniscono ulteriore sicurezza per l'accesso basato sulle attività ai dati e alle impostazioni di configurazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="69415-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="69415-110">Per iniziare a utilizzare l'accesso con privilegi nell'organizzazione, è necessario eseguire tre operazioni di base:</span><span class="sxs-lookup"><span data-stu-id="69415-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="69415-111">Creazione di un gruppo responsabile dell'approvazione</span><span class="sxs-lookup"><span data-stu-id="69415-111">Creating an approver's group</span></span>
- <span data-ttu-id="69415-112">Abilitazione dell’accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="69415-112">Enabling privileged access</span></span>
- <span data-ttu-id="69415-113">Creazione di criteri per l'approvazione</span><span class="sxs-lookup"><span data-stu-id="69415-113">Creating approval policies</span></span>

<span data-ttu-id="69415-p103">Una volta configurata, la gestione degli accessi con privilegi consentirà all'organizzazione di operare con privilegi permanenti uguali a zero e di fornire un livello di protezione contro vulnerabilità che si verificano a causa di questo tipo di accesso amministrativo permanente. L’accesso con privilegi richiede l'approvazione per l'esecuzione di tutte le attività associate a un criterio di approvazione definito. Gli utenti che necessitano di eseguire attività incluse nei criteri di approvazione devono richiedere e ottenere l'approvazione di accesso per disporre delle autorizzazioni necessarie a eseguire le attività definite nel criterio.</span><span class="sxs-lookup"><span data-stu-id="69415-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="69415-117">Per abilitare la gestione degli accessi con privilegi, vedere l'argomento [Configure Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .</span><span class="sxs-lookup"><span data-stu-id="69415-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="69415-118">Per ulteriori informazioni, vedere l'argomento relativo alla [gestione degli accessi con privilegi](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .</span><span class="sxs-lookup"><span data-stu-id="69415-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="69415-120">Per eseguire questa procedura in un ambiente di testing, vedere la [Guida al lab di test gestione degli accessi privilegiati](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="69415-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="69415-121">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step7) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="69415-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="69415-122">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="69415-122">Next Step</span></span>

[<span data-ttu-id="69415-123">Criteri uscita dell'infrastruttura di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="69415-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
