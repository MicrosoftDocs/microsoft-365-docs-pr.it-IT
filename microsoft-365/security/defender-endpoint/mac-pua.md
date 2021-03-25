---
title: Rilevare e bloccare le applicazioni potenzialmente indesiderate con Microsoft Defender ATP per Mac
description: Rilevare e bloccare le applicazioni potenzialmente indesiderate usando Microsoft Defender ATP per Mac.
keywords: microsoft, defender, atp, mac, pua, pus
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
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187422"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="32ee3-104">Rilevare e bloccare le applicazioni potenzialmente indesiderate con Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="32ee3-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="32ee3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="32ee3-105">**Applies to:**</span></span>
- [<span data-ttu-id="32ee3-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="32ee3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="32ee3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32ee3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="32ee3-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="32ee3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="32ee3-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="32ee3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="32ee3-110">La funzionalità di protezione delle applicazioni potenzialmente indesiderate in Microsoft Defender per Endpoint per Mac può rilevare e bloccare i file PUA negli endpoint della rete.</span><span class="sxs-lookup"><span data-stu-id="32ee3-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="32ee3-111">Queste applicazioni non sono considerate virus, malware o altri tipi di minacce, ma possono eseguire azioni sugli endpoint che influiscono negativamente sulle prestazioni o sull'uso.</span><span class="sxs-lookup"><span data-stu-id="32ee3-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="32ee3-112">PuA può anche fare riferimento ad applicazioni considerate di scarsa reputazione.</span><span class="sxs-lookup"><span data-stu-id="32ee3-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="32ee3-113">Queste applicazioni possono aumentare il rischio che la rete sia infettata da malware, causare infezioni da malware più difficili da identificare e può sprecare risorse IT nella pulizia delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="32ee3-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="32ee3-114">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="32ee3-114">How it works</span></span>

<span data-ttu-id="32ee3-115">Microsoft Defender per Endpoint per Mac può rilevare e segnalare i file PUA.</span><span class="sxs-lookup"><span data-stu-id="32ee3-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="32ee3-116">Se configurati in modalità di blocco, i file PUA vengono spostati in quarantena.</span><span class="sxs-lookup"><span data-stu-id="32ee3-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="32ee3-117">Quando viene rilevata una puA in un endpoint, Microsoft Defender per Endpoint per Mac presenta una notifica all'utente, a meno che le notifiche non siano state disabilitate.</span><span class="sxs-lookup"><span data-stu-id="32ee3-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="32ee3-118">Il nome della minaccia conterrà la parola "Applicazione".</span><span class="sxs-lookup"><span data-stu-id="32ee3-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="32ee3-119">Configurare la protezione puA</span><span class="sxs-lookup"><span data-stu-id="32ee3-119">Configure PUA protection</span></span>

<span data-ttu-id="32ee3-120">La protezione delle app di accesso pubblico in Microsoft Defender per Endpoint per Mac può essere configurata in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="32ee3-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="32ee3-121">**Disattivato:** la protezione dell'applicazione può essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="32ee3-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="32ee3-122">**Controllo:** i file PUA vengono riportati nei log del prodotto, ma non in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="32ee3-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="32ee3-123">All'utente non viene presentata alcuna notifica e non viene eseguita alcuna azione da parte del prodotto.</span><span class="sxs-lookup"><span data-stu-id="32ee3-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="32ee3-124">**Blocca:** i file PUA vengono segnalati nei log del prodotto e in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="32ee3-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="32ee3-125">All'utente viene presentata una notifica e viene eseguita un'azione da parte del prodotto.</span><span class="sxs-lookup"><span data-stu-id="32ee3-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="32ee3-126">Per impostazione predefinita, la protezione puA è configurata in **modalità** di controllo.</span><span class="sxs-lookup"><span data-stu-id="32ee3-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="32ee3-127">È possibile configurare la modalità di gestione dei file PUA dalla riga di comando o dalla console di gestione.</span><span class="sxs-lookup"><span data-stu-id="32ee3-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="32ee3-128">Utilizzare lo strumento da riga di comando per configurare la protezione da accesso basato su account utente:</span><span class="sxs-lookup"><span data-stu-id="32ee3-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="32ee3-129">In Terminale, eseguire il comando seguente per configurare la protezione puA:</span><span class="sxs-lookup"><span data-stu-id="32ee3-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="32ee3-130">Utilizzare la console di gestione per configurare la protezione dell'account di accesso alla posta elettronica:Use the management console to configure PUA protection:</span><span class="sxs-lookup"><span data-stu-id="32ee3-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="32ee3-131">Nell'organizzazione, è possibile configurare la protezione puA da una console di gestione, ad esempio JAMF o Intune, in modo analogo alla configurazione di altre impostazioni del prodotto.</span><span class="sxs-lookup"><span data-stu-id="32ee3-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="32ee3-132">Per altre informazioni, vedi la sezione Impostazioni del [tipo di](mac-preferences.md#threat-type-settings) minaccia dell'argomento Impostare le preferenze per Microsoft Defender per Endpoint [per Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="32ee3-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32ee3-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="32ee3-133">Related topics</span></span>

- [<span data-ttu-id="32ee3-134">Impostare le preferenze per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="32ee3-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)
