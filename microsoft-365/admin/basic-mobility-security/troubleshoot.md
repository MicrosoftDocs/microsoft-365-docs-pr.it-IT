---
title: Risolvere i problemi relativi alla mobilità e alla sicurezza di base
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
description: Provare questi passaggi per tenere traccia dei problemi di sicurezza e mobilità di base
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876853"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="5a545-103">Risolvere i problemi relativi alla mobilità e alla sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="5a545-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="5a545-104">Se si verificano problemi quando si tenta di registrare un dispositivo in Dispositivi mobili e sicurezza di base, provare la procedura qui per rilevare il problema.</span><span class="sxs-lookup"><span data-stu-id="5a545-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="5a545-105">Se la procedura generale non consente di risolvere il problema, vedi una delle sezioni successive con passaggi specifici per il tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5a545-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="5a545-106">Passaggi da provare per primi</span><span class="sxs-lookup"><span data-stu-id="5a545-106">Steps to try first</span></span>

<span data-ttu-id="5a545-107">Per iniziare, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5a545-107">To start, check the following:</span></span>

- <span data-ttu-id="5a545-108">Assicurati che il dispositivo non sia già registrato con un altro provider di gestione dei dispositivi mobili, ad esempio Intune.</span><span class="sxs-lookup"><span data-stu-id="5a545-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="5a545-109">Assicurati che il dispositivo sia impostato sulla data e sull'ora corrette.</span><span class="sxs-lookup"><span data-stu-id="5a545-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="5a545-110">Passare a una rete WIFI o cellulare diversa nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5a545-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="5a545-111">Per i dispositivi Android o iOS, disinstalla e reinstalla l Portale aziendale Intune app nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5a545-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="5a545-112">Telefono o tablet iOS</span><span class="sxs-lookup"><span data-stu-id="5a545-112">iOS phone or tablet</span></span>

- <span data-ttu-id="5a545-113">Assicurati di aver configurato un certificato APNs.</span><span class="sxs-lookup"><span data-stu-id="5a545-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="5a545-114">Per altre info, vedi [Creare un certificato APNs per i dispositivi iOS.](create-an-apns-certificate-for-ios-devices.md)</span><span class="sxs-lookup"><span data-stu-id="5a545-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="5a545-115">In **Impostazioni**   >  **profilo**   >  **generale (o Gestione dispositivi)** assicurati che un profilo di gestione non sia già installato.</span><span class="sxs-lookup"><span data-stu-id="5a545-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="5a545-116">In caso contrario, rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="5a545-116">If it is, remove it.</span></span>

- <span data-ttu-id="5a545-117">Se viene visualizzato il messaggio di errore "Impossibile registrare il dispositivo", accedere a Microsoft 365 e assicurarsi che all'utente che ha eseguito l'accesso al dispositivo sia stata assegnata una licenza che include Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5a545-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="5a545-118">Se viene visualizzato il messaggio di errore "Impossibile installare il profilo", provare a eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a545-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="5a545-119">Assicurati che Safari sia il browser predefinito nel dispositivo e che i cookie non siano disabilitati.</span><span class="sxs-lookup"><span data-stu-id="5a545-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="5a545-120">Riavvia il dispositivo e quindi passa a portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5a545-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="5a545-121">Accedi con l'ID Microsoft 365 utente e la password e prova a installare il profilo manualmente.</span><span class="sxs-lookup"><span data-stu-id="5a545-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="5a545-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="5a545-122">Windows RT</span></span>

- <span data-ttu-id="5a545-123">Assicurati che il dominio sia configurato in Microsoft 365 per l'utilizzo con Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="5a545-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="5a545-124">Per altre info, vedi [Configurare dispositivi mobili e sicurezza di base.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="5a545-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="5a545-125">Assicurati che l'utente scegli **Attiva invece** di   scegliere **Partecipa.**</span><span class="sxs-lookup"><span data-stu-id="5a545-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="5a545-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="5a545-126">Windows 10 PC</span></span>

- <span data-ttu-id="5a545-127">Assicurati che il dominio sia configurato in Microsoft 365 per l'utilizzo con Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="5a545-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="5a545-128">Per altre info, vedi [Configurare dispositivi mobili e sicurezza di base.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="5a545-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="5a545-129">A meno che non Azure Active Directory Premium, assicurati che l'utente scegli Registra **solo in** Gestione dispositivi invece di   scegliere **Connessione**.</span><span class="sxs-lookup"><span data-stu-id="5a545-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="5a545-130">Telefono o tablet Android</span><span class="sxs-lookup"><span data-stu-id="5a545-130">Android phone or tablet</span></span>

- <span data-ttu-id="5a545-131">Assicurati che il dispositivo eserciti Android 4.4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="5a545-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="5a545-132">Assicurati che Chrome sia aggiornato e sia impostato come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="5a545-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="5a545-133">Se viene visualizzato il messaggio di errore "Impossibile registrare questo dispositivo", accedere a Microsoft 365 e assicurarsi che all'utente che ha eseguito l'accesso al dispositivo sia stata assegnata una licenza che include Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5a545-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="5a545-134">Controlla l'area di notifica nel dispositivo per verificare se sono in sospeso eventuali azioni dell'utente finale necessarie e, in caso contrario, completa le azioni.</span><span class="sxs-lookup"><span data-stu-id="5a545-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>