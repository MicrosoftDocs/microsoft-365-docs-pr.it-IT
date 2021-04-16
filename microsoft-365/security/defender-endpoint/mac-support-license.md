---
title: Risolvere i problemi di licenza per Microsoft Defender per Endpoint per Mac
description: Risolvere i problemi relativi alle licenze in Microsoft Defender per Endpoint per Mac.
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
ms.openlocfilehash: 3fb351d9ce8e9beef812e6aaa7d463161a6af8df
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862188"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="22333-104">Risolvere i problemi di licenza per Microsoft Defender per Endpoint in macOS</span><span class="sxs-lookup"><span data-stu-id="22333-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="22333-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="22333-105">**Applies to:**</span></span>

- [<span data-ttu-id="22333-106">Microsoft Defender per endpoint su macOS</span><span class="sxs-lookup"><span data-stu-id="22333-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="22333-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="22333-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22333-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22333-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="22333-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="22333-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22333-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="22333-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="22333-111">Durante l'esecuzione di Microsoft Defender for [](mac-install-manually.md) Endpoint su [macOS](microsoft-defender-endpoint-mac.md) e test di distribuzione manuale o di un modello di prova (PoC), è possibile che venga visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="22333-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Immagine dell'errore di licenza](images/no-license-found.png)

<span data-ttu-id="22333-113&quot;>**Messaggio:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22333-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;22333-114&quot;>Nessuna licenza trovata</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22333-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;22333-115&quot;>Sembra che l'organizzazione non abbia una licenza per l'abbonamento a Microsoft 365 Enterprise.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22333-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;22333-116&quot;>Contattare l'amministratore per assistenza.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22333-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;22333-117&quot;>**Causa:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;22333-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;22333-118&quot;>Hai distribuito e/o installato il pacchetto Microsoft Defender for Endpoint su macOS (&quot;Scarica pacchetto di installazione") ma potresti aver eseguito lo script di configurazione ("Scarica pacchetto di onboarding").</span><span class="sxs-lookup"><span data-stu-id="22333-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="22333-119">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="22333-119">**Solution:**</span></span>

<span data-ttu-id="22333-120">Seguire le MicrosoftDefenderATPOnboardingMacOs.py seguenti: Configurazione [client](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="22333-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

