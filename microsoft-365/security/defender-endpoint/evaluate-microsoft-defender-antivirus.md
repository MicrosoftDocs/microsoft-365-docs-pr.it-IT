---
title: Valutare Microsoft Defender Antivirus
description: Le aziende di tutte le dimensioni possono usare questa guida per valutare e testare la protezione offerta da Microsoft Defender Antivirus in Windows 10.
keywords: Microsoft Defender Antivirus, protezione cloud, cloud, antimalware, sicurezza, defender, valutare, testare, proteggere, confrontare, protezione in tempo reale
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764832"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="3199e-104">Valutare Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3199e-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3199e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3199e-105">**Applies to:**</span></span>

- [<span data-ttu-id="3199e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3199e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3199e-107">Usa questa guida per determinare il livello di protezione di Microsoft Defender Antivirus da virus, malware e applicazioni potenzialmente indesiderate.</span><span class="sxs-lookup"><span data-stu-id="3199e-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="3199e-108">Puoi anche visitare il sito Web demo di Microsoft Defender for Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che le funzionalità seguenti funzionino e vedere come funzionano:</span><span class="sxs-lookup"><span data-stu-id="3199e-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="3199e-109">Protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="3199e-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="3199e-110">Apprendimento rapido (incluso Blocco a prima vista)</span><span class="sxs-lookup"><span data-stu-id="3199e-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="3199e-111">Blocco di applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="3199e-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="3199e-112">Spiega le importanti funzionalità di protezione di nuova generazione di Microsoft Defender Antivirus disponibili sia per le piccole che per le grandi aziende e come aumentano il rilevamento e la protezione da malware nella rete.</span><span class="sxs-lookup"><span data-stu-id="3199e-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="3199e-113">Puoi scegliere di configurare e valutare ogni impostazione in modo indipendente o contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3199e-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="3199e-114">Sono state raggruppate impostazioni simili in base a scenari di valutazione tipici e sono incluse istruzioni per l'utilizzo di PowerShell per abilitare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3199e-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="3199e-115">La guida è disponibile in formato PDF per la visualizzazione offline:</span><span class="sxs-lookup"><span data-stu-id="3199e-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="3199e-116">Scaricare la guida in formato PDF</span><span class="sxs-lookup"><span data-stu-id="3199e-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="3199e-117">Puoi anche scaricare powershell che abiliterà automaticamente tutte le impostazioni descritte nella guida.</span><span class="sxs-lookup"><span data-stu-id="3199e-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="3199e-118">Puoi ottenere lo script insieme al download pdf precedente o singolarmente da PowerShell Gallery:</span><span class="sxs-lookup"><span data-stu-id="3199e-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="3199e-119">Scaricare lo script di PowerShell per configurare automaticamente le impostazioni</span><span class="sxs-lookup"><span data-stu-id="3199e-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="3199e-120">La guida è attualmente destinata alla valutazione a computer singolo di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3199e-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3199e-121">L'abilitazione di tutte le impostazioni in questa guida potrebbe non essere adatta per la distribuzione reale.</span><span class="sxs-lookup"><span data-stu-id="3199e-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="3199e-122">Per i consigli più recenti per la distribuzione e il monitoraggio di Microsoft Defender Antivirus in una rete, vedi [Distribuire Microsoft Defender Antivirus.](deploy-manage-report-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3199e-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3199e-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3199e-123">Related topics</span></span>

- [<span data-ttu-id="3199e-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="3199e-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="3199e-125">Distribuire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3199e-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)