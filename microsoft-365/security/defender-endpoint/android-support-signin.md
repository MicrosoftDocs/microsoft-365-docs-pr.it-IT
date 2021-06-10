---
title: Risolvere i problemi relativi a Microsoft Defender per Endpoint su Android
description: Risolvere i problemi di Microsoft Defender per Endpoint su Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, cloud, connettività, comunicazione
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246357"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="ced93-104">Risoluzione dei problemi in Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="ced93-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ced93-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ced93-105">**Applies to:**</span></span>
- [<span data-ttu-id="ced93-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ced93-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ced93-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ced93-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ced93-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ced93-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ced93-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ced93-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="ced93-110">Quando si esegue l'onboarding di un dispositivo, potrebbero verificarsi problemi di accesso dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="ced93-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="ced93-111">Durante l'onboarding, potresti riscontrare problemi di accesso dopo l'installazione dell'app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ced93-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="ced93-112">In questo articolo vengono fornite soluzioni per risolvere i problemi di accesso.</span><span class="sxs-lookup"><span data-stu-id="ced93-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="ced93-113">Accesso non riuscito - Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="ced93-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="ced93-114">**Accesso non riuscito: errore** *imprevisto, riprovare in un secondo momento*</span><span class="sxs-lookup"><span data-stu-id="ced93-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Immagine dell'errore di accesso non riuscito Errore imprevisto](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="ced93-116">**Messaggio:**</span><span class="sxs-lookup"><span data-stu-id="ced93-116">**Message:**</span></span>

<span data-ttu-id="ced93-117">Errore imprevisto, riprovare in un secondo momento</span><span class="sxs-lookup"><span data-stu-id="ced93-117">Unexpected error, try later</span></span>

<span data-ttu-id="ced93-118">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="ced93-118">**Cause:**</span></span>

<span data-ttu-id="ced93-119">Hai una versione precedente dell'app "Microsoft Authenticator" installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ced93-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="ced93-120">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="ced93-120">**Solution:**</span></span>

<span data-ttu-id="ced93-121">Installare la versione più recente [e Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) da Google Play Store e riprovare</span><span class="sxs-lookup"><span data-stu-id="ced93-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="ced93-122">Accesso non riuscito - Licenza non valida</span><span class="sxs-lookup"><span data-stu-id="ced93-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="ced93-123">**Accesso non riuscito: licenza** *non valida, contattare l'amministratore*</span><span class="sxs-lookup"><span data-stu-id="ced93-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Immagine dell'accesso non riuscita contattare l'amministratore](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="ced93-125">**Messaggio: Licenza** *non valida, contattare l'amministratore*</span><span class="sxs-lookup"><span data-stu-id="ced93-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="ced93-126">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="ced93-126">**Cause:**</span></span>

<span data-ttu-id="ced93-127">Non è stata assegnata Microsoft 365 licenza oppure l'organizzazione non dispone di una licenza per Microsoft 365 Enterprise abbonamento.</span><span class="sxs-lookup"><span data-stu-id="ced93-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="ced93-128">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="ced93-128">**Solution:**</span></span>

<span data-ttu-id="ced93-129">Contattare l'amministratore per assistenza.</span><span class="sxs-lookup"><span data-stu-id="ced93-129">Contact your administrator for help.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="ced93-130">Segnala sito non sicuro</span><span class="sxs-lookup"><span data-stu-id="ced93-130">Report unsafe site</span></span>

<span data-ttu-id="ced93-131">I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie.</span><span class="sxs-lookup"><span data-stu-id="ced93-131">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="ced93-132">Visitare la [pagina Fornire commenti e](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) suggerimenti sulla protezione di rete se si desidera segnalare un sito Web che potrebbe essere un sito di phishing.</span><span class="sxs-lookup"><span data-stu-id="ced93-132">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="ced93-133">Le pagine di phishing non vengono bloccate in alcuni dispositivi OEM</span><span class="sxs-lookup"><span data-stu-id="ced93-133">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="ced93-134">**Si applica a:** Solo OEM specifici</span><span class="sxs-lookup"><span data-stu-id="ced93-134">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="ced93-135">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="ced93-135">**Xiaomi**</span></span>

<span data-ttu-id="ced93-136">Phishing e minacce Web dannose rilevate da Defender per Endpoint per Android non sono bloccate in alcuni dispositivi Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="ced93-136">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="ced93-137">La funzionalità seguente non funziona su questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ced93-137">The following functionality doesn't work on these devices.</span></span>

![Immagine del sito segnalato non sicuro](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="ced93-139">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="ced93-139">**Cause:**</span></span>

<span data-ttu-id="ced93-140">I dispositivi Xiaomi includono un nuovo modello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="ced93-140">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="ced93-141">Ciò impedisce a Defender per Endpoint per Android di visualizzare le finestre popup mentre viene eseguito in background.</span><span class="sxs-lookup"><span data-stu-id="ced93-141">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="ced93-142">Autorizzazione per i dispositivi Xiaomi: "Visualizza le finestre popup durante l'esecuzione in background".</span><span class="sxs-lookup"><span data-stu-id="ced93-142">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Immagine dell'impostazione popup](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="ced93-144">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="ced93-144">**Solution:**</span></span>

<span data-ttu-id="ced93-145">Abilita l'autorizzazione necessaria nei dispositivi Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="ced93-145">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="ced93-146">Visualizzare le finestre popup durante l'esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="ced93-146">Display pop-up windows while running in the background.</span></span>
