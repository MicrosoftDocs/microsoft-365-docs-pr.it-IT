---
title: Configurare Antivirus Microsoft Defender notifiche
description: Informazioni su come configurare e personalizzare le notifiche Antivirus Microsoft Defender standard e aggiuntive sugli endpoint.
keywords: notifiche, defender, antivirus, endpoint, gestione, amministratore
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572346"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="e7998-104">Configurare le notifiche che vengono visualizzate negli endpoint</span><span class="sxs-lookup"><span data-stu-id="e7998-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="e7998-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e7998-105">**Applies to:**</span></span>

- [<span data-ttu-id="e7998-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e7998-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e7998-107">In Windows 10, le notifiche delle applicazioni relative al rilevamento e alla correzione di malware sono più affidabili, coerenti e concise.</span><span class="sxs-lookup"><span data-stu-id="e7998-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="e7998-108">Le notifiche vengono visualizzate sugli endpoint quando vengono completate analisi attivate manualmente e pianificate e vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="e7998-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="e7998-109">Queste notifiche vengono visualizzate anche nel **Centro notifiche** e un riepilogo delle analisi e dei rilevamenti delle minacce viene visualizzato a intervalli di tempo regolari.</span><span class="sxs-lookup"><span data-stu-id="e7998-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="e7998-110">Puoi anche configurare la modalità di visualizzazione delle notifiche standard sugli endpoint, ad esempio le notifiche per il riavvio o quando è stata rilevata e corretti una minaccia.</span><span class="sxs-lookup"><span data-stu-id="e7998-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="e7998-111">Configurare le notifiche aggiuntive visualizzate sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="e7998-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="e7998-112">Puoi configurare la visualizzazione di notifiche aggiuntive, ad esempio riepiloghi di rilevamento delle minacce recenti, [nell'app](microsoft-defender-security-center-antivirus.md) Sicurezza di Windows e con Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e7998-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="e7998-113">In Windows 10 versione 1607 la funzionalità  era denominata Notifiche avanzate e poteva essere configurata in Windows Impostazioni Aggiornamento &  >  **sicurezza**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="e7998-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="e7998-114">Nelle impostazioni di Criteri di gruppo in tutte le versioni di Windows 10, si chiama **Notifiche avanzate.**</span><span class="sxs-lookup"><span data-stu-id="e7998-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7998-115">La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.</span><span class="sxs-lookup"><span data-stu-id="e7998-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="e7998-116">**Usa l'app Sicurezza di Windows per disabilitare notifiche aggiuntive:**</span><span class="sxs-lookup"><span data-stu-id="e7998-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="e7998-117">Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando sicurezza nel menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="e7998-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="e7998-118">Seleziona **Riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona **Impostazioni** protezione da & virus</span><span class="sxs-lookup"><span data-stu-id="e7998-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="e7998-119">Scorrere fino alla **sezione Notifiche** e fare clic su Modifica **impostazioni notifica.**</span><span class="sxs-lookup"><span data-stu-id="e7998-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="e7998-120">Fai scorrere **l'interruttore su Disattivato** o **Attivato** per disabilitare o abilitare notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e7998-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="e7998-121">**Utilizzare Criteri di gruppo per disabilitare notifiche aggiuntive:**</span><span class="sxs-lookup"><span data-stu-id="e7998-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="e7998-122">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e7998-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e7998-123">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="e7998-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e7998-124">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="e7998-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="e7998-125">Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="e7998-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="e7998-126">Fai doppio clic **su Disattiva notifiche avanzate** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="e7998-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="e7998-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7998-127">Click **OK**.</span></span> <span data-ttu-id="e7998-128">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e7998-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="e7998-129">Configurare le notifiche standard sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="e7998-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="e7998-130">È possibile utilizzare Criteri di gruppo per:</span><span class="sxs-lookup"><span data-stu-id="e7998-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="e7998-131">Visualizzare testo aggiuntivo personalizzato sugli endpoint quando l'utente deve eseguire un'azione</span><span class="sxs-lookup"><span data-stu-id="e7998-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="e7998-132">Nascondere tutte le notifiche sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="e7998-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="e7998-133">Nascondere le notifiche di riavvio sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="e7998-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="e7998-134">Nascondere le notifiche può essere utile in situazioni in cui non è possibile nascondere l'intera Antivirus Microsoft Defender interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e7998-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="e7998-135">Per altre informazioni, vedi Impedire agli utenti di visualizzare o interagire con [Antivirus Microsoft Defender'interfaccia](prevent-end-user-interaction-microsoft-defender-antivirus.md) utente.</span><span class="sxs-lookup"><span data-stu-id="e7998-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="e7998-136">Le notifiche nascoste verranno eseguite solo sugli endpoint in cui è stato distribuito il criterio.</span><span class="sxs-lookup"><span data-stu-id="e7998-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="e7998-137">Le notifiche relative alle azioni che devono essere eseguite (ad esempio un riavvio) verranno comunque visualizzate nel dashboard e nei report Microsoft Endpoint Manager Endpoint Protection [monitoraggio.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="e7998-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="e7998-138">Per [istruzioni su come aggiungere](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) informazioni di contatto personalizzate alle notifiche visualizzate dagli utenti nei computer, vedi Personalizzare l'app Sicurezza di Windows per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7998-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="e7998-139">**Usare Criteri di gruppo per nascondere le notifiche:**</span><span class="sxs-lookup"><span data-stu-id="e7998-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="e7998-140">Nel computer di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e7998-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="e7998-141">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="e7998-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="e7998-142">Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender >'interfaccia client**.</span><span class="sxs-lookup"><span data-stu-id="e7998-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="e7998-143">Fare doppio clic **su Elimina tutte le notifiche** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="e7998-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="e7998-144">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7998-144">Click **OK**.</span></span> <span data-ttu-id="e7998-145">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e7998-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="e7998-146">**Usare Criteri di gruppo per nascondere le notifiche di riavvio:**</span><span class="sxs-lookup"><span data-stu-id="e7998-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="e7998-147">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e7998-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e7998-148">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="e7998-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e7998-149">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="e7998-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="e7998-150">Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender >'interfaccia client**.</span><span class="sxs-lookup"><span data-stu-id="e7998-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="e7998-151">Fai doppio clic **su Elimina le notifiche di riavvio** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="e7998-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="e7998-152">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7998-152">Click **OK**.</span></span> <span data-ttu-id="e7998-153">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e7998-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7998-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e7998-154">Related topics</span></span>

- [<span data-ttu-id="e7998-155">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e7998-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e7998-156">Configurare l'interazione dell'utente finale con Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e7998-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
