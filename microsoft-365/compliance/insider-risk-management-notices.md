---
title: Modelli di avviso per la gestione dei rischi Insider
description: Informazioni sui modelli di avviso per la gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0211eefe3c4a946bbaa4ad4c8c66e5df7b37091e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199489"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="3f9fa-104">Modelli di avviso per la gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="3f9fa-104">Insider risk management notice templates</span></span>

<span data-ttu-id="3f9fa-105">I modelli di avviso per la gestione dei rischi Insider consentono di inviare messaggi di posta elettronica agli utenti quando le attività generano un criterio di corrispondenza e avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="3f9fa-106">Nella maggior parte dei casi, le azioni degli utenti che generano avvisi sono il risultato di errori o attività involontarie senza intenti.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="3f9fa-107">Gli avvisi fungono da promemoria semplici per gli utenti per essere più cauti, per fornire collegamenti alle informazioni per l'aggiornamento, o per le risorse dei criteri aziendali.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="3f9fa-108">Gli avvisi possono essere una parte importante del programma di formazione per la conformità interno e possono contribuire alla creazione di una traccia di controllo documentata per gli utenti con attività di rischio ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="3f9fa-109">Creare modelli di avviso se si desidera inviare agli utenti una notifica di promemoria tramite posta elettronica per le corrispondenze di criteri nell'ambito del processo di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="3f9fa-110">Gli avvisi possono essere inviati solo all'indirizzo di posta elettronica dell'utente associato all'avviso specifico in fase di revisione.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="3f9fa-111">Quando si seleziona un modello di avviso da applicare a una corrispondenza di criteri, è possibile scegliere di accettare i valori del campo definiti nel modello o sovrascrivere i campi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="3f9fa-112">Dashboard modelli di avviso</span><span class="sxs-lookup"><span data-stu-id="3f9fa-112">Notice templates dashboard</span></span>

<span data-ttu-id="3f9fa-113">Il **dashboard dei modelli di avviso** Visualizza un elenco di modelli di avviso configurati e consente di creare nuovi modelli di avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="3f9fa-114">I modelli di avviso sono elencati nell'ordine di data inverso con il modello di avviso più recente elencato per primo.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Dashboard del modello di avviso gestione dei rischi Insider](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="3f9fa-116">HTML per gli avvisi</span><span class="sxs-lookup"><span data-stu-id="3f9fa-116">HTML for notices</span></span>

<span data-ttu-id="3f9fa-117">Se si desidera creare più di un semplice messaggio di posta elettronica basato su testo per le notifiche, è possibile creare un messaggio più dettagliato utilizzando HTML nel campo corpo del messaggio di un modello di avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="3f9fa-118">Nell'esempio seguente viene fornito il formato del corpo del messaggio per un modello di notifica di posta elettronica basato su HTML:</span><span class="sxs-lookup"><span data-stu-id="3f9fa-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="3f9fa-119">L'implementazione dell'attributo HTML href nei modelli di avviso per la gestione dei rischi Insider attualmente supporta solo virgolette singole anziché virgolette doppie per i riferimenti URL.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="3f9fa-120">Creare un nuovo modello di avviso</span><span class="sxs-lookup"><span data-stu-id="3f9fa-120">Create a new notice template</span></span>

