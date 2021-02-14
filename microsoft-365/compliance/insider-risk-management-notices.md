---
title: Modelli di avviso per la gestione dei rischi Insider
description: Informazioni sui modelli di avviso per la gestione dei rischi Insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416480"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="d6efc-104">Modelli di avviso per la gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="d6efc-104">Insider risk management notice templates</span></span>

<span data-ttu-id="d6efc-105">I modelli di avviso per la gestione dei rischi Insider consentono di inviare messaggi di posta elettronica agli utenti quando le loro attività generano una corrispondenza e un avviso dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d6efc-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="d6efc-106">Nella maggior parte dei casi, le azioni degli utenti che generano avvisi sono il risultato di errori o attività accidentali senza intento sbagliato.</span><span class="sxs-lookup"><span data-stu-id="d6efc-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="d6efc-107">Gli avvisi fungono da semplici promemoria per gli utenti per prestare maggiore attenzione, per fornire collegamenti a informazioni per la formazione sugli aggiornamenti o per le risorse dei criteri aziendali.</span><span class="sxs-lookup"><span data-stu-id="d6efc-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="d6efc-108">Le comunicazioni possono essere una parte importante del programma di formazione sulla conformità interna e possono contribuire a creare un audit trail documentato per gli utenti con attività di rischio ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="d6efc-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="d6efc-109">Creare modelli di avviso se si desidera inviare agli utenti un avviso di promemoria tramite posta elettronica per le corrispondenze dei criteri nell'ambito del processo di risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="d6efc-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="d6efc-110">Le notifiche possono essere inviate solo all'indirizzo di posta elettronica dell'utente associato all'avviso specifico da esaminare.</span><span class="sxs-lookup"><span data-stu-id="d6efc-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="d6efc-111">Quando si seleziona un modello di avviso da applicare a una corrispondenza dei criteri, è possibile scegliere di accettare i valori dei campi definiti nel modello o sovrascrivere i campi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d6efc-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="d6efc-112">Dashboard dei modelli di avviso</span><span class="sxs-lookup"><span data-stu-id="d6efc-112">Notice templates dashboard</span></span>

<span data-ttu-id="d6efc-113">Il **dashboard dei modelli di** avviso visualizza un elenco di modelli di avviso configurati e consente di creare nuovi modelli di avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="d6efc-114">I modelli di avviso sono elencati in ordine inverso con il modello di avviso più recente elencato per primo.</span><span class="sxs-lookup"><span data-stu-id="d6efc-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Dashboard del modello di avviso per la gestione dei rischi Insider](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="d6efc-116">HTML per gli avvisi</span><span class="sxs-lookup"><span data-stu-id="d6efc-116">HTML for notices</span></span>

<span data-ttu-id="d6efc-117">Se si desidera creare più di un semplice messaggio di posta elettronica basato su testo per le notifiche, è possibile creare un messaggio più dettagliato utilizzando HTML nel campo corpo del messaggio di un modello di avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="d6efc-118">Nell'esempio seguente viene fornito il formato del corpo del messaggio per un modello di notifica di posta elettronica basato su HTML di base:</span><span class="sxs-lookup"><span data-stu-id="d6efc-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

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
> <span data-ttu-id="d6efc-119">L'implementazione dell'attributo href HTML nei modelli di avviso per la gestione dei rischi Insider attualmente supporta solo le virgolette singole anziché le virgolette doppie per i riferimenti URL.</span><span class="sxs-lookup"><span data-stu-id="d6efc-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="d6efc-120">Creare un nuovo modello di avviso</span><span class="sxs-lookup"><span data-stu-id="d6efc-120">Create a new notice template</span></span>

