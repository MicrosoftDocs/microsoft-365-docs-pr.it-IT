---
title: Proteggere i PC e i Mac Windows 10 non gestiti
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteggersi da tentativi di phishing e altri attacchi con Microsoft 365 per le campagne.
ms.openlocfilehash: 7cb09d0cadcc70b96c5f1404defa5d0387947ca8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594797"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="388ca-103">Proteggere i PC e i Mac Windows 10 non gestiti</span><span class="sxs-lookup"><span data-stu-id="388ca-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="388ca-104">È possibile gestire Windows 10 PC e Mac eseguendo la registrazione in Microsoft Intune, che consente di verificare che siano integri e sicuri prima di accedere ai dati nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="388ca-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="388ca-105">Tuttavia, molte campagne e piccole aziende includono personale che porta i propri dispositivi (BYOD), che non verranno gestiti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="388ca-105">However, many campaigns and small businesses include staff who bring their own devices (byod), which will not be managed by the organization.</span></span> <span data-ttu-id="388ca-106">Per questi PC e Mac non gestiti, utilizzare questo articolo per verificare che siano configurate le funzionalità di sicurezza minime.</span><span class="sxs-lookup"><span data-stu-id="388ca-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="388ca-107">Proteggere un computer che esegue Windows 10 o un Mac</span><span class="sxs-lookup"><span data-stu-id="388ca-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="388ca-108">Se il PC o Mac Windows 10 non è gestito dall'organizzazione, assicurarsi di configurare queste funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="388ca-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10tabwindows10"></a>[<span data-ttu-id="388ca-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="388ca-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="388ca-110">**Attivazione della crittografia del dispositivo**</span><span class="sxs-lookup"><span data-stu-id="388ca-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="388ca-111">La crittografia del dispositivo è disponibile su una vasta gamma di dispositivi Windows e consente di proteggere i dati crittografati.</span><span class="sxs-lookup"><span data-stu-id="388ca-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="388ca-112">Se si attiva la crittografia del dispositivo, solo gli utenti autorizzati saranno in grado di accedere al dispositivo e ai dati.</span><span class="sxs-lookup"><span data-stu-id="388ca-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="388ca-113">Per istruzioni, vedere [abilitare la crittografia del dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .</span><span class="sxs-lookup"><span data-stu-id="388ca-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="388ca-114">Se la crittografia del dispositivo non è disponibile nel dispositivo, è possibile abilitare invece la [crittografia BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) standard.</span><span class="sxs-lookup"><span data-stu-id="388ca-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="388ca-115">(BitLocker non è disponibile in Windows 10 Home Edition).</span><span class="sxs-lookup"><span data-stu-id="388ca-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 


<span data-ttu-id="388ca-116">**Protezione del dispositivo con sicurezza di Windows**</span><span class="sxs-lookup"><span data-stu-id="388ca-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="388ca-117">Se si dispone di Windows 10, è possibile ottenere la protezione antivirus più recente con sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="388ca-117">If you have Windows 10, you’ll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="388ca-118">Quando si avvia Windows 10 per la prima volta, Windows Security è attivo e contribuisce attivamente alla protezione del PC tramite la ricerca di malware (software dannoso), virus e minacce alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="388ca-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="388ca-119">La sicurezza di Windows utilizza la protezione in tempo reale per analizzare tutto quello che scarichi o Esegui nel PC.</span><span class="sxs-lookup"><span data-stu-id="388ca-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="388ca-120">Windows Update Scarica automaticamente gli aggiornamenti per la sicurezza di Windows per mantenere il PC sicuro e proteggerlo dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="388ca-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="388ca-121">Se si dispone di una versione precedente di Windows e si utilizza Microsoft Security Essentials, è consigliabile passare alla sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="388ca-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it’s a good idea to move to Windows Security.</span></span> <span data-ttu-id="388ca-122">Per ulteriori informazioni, vedere [la guida alla protezione del dispositivo con Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span><span class="sxs-lookup"><span data-stu-id="388ca-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="388ca-123">**Attivazione di Windows Firewall**</span><span class="sxs-lookup"><span data-stu-id="388ca-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="388ca-124">È consigliabile eseguire sempre Windows Firewall anche se è stato attivato un altro firewall.</span><span class="sxs-lookup"><span data-stu-id="388ca-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="388ca-125">La disattivazione di Windows Firewall potrebbe rendere il dispositivo (e la rete, se ne esiste uno) più vulnerabile all'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="388ca-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="388ca-126">Per istruzioni, vedere [attivazione o disattivazione di Windows Firewall](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="388ca-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mactabmac"></a>[<span data-ttu-id="388ca-127">Mac</span><span class="sxs-lookup"><span data-stu-id="388ca-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="388ca-128">**Utilizzo di FileVault per crittografare il disco Mac**</span><span class="sxs-lookup"><span data-stu-id="388ca-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="388ca-129">La crittografia del disco protegge i dati quando i dispositivi vengono persi o rubati.</span><span class="sxs-lookup"><span data-stu-id="388ca-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="388ca-130">La crittografia Full-Disk di FileVault consente di impedire l'accesso non autorizzato alle informazioni sul disco di avvio.</span><span class="sxs-lookup"><span data-stu-id="388ca-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="388ca-131">Per istruzioni, vedere [utilizzare FileVault per crittografare il disco di avvio sul Mac](https://support.apple.com/HT204837) .</span><span class="sxs-lookup"><span data-stu-id="388ca-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="388ca-132">**Proteggi il tuo Mac da malware**</span><span class="sxs-lookup"><span data-stu-id="388ca-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="388ca-133">Microsoft consiglia di installare e utilizzare un software antivirus affidabile sul Mac.</span><span class="sxs-lookup"><span data-stu-id="388ca-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="388ca-134">Per un elenco delle opzioni, vedere l'articolo seguente: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="388ca-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="388ca-135">È inoltre possibile ridurre il rischio di malware utilizzando il software solo da origini affidabili.</span><span class="sxs-lookup"><span data-stu-id="388ca-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="388ca-136">Le impostazioni delle preferenze di sicurezza & privacy consentono di specificare le fonti del software installate sul Mac.</span><span class="sxs-lookup"><span data-stu-id="388ca-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="388ca-137">Per ulteriori informazioni, vedere [Protect your Mac from malware](https://support.apple.com/kb/PH25087).</span><span class="sxs-lookup"><span data-stu-id="388ca-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="388ca-138">**Attiva protezione firewall**</span><span class="sxs-lookup"><span data-stu-id="388ca-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="388ca-139">Utilizzare le impostazioni del firewall per proteggere il Mac da contatti indesiderati avviati da altri computer quando si è connessi a Internet o a una rete.</span><span class="sxs-lookup"><span data-stu-id="388ca-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you’re connected to the Internet or a network.</span></span> <span data-ttu-id="388ca-140">Senza questa protezione, il Mac potrebbe essere più vulnerabile all'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="388ca-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="388ca-141">Per istruzioni, vedere [informazioni sul firewall dell'applicazione](https://support.apple.com/HT201642) .</span><span class="sxs-lookup"><span data-stu-id="388ca-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
