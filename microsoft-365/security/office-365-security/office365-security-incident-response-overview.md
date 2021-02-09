---
title: Risposta agli incidenti di sicurezza
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Questa soluzione indica l'aspetto degli attacchi di cybersecurity più comuni in Microsoft 365 e come rispondere a tali attacchi
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8dd7a90255fdd3e083a5d7306cac2e9ca6411024
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150184"
---
# <a name="security-incident-response"></a><span data-ttu-id="0ebbc-103">Risposta agli incidenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0ebbc-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ebbc-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="0ebbc-104">**Applies to**</span></span>
- [<span data-ttu-id="0ebbc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ebbc-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="0ebbc-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="0ebbc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="0ebbc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ebbc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="0ebbc-108">**Riepilogo:** Questa soluzione indica quali sono gli indicatori per gli attacchi di cybersecurity più comuni in Office 365, come confermare in modo positivo qualsiasi attacco e come rispondere ad esso.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="0ebbc-109">Informazioni su come rispondere agli attacchi informatici</span><span class="sxs-lookup"><span data-stu-id="0ebbc-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="0ebbc-110">Non tutti gli attacchi informatici possono essere sventati.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="0ebbc-111">Gli utenti malintenzionati cercano costantemente nuove debolezze nella strategia difensiva o sfruttano quelli precedenti.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="0ebbc-112">Sapere come riconoscere un attacco consente di rispondere più velocemente, riducendo la durata dell'incidente di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="0ebbc-113">Questa serie di articoli consente di comprendere l'aspetto di un particolare tipo di attacco in Microsoft 365 e fornisce le procedure necessarie per rispondere.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="0ebbc-114">Sono punti di ingresso rapidi da comprendere:</span><span class="sxs-lookup"><span data-stu-id="0ebbc-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="0ebbc-115">Cos'è l'attacco e come funziona.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="0ebbc-116">Quali segnali, denominati indicatori di compromissione (IOC), da cercare e come cercarli.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="0ebbc-117">Come confermare l'attacco in modo positivo.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="0ebbc-118">Passaggi da eseguire per ridurre l'attacco e proteggere meglio l'organizzazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="0ebbc-119">Collegamenti a informazioni approfondite su ogni tipo di attacco.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="0ebbc-120">Torna qui mensilmente perché verranno aggiunti altri articoli nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="0ebbc-121">Rilevare e correggere gli articoli</span><span class="sxs-lookup"><span data-stu-id="0ebbc-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="0ebbc-122">Rilevare e rimediare a concessioni di consenso illecite in Office 365</span><span class="sxs-lookup"><span data-stu-id="0ebbc-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="0ebbc-123">Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Office 365</span><span class="sxs-lookup"><span data-stu-id="0ebbc-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="0ebbc-124">Articoli sulla risposta a eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="0ebbc-124">Incident response articles</span></span>

- [<span data-ttu-id="0ebbc-125">Rispondere a un account di posta elettronica compromesso in Office 365</span><span class="sxs-lookup"><span data-stu-id="0ebbc-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="0ebbc-126">Proteggere Microsoft 365 come un professionista della sicurezza informatica</span><span class="sxs-lookup"><span data-stu-id="0ebbc-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="0ebbc-127">L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="0ebbc-128">Usare la roadmap per la sicurezza di Microsoft 365- Priorità principali per i primi [30 giorni, 90](security-roadmap.md) giorni e oltre per implementare le procedure consigliate da Microsoft per proteggere l'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="0ebbc-129">Attività da eseguire i primi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="0ebbc-130">Queste hanno effetto immediato e sono a basso impatto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="0ebbc-131">Attività da completare in 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="0ebbc-132">La pianificazione e l'implementazione di queste attività impietosino un po' più di tempo, ma migliorano notevolmente la sicurezza</span><span class="sxs-lookup"><span data-stu-id="0ebbc-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="0ebbc-133">Dopo 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-133">Beyond 90 days.</span></span> <span data-ttu-id="0ebbc-134">Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.</span><span class="sxs-lookup"><span data-stu-id="0ebbc-134">These enhancements build in your first 90 days work.</span></span>
