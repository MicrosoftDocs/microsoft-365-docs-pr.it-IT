---
title: Abilitare l'accesso condizionale per proteggere meglio utenti, dispositivi e dati
description: Abilitare l'accesso condizionale per impedire l'esecuzione delle applicazioni se un dispositivo è considerato a rischio e un'applicazione è considerata non conforme.
keywords: accesso condizionale, bloccare le applicazioni, livello di sicurezza, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166198"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="a6bee-104">Abilitare l'accesso condizionale per proteggere meglio utenti, dispositivi e dati</span><span class="sxs-lookup"><span data-stu-id="a6bee-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6bee-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a6bee-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6bee-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a6bee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a6bee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6bee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a6bee-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a6bee-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a6bee-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a6bee-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="a6bee-110">L'accesso condizionale è una funzionalità che consente di proteggere meglio gli utenti e le informazioni aziendali assicurando che solo i dispositivi sicuri hanno accesso alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a6bee-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="a6bee-111">Con l'accesso condizionale puoi controllare l'accesso alle informazioni aziendali in base al livello di rischio di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a6bee-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="a6bee-112">Ciò consente di mantenere gli utenti attendibili nei dispositivi attendibili utilizzando applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="a6bee-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="a6bee-113">Puoi definire le condizioni di sicurezza in base alle quali i dispositivi e le applicazioni possono eseguire e accedere alle informazioni dalla rete, mediante l'applicazione di criteri per impedire l'esecuzione delle applicazioni fino a quando un dispositivo non torna a uno stato conforme.</span><span class="sxs-lookup"><span data-stu-id="a6bee-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="a6bee-114">L'implementazione dell'accesso condizionale in Defender for Endpoint si basa sui criteri di conformità dei dispositivi Microsoft Intune (Intune) e sui criteri di accesso condizionale Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a6bee-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="a6bee-115">I criteri di conformità vengono utilizzati con l'accesso condizionale per consentire l'accesso alle applicazioni solo ai dispositivi che soddisfano una o più regole dei criteri di conformità dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a6bee-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="a6bee-116">Informazioni sul flusso di accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="a6bee-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="a6bee-117">L'accesso condizionale viene messo in atto in modo che quando una minaccia viene vista in un dispositivo, l'accesso ai contenuti sensibili viene bloccato fino a quando la minaccia non viene corretti.</span><span class="sxs-lookup"><span data-stu-id="a6bee-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="a6bee-118">Il flusso inizia con i dispositivi a basso, medio o alto rischio.</span><span class="sxs-lookup"><span data-stu-id="a6bee-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="a6bee-119">Queste determinazioni dei rischi vengono quindi inviate a Intune.</span><span class="sxs-lookup"><span data-stu-id="a6bee-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="a6bee-120">A seconda di come si configurano i criteri in Intune, è possibile configurare l'accesso condizionale in modo che, quando vengono soddisfatte determinate condizioni, il criterio viene applicato.</span><span class="sxs-lookup"><span data-stu-id="a6bee-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="a6bee-121">Ad esempio, è possibile configurare Intune per applicare l'accesso condizionale ai dispositivi che hanno un rischio elevato.</span><span class="sxs-lookup"><span data-stu-id="a6bee-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="a6bee-122">In Intune, i criteri di conformità dei dispositivi vengono usati insieme ad Accesso condizionale di Azure AD per bloccare l'accesso alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a6bee-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="a6bee-123">In parallelo, viene avviato un processo di analisi e correzione automatizzato.</span><span class="sxs-lookup"><span data-stu-id="a6bee-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="a6bee-124">Un utente può comunque usare il dispositivo mentre è in corso l'indagine e la correzione automatizzate, ma l'accesso ai dati aziendali viene bloccato fino a quando la minaccia non viene completamente corretti.</span><span class="sxs-lookup"><span data-stu-id="a6bee-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="a6bee-125">Per risolvere il rischio riscontrato in un dispositivo, dovrai riportare il dispositivo a uno stato conforme.</span><span class="sxs-lookup"><span data-stu-id="a6bee-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="a6bee-126">Un dispositivo torna allo stato conforme quando non è presente alcun rischio.</span><span class="sxs-lookup"><span data-stu-id="a6bee-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="a6bee-127">Esistono tre modi per affrontare un rischio:</span><span class="sxs-lookup"><span data-stu-id="a6bee-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="a6bee-128">Usa la correzione manuale o automatica.</span><span class="sxs-lookup"><span data-stu-id="a6bee-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="a6bee-129">Risolvere gli avvisi attivi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a6bee-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="a6bee-130">Questo rimuoverà il rischio dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a6bee-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="a6bee-131">Puoi rimuovere il dispositivo dai criteri attivi e di conseguenza l'accesso condizionale non verrà applicato al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a6bee-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="a6bee-132">La correzione manuale richiede a un amministratore secops di analizzare un avviso e affrontare il rischio visto nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a6bee-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="a6bee-133">La correzione automatica viene configurata tramite le impostazioni di configurazione fornite nella sezione seguente, [Configure Conditional Access](configure-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="a6bee-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="a6bee-134">Quando il rischio viene rimosso tramite correzione manuale o automatica, il dispositivo torna allo stato conforme e viene concesso l'accesso alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a6bee-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="a6bee-135">Nella sequenza di eventi di esempio seguente viene illustrato l'accesso condizionale in azione:</span><span class="sxs-lookup"><span data-stu-id="a6bee-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="a6bee-136">Un utente apre un file dannoso e Defender for Endpoint contrassegna il dispositivo come ad alto rischio.</span><span class="sxs-lookup"><span data-stu-id="a6bee-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="a6bee-137">La valutazione ad alto rischio viene passata a Intune.</span><span class="sxs-lookup"><span data-stu-id="a6bee-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="a6bee-138">In parallelo, viene avviata un'indagine automatizzata per correggere la minaccia identificata.</span><span class="sxs-lookup"><span data-stu-id="a6bee-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="a6bee-139">È inoltre possibile eseguire una correzione manuale per correggere la minaccia identificata.</span><span class="sxs-lookup"><span data-stu-id="a6bee-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="a6bee-140">In base ai criteri creati in Intune, il dispositivo viene contrassegnato come non conforme.</span><span class="sxs-lookup"><span data-stu-id="a6bee-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="a6bee-141">La valutazione viene quindi comunicata ad Azure AD dai criteri di accesso condizionale di Intune.</span><span class="sxs-lookup"><span data-stu-id="a6bee-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="a6bee-142">In Azure AD, il criterio corrispondente viene applicato per bloccare l'accesso alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a6bee-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="a6bee-143">L'analisi e la correzione manuali o automatizzate vengono completate e la minaccia viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="a6bee-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="a6bee-144">Defender for Endpoint vede che il dispositivo non è a rischio e Intune valuta che il dispositivo sia in uno stato conforme.</span><span class="sxs-lookup"><span data-stu-id="a6bee-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="a6bee-145">Azure AD applica il criterio che consente l'accesso alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a6bee-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="a6bee-146">Gli utenti possono ora accedere alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a6bee-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="a6bee-147">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="a6bee-147">Related topic</span></span>
- [<span data-ttu-id="a6bee-148">Configurare l'accesso condizionale in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="a6bee-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
