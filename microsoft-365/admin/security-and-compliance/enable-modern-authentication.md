---
title: Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Informazioni su come impostare le chiavi del Registro di sistema per abilitare l'autenticazione moderna per i dispositivi Microsoft Office 2013.
ms.openlocfilehash: 2a4be82328d391db7808cb9197ce259275b567c6
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758929"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="c2ed7-103">Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows</span><span class="sxs-lookup"><span data-stu-id="c2ed7-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="c2ed7-104">Per abilitare l'autenticazione moderna per tutti i dispositivi Windows con Office 2013 installato, è necessario impostare specifiche chiavi del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="c2ed7-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="c2ed7-105">Abilitare l'autenticazione moderna per i client di Office 2013</span><span class="sxs-lookup"><span data-stu-id="c2ed7-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="c2ed7-106">L'autenticazione moderna è già attivata per i client di Office 2016, non è necessario impostare le chiavi del Registro di sistema per Office 2016.</span><span class="sxs-lookup"><span data-stu-id="c2ed7-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="c2ed7-p101">Per abilitare l'autenticazione moderna per tutti i dispositivi che eseguono Windows (ad esempio su portatili e tablet) con Microsoft Office 2013 installato, è necessario impostare le seguenti chiavi del Registro di sistema. Le chiavi devono essere impostate in ogni dispositivo per cui si vuole abilitare l'autenticazione moderna:</span><span class="sxs-lookup"><span data-stu-id="c2ed7-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="c2ed7-109">**Chiave del Registro di sistema**</span><span class="sxs-lookup"><span data-stu-id="c2ed7-109">**Registry key**</span></span>|<span data-ttu-id="c2ed7-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c2ed7-110">**Type**</span></span>|<span data-ttu-id="c2ed7-111">**Valore**</span><span class="sxs-lookup"><span data-stu-id="c2ed7-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="c2ed7-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="c2ed7-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="c2ed7-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c2ed7-113">REG_DWORD</span></span>  |<span data-ttu-id="c2ed7-114">1</span><span class="sxs-lookup"><span data-stu-id="c2ed7-114">1</span></span>  |
|<span data-ttu-id="c2ed7-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="c2ed7-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="c2ed7-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c2ed7-116">REG_DWORD</span></span> |<span data-ttu-id="c2ed7-117">1</span><span class="sxs-lookup"><span data-stu-id="c2ed7-117">1</span></span> |
   
<span data-ttu-id="c2ed7-118">Dopo aver impostato le chiavi del Registro di sistema, è possibile impostare le app dei dispositivi di Office 2013 per l'utilizzo dell'autenticazione a più fattori [(MFA)](set-up-multi-factor-authentication.md) con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2ed7-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="c2ed7-p102">Se si è attualmente connessi con una delle app client, è necessario disconnettersi e accedere di nuovo per rendere effettive le modifiche. In caso contrario, le impostazioni MRU e di roaming non saranno disponibili finché non viene stabilita l'identità ADAL.</span><span class="sxs-lookup"><span data-stu-id="c2ed7-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="c2ed7-121">Disabilitare l'autenticazione moderna nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c2ed7-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="c2ed7-122">Per disabilitare l'autenticazione moderna in un dispositivo, impostare le seguenti chiavi del Registro di sistema nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c2ed7-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="c2ed7-123">**Chiave del Registro di sistema**</span><span class="sxs-lookup"><span data-stu-id="c2ed7-123">**Registry key**</span></span>|<span data-ttu-id="c2ed7-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c2ed7-124">**Type**</span></span>|<span data-ttu-id="c2ed7-125">**Valore**</span><span class="sxs-lookup"><span data-stu-id="c2ed7-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="c2ed7-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="c2ed7-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="c2ed7-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c2ed7-127">REG_DWORD</span></span>|<span data-ttu-id="c2ed7-128">0</span><span class="sxs-lookup"><span data-stu-id="c2ed7-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="c2ed7-129">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="c2ed7-129">Related articles</span></span>
[<span data-ttu-id="c2ed7-130">Accedere a Office 2013 con un secondo metodo di verifica</span><span class="sxs-lookup"><span data-stu-id="c2ed7-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[<span data-ttu-id="c2ed7-131">Outlook richiede la password e non usa l'autenticazione moderna per connettersi a Office 365</span><span class="sxs-lookup"><span data-stu-id="c2ed7-131">Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365</span></span>](https://docs.microsoft.com/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

  
