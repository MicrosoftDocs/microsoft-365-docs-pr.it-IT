---
title: Valutare l’accesso controllato alle cartelle
description: Scopri in che modo l'accesso controllato alle cartelle consente di proteggere i file dalle modifiche da parte di app dannose.
keywords: Protezione degli exploit, Windows 10, windows defender, ransomware, proteggere, valutare, testare, demo, provare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15ea4696052a6c987314e3c7b0dd282a49ed4df8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842915"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="cddc6-104">Valutare l’accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="cddc6-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cddc6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cddc6-105">**Applies to:**</span></span>
- [<span data-ttu-id="cddc6-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="cddc6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cddc6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cddc6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cddc6-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cddc6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cddc6-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="cddc6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="cddc6-110">[L'accesso controllato](controlled-folders.md) alle cartelle è una funzionalità che consente di proteggere i documenti e i file da modifiche da app sospette o dannose.</span><span class="sxs-lookup"><span data-stu-id="cddc6-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="cddc6-111">L'accesso controllato alle cartelle è supportato Windows Server 2019 e Windows 10 client.</span><span class="sxs-lookup"><span data-stu-id="cddc6-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="cddc6-112">È particolarmente utile per proteggere da [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) che tenta di crittografare i file e tenerli in ostaggio.</span><span class="sxs-lookup"><span data-stu-id="cddc6-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="cddc6-113">Questo articolo consente di valutare l'accesso controllato alle cartelle.</span><span class="sxs-lookup"><span data-stu-id="cddc6-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="cddc6-114">Viene illustrato come abilitare la modalità di controllo in modo da poter testare la funzionalità direttamente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cddc6-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="cddc6-115">Puoi anche visitare il sito Web dello scenario demo di Microsoft Defender per Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.</span><span class="sxs-lookup"><span data-stu-id="cddc6-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="cddc6-116">Usare la modalità di controllo per misurare l'impatto</span><span class="sxs-lookup"><span data-stu-id="cddc6-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="cddc6-117">Abilita l'accesso controllato alle cartelle in  modalità di controllo per visualizzare un record di ciò che sarebbe successo se fosse stata completamente abilitata.</span><span class="sxs-lookup"><span data-stu-id="cddc6-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="cddc6-118">Testare il funzionamento della funzionalità nell'organizzazione per assicurarsi che non influisca sulle app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="cddc6-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="cddc6-119">Puoi anche avere un'idea del numero di tentativi di modifica dei file sospetti in genere eseguiti in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="cddc6-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="cddc6-120">Per abilitare la modalità di controllo, utilizzare il cmdlet PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="cddc6-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="cddc6-121">Se si desidera controllare completamente il funzionamento dell'accesso controllato alle cartelle nell'organizzazione, è necessario utilizzare uno strumento di gestione per distribuire questa impostazione nei dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="cddc6-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="cddc6-122">Puoi anche usare Criteri di gruppo, Intune, gestione dei dispositivi mobili (MDM) o Microsoft Endpoint Manager per configurare e distribuire l'impostazione, come descritto nell'argomento principale accesso controllato [alle cartelle.](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="cddc6-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="cddc6-123">Esaminare gli eventi di accesso controllato alle cartelle nel Visualizzatore Windows eventi</span><span class="sxs-lookup"><span data-stu-id="cddc6-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="cddc6-124">I seguenti eventi di accesso controllato alle cartelle vengono visualizzati Windows visualizzatore eventi in Microsoft/Windows/Windows Defender/Operational.</span><span class="sxs-lookup"><span data-stu-id="cddc6-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="cddc6-125">ID evento</span><span class="sxs-lookup"><span data-stu-id="cddc6-125">Event ID</span></span> | <span data-ttu-id="cddc6-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cddc6-126">Description</span></span>
-|-
 <span data-ttu-id="cddc6-127">5007</span><span class="sxs-lookup"><span data-stu-id="cddc6-127">5007</span></span> | <span data-ttu-id="cddc6-128">Evento quando vengono modificate le impostazioni</span><span class="sxs-lookup"><span data-stu-id="cddc6-128">Event when settings are changed</span></span>
 <span data-ttu-id="cddc6-129">1124</span><span class="sxs-lookup"><span data-stu-id="cddc6-129">1124</span></span> | <span data-ttu-id="cddc6-130">Evento di accesso controllato alle cartelle controllato</span><span class="sxs-lookup"><span data-stu-id="cddc6-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="cddc6-131">1123</span><span class="sxs-lookup"><span data-stu-id="cddc6-131">1123</span></span> | <span data-ttu-id="cddc6-132">Evento di accesso controllato alla cartella bloccato</span><span class="sxs-lookup"><span data-stu-id="cddc6-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="cddc6-133">È possibile configurare una sottoscrizione [Windows inoltro eventi per](/windows/win32/wec/setting-up-a-source-initiated-subscription) raccogliere i registri in modo centralizzato.</span><span class="sxs-lookup"><span data-stu-id="cddc6-133">You can configure a [Windows Event Forwarding subscription](/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="cddc6-134">Personalizzare le app e le cartelle protette</span><span class="sxs-lookup"><span data-stu-id="cddc6-134">Customize protected folders and apps</span></span>

<span data-ttu-id="cddc6-135">Durante la valutazione, potresti voler aggiungere all'elenco delle cartelle protette o consentire a determinate app di modificare i file.</span><span class="sxs-lookup"><span data-stu-id="cddc6-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="cddc6-136">Vedi [Proteggere le cartelle importanti con](controlled-folders.md) accesso controllato alle cartelle per configurare la funzionalità con strumenti di gestione, tra cui Criteri di gruppo, PowerShell e provider di servizi di configurazione MDM .</span><span class="sxs-lookup"><span data-stu-id="cddc6-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="cddc6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cddc6-137">See also</span></span>

* [<span data-ttu-id="cddc6-138">Proteggere le cartelle importanti con l'accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="cddc6-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="cddc6-139">Valutare Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="cddc6-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="cddc6-140">Usare la modalità di controllo</span><span class="sxs-lookup"><span data-stu-id="cddc6-140">Use audit mode</span></span>](audit-windows-defender.md)
