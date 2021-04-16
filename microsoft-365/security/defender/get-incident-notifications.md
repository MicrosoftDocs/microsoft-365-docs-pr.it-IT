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
ms.openlocfilehash: 72a1f8fe71efcfa7f4f73671611576a454b508e6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861318"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="71476-104">Ricevere notifiche di eventi imprevisti tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="71476-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="71476-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="71476-105">**Applies to:**</span></span>
- <span data-ttu-id="71476-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71476-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="71476-107">Puoi configurare Microsoft 365 Defender per informare il personale con un messaggio di posta elettronica di nuovi eventi imprevisti o aggiornamenti di eventi imprevisti esistenti.</span><span class="sxs-lookup"><span data-stu-id="71476-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="71476-108">Puoi scegliere di ricevere notifiche in base a:</span><span class="sxs-lookup"><span data-stu-id="71476-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="71476-109">Gravità dell'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="71476-109">Incident severity.</span></span>
- <span data-ttu-id="71476-110">Gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="71476-110">Device group.</span></span>
- <span data-ttu-id="71476-111">Solo al primo aggiornamento per evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="71476-111">Only on the first update per incident.</span></span>

<span data-ttu-id="71476-112">La notifica di posta elettronica contiene dettagli importanti sull'evento imprevisto, ad esempio il nome, la gravità e le categorie dell'evento imprevisto, tra gli altri.</span><span class="sxs-lookup"><span data-stu-id="71476-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="71476-113">Puoi anche passare direttamente all'incidente e avviare subito l'indagine.</span><span class="sxs-lookup"><span data-stu-id="71476-113">You can also go directly to the incident and start your investigation right away.</span></span> <span data-ttu-id="71476-114">Per ulteriori informazioni, vedere [Investigate incidents](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="71476-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="71476-115">È possibile aggiungere o rimuovere destinatari nelle notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="71476-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="71476-116">Dopo l'aggiunta, i nuovi destinatari riceveranno una notifica sugli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="71476-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="71476-117">È necessaria l'autorizzazione "Gestisci impostazioni di sicurezza" per configurare le impostazioni di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="71476-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="71476-118">Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare automaticamente le notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="71476-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="71476-119">Allo stesso modo, se l'organizzazione utilizza il controllo di accesso basato sui ruoli(RBAC), è possibile creare, modificare, eliminare e ricevere notifiche in base ai gruppi di dispositivi che sono autorizzati a gestire.</span><span class="sxs-lookup"><span data-stu-id="71476-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="71476-120">Creare una regola per le notifiche di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="71476-120">Create a rule for email notifications</span></span>

<span data-ttu-id="71476-121">Seguire questa procedura per creare una nuova regola e personalizzare le impostazioni di notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="71476-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="71476-122">Nel riquadro di spostamento seleziona Impostazioni > notifiche di posta elettronica di **Microsoft 365 Defender > eventi imprevisti**.</span><span class="sxs-lookup"><span data-stu-id="71476-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="71476-123">Selezionare **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="71476-123">Select **Add item**.</span></span>
3. <span data-ttu-id="71476-124">Nella pagina **Nozioni di** base digitare il nome della regola e una descrizione e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="71476-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="71476-125">Nella pagina **Impostazioni notifica** configurare:</span><span class="sxs-lookup"><span data-stu-id="71476-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="71476-126">**Gravità avviso:** scegliere le gravità dell'avviso che attiveranno una notifica di evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="71476-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="71476-127">Ad esempio, se si desidera essere informati solo su eventi imprevisti di gravità elevata, selezionare **Alta**.</span><span class="sxs-lookup"><span data-stu-id="71476-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="71476-128">**Ambito del gruppo di** dispositivi- È possibile specificare tutti i gruppi di dispositivi o selezionarli dall'elenco dei gruppi di dispositivi nel tenant.</span><span class="sxs-lookup"><span data-stu-id="71476-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="71476-129">**Notifica solo alla prima occorrenza per evento** imprevisto: selezionare se si desidera una notifica solo sul primo avviso corrispondente alle altre selezioni.</span><span class="sxs-lookup"><span data-stu-id="71476-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="71476-130">Gli aggiornamenti o gli avvisi successivi correlati all'evento imprevisto non invierà notifiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="71476-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="71476-131">**Includi il nome dell'organizzazione nel messaggio** di posta elettronica- Selezionare se si desidera che il nome dell'organizzazione venga visualizzato nella notifica di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="71476-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="71476-132">**Includi collegamento al portale specifico del** tenant: selezionare se si desidera aggiungere un collegamento con l'ID tenant nella notifica di posta elettronica per l'accesso a un tenant di Microsoft 365 specifico.</span><span class="sxs-lookup"><span data-stu-id="71476-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Impostazioni di notifica per le notifiche di posta elettronica degli eventi imprevisti":::

5. <span data-ttu-id="71476-134">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="71476-134">Select **Next**.</span></span> <span data-ttu-id="71476-135">Nella pagina **Destinatari** aggiungere gli indirizzi di posta elettronica che riceveranno le notifiche degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="71476-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="71476-136">Selezionare **Aggiungi dopo** aver digitato ogni nuovo indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="71476-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="71476-137">Per testare le notifiche e assicurarsi che i destinatari le ricevano nelle cartelle Posta in arrivo, selezionare **Invia messaggio di posta elettronica di prova.**</span><span class="sxs-lookup"><span data-stu-id="71476-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="71476-138">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="71476-138">Select **Next**.</span></span> <span data-ttu-id="71476-139">Nella pagina **Verifica regola** esaminare le impostazioni della regola e quindi selezionare **Crea regola.**</span><span class="sxs-lookup"><span data-stu-id="71476-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="71476-140">I destinatari inizieranno a ricevere notifiche di eventi imprevisti tramite posta elettronica in base alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="71476-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="71476-141">Per modificare una regola esistente, selezionarla nell'elenco delle regole.</span><span class="sxs-lookup"><span data-stu-id="71476-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="71476-142">Nel riquadro con il nome  della regola selezionare Modifica regola e apportare le modifiche nelle pagine Nozioni di **base,** Impostazioni di **notifica** **e** Destinatari.</span><span class="sxs-lookup"><span data-stu-id="71476-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="71476-143">Per modificare una regola esistente, selezionarla nell'elenco delle regole.</span><span class="sxs-lookup"><span data-stu-id="71476-143">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="71476-144">Nel riquadro con il nome della regola selezionare **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="71476-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="71476-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71476-145">See also</span></span>
- [<span data-ttu-id="71476-146">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="71476-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="71476-147">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="71476-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="71476-148">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="71476-148">Investigate incidents</span></span>](investigate-incidents.md)
