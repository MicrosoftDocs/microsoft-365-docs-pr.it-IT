---
title: Proteggere i PC Windows 10 e Mac non gestiti
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteggi i dispositivi non gestiti o bring-your-own (BYOD) con Microsoft 365.
ms.openlocfilehash: 40e94e2f961ab34827de4ce5e43e100af53a7340
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227500"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="3301a-103">Proteggere i PC Windows 10 e Mac non gestiti</span><span class="sxs-lookup"><span data-stu-id="3301a-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="3301a-104">Puoi gestire Windows 10 PC e Mac registrandoli in Microsoft Intune, che ti consente di assicurarti che siano integri e sicuri prima di accedere ai dati nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="3301a-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="3301a-105">Tuttavia, molte campagne e piccole aziende includono personale che porta i propri dispositivi (BYOD), che non verranno gestiti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3301a-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="3301a-106">Per questi PC e Mac non gestiti, usa questo articolo per assicurarti che le funzionalità di sicurezza minime siano configurate.</span><span class="sxs-lookup"><span data-stu-id="3301a-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="3301a-107">Proteggere un computer che esegue Windows 10 o un Mac</span><span class="sxs-lookup"><span data-stu-id="3301a-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="3301a-108">Se il Windows 10 PC o Mac non è gestito dall'organizzazione, assicurati di configurare queste funzionalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3301a-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="3301a-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3301a-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="3301a-110">**Attivare la crittografia del dispositivo**</span><span class="sxs-lookup"><span data-stu-id="3301a-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="3301a-111">La crittografia dei dispositivi è disponibile in un'ampia gamma di Windows e consente di proteggere i dati crittografando i dati.</span><span class="sxs-lookup"><span data-stu-id="3301a-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="3301a-112">Se si attiva la crittografia del dispositivo, solo gli utenti autorizzati potranno accedere al dispositivo e ai dati.</span><span class="sxs-lookup"><span data-stu-id="3301a-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="3301a-113">Per [istruzioni, vedi Attivare la crittografia](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3301a-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="3301a-114">Se la crittografia del dispositivo non è disponibile nel dispositivo, puoi attivare la crittografia [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) standard.</span><span class="sxs-lookup"><span data-stu-id="3301a-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="3301a-115">BitLocker non è disponibile nell'Windows 10 Home edizione.</span><span class="sxs-lookup"><span data-stu-id="3301a-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="3301a-116">**Proteggere il dispositivo con Sicurezza di Windows**</span><span class="sxs-lookup"><span data-stu-id="3301a-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="3301a-117">Se si dispone Windows 10, si otterrà la protezione antivirus più recente con Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="3301a-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="3301a-118">Quando si avvia Windows 10 per la prima volta, Sicurezza di Windows è attivo e aiuta attivamente a proteggere il PC mediante la ricerca di malware (software dannoso), virus e minacce alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3301a-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="3301a-119">Sicurezza di Windows usa la protezione in tempo reale per analizzare tutto ciò che scari clici o esegui sul PC.</span><span class="sxs-lookup"><span data-stu-id="3301a-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="3301a-120">Windows Update scarica automaticamente gli aggiornamenti per Sicurezza di Windows per proteggere il computer e difenderlo dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="3301a-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="3301a-121">Se si dispone di una versione precedente di Windows e si utilizza Microsoft Security Essentials, è buona idea passare a Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="3301a-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="3301a-122">Per altre informazioni, vedi [proteggere il dispositivo con Sicurezza di Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span><span class="sxs-lookup"><span data-stu-id="3301a-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="3301a-123">**Attivare Windows firewall**</span><span class="sxs-lookup"><span data-stu-id="3301a-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="3301a-124">Dovresti sempre eseguire Windows Firewall anche se hai un altro firewall attivato.</span><span class="sxs-lookup"><span data-stu-id="3301a-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="3301a-125">La disattivazione Windows firewall potrebbe rendere il dispositivo (e la rete, se ne hai uno) più vulnerabile agli accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="3301a-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="3301a-126">Per [istruzioni, Windows attivare o disattivare](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) firewall.</span><span class="sxs-lookup"><span data-stu-id="3301a-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions.</span></span>

## <a name="mac"></a>[<span data-ttu-id="3301a-127">Mac</span><span class="sxs-lookup"><span data-stu-id="3301a-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="3301a-128">**Usare FileVault per crittografare il disco Mac**</span><span class="sxs-lookup"><span data-stu-id="3301a-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="3301a-129">La crittografia del disco protegge i dati quando i dispositivi vengono persi o rubati.</span><span class="sxs-lookup"><span data-stu-id="3301a-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="3301a-130">La crittografia su disco completo di FileVault consente di impedire l'accesso non autorizzato alle informazioni sul disco di avvio.</span><span class="sxs-lookup"><span data-stu-id="3301a-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="3301a-131">Per [istruzioni, vedi usare FileVault per crittografare il disco di avvio sul Mac.](https://support.apple.com/HT204837)</span><span class="sxs-lookup"><span data-stu-id="3301a-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="3301a-132">**Proteggere il mac da malware**</span><span class="sxs-lookup"><span data-stu-id="3301a-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="3301a-133">Microsoft consiglia di installare e usare software antivirus affidabile sul Mac.</span><span class="sxs-lookup"><span data-stu-id="3301a-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="3301a-134">Vedi l'articolo seguente per un elenco di scelte: [Best Mac antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="3301a-134">See the following article for a list of choices: [Best Mac antivirus 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="3301a-135">È inoltre possibile ridurre il rischio di malware utilizzando software solo da fonti affidabili.</span><span class="sxs-lookup"><span data-stu-id="3301a-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="3301a-136">Le impostazioni in Impostazioni & preferenze privacy consentono di specificare le origini del software installato nel Mac.</span><span class="sxs-lookup"><span data-stu-id="3301a-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="3301a-137">Per altre informazioni, vedi [Proteggere il Mac da malware.](https://support.apple.com/kb/PH25087)</span><span class="sxs-lookup"><span data-stu-id="3301a-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="3301a-138">**Attivare la protezione firewall**</span><span class="sxs-lookup"><span data-stu-id="3301a-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="3301a-139">Usa le impostazioni del firewall per proteggere il Mac da contatti indesiderati avviati da altri computer quando sei connesso a Internet o a una rete.</span><span class="sxs-lookup"><span data-stu-id="3301a-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="3301a-140">Senza questa protezione, il Mac potrebbe essere più vulnerabile agli accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="3301a-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="3301a-141">Per [istruzioni, vedere Firewall applicazioni.](https://support.apple.com/HT201642)</span><span class="sxs-lookup"><span data-stu-id="3301a-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
