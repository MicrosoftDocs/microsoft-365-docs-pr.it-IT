---
title: Servizi di posizione di Windows 10
description: Come impostare i Windows di posizione per i dispositivi
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
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929501"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="0040b-104">Servizi di posizione di Windows 10</span><span class="sxs-lookup"><span data-stu-id="0040b-104">Windows 10 location service</span></span>

<span data-ttu-id="0040b-105">I dispositivi Microsoft Managed Desktop vengono registrati tramite Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0040b-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="0040b-106">Questo processo ci consente di gestirli con Azure Active Directory e Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="0040b-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="0040b-107">Per impostazione predefinita, il servizio Windows 10 posizione è disabilitato quando un dispositivo è attivato per la prima volta, a meno che questa funzionalità non sia abilitata nelle impostazioni privacy durante l'esperienza predefinita.</span><span class="sxs-lookup"><span data-stu-id="0040b-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="0040b-108">Queste impostazioni sono nascoste durante la registrazione autopilot in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0040b-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="0040b-109">Per ulteriori informazioni sulla configurazione di Autopilot, vedere [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="0040b-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="0040b-110">Per questo motivo, Microsoft Managed Desktop dispositivi non possono ottenere la posizione del dispositivo, il che limita le funzionalità di diverse funzionalità Windows, ad esempio i fusi orari.</span><span class="sxs-lookup"><span data-stu-id="0040b-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="0040b-111">Per ulteriori informazioni sul servizio di Windows 10, vedere Windows 10 [servizio di posizione e privacy.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="0040b-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="0040b-112">Non è necessario utilizzare il servizio di posizione per partecipare a Microsoft Managed Desktop, ma l'esperienza utente sarà limitata.</span><span class="sxs-lookup"><span data-stu-id="0040b-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="0040b-113">Ad esempio, i dispositivi non saranno in grado di determinare automaticamente il fuso orario in cui si verificano quando gli utenti lavorano in un fuso orario diverso.</span><span class="sxs-lookup"><span data-stu-id="0040b-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="0040b-114">Abilitare il servizio di posizione</span><span class="sxs-lookup"><span data-stu-id="0040b-114">Enable the location service</span></span>

<span data-ttu-id="0040b-115">Puoi acconsentire esplicitamente all'uso del servizio di posizione quando i dispositivi vengono registrati nel servizio Microsoft Managed Desktop oppure puoi attivare o disattivare il servizio dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="0040b-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="0040b-116">Acconsentire esplicitamente durante la registrazione</span><span class="sxs-lookup"><span data-stu-id="0040b-116">Opt in during enrollment</span></span>

<span data-ttu-id="0040b-117">È possibile fare in modo che il Microsoft Managed Desktop abiliti il servizio di posizione.</span><span class="sxs-lookup"><span data-stu-id="0040b-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="0040b-118">Durante la sequenza di registrazione, ti verrà chiesto di scegliere se consentire o meno l'attivazione del servizio di Windows 10 di registrazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0040b-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="0040b-119">Controllare il servizio di posizione dopo la registrazione</span><span class="sxs-lookup"><span data-stu-id="0040b-119">Control the location service after enrollment</span></span>

<span data-ttu-id="0040b-120">Puoi avere il servizio di posizione attivato (o disattivato) in qualsiasi momento inviando una richiesta [di supporto](../working-with-managed-desktop/admin-support.md) tramite il portale [di amministrazione.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="0040b-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="0040b-121">Come Microsoft Managed Desktop il servizio di Windows 10 locale</span><span class="sxs-lookup"><span data-stu-id="0040b-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="0040b-122">Se si acconsente esplicitamente all'utilizzo del servizio di posizione, vengono utilizzate le impostazioni minime necessarie senza influire sulla privacy degli utenti.</span><span class="sxs-lookup"><span data-stu-id="0040b-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="0040b-123">Per ulteriori informazioni, vedere Windows 10 [servizio di posizione e privacy.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="0040b-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="0040b-124">Microsoft Managed Desktop **l'impostazione Privacy percorso** nelle impostazioni Windows **su** Consenti accesso alla posizione **nel dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="0040b-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="0040b-125">L'interfaccia utente è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0040b-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Impostazioni percorso in Windows impostazioni":::

> [!NOTE]
> <span data-ttu-id="0040b-127">Se acconsenti esplicitamente all'uso del servizio di posizione, questo vale solo per il Windows sistema operativo stesso.</span><span class="sxs-lookup"><span data-stu-id="0040b-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="0040b-128">Le app non possono usare i servizi di posizione.</span><span class="sxs-lookup"><span data-stu-id="0040b-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="0040b-129">Ogni utente può scegliere se consentire alle app di accedere alla propria posizione.</span><span class="sxs-lookup"><span data-stu-id="0040b-129">Each user can choose whether to allow apps to access their location.</span></span>