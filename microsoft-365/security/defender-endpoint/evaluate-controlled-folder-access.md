---
title: Valutare l'accesso controllato alle cartelle
description: Scopri in che modo l'accesso controllato alle cartelle consente di proteggere i file dalle modifiche da parte di app dannose.
keywords: Protezione degli exploit, Windows 10, windows defender, ransomware, proteggere, valutare, testare, demo, provare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e965e1a882dadfb565231074165507a6727b45c1
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218749"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="3c7fd-104">Valutare l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="3c7fd-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c7fd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3c7fd-105">**Applies to:**</span></span>
- [<span data-ttu-id="3c7fd-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3c7fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3c7fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c7fd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3c7fd-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3c7fd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3c7fd-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="3c7fd-110">[L'accesso controllato](controlled-folders.md) alle cartelle è una funzionalità che consente di proteggere i documenti e i file da modifiche da app sospette o dannose.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="3c7fd-111">L'accesso controllato alle cartelle è supportato nei client Windows Server 2019 e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="3c7fd-112">È particolarmente utile per proteggere da [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) che tenta di crittografare i file e tenerli in ostaggio.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="3c7fd-113">Questo articolo consente di valutare l'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="3c7fd-114">Viene illustrato come abilitare la modalità di controllo in modo da poter testare la funzionalità direttamente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="3c7fd-115">Puoi anche visitare il sito Web dello scenario demo di Microsoft Defender per Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="3c7fd-116">Usare la modalità di controllo per misurare l'impatto</span><span class="sxs-lookup"><span data-stu-id="3c7fd-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="3c7fd-117">Abilita l'accesso controllato alle cartelle in  modalità di controllo per visualizzare un record di ciò che sarebbe successo se fosse stata completamente abilitata.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="3c7fd-118">Testare il funzionamento della funzionalità nell'organizzazione per assicurarsi che non influisca sulle app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="3c7fd-119">Puoi anche avere un'idea del numero di tentativi di modifica dei file sospetti in genere eseguiti in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="3c7fd-120">Per abilitare la modalità di controllo, utilizzare il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="3c7fd-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="3c7fd-121">Se si desidera controllare completamente il funzionamento dell'accesso controllato alle cartelle nell'organizzazione, è necessario utilizzare uno strumento di gestione per distribuire questa impostazione nei dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="3c7fd-122">Puoi anche usare Criteri di gruppo, Intune, gestione dei dispositivi mobili (MDM) o Microsoft Endpoint Manager per configurare e distribuire l'impostazione, come descritto nell'argomento principale accesso controllato [alle cartelle.](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="3c7fd-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="3c7fd-123">Esaminare gli eventi di accesso controllato alle cartelle nel Visualizzatore eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="3c7fd-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="3c7fd-124">I seguenti eventi di accesso controllato alle cartelle vengono visualizzati nel Visualizzatore eventi di Windows nella cartella Microsoft/Windows/Windows Defender/Operational.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="3c7fd-125">ID evento</span><span class="sxs-lookup"><span data-stu-id="3c7fd-125">Event ID</span></span> | <span data-ttu-id="3c7fd-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c7fd-126">Description</span></span>
-|-
 <span data-ttu-id="3c7fd-127">5007</span><span class="sxs-lookup"><span data-stu-id="3c7fd-127">5007</span></span> | <span data-ttu-id="3c7fd-128">Evento quando vengono modificate le impostazioni</span><span class="sxs-lookup"><span data-stu-id="3c7fd-128">Event when settings are changed</span></span>
 <span data-ttu-id="3c7fd-129">1124</span><span class="sxs-lookup"><span data-stu-id="3c7fd-129">1124</span></span> | <span data-ttu-id="3c7fd-130">Evento di accesso controllato alle cartelle controllato</span><span class="sxs-lookup"><span data-stu-id="3c7fd-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="3c7fd-131">1123</span><span class="sxs-lookup"><span data-stu-id="3c7fd-131">1123</span></span> | <span data-ttu-id="3c7fd-132">Evento di accesso controllato alla cartella bloccato</span><span class="sxs-lookup"><span data-stu-id="3c7fd-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="3c7fd-133">È possibile configurare una sottoscrizione di [Inoltro eventi di Windows per](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) raccogliere i registri in modo centralizzato.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-133">You can configure a [Windows Event Forwarding subscription](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="3c7fd-134">Personalizzare le app e le cartelle protette</span><span class="sxs-lookup"><span data-stu-id="3c7fd-134">Customize protected folders and apps</span></span>

<span data-ttu-id="3c7fd-135">Durante la valutazione, potresti voler aggiungere all'elenco delle cartelle protette o consentire a determinate app di modificare i file.</span><span class="sxs-lookup"><span data-stu-id="3c7fd-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="3c7fd-136">Vedi [Proteggere le cartelle importanti con](controlled-folders.md) accesso controllato alle cartelle per configurare la funzionalità con strumenti di gestione, tra cui Criteri di gruppo, PowerShell e provider di servizi di configurazione MDM .</span><span class="sxs-lookup"><span data-stu-id="3c7fd-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c7fd-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c7fd-137">See also</span></span>

* [<span data-ttu-id="3c7fd-138">Proteggere le cartelle importanti con l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="3c7fd-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="3c7fd-139">Valutare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c7fd-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="3c7fd-140">Usare la modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="3c7fd-140">Use audit mode</span></span>](audit-windows-defender.md)
