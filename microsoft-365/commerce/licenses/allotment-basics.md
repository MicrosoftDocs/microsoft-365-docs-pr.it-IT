---
title: Nozioni di base di assegnazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: Ulteriori informazioni sulla nuova funzionalità di assegnazione.
ms.openlocfilehash: d1f926165678b57ec46195d525f2fcdaa6976501
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632414"
---
# <a name="allotment-basics"></a><span data-ttu-id="f74a6-103">Nozioni di base di assegnazione</span><span class="sxs-lookup"><span data-stu-id="f74a6-103">Allotment basics</span></span>

<span data-ttu-id="f74a6-104">Le assegnazioni delle licenze consentono di impostare i limiti delle licenze e di delegare la gestione dell'assegnazione delle licenze solo ai prodotti e ai limiti di licenza selezionati.</span><span class="sxs-lookup"><span data-stu-id="f74a6-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="f74a6-105">Le assegnazioni utilizzano le licenze basate su gruppo per assegnare le licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f74a6-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="f74a6-106">I limiti relativi alle licenze consentono di controllare il numero di licenze assegnate agli utenti nei gruppi.</span><span class="sxs-lookup"><span data-stu-id="f74a6-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="f74a6-107">In questo modo, anche quando aumenta il numero di utenti nei gruppi, è possibile verificare di rimanere entro il limite di licenza impostato per l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="f74a6-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="f74a6-108">È inoltre possibile delegare la gestione delle assegnazioni.</span><span class="sxs-lookup"><span data-stu-id="f74a6-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="f74a6-109">I proprietari di riparto delegati accedono all'interfaccia di amministrazione, ma possono solo visualizzare e gestire le licenze nelle assegnazioni possedute.</span><span class="sxs-lookup"><span data-stu-id="f74a6-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="f74a6-110">In questo modo viene fornita una delega più granulare della gestione delle licenze all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f74a6-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f74a6-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f74a6-111">Prerequisites</span></span>

<span data-ttu-id="f74a6-112">È necessario soddisfare i requisiti di licenza per la [gestione delle licenze basate su gruppo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f74a6-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="f74a6-113">È possibile utilizzare gli assegnamenti con qualsiasi prodotto disponibile per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="f74a6-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="f74a6-114">Suite di Office e prodotti autonomi</span><span class="sxs-lookup"><span data-stu-id="f74a6-114">Office suites and standalone products</span></span>
- <span data-ttu-id="f74a6-115">Prodotti Enterprise e mobili</span><span class="sxs-lookup"><span data-stu-id="f74a6-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="f74a6-116">Prodotti Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f74a6-116">Dynamics 365 products</span></span>

<span data-ttu-id="f74a6-117">I prodotti seguenti non possono essere utilizzati con le assegnazioni:</span><span class="sxs-lookup"><span data-stu-id="f74a6-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="f74a6-118">App di Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f74a6-118">Microsoft Store apps</span></span>
- <span data-ttu-id="f74a6-119">Software perpetuo o software direttamente assegnato a un utente se non sono presenti licenze.</span><span class="sxs-lookup"><span data-stu-id="f74a6-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="f74a6-120">Risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="f74a6-120">Azure resources</span></span>

<span data-ttu-id="f74a6-121">Per iniziare a utilizzare un riparto, è necessario essere un amministratore globale o di licenza.</span><span class="sxs-lookup"><span data-stu-id="f74a6-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="f74a6-122">Introduzione</span><span class="sxs-lookup"><span data-stu-id="f74a6-122">Getting started</span></span>

<span data-ttu-id="f74a6-123">La funzionalità di assegnazione è disponibile in un'anteprima privata solo per un numero limitato di clienti.</span><span class="sxs-lookup"><span data-stu-id="f74a6-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="f74a6-124">Se si è interessati a partecipare, compilare questo modulo: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span><span class="sxs-lookup"><span data-stu-id="f74a6-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
