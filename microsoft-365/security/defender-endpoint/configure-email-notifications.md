---
title: Configurare le notifiche di avviso in Microsoft Defender per Endpoint
description: Puoi usare Microsoft Defender per Endpoint per configurare le impostazioni di notifica tramite posta elettronica per gli avvisi di sicurezza, in base alla gravità e ad altri criteri.
keywords: notifiche di posta elettronica, configurare le notifiche di avviso, microsoft defender atp notifiche, avvisi di microsoft defender atp, windows 10 enterprise, windows 10 education
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0d9e63c5d89b13b02dfcf116c1555c8db319d23f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445365"
---
# <a name="configure-alert-notifications-in-microsoft-defender-atp"></a><span data-ttu-id="60576-104">Configurare le notifiche di avviso in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="60576-104">Configure alert notifications in Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="60576-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="60576-105">**Applies to:**</span></span>
- [<span data-ttu-id="60576-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="60576-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="60576-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60576-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="60576-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="60576-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="60576-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="60576-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="60576-110">Puoi configurare Defender per Endpoint per inviare notifiche tramite posta elettronica a destinatari specifici per nuovi avvisi.</span><span class="sxs-lookup"><span data-stu-id="60576-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="60576-111">Questa funzionalità consente di identificare un gruppo di utenti che verranno immediatamente informati e di agire sugli avvisi in base alla gravità.</span><span class="sxs-lookup"><span data-stu-id="60576-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="60576-112">Solo gli utenti con autorizzazioni "Gestisci impostazioni di sicurezza" possono configurare le notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60576-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="60576-113">Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare le notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60576-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="60576-114">Puoi impostare i livelli di gravità degli avvisi che attivano le notifiche.</span><span class="sxs-lookup"><span data-stu-id="60576-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="60576-115">È inoltre possibile aggiungere o rimuovere destinatari della notifica di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60576-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="60576-116">I nuovi destinatari riceveranno una notifica sugli avvisi rilevati dopo l'aggiunta.</span><span class="sxs-lookup"><span data-stu-id="60576-116">New recipients get notified about alerts encountered after they are added.</span></span> <span data-ttu-id="60576-117">Per ulteriori informazioni sugli avvisi, vedere [View and organize the Alerts queue.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="60576-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="60576-118">Se si utilizza il controllo di accesso basato sui ruoli, i destinatari riceveranno solo notifiche basate sui gruppi di dispositivi configurati nella regola di notifica.</span><span class="sxs-lookup"><span data-stu-id="60576-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="60576-119">Gli utenti con l'autorizzazione appropriata possono solo creare, modificare o eliminare notifiche limitate all'ambito di gestione dei gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="60576-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="60576-120">Solo gli utenti assegnati al ruolo amministratore globale possono gestire le regole di notifica configurate per tutti i gruppi di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="60576-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="60576-121">La notifica tramite posta elettronica include informazioni di base sull'avviso e un collegamento al portale in cui è possibile eseguire ulteriori indagini.</span><span class="sxs-lookup"><span data-stu-id="60576-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="60576-122">Creare regole per le notifiche di avviso</span><span class="sxs-lookup"><span data-stu-id="60576-122">Create rules for alert notifications</span></span>
<span data-ttu-id="60576-123">È possibile creare regole che determinano i dispositivi e la gravità degli avvisi per l'invio di notifiche tramite posta elettronica per i destinatari della notifica.</span><span class="sxs-lookup"><span data-stu-id="60576-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="60576-124">Nel riquadro di spostamento selezionare Impostazioni  >  **Notifiche di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="60576-124">In the navigation pane, select **Settings** > **Email notifications**.</span></span>

2. <span data-ttu-id="60576-125">Fare **clic su Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="60576-125">Click **Add item**.</span></span>

3. <span data-ttu-id="60576-126">Specificare le informazioni generali:</span><span class="sxs-lookup"><span data-stu-id="60576-126">Specify the General information:</span></span>
    - <span data-ttu-id="60576-127">**Nome regola:** specificare un nome per la regola di notifica.</span><span class="sxs-lookup"><span data-stu-id="60576-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="60576-128">**Includi nome organizzazione:** specificare il nome del cliente visualizzato nella notifica tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60576-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="60576-129">**Includi collegamento al portale specifico del** tenant - Aggiunge un collegamento con l'ID tenant per consentire l'accesso a un tenant specifico.</span><span class="sxs-lookup"><span data-stu-id="60576-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="60576-130">**Includi informazioni sul dispositivo:** include il nome del dispositivo nel corpo dell'avviso di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60576-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="60576-131">Queste informazioni potrebbero essere elaborate dai server di posta del destinatario che non sono nella posizione geografica selezionata per i dati di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="60576-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="60576-132">**Dispositivi:** scegliere se inviare una notifica ai destinatari per gli avvisi su tutti i dispositivi (solo ruolo amministratore globale) o sui gruppi di dispositivi selezionati.</span><span class="sxs-lookup"><span data-stu-id="60576-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="60576-133">Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="60576-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="60576-134">**Gravità avviso:** scegliere il livello di gravità dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="60576-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="60576-135">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="60576-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="60576-136">Immettere l'indirizzo di posta elettronica del destinatario, quindi fare clic **su Aggiungi destinatario.**</span><span class="sxs-lookup"><span data-stu-id="60576-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="60576-137">È possibile aggiungere più indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60576-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="60576-138">Verificare che i destinatari di posta elettronica siano in grado di ricevere le notifiche tramite posta elettronica selezionando **Invia messaggio di posta elettronica di prova**.</span><span class="sxs-lookup"><span data-stu-id="60576-138">Check that email recipients are able to receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="60576-139">Fare clic **su Salva regola di notifica.**</span><span class="sxs-lookup"><span data-stu-id="60576-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="60576-140">Modificare una regola di notifica</span><span class="sxs-lookup"><span data-stu-id="60576-140">Edit a notification rule</span></span>
1. <span data-ttu-id="60576-141">Seleziona la regola di notifica che vuoi modificare.</span><span class="sxs-lookup"><span data-stu-id="60576-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="60576-142">Aggiornare le informazioni della scheda Generale e Destinatario.</span><span class="sxs-lookup"><span data-stu-id="60576-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="60576-143">Fare clic **su Salva regola di notifica.**</span><span class="sxs-lookup"><span data-stu-id="60576-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="60576-144">Elimina regola di notifica</span><span class="sxs-lookup"><span data-stu-id="60576-144">Delete notification rule</span></span>

1. <span data-ttu-id="60576-145">Seleziona la regola di notifica che vuoi eliminare.</span><span class="sxs-lookup"><span data-stu-id="60576-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="60576-146">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="60576-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="60576-147">Risolvere i problemi relativi alle notifiche di posta elettronica per gli avvisi</span><span class="sxs-lookup"><span data-stu-id="60576-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="60576-148">In questa sezione sono elencati i vari problemi che possono verificarsi quando si utilizzano le notifiche tramite posta elettronica per gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="60576-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="60576-149">**Problema:** I destinatari previsti segnalano di non ricevere le notifiche.</span><span class="sxs-lookup"><span data-stu-id="60576-149">**Problem:** Intended recipients report they are not getting the notifications.</span></span>

<span data-ttu-id="60576-150">**Soluzione:** Assicurarsi che le notifiche non siano bloccate dai filtri di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="60576-150">**Solution:** Make sure that the notifications are not blocked by email filters:</span></span>

1. <span data-ttu-id="60576-151">Verificare che le notifiche di posta elettronica di Defender for Endpoint non siano inviate alla cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="60576-151">Check that the Defender for Endpoint email notifications are not sent to the Junk Email folder.</span></span> <span data-ttu-id="60576-152">Contrassegnarli come Non indesiderati.</span><span class="sxs-lookup"><span data-stu-id="60576-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="60576-153">Verificare che il prodotto di sicurezza della posta elettronica non blocchi le notifiche di posta elettronica da Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="60576-153">Check that your email security product is not blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="60576-154">Controlla le regole dell'applicazione di posta elettronica che potrebbero intercettare e spostare defender per le notifiche di posta elettronica dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="60576-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="60576-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="60576-155">Related topics</span></span>
- [<span data-ttu-id="60576-156">Aggiornare le impostazioni di conservazione dei dati</span><span class="sxs-lookup"><span data-stu-id="60576-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="60576-157">Configurare le funzionalità avanzate</span><span class="sxs-lookup"><span data-stu-id="60576-157">Configure advanced features</span></span>](advanced-features.md)