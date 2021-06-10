---
title: Blocco comportamentale client
description: Il blocco comportamentale client fa parte delle funzionalità di blocco e contenimento comportamentali in Microsoft Defender for Endpoint
keywords: blocco comportamentale, protezione rapida, comportamento client, Microsoft Defender for Endpoint
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
ms.openlocfilehash: 295987ad28675b4381e266539846563240c0a528
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866656"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="21a67-104">Blocco comportamentale client</span><span class="sxs-lookup"><span data-stu-id="21a67-104">Client behavioral blocking</span></span>

<span data-ttu-id="21a67-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="21a67-105">**Applies to:**</span></span>
- [<span data-ttu-id="21a67-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="21a67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="21a67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21a67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="21a67-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="21a67-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="21a67-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="21a67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="21a67-110">Panoramica</span><span class="sxs-lookup"><span data-stu-id="21a67-110">Overview</span></span>

<span data-ttu-id="21a67-111">Il blocco comportamentale del client è un componente delle funzionalità di blocco [e contenimento comportamentali](behavioral-blocking-containment.md) in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="21a67-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="21a67-112">Quando vengono rilevati comportamenti sospetti nei dispositivi (denominati anche client o endpoint), gli artefatti (ad esempio file o applicazioni) vengono bloccati, controllati e corretti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="21a67-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protezione cloud e client":::

<span data-ttu-id="21a67-114">La protezione antivirus funziona meglio se abbinata alla protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="21a67-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="21a67-115">Funzionamento del blocco comportamentale client</span><span class="sxs-lookup"><span data-stu-id="21a67-115">How client behavioral blocking works</span></span>

<span data-ttu-id="21a67-116">[Antivirus Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) in grado di rilevare comportamenti sospetti, codice dannoso, attacchi senza file e in memoria e altro ancora in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="21a67-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="21a67-117">Quando vengono rilevati comportamenti sospetti, Antivirus Microsoft Defender questi comportamenti sospetti e i relativi alberi di processo vengono monitorati e inviati al servizio di protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="21a67-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="21a67-118">L'apprendimento automatico distingue tra applicazioni dannose e comportamenti buoni in pochi millisecondi e classifica ogni artefatto.</span><span class="sxs-lookup"><span data-stu-id="21a67-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="21a67-119">In tempo quasi reale, non appena un artefatto viene rilevato dannoso, viene bloccato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="21a67-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="21a67-120">Ogni volta che viene rilevato un comportamento sospetto, [viene](alerts-queue.md) generato un avviso ed è visibile nel Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="21a67-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="21a67-121">Il blocco comportamentale del client è efficace perché non solo consente di impedire l'avvio di un attacco, ma può aiutare a interrompere un attacco che ha iniziato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21a67-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="21a67-122">Inoltre, con [il blocco del ciclo](feedback-loop-blocking.md) di feedback (un'altra funzionalità di blocco e contenimento comportamentale), gli attacchi vengono impediti su altri dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21a67-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="21a67-123">Rilevamenti basati sul comportamento</span><span class="sxs-lookup"><span data-stu-id="21a67-123">Behavior-based detections</span></span>

<span data-ttu-id="21a67-124">I rilevamenti basati sul comportamento sono denominati in base alla matrice [MITRE ATT&CK per Enterprise](https://attack.mitre.org/matrices/enterprise).</span><span class="sxs-lookup"><span data-stu-id="21a67-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="21a67-125">La convenzione di denominazione consente di identificare la fase di attacco in cui è stato osservato il comportamento dannoso:</span><span class="sxs-lookup"><span data-stu-id="21a67-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="21a67-126">Tattica</span><span class="sxs-lookup"><span data-stu-id="21a67-126">Tactic</span></span> |   <span data-ttu-id="21a67-127">Nome minaccia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="21a67-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="21a67-128">Accesso iniziale</span><span class="sxs-lookup"><span data-stu-id="21a67-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="21a67-129">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="21a67-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="21a67-130">Persistenza</span><span class="sxs-lookup"><span data-stu-id="21a67-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="21a67-131">Escalation dei privilegi</span><span class="sxs-lookup"><span data-stu-id="21a67-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="21a67-132">Evasione della difesa</span><span class="sxs-lookup"><span data-stu-id="21a67-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="21a67-133">Accesso credenziali</span><span class="sxs-lookup"><span data-stu-id="21a67-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="21a67-134">Individuazione</span><span class="sxs-lookup"><span data-stu-id="21a67-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="21a67-135">Movimento laterale</span><span class="sxs-lookup"><span data-stu-id="21a67-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="21a67-136">Raccolta</span><span class="sxs-lookup"><span data-stu-id="21a67-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="21a67-137">Comando e controllo</span><span class="sxs-lookup"><span data-stu-id="21a67-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="21a67-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="21a67-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="21a67-139">Impatto</span><span class="sxs-lookup"><span data-stu-id="21a67-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="21a67-140">Non classificato</span><span class="sxs-lookup"><span data-stu-id="21a67-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="21a67-141">Per ulteriori informazioni sulle minacce specifiche, vedere **[Attività di minacce globali recenti.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="21a67-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="21a67-142">Configurazione del blocco comportamentale del client</span><span class="sxs-lookup"><span data-stu-id="21a67-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="21a67-143">Se l'organizzazione usa Defender per Endpoint, il blocco comportamentale del client è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="21a67-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="21a67-144">Tuttavia, per trarre vantaggio da tutte le funzionalità di Defender for Endpoint, tra cui il blocco comportamentale e il [contenimento,](behavioral-blocking-containment.md)assicurati che le funzionalità e le funzionalità seguenti di Defender for Endpoint siano abilitate e configurate:</span><span class="sxs-lookup"><span data-stu-id="21a67-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="21a67-145">Linee di base di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="21a67-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="21a67-146">Dispositivi onboarded in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="21a67-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="21a67-147">EdR in modalità blocco</span><span class="sxs-lookup"><span data-stu-id="21a67-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="21a67-148">Riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="21a67-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="21a67-149">[Protezione di nuova generazione](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware e altre funzionalità di protezione dalle minacce)</span><span class="sxs-lookup"><span data-stu-id="21a67-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

