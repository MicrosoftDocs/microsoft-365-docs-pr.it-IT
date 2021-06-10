---
title: Localizzare l'esperienza utente
description: Come localizzare i dispositivi per gli utenti
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023262"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="8e5ba-104">Localizzare l'esperienza utente</span><span class="sxs-lookup"><span data-stu-id="8e5ba-104">Localize the user experience</span></span>

<span data-ttu-id="8e5ba-105">Gli utenti Microsoft Managed Desktop dispositivi possono selezionare la lingua desiderata durante il processo di installazione (l'esperienza predefinita) o successivamente.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="8e5ba-106">Durante l'installazione (l'esperienza "out-of-box")</span><span class="sxs-lookup"><span data-stu-id="8e5ba-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="8e5ba-107">Durante il processo di completamento dell'installazione, gli utenti possono selezionare la lingua desiderata.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="8e5ba-108">Questa selezione influisce su questi attributi:</span><span class="sxs-lookup"><span data-stu-id="8e5ba-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="8e5ba-109">Windows 10 delle lingue:</span><span class="sxs-lookup"><span data-stu-id="8e5ba-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="8e5ba-110">Lingua di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8e5ba-110">Display language</span></span>
    - <span data-ttu-id="8e5ba-111">Lingua tastiera</span><span class="sxs-lookup"><span data-stu-id="8e5ba-111">Keyboard language</span></span>
    - <span data-ttu-id="8e5ba-112">Funzionalità correlate alla lingua su richiesta</span><span class="sxs-lookup"><span data-stu-id="8e5ba-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="8e5ba-113">Microsoft 365 Apps per le Enterprise linguistiche:</span><span class="sxs-lookup"><span data-stu-id="8e5ba-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="8e5ba-114">Lingua di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8e5ba-114">Display language</span></span>
    - <span data-ttu-id="8e5ba-115">Strumenti di correzione e creazione</span><span class="sxs-lookup"><span data-stu-id="8e5ba-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="8e5ba-116">Gli utenti possono ottenere funzionalità correlate alla lingua solo su richiesta selezionando la lingua durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="8e5ba-117">Dopo aver completato l'installazione</span><span class="sxs-lookup"><span data-stu-id="8e5ba-117">After completing setup</span></span>

<span data-ttu-id="8e5ba-118">Gli utenti possono selezionare la lingua desiderata per Windows 10 e Microsoft 365 Apps per Enterprise in qualsiasi momento al termine del processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="8e5ba-119">In particolare:</span><span class="sxs-lookup"><span data-stu-id="8e5ba-119">Specifically:</span></span>

- <span data-ttu-id="8e5ba-120">Windows 10 delle lingue:</span><span class="sxs-lookup"><span data-stu-id="8e5ba-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="8e5ba-121">Lingua di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8e5ba-121">Display language</span></span>
    - <span data-ttu-id="8e5ba-122">Lingua tastiera</span><span class="sxs-lookup"><span data-stu-id="8e5ba-122">Keyboard language</span></span>

- <span data-ttu-id="8e5ba-123">Microsoft 365 Apps per le Enterprise linguistiche:</span><span class="sxs-lookup"><span data-stu-id="8e5ba-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="8e5ba-124">Lingua di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="8e5ba-124">Display language</span></span>
    - <span data-ttu-id="8e5ba-125">Strumenti di correzione e creazione</span><span class="sxs-lookup"><span data-stu-id="8e5ba-125">Proofing and authoring tools</span></span>

<span data-ttu-id="8e5ba-126">Per rendere disponibili [le](#supported-languages) lingue supportate per Microsoft 365 Apps per Enterprise per gli utenti, aggiungere gli utenti al gruppo **Office-Language_Packs** moderno.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="8e5ba-127">Le lingue saranno disponibili nella Portale aziendale Intune.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="8e5ba-128">Lingue supportate</span><span class="sxs-lookup"><span data-stu-id="8e5ba-128">Supported languages</span></span>

<span data-ttu-id="8e5ba-129">Per i nuovi dispositivi, il produttore deve fornire immagini del dispositivo che includono le lingue necessarie.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="8e5ba-130">Se l'immagine del produttore include lingue diverse da quelle incluse nell'elenco delle lingue supportate, è ancora supportata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="8e5ba-131">Se si riutilizzano dispositivi esistenti, potrebbe essere necessario collaborare con il rappresentante dell'account Microsoft per ottenere le immagini appropriate.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="8e5ba-132">Per altre informazioni, vedi [Immagini dispositivo.](../service-description/device-images.md)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="8e5ba-133">[L'immagine universale](../service-description/device-images.md#universal-image) fornita da Microsoft Managed Desktop include queste lingue e per Windows 10:</span><span class="sxs-lookup"><span data-stu-id="8e5ba-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="8e5ba-134">Arabo</span><span class="sxs-lookup"><span data-stu-id="8e5ba-134">Arabic</span></span>
- <span data-ttu-id="8e5ba-135">Bulgaro</span><span class="sxs-lookup"><span data-stu-id="8e5ba-135">Bulgarian</span></span>
- <span data-ttu-id="8e5ba-136">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="8e5ba-136">Chinese Simplified</span></span>
- <span data-ttu-id="8e5ba-137">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="8e5ba-137">Chinese Traditional</span></span>
- <span data-ttu-id="8e5ba-138">Croato</span><span class="sxs-lookup"><span data-stu-id="8e5ba-138">Croatian</span></span>
- <span data-ttu-id="8e5ba-139">Ceco</span><span class="sxs-lookup"><span data-stu-id="8e5ba-139">Czech</span></span>
- <span data-ttu-id="8e5ba-140">Danese</span><span class="sxs-lookup"><span data-stu-id="8e5ba-140">Danish</span></span>  
- <span data-ttu-id="8e5ba-141">Olandese</span><span class="sxs-lookup"><span data-stu-id="8e5ba-141">Dutch</span></span>  
- <span data-ttu-id="8e5ba-142">Inglese (US, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="8e5ba-143">Estone</span><span class="sxs-lookup"><span data-stu-id="8e5ba-143">Estonian</span></span>
- <span data-ttu-id="8e5ba-144">Finlandese</span><span class="sxs-lookup"><span data-stu-id="8e5ba-144">Finnish</span></span> 
- <span data-ttu-id="8e5ba-145">Francese (Francia, Canada)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-145">French (France, Canada)</span></span>
- <span data-ttu-id="8e5ba-146">Tedesco</span><span class="sxs-lookup"><span data-stu-id="8e5ba-146">German</span></span>
- <span data-ttu-id="8e5ba-147">Greco</span><span class="sxs-lookup"><span data-stu-id="8e5ba-147">Greek</span></span>
- <span data-ttu-id="8e5ba-148">Ebraico</span><span class="sxs-lookup"><span data-stu-id="8e5ba-148">Hebrew</span></span>
- <span data-ttu-id="8e5ba-149">Ungherese</span><span class="sxs-lookup"><span data-stu-id="8e5ba-149">Hungarian</span></span>
- <span data-ttu-id="8e5ba-150">Indonesiano</span><span class="sxs-lookup"><span data-stu-id="8e5ba-150">Indonesian</span></span>
- <span data-ttu-id="8e5ba-151">Italiano</span><span class="sxs-lookup"><span data-stu-id="8e5ba-151">Italian</span></span>
- <span data-ttu-id="8e5ba-152">Giapponese</span><span class="sxs-lookup"><span data-stu-id="8e5ba-152">Japanese</span></span>
- <span data-ttu-id="8e5ba-153">Coreano</span><span class="sxs-lookup"><span data-stu-id="8e5ba-153">Korean</span></span>
- <span data-ttu-id="8e5ba-154">Lettone</span><span class="sxs-lookup"><span data-stu-id="8e5ba-154">Latvian</span></span>
- <span data-ttu-id="8e5ba-155">Lituano</span><span class="sxs-lookup"><span data-stu-id="8e5ba-155">Lithuanian</span></span>
- <span data-ttu-id="8e5ba-156">Norvegese (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="8e5ba-157">Polacco</span><span class="sxs-lookup"><span data-stu-id="8e5ba-157">Polish</span></span>
- <span data-ttu-id="8e5ba-158">Portoghese (Brasile)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="8e5ba-159">Portoghese (Portogallo)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="8e5ba-160">Rumeno</span><span class="sxs-lookup"><span data-stu-id="8e5ba-160">Romanian</span></span>
- <span data-ttu-id="8e5ba-161">Russo</span><span class="sxs-lookup"><span data-stu-id="8e5ba-161">Russian</span></span> 
- <span data-ttu-id="8e5ba-162">Serbo (alfabeto latino)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="8e5ba-163">Slovacco</span><span class="sxs-lookup"><span data-stu-id="8e5ba-163">Slovak</span></span>
- <span data-ttu-id="8e5ba-164">Sloveno</span><span class="sxs-lookup"><span data-stu-id="8e5ba-164">Slovenian</span></span>
- <span data-ttu-id="8e5ba-165">Spagnolo (Spagna, Messico)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="8e5ba-166">Svedese</span><span class="sxs-lookup"><span data-stu-id="8e5ba-166">Swedish</span></span>
- <span data-ttu-id="8e5ba-167">Tailandese</span><span class="sxs-lookup"><span data-stu-id="8e5ba-167">Thai</span></span>
- <span data-ttu-id="8e5ba-168">Turco</span><span class="sxs-lookup"><span data-stu-id="8e5ba-168">Turkish</span></span>
- <span data-ttu-id="8e5ba-169">Ucraino</span><span class="sxs-lookup"><span data-stu-id="8e5ba-169">Ukrainian</span></span>
- <span data-ttu-id="8e5ba-170">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="8e5ba-170">Vietnamese</span></span>

<span data-ttu-id="8e5ba-171">Microsoft 365 Apps per Enterprise potrebbe supportare un elenco leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="8e5ba-172">Se gli utenti hanno bisogno di una lingua diversa da quella elencata qui, stendiamo una richiesta [di supporto](../working-with-managed-desktop/admin-support.md) tramite il portale [di amministrazione.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="8e5ba-173">Lingue per il supporto e le operazioni</span><span class="sxs-lookup"><span data-stu-id="8e5ba-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="8e5ba-174">Supporto agli utenti</span><span class="sxs-lookup"><span data-stu-id="8e5ba-174">User support</span></span>
<span data-ttu-id="8e5ba-175">Microsoft Managed Desktop il supporto solo in inglese.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="8e5ba-176">Se gli utenti scelgono un'altra lingua nell'app Richiesta supporto, riceveranno supporto dai canali di supporto Microsoft generali, anziché direttamente da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="8e5ba-177">Per ulteriori informazioni, vedere [Ottenere assistenza per gli utenti.](../working-with-managed-desktop/end-user-support.md)</span><span class="sxs-lookup"><span data-stu-id="8e5ba-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="8e5ba-178">Se gli utenti necessitano di supporto in altre lingue, è necessario fornire tale supporto tramite fonti di supporto non Microsoft o dalla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="8e5ba-179">Supporto e operazioni dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="8e5ba-179">Admin support and operations</span></span>
<span data-ttu-id="8e5ba-180">Microsoft Managed Desktop il supporto dell'amministratore solo in inglese.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="8e5ba-181">Sono inclusi il portale di amministrazione e tutte le comunicazioni con Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="8e5ba-182">È consigliabile presupporre che tutte le interazioni e le interfacce correlate all'amministratore siano in inglese, a meno che non venga specificato diversamente.</span><span class="sxs-lookup"><span data-stu-id="8e5ba-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


