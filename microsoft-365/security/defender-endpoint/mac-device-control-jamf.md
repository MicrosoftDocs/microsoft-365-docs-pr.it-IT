---
title: Esempi di criteri di controllo dei dispositivi per JAMF
description: Scopri come usare i criteri di controllo dei dispositivi usando esempi che possono essere usati con JAMF.
keywords: microsoft, defender, endpoint, atp, mac, dispositivo, controllo, usb, rimovibile, supporto, jamf
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 8990979024c033d4142b595d6fef94f7b872e7c9
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187682"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="56444-104">Esempi di criteri di controllo dei dispositivi per JAMF</span><span class="sxs-lookup"><span data-stu-id="56444-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56444-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="56444-105">**Applies to:**</span></span>
- [<span data-ttu-id="56444-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="56444-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="56444-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56444-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="56444-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="56444-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="56444-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="56444-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="56444-110">Questo documento contiene esempi di criteri di controllo dei dispositivi che puoi personalizzare per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="56444-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="56444-111">Questi esempi sono applicabili se si usa JAMF per gestire i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="56444-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="56444-112">Limitare l'accesso a tutti i supporti rimovibili</span><span class="sxs-lookup"><span data-stu-id="56444-112">Restrict access to all removable media</span></span>

<span data-ttu-id="56444-113">Nell'esempio seguente viene limitato l'accesso a tutti i supporti rimovibili.</span><span class="sxs-lookup"><span data-stu-id="56444-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="56444-114">Si noti l'autorizzazione applicata al livello superiore del criterio, pertanto tutte le operazioni sui `none` file saranno proibite.</span><span class="sxs-lookup"><span data-stu-id="56444-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="56444-115">Impostare tutti i supporti rimovibili in sola lettura</span><span class="sxs-lookup"><span data-stu-id="56444-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="56444-116">Nell'esempio seguente tutti i supporti rimovibili vengono configurati in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="56444-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="56444-117">Si noti l'autorizzazione applicata al livello superiore del criterio, il che significa che tutte le operazioni di scrittura ed esecuzione `read` non saranno consentite.</span><span class="sxs-lookup"><span data-stu-id="56444-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="56444-118">Non consentire l'esecuzione del programma da supporti rimovibili</span><span class="sxs-lookup"><span data-stu-id="56444-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="56444-119">Nell'esempio seguente viene illustrato come non è consentita l'esecuzione del programma da supporti rimovibili.</span><span class="sxs-lookup"><span data-stu-id="56444-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="56444-120">Prendere nota `read` delle autorizzazioni e applicate al livello superiore del `write` criterio.</span><span class="sxs-lookup"><span data-stu-id="56444-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="56444-121">Limitare tutti i dispositivi di fornitori specifici</span><span class="sxs-lookup"><span data-stu-id="56444-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="56444-122">L'esempio seguente limita tutti i dispositivi di fornitori specifici (in questo caso identificati da `fff0` e `4525` ).</span><span class="sxs-lookup"><span data-stu-id="56444-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="56444-123">Tutti gli altri dispositivi saranno senza restrizioni, poiché l'autorizzazione definita al livello superiore del criterio elenca tutte le autorizzazioni possibili (lettura, scrittura ed esecuzione).</span><span class="sxs-lookup"><span data-stu-id="56444-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="56444-124">Limitare dispositivi specifici identificati dall'ID fornitore, dall'ID prodotto e dal numero di serie</span><span class="sxs-lookup"><span data-stu-id="56444-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="56444-125">Nell'esempio seguente vengono restrizioni due dispositivi specifici, identificati dall'ID `fff0` fornitore, dall'ID prodotto `1000` e dai numeri di serie e `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` .</span><span class="sxs-lookup"><span data-stu-id="56444-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="56444-126">In tutti gli altri livelli del criterio le autorizzazioni includono tutti i valori possibili (lettura, scrittura ed esecuzione), ovvero tutti gli altri dispositivi saranno senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="56444-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="56444-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="56444-127">Related topics</span></span>

- [<span data-ttu-id="56444-128">Panoramica del controllo del dispositivo per macOS</span><span class="sxs-lookup"><span data-stu-id="56444-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
