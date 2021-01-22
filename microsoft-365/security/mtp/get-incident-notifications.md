---
title: Ricevere notifiche di eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come creare regole per ricevere notifiche tramite posta elettronica per gli eventi imprevisti in Microsoft 365 Defender
keywords: evento imprevisto, posta elettronica, notifica di posta elettronica, configurare, utenti, cassetta postale, posta elettronica, eventi imprevisti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930979"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="4b1dc-104">Ricevere notifiche di eventi imprevisti tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="4b1dc-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4b1dc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4b1dc-105">**Applies to:**</span></span>
- <span data-ttu-id="4b1dc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b1dc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4b1dc-107">È possibile configurare Microsoft 365 Defender per inviare una notifica tramite posta elettronica ogni volta che sono presenti nuovi eventi imprevisti o nuovi aggiornamenti per gli eventi imprevisti esistenti.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="4b1dc-108">Puoi scegliere di ricevere notifiche in base alla gravità dell'incidente o in base al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="4b1dc-109">Puoi anche scegliere di ricevere una notifica solo sul primo aggiornamento per ogni evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="4b1dc-110">È possibile aggiungere o rimuovere destinatari nelle notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="4b1dc-111">I nuovi destinatari aggiunti vengono avvisati degli eventi imprevisti dopo l'aggiunta.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="4b1dc-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="4b1dc-113">È inoltre possibile passare direttamente agli eventi imprevisti in modo da poter avviare immediatamente l'indagine.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="4b1dc-114">Per altre informazioni sull'analisi degli eventi imprevisti, vedere [Analizzare gli eventi imprevisti in Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)</span><span class="sxs-lookup"><span data-stu-id="4b1dc-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="4b1dc-115">Per configurare le impostazioni di notifica tramite posta elettronica, sono necessarie le autorizzazioni "Gestisci impostazioni di sicurezza".</span><span class="sxs-lookup"><span data-stu-id="4b1dc-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="4b1dc-116">Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare automaticamente le notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="4b1dc-117">Analogamente, se l'organizzazione usa il controllo di accesso basato sui ruoli (RBAC), è possibile creare, modificare, eliminare e ricevere notifiche solo in base ai gruppi di dispositivi che è possibile gestire.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="4b1dc-118">Creare regole per le notifiche di eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="4b1dc-118">Create rules for incident notifications</span></span>

<span data-ttu-id="4b1dc-119">Per configurare la prima notifica tramite posta elettronica per gli eventi imprevisti, creare una nuova regola e personalizzare le impostazioni di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="4b1dc-120">Nel riquadro di spostamento, selezionare **Impostazioni** notifiche e-mail evento  >  **imprevisto.**</span><span class="sxs-lookup"><span data-stu-id="4b1dc-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="4b1dc-121">Selezionare **Aggiungi elemento.**</span><span class="sxs-lookup"><span data-stu-id="4b1dc-121">Select **Add item**.</span></span>
3. <span data-ttu-id="4b1dc-122">Assegnare alla regola un nome in **Nome** e specificare una **descrizione.**</span><span class="sxs-lookup"><span data-stu-id="4b1dc-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Finestra delle regole di creazione per i notif di posta elettronica degli eventi imprevisti](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="4b1dc-124">Selezionare **Avanti** per passare alle **impostazioni di notifica.**</span><span class="sxs-lookup"><span data-stu-id="4b1dc-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="4b1dc-125">Qui è possibile specificare:</span><span class="sxs-lookup"><span data-stu-id="4b1dc-125">Here you can specify:</span></span>
    - <span data-ttu-id="4b1dc-126">**Gravità avviso: scegliere** la gravità dell'avviso che attiverà una notifica di evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="4b1dc-127">Ad esempio, se si desidera essere informati solo su eventi imprevisti di gravità elevata, selezionare Alta.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="4b1dc-128">**Ambito del gruppo di dispositivi:** questo elenco a discesa visualizza tutti i gruppi di dispositivi a cui l'utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="4b1dc-129">Selezionare i gruppi di dispositivi per cui si stanno creando le regole di notifica degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="4b1dc-130">**Notifica solo alla prima occorrenza per** evento imprevisto: se si seleziona questa opzione, verrà inviata una notifica tramite posta elettronica solo al primo avviso corrispondente alle altre selezioni.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="4b1dc-131">Gli aggiornamenti o gli avvisi successivi correlati all'evento non attiverà una notifica.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="4b1dc-132">**Includi nome organizzazione-** Indica se il nome del cliente viene visualizzato o meno nella notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="4b1dc-133">**Includi collegamento al portale specifico del tenant:** aggiunge un collegamento con l'ID tenant per consentire l'accesso a un tenant specifico.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Finestra delle impostazioni notif per le notifiche di posta elettronica per eventi imprevisti](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="4b1dc-135">Selezionare **Avanti** per passare alla **sezione Destinatari.**</span><span class="sxs-lookup"><span data-stu-id="4b1dc-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="4b1dc-136">Qui è possibile specificare gli indirizzi di posta elettronica che riceveranno le notifiche di posta elettronica degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="4b1dc-137">Selezionare **Aggiungi un destinatario dopo aver** digitato ogni indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Finestra Aggiungi destinatari per notifiche di posta elettronica operazioni non consentite](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="4b1dc-139">Infine, selezionare **Avanti** per passare a **Revisione regola in** modo da visualizzare tutte le impostazioni associate alla nuova regola.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="4b1dc-140">I destinatari inizieranno a ricevere notifiche di eventi imprevisti tramite posta elettronica in base alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4b1dc-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b1dc-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b1dc-141">See also</span></span>
- [<span data-ttu-id="4b1dc-142">Panoramica degli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b1dc-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="4b1dc-143">Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b1dc-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="4b1dc-144">Analizzare gli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b1dc-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

