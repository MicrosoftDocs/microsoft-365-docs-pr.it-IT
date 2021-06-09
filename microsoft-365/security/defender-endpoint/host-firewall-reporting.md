---
title: Ospitare la creazione di report dei firewall in Microsoft Defender per endpoint
description: Ospitare e visualizzare i report del firewall Microsoft 365 centro sicurezza.
keywords: windows defender, firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809307"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c421d-104">Ospitare la creazione di report dei firewall in Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c421d-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c421d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c421d-105">**Applies to:**</span></span>
- [<span data-ttu-id="c421d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c421d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c421d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c421d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c421d-108">Se sei un amministratore, ora puoi ospitare la segnalazione del firewall [Microsoft 365 centro sicurezza](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c421d-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="c421d-109">Questa funzionalità consente di visualizzare i report Windows 10 e Windows server 2019 da una posizione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="c421d-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c421d-110">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="c421d-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="c421d-111">È necessario eseguire Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c421d-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="c421d-112">Per eseguire l'onboard dei dispositivi nel servizio Microsoft Defender for Endpoint, vedi [qui](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="c421d-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="c421d-113">Per Microsoft 365 centro sicurezza per iniziare a ricevere  i dati, è necessario abilitare gli eventi di controllo per Windows Defender Firewall sicurezza avanzata:</span><span class="sxs-lookup"><span data-stu-id="c421d-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="c421d-114">Audit Filtering Platform Packet Drop</span><span class="sxs-lookup"><span data-stu-id="c421d-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="c421d-115">Audit Filtering Platform Connection</span><span class="sxs-lookup"><span data-stu-id="c421d-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="c421d-116">Abilitare questi eventi utilizzando Editor oggetti Criteri di gruppo, Criteri di sicurezza locali o i auditpol.exe comandi.</span><span class="sxs-lookup"><span data-stu-id="c421d-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="c421d-117">Per ulteriori informazioni, vedere [qui](/windows/win32/fwp/auditing-and-logging).</span><span class="sxs-lookup"><span data-stu-id="c421d-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="c421d-118">I due comandi di PowerShell sono:</span><span class="sxs-lookup"><span data-stu-id="c421d-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="c421d-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="c421d-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="c421d-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="c421d-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="c421d-121">Processo</span><span class="sxs-lookup"><span data-stu-id="c421d-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="c421d-122">Assicurati di seguire le istruzioni della sezione precedente e configurare correttamente i dispositivi per la partecipazione all'anteprima anticipata.</span><span class="sxs-lookup"><span data-stu-id="c421d-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="c421d-123">Dopo aver abilitato gli eventi, Microsoft 365 centro sicurezza inizierà a monitorare i dati.</span><span class="sxs-lookup"><span data-stu-id="c421d-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="c421d-124">IP remoto, porta remota, porta locale, IP locale, nome computer, processo attraverso connessioni in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="c421d-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="c421d-125">Gli amministratori possono ora visualizzare l Windows'attività del firewall host [qui](https://security.microsoft.com/firewall).</span><span class="sxs-lookup"><span data-stu-id="c421d-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="c421d-126">È possibile semplificare la creazione di report aggiuntivi scaricando lo [script per](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) la creazione di report personalizzati per monitorare le attività Windows Defender Firewall tramite Power BI.</span><span class="sxs-lookup"><span data-stu-id="c421d-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="c421d-127">Possono essere necessario fino a 12 ore prima che i dati riflettano.</span><span class="sxs-lookup"><span data-stu-id="c421d-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="c421d-128">Scenari supportati</span><span class="sxs-lookup"><span data-stu-id="c421d-128">Supported scenarios</span></span>
<span data-ttu-id="c421d-129">Durante Ring0 Preview sono supportati gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="c421d-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="c421d-130">Creazione di report firewall nel Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="c421d-130">Firewall reporting in security center</span></span>

<span data-ttu-id="c421d-131">Ecco un paio di esempi delle pagine di report del firewall.</span><span class="sxs-lookup"><span data-stu-id="c421d-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="c421d-132">Qui troverai un riepilogo delle attività in ingresso, in uscita e dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c421d-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="c421d-133">È possibile accedere a questa pagina direttamente da https://security.microsoft.com/firewall .</span><span class="sxs-lookup"><span data-stu-id="c421d-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c421d-134">![Pagina di creazione di report del firewall host](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="c421d-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="c421d-135">È inoltre possibile accedere a questi report accedendo a Report Dispositivi report di sicurezza (sezione) nella parte inferiore della scheda Connessioni in ingresso  >    >   bloccate dal firewall. </span><span class="sxs-lookup"><span data-stu-id="c421d-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="c421d-136">Da "Computer con una connessione bloccata" al dispositivo</span><span class="sxs-lookup"><span data-stu-id="c421d-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="c421d-137">Le schede supportano oggetti interattivi.</span><span class="sxs-lookup"><span data-stu-id="c421d-137">Cards support interactive objects.</span></span> <span data-ttu-id="c421d-138">Puoi analizzare l'attività di un dispositivo facendo clic sul nome del dispositivo, che verrà avviato in una nuova scheda, e passare direttamente alla https://securitycenter.microsoft.com **scheda Sequenza temporale** del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c421d-139">![Computer con una connessione bloccata](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="c421d-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="c421d-140">Ora puoi selezionare la **scheda Sequenza** temporale, che ti darà un elenco di eventi associati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="c421d-141">Dopo aver fatto clic **sul pulsante** Filtri nell'angolo superiore destro del riquadro di visualizzazione, selezionare il tipo di evento desiderato.</span><span class="sxs-lookup"><span data-stu-id="c421d-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="c421d-142">In questo caso, selezionare **Eventi firewall** e il riquadro verrà filtrato in Eventi firewall.</span><span class="sxs-lookup"><span data-stu-id="c421d-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c421d-143">![Pulsante Filtri](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="c421d-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="c421d-144">Drill-into advanced hunting (preview refresh)</span><span class="sxs-lookup"><span data-stu-id="c421d-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="c421d-145">I report firewall supportano il drilling dalla scheda direttamente in **Ricerca avanzata** facendo clic sul pulsante **Apri ricerca** avanzata.</span><span class="sxs-lookup"><span data-stu-id="c421d-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="c421d-146">La query verrà precompilato.</span><span class="sxs-lookup"><span data-stu-id="c421d-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c421d-147">![Pulsante Apri ricerca avanzata](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="c421d-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="c421d-148">La query può ora essere eseguita e tutti gli eventi firewall correlati degli ultimi 30 giorni possono essere esplorati.</span><span class="sxs-lookup"><span data-stu-id="c421d-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="c421d-149">Per ulteriori report o modifiche personalizzate, la query può essere esportata in Power BI per ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="c421d-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="c421d-150">I report personalizzati possono essere semplificati scaricando lo [script di](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) creazione di report personalizzati per monitorare le attività Windows Defender Firewall tramite Power BI.</span><span class="sxs-lookup"><span data-stu-id="c421d-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 