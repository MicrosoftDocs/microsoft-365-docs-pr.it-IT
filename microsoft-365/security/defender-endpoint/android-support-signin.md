---
title: Risolvere i problemi in Microsoft Defender ATP per Android
description: Risolvere i problemi relativi a Microsoft Defender ATP per Android
keywords: microsoft, defender, atp, android, cloud, connettività, comunicazione
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 444541c85f8f4416288dcebf4bbee2c65a33d3d2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164870"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="4d2db-104">Risoluzione dei problemi in Microsoft Defender per Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="4d2db-104">Troubleshooting issues on Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4d2db-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-105">**Applies to:**</span></span>
- [<span data-ttu-id="4d2db-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4d2db-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d2db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d2db-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4d2db-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4d2db-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d2db-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4d2db-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="4d2db-110">Quando si esegue l'onboarding di un dispositivo, potrebbero verificarsi problemi di accesso dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="4d2db-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="4d2db-111">Durante l'onboarding, potresti riscontrare problemi di accesso dopo l'installazione dell'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d2db-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="4d2db-112">In questo articolo vengono fornite soluzioni per risolvere i problemi di accesso.</span><span class="sxs-lookup"><span data-stu-id="4d2db-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="4d2db-113">Accesso non riuscito - Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="4d2db-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="4d2db-114">**Accesso non riuscito: errore** *imprevisto, riprovare in un secondo momento*</span><span class="sxs-lookup"><span data-stu-id="4d2db-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Immagine dell'errore di accesso non riuscito Errore imprevisto](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="4d2db-116">**Messaggio:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-116">**Message:**</span></span>

<span data-ttu-id="4d2db-117">Errore imprevisto, riprovare in un secondo momento</span><span class="sxs-lookup"><span data-stu-id="4d2db-117">Unexpected error, try later</span></span>

<span data-ttu-id="4d2db-118">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-118">**Cause:**</span></span>

<span data-ttu-id="4d2db-119">Nel dispositivo è installata una versione precedente dell'app "Microsoft Authenticator".</span><span class="sxs-lookup"><span data-stu-id="4d2db-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="4d2db-120">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-120">**Solution:**</span></span>

<span data-ttu-id="4d2db-121">Installare la versione più recente e [di Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) da Google Play Store e riprovare</span><span class="sxs-lookup"><span data-stu-id="4d2db-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="4d2db-122">Accesso non riuscito - Licenza non valida</span><span class="sxs-lookup"><span data-stu-id="4d2db-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="4d2db-123">**Accesso non riuscito: licenza** *non valida, contattare l'amministratore*</span><span class="sxs-lookup"><span data-stu-id="4d2db-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Immagine dell'accesso non riuscita contattare l'amministratore](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="4d2db-125">**Messaggio: Licenza** *non valida, contattare l'amministratore*</span><span class="sxs-lookup"><span data-stu-id="4d2db-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="4d2db-126">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-126">**Cause:**</span></span>

<span data-ttu-id="4d2db-127">Non si dispone di una licenza di Microsoft 365 assegnata o l'organizzazione non dispone di una licenza per l'abbonamento a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4d2db-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="4d2db-128">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-128">**Solution:**</span></span>

<span data-ttu-id="4d2db-129">Contattare l'amministratore per assistenza.</span><span class="sxs-lookup"><span data-stu-id="4d2db-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="4d2db-130">Le pagine di phishing non vengono bloccate in alcuni dispositivi OEM</span><span class="sxs-lookup"><span data-stu-id="4d2db-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="4d2db-131">**Si applica a:** Solo OEM specifici</span><span class="sxs-lookup"><span data-stu-id="4d2db-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="4d2db-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="4d2db-132">**Xiaomi**</span></span>

<span data-ttu-id="4d2db-133">Phishing e minacce Web dannose rilevate da Defender per Endpoint per Android non sono bloccate in alcuni dispositivi Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="4d2db-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="4d2db-134">La funzionalità seguente non funziona su questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4d2db-134">The following functionality doesn't work on these devices.</span></span>

![Immagine del sito segnalato non sicuro](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="4d2db-136">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-136">**Cause:**</span></span>

<span data-ttu-id="4d2db-137">I dispositivi Xiaomi includono un nuovo modello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d2db-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="4d2db-138">Ciò impedisce a Defender per Endpoint per Android di visualizzare le finestre popup mentre viene eseguito in background.</span><span class="sxs-lookup"><span data-stu-id="4d2db-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="4d2db-139">Autorizzazione per i dispositivi Xiaomi: "Visualizza le finestre popup durante l'esecuzione in background".</span><span class="sxs-lookup"><span data-stu-id="4d2db-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Immagine dell'impostazione popup](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="4d2db-141">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="4d2db-141">**Solution:**</span></span>

<span data-ttu-id="4d2db-142">Abilita l'autorizzazione necessaria nei dispositivi Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="4d2db-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="4d2db-143">Visualizzare le finestre popup durante l'esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="4d2db-143">Display pop-up windows while running in the background.</span></span>