<span data-ttu-id="3f9fa-121">Per creare un nuovo modello di avviso per la gestione dei rischi Insider, è possibile utilizzare la procedura guidata di avviso nella soluzione di **gestione dei rischi Insider** nel centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="3f9fa-122">Completare la procedura seguente per creare un nuovo modello di avviso per la gestione dei rischi Insider:</span><span class="sxs-lookup"><span data-stu-id="3f9fa-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="3f9fa-123">Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **modelli di avviso** .</span><span class="sxs-lookup"><span data-stu-id="3f9fa-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="3f9fa-124">Selezionare **Crea modello di avviso** per aprire la procedura guidata di avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="3f9fa-125">Nella pagina **Crea un nuovo modello di avviso** completare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="3f9fa-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="3f9fa-126">**Nome modello**: immettere un nome descrittivo per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="3f9fa-127">Questo nome viene visualizzato nell'elenco delle notifiche nel dashboard di avviso e nell'elenco di selezione delle notifiche quando si inviano notifiche da un caso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="3f9fa-128">**Invia da**: immettere l'indirizzo di posta elettronica del mittente per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="3f9fa-129">Questo indirizzo verrà visualizzato nel campo **da:** in tutti gli avvisi inviati agli utenti, a meno che non siano stati modificati quando si invia un avviso da un caso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="3f9fa-130">Campi **CC e Ccn** : utenti facoltativi o gruppi da notificare della corrispondenza dei criteri, selezionati da Active Directory per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="3f9fa-131">**Oggetto**: le informazioni visualizzate nella riga dell'oggetto del messaggio supportano caratteri di testo.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="3f9fa-132">**Corpo del messaggio**: informazioni visualizzate nel corpo del messaggio, che supportano i valori di testo o HTML.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="3f9fa-133">Selezionare **Crea** per creare e salvare il modello di avviso oppure fare clic su **Annulla** per chiudere senza salvare il modello di avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="3f9fa-134">Aggiornare un modello di avviso</span><span class="sxs-lookup"><span data-stu-id="3f9fa-134">Update a notice template</span></span>

<span data-ttu-id="3f9fa-135">Per aggiornare un modello di avviso per la gestione dei rischi Insider esistente, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f9fa-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="3f9fa-136">Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **modelli di avviso** .</span><span class="sxs-lookup"><span data-stu-id="3f9fa-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="3f9fa-137">Nel dashboard di avviso selezionare il modello di avviso che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="3f9fa-138">Nella pagina Dettagli avviso selezionare **modifica**</span><span class="sxs-lookup"><span data-stu-id="3f9fa-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="3f9fa-139">Nella pagina **modifica** è possibile modificare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f9fa-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="3f9fa-140">**Nome modello**: immettere un nuovo nome descrittivo per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="3f9fa-141">Questo nome viene visualizzato nell'elenco delle notifiche nel dashboard di avviso e nell'elenco di selezione delle notifiche quando si inviano notifiche da un caso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="3f9fa-142">**Invia da**: aggiornare l'indirizzo di posta elettronica del mittente per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="3f9fa-143">Questo indirizzo verrà visualizzato nel campo **da:** in tutti gli avvisi inviati agli utenti, a meno che non siano stati modificati quando si invia un avviso da un caso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="3f9fa-144">Campi **CC e Ccn** : aggiornare gli utenti o i gruppi facoltativi da notificare la corrispondenza dei criteri, selezionata da Active Directory per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="3f9fa-145">**Oggetto**: aggiornare le informazioni visualizzate nella riga dell'oggetto del messaggio, che supportano caratteri di testo.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="3f9fa-146">**Corpo del messaggio**: aggiornare le informazioni visualizzate nel corpo del messaggio, supporta i valori di testo o HTML.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="3f9fa-147">Selezionare **Salva** per aggiornare e salvare l'avviso oppure fare clic su **Annulla** per chiudere senza salvare il modello di avviso.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="3f9fa-148">Eliminare un modello di avviso</span><span class="sxs-lookup"><span data-stu-id="3f9fa-148">Delete a notice template</span></span>

<span data-ttu-id="3f9fa-149">Per eliminare un modello di avviso per la gestione dei rischi Insider esistente, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f9fa-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="3f9fa-150">Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **modelli di avviso** .</span><span class="sxs-lookup"><span data-stu-id="3f9fa-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="3f9fa-151">Nel dashboard di avviso selezionare il modello di avviso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="3f9fa-152">Selezionare l'icona **Elimina** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="3f9fa-153">Per eliminare il modello di avviso, selezionare **Sì** nella finestra di dialogo Elimina.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="3f9fa-154">Per annullare l'eliminazione, selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="3f9fa-154">To cancel the deletion, select **Cancel**.</span></span>
