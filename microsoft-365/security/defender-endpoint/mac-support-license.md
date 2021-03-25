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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066429"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="4eb5f-104">Risolvere i problemi di licenza per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="4eb5f-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4eb5f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4eb5f-105">**Applies to:**</span></span>

- [<span data-ttu-id="4eb5f-106">Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="4eb5f-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="4eb5f-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4eb5f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4eb5f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eb5f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4eb5f-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4eb5f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4eb5f-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4eb5f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4eb5f-111">Mentre stai passando a [Microsoft Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md) e al test di distribuzione manuale o a un modello di prova (PoC), potresti ricevere l'errore seguente: [](mac-install-manually.md)</span><span class="sxs-lookup"><span data-stu-id="4eb5f-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Immagine dell'errore di licenza](images/no-license-found.png)

<span data-ttu-id="4eb5f-113">**Messaggio:**</span><span class="sxs-lookup"><span data-stu-id="4eb5f-113">**Message:**</span></span> 

<span data-ttu-id="4eb5f-114">Nessuna licenza trovata</span><span class="sxs-lookup"><span data-stu-id="4eb5f-114">No license found</span></span>

<span data-ttu-id="4eb5f-115">Sembra che l'organizzazione non abbia una licenza per l'abbonamento a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4eb5f-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="4eb5f-116">Contattare l'amministratore per assistenza.</span><span class="sxs-lookup"><span data-stu-id="4eb5f-116">Contact your administrator for help.</span></span>

<span data-ttu-id="4eb5f-117">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="4eb5f-117">**Cause:**</span></span> 

<span data-ttu-id="4eb5f-118">Hai distribuito e/o installato il pacchetto Microsoft Defender for Endpoint per macOS ("Scarica pacchetto di installazione") ma potresti aver eseguito lo script di configurazione ("Scarica pacchetto di onboarding").</span><span class="sxs-lookup"><span data-stu-id="4eb5f-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="4eb5f-119">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="4eb5f-119">**Solution:**</span></span>

<span data-ttu-id="4eb5f-120">Seguire le MicrosoftDefenderATPOnboardingMacOs.py seguenti: Configurazione [client](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="4eb5f-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

