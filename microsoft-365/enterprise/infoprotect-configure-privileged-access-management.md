---
title: 'Passaggio 7: configurare la gestione degli accessi con privilegi per Office 365'
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
description: Comprendere e configurare la gestione degli accessi con privilegi per Office 365.
ms.openlocfilehash: e9c68e4fafb1e9537b403965b4360806938c6a6f
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370423"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="e30b4-103">Passaggio 7: configurare la gestione degli accessi con privilegi per Office 365</span><span class="sxs-lookup"><span data-stu-id="e30b4-103">Step 7: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="e30b4-104">*Questo passaggio è facoltativo e si applica solo alle versioni E5 e Advanced Compliance di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e30b4-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: protezione delle informazioni](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="e30b4-p101">La gestione degli accessi con privilegi è abilitata mediante la configurazione di criteri che specificano l'accesso just-in-time per le operazioni basate sulle attività nel tenant di Office 365. Può aumentare il livello di protezione dell'organizzazione da violazioni che possono usare account di amministratore privilegiato esistenti con accesso permanente a dati riservati o con accesso a impostazioni di configurazione cruciali. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e30b4-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="e30b4-p102">In questo passaggio verrà abilitata la gestione degli accessi con privilegi nel tenant di Office 365 e verranno configurati i criteri di accesso con privilegi che garantiscono una maggiore protezione per gli accessi basati sulle attività a impostazioni dati e configurazione di Office 365 dell’organizzazione. Esistono tre passaggi di base per iniziare a usare gli accessi con privilegi nell'organizzazione di Office 365:</span><span class="sxs-lookup"><span data-stu-id="e30b4-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="e30b4-111">Creazione di un gruppo responsabile dell'approvazione</span><span class="sxs-lookup"><span data-stu-id="e30b4-111">Creating an approver's group</span></span>
- <span data-ttu-id="e30b4-112">Abilitazione dell’accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="e30b4-112">Enabling privileged access</span></span>
- <span data-ttu-id="e30b4-113">Creazione di criteri per l'approvazione</span><span class="sxs-lookup"><span data-stu-id="e30b4-113">Creating approval policies</span></span>

<span data-ttu-id="e30b4-p103">Una volta configurata, la gestione degli accessi con privilegi consentirà all'organizzazione di operare con privilegi permanenti uguali a zero e di fornire un livello di protezione contro vulnerabilità che si verificano a causa di questo tipo di accesso amministrativo permanente. L’accesso con privilegi richiede l'approvazione per l'esecuzione di tutte le attività associate a un criterio di approvazione definito. Gli utenti che necessitano di eseguire attività incluse nei criteri di approvazione devono richiedere e ottenere l'approvazione di accesso per disporre delle autorizzazioni necessarie a eseguire le attività definite nel criterio.</span><span class="sxs-lookup"><span data-stu-id="e30b4-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="e30b4-117">Per abilitare la gestione degli accessi con privilegi di Office 365, vedere l’argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="e30b4-117">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="e30b4-118">Per ulteriori informazioni, vedere l’argomento [Gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="e30b4-118">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="e30b4-120">Per eseguire questa configurazione in un ambiente di laboratorio di testing, vedere la [Guida al Lab di test di gestione di accessi con privilegi](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e30b4-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="e30b4-121">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step7) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e30b4-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e30b4-122">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e30b4-122">Next Step</span></span>

[<span data-ttu-id="e30b4-123">Criteri uscita dell'infrastruttura di protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="e30b4-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
