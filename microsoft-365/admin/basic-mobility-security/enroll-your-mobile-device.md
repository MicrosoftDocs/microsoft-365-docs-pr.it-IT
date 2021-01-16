---
title: Registrazione del dispositivo mobile tramite la sicurezza e la mobilità di base
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
description: Prima di poter utilizzare i servizi Microsoft 365 con il dispositivo, potrebbe essere necessario prima iscriverlo in Basic Mobility and Security per Microsoft 365.
ms.openlocfilehash: dc5a43b12fce50c9146200a4559fe9b7e6824b18
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877057"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="95a06-103">Registrazione del dispositivo mobile tramite la sicurezza e la mobilità di base</span><span class="sxs-lookup"><span data-stu-id="95a06-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="95a06-104">L'utilizzo del telefono, del tablet e di altri dispositivi mobili per il lavoro è un ottimo modo per rimanere informati e lavorare su progetti aziendali mentre si è lontani dall'ufficio.</span><span class="sxs-lookup"><span data-stu-id="95a06-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="95a06-105">Prima di poter utilizzare i servizi Microsoft 365 con il dispositivo, potrebbe essere necessario prima iscriverlo in Basic Mobility and Security per Microsoft 365 utilizzando il portale aziendale di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="95a06-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="95a06-106">Le organizzazioni scelgono la mobilità e la sicurezza di base, in modo che i dipendenti possano utilizzare i propri dispositivi mobili per accedere in sicurezza ai messaggi di posta elettronica, ai calendari e ai documenti di lavoro, mentre l'azienda protegge i dati importanti e soddisfa i requisiti</span><span class="sxs-lookup"><span data-stu-id="95a06-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="95a06-107">Per ulteriori informazioni, vedere [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="95a06-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="95a06-108">Per altre informazioni, vedere [quali informazioni possono essere visualizzate dall'organizzazione quando si esegue la registrazione del dispositivo?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="95a06-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="95a06-109">Quando si registra il dispositivo in mobilità e sicurezza di base per Microsoft 365, potrebbe essere necessario impostare una password, insieme all'opzione che consente all'organizzazione del lavoro di cancellare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95a06-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="95a06-110">Un wipe del dispositivo può essere eseguito dall'interfaccia di amministrazione di Microsoft 365, ad esempio, per rimuovere tutti i dati dal dispositivo se la password viene immessa in modo errato troppe volte o se i termini di utilizzo sono interrotti.</span><span class="sxs-lookup"><span data-stu-id="95a06-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="95a06-111">Dispositivi supportati</span><span class="sxs-lookup"><span data-stu-id="95a06-111">Supported devices</span></span>

<span data-ttu-id="95a06-112">La sicurezza e la mobilità di base per Microsoft 365 ospitate dal servizio di Intune funzionano con la maggior parte dei dispositivi mobili, ma non di tutti.</span><span class="sxs-lookup"><span data-stu-id="95a06-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="95a06-113">Di seguito sono supportate le funzionalità di base per dispositivi mobili e sicurezza:</span><span class="sxs-lookup"><span data-stu-id="95a06-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="95a06-114">iOS 10,0 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="95a06-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="95a06-115">Android 4,4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="95a06-115">Android 4.4 or later</span></span>

- <span data-ttu-id="95a06-116">Windows 8,1 e Windows 10 (telefono e PC)</span><span class="sxs-lookup"><span data-stu-id="95a06-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="95a06-117">Se il dispositivo non è elencato sopra ed è necessario utilizzarlo con la sicurezza e la mobilità di base, contattare l'amministratore del lavoro o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="95a06-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="95a06-118">In caso di problemi di registrazione del dispositivo, vedere risolvere i [problemi relativi a mobilità e sicurezza di base](/basic-mobility-security/troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="95a06-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](/basic-mobility-security/troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="95a06-119">Configurare il dispositivo mobile con Intune e la mobilità e la sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="95a06-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="95a06-120">Il portale aziendale di Intune consente a un dispositivo di essere gestito da Microsoft 365 e dalla mobilità e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="95a06-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="95a06-121">iPhone o iPad</span><span class="sxs-lookup"><span data-stu-id="95a06-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="95a06-122">L'utente non sarà in grado di inviare e ricevere messaggi di posta elettronica fino al completamento di questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="95a06-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="95a06-123">Accedere all'App Store di Apple e scaricare e installare il portale aziendale di Intune.</span><span class="sxs-lookup"><span data-stu-id="95a06-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="95a06-124">Per connettere e configurare il telefono o tablet iOS con il portale aziendale in Office 365, vedere [configurare l'accesso ai dispositivi iOS alle risorse aziendali](https://go.microsoft.com/fwlink/?linkid=875316).</span><span class="sxs-lookup"><span data-stu-id="95a06-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="95a06-125">Telefono o tablet Android</span><span class="sxs-lookup"><span data-stu-id="95a06-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="95a06-126">L'utente non sarà in grado di inviare e ricevere messaggi di posta elettronica fino al completamento di questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="95a06-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="95a06-127">Accedere a Google Play Store e scaricare e installare il portale aziendale di Intune.</span><span class="sxs-lookup"><span data-stu-id="95a06-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="95a06-128">Per connettere e configurare il telefono o tablet Android con il portale aziendale su Microsoft 365, vedere [registrazione del dispositivo con il portale aziendale](https://go.microsoft.com/fwlink/?linkid=875317).</span><span class="sxs-lookup"><span data-stu-id="95a06-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="95a06-129">Windows 8,1 e Windows 10</span><span class="sxs-lookup"><span data-stu-id="95a06-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="95a06-130">Accedere a Microsoft Store e scaricare e installare il portale aziendale di Intune</span><span class="sxs-lookup"><span data-stu-id="95a06-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="95a06-131">Per connettere e configurare Windows Phone o PC con il portale aziendale su Microsoft 365, vedere [registrazione dei dispositivi di Windows nel portale aziendale di Intune](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="95a06-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="95a06-132">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="95a06-132">What's next?</span></span>

<span data-ttu-id="95a06-133">Dopo che il dispositivo è stato registrato in mobilità e sicurezza di base, è possibile iniziare a utilizzare le app di Office nel dispositivo per collaborare con posta elettronica, calendario, contatti e documenti.</span><span class="sxs-lookup"><span data-stu-id="95a06-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
