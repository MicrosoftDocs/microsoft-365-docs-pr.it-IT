---
title: Anteprima e test Windows 11 con Microsoft Managed Desktop
description: Come ottenere Windows 11 nell'ambiente
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8dee18909d82656bcfb3e63fdc078328c678e660
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461388"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a><span data-ttu-id="a410f-104">Anteprima e test Windows 11 con Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a410f-104">Preview and test Windows 11 with Microsoft Managed Desktop</span></span>

 <span data-ttu-id="a410f-105">Come registrare e partecipare al programma di test di compatibilità Windows 11 nell'ambiente Microsoft Managed Desktop 11.</span><span class="sxs-lookup"><span data-stu-id="a410f-105">How to enroll and participate in the Windows 11 compatibility testing program within your Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="a410f-106">Per ulteriori informazioni su Windows 11 e Microsoft Managed Desktop in generale, vedere [Windows 11 e Microsoft Managed Desktop](../intro/win11-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a410f-106">For more about Windows 11 and Microsoft Managed Desktop generally, see [Windows 11 and Microsoft Managed Desktop](../intro/win11-overview.md).</span></span> 

## <a name="check-device-eligibility"></a><span data-ttu-id="a410f-107">Verificare l'idoneità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a410f-107">Check device eligibility</span></span>

<span data-ttu-id="a410f-108">Ad oggi, più del 95% dei Microsoft Managed Desktop soddisfa i criteri di idoneità per [Windows 11](/windows/whats-new/windows-11-requirements).</span><span class="sxs-lookup"><span data-stu-id="a410f-108">To date, more than 95% of Microsoft Managed Desktop devices meet [eligibility criteria for Windows 11](/windows/whats-new/windows-11-requirements).</span></span> <span data-ttu-id="a410f-109">Puoi richiedere dettagli sullo stato di idoneità dei dispositivi da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a410f-109">You can request details about the eligibility status of your devices from Microsoft Managed Desktop.</span></span> <span data-ttu-id="a410f-110">Per descrizione della richiesta, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="a410f-110">To file the request, follow these steps:</span></span>

