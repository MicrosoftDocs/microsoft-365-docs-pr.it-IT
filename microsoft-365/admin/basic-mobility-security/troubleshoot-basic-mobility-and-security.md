---
title: Risoluzione dei problemi relativi a mobilità e sicurezza di base
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Provare a eseguire questa procedura per individuare i problemi di sicurezza e mobilità di base
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336936"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="1398f-103">Risoluzione dei problemi relativi a mobilità e sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="1398f-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="1398f-104">Se si verificano problemi durante il tentativo di registrazione di un dispositivo in mobilità e sicurezza di base, provare a eseguire i passaggi seguenti per individuare il problema.</span><span class="sxs-lookup"><span data-stu-id="1398f-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="1398f-105">Se la procedura generale non risolve il problema, vedere una delle sezioni successive con passaggi specifici per il tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1398f-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="1398f-106">Passaggi da provare per primo</span><span class="sxs-lookup"><span data-stu-id="1398f-106">Steps to try first</span></span>

<span data-ttu-id="1398f-107">Per iniziare, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1398f-107">To start, check the following:</span></span>

- <span data-ttu-id="1398f-108">Verificare che il dispositivo non sia già stato registrato con un altro provider di gestione dei dispositivi mobili, ad esempio Intune.</span><span class="sxs-lookup"><span data-stu-id="1398f-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="1398f-109">Verificare che il dispositivo sia impostato sulla data e l'ora corrette.</span><span class="sxs-lookup"><span data-stu-id="1398f-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="1398f-110">Passare a una rete Wi-Fi o cellulare diversa nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1398f-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="1398f-111">Per i dispositivi Android o iOS, disinstallare e reinstallare l'app portale aziendale di Intune nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1398f-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="1398f-112">telefono o tablet iOS</span><span class="sxs-lookup"><span data-stu-id="1398f-112">iOS phone or tablet</span></span>

- <span data-ttu-id="1398f-113">Assicurarsi di aver configurato un certificato di APNs.</span><span class="sxs-lookup"><span data-stu-id="1398f-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="1398f-114">Per altre informazioni, vedere [Create an APNs certificate for iOS Devices](create-an-apns-certificate-for-ios-devices.md).</span><span class="sxs-lookup"><span data-stu-id="1398f-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="1398f-115">In **Impostazioni**   >  **General**   >  **profilo generale (o gestione dispositivi)** verificare che un profilo di gestione non sia già installato.</span><span class="sxs-lookup"><span data-stu-id="1398f-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="1398f-116">In tal caso, rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="1398f-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="1398f-117">Se viene visualizzato il messaggio di errore "il dispositivo non è in grado di eseguire la registrazione", accedere a Microsoft 365 e verificare che sia stata assegnata una licenza che include Exchange Online all'utente che ha eseguito l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1398f-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="1398f-118">Se viene visualizzato il messaggio di errore "profilo non riuscito per l'installazione", provare a eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1398f-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="1398f-119">Verificare che Safari sia il browser predefinito del dispositivo e che i cookie non siano disabilitati.</span><span class="sxs-lookup"><span data-stu-id="1398f-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="1398f-120">Riavviare il dispositivo, quindi passare a portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1398f-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="1398f-121">Accedere con l'ID utente e la password Microsoft 365 e tentare di installare il profilo manualmente.</span><span class="sxs-lookup"><span data-stu-id="1398f-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="1398f-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="1398f-122">Windows RT</span></span>

- <span data-ttu-id="1398f-123">Verificare che il dominio sia configurato in Microsoft 365 per funzionare con la sicurezza e la mobilità di base.</span><span class="sxs-lookup"><span data-stu-id="1398f-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="1398f-124">Per altre informazioni, vedere [configurare la sicurezza e la mobilità di base](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="1398f-124">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="1398f-125">Assicurarsi che l'utente abbia scelto **attiva**   invece di scegliere **join**.</span><span class="sxs-lookup"><span data-stu-id="1398f-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="1398f-126">PC con Windows 10</span><span class="sxs-lookup"><span data-stu-id="1398f-126">Windows 10 PC</span></span>

- <span data-ttu-id="1398f-127">Verificare che il dominio sia configurato in Microsoft 365 per funzionare con la sicurezza e la mobilità di base.</span><span class="sxs-lookup"><span data-stu-id="1398f-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="1398f-128">Per altre informazioni, vedere [configurare la sicurezza e la mobilità di base](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="1398f-128">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="1398f-129">Se non si dispone di Azure Active Directory Premium, assicurarsi che l'utente stia scegliendo **registrazione in gestione dispositivi solo**   anziché scegliere **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="1398f-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="1398f-130">Telefono o tablet Android</span><span class="sxs-lookup"><span data-stu-id="1398f-130">Android phone or tablet</span></span>

- <span data-ttu-id="1398f-131">Verificare che il dispositivo esegua Android 4,4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1398f-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="1398f-132">Verificare che Chrome sia aggiornato e che sia impostato come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="1398f-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="1398f-133">Se viene visualizzato il messaggio di errore "non è stato possibile registrare il dispositivo", accedere a Microsoft 365 e verificare che sia stata assegnata una licenza che include Exchange Online all'utente che ha eseguito l'accesso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1398f-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="1398f-134">Controllare l'area di notifica del dispositivo per verificare se le azioni dell'utente finale devono essere in sospeso e, se lo sono, completare le azioni.</span><span class="sxs-lookup"><span data-stu-id="1398f-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>