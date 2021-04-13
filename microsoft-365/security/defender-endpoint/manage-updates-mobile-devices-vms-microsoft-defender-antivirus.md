---
title: Definire il modo in cui i dispositivi mobili vengono aggiornati da Microsoft Defender Antivirus
description: Gestire la modalità di aggiornamento dei dispositivi mobili, ad esempio i portatili, con gli aggiornamenti di protezione di Microsoft Defender Antivirus.
keywords: aggiornamenti, protezione, pianificazione degli aggiornamenti, batteria, dispositivo mobile, portatile, blocco appunti, consenso esplicito, microsoft update, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f67330e1ccd7361c3982b76a6ab8754db23bd110
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690396"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="25dc2-104">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali</span><span class="sxs-lookup"><span data-stu-id="25dc2-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25dc2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="25dc2-105">**Applies to:**</span></span>

- [<span data-ttu-id="25dc2-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="25dc2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="25dc2-107">I dispositivi mobili e le macchine virtuali potrebbero richiedere una configurazione maggiore per garantire che le prestazioni non siano influenzate dagli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="25dc2-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="25dc2-108">Esistono due impostazioni utili per questi dispositivi:</span><span class="sxs-lookup"><span data-stu-id="25dc2-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="25dc2-109">Acconsentire esplicitamente a Microsoft Update nei computer mobili senza una connessione WSUS</span><span class="sxs-lookup"><span data-stu-id="25dc2-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="25dc2-110">Impedisci aggiornamenti di Intelligence per la sicurezza durante l'esecuzione con alimentazione a batteria</span><span class="sxs-lookup"><span data-stu-id="25dc2-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="25dc2-111">Gli articoli seguenti possono essere utili anche in queste situazioni:</span><span class="sxs-lookup"><span data-stu-id="25dc2-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="25dc2-112">Configurazione delle analisi pianificate e di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="25dc2-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="25dc2-113">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="25dc2-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="25dc2-114">Guida alla distribuzione di Microsoft Defender Antivirus in un ambiente VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="25dc2-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="25dc2-115">Acconsentire esplicitamente a Microsoft Update nei computer mobili senza una connessione WSUS</span><span class="sxs-lookup"><span data-stu-id="25dc2-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="25dc2-116">Puoi usare Microsoft Update per mantenere aggiornata l'intelligence per la sicurezza nei dispositivi mobili che eseguono Microsoft Defender Antivirus quando non sono connessi alla rete aziendale o non hanno altrimenti una connessione WSUS.</span><span class="sxs-lookup"><span data-stu-id="25dc2-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="25dc2-117">Ciò significa che gli aggiornamenti della protezione possono essere recapitati ai dispositivi (tramite Microsoft Update) anche se WSUS è stato impostato per sostituire Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="25dc2-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="25dc2-118">Puoi acconsentire esplicitamente a Microsoft Update nel dispositivo mobile in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="25dc2-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="25dc2-119">Modificare l'impostazione con Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="25dc2-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="25dc2-120">Utilizzare un VBScript per creare uno script, quindi eseguirlo in ogni computer della rete.</span><span class="sxs-lookup"><span data-stu-id="25dc2-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="25dc2-121">Acconsentire manualmente a tutti i computer della rete **tramite** il menu Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="25dc2-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="25dc2-122">Usare Criteri di gruppo per acconsentire esplicitamente a Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="25dc2-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="25dc2-123">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="25dc2-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="25dc2-124">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="25dc2-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="25dc2-125">Selezionare **Criteri** e **modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="25dc2-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="25dc2-126">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **Signature Updates**.</span><span class="sxs-lookup"><span data-stu-id="25dc2-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="25dc2-127">Impostare **Consenti aggiornamenti di intelligence per la sicurezza da Microsoft Update** su **Abilitato** e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="25dc2-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="25dc2-128">Usare un VBScript per acconsentire esplicitamente a Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="25dc2-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="25dc2-129">Seguire le istruzioni nell'articolo MSDN [Acconsentire esplicitamente a Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) per creare VBScript.</span><span class="sxs-lookup"><span data-stu-id="25dc2-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="25dc2-130">Eseguire vbScript creato in ogni computer della rete.</span><span class="sxs-lookup"><span data-stu-id="25dc2-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="25dc2-131">Acconsentire manualmente a Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="25dc2-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="25dc2-132">Apri **Windows Update** in Update & **di** sicurezza nel computer in cui vuoi acconsentire esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="25dc2-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="25dc2-133">Selezionare **Opzioni** avanzate.</span><span class="sxs-lookup"><span data-stu-id="25dc2-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="25dc2-134">Seleziona la casella di controllo **Dammi aggiornamenti per altri prodotti Microsoft quando aggiorno Windows.**</span><span class="sxs-lookup"><span data-stu-id="25dc2-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="25dc2-135">Impedisci aggiornamenti di Intelligence per la sicurezza durante l'esecuzione con alimentazione a batteria</span><span class="sxs-lookup"><span data-stu-id="25dc2-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="25dc2-136">Puoi configurare Microsoft Defender Antivirus per scaricare gli aggiornamenti della protezione solo quando il PC è connesso a una fonte di alimentazione cablata.</span><span class="sxs-lookup"><span data-stu-id="25dc2-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="25dc2-137">Utilizzare Criteri di gruppo per impedire gli aggiornamenti delle funzionalità di intelligence per la sicurezza nell'alimentazione a batteria</span><span class="sxs-lookup"><span data-stu-id="25dc2-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="25dc2-138">Nel computer di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, scegliere l'oggetto Criteri di gruppo che si desidera configurare e aprirlo per la modifica.</span><span class="sxs-lookup"><span data-stu-id="25dc2-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="25dc2-139">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="25dc2-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="25dc2-140">Selezionare **Criteri** e **modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="25dc2-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="25dc2-141">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender Antivirus Signature Updates e quindi impostare Allow security intelligence updates when running on battery  >    >   **power** su **Disabled**.</span><span class="sxs-lookup"><span data-stu-id="25dc2-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="25dc2-142">Infine scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="25dc2-142">Then select **OK**.</span></span> 

<span data-ttu-id="25dc2-143">Questa azione impedisce il download degli aggiornamenti di protezione quando il PC è alimentato a batteria.</span><span class="sxs-lookup"><span data-stu-id="25dc2-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="25dc2-144">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="25dc2-144">Related articles</span></span>

- [<span data-ttu-id="25dc2-145">Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base</span><span class="sxs-lookup"><span data-stu-id="25dc2-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="25dc2-146">Aggiornare e gestire Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="25dc2-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)