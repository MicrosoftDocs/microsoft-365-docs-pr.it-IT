---
title: Compatibilità di Microsoft Defender Antivirus con Defender for Endpoint
description: Informazioni su come Windows Defender con Microsoft Defender per Endpoint e su come funziona quando viene utilizzato un client antimalware di terze parti.
keywords: Compatibilità con windows Defender, defender, microsoft defender atp, defender per endpoint, antivirus, mde
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
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165958"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="fc507-104">Compatibilità di Microsoft Defender Antivirus con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fc507-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc507-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fc507-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc507-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="fc507-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc507-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc507-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fc507-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="fc507-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc507-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="fc507-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="fc507-110">L'agente microsoft Defender for Endpoint dipende da Microsoft Defender Antivirus per alcune funzionalità, ad esempio l'analisi dei file.</span><span class="sxs-lookup"><span data-stu-id="fc507-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fc507-111">Defender for Endpoint non rispetta le impostazioni di esclusione di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="fc507-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="fc507-112">Devi configurare gli aggiornamenti di Security intelligence in Defender per i dispositivi endpoint indipendentemente dal fatto che Microsoft Defender Antivirus sia l'antimalware attivo o meno.</span><span class="sxs-lookup"><span data-stu-id="fc507-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="fc507-113">Per altre informazioni, vedi [Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fc507-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="fc507-114">Se un dispositivo onboarded è protetto da un client antimalware di terze parti, Microsoft Defender Antivirus su tale endpoint entra in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="fc507-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="fc507-115">Microsoft Defender Antivirus continuerà a ricevere gli aggiornamenti e il processo *dimspeng.exe* verrà elencato come un servizio in esecuzione, ma non eseguirà analisi e non sostituirà il client antimalware di terze parti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fc507-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="fc507-116">L'interfaccia di Microsoft Defender Antivirus verrà disabilitata e gli utenti nel dispositivo non potranno usare Microsoft Defender Antivirus per eseguire analisi su richiesta o configurare la maggior parte delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="fc507-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="fc507-117">Per altre informazioni, vedi l'argomento Microsoft Defender Antivirus e Defender per la compatibilità [degli endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="fc507-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
