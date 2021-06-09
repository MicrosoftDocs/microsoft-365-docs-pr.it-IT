---
title: Blocco del ciclo di feedback
description: Il blocco del ciclo di feedback, denominato anche protezione rapida, fa parte delle funzionalità di blocco e contenimento comportamentali in Microsoft Defender for Endpoint
keywords: behavioral blocking, rapid protection, feedback blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842459"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="88668-104">Blocco del ciclo di feedback</span><span class="sxs-lookup"><span data-stu-id="88668-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="88668-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="88668-105">**Applies to:**</span></span>
- [<span data-ttu-id="88668-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="88668-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="88668-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="88668-107">Overview</span></span>

<span data-ttu-id="88668-108">Il blocco del ciclo di feedback, noto anche come protezione rapida, è un componente delle funzionalità di blocco e [contenimento](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) comportamentali in [Microsoft Defender per Endpoint.](/windows/security/threat-protection/)</span><span class="sxs-lookup"><span data-stu-id="88668-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](/windows/security/threat-protection/).</span></span> <span data-ttu-id="88668-109">Con il blocco del ciclo di feedback, i dispositivi all'interno dell'organizzazione sono meglio protetti dagli attacchi.</span><span class="sxs-lookup"><span data-stu-id="88668-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="88668-110">Funzionamento del blocco del ciclo di feedback</span><span class="sxs-lookup"><span data-stu-id="88668-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="88668-111">Quando viene rilevato un comportamento o un file sospetto, ad esempio da Antivirus Microsoft Defender [,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)le informazioni sull'artefatto vengono inviate a più classificatori.</span><span class="sxs-lookup"><span data-stu-id="88668-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="88668-112">Il motore loop di protezione rapida esamina e correla le informazioni con altri segnali per arrivare a una decisione se bloccare un file.</span><span class="sxs-lookup"><span data-stu-id="88668-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="88668-113">Il controllo e la classificazione degli artefatti avviene rapidamente.</span><span class="sxs-lookup"><span data-stu-id="88668-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="88668-114">Si verifica un rapido blocco del malware confermato e la protezione viene estesa all'intero ecosistema.</span><span class="sxs-lookup"><span data-stu-id="88668-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="88668-115">Con la protezione rapida in atto, un attacco può essere arrestato su un dispositivo, altri dispositivi nell'organizzazione e dispositivi in altre organizzazioni, mentre un attacco tenta di ampliare il proprio punto di appoggio.</span><span class="sxs-lookup"><span data-stu-id="88668-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="88668-116">Configurazione del blocco del ciclo di feedback</span><span class="sxs-lookup"><span data-stu-id="88668-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="88668-117">Se l'organizzazione usa Defender per Endpoint, il blocco del ciclo di feedback è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="88668-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="88668-118">Tuttavia, la protezione rapida avviene tramite una combinazione di funzionalità di Defender for Endpoint, funzionalità di protezione di machine learning e condivisione dei segnali tra i servizi di sicurezza Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88668-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="88668-119">Assicurati che le funzionalità e le funzionalità seguenti di Defender for Endpoint siano abilitate e configurate:</span><span class="sxs-lookup"><span data-stu-id="88668-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="88668-120">Linee di base di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="88668-120">Microsoft Defender for Endpoint baselines</span></span>](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="88668-121">Dispositivi onboarded in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="88668-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="88668-122">EdR in modalità blocco</span><span class="sxs-lookup"><span data-stu-id="88668-122">EDR in block mode</span></span>](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="88668-123">Riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="88668-123">Attack surface reduction</span></span>](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="88668-124">[Protezione di nuova generazione](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="88668-124">[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="88668-125">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="88668-125">Related articles</span></span>

- [<span data-ttu-id="88668-126">Blocco e contenimento comportamentale</span><span class="sxs-lookup"><span data-stu-id="88668-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="88668-127">(Blog) Blocco e contenimento comportamentali: trasformazione dell'ottica in protezione</span><span class="sxs-lookup"><span data-stu-id="88668-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="88668-128">Risorse utili per Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="88668-128">Helpful Microsoft Defender for Endpoint resources</span></span>](/microsoft-365/security/defender-endpoint/helpful-resources)
