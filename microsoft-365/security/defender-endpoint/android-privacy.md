---
title: Microsoft Defender ATP per Android - Informazioni sulla privacy
description: Controlli sulla privacy, come configurare le impostazioni dei criteri che influiscono sulla privacy e informazioni sui dati di diagnostica raccolti in Microsoft Defender ATP per Android.
keywords: microsoft, defender, atp, android, privacy, diagnostica
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d38d7a54aa860049e1968e5b92c801107bea0514
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687962"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="f23eb-104">Microsoft Defender per Endpoint su Android - Informazioni sulla privacy</span><span class="sxs-lookup"><span data-stu-id="f23eb-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="f23eb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f23eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="f23eb-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f23eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f23eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f23eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f23eb-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f23eb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f23eb-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f23eb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="f23eb-110">Defender for Endpoint per Android raccoglie le informazioni dai dispositivi Android configurati e le archivia nello stesso tenant in cui si dispone di Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f23eb-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="f23eb-111">Vengono raccolte informazioni per mantenere Defender for Endpoint per Android sicuro, aggiornato, che funzioni come previsto e supporti il servizio.</span><span class="sxs-lookup"><span data-stu-id="f23eb-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="f23eb-112">Dati obbligatori</span><span class="sxs-lookup"><span data-stu-id="f23eb-112">Required Data</span></span> 

<span data-ttu-id="f23eb-113">I dati necessari sono costituiti dai dati necessari per far funzionare Defender for Endpoint per Android come previsto.</span><span class="sxs-lookup"><span data-stu-id="f23eb-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="f23eb-114">Questi dati sono essenziali per il funzionamento del servizio e possono includere dati relativi all'utente finale, all'organizzazione, al dispositivo e alle app.</span><span class="sxs-lookup"><span data-stu-id="f23eb-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="f23eb-115">Ecco un elenco dei tipi di dati raccolti:</span><span class="sxs-lookup"><span data-stu-id="f23eb-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="f23eb-116">Informazioni sull'app</span><span class="sxs-lookup"><span data-stu-id="f23eb-116">App information</span></span>

<span data-ttu-id="f23eb-117">Informazioni sui pacchetti di applicazioni Android (APK) nel dispositivo, tra cui</span><span class="sxs-lookup"><span data-stu-id="f23eb-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="f23eb-118">Origine installazione</span><span class="sxs-lookup"><span data-stu-id="f23eb-118">Install source</span></span>
-  <span data-ttu-id="f23eb-119">Percorso di archiviazione (percorso file) dell'APK</span><span class="sxs-lookup"><span data-stu-id="f23eb-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="f23eb-120">Tempo di installazione, dimensioni di APK e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f23eb-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="f23eb-121">Pagina Web / Informazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f23eb-121">Web page / Network information</span></span>

- <span data-ttu-id="f23eb-122">URL completo (nei browser supportati), quando si fa clic su</span><span class="sxs-lookup"><span data-stu-id="f23eb-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="f23eb-123">Informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="f23eb-123">Connection information</span></span>
- <span data-ttu-id="f23eb-124">Tipo di protocollo (ad esempio HTTP, HTTPS e così via)</span><span class="sxs-lookup"><span data-stu-id="f23eb-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="f23eb-125">Informazioni su dispositivi e account</span><span class="sxs-lookup"><span data-stu-id="f23eb-125">Device and account information</span></span>

- <span data-ttu-id="f23eb-126">Informazioni sul dispositivo, ad esempio data &, versione Android, modello OEM, informazioni sulla CPU e identificatore del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f23eb-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="f23eb-127">L'identificatore del dispositivo è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="f23eb-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="f23eb-128">Wi-Fi mac della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="f23eb-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="f23eb-129">[ID Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generato da Android al momento del primo avvio del dispositivo)</span><span class="sxs-lookup"><span data-stu-id="f23eb-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="f23eb-130">Identificatore univoco globale (GUID) generato in modo casuale</span><span class="sxs-lookup"><span data-stu-id="f23eb-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="f23eb-131">Informazioni su tenant, dispositivo e utente</span><span class="sxs-lookup"><span data-stu-id="f23eb-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="f23eb-132">ID dispositivo di Azure Active Directory (AD) e ID utente di Azure: identifica in modo univoco il dispositivo, rispettivamente Utente in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f23eb-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="f23eb-133">ID tenant di Azure - GUID che identifica l'organizzazione all'interno di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f23eb-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="f23eb-134">ID organizzazione di Microsoft Defender ATP - Identificatore univoco associato all'organizzazione a cui appartiene il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f23eb-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="f23eb-135">Consente a Microsoft di identificare se i problemi influiscono su un set selezionato di aziende e su quante aziende sono influenzate</span><span class="sxs-lookup"><span data-stu-id="f23eb-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="f23eb-136">Nome entità utente - ID posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="f23eb-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="f23eb-137">Dati sull'utilizzo di prodotti e servizi</span><span class="sxs-lookup"><span data-stu-id="f23eb-137">Product and service usage data</span></span>
-   <span data-ttu-id="f23eb-138">Informazioni sul pacchetto dell'app, tra cui nome, versione e stato dell'aggiornamento dell'app</span><span class="sxs-lookup"><span data-stu-id="f23eb-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="f23eb-139">Azioni eseguite nell'app</span><span class="sxs-lookup"><span data-stu-id="f23eb-139">Actions performed in the app</span></span>

-   <span data-ttu-id="f23eb-140">Informazioni sul rilevamento delle minacce, ad esempio nome, categoria e così via.</span><span class="sxs-lookup"><span data-stu-id="f23eb-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="f23eb-141">Log dei rapporti di arresto anomalo generati da Android</span><span class="sxs-lookup"><span data-stu-id="f23eb-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="f23eb-142">Dati facoltativi</span><span class="sxs-lookup"><span data-stu-id="f23eb-142">Optional Data</span></span>

<span data-ttu-id="f23eb-143">I dati facoltativi includono i dati di diagnostica e i dati di feedback.</span><span class="sxs-lookup"><span data-stu-id="f23eb-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="f23eb-144">Dati di diagnostica facoltativi sono i dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="f23eb-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="f23eb-145">I dati di diagnostica facoltativi includono:</span><span class="sxs-lookup"><span data-stu-id="f23eb-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="f23eb-146">Utilizzo di app, CPU e rete</span><span class="sxs-lookup"><span data-stu-id="f23eb-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="f23eb-147">Stato del dispositivo dal punto di vista dell'app, inclusi lo stato dell'analisi, gli intervalli di analisi, le autorizzazioni dell'app concesse e lo stato dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f23eb-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="f23eb-148">Funzionalità configurate dall'amministratore</span><span class="sxs-lookup"><span data-stu-id="f23eb-148">Features configured by the admin</span></span>

-   <span data-ttu-id="f23eb-149">Informazioni di base sui browser nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="f23eb-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="f23eb-150">**Feedback I dati** vengono raccolti tramite il feedback in-app fornito dall'utente</span><span class="sxs-lookup"><span data-stu-id="f23eb-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="f23eb-151">Indirizzo di posta elettronica dell'utente, se sceglie di fornirlo</span><span class="sxs-lookup"><span data-stu-id="f23eb-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="f23eb-152">Tipo di feedback (smile, cipiglio, idea) ed eventuali commenti di feedback inviati dall'utente</span><span class="sxs-lookup"><span data-stu-id="f23eb-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
