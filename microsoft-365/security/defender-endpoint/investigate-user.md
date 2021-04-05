---
title: Analizzare un account utente in Microsoft Defender for Endpoint
description: Analizzare un account utente per individuare potenziali credenziali compromesse o eseguire il pivot sull'account utente associato durante un'indagine.
keywords: analizzare, account, utente, entità utente, avviso, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 672867d107d005004201caab7d6497ceb048ac97
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587708"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f1bde-104">Analizzare un account utente in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1bde-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1bde-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f1bde-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1bde-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f1bde-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1bde-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1bde-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="f1bde-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f1bde-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f1bde-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f1bde-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="f1bde-110">Analizzare le entità account utente</span><span class="sxs-lookup"><span data-stu-id="f1bde-110">Investigate user account entities</span></span>

<span data-ttu-id="f1bde-111">Identificare gli account utente con gli avvisi più attivi (visualizzati nel dashboard come "Utenti a rischio") e analizzare i casi di potenziali credenziali compromesse o eseguire il pivot sull'account utente associato durante l'analisi di un avviso o di un dispositivo per identificare possibili spostamenti laterali tra dispositivi con tale account utente.</span><span class="sxs-lookup"><span data-stu-id="f1bde-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="f1bde-112">Le informazioni sull'account utente sono disponibili nelle visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1bde-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="f1bde-113">Dashboard</span><span class="sxs-lookup"><span data-stu-id="f1bde-113">Dashboard</span></span>
- <span data-ttu-id="f1bde-114">Coda avvisi</span><span class="sxs-lookup"><span data-stu-id="f1bde-114">Alert queue</span></span>
- <span data-ttu-id="f1bde-115">Pagina dettagli dispositivo</span><span class="sxs-lookup"><span data-stu-id="f1bde-115">Device details page</span></span>

<span data-ttu-id="f1bde-116">In queste visualizzazioni è disponibile un collegamento all'account utente selezionabile che consente di accedere alla pagina dei dettagli dell'account utente in cui vengono visualizzati ulteriori dettagli sull'account utente.</span><span class="sxs-lookup"><span data-stu-id="f1bde-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="f1bde-117">Quando si analizza un'entità account utente, viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="f1bde-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="f1bde-118">Dettagli dell'account utente, avvisi di Azure Advanced Threat Protection (Azure ATP) e dispositivi connessi, ruolo, tipo di accesso e altri dettagli</span><span class="sxs-lookup"><span data-stu-id="f1bde-118">User account details, Azure Advanced Threat Protection (Azure ATP) alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="f1bde-119">Panoramica degli eventi imprevisti e dei dispositivi dell'utente</span><span class="sxs-lookup"><span data-stu-id="f1bde-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="f1bde-120">Avvisi correlati a questo utente</span><span class="sxs-lookup"><span data-stu-id="f1bde-120">Alerts related to this user</span></span>
- <span data-ttu-id="f1bde-121">Osservato nell'organizzazione (dispositivi connessi a)</span><span class="sxs-lookup"><span data-stu-id="f1bde-121">Observed in organization (devices logged on to)</span></span>

