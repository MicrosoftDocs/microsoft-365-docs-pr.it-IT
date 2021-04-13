---
title: Configurare le notifiche di Microsoft Defender Antivirus
description: Scopri come configurare e personalizzare le notifiche standard e aggiuntive di Microsoft Defender Antivirus sugli endpoint.
keywords: notifiche, defender, antivirus, endpoint, gestione, amministratore
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82ca54e383943f4994f9647ce1e110a6621b1327
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691414"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="c8798-104">Configurare le notifiche visualizzate sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="c8798-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c8798-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c8798-105">**Applies to:**</span></span>

- [<span data-ttu-id="c8798-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c8798-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c8798-107">In Windows 10, le notifiche delle applicazioni relative al rilevamento e alla correzione di malware sono più affidabili, coerenti e concise.</span><span class="sxs-lookup"><span data-stu-id="c8798-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="c8798-108">Le notifiche vengono visualizzate sugli endpoint quando vengono completate analisi attivate manualmente e pianificate e vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="c8798-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="c8798-109">Queste notifiche vengono visualizzate anche nel **Centro notifiche** e un riepilogo delle analisi e dei rilevamenti delle minacce viene visualizzato a intervalli di tempo regolari.</span><span class="sxs-lookup"><span data-stu-id="c8798-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="c8798-110">Puoi anche configurare la modalità di visualizzazione delle notifiche standard sugli endpoint, ad esempio le notifiche per il riavvio o quando è stata rilevata e corretti una minaccia.</span><span class="sxs-lookup"><span data-stu-id="c8798-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="c8798-111">Configurare le notifiche aggiuntive visualizzate sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="c8798-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="c8798-112">Puoi configurare la visualizzazione di notifiche aggiuntive, ad esempio riepiloghi di rilevamento delle minacce recenti, [nell'app Sicurezza](microsoft-defender-security-center-antivirus.md) di Windows e con Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8798-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c8798-113">In Windows 10 versione 1607  la funzionalità era denominata Notifiche avanzate e poteva essere configurata in Impostazioni di **Windows** Aggiornamento &  >  **sicurezza**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="c8798-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="c8798-114">Nelle impostazioni di Criteri di gruppo in tutte le versioni di Windows 10, si chiama **Notifiche avanzate.**</span><span class="sxs-lookup"><span data-stu-id="c8798-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8798-115">La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.</span><span class="sxs-lookup"><span data-stu-id="c8798-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="c8798-116">**Usa l'app Sicurezza di Windows per disabilitare notifiche aggiuntive:**</span><span class="sxs-lookup"><span data-stu-id="c8798-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="c8798-117">Apri l'app Sicurezza di Windows facendo clic sull'icona scudo nella barra delle applicazioni o cercando **Defender** nel menu Start.</span><span class="sxs-lookup"><span data-stu-id="c8798-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="c8798-118">Fai clic **sul riquadro Protezione** da & virus (o sull'icona scudo sulla barra dei menu sinistra) e quindi sull'etichetta **Impostazioni** protezione da & virus:</span><span class="sxs-lookup"><span data-stu-id="c8798-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="c8798-120">Scorrere fino alla **sezione Notifiche** e fare clic su Modifica **impostazioni notifica.**</span><span class="sxs-lookup"><span data-stu-id="c8798-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="c8798-121">Fai scorrere **l'interruttore su Disattivato** o **Attivato** per disabilitare o abilitare notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c8798-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="c8798-122">**Utilizzare Criteri di gruppo per disabilitare notifiche aggiuntive:**</span><span class="sxs-lookup"><span data-stu-id="c8798-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="c8798-123">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c8798-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="c8798-124">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="c8798-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c8798-125">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="c8798-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c8798-126">Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="c8798-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="c8798-127">Fai doppio clic **su Disattiva notifiche avanzate** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="c8798-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c8798-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8798-128">Click **OK**.</span></span> <span data-ttu-id="c8798-129">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c8798-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="c8798-130">Configurare le notifiche standard sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="c8798-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="c8798-131">È possibile utilizzare Criteri di gruppo per:</span><span class="sxs-lookup"><span data-stu-id="c8798-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="c8798-132">Visualizzare testo aggiuntivo personalizzato sugli endpoint quando l'utente deve eseguire un'azione</span><span class="sxs-lookup"><span data-stu-id="c8798-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="c8798-133">Nascondere tutte le notifiche sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="c8798-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="c8798-134">Nascondere le notifiche di riavvio sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="c8798-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="c8798-135">Nascondere le notifiche può essere utile in situazioni in cui non è possibile nascondere l'intera interfaccia di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="c8798-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="c8798-136">Per [altre informazioni, vedi Impedire](prevent-end-user-interaction-microsoft-defender-antivirus.md) agli utenti di visualizzare o interagire con l'interfaccia utente di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="c8798-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8798-137">Le notifiche nascoste verranno eseguite solo sugli endpoint in cui è stato distribuito il criterio.</span><span class="sxs-lookup"><span data-stu-id="c8798-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="c8798-138">Le notifiche relative alle azioni che devono essere eseguite (ad esempio un riavvio) verranno comunque visualizzate nel dashboard e nei report di monitoraggio di [Endpoint Protection di Microsoft Endpoint Manager.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="c8798-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="c8798-139">Per istruzioni su come aggiungere informazioni di contatto personalizzate alle notifiche visualizzate dagli utenti nei computer, vedi Personalizzare [l'app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) Sicurezza di Windows per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8798-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="c8798-140">**Usare Criteri di gruppo per nascondere le notifiche:**</span><span class="sxs-lookup"><span data-stu-id="c8798-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="c8798-141">Nel computer di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c8798-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="c8798-142">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="c8798-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="c8798-143">Espandi l'albero **fino a visualizzare i componenti di Windows >'interfaccia > Client di Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="c8798-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="c8798-144">Fare doppio clic **su Elimina tutte le notifiche** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="c8798-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c8798-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8798-145">Click **OK**.</span></span> <span data-ttu-id="c8798-146">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c8798-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="c8798-147">**Usare Criteri di gruppo per nascondere le notifiche di riavvio:**</span><span class="sxs-lookup"><span data-stu-id="c8798-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="c8798-148">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c8798-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="c8798-149">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="c8798-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c8798-150">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="c8798-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c8798-151">Espandi l'albero **fino a visualizzare i componenti di Windows >'interfaccia > Client di Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="c8798-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="c8798-152">Fai doppio clic **su Elimina le notifiche di riavvio** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="c8798-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c8798-153">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8798-153">Click **OK**.</span></span> <span data-ttu-id="c8798-154">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c8798-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8798-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c8798-155">Related topics</span></span>

- [<span data-ttu-id="c8798-156">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="c8798-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="c8798-157">Configurare l'interazione dell'utente finale con Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="c8798-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)