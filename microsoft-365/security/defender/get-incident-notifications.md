---
title: Ricevere notifiche di eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come creare regole per ricevere notifiche tramite posta elettronica per eventi imprevisti in Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fec2263599f3ed727d3d9d70023927084eb1c094
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501066"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="74849-104">Ricevere notifiche di eventi imprevisti tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="74849-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="74849-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="74849-105">**Applies to:**</span></span>
- <span data-ttu-id="74849-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74849-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="74849-107">È possibile configurare Microsoft 365 Defender per inviare una notifica tramite posta elettronica ogni volta che sono presenti nuovi eventi imprevisti o nuovi aggiornamenti a eventi imprevisti esistenti.</span><span class="sxs-lookup"><span data-stu-id="74849-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="74849-108">Puoi scegliere di ricevere notifiche in base alla gravità dell'incidente o in base al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="74849-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="74849-109">Puoi anche scegliere di ricevere una notifica solo al primo aggiornamento per evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="74849-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="74849-110">È possibile aggiungere o rimuovere destinatari nelle notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74849-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="74849-111">I nuovi destinatari aggiunti riceveranno una notifica sugli eventi imprevisti dopo l'aggiunta.</span><span class="sxs-lookup"><span data-stu-id="74849-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="74849-112">La notifica di posta elettronica contiene dettagli importanti sull'evento imprevisto, ad esempio il nome, la gravità e le categorie dell'evento imprevisto, tra gli altri.</span><span class="sxs-lookup"><span data-stu-id="74849-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="74849-113">È inoltre possibile passare direttamente agli eventi imprevisti in modo da poter avviare immediatamente l'indagine.</span><span class="sxs-lookup"><span data-stu-id="74849-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="74849-114">Per ulteriori informazioni sull'analisi degli incidenti, vedere [Investigate incidents in Microsoft 365 Defender.](./investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="74849-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="74849-115">Per configurare le impostazioni di notifica tramite posta elettronica, è necessario disporre delle autorizzazioni "Gestisci impostazioni di sicurezza".</span><span class="sxs-lookup"><span data-stu-id="74849-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="74849-116">Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare automaticamente le notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74849-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="74849-117">Allo stesso modo, se l'organizzazione utilizza il controllo di accesso basato sui ruoli(RBAC), è possibile creare, modificare, eliminare e ricevere notifiche in base ai gruppi di dispositivi che sono autorizzati a gestire.</span><span class="sxs-lookup"><span data-stu-id="74849-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="74849-118">Creare regole per le notifiche di eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="74849-118">Create rules for incident notifications</span></span>

<span data-ttu-id="74849-119">Per configurare la prima notifica tramite posta elettronica per gli eventi imprevisti, creare una nuova regola e personalizzare le impostazioni di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74849-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="74849-120">Nel riquadro di spostamento, selezionare **Impostazioni**  >  **Notifiche e-mail evento imprevisto.**</span><span class="sxs-lookup"><span data-stu-id="74849-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="74849-121">Selezionare **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="74849-121">Select **Add item**.</span></span>
3. <span data-ttu-id="74849-122">Assegnare un nome alla regola in **Nome** e specificare una **Descrizione.**</span><span class="sxs-lookup"><span data-stu-id="74849-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Finestra crea regola per notif di posta elettronica operazioni non consentite](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="74849-124">Selezionare **Avanti** per passare a **Impostazioni notifica.**</span><span class="sxs-lookup"><span data-stu-id="74849-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="74849-125">Qui puoi specificare:</span><span class="sxs-lookup"><span data-stu-id="74849-125">Here you can specify:</span></span>
    - <span data-ttu-id="74849-126">**Gravità avviso:** scegliere la gravità dell'avviso che attiverà una notifica di evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="74849-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="74849-127">Ad esempio, se si desidera essere informati solo sugli eventi imprevisti di gravità elevata, selezionare Alta.</span><span class="sxs-lookup"><span data-stu-id="74849-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="74849-128">**Ambito del gruppo di dispositivi-** Questo elenco a discesa visualizza tutti i gruppi di dispositivi a cui l'utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="74849-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="74849-129">Seleziona i gruppi di dispositivi per cui stai creando le regole di notifica degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="74849-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="74849-130">**Notifica solo alla prima occorrenza per evento** imprevisto: selezionando questa opzione verrà inviata una notifica tramite posta elettronica solo al primo avviso corrispondente alle altre selezioni.</span><span class="sxs-lookup"><span data-stu-id="74849-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="74849-131">Gli aggiornamenti o gli avvisi successivi correlati all'evento imprevisto non attivano una notifica.</span><span class="sxs-lookup"><span data-stu-id="74849-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="74849-132">**Includi nome organizzazione** - Indica se il nome del cliente viene visualizzato o meno nella notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74849-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="74849-133">**Includi collegamento al portale specifico del** tenant - Aggiunge un collegamento con l'ID tenant per consentire l'accesso a un tenant specifico.</span><span class="sxs-lookup"><span data-stu-id="74849-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Finestra delle impostazioni notif per i notif di posta elettronica degli eventi imprevisti](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="74849-135">Selezionare **Avanti** per passare alla **sezione** Destinatari.</span><span class="sxs-lookup"><span data-stu-id="74849-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="74849-136">Qui è possibile specificare gli indirizzi di posta elettronica che riceveranno le notifiche di posta elettronica degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="74849-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="74849-137">Selezionare **Aggiungi un destinatario dopo** aver digitato ogni indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="74849-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Finestra Aggiungi destinatari per notif di posta elettronica operazioni non consentite](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="74849-139">Infine, selezionare **Avanti** per passare a **Rivedi regola** in modo da poter visualizzare tutte le impostazioni associate alla nuova regola.</span><span class="sxs-lookup"><span data-stu-id="74849-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="74849-140">I destinatari inizieranno a ricevere notifiche di eventi imprevisti tramite posta elettronica in base alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="74849-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="74849-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74849-141">See also</span></span>
- [<span data-ttu-id="74849-142">Panoramica degli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74849-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="74849-143">Assegnare priorità agli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74849-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="74849-144">Analizzare gli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74849-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)