![Immagine della pagina dei dettagli dell'entità account utente](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="f1bde-123">Dettagli utente</span><span class="sxs-lookup"><span data-stu-id="f1bde-123">User details</span></span>

<span data-ttu-id="f1bde-124">Il  riquadro Dettagli utente a sinistra fornisce informazioni sull'utente, ad esempio eventi imprevisti aperti correlati, avvisi attivi, nome SAM, SID, avvisi di Azure ATP, numero di dispositivi a cui l'utente è connesso, quando l'utente è stato visto per primo e per ultimo, ruolo e tipi di accesso.</span><span class="sxs-lookup"><span data-stu-id="f1bde-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Azure ATP alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="f1bde-125">A seconda delle funzionalità di integrazione abilitate, verranno visualizzati altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="f1bde-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="f1bde-126">Ad esempio, se abiliti l'integrazione di Skype for business, potrai contattare l'utente dal portale.</span><span class="sxs-lookup"><span data-stu-id="f1bde-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="f1bde-127">La sezione Avvisi di **Azure ATP** contiene un collegamento che consente di accedere alla pagina di Azure ATP, se è stata abilitata la funzionalità Azure ATP e sono presenti avvisi correlati all'utente.</span><span class="sxs-lookup"><span data-stu-id="f1bde-127">The **Azure ATP alerts** section contains a link that will take you to the Azure ATP page, if you have enabled the Azure ATP feature, and there are alerts related to the user.</span></span> <span data-ttu-id="f1bde-128">La pagina di Azure ATP fornirà ulteriori informazioni sugli avvisi.</span><span class="sxs-lookup"><span data-stu-id="f1bde-128">The Azure ATP page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="f1bde-129">Dovrai abilitare l'integrazione sia in Azure ATP che in Defender for Endpoint per usare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f1bde-129">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="f1bde-130">In Defender for Endpoint puoi abilitare questa funzionalità nelle funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="f1bde-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="f1bde-131">Per ulteriori informazioni su come abilitare le funzionalità avanzate, vedere [Attivare le funzionalità avanzate.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="f1bde-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="f1bde-132">Le schede Panoramica, Avvisi e Osservati nell'organizzazione sono schede diverse che visualizzano vari attributi relativi all'account utente.</span><span class="sxs-lookup"><span data-stu-id="f1bde-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="f1bde-133">Panoramica</span><span class="sxs-lookup"><span data-stu-id="f1bde-133">Overview</span></span>

<span data-ttu-id="f1bde-134">La **scheda Panoramica** mostra i dettagli degli eventi imprevisti e un elenco dei dispositivi a cui l'utente ha eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f1bde-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="f1bde-135">Puoi espandere questi elementi per visualizzare i dettagli degli eventi di accesso per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1bde-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="f1bde-136">Avvisi</span><span class="sxs-lookup"><span data-stu-id="f1bde-136">Alerts</span></span>

<span data-ttu-id="f1bde-137">Nella **scheda Avvisi** è disponibile un elenco di avvisi associati all'account utente.</span><span class="sxs-lookup"><span data-stu-id="f1bde-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="f1bde-138">Questo elenco è una visualizzazione [](alerts-queue.md)filtrata della coda degli avvisi e mostra gli avvisi in cui il contesto utente è l'account utente selezionato, la data in cui è stata rilevata l'ultima attività, una breve descrizione dell'avviso, il dispositivo associato all'avviso, la gravità dell'avviso, lo stato dell'avviso nella coda e a chi è assegnato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="f1bde-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="f1bde-139">Osservato nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f1bde-139">Observed in organization</span></span>

<span data-ttu-id="f1bde-140">La scheda Osservati **nell'organizzazione** consente di specificare un intervallo di date per visualizzare un elenco dei dispositivi a cui l'utente è stato osservato connesso, l'account utente connesso più frequente e meno frequente per ognuno di questi dispositivi e il totale degli utenti osservati in ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1bde-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="f1bde-141">Selezionando un elemento nella tabella Osservati nell'organizzazione, l'elemento verrà espanso, rivelando altri dettagli sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1bde-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="f1bde-142">Selezionando direttamente un collegamento all'interno di un elemento, si invierà alla pagina corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f1bde-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="f1bde-143">Cercare account utente specifici</span><span class="sxs-lookup"><span data-stu-id="f1bde-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="f1bde-144">Seleziona **Utente** dal menu **a** discesa della barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f1bde-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="f1bde-145">Immettere l'account utente nel **campo Cerca.**</span><span class="sxs-lookup"><span data-stu-id="f1bde-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="f1bde-146">Fare clic sull'icona di ricerca o premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="f1bde-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="f1bde-147">Viene visualizzato un elenco di utenti che corrispondono al testo della query.</span><span class="sxs-lookup"><span data-stu-id="f1bde-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="f1bde-148">Vedrai il dominio e il nome dell'account utente, l'ultima volta che l'account utente è stato visualizzato e il numero totale di dispositivi a cui è stato eseguito l'accesso negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f1bde-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="f1bde-149">È possibile filtrare i risultati in base ai periodi di tempo seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1bde-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="f1bde-150">1 giorno</span><span class="sxs-lookup"><span data-stu-id="f1bde-150">1 day</span></span>
- <span data-ttu-id="f1bde-151">3 giorni</span><span class="sxs-lookup"><span data-stu-id="f1bde-151">3 days</span></span>
- <span data-ttu-id="f1bde-152">7 giorni</span><span class="sxs-lookup"><span data-stu-id="f1bde-152">7 days</span></span>
- <span data-ttu-id="f1bde-153">30 giorni</span><span class="sxs-lookup"><span data-stu-id="f1bde-153">30 days</span></span>
- <span data-ttu-id="f1bde-154">6 mesi</span><span class="sxs-lookup"><span data-stu-id="f1bde-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1bde-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1bde-155">Related topics</span></span>

- [<span data-ttu-id="f1bde-156">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts</span><span class="sxs-lookup"><span data-stu-id="f1bde-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="f1bde-157">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1bde-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="f1bde-158">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1bde-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="f1bde-159">Analizzare un file associato a un avviso di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1bde-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="f1bde-160">Analizzare i dispositivi nell'elenco Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="f1bde-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="f1bde-161">Analizzare un indirizzo IP associato a un avviso Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1bde-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="f1bde-162">Analizzare un dominio associato a un avviso Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1bde-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
