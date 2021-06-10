---
title: Rilevare e bloccare le applicazioni potenzialmente indesiderate con Microsoft Defender per Endpoint su Linux
description: Rilevare e bloccare le applicazioni potenzialmente indesiderate usando Microsoft Defender per Endpoint su Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, pua, pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7ec3399129cc65d75b464f5d5f56bb11250ccaf2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933158"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="8a29b-104">Rilevare e bloccare le applicazioni potenzialmente indesiderate con Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="8a29b-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8a29b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8a29b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a29b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8a29b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8a29b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a29b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8a29b-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8a29b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8a29b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8a29b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8a29b-110">La funzionalità di protezione delle applicazioni potenzialmente indesiderate in Defender for Endpoint su Linux può rilevare e bloccare i file PUA negli endpoint della rete.</span><span class="sxs-lookup"><span data-stu-id="8a29b-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint on Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="8a29b-111">Queste applicazioni non sono considerate virus, malware o altri tipi di minacce, ma possono eseguire azioni sugli endpoint che influiscono negativamente sulle prestazioni o sull'uso.</span><span class="sxs-lookup"><span data-stu-id="8a29b-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="8a29b-112">PuA può anche fare riferimento ad applicazioni considerate di scarsa reputazione.</span><span class="sxs-lookup"><span data-stu-id="8a29b-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="8a29b-113">Queste applicazioni possono aumentare il rischio che la rete sia infettata da malware, causare infezioni da malware più difficili da identificare e può sprecare risorse IT nella pulizia delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8a29b-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="8a29b-114">Come funziona</span><span class="sxs-lookup"><span data-stu-id="8a29b-114">How it works</span></span>

<span data-ttu-id="8a29b-115">Defender per Endpoint su Linux può rilevare e segnalare i file PUA.</span><span class="sxs-lookup"><span data-stu-id="8a29b-115">Defender for Endpoint on Linux can detect and report PUA files.</span></span> <span data-ttu-id="8a29b-116">Se configurati in modalità di blocco, i file PUA vengono spostati in quarantena.</span><span class="sxs-lookup"><span data-stu-id="8a29b-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="8a29b-117">Quando viene rilevata una puA in un endpoint, Defender per Endpoint su Linux mantiene un record dell'infezione nella cronologia delle minacce.</span><span class="sxs-lookup"><span data-stu-id="8a29b-117">When a PUA is detected on an endpoint, Defender for Endpoint on Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="8a29b-118">La cronologia può essere visualizzato dal portale Microsoft Defender Security Center o tramite lo `mdatp` strumento da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8a29b-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="8a29b-119">Il nome della minaccia conterrà la parola "Applicazione".</span><span class="sxs-lookup"><span data-stu-id="8a29b-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="8a29b-120">Configurare la protezione puA</span><span class="sxs-lookup"><span data-stu-id="8a29b-120">Configure PUA protection</span></span>

<span data-ttu-id="8a29b-121">La protezione dell'applicazione di accesso basato su accesso pubblico in Defender per Endpoint su Linux può essere configurata in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a29b-121">PUA protection in Defender for Endpoint on Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="8a29b-122">**Disattivato:** la protezione dell'applicazione può essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="8a29b-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="8a29b-123">**Controllo:** i file PUA vengono riportati nei log del prodotto, ma non in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="8a29b-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="8a29b-124">Nella cronologia delle minacce non viene archiviato alcun record dell'infezione e non viene eseguita alcuna azione da parte del prodotto.</span><span class="sxs-lookup"><span data-stu-id="8a29b-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="8a29b-125">**Blocca:** i file PUA vengono riportati nei log del prodotto e Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="8a29b-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="8a29b-126">Un record dell'infezione viene archiviato nella cronologia delle minacce e l'azione viene eseguita dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="8a29b-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="8a29b-127">Per impostazione predefinita, la protezione puA è configurata in **modalità** di controllo.</span><span class="sxs-lookup"><span data-stu-id="8a29b-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="8a29b-128">È possibile configurare la modalità di gestione dei file PUA dalla riga di comando o dalla console di gestione.</span><span class="sxs-lookup"><span data-stu-id="8a29b-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="8a29b-129">Utilizzare lo strumento da riga di comando per configurare la protezione da accesso basato su account utente:</span><span class="sxs-lookup"><span data-stu-id="8a29b-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="8a29b-130">In Terminale, eseguire il comando seguente per configurare la protezione puA:</span><span class="sxs-lookup"><span data-stu-id="8a29b-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="8a29b-131">Utilizzare la console di gestione per configurare la protezione dell'account di accesso alla posta elettronica:Use the management console to configure PUA protection:</span><span class="sxs-lookup"><span data-stu-id="8a29b-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="8a29b-132">Nella tua azienda puoi configurare la protezione puA da una console di gestione, ad esempio Pupazzo o Ansible, in modo analogo alla configurazione di altre impostazioni del prodotto.</span><span class="sxs-lookup"><span data-stu-id="8a29b-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="8a29b-133">Per altre informazioni, vedi la sezione [Impostazioni del tipo di](linux-preferences.md#threat-type-settings) minaccia dell'articolo Impostare le preferenze per Defender per Endpoint su [Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="8a29b-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint on Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8a29b-134">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="8a29b-134">Related articles</span></span>

- [<span data-ttu-id="8a29b-135">Impostare le preferenze per Defender per Endpoint in Linux</span><span class="sxs-lookup"><span data-stu-id="8a29b-135">Set preferences for Defender for Endpoint on Linux</span></span>](linux-preferences.md)
