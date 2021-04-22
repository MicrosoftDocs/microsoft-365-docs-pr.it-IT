---
title: Microsoft Defender per Endpoint su Android - Informazioni sulla privacy
description: Controlli sulla privacy, come configurare le impostazioni dei criteri che influiscono sulla privacy e informazioni sui dati di diagnostica raccolti in Microsoft Defender per Endpoint su Android.
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostica
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
ms.openlocfilehash: 415a1f555e1a33c103894221086b783aa754cf32
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930138"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="5275d-104">Microsoft Defender per Endpoint su Android - Informazioni sulla privacy</span><span class="sxs-lookup"><span data-stu-id="5275d-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="5275d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5275d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5275d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5275d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5275d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5275d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5275d-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5275d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5275d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5275d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="5275d-110">Defender per Endpoint su Android raccoglie le informazioni dai dispositivi Android configurati e le archivia nello stesso tenant in cui si dispone di Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5275d-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="5275d-111">Le informazioni vengono raccolte per mantenere Defender for Endpoint per Android sicuro, aggiornato, che funzioni come previsto e per supportare il servizio.</span><span class="sxs-lookup"><span data-stu-id="5275d-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="5275d-112">Per altre informazioni sull'archiviazione dei dati, vedi [Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="5275d-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="5275d-113">Vengono raccolte informazioni per mantenere Defender for Endpoint per Android sicuro, aggiornato, che funzioni come previsto e supporti il servizio.</span><span class="sxs-lookup"><span data-stu-id="5275d-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="5275d-114">Dati obbligatori</span><span class="sxs-lookup"><span data-stu-id="5275d-114">Required Data</span></span> 

<span data-ttu-id="5275d-115">I dati necessari sono costituiti dai dati necessari per far funzionare Defender for Endpoint per Android come previsto.</span><span class="sxs-lookup"><span data-stu-id="5275d-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="5275d-116">Questi dati sono essenziali per il funzionamento del servizio e possono includere dati relativi all'utente finale, all'organizzazione, al dispositivo e alle app.</span><span class="sxs-lookup"><span data-stu-id="5275d-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="5275d-117">Ecco un elenco dei tipi di dati raccolti:</span><span class="sxs-lookup"><span data-stu-id="5275d-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="5275d-118">Informazioni sull'app</span><span class="sxs-lookup"><span data-stu-id="5275d-118">App information</span></span>

<span data-ttu-id="5275d-119">Informazioni sui **pacchetti di** applicazioni Android dannosi (APK) nel dispositivo, tra cui</span><span class="sxs-lookup"><span data-stu-id="5275d-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="5275d-120">Origine installazione</span><span class="sxs-lookup"><span data-stu-id="5275d-120">Install source</span></span>
-  <span data-ttu-id="5275d-121">Percorso di archiviazione (percorso file) dell'APK</span><span class="sxs-lookup"><span data-stu-id="5275d-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="5275d-122">Tempo di installazione, dimensioni di APK e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5275d-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="5275d-123">Pagina Web / Informazioni di rete</span><span class="sxs-lookup"><span data-stu-id="5275d-123">Web page / Network information</span></span>

- <span data-ttu-id="5275d-124">URL completo del sito Web solo quando viene rilevata una connessione o una pagina Web dannosa.</span><span class="sxs-lookup"><span data-stu-id="5275d-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="5275d-125">Informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="5275d-125">Connection information</span></span>
- <span data-ttu-id="5275d-126">Tipo di protocollo (ad esempio HTTP, HTTPS e così via)</span><span class="sxs-lookup"><span data-stu-id="5275d-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="5275d-127">Informazioni su dispositivi e account</span><span class="sxs-lookup"><span data-stu-id="5275d-127">Device and account information</span></span>

