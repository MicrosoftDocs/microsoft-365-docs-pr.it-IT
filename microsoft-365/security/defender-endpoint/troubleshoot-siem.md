---
title: Risolvere i problemi di integrazione degli strumenti SIEM in Microsoft Defender for Endpoint
description: Risolvere i problemi che possono verificarsi quando si usano gli strumenti SIEM con Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, siem, segreto client, segreto
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
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 60220d00ca1b612564b72103b9206e3d6d89dc60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689450"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="82c6c-104">Risolvere i problemi di integrazione degli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="82c6c-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82c6c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="82c6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="82c6c-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="82c6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82c6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82c6c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="82c6c-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="82c6c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82c6c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="82c6c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="82c6c-110">Potrebbe essere necessario risolvere i problemi durante il pull dei rilevamenti negli strumenti SIEM.</span><span class="sxs-lookup"><span data-stu-id="82c6c-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="82c6c-111">In questa pagina vengono descritti i passaggi dettagliati per la risoluzione dei problemi che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="82c6c-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="82c6c-112">Informazioni su come ottenere un nuovo segreto client</span><span class="sxs-lookup"><span data-stu-id="82c6c-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="82c6c-113">Se il segreto client scade o se la copia fornita durante l'abilitazione dell'applicazione dello strumento SIEM è stata smarrita, sarà necessario ottenere un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="82c6c-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="82c6c-114">Accedere al [portale di gestione di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="82c6c-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="82c6c-115">Selezionare **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="82c6c-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="82c6c-116">Selezionare il tenant.</span><span class="sxs-lookup"><span data-stu-id="82c6c-116">Select your tenant.</span></span>

4. <span data-ttu-id="82c6c-117">Fare **clic su Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="82c6c-117">Click **App registrations**.</span></span> <span data-ttu-id="82c6c-118">Selezionare quindi l'applicazione nell'elenco delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="82c6c-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="82c6c-119">Seleziona **la sezione** Chiavi, quindi fornisci una descrizione chiave e specifica la durata della validità della chiave.</span><span class="sxs-lookup"><span data-stu-id="82c6c-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="82c6c-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="82c6c-120">Click **Save**.</span></span> <span data-ttu-id="82c6c-121">Viene visualizzato il valore della chiave.</span><span class="sxs-lookup"><span data-stu-id="82c6c-121">The key value is displayed.</span></span>

7. <span data-ttu-id="82c6c-122">Copiare il valore e salvarlo in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="82c6c-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="82c6c-123">Errore durante il recupero di un token di accesso di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="82c6c-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="82c6c-124">Se si verifica un errore durante il tentativo di ottenere un token di aggiornamento quando si usano l'API di threat intelligence o gli strumenti SIEM, è necessario aggiungere l'URL di risposta per l'applicazione pertinente in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82c6c-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="82c6c-125">Accedere al [portale di gestione di Azure](https://ms.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="82c6c-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="82c6c-126">Selezionare **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="82c6c-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="82c6c-127">Selezionare il tenant.</span><span class="sxs-lookup"><span data-stu-id="82c6c-127">Select your tenant.</span></span>

4. <span data-ttu-id="82c6c-128">Fai **clic su Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="82c6c-128">Click **App Registrations**.</span></span> <span data-ttu-id="82c6c-129">Selezionare quindi l'applicazione nell'elenco delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="82c6c-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="82c6c-130">Aggiungere l'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="82c6c-130">Add the following URL:</span></span>
   - <span data-ttu-id="82c6c-131">Per l'Unione europea: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="82c6c-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="82c6c-132">Per il Regno Unito: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="82c6c-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="82c6c-133">Per gli Stati Uniti:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="82c6c-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="82c6c-134">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="82c6c-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="82c6c-135">Errore durante l'abilitazione dell'applicazione connettore SIEM</span><span class="sxs-lookup"><span data-stu-id="82c6c-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="82c6c-136">Se si verifica un errore durante il tentativo di abilitare l'applicazione connettore SIEM, controllare le impostazioni di blocco popup del browser.</span><span class="sxs-lookup"><span data-stu-id="82c6c-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="82c6c-137">È possibile che la nuova finestra venga aperta quando si abilita la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="82c6c-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="82c6c-138">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="82c6c-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82c6c-139">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="82c6c-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="82c6c-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="82c6c-140">Related topics</span></span>
- [<span data-ttu-id="82c6c-141">Abilitare l'integrazione SIEM in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="82c6c-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="82c6c-142">Configurare ArcSight per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c6c-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="82c6c-143">Eseguire il pull dei rilevamenti agli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="82c6c-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="82c6c-144">Campi di Microsoft Defender per il rilevamento degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c6c-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="82c6c-145">Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST</span><span class="sxs-lookup"><span data-stu-id="82c6c-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
