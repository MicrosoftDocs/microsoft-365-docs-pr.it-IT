---
title: Esaminare le minacce rilevate e intervenire
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
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
search.appverid: MET150
description: Informazioni su come esaminare e gestire le minacce rilevate da Microsoft Defender antivirus nei dispositivi Windows 10.
ms.openlocfilehash: 21830b91bfbb88fdd5d5139ee07c4dfb35f5b875
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376703"
---
# <a name="review-detected-threats-and-take-action"></a><span data-ttu-id="2c823-103">Esaminare le minacce rilevate e intervenire</span><span class="sxs-lookup"><span data-stu-id="2c823-103">Review detected threats and take action</span></span>

<span data-ttu-id="2c823-104">Non appena viene rilevato un file o un software dannoso, Microsoft Defender antivirus lo blocca e ne impedisce l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2c823-104">As soon as a malicious file or software is detected, Microsoft Defender Antivirus blocks it and prevents it from running.</span></span> <span data-ttu-id="2c823-105">E con la protezione fornita dal cloud attivata, le minacce appena rilevate vengono aggiunte al motore antivirus e antimalware in modo che anche gli altri dispositivi e gli altri utenti siano protetti.</span><span class="sxs-lookup"><span data-stu-id="2c823-105">And with cloud-delivered protection turned on, newly detected threats are added to the antivirus and antimalware engine so that your other devices and users are protected, as well.</span></span>

<span data-ttu-id="2c823-106">Microsoft Defender Antivirus rileva e protegge i tipi di minacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c823-106">Microsoft Defender Antivirus detects and protects against the following kinds of threats:</span></span>

- <span data-ttu-id="2c823-107">Virus, malware e minacce basate sul Web sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="2c823-107">Viruses, malware, and web-based threats on devices</span></span>
- <span data-ttu-id="2c823-108">Tentativi di phishing</span><span class="sxs-lookup"><span data-stu-id="2c823-108">Phishing attempts</span></span>
- <span data-ttu-id="2c823-109">Tentativi di furto dei dati</span><span class="sxs-lookup"><span data-stu-id="2c823-109">Data theft attempts</span></span>

<span data-ttu-id="2c823-110">Come un professionista IT/amministratore, è possibile visualizzare le informazioni sui rilevamenti di minacce nei [dispositivi Windows 10 registrati in Intune](/mem/intune/enrollment/device-enrollment) nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c823-110">As an IT professional/admin, you can view information about threat detections across [Windows 10 devices that are enrolled in Intune](/mem/intune/enrollment/device-enrollment) in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2c823-111">Verranno visualizzate informazioni di riepilogo, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2c823-111">You'll see summary information, such as:</span></span>

- <span data-ttu-id="2c823-112">Il numero di dispositivi necessari per la protezione antivirus</span><span class="sxs-lookup"><span data-stu-id="2c823-112">How many devices need antivirus protection</span></span>
- <span data-ttu-id="2c823-113">Numero di dispositivi non conformi ai criteri di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2c823-113">How many devices are not in compliance with security policies</span></span>
- <span data-ttu-id="2c823-114">Quante minacce sono attualmente attive, attenuate o risolte</span><span class="sxs-lookup"><span data-stu-id="2c823-114">How many threats are currently active, mitigated, or resolved</span></span>

<span data-ttu-id="2c823-115">Sono disponibili diverse opzioni per visualizzare informazioni specifiche sui dispositivi e sui rilevamenti di minacce:</span><span class="sxs-lookup"><span data-stu-id="2c823-115">You have several options to view specific information about threat detections and devices:</span></span>

