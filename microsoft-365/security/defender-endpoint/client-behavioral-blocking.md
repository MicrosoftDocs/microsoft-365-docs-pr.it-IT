---
title: Blocco comportamentale client
description: Il blocco comportamentale client fa parte delle funzionalità di blocco e contenimento comportamentali in Microsoft Defender for Endpoint
keywords: blocco comportamentale, protezione rapida, comportamento client, Microsoft Defender ATP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 9fcff96b2583c6ef6bec05429ec50a71f3872e43
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587108"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="d294a-104">Blocco comportamentale client</span><span class="sxs-lookup"><span data-stu-id="d294a-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d294a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d294a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d294a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d294a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d294a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d294a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d294a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d294a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d294a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d294a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="d294a-110">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d294a-110">Overview</span></span>

<span data-ttu-id="d294a-111">Il blocco comportamentale del client è un componente delle funzionalità di blocco [e contenimento comportamentali](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d294a-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="d294a-112">Quando vengono rilevati comportamenti sospetti nei dispositivi (denominati anche client o endpoint), gli artefatti (ad esempio file o applicazioni) vengono bloccati, controllati e corretti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d294a-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protezione cloud e client":::

<span data-ttu-id="d294a-114">La protezione antivirus funziona meglio se abbinata alla protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="d294a-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="d294a-115">Funzionamento del blocco comportamentale client</span><span class="sxs-lookup"><span data-stu-id="d294a-115">How client behavioral blocking works</span></span>

<span data-ttu-id="d294a-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) è in grado di rilevare comportamenti sospetti, codice dannoso, attacchi senza file e in memoria e altro ancora in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d294a-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="d294a-117">Quando vengono rilevati comportamenti sospetti, Microsoft Defender Antivirus monitora e invia tali comportamenti sospetti e i relativi alberi di processo al servizio di protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="d294a-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="d294a-118">L'apprendimento automatico distingue tra applicazioni dannose e comportamenti buoni in pochi millisecondi e classifica ogni artefatto.</span><span class="sxs-lookup"><span data-stu-id="d294a-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="d294a-119">In tempo quasi reale, non appena un artefatto viene rilevato dannoso, viene bloccato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d294a-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="d294a-120">Ogni volta che viene rilevato un comportamento sospetto, [viene](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) generato un avviso ed è visibile in Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="d294a-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="d294a-121">Il blocco comportamentale del client è efficace perché non solo consente di impedire l'avvio di un attacco, ma può aiutare a interrompere un attacco che ha iniziato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d294a-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="d294a-122">Inoltre, con [il blocco del ciclo](feedback-loop-blocking.md) di feedback (un'altra funzionalità di blocco e contenimento comportamentale), gli attacchi vengono impediti su altri dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d294a-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="d294a-123">Rilevamenti basati sul comportamento</span><span class="sxs-lookup"><span data-stu-id="d294a-123">Behavior-based detections</span></span>

<span data-ttu-id="d294a-124">I rilevamenti basati sul comportamento sono denominati in base [all'ATT MITRE&CK Matrix for Enterprise.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="d294a-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="d294a-125">La convenzione di denominazione consente di identificare la fase di attacco in cui è stato osservato il comportamento dannoso:</span><span class="sxs-lookup"><span data-stu-id="d294a-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="d294a-126">Tattica</span><span class="sxs-lookup"><span data-stu-id="d294a-126">Tactic</span></span> |   <span data-ttu-id="d294a-127">Nome minaccia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d294a-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="d294a-128">Accesso iniziale</span><span class="sxs-lookup"><span data-stu-id="d294a-128">Initial Access</span></span> | <span data-ttu-id="d294a-129">Behavior:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="d294a-130">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="d294a-130">Execution</span></span>  | <span data-ttu-id="d294a-131">Behavior:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="d294a-132">Persistenza</span><span class="sxs-lookup"><span data-stu-id="d294a-132">Persistence</span></span>    | <span data-ttu-id="d294a-133">Behavior:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="d294a-134">Escalation dei privilegi</span><span class="sxs-lookup"><span data-stu-id="d294a-134">Privilege Escalation</span></span>   | <span data-ttu-id="d294a-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="d294a-136">Evasione della difesa</span><span class="sxs-lookup"><span data-stu-id="d294a-136">Defense Evasion</span></span>    | <span data-ttu-id="d294a-137">Behavior:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="d294a-138">Accesso credenziali</span><span class="sxs-lookup"><span data-stu-id="d294a-138">Credential Access</span></span>  | <span data-ttu-id="d294a-139">Behavior:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="d294a-140">Individuazione</span><span class="sxs-lookup"><span data-stu-id="d294a-140">Discovery</span></span>  | <span data-ttu-id="d294a-141">Behavior:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="d294a-142">Movimento laterale</span><span class="sxs-lookup"><span data-stu-id="d294a-142">Lateral Movement</span></span> | <span data-ttu-id="d294a-143">Behavior:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="d294a-144">Raccolta</span><span class="sxs-lookup"><span data-stu-id="d294a-144">Collection</span></span> |   <span data-ttu-id="d294a-145">Behavior:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="d294a-146">Comando e controllo</span><span class="sxs-lookup"><span data-stu-id="d294a-146">Command and Control</span></span> | <span data-ttu-id="d294a-147">Behavior:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="d294a-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="d294a-148">Exfiltration</span></span>   | <span data-ttu-id="d294a-149">Behavior:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="d294a-150">Impatto</span><span class="sxs-lookup"><span data-stu-id="d294a-150">Impact</span></span> | <span data-ttu-id="d294a-151">Behavior:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="d294a-152">Non classificato</span><span class="sxs-lookup"><span data-stu-id="d294a-152">Uncategorized</span></span>  | <span data-ttu-id="d294a-153">Behavior:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="d294a-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="d294a-154">Per ulteriori informazioni sulle minacce specifiche, vedere **[Attività di minacce globali recenti.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="d294a-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="d294a-155">Configurazione del blocco comportamentale del client</span><span class="sxs-lookup"><span data-stu-id="d294a-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="d294a-156">Se l'organizzazione usa Defender per Endpoint, il blocco comportamentale del client è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d294a-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="d294a-157">Tuttavia, per trarre vantaggio da tutte le funzionalità di Defender for Endpoint, tra cui il blocco comportamentale e il [contenimento,](behavioral-blocking-containment.md)assicurati che le funzionalità e le funzionalità seguenti di Defender for Endpoint siano abilitate e configurate:</span><span class="sxs-lookup"><span data-stu-id="d294a-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="d294a-158">Linee di base di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d294a-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="d294a-159">Dispositivi onboarded in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d294a-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="d294a-160">EdR in modalità blocco</span><span class="sxs-lookup"><span data-stu-id="d294a-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="d294a-161">Riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="d294a-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="d294a-162">[Protezione di nuova generazione](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="d294a-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="d294a-163">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="d294a-163">Related articles</span></span>

- [<span data-ttu-id="d294a-164">Blocco e contenimento comportamentale</span><span class="sxs-lookup"><span data-stu-id="d294a-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="d294a-165">Blocco del ciclo di feedback</span><span class="sxs-lookup"><span data-stu-id="d294a-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="d294a-166">(Blog) Blocco e contenimento comportamentali: trasformazione dell'ottica in protezione</span><span class="sxs-lookup"><span data-stu-id="d294a-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="d294a-167">Defender utile per le risorse endpoint</span><span class="sxs-lookup"><span data-stu-id="d294a-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
