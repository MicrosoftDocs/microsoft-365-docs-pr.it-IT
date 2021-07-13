---
title: Microsoft 365 Lighthouse'elenco dei tenant
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP) Microsoft 365 Lighthouse, informazioni sull'elenco dei tenant.
ms.openlocfilehash: 05c6bf6c1b9529d05fac04c2d5c43802280cfbc9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395176"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a><span data-ttu-id="1bc33-103">Microsoft 365 Lighthouse'elenco dei tenant</span><span class="sxs-lookup"><span data-stu-id="1bc33-103">Microsoft 365 Lighthouse tenant list overview</span></span>

> [!NOTE]
> <span data-ttu-id="1bc33-104">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bc33-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="1bc33-105">Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="1bc33-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="1bc33-106">L Microsoft 365 Lighthouse di tenant fornisce informazioni dettagliate sui diversi tenant con cui hai un contratto, incluso lo stato di onboarding del tenant rispetto a Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="1bc33-106">The Microsoft 365 Lighthouse tenant list provides insights into the different tenants you have a contract with, including tenant onboarding status relative to Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="1bc33-107">L'elenco dei tenant consente inoltre di contrassegnare i tenant per fornire filtri diversi Microsoft 365 Lighthouse ed eseguire il drill-down per ottenere ulteriori informazioni su un determinato tenant e sullo stato del piano di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1bc33-107">The tenant list also lets you tag tenants to provide different filters throughout Microsoft 365 Lighthouse, and drill down to learn more about a given tenant and the status of their deployment plan.</span></span>

<span data-ttu-id="1bc33-108">Dopo che i tenant soddisfano [i Microsoft 365 Lighthouse di onboarding,](m365-lighthouse-requirements.md)il relativo stato verrà visualizzato come **Attivo** nell'elenco dei tenant.</span><span class="sxs-lookup"><span data-stu-id="1bc33-108">After your tenants meet the [Microsoft 365 Lighthouse onboarding requirements](m365-lighthouse-requirements.md), their status will show as **Active** in the tenant list.</span></span>

<span data-ttu-id="1bc33-109">Per accedere all'elenco dei tenant in Microsoft 365 Lighthouse, selezionare **Tenant nel** riquadro di spostamento sinistro per aprire la pagina Tenant.</span><span class="sxs-lookup"><span data-stu-id="1bc33-109">To access the tenant list in Microsoft 365 Lighthouse, select **Tenants** in the left navigation pane to open the Tenants page.</span></span>

## <a name="tenant-status"></a><span data-ttu-id="1bc33-110">Stato tenant</span><span class="sxs-lookup"><span data-stu-id="1bc33-110">Tenant status</span></span>

<span data-ttu-id="1bc33-111">La tabella seguente mostra i diversi messaggi di stato e il relativo significato.</span><span class="sxs-lookup"><span data-stu-id="1bc33-111">The following table shows the different status messages and their meaning.</span></span><br><br>

