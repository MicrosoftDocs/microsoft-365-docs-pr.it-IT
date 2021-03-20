---
title: Nozioni di base sulla assegnazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: Informazioni sulla nuova funzionalità di assegnazione.
ms.openlocfilehash: 62df346def3fd2577568916d2d668ca50542bdbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911615"
---
# <a name="allotment-basics"></a><span data-ttu-id="1482e-103">Nozioni di base sulla assegnazione</span><span class="sxs-lookup"><span data-stu-id="1482e-103">Allotment basics</span></span>

<span data-ttu-id="1482e-104">Le assegnazioni delle licenze consentono di impostare i limiti di licenza e delegare la gestione dell'assegnazione delle licenze solo ai prodotti e ai limiti di licenza selezionati.</span><span class="sxs-lookup"><span data-stu-id="1482e-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="1482e-105">Le autorizzazioni usano le licenze basate su gruppo per assegnare licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1482e-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="1482e-106">I limiti di licenza offrono un controllo aggiunto sul numero di licenze assegnate agli utenti dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="1482e-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="1482e-107">Pertanto, anche con l'aumentare del numero di utenti nei gruppi, puoi assicurarti di rimanere entro il limite di licenza impostato per l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="1482e-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="1482e-108">Puoi anche delegare la gestione delle tue attività.</span><span class="sxs-lookup"><span data-stu-id="1482e-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="1482e-109">I proprietari di assegnazione delegata ottengono l'accesso all'interfaccia di amministrazione, ma possono solo visualizzare e gestire le licenze nelle autorizzazioni di cui sono proprietari.</span><span class="sxs-lookup"><span data-stu-id="1482e-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="1482e-110">In questo modo viene fornita una delega più granulare della gestione delle licenze all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1482e-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1482e-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1482e-111">Prerequisites</span></span>

<span data-ttu-id="1482e-112">È necessario soddisfare i requisiti di licenza per [le licenze basate su gruppo](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="1482e-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="1482e-113">È possibile utilizzare le risorse con qualsiasi prodotto disponibile per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="1482e-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="1482e-114">Famiglia di prodotti Office e prodotti autonomi</span><span class="sxs-lookup"><span data-stu-id="1482e-114">Office suites and standalone products</span></span>
- <span data-ttu-id="1482e-115">Prodotti Enterprise e Mobility</span><span class="sxs-lookup"><span data-stu-id="1482e-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="1482e-116">Prodotti Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1482e-116">Dynamics 365 products</span></span>

<span data-ttu-id="1482e-117">I prodotti seguenti non possono essere utilizzati con le operazioni di assegnazione:</span><span class="sxs-lookup"><span data-stu-id="1482e-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="1482e-118">App di Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1482e-118">Microsoft Store apps</span></span>
- <span data-ttu-id="1482e-119">Software perpetuo o software direttamente assegnato a un utente se non è coinvolta alcuna licenza.</span><span class="sxs-lookup"><span data-stu-id="1482e-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="1482e-120">Risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="1482e-120">Azure resources</span></span>

<span data-ttu-id="1482e-121">Per iniziare a usare un'assegnazione, devi essere un amministratore globale o di licenza.</span><span class="sxs-lookup"><span data-stu-id="1482e-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="1482e-122">Introduzione</span><span class="sxs-lookup"><span data-stu-id="1482e-122">Getting started</span></span>

<span data-ttu-id="1482e-123">La funzionalità di assegnazione è disponibile in un'anteprima privata solo a un numero limitato di clienti.</span><span class="sxs-lookup"><span data-stu-id="1482e-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="1482e-124">Se si desidera partecipare, compilare il modulo seguente: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="1482e-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>