1. <span data-ttu-id="a410f-111">Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering.</span><span class="sxs-lookup"><span data-stu-id="a410f-111">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span> <span data-ttu-id="a410f-112">Se hai bisogno di altre info su come determinare la richiesta, vedi [Supporto per gli amministratori.](admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="a410f-112">If you need more info on how to file the request, see [Admin support](admin-support.md).</span></span>
2. <span data-ttu-id="a410f-113">Utilizzare questi valori per i campi:</span><span class="sxs-lookup"><span data-stu-id="a410f-113">Use these values for the fields:</span></span>
    - <span data-ttu-id="a410f-114">Title: Windows 11 device eligibility</span><span class="sxs-lookup"><span data-stu-id="a410f-114">Title: Windows 11 device eligibility</span></span>
    - <span data-ttu-id="a410f-115">Tipo di richiesta: Richiesta di informazioni</span><span class="sxs-lookup"><span data-stu-id="a410f-115">Request type: Request for information</span></span>
    - <span data-ttu-id="a410f-116">Categoria: Dispositivi</span><span class="sxs-lookup"><span data-stu-id="a410f-116">Category: Devices</span></span>
    - <span data-ttu-id="a410f-117">Sottocategoria: Altro</span><span class="sxs-lookup"><span data-stu-id="a410f-117">Subcategory: Other</span></span>


## <a name="add-devices-to-the-windows-11-test-group"></a><span data-ttu-id="a410f-118">Aggiungere dispositivi al gruppo di test Windows 11</span><span class="sxs-lookup"><span data-stu-id="a410f-118">Add devices to the Windows 11 test group</span></span>

<span data-ttu-id="a410f-119">Inizia aggiungendo dispositivi al gruppo di dispositivi (**\[ Modern Workplace Windows \] 11 Pre-Release Test Devices**) creato per il test e la valutazione Windows 11.</span><span class="sxs-lookup"><span data-stu-id="a410f-119">Start by adding devices to the device group (**\[Modern Workplace\] Windows 11 Pre-Release Test Devices**) created for testing and evaluating Windows 11.</span></span> <span data-ttu-id="a410f-120">I dispositivi in questo gruppo ottengono nuove Windows 11 build e Microsoft Managed Desktop di base non appena diventano disponibili e vengono monitorati per i problemi di affidabilità.</span><span class="sxs-lookup"><span data-stu-id="a410f-120">Devices in this group get new Windows 11 builds and Microsoft Managed Desktop baseline configurations as they become available and are monitored for reliability issues.</span></span>

<span data-ttu-id="a410f-121">Puoi scegliere uno dei dispositivi esistenti o nuovi per i test di Windows 11, ma non registrare i dispositivi di produzione in questo gruppo a causa del rischio elevato di difetti o problemi di compatibilità nelle build non definitiva.</span><span class="sxs-lookup"><span data-stu-id="a410f-121">You can choose any of your existing or new devices for Windows 11 testing, but you shouldn't enroll production devices in this group due to the elevated risk of defects or compatibility issues in pre-release builds.</span></span> <span data-ttu-id="a410f-122">Le assegnazioni precedenti del gruppo di dispositivi vengono rimosse dopo l'assegnazione a questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="a410f-122">Prior device group assignments are removed upon assignment to this group.</span></span>

<span data-ttu-id="a410f-123">Per registrare i dispositivi nel gruppo di test non definitiva:</span><span class="sxs-lookup"><span data-stu-id="a410f-123">To enroll your devices in the pre-release test group:</span></span>

1. <span data-ttu-id="a410f-124">Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering.</span><span class="sxs-lookup"><span data-stu-id="a410f-124">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span>
2. <span data-ttu-id="a410f-125">Utilizzare questi valori per i campi:</span><span class="sxs-lookup"><span data-stu-id="a410f-125">Use these values for the fields:</span></span>
    - <span data-ttu-id="a410f-126">Title: Windows 11 compatibility enrollment</span><span class="sxs-lookup"><span data-stu-id="a410f-126">Title: Windows 11 compatibility enrollment</span></span>
    - <span data-ttu-id="a410f-127">Tipo di richiesta: Richiesta di modifica</span><span class="sxs-lookup"><span data-stu-id="a410f-127">Request type: Change request</span></span>
    - <span data-ttu-id="a410f-128">Categoria: Dispositivi</span><span class="sxs-lookup"><span data-stu-id="a410f-128">Category: Devices</span></span>
    - <span data-ttu-id="a410f-129">Sottocategoria: Assegnazione gruppo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="a410f-129">Subcategory: Deployment group assignment</span></span>
3. <span data-ttu-id="a410f-130">Nel campo description elencare i numeri di serie dei dispositivi che si desidera utilizzare per Windows 11 test.</span><span class="sxs-lookup"><span data-stu-id="a410f-130">In the description field, list the serial numbers of the devices that you want to use for Windows 11 testing.</span></span> <span data-ttu-id="a410f-131">Nota che, se presente, dei dispositivi specificati non sono ancora distribuiti nel tenant Microsoft Managed Desktop tenant.</span><span class="sxs-lookup"><span data-stu-id="a410f-131">Note which, if any, of the specified devices aren't yet deployed in your Microsoft Managed Desktop tenant.</span></span>

## <a name="prioritize-applications-to-submit-to-test-base"></a><span data-ttu-id="a410f-132">Assegnare priorità alle applicazioni da inviare a Test Base</span><span class="sxs-lookup"><span data-stu-id="a410f-132">Prioritize applications to submit to Test Base</span></span>

<span data-ttu-id="a410f-133">Le applicazioni business-critical sono i candidati migliori per una maggiore convalida in un ambiente Windows 11.</span><span class="sxs-lookup"><span data-stu-id="a410f-133">Business-critical applications are the best candidates for more validation in a closed Windows 11 environment.</span></span> <span data-ttu-id="a410f-134">Possiamo aiutarti a definire la priorità delle app per Windows 11 test in base ai dati di utilizzo e affidabilità.</span><span class="sxs-lookup"><span data-stu-id="a410f-134">We can help you prioritize apps for Windows 11 testing based on usage and reliability data.</span></span> <span data-ttu-id="a410f-135">Per richiedere i suggerimenti, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="a410f-135">To request our recommendations, follow these steps:</span></span>

1. <span data-ttu-id="a410f-136">Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering.</span><span class="sxs-lookup"><span data-stu-id="a410f-136">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span> <span data-ttu-id="a410f-137">Se hai bisogno di altre info su come determinare la richiesta, vedi [Supporto per gli amministratori.](admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="a410f-137">If you need more info on how to file the request, see [Admin support](admin-support.md).</span></span>
2. <span data-ttu-id="a410f-138">Utilizzare questi valori per i campi:</span><span class="sxs-lookup"><span data-stu-id="a410f-138">Use these values for the fields:</span></span>
    - <span data-ttu-id="a410f-139">Title: Windows 11 Test Base candidates</span><span class="sxs-lookup"><span data-stu-id="a410f-139">Title: Windows 11 Test Base candidates</span></span>
    - <span data-ttu-id="a410f-140">Tipo di richiesta: Richiesta di informazioni</span><span class="sxs-lookup"><span data-stu-id="a410f-140">Request type: Request for information</span></span>
    - <span data-ttu-id="a410f-141">Categoria: App</span><span class="sxs-lookup"><span data-stu-id="a410f-141">Category: Apps</span></span>
    - <span data-ttu-id="a410f-142">Sottocategoria: Altro</span><span class="sxs-lookup"><span data-stu-id="a410f-142">Subcategory: Other</span></span>

## <a name="report-issues"></a><span data-ttu-id="a410f-143">Segnalare i problemi</span><span class="sxs-lookup"><span data-stu-id="a410f-143">Report issues</span></span>

<span data-ttu-id="a410f-144">Se si verificano Windows 11 problemi di compatibilità con le app line-of-business o Microsoft 365, segnalarle a Microsoft per indagini e correzioni.</span><span class="sxs-lookup"><span data-stu-id="a410f-144">If you encounter Windows 11 compatibility issues with your line-of-business or Microsoft 365 apps, report them to us for investigation and remediation.</span></span> <span data-ttu-id="a410f-145">Per segnalare un problema, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="a410f-145">To report an issue, follow these steps:</span></span>

1. <span data-ttu-id="a410f-146">Aprire una nuova richiesta di servizio con il team Microsoft Managed Desktop Service Engineering.</span><span class="sxs-lookup"><span data-stu-id="a410f-146">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span>
2. <span data-ttu-id="a410f-147">Utilizzare questi valori per i campi:</span><span class="sxs-lookup"><span data-stu-id="a410f-147">Use these values for the fields:</span></span>
    - <span data-ttu-id="a410f-148">Titolo: Windows 11 test di compatibilità</span><span class="sxs-lookup"><span data-stu-id="a410f-148">Title: Windows 11 compatibility testing</span></span>
    - <span data-ttu-id="a410f-149">Tipo di richiesta: Evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="a410f-149">Request type: Incident</span></span>
    - <span data-ttu-id="a410f-150">Categoria: Dispositivi</span><span class="sxs-lookup"><span data-stu-id="a410f-150">Category: Devices</span></span>
    - <span data-ttu-id="a410f-151">Sottocategoria: Windows Upgrade/Update</span><span class="sxs-lookup"><span data-stu-id="a410f-151">Subcategory: Windows Upgrade/Update</span></span>
3. <span data-ttu-id="a410f-152">Descrivere il comportamento e il livello di intralcio dell'azienda in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="a410f-152">Describe the behavior and how severely it would hinder your business in a production environment.</span></span>

<span data-ttu-id="a410f-153">Microsoft Managed Desktop e gestisce i problemi relativi alle build non definitiva in base all'effetto sulla produttività.</span><span class="sxs-lookup"><span data-stu-id="a410f-153">Microsoft Managed Desktop triages and handles issues with pre-release builds based on the effect on productivity.</span></span> <span data-ttu-id="a410f-154">Sebbene la descrizione del servizio non riguardi i problemi relativi alle build non definitiva, microsoft conferirà agli amministratori dei clienti la risoluzione dei problemi che bloccano la produttività degli utenti prima di avviare la migrazione all'interno di un determinato tenant.</span><span class="sxs-lookup"><span data-stu-id="a410f-154">While our service description doesn't cover issues with pre-release builds, we'll confer with customer admins to ensure that issues that block user productivity are resolved prior to starting migration within any given tenant.</span></span>