<span data-ttu-id="d6efc-121">Per creare un nuovo modello di avviso per la gestione dei rischi Insider, si userà la procedura guidata di avviso nella soluzione di gestione dei rischi **Insider** nel Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6efc-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="d6efc-122">Completare la procedura seguente per creare un nuovo modello di avviso per la gestione dei rischi Insider:</span><span class="sxs-lookup"><span data-stu-id="d6efc-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="d6efc-123">Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda Modelli **di** avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="d6efc-124">Selezionare **Crea modello di avviso** per aprire la procedura guidata di avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="d6efc-125">Nella pagina **Crea un nuovo modello di avviso** completare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6efc-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="d6efc-126">**Nome modello:** immettere un nome descrittivo per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="d6efc-127">Questo nome viene visualizzato nell'elenco degli avvisi nel dashboard degli avvisi e nell'elenco di selezione degli avvisi quando si inviano avvisi da un caso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="d6efc-128">**Invia da:** immettere l'indirizzo di posta elettronica del mittente per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="d6efc-129">Questo indirizzo verrà visualizzato nel campo **Da:** in tutti gli avvisi inviati agli utenti, a meno che non venga modificato quando si invia un avviso da un caso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="d6efc-130">**Campi Cc e Ccn:** utenti o gruppi facoltativi a cui notificare la corrispondenza ai criteri, selezionati da Active Directory per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="d6efc-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="d6efc-131">**Oggetto:** le informazioni visualizzate nella riga dell'oggetto del messaggio supportano i caratteri di testo.</span><span class="sxs-lookup"><span data-stu-id="d6efc-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="d6efc-132">**Corpo del** messaggio: informazioni visualizzate nel corpo del messaggio, che supportano testo o valori HTML.</span><span class="sxs-lookup"><span data-stu-id="d6efc-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="d6efc-133">Selezionare **Crea** per creare e salvare il modello di avviso oppure **scegliere** Annulla per chiudere senza salvare il modello di avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="d6efc-134">Aggiornare un modello di avviso</span><span class="sxs-lookup"><span data-stu-id="d6efc-134">Update a notice template</span></span>

<span data-ttu-id="d6efc-135">Per aggiornare un modello di avviso per la gestione dei rischi Insider esistente, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6efc-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="d6efc-136">Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda Modelli **di** avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="d6efc-137">Nel dashboard dell'avviso selezionare il modello di avviso che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="d6efc-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="d6efc-138">Nella pagina dei dettagli dell'avviso, selezionare **Modifica**</span><span class="sxs-lookup"><span data-stu-id="d6efc-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="d6efc-139">Nella pagina **Modifica** è possibile modificare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6efc-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="d6efc-140">**Nome modello:** immettere un nuovo nome descrittivo per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="d6efc-141">Questo nome viene visualizzato nell'elenco degli avvisi nel dashboard degli avvisi e nell'elenco di selezione degli avvisi quando si inviano avvisi da un caso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="d6efc-142">**Invia da:** aggiornare l'indirizzo di posta elettronica del mittente per l'avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="d6efc-143">Questo indirizzo verrà visualizzato nel campo **Da:** in tutti gli avvisi inviati agli utenti, a meno che non venga modificato quando si invia un avviso da un caso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="d6efc-144">**Campi Cc e Ccn:** aggiornare gli utenti o i gruppi facoltativi per ricevere una notifica della corrispondenza dei criteri, selezionata da Active Directory per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="d6efc-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="d6efc-145">**Oggetto:** le informazioni di aggiornamento visualizzate nella riga dell'oggetto del messaggio supportano i caratteri di testo.</span><span class="sxs-lookup"><span data-stu-id="d6efc-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="d6efc-146">**Corpo del** messaggio: aggiorna le informazioni visualizzate nel corpo del messaggio, supporta testo o valori HTML.</span><span class="sxs-lookup"><span data-stu-id="d6efc-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="d6efc-147">Selezionare **Salva** per aggiornare e salvare l'avviso oppure scegliere **Annulla** per chiudere senza salvare il modello di avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="d6efc-148">Eliminare un modello di avviso</span><span class="sxs-lookup"><span data-stu-id="d6efc-148">Delete a notice template</span></span>

<span data-ttu-id="d6efc-149">Per eliminare un modello di avviso per la gestione dei rischi Insider esistente, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="d6efc-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="d6efc-150">Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda Modelli **di** avviso.</span><span class="sxs-lookup"><span data-stu-id="d6efc-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="d6efc-151">Nel dashboard dell'avviso selezionare il modello di avviso che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="d6efc-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="d6efc-152">Selezionare **l'icona** Elimina sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="d6efc-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="d6efc-153">Per eliminare il modello di avviso, selezionare **Sì** nella finestra di dialogo di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d6efc-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="d6efc-154">Per annullare l'eliminazione, selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="d6efc-154">To cancel the deletion, select **Cancel**.</span></span>