- <span data-ttu-id="2c823-116">La pagina **dispositivi attivi** nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2c823-116">The **Active devices** page in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="2c823-117">Vedere [gestire i rilevamenti di minacce nella pagina dispositivi attivi](#manage-threat-detections-on-the-active-devices-page) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2c823-117">See [Manage threat detections on the Active devices page](#manage-threat-detections-on-the-active-devices-page) in this article.</span></span>
- <span data-ttu-id="2c823-118">La pagina **minacce attive** nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2c823-118">The **Active threats** page in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="2c823-119">Vedere [gestire i rilevamenti di minacce nella pagina minacce attive](#manage-threat-detections-on-the-active-threats-page) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2c823-119">See [Manage threat detections on the Active threats page](#manage-threat-detections-on-the-active-threats-page) in this article.</span></span>
- <span data-ttu-id="2c823-120">La pagina **antivirus** in <a href="https://endpoint.microsoft.com" target="_blank">Microsoft Endpoint Manager</a>.</span><span class="sxs-lookup"><span data-stu-id="2c823-120">The **Antivirus** page in <a href="https://endpoint.microsoft.com" target="_blank">Microsoft Endpoint Manager</a>.</span></span> <span data-ttu-id="2c823-121">Vedere [gestire i rilevamenti di minacce in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2c823-121">See [Manage threat detections in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) in this article.</span></span>

<span data-ttu-id="2c823-122">Per ulteriori informazioni, vedere [minacce rilevate da Microsoft Defender Antivirus](threats-detected-defender-av.md).</span><span class="sxs-lookup"><span data-stu-id="2c823-122">To learn more, see [Threats detected by Microsoft Defender Antivirus](threats-detected-defender-av.md).</span></span>

## <a name="manage-threat-detections-on-the-active-devices-page"></a><span data-ttu-id="2c823-123">Gestire i rilevamenti di minacce nella pagina **dispositivi attivi**</span><span class="sxs-lookup"><span data-stu-id="2c823-123">Manage threat detections on the **Active devices** page</span></span>

<span data-ttu-id="2c823-124">La procedura seguente si applica ai clienti che dispongono di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2c823-124">The following procedure applies to customers who have Microsoft 365 Business Premium.</span></span>

1. <span data-ttu-id="2c823-125">Accedere all'interfaccia di amministrazione di Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2c823-125">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> and sign in.</span></span>

2. <span data-ttu-id="2c823-126">Nella pagina navigazione selezionare **dispositivi**  >  **attivi**.</span><span class="sxs-lookup"><span data-stu-id="2c823-126">In the navigation page, select **Devices** > **Active devices**.</span></span> <span data-ttu-id="2c823-127">Verrà visualizzato un elenco di dispositivi attivi e dettagli, ad esempio lo stato di protezione, lo stato di protezione antivirus (AV) e il numero di minacce attive rilevate.</span><span class="sxs-lookup"><span data-stu-id="2c823-127">You'll see a list of active devices and details, such as protection status, antivirus (AV) protection state, and the number of active threats detected.</span></span>

3. <span data-ttu-id="2c823-128">Selezionare un dispositivo per visualizzare ulteriori dettagli sul dispositivo e sulle azioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="2c823-128">Select a device to view more details about that device and available actions.</span></span> <span data-ttu-id="2c823-129">Viene aperto un riquadro a comparsa con suggerimenti e azioni disponibili, ad esempio **criteri di aggiornamento**, **aggiornamento antivirus**, **esecuzione di analisi rapida**, **esecuzione dell'analisi completa** e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="2c823-129">A flyout opens with recommendations and available actions, such as **Update policy**, **Update antivirus**, **Run quick scan**, **Run full scan**, and more.</span></span>

## <a name="manage-threat-detections-on-the-active-threats-page"></a><span data-ttu-id="2c823-130">Gestire i rilevamenti di minacce nella pagina **minacce attive**</span><span class="sxs-lookup"><span data-stu-id="2c823-130">Manage threat detections on the **Active threats** page</span></span>

<span data-ttu-id="2c823-131">La procedura seguente si applica ai clienti che dispongono di Microsoft 365 business.</span><span class="sxs-lookup"><span data-stu-id="2c823-131">The following procedure applies to customers who have Microsoft 365 Business.</span></span> <span data-ttu-id="2c823-132">I [dispositivi Windows 10 devono essere protetti](/microsoft-365/business/secure-win-10-pcs) e [registrati in Intune](/mem/intune/enrollment/windows-enrollment-methods).</span><span class="sxs-lookup"><span data-stu-id="2c823-132">[Windows 10 devices must be secured](/microsoft-365/business/secure-win-10-pcs) and [enrolled in Intune](/mem/intune/enrollment/windows-enrollment-methods).</span></span>

> [!NOTE]
> <span data-ttu-id="2c823-133">La pagina **Microsoft Defender Antivirus** e le **minacce attive** vengono distribuite in fasi, pertanto non è possibile accedervi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="2c823-133">The **Microsoft Defender Antivirus** card and **Active threats** page are being rolled out in phases, so you may not have immediate access to them.</span></span>

1. <span data-ttu-id="2c823-134">Accedere all'interfaccia di amministrazione di Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2c823-134">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> and sign in.</span></span>

2. <span data-ttu-id="2c823-135">Nella scheda **Microsoft Defender Antivirus** selezionare **Visualizza minacce attive**.</span><span class="sxs-lookup"><span data-stu-id="2c823-135">On the **Microsoft Defender Antivirus** card, select **View active threats**.</span></span> <span data-ttu-id="2c823-136">In alternativa, nel riquadro di spostamento selezionare **integrità**  >  **Minacce & antivirus**.)</span><span class="sxs-lookup"><span data-stu-id="2c823-136">(Alternatively, in the navigation pane, select **Health** > **Threats & antivirus**.)</span></span>

3. <span data-ttu-id="2c823-137">Nella pagina **minacce attive** selezionare una minaccia rilevata per ulteriori informazioni su di esso.</span><span class="sxs-lookup"><span data-stu-id="2c823-137">On the **Active threats** page, select a detected threat to learn more about it.</span></span> <span data-ttu-id="2c823-138">Verrà aperto un riquadro a comparsa con informazioni dettagliate su tale minaccia, inclusi i dispositivi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="2c823-138">A flyout opens with details about that threat, including which devices are affected.</span></span>

4. <span data-ttu-id="2c823-139">Nel riquadro a comparsa, selezionare un dispositivo per visualizzare le azioni disponibili, ad esempio **criteri di aggiornamento**, **aggiornamento antivirus**, **esecuzione di analisi rapida** e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="2c823-139">On the flyout, select a device to view available actions, such as **Update policy**, **Update antivirus**, **Run quick scan**, and more.</span></span>

## <a name="actions-you-can-take"></a><span data-ttu-id="2c823-140">Azioni che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="2c823-140">Actions you can take</span></span>

<span data-ttu-id="2c823-141">Quando si visualizzano i dettagli relativi a minacce o dispositivi specifici, verranno visualizzati suggerimenti e una o più azioni che è possibile eseguire.</span><span class="sxs-lookup"><span data-stu-id="2c823-141">When you view details about specific threats or devices, you’ll see recommendations and one or more actions you can take.</span></span> <span data-ttu-id="2c823-142">Nella tabella seguente vengono descritte le azioni che è possibile visualizzare.</span><span class="sxs-lookup"><span data-stu-id="2c823-142">The following table describes actions that you might see.</span></span><br><br>

| <span data-ttu-id="2c823-143">Azione</span><span class="sxs-lookup"><span data-stu-id="2c823-143">Action</span></span> | <span data-ttu-id="2c823-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c823-144">Description</span></span> |
|--|--|
| <span data-ttu-id="2c823-145">Configurare la protezione</span><span class="sxs-lookup"><span data-stu-id="2c823-145">Configure protection</span></span> | <span data-ttu-id="2c823-146">I criteri di protezione dalle minacce devono essere configurati.</span><span class="sxs-lookup"><span data-stu-id="2c823-146">Your threat protection policies need to be configured.</span></span> <span data-ttu-id="2c823-147">Selezionare il collegamento per passare alla pagina di configurazione del criterio.</span><span class="sxs-lookup"><span data-stu-id="2c823-147">Select the link to go to your policy configuration page.</span></span><br><br><span data-ttu-id="2c823-148">Hai bisogno di assistenza?</span><span class="sxs-lookup"><span data-stu-id="2c823-148">Need help?</span></span> <span data-ttu-id="2c823-149">Vedere [gestire la sicurezza dei dispositivi con i criteri di sicurezza di endpoint in Microsoft Intune](/mem/intune/protect/endpoint-security-policy).</span><span class="sxs-lookup"><span data-stu-id="2c823-149">See [Manage device security with endpoint security policies in Microsoft Intune](/mem/intune/protect/endpoint-security-policy).</span></span> |
| <span data-ttu-id="2c823-150">Criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2c823-150">Update policy</span></span> | <span data-ttu-id="2c823-151">I criteri di protezione antivirus e in tempo reale devono essere aggiornati o configurati.</span><span class="sxs-lookup"><span data-stu-id="2c823-151">Your antivirus and real-time protection policies need to be updated or configured.</span></span> <span data-ttu-id="2c823-152">Selezionare il collegamento per passare alla pagina Configurazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="2c823-152">Select the link to go to the policy configuration page.</span></span><br><br><span data-ttu-id="2c823-153">Hai bisogno di assistenza?</span><span class="sxs-lookup"><span data-stu-id="2c823-153">Need help?</span></span> <span data-ttu-id="2c823-154">Vedere [gestire la sicurezza dei dispositivi con i criteri di sicurezza di endpoint in Microsoft Intune](/mem/intune/protect/endpoint-security-policy).</span><span class="sxs-lookup"><span data-stu-id="2c823-154">See [Manage device security with endpoint security policies in Microsoft Intune](/mem/intune/protect/endpoint-security-policy).</span></span> |
| <span data-ttu-id="2c823-155">Eseguire un'analisi rapida</span><span class="sxs-lookup"><span data-stu-id="2c823-155">Run quick scan</span></span> | <span data-ttu-id="2c823-156">Avvia un'analisi antivirus rapida sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware, ad esempio le chiavi del registro di sistema e le cartelle di avvio di Windows note.</span><span class="sxs-lookup"><span data-stu-id="2c823-156">Starts a quick antivirus scan on the device, focusing on common locations where malware might be registered, such as registry keys and known Windows startup folders.</span></span> |
| <span data-ttu-id="2c823-157">Eseguire l'analisi completa</span><span class="sxs-lookup"><span data-stu-id="2c823-157">Run full scan</span></span> | <span data-ttu-id="2c823-158">Avvia un'analisi antivirus completa sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware e includendo tutti i file e le cartelle presenti nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c823-158">Starts a full antivirus scan on the device, focusing on common locations where malware might be registered, and including every file and folder on the device.</span></span> <span data-ttu-id="2c823-159">I risultati vengono inviati a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="2c823-159">Results are sent to [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span> |
| <span data-ttu-id="2c823-160">Aggiornamento antivirus</span><span class="sxs-lookup"><span data-stu-id="2c823-160">Update antivirus</span></span> | <span data-ttu-id="2c823-161">Richiede il dispositivo per ottenere [gli aggiornamenti di sicurezza intelligence](https://go.microsoft.com/fwlink/?linkid=2149926) per la protezione antivirus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="2c823-161">Requires the device to get [security intelligence updates](https://go.microsoft.com/fwlink/?linkid=2149926) for antivirus and antimalware protection.</span></span> |
| <span data-ttu-id="2c823-162">Riavvia il dispositivo</span><span class="sxs-lookup"><span data-stu-id="2c823-162">Restart device</span></span> | <span data-ttu-id="2c823-163">Forza il riavvio di un dispositivo Windows 10 entro cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="2c823-163">Forces a Windows 10 device to restart within five minutes.</span></span><br><br><span data-ttu-id="2c823-164">**Importante:** Il proprietario o l'utente del dispositivo non viene automaticamente informato del riavvio e potrebbe perdere il lavoro non salvato.</span><span class="sxs-lookup"><span data-stu-id="2c823-164">**IMPORTANT:** The device owner or user is not automatically notified of the restart and could lose unsaved work.</span></span> |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a><span data-ttu-id="2c823-165">Gestire i rilevamenti di minacce in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2c823-165">Manage threat detections in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="2c823-166">È possibile utilizzare Microsoft Endpoint Manager per gestire i rilevamenti di minacce.</span><span class="sxs-lookup"><span data-stu-id="2c823-166">You can use Microsoft Endpoint Manager to manage threat detections.</span></span> <span data-ttu-id="2c823-167">I dispositivi Windows 10 devono essere [registrati in Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte di Microsoft Endpoint Manager).</span><span class="sxs-lookup"><span data-stu-id="2c823-167">Windows 10 devices must be [enrolled in Intune](/mem/intune/enrollment/windows-enrollment-methods) (part of Microsoft Endpoint Manager).</span></span>

1. <span data-ttu-id="2c823-168">Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2c823-168">Go to the Microsoft Endpoint Manager admin center at <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> and sign in.</span></span>

2. <span data-ttu-id="2c823-169">Nel riquadro di spostamento selezionare **Endpoint Security**.</span><span class="sxs-lookup"><span data-stu-id="2c823-169">In the navigation pane, select **Endpoint security**.</span></span>

3. <span data-ttu-id="2c823-170">In **Gestisci** selezionare **antivirus**.</span><span class="sxs-lookup"><span data-stu-id="2c823-170">Under **Manage**, select **Antivirus**.</span></span> <span data-ttu-id="2c823-171">Verranno visualizzate diverse schede, ad esempio **Riepilogo**, **endpoint non integri di Windows 10** e **malware rilevati da Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="2c823-171">You'll see several tabs, such as **Summary**, **Windows 10 unhealthy endpoints**, and **Windows 10 detected malware**.</span></span>

4. <span data-ttu-id="2c823-172">Rivedere le informazioni sulle schede disponibili e quindi eseguire tutte le operazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="2c823-172">Review the information on the available tabs, and then take any needed action.</span></span>

<span data-ttu-id="2c823-173">Si supponga, ad esempio, che i dispositivi siano elencati nella scheda **malware rilevato di Windows 10** . Quando si seleziona un dispositivo, sono disponibili determinate azioni, ad esempio **riavvio**, **analisi rapida**, **analisi completa**, **sincronizzazione** o **aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="2c823-173">For example, suppose that devices are listed on the **Windows 10 detected malware** tab. When you select a device, you'll have certain actions available, such as **Restart**, **Quick Scan**, **Full Scan**, **Sync**, or **Update signatures**.</span></span> <span data-ttu-id="2c823-174">Selezionare un'azione per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c823-174">Select an action for that device.</span></span>

<span data-ttu-id="2c823-175">Nella tabella seguente vengono descritte le azioni che è possibile visualizzare in Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="2c823-175">The following table describes the actions you might see in Microsoft Endpoint Manager.</span></span><br><br>

| <span data-ttu-id="2c823-176">Azione</span><span class="sxs-lookup"><span data-stu-id="2c823-176">Action</span></span> | <span data-ttu-id="2c823-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c823-177">Description</span></span> |
|--|--|
| <span data-ttu-id="2c823-178">Riavvia</span><span class="sxs-lookup"><span data-stu-id="2c823-178">Restart</span></span> | <span data-ttu-id="2c823-179">Forza il riavvio di un dispositivo Windows 10 entro cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="2c823-179">Forces a Windows 10 device to restart within five minutes.</span></span><br><br><span data-ttu-id="2c823-180">**Importante:** Il proprietario o l'utente del dispositivo non viene automaticamente informato del riavvio e potrebbe perdere il lavoro non salvato.</span><span class="sxs-lookup"><span data-stu-id="2c823-180">**IMPORTANT:** The device owner or user is not automatically notified of the restart and could lose unsaved work.</span></span> |
| <span data-ttu-id="2c823-181">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="2c823-181">Quick Scan</span></span> | <span data-ttu-id="2c823-182">Avvia un'analisi antivirus rapida sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware, ad esempio le chiavi del registro di sistema e le cartelle di avvio di Windows note.</span><span class="sxs-lookup"><span data-stu-id="2c823-182">Starts a quick antivirus scan on the device, focusing on common locations where malware might be registered, such as registry keys and known Windows startup folders.</span></span> <span data-ttu-id="2c823-183">I risultati vengono inviati a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="2c823-183">Results are sent to [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span> |
| <span data-ttu-id="2c823-184">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="2c823-184">Full Scan</span></span> | <span data-ttu-id="2c823-185">Avvia un'analisi antivirus completa sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware e includendo tutti i file e le cartelle presenti nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c823-185">Starts a full antivirus scan on the device, focusing on common locations where malware might be registered, and including every file and folder on the device.</span></span> <span data-ttu-id="2c823-186">I risultati vengono inviati a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="2c823-186">Results are sent to [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span> |
| <span data-ttu-id="2c823-187">Sincronizza</span><span class="sxs-lookup"><span data-stu-id="2c823-187">Sync</span></span> | <span data-ttu-id="2c823-188">Richiede l'archiviazione di un dispositivo con Intune (parte di Microsoft Endpoint Manager).</span><span class="sxs-lookup"><span data-stu-id="2c823-188">Requires a device to check in with Intune (part of Microsoft Endpoint Manager).</span></span> <span data-ttu-id="2c823-189">Quando il dispositivo esegue la verifica, il dispositivo riceve eventuali azioni o criteri in sospeso assegnati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c823-189">When the device checks in, the device receives any pending actions or policies assigned to the device.</span></span> |
| <span data-ttu-id="2c823-190">Aggiornare le firme</span><span class="sxs-lookup"><span data-stu-id="2c823-190">Update signatures</span></span> | <span data-ttu-id="2c823-191">Richiede il dispositivo per ottenere [gli aggiornamenti di sicurezza intelligence](https://go.microsoft.com/fwlink/?linkid=2149926) per la protezione antivirus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="2c823-191">Requires the device to get [security intelligence updates](https://go.microsoft.com/fwlink/?linkid=2149926) for antivirus and antimalware protection.</span></span> |

> [!TIP]
> <span data-ttu-id="2c823-192">Per ulteriori informazioni, vedere [Remote actions for Devices](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).</span><span class="sxs-lookup"><span data-stu-id="2c823-192">For more information, see [Remote actions for devices](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).</span></span>

## <a name="how-to-submit-a-file-for-malware-analysis"></a><span data-ttu-id="2c823-193">Come inviare un file per l'analisi antimalware</span><span class="sxs-lookup"><span data-stu-id="2c823-193">How to submit a file for malware analysis</span></span>

<span data-ttu-id="2c823-194">Se si dispone di un file che si ritiene mancato o classificato erroneamente come malware, è possibile inviare tale file a Microsoft per l'analisi antimalware.</span><span class="sxs-lookup"><span data-stu-id="2c823-194">If you have a file that you think was missed or wrongly classified as malware, you can submit that file to Microsoft for malware analysis.</span></span> <span data-ttu-id="2c823-195">Gli utenti e gli amministratori IT possono inviare un file per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="2c823-195">Users and IT admins can submit a file for analysis.</span></span> <span data-ttu-id="2c823-196">Visitare [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .</span><span class="sxs-lookup"><span data-stu-id="2c823-196">Visit [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission).</span></span>