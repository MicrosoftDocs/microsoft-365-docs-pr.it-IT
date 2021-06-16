---
title: Informazioni aggiuntive per i provider di soluzioni cloud
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: informazioni aggiuntive per i provider di soluzioni cloud rilevanti per la migrazione da Microsoft Cloud Deutschland.'
ms.openlocfilehash: 7a7c377d8e0b72a0179ff28a93018f88d22a5325
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52931050"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="3d71e-103">Informazioni aggiuntive per i provider di soluzioni cloud</span><span class="sxs-lookup"><span data-stu-id="3d71e-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="3d71e-104">I provider di soluzioni cloud (CSP) che supportano i clienti devono eseguire ulteriori passaggi durante la migrazione da Microsoft Cloud Deutschland alla nuova area data center tedesca.</span><span class="sxs-lookup"><span data-stu-id="3d71e-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="3d71e-105">Migrazione tenant partner</span><span class="sxs-lookup"><span data-stu-id="3d71e-105">Partner tenant migration</span></span>

<span data-ttu-id="3d71e-106">I tenant di Microsoft Cloud Deutschland partner non verranno migrati.</span><span class="sxs-lookup"><span data-stu-id="3d71e-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="3d71e-107">Verrà invece creato un nuovo tenant dei Office 365 per ogni partner Microsoft nella nuova area data center tedesca.</span><span class="sxs-lookup"><span data-stu-id="3d71e-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="3d71e-108">I tenant dei clienti CSP verranno migrati nella nuova area dati tedesca e collegati al nuovo tenant dei servizi di Office 365 dello stesso partner.</span><span class="sxs-lookup"><span data-stu-id="3d71e-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="3d71e-109">Dopo la transizione del cliente, il partner può gestire il cliente usando il nuovo tenant dei Office 365 nell'area del datacenter tedesco.</span><span class="sxs-lookup"><span data-stu-id="3d71e-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="3d71e-110">Sottoscrizioni mancanti in Azure</span><span class="sxs-lookup"><span data-stu-id="3d71e-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="3d71e-111">Dopo il completamento della transizione di sottoscrizione e licenza [(fase 3),](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) i provider di soluzioni cloud non avranno più accesso alla sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3d71e-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="3d71e-112">Per ripristinare l'accesso, eseguire la procedura seguente per [elevare l'accesso per gestire tutte le sottoscrizioni e i gruppi di gestione di Azure.](/azure/role-based-access-control/elevate-access-global-admin)</span><span class="sxs-lookup"><span data-stu-id="3d71e-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
