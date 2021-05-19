---
title: Pianificare le versioni software e software di fine supporto
description: Individuare e pianificare versioni software e software non più supportate e che non riceveranno aggiornamenti della sicurezza.
keywords: gestione di minacce e vulnerabilità, raccomandazione sulla sicurezza di Microsoft Defender for Endpoint tvm, raccomandazione sulla sicurezza informatica, raccomandazione di sicurezza utilizzabile
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb436cbd2d0fa453872760c1d2656585e02d1767
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538868"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="09b46-104">Pianificare le versioni software e software di fine supporto con gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="09b46-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09b46-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="09b46-105">**Applies to:**</span></span>

- [<span data-ttu-id="09b46-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="09b46-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="09b46-107">Minaccia e gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="09b46-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="09b46-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09b46-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="09b46-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="09b46-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="09b46-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="09b46-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="09b46-111">End-of-support (EOS), altrimenti noto come end-of-life (EOL), per le versioni software o software significa che non saranno più supportati o serviced e non riceveranno aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="09b46-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="09b46-112">Quando si utilizzano versioni software o software con supporto terminato, si espone l'organizzazione a vulnerabilità della sicurezza, rischi legali e finanziari.</span><span class="sxs-lookup"><span data-stu-id="09b46-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="09b46-113">È fondamentale che gli amministratori IT e della sicurezza lavorino insieme e assicurino che l'inventario software dell'organizzazione sia configurato per ottenere risultati ottimali, conformità e un ecosistema di rete sano.</span><span class="sxs-lookup"><span data-stu-id="09b46-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="09b46-114">Devono esaminare le opzioni per rimuovere o sostituire le app che hanno raggiunto la fine del supporto e aggiornano le versioni non più supportate.</span><span class="sxs-lookup"><span data-stu-id="09b46-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="09b46-115">È meglio creare e implementare un piano prima **della** fine delle date di supporto.</span><span class="sxs-lookup"><span data-stu-id="09b46-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

>[!NOTE]
> <span data-ttu-id="09b46-116">La funzionalità EOS non è attualmente disponibile per i prodotti non Windows (Mac, Linux); verrà tuttavia aggiunto in futuro.</span><span class="sxs-lookup"><span data-stu-id="09b46-116">EOS capability is not currently available for non-Windows products (Mac, Linux); it will, however, be added in the future.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="09b46-117">Trovare versioni software o software non più supportate</span><span class="sxs-lookup"><span data-stu-id="09b46-117">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="09b46-118">Dal menu gestione di minacce e vulnerabilità, passare a [**Suggerimenti per la sicurezza.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="09b46-118">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="09b46-119">Vai al pannello **Filtri** e cerca la sezione tag.</span><span class="sxs-lookup"><span data-stu-id="09b46-119">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="09b46-120">Selezionare una o più opzioni di tag EOS.</span><span class="sxs-lookup"><span data-stu-id="09b46-120">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="09b46-121">Quindi **applica**.</span><span class="sxs-lookup"><span data-stu-id="09b46-121">Then **Apply**.</span></span>

    ![Tag screenshot che affermano che il software EOS, le versioni EOS e le versioni future di EOS.](images/tvm-eos-tag.png)

3. <span data-ttu-id="09b46-123">Verrà visualizzato un elenco di suggerimenti relativi al software con supporto terminato, alle versioni software che terminano il supporto o alle versioni con fine del supporto imminente.</span><span class="sxs-lookup"><span data-stu-id="09b46-123">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="09b46-124">Questi tag sono visibili anche nella pagina [dell'inventario software.](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="09b46-124">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Consigli con tag EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="09b46-126">Elenco di versioni e date</span><span class="sxs-lookup"><span data-stu-id="09b46-126">List of versions and dates</span></span>

<span data-ttu-id="09b46-127">Per visualizzare un elenco delle versioni che hanno raggiunto la fine del supporto, o la fine o il supporto a breve e tali date, seguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="09b46-127">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="09b46-128">Un messaggio verrà visualizzato nel riquadro a comparsa dei suggerimenti per la sicurezza per il software con versioni che hanno raggiunto la fine del supporto o raggiungeranno la fine del supporto a breve.</span><span class="sxs-lookup"><span data-stu-id="09b46-128">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Screenshot del collegamento di distribuzione della versione.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="09b46-130">Selezionare il **collegamento di distribuzione** della versione per passare alla pagina di drill-down del software.</span><span class="sxs-lookup"><span data-stu-id="09b46-130">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="09b46-131">È possibile visualizzare un elenco filtrato di versioni con tag che le identificano come fine del supporto o fine imminente del supporto.</span><span class="sxs-lookup"><span data-stu-id="09b46-131">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Screenshot della pagina di drill-down del software con fine del software di supporto.](images/software-drilldown-eos.png)

3. <span data-ttu-id="09b46-133">Selezionare una delle versioni della tabella da aprire.</span><span class="sxs-lookup"><span data-stu-id="09b46-133">Select one of the versions in the table to open.</span></span> <span data-ttu-id="09b46-134">Ad esempio, versione 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="09b46-134">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="09b46-135">Verrà visualizzato un riquadro a comparsa con la data di fine del supporto.</span><span class="sxs-lookup"><span data-stu-id="09b46-135">A flyout will appear with the end of support date.</span></span>

    ![Screenshot della data di fine del supporto.](images/version-eos-date.png)

<span data-ttu-id="09b46-137">Dopo aver identificato le versioni software e software vulnerabili a causa del loro stato di fine supporto, è necessario decidere se aggiornarle o rimuoverle dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="09b46-137">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="09b46-138">In questo modo si riduce l'esposizione delle organizzazioni a vulnerabilità e minacce persistenti avanzate.</span><span class="sxs-lookup"><span data-stu-id="09b46-138">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09b46-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="09b46-139">Related topics</span></span>

- [<span data-ttu-id="09b46-140">Panoramica delle minacce gestione delle vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="09b46-140">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="09b46-141">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="09b46-141">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="09b46-142">Inventario software</span><span class="sxs-lookup"><span data-stu-id="09b46-142">Software inventory</span></span>](tvm-software-inventory.md)
