---
title: Gestione degli accessi privilegiati in Microsoft 365
description: Scopri come configurare le funzionalità di rischio insider in Microsoft 365.
keywords: Microsoft 365, rischio insider, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423809"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="2d983-104">Gestione degli accessi privilegiati in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d983-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="2d983-105">L'accesso permanente da parte di alcuni utenti alle informazioni riservate o alle impostazioni di configurazione di rete critiche in Microsoft Exchange Online rappresenta un potenziale percorso per gli account compromessi o le attività di minacce interne.</span><span class="sxs-lookup"><span data-stu-id="2d983-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="2d983-106">La gestione degli accessi privilegiati consente di proteggere l'organizzazione dalle violazioni e consente di soddisfare le procedure consigliate di conformità limitando l'accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche.</span><span class="sxs-lookup"><span data-stu-id="2d983-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="2d983-107">Invece che gli amministratori hanno accesso costante, vengono implementate regole di accesso just-in-time per le attività che necessitano di autorizzazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="2d983-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="2d983-108">L'abilitazione della gestione degli accessi con privilegi per Exchange Online in Microsoft 365 consente all'organizzazione di operare senza privilegi permanenti e fornire un livello di difesa contro le vulnerabilità di accesso amministrativo permanenti.</span><span class="sxs-lookup"><span data-stu-id="2d983-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="2d983-109">Configurare la gestione degli accessi con privilegi per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d983-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="2d983-110">Utilizzare la procedura seguente per configurare la gestione degli accessi con privilegi per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="2d983-110">Use the following steps to configure privileged access management for your organization:</span></span>

![Passaggi di gestione degli accessi privilegiati della soluzione di rischio Insider](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="2d983-112">Informazioni sulla [gestione degli accessi con](privileged-access-management-overview.md) privilegi in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d983-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="2d983-113">Creare un [gruppo di responsabili approvazione](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="2d983-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="2d983-114">Abilitare [la gestione degli accessi con privilegi](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="2d983-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="2d983-115">Creare un [criterio di accesso](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="2d983-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="2d983-116">Inviare/approvare [richieste di accesso con privilegi](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="2d983-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="2d983-117">Ulteriori informazioni sulla gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="2d983-117">More information about privileged access management</span></span>

- [<span data-ttu-id="2d983-118">Domande frequenti sulla gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="2d983-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)