| <span data-ttu-id="1bc33-112">Messaggio di stato</span><span class="sxs-lookup"><span data-stu-id="1bc33-112">Status message</span></span> | <span data-ttu-id="1bc33-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bc33-113">Description</span></span> |
|--|--|
| <span data-ttu-id="1bc33-114">Attivazione</span><span class="sxs-lookup"><span data-stu-id="1bc33-114">Active</span></span> | <span data-ttu-id="1bc33-115">L'onboarding e il flusso di dati sono stati avviati.</span><span class="sxs-lookup"><span data-stu-id="1bc33-115">Onboarding and data flow has started.</span></span> |
| <span data-ttu-id="1bc33-116">In corso</span><span class="sxs-lookup"><span data-stu-id="1bc33-116">In process</span></span> | <span data-ttu-id="1bc33-117">Tenant individuato, ma non completamente onboarded.</span><span class="sxs-lookup"><span data-stu-id="1bc33-117">Tenant discovered, but not fully onboarded.</span></span> |
| <span data-ttu-id="1bc33-118">Non idoneo, DAP</span><span class="sxs-lookup"><span data-stu-id="1bc33-118">Ineligible, DAP</span></span> | <span data-ttu-id="1bc33-119">L'installazione dei privilegi di amministratore delegato (DAP, Delegated Admin Privileges) è necessaria.</span><span class="sxs-lookup"><span data-stu-id="1bc33-119">Delegated Admin Privileges (DAP) setup is required.</span></span> |
| <span data-ttu-id="1bc33-120">Non idoneo, conteggio utenti</span><span class="sxs-lookup"><span data-stu-id="1bc33-120">Ineligible, user count</span></span> | <span data-ttu-id="1bc33-121">Il tenant ha un numero di utenti superiore a quello consentito.</span><span class="sxs-lookup"><span data-stu-id="1bc33-121">Tenant has more users than allowed.</span></span> |
| <span data-ttu-id="1bc33-122">Non idoneo, licenza</span><span class="sxs-lookup"><span data-stu-id="1bc33-122">Ineligible, license</span></span> | <span data-ttu-id="1bc33-123">Il tenant non dispone di una licenza necessaria.</span><span class="sxs-lookup"><span data-stu-id="1bc33-123">Tenant does not have required license.</span></span> |
| <span data-ttu-id="1bc33-124">Inattivo</span><span class="sxs-lookup"><span data-stu-id="1bc33-124">Inactive</span></span> | <span data-ttu-id="1bc33-125">Il tenant non è più attivo.</span><span class="sxs-lookup"><span data-stu-id="1bc33-125">Tenant is no longer active.</span></span> |

<span data-ttu-id="1bc33-126">Dopo aver disattivato un tenant, non è possibile eseguire azioni nel tenant Microsoft 365 Lighthouse completare il processo di disattivazione.</span><span class="sxs-lookup"><span data-stu-id="1bc33-126">Once you inactivate a tenant, you can't take action on the tenant while Microsoft 365 Lighthouse completes the inactivation process.</span></span> <span data-ttu-id="1bc33-127">Il completamento della disattivazione può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="1bc33-127">It may take up to 48 hours for inactivation to complete.</span></span>

<span data-ttu-id="1bc33-128">Se si decide di riattivare un tenant, potrebbero essere necessario fino a 48 ore per la ricomparsa dei dati.</span><span class="sxs-lookup"><span data-stu-id="1bc33-128">If you decide to reactivate a tenant, it may take up to 48 hours for data to reappear.</span></span>

## <a name="tenant-tags"></a><span data-ttu-id="1bc33-129">Tag tenant</span><span class="sxs-lookup"><span data-stu-id="1bc33-129">Tenant tags</span></span>

<span data-ttu-id="1bc33-130">È possibile contrassegnare i tenant dei clienti con un'etichetta personalizzata all'interno Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="1bc33-130">You can tag your customer tenants with a custom label within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="1bc33-131">Questi tag possono essere usati per organizzare i tenant e possono anche aiutarti a filtrare facilmente le visualizzazioni e le informazioni dettagliate esistenti disponibili per i set pertinenti di tenant dei clienti.</span><span class="sxs-lookup"><span data-stu-id="1bc33-131">These tags can be used to organize your tenants and can also help you easily filter the existing views and insights available to relevant sets of customer tenants.</span></span> <span data-ttu-id="1bc33-132">Puoi anche gestire i tag e i tenant a cui sono assegnati dalla pagina Tenant.</span><span class="sxs-lookup"><span data-stu-id="1bc33-132">You can also manage your tags and which tenants they're assigned to from the Tenants page.</span></span>

## <a name="related-content"></a><span data-ttu-id="1bc33-133">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="1bc33-133">Related content</span></span>

<span data-ttu-id="1bc33-134">[Requisiti per Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="1bc33-134">[Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (article)</span></span>\
<span data-ttu-id="1bc33-135">[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)</span><span class="sxs-lookup"><span data-stu-id="1bc33-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>