- <span data-ttu-id="5275d-128">Informazioni sul dispositivo, ad esempio data &, versione Android, modello OEM, informazioni sulla CPU e identificatore del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5275d-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="5275d-129">L'identificatore del dispositivo è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="5275d-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="5275d-130">Wi-Fi mac della scheda di rete</span><span class="sxs-lookup"><span data-stu-id="5275d-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="5275d-131">[ID Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generato da Android al momento del primo avvio del dispositivo)</span><span class="sxs-lookup"><span data-stu-id="5275d-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="5275d-132">Identificatore univoco globale (GUID) generato in modo casuale</span><span class="sxs-lookup"><span data-stu-id="5275d-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="5275d-133">Informazioni su tenant, dispositivo e utente</span><span class="sxs-lookup"><span data-stu-id="5275d-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="5275d-134">ID dispositivo di Azure Active Directory (AD) e ID utente di Azure: identifica in modo univoco il dispositivo, rispettivamente Utente in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5275d-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="5275d-135">ID tenant di Azure - GUID che identifica l'organizzazione all'interno di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5275d-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="5275d-136">ID organizzazione di Microsoft Defender ATP - Identificatore univoco associato all'organizzazione a cui appartiene il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5275d-136">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="5275d-137">Consente a Microsoft di identificare se i problemi influiscono su un set selezionato di aziende e su quante aziende sono influenzate</span><span class="sxs-lookup"><span data-stu-id="5275d-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="5275d-138">Nome entità utente - ID posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="5275d-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="5275d-139">Dati sull'utilizzo di prodotti e servizi</span><span class="sxs-lookup"><span data-stu-id="5275d-139">Product and service usage data</span></span>

<span data-ttu-id="5275d-140">Le informazioni seguenti vengono raccolte solo per l'app Microsoft Defender for Endpoint installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5275d-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="5275d-141">Informazioni sul pacchetto dell'app, tra cui nome, versione e stato dell'aggiornamento dell'app</span><span class="sxs-lookup"><span data-stu-id="5275d-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="5275d-142">Azioni eseguite nell'app</span><span class="sxs-lookup"><span data-stu-id="5275d-142">Actions performed in the app</span></span>

-   <span data-ttu-id="5275d-143">Informazioni sul rilevamento delle minacce, ad esempio nome, categoria e così via.</span><span class="sxs-lookup"><span data-stu-id="5275d-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="5275d-144">Log dei rapporti di arresto anomalo generati da Android</span><span class="sxs-lookup"><span data-stu-id="5275d-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="5275d-145">Dati facoltativi</span><span class="sxs-lookup"><span data-stu-id="5275d-145">Optional Data</span></span>

<span data-ttu-id="5275d-146">I dati facoltativi includono i dati di diagnostica e i dati di feedback.</span><span class="sxs-lookup"><span data-stu-id="5275d-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="5275d-147">Dati di diagnostica facoltativi sono i dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="5275d-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="5275d-148">I dati di diagnostica facoltativi includono:</span><span class="sxs-lookup"><span data-stu-id="5275d-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="5275d-149">Utilizzo di app, CPU e rete</span><span class="sxs-lookup"><span data-stu-id="5275d-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="5275d-150">Stato del dispositivo dal punto di vista dell'app, inclusi lo stato dell'analisi, gli intervalli di analisi, le autorizzazioni dell'app concesse e lo stato dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="5275d-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="5275d-151">Funzionalità configurate dall'amministratore</span><span class="sxs-lookup"><span data-stu-id="5275d-151">Features configured by the admin</span></span>

-   <span data-ttu-id="5275d-152">Informazioni di base sui browser nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="5275d-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="5275d-153">**Feedback I dati** vengono raccolti tramite il feedback in-app fornito dall'utente</span><span class="sxs-lookup"><span data-stu-id="5275d-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="5275d-154">Indirizzo di posta elettronica dell'utente, se sceglie di fornirlo</span><span class="sxs-lookup"><span data-stu-id="5275d-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="5275d-155">Tipo di feedback (smile, cipiglio, idea) ed eventuali commenti di feedback inviati dall'utente</span><span class="sxs-lookup"><span data-stu-id="5275d-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
