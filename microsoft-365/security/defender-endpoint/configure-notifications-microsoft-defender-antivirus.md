---
title: Configurare Antivirus Microsoft Defender notifiche
description: Informazioni su come configurare e personalizzare sia le notifiche standard che altre Antivirus Microsoft Defender sugli endpoint.
keywords: notifiche, defender, antivirus, endpoint, gestione, amministratore
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985409"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="6cbcf-104">Configurare Antivirus Microsoft Defender notifiche visualizzate sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="6cbcf-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="6cbcf-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-105">**Applies to:**</span></span>

- [<span data-ttu-id="6cbcf-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6cbcf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6cbcf-107">In Windows 10, le notifiche delle applicazioni relative al rilevamento e alla correzione di malware sono più affidabili, coerenti e concise.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="6cbcf-108">Antivirus Microsoft Defender notifiche vengono visualizzate sugli endpoint quando vengono completate le analisi e vengono rilevate minacce.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="6cbcf-109">Le notifiche seguono sia le analisi pianificate che le analisi attivate manualmente.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="6cbcf-110">Queste notifiche vengono visualizzate anche nel **Centro notifiche** e un riepilogo delle analisi e dei rilevamenti delle minacce viene visualizzato a intervalli di tempo regolari.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="6cbcf-111">Se si fa parte del team di sicurezza dell'organizzazione, è possibile configurare la modalità di visualizzazione delle notifiche sugli endpoint, ad esempio le notifiche che richiede un riavvio del sistema o che indicano che è stata rilevata e corretti una minaccia.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="6cbcf-112">Configurare le notifiche antivirus tramite Criteri di gruppo o l Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="6cbcf-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="6cbcf-113">Puoi configurare la visualizzazione di notifiche aggiuntive, ad esempio riepiloghi di rilevamento delle minacce recenti, [nell'app](microsoft-defender-security-center-antivirus.md) Sicurezza di Windows e con Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="6cbcf-114">In Windows 10 versione 1607 la funzionalità  è stata denominata Notifiche avanzate ed è stata configurata in Windows Impostazioni Aggiornamento &  >  **sicurezza**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="6cbcf-115">Nelle impostazioni di Criteri di gruppo per tutte le versioni di Windows 10, la funzionalità di notifica è denominata **Notifiche avanzate.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="6cbcf-116">Usare Criteri di gruppo per disabilitare notifiche aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6cbcf-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="6cbcf-117">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="6cbcf-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="6cbcf-118">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="6cbcf-119">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="6cbcf-120">Selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="6cbcf-121">Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender** > Reporting\*\*.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="6cbcf-122">Fai doppio clic **su Disattiva notifiche avanzate** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="6cbcf-123">Infine scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-123">Then select **OK**.</span></span> <span data-ttu-id="6cbcf-124">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cbcf-125">La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="6cbcf-126">Usare l'app Sicurezza di Windows per disabilitare notifiche aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6cbcf-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="6cbcf-127">Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando sicurezza nel menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="6cbcf-128">Seleziona **Riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona **Impostazioni** protezione da & virus</span><span class="sxs-lookup"><span data-stu-id="6cbcf-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="6cbcf-129">Scorri fino alla **sezione Notifiche** e seleziona Modifica **impostazioni notifica.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="6cbcf-130">Fai scorrere **l'interruttore su Disattivato** o **Attivato** per disabilitare o abilitare notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cbcf-131">La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="6cbcf-132">Configurare le notifiche standard sugli endpoint tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="6cbcf-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="6cbcf-133">È possibile utilizzare Criteri di gruppo per:</span><span class="sxs-lookup"><span data-stu-id="6cbcf-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="6cbcf-134">Visualizzare testo aggiuntivo personalizzato sugli endpoint quando l'utente deve eseguire un'azione</span><span class="sxs-lookup"><span data-stu-id="6cbcf-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="6cbcf-135">Nascondere tutte le notifiche sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="6cbcf-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="6cbcf-136">Nascondere le notifiche di riavvio sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="6cbcf-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="6cbcf-137">Nascondere le notifiche può essere utile in situazioni in cui non è possibile nascondere l'intera Antivirus Microsoft Defender interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="6cbcf-138">Per altre informazioni, vedi Impedire agli utenti di visualizzare o interagire con [Antivirus Microsoft Defender'interfaccia](prevent-end-user-interaction-microsoft-defender-antivirus.md) utente.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="6cbcf-139">Le notifiche nascoste verranno eseguite solo sugli endpoint in cui è stato distribuito il criterio.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="6cbcf-140">Le notifiche relative alle azioni che devono essere eseguite (ad esempio un riavvio) verranno comunque visualizzate nel dashboard e nei report Microsoft Endpoint Manager Endpoint Protection [monitoraggio.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="6cbcf-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="6cbcf-141">Per aggiungere informazioni di contatto personalizzate alle notifiche degli endpoint, vedi Personalizzare [l'app Sicurezza di Windows per l'organizzazione.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="6cbcf-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="6cbcf-142">Usare Criteri di gruppo per nascondere le notifiche</span><span class="sxs-lookup"><span data-stu-id="6cbcf-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="6cbcf-143">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="6cbcf-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="6cbcf-144">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="6cbcf-145">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e quindi selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="6cbcf-146">Espandere l'albero per **Windows componenti**  >    >  **Antivirus Microsoft Defender'interfaccia client**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="6cbcf-147">Fare doppio clic **su Elimina tutte le notifiche** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="6cbcf-148">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-148">Select **OK**.</span></span> <span data-ttu-id="6cbcf-149">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="6cbcf-150">Usare Criteri di gruppo per nascondere le notifiche di riavvio</span><span class="sxs-lookup"><span data-stu-id="6cbcf-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="6cbcf-151">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="6cbcf-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="6cbcf-152">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="6cbcf-153">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6cbcf-154">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="6cbcf-155">Espandere l'albero per **Windows componenti**  >    >  **Antivirus Microsoft Defender'interfaccia client**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="6cbcf-156">Fai doppio clic **su Elimina le notifiche di riavvio** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="6cbcf-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="6cbcf-157">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-157">Select **OK**.</span></span> <span data-ttu-id="6cbcf-158">In questo modo si impedirà la visualizzazione di notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="6cbcf-158">This will prevent additional notifications from appearing.</span></span>

