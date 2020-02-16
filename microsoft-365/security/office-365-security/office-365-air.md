---
title: Analizzare e rispondere automaticamente alle minacce in Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Iniziare a utilizzare le funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d45141ce671a4615cb4fd550e36bc7215cd38d51
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088315"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="d3185-104">Analizzare e rispondere automaticamente alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="d3185-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="d3185-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d3185-105">Overview</span></span>

<span data-ttu-id="d3185-106">A seconda dell'abbonamento, la [protezione avanzata dalle minacce di Office 365](office-365-atp.md) può includere funzionalità di analisi e risposta automatizzate in grado di salvare il tempo e lo sforzo del team per le operazioni di sicurezza per gestire gli avvisi e le minacce.</span><span class="sxs-lookup"><span data-stu-id="d3185-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="d3185-107">Per iniziare a usare le funzionalità di analisi e risposta automatizzate in Office 365, utilizzare questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d3185-107">To get started using automated investigation and response capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="d3185-108">Per ottenere una panoramica di come funziona, vedere [Automatic Investigation and Response in Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="d3185-108">To get an overview of how it works, see [Automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

> [!TIP]
> <span data-ttu-id="d3185-109">Si possiedono Microsoft 365 E5 o Microsoft 365 E3 con identità e protezione dalle minacce?</span><span class="sxs-lookup"><span data-stu-id="d3185-109">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="d3185-110">Valutare la possibilità di provare l' [analisi automatizzata e la risposta (Air) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="d3185-110">Consider trying [Automated investigation and response (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span></span>

<span data-ttu-id="d3185-111">Con le funzionalità di analisi e risposta automatizzate, quando vengono attivati determinati avvisi, vengono avviati uno o più schemi di sicurezza e il processo di analisi automatizzato inizia.</span><span class="sxs-lookup"><span data-stu-id="d3185-111">With automated investigation and response capabilities, when certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="d3185-112">Durante e dopo un processo di analisi automatizzato, il team di sicurezza può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3185-112">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="d3185-113">Visualizzare i dettagli di un'indagine</span><span class="sxs-lookup"><span data-stu-id="d3185-113">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="d3185-114">Esaminare e approvare le azioni in seguito a un'indagine</span><span class="sxs-lookup"><span data-stu-id="d3185-114">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="d3185-115">Visualizzare i dettagli relativi a un avviso relativo a un'indagine</span><span class="sxs-lookup"><span data-stu-id="d3185-115">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> <span data-ttu-id="d3185-116">Per eseguire le attività descritte in questo articolo, è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="d3185-116">To perform the tasks described in this article, you must have appropriate permissions assigned.</span></span> <span data-ttu-id="d3185-117">Vedere le [autorizzazioni necessarie per utilizzare le funzionalità aeree](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="d3185-117">See [required permissions to use AIR capabilities](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="d3185-118">Visualizzare i dettagli di un'indagine</span><span class="sxs-lookup"><span data-stu-id="d3185-118">View details of an investigation</span></span>

