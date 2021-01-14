---
title: Ottenere notifiche degli incidenti in Microsoft 365 Defender
description: Informazioni su come creare regole per ricevere notifiche tramite posta elettronica per gli eventi non consentiti in Microsoft 365 Defender
keywords: incidente, posta elettronica, posta elettronica notfications, configurare, utenti, cassetta postale, posta elettronica, incidenti
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848892"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="78736-104">Ottenere notifiche sugli incidenti tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="78736-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="78736-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="78736-105">**Applies to:**</span></span>
- <span data-ttu-id="78736-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78736-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="78736-107">È possibile configurare Microsoft 365 Defender per inviare una notifica tramite posta elettronica ogni volta che sono presenti nuovi incidenti o nuovi aggiornamenti per gli incidenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="78736-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="78736-108">È possibile scegliere di ottenere notifiche in base alla gravità degli incidenti o al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="78736-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="78736-109">È anche possibile scegliere di ricevere una notifica solo sul primo aggiornamento per evento Incident.</span><span class="sxs-lookup"><span data-stu-id="78736-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="78736-110">È possibile aggiungere o rimuovere i destinatari nelle notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="78736-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="78736-111">I destinatari appena aggiunti ricevono una notifica sugli incidenti dopo che sono stati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="78736-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="78736-112">La notifica di posta elettronica contiene informazioni importanti sull'incidente, ad esempio il nome, la gravità e le categorie degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="78736-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="78736-113">È inoltre possibile accedere direttamente agli eventi non consentiti in modo da poter avviare immediatamente l'indagine.</span><span class="sxs-lookup"><span data-stu-id="78736-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="78736-114">Per ulteriori informazioni sulle indagini sugli incidenti, vedere [indagini sugli incidenti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span><span class="sxs-lookup"><span data-stu-id="78736-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="78736-115">Per configurare le impostazioni di notifica di posta elettronica, è necessario disporre delle autorizzazioni di gestione delle impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="78736-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="78736-116">Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli di amministratore di sicurezza o di amministratore globale possono configurare le notifiche di posta elettronica per l'utente.</span><span class="sxs-lookup"><span data-stu-id="78736-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="78736-117">Analogamente, se l'organizzazione utilizza il controllo di accesso basato sui ruoli (RBAC), è possibile creare, modificare, eliminare e ricevere notifiche solo in base ai gruppi di dispositivi che sono autorizzati a gestire.</span><span class="sxs-lookup"><span data-stu-id="78736-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="78736-118">Creare regole per le notifiche degli eventi non consentiti</span><span class="sxs-lookup"><span data-stu-id="78736-118">Create rules for incident notifications</span></span>

<span data-ttu-id="78736-119">Per impostare la prima notifica di posta elettronica per gli eventi non consentiti, creare una nuova regola e personalizzare le impostazioni di notifica di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="78736-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="78736-120">Nel riquadro di spostamento, selezionare **Impostazioni**  >  **notifiche di posta elettronica eventi** non consentiti.</span><span class="sxs-lookup"><span data-stu-id="78736-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="78736-121">Selezionare **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="78736-121">Select **Add item**.</span></span>
3. <span data-ttu-id="78736-122">Assegnare alla regola un nome in **nome** e specificare una **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="78736-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Creare la finestra della regola per la posta elettronica notifs](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="78736-124">Fare clic su **Avanti** per accedere alle **impostazioni di notifica**.</span><span class="sxs-lookup"><span data-stu-id="78736-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="78736-125">Qui è possibile specificare:</span><span class="sxs-lookup"><span data-stu-id="78736-125">Here you can specify:</span></span>
    - <span data-ttu-id="78736-126">**Severità degli avvisi** -scegliere la gravità degli avvisi che attiverà una notifica di emergenza.</span><span class="sxs-lookup"><span data-stu-id="78736-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="78736-127">Ad esempio, se si desidera solo essere informati sugli incidenti di gravità elevata, selezionare elevato.</span><span class="sxs-lookup"><span data-stu-id="78736-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="78736-128">**Ambito gruppo di dispositivi** -in questo elenco a discesa vengono visualizzati tutti i gruppi di dispositivi che l'utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="78736-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="78736-129">Selezionare i gruppi di dispositivi in cui si stanno creando le regole per la notifica degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="78736-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="78736-130">**Solo notifica sulla prima occorrenza per** evento: selezionando questa opzione, verrà inviata una notifica tramite posta elettronica solo sul primo avviso corrispondente alle altre selezioni.</span><span class="sxs-lookup"><span data-stu-id="78736-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="78736-131">Gli aggiornamenti o gli avvisi successivi relativi all'incidente non attiveranno una notifica.</span><span class="sxs-lookup"><span data-stu-id="78736-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="78736-132">**Includi nome organizzazione** -indica se il nome del cliente viene visualizzato nella notifica di posta elettronica o meno.</span><span class="sxs-lookup"><span data-stu-id="78736-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="78736-133">**Includi collegamento portale specifico del tenant** -aggiunge un collegamento all'ID tenant per consentire l'accesso a un tenant specifico.</span><span class="sxs-lookup"><span data-stu-id="78736-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Finestra delle impostazioni di Notif per la posta elettronica Incident notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="78736-135">Selezionare **Avanti** per andare alla sezione **destinatari** .</span><span class="sxs-lookup"><span data-stu-id="78736-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="78736-136">Qui è possibile specificare gli indirizzi di posta elettronica che riceveranno le notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="78736-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="78736-137">Selezionare **Aggiungi un destinatario** dopo aver digitato tutti gli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="78736-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Finestra Aggiungi destinatari per la posta elettronica notifs](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="78736-139">Infine, fare clic su **Avanti** per passare a **Revisione regola** in modo da poter visualizzare tutte le impostazioni associate alla nuova regola.</span><span class="sxs-lookup"><span data-stu-id="78736-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="78736-140">I destinatari inizieranno a ricevere notifiche sugli incidenti tramite posta elettronica in base alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="78736-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="78736-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78736-141">See also</span></span>
- [<span data-ttu-id="78736-142">Panoramica degli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78736-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="78736-143">Assegnare la priorità agli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78736-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="78736-144">Esaminare gli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78736-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

