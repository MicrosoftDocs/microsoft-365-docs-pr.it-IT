---
title: Risolvere i problemi di licenza per Microsoft Defender ATP per Mac
description: Risolvere i problemi relativi alle licenze in Microsoft Defender ATP per Mac.
keywords: microsoft, defender, atp, mac, prestazioni
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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689114"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="ed1eb-104">Risolvere i problemi di licenza per Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="ed1eb-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ed1eb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ed1eb-105">**Applies to:**</span></span>

- [<span data-ttu-id="ed1eb-106">Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="ed1eb-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="ed1eb-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ed1eb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ed1eb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed1eb-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ed1eb-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ed1eb-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ed1eb-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ed1eb-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ed1eb-111">Durante l'esecuzione di Microsoft Defender for [](mac-install-manually.md) Endpoint su [macOS](microsoft-defender-endpoint-mac.md) e test di distribuzione manuale o di un modello di prova (PoC), è possibile che venga visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="ed1eb-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Immagine dell'errore di licenza](images/no-license-found.png)

<span data-ttu-id="ed1eb-113&quot;>**Messaggio:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ed1eb-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;ed1eb-114&quot;>Nessuna licenza trovata</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ed1eb-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;ed1eb-115&quot;>Sembra che l'organizzazione non abbia una licenza per l'abbonamento a Microsoft 365 Enterprise.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ed1eb-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;ed1eb-116&quot;>Contattare l'amministratore per assistenza.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ed1eb-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;ed1eb-117&quot;>**Causa:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ed1eb-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;ed1eb-118&quot;>Hai distribuito e/o installato il pacchetto Microsoft Defender for Endpoint su macOS (&quot;Scarica pacchetto di installazione") ma potresti aver eseguito lo script di configurazione ("Scarica pacchetto di onboarding").</span><span class="sxs-lookup"><span data-stu-id="ed1eb-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="ed1eb-119">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="ed1eb-119">**Solution:**</span></span>

<span data-ttu-id="ed1eb-120">Seguire le MicrosoftDefenderATPOnboardingMacOs.py seguenti: Configurazione [client](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="ed1eb-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