1. <span data-ttu-id="d3185-119">Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d3185-119">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="d3185-120">Questo porta al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="d3185-120">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="d3185-121">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3185-121">Do one of the following:</span></span>

    - <span data-ttu-id="d3185-122">Andare al > **Dashboard**di **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="d3185-122">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="d3185-123">Questo porta al dashboard di [sicurezza](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="d3185-123">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="d3185-124">I widget aria vengono visualizzati nella parte superiore del [dashboard di sicurezza](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="d3185-124">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="d3185-125">Selezionare un widget, ad esempio **Riepilogo indagini**.</span><span class="sxs-lookup"><span data-stu-id="d3185-125">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="d3185-126">Andare a > **indagini**sulla **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="d3185-126">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="d3185-127">Entrambi i metodi consentono di eseguire l'elenco delle indagini.</span><span class="sxs-lookup"><span data-stu-id="d3185-127">Either method takes you to a list of investigations.</span></span>

    ![Pagina di ricerca principale per AIR](../../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="d3185-129">Nell'elenco delle indagini selezionare un elemento nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="d3185-129">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="d3185-130">Verrà visualizzata la pagina Dettagli analisi, a partire dal grafico di analisi in visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="d3185-130">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Pagina del grafico dell'indagine aerea](../../media/air-investigationgraphpage.png)

4. <span data-ttu-id="d3185-132">Utilizzare le varie schede per ulteriori informazioni sull'indagine.</span><span class="sxs-lookup"><span data-stu-id="d3185-132">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="d3185-133">Esaminare e approvare le azioni</span><span class="sxs-lookup"><span data-stu-id="d3185-133">Review and approve actions</span></span>

<span data-ttu-id="d3185-134">In Office 365, le indagini automatizzate in genere determinano una o più azioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="d3185-134">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="d3185-135">Tuttavia, non vengono eseguite azioni finché non vengono approvate dal team di operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d3185-135">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="d3185-136">Utilizzare la procedura seguente per esaminare e approvare le azioni.</span><span class="sxs-lookup"><span data-stu-id="d3185-136">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="d3185-137">Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d3185-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="d3185-138">Andare a > **indagini**sulla **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="d3185-138">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="d3185-139">Nell'elenco delle indagini selezionare un elemento nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="d3185-139">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="d3185-140">Nella visualizzazione dettagli analisi selezionare la scheda **azioni** . Tutte le azioni che sono in attesa di approvazione sono elencate qui.</span><span class="sxs-lookup"><span data-stu-id="d3185-140">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="d3185-141">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d3185-141">Select an item in the list.</span></span>

5. <span data-ttu-id="d3185-142">Selezionare **approva** per eseguire l'azione consigliata (o **rifiuta** per chiudere l'inchiesta senza intervenire).</span><span class="sxs-lookup"><span data-stu-id="d3185-142">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="d3185-143">Visualizzare i dettagli relativi a un avviso relativo a un'indagine</span><span class="sxs-lookup"><span data-stu-id="d3185-143">View details about an alert related to an investigation</span></span>

<span data-ttu-id="d3185-144">Alcuni tipi di avvisi attivano l'analisi automatizzata in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3185-144">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="d3185-145">Per ulteriori informazioni, vedere [Alerts](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="d3185-145">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="d3185-146">Utilizzare la procedura seguente per visualizzare i dettagli relativi a un avviso associato a un'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="d3185-146">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="d3185-147">Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d3185-147">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="d3185-148">Questo porta al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="d3185-148">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="d3185-149">Andare a > **indagini**sulla **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="d3185-149">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="d3185-150">Nell'elenco delle indagini selezionare un elemento nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="d3185-150">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="d3185-151">Per informazioni dettagliate sull'apertura di un'indagine, selezionare la scheda **avvisi** . Tutti gli avvisi che hanno attivato l'indagine sono elencati qui.</span><span class="sxs-lookup"><span data-stu-id="d3185-151">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="d3185-152">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d3185-152">Select an item in the list.</span></span> <span data-ttu-id="d3185-153">Verrà aperto un riquadro a comparsa con informazioni dettagliate sull'avviso e collegamenti a ulteriori operazioni.</span><span class="sxs-lookup"><span data-stu-id="d3185-153">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="d3185-154">Esaminare le informazioni nel riquadro a comparsa e, a seconda dell'avviso specifico, eseguire un'azione, ad esempio **risolvere**, **sopprimere**o **informare gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="d3185-154">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="d3185-155">La **risoluzione** equivale alla chiusura di un avviso</span><span class="sxs-lookup"><span data-stu-id="d3185-155">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="d3185-156">Non **consente a** un criterio di attivare avvisi per un determinato periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="d3185-156">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="d3185-157">**Notify gli utenti** avviano un messaggio di posta elettronica con gli indirizzi di posta elettronica degli utenti già immessi e consentono al team di operazioni di sicurezza di digitare un testo per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d3185-157">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="d3185-158">(Analogo all'invio di un messaggio ai destinatari tramite [Esplora minacce](threat-explorer.md)).</span><span class="sxs-lookup"><span data-stu-id="d3185-158">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="d3185-159">Utilizzare l'API di attività di gestione di Office 365 per soluzioni di Reporting personalizzate o di terze parti</span><span class="sxs-lookup"><span data-stu-id="d3185-159">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="d3185-160">Se l'organizzazione utilizza una soluzione di report personalizzata o di terze parti, è possibile visualizzare le informazioni sulle indagini automatizzate in tale soluzione utilizzando l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3185-160">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="d3185-161">Per impostare questa impostazione, utilizzare le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3185-161">Use the following resources to set this up:</span></span>

|<span data-ttu-id="d3185-162">Risorsa</span><span class="sxs-lookup"><span data-stu-id="d3185-162">Resource</span></span>  |<span data-ttu-id="d3185-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3185-163">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="d3185-164">Panoramica delle API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="d3185-164">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="d3185-165">L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Office 365 e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d3185-165">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="d3185-166">Iniziare a utilizzare le API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="d3185-166">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="d3185-167">L'API di gestione di Office 365 utilizza Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3185-167">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="d3185-168">Seguire la procedura descritta in questo articolo per configurare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d3185-168">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="d3185-169">Guida di riferimento all'API dell'attività di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="d3185-169">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="d3185-170">È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare le informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Office 365 e Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d3185-170">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="d3185-171">Leggere questo articolo per ulteriori informazioni su come funziona.</span><span class="sxs-lookup"><span data-stu-id="d3185-171">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="d3185-172">Schema API di attività di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="d3185-172">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="d3185-173">Ottenere una panoramica dello [schema comune](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e dello [schema di analisi e risposta di Office 365 ATP and Threat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) per informazioni su tipi specifici di dati disponibili tramite l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3185-173">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="d3185-174">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d3185-174">Next steps</span></span>

- [<span data-ttu-id="d3185-175">Informazioni su come ottenere l'aria e vedere le autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="d3185-175">Find out how to get AIR and see required permissions</span></span>](automated-investigation-response-office.md#how-to-get-air)
- [<span data-ttu-id="d3185-176">Ulteriori informazioni sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="d3185-176">Learn more about alerts</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="d3185-177">Trovare e studiare manualmente messaggi di posta elettronica dannosi che sono stati recapitati in Office 365</span><span class="sxs-lookup"><span data-stu-id="d3185-177">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="d3185-178">Informazioni su AIR in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d3185-178">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="d3185-179">Visitare la Guida di orientamento di Microsoft 365 per vedere cosa succederà tra breve e in uscita</span><span class="sxs-lookup"><span data-stu-id="d3185-179">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
