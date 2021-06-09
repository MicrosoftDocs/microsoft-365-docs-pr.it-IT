---
title: Introduzione alla risposta al primo incidente
description: Nozioni di base sulla risposta al primo evento imprevisto in Microsoft 365 Defender.
keywords: incidenti, avvisi, indagare, correlazione, attacco, dispositivi, utenti, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365, risposta agli incidenti, cyberattacco
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6e65a12f42b9f5f75c1a19cb9c4a261c94feaf31
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841715"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="d403c-104">Introduzione alla risposta al primo incidente</span><span class="sxs-lookup"><span data-stu-id="d403c-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d403c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d403c-105">**Applies to:**</span></span>
- <span data-ttu-id="d403c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d403c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d403c-107">La strategia di risposta agli incidenti di un'organizzazione determina la capacità di gestire incidenti di sicurezza sempre più dirompenti e crimini informatici.</span><span class="sxs-lookup"><span data-stu-id="d403c-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="d403c-108">Anche se è importante adottare misure preventive, la capacità di agire rapidamente per contenere, eliminare e recuperare dagli incidenti rilevati può ridurre al minimo i danni e le perdite aziendali.</span><span class="sxs-lookup"><span data-stu-id="d403c-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="d403c-109">Questa procedura dettagliata di risposta agli eventi imprevisti mostra come l'utente, come parte di un team delle operazioni di sicurezza, può eseguire la maggior parte dei passaggi chiave di risposta agli eventi imprevisti all'interno di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d403c-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="d403c-110">Ecco la procedura:</span><span class="sxs-lookup"><span data-stu-id="d403c-110">Here are the steps:</span></span>

- <span data-ttu-id="d403c-111">Preparazione della posizione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d403c-111">Preparation of your security posture</span></span>
- <span data-ttu-id="d403c-112">Per ogni evento imprevisto:</span><span class="sxs-lookup"><span data-stu-id="d403c-112">For each incident:</span></span>
  - <span data-ttu-id="d403c-113">Passaggio 1: analisi e analisi</span><span class="sxs-lookup"><span data-stu-id="d403c-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="d403c-114">Passaggio 2: correzione (contenimento, eradicazione e ripristino)</span><span class="sxs-lookup"><span data-stu-id="d403c-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="d403c-115">Passaggio 3: revisione post-incidente</span><span class="sxs-lookup"><span data-stu-id="d403c-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="d403c-116">Un incidente di sicurezza è definito dal National Institute of Standards and Technology (NIST) come "un evento che in realtà o potenzialmente mette a rischio la riservatezza, l'integrità o la disponibilità di un sistema di informazioni; o le informazioni che il sistema elabora, archivia o trasmette; o che costituisce una violazione o una minaccia imminente di violazione dei criteri di sicurezza, delle procedure di sicurezza o dei criteri di utilizzo accettabili."</span><span class="sxs-lookup"><span data-stu-id="d403c-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="d403c-117">Gli incidenti in Microsoft 365 Defender sono i punti di partenza logici per l'analisi e la risposta agli incidenti.</span><span class="sxs-lookup"><span data-stu-id="d403c-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="d403c-118">L'analisi e la correzione degli eventi imprevisti in genere costituisce la maggior parte delle attività di un team delle operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d403c-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="d403c-119">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d403c-119">Next step</span></span>

<span data-ttu-id="d403c-120">[![Preparare l'organizzazione e Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="d403c-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="d403c-121">Verificare che l'organizzazione e Microsoft 365 tenant siano [pronti per la gestione degli eventi imprevisti.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="d403c-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d403c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d403c-122">See also</span></span>

<span data-ttu-id="d403c-123">Indicazioni per la risposta agli eventi imprevisti per Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="d403c-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="d403c-124">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="d403c-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d403c-125">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="d403c-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d403c-126">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="d403c-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="d403c-127">Esempi aggiuntivi di prime risposte agli eventi imprevisti:</span><span class="sxs-lookup"><span data-stu-id="d403c-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="d403c-128">Posta di phishing</span><span class="sxs-lookup"><span data-stu-id="d403c-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="d403c-129">Attacco di base dell'identità</span><span class="sxs-lookup"><span data-stu-id="d403c-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="d403c-130">Playbook dettagliati sulla risposta agli incidenti</span><span class="sxs-lookup"><span data-stu-id="d403c-130">Detailed incident response playbooks</span></span>](/security/compass/incident-response-playbooks)


