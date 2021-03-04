---
title: Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Prima di poter usare i servizi di Microsoft 365 con il dispositivo, potrebbe essere necessario registrarlo in Basic Mobility and Security per Microsoft 365.
ms.openlocfilehash: 2a9c0bd9faf670d7dca340d3bc4e9f6586bd6b66
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423202"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="6dd2e-103">Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="6dd2e-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="6dd2e-104">L'uso di telefoni, tablet e altri dispositivi mobili per il lavoro è un ottimo modo per rimanere informati e lavorare ai progetti aziendali mentre si è fuori dall'ufficio.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="6dd2e-105">Prima di poter usare i servizi di Microsoft 365 con il dispositivo, potrebbe essere necessario registrarlo in Basic Mobility and Security per Microsoft 365 tramite il portale aziendale di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="6dd2e-106">Le organizzazioni scelgono La mobilità e la sicurezza di base in modo che i dipendenti possano usare i dispositivi mobili per accedere in modo sicuro alla posta elettronica, ai calendari e ai documenti di lavoro, mentre l'azienda protegge i dati importanti e soddisfa i requisiti di conformità.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="6dd2e-107">Per altre informazioni, vedere Panoramica della mobilità e della sicurezza di [base per Microsoft 365.](overview.md)</span><span class="sxs-lookup"><span data-stu-id="6dd2e-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="6dd2e-108">Per altre info, vedi Quali informazioni possono essere visualizzate [dall'organizzazione quando si registra il dispositivo?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="6dd2e-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="6dd2e-109">Quando si registra il dispositivo in Basic Mobility and Security per Microsoft 365, potrebbe essere necessario configurare una password, oltre a consentire all'organizzazione aziendale di cancellare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="6dd2e-110">Una cancellazione del dispositivo può essere eseguita dall'interfaccia di amministrazione di Microsoft 365, ad esempio, per rimuovere tutti i dati dal dispositivo se la password viene immessa in modo errato troppe volte o se i termini di utilizzo sono interrotti.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="6dd2e-111">Dispositivi supportati</span><span class="sxs-lookup"><span data-stu-id="6dd2e-111">Supported devices</span></span>

<span data-ttu-id="6dd2e-112">Basic Mobility and Security per Microsoft 365 ospitato dal servizio Intune funziona con la maggior parte dei dispositivi mobili, ma non con tutti.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="6dd2e-113">Le funzionalità di mobilità e sicurezza di base sono supportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="6dd2e-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="6dd2e-114">iOS 10.0 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="6dd2e-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="6dd2e-115">Android 4.4 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="6dd2e-115">Android 4.4 or later</span></span>

- <span data-ttu-id="6dd2e-116">Windows 8.1 e Windows 10 (telefono e PC)</span><span class="sxs-lookup"><span data-stu-id="6dd2e-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="6dd2e-117">Se il dispositivo non è elencato in precedenza ed è necessario usarlo con Basic Mobility and Security, contattare l'amministratore aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="6dd2e-118">Se si verificano problemi durante la registrazione del dispositivo, vedere [Risolvere i problemi di sicurezza e mobilità di base.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="6dd2e-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="6dd2e-119">Configurare il dispositivo mobile con Intune e Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="6dd2e-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="6dd2e-120">Il portale aziendale intune consente di gestire un dispositivo da Microsoft 365 e Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="6dd2e-121">iPhone o iPad</span><span class="sxs-lookup"><span data-stu-id="6dd2e-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="6dd2e-122">Non sarà possibile inviare e ricevere messaggi di posta elettronica finché non si completa questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="6dd2e-123">Accedere all'App Store di Apple e scaricare e installare il portale aziendale di Intune.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="6dd2e-124">Per connettere e configurare il telefono o il tablet iOS con il portale aziendale a Office 365, vedere Configurare l'accesso dei dispositivi [iOS alle risorse aziendali.](https://go.microsoft.com/fwlink/?linkid=875316)</span><span class="sxs-lookup"><span data-stu-id="6dd2e-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="6dd2e-125">Telefono o tablet Android</span><span class="sxs-lookup"><span data-stu-id="6dd2e-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="6dd2e-126">Non sarà possibile inviare e ricevere messaggi di posta elettronica finché non si completa questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="6dd2e-127">Passare a Google Play Store e scaricare e installare il portale aziendale di Intune.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="6dd2e-128">Per connettere e configurare il telefono o il tablet Android con il portale aziendale a Microsoft 365, vedere [Registrare il dispositivo con Portale aziendale.](https://go.microsoft.com/fwlink/?linkid=875317)</span><span class="sxs-lookup"><span data-stu-id="6dd2e-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="6dd2e-129">Windows 8.1 e Windows 10</span><span class="sxs-lookup"><span data-stu-id="6dd2e-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="6dd2e-130">Passare a Microsoft Store e scaricare e installare il portale aziendale di Intune</span><span class="sxs-lookup"><span data-stu-id="6dd2e-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="6dd2e-131">Per connettere e configurare windows phone o PC con il portale aziendale a Microsoft 365, vedere Registrazione di dispositivi [Windows nel portale aziendale di Intune.](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="6dd2e-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="6dd2e-132">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="6dd2e-132">What's next?</span></span>

<span data-ttu-id="6dd2e-133">Dopo aver registrato il dispositivo in Basic Mobility and Security, è possibile iniziare a usare le app di Office nel dispositivo per usare posta elettronica, calendario, contatti e documenti.</span><span class="sxs-lookup"><span data-stu-id="6dd2e-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
