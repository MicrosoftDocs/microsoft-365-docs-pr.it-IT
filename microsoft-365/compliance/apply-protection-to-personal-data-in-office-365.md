---
title: Applicare protezione ai dati personali in Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come usare i criteri DLP per proteggere i dati personali in Office 365.
ms.openlocfilehash: 12d6de9b8012062e26daec922d5c55fa0f52381a
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "38708139"
---
# <a name="apply-protection-to-personal-data-in-office-365"></a><span data-ttu-id="d81c9-103">Applicare protezione ai dati personali in Office 365</span><span class="sxs-lookup"><span data-stu-id="d81c9-103">Apply protection to personal data in Office 365</span></span>

<span data-ttu-id="d81c9-104">La protezione delle informazioni personali in Office 365 include l'uso delle funzionalità di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="d81c9-104">Protection of personal information in Office 365 includes using data loss prevention capabilities.</span></span> <span data-ttu-id="d81c9-105">I criteri di prevenzione della perdita dei dati del centro conformità permettono di identificare, monitorare e proteggere automaticamente le informazioni sensibili in tutto Office 365.</span><span class="sxs-lookup"><span data-stu-id="d81c9-105">With data loss prevention (DLP) policies in the compliance center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="d81c9-p102">In questo argomento viene descritto come usare la prevenzione della perdita dei dati per proteggere i dati personali. Inoltre, vengono elencate altre funzionalità di protezione che possono essere usate per raggiungere la conformità con il GDPR, tra cui l'impostazione delle autorizzazioni nelle raccolte di SharePoint e l'uso di criteri di accesso ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p102">This topic describes how to use DLP to protect personal data. This topic also lists other protection capabilities that can be used to achieve GDPR compliance, including setting permissions in SharePoint libraries and using device access policies.</span></span>

## <a name="apply-protection-using-data-loss-prevention-in-office-365"></a><span data-ttu-id="d81c9-108">Applicare la protezione utilizzando la prevenzione della perdita di dati in Office 365</span><span class="sxs-lookup"><span data-stu-id="d81c9-108">Apply protection using data loss prevention in Office 365</span></span>

<span data-ttu-id="d81c9-109">Con DLP, è possibile:</span><span class="sxs-lookup"><span data-stu-id="d81c9-109">With DLP, you can:</span></span>

-   <span data-ttu-id="d81c9-110">Identificare informazioni riservate in più percorsi.</span><span class="sxs-lookup"><span data-stu-id="d81c9-110">Identify sensitive information across many locations.</span></span>

-   <span data-ttu-id="d81c9-111">Impedire la condivisione accidentale di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="d81c9-111">Prevent accidental sharing of sensitive information.</span></span>

-   <span data-ttu-id="d81c9-112">Fornire agli utenti informazioni su come garantire la conformità senza interrompere il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d81c9-112">Help users learn how to stay compliant without interrupting their workflow.</span></span>

-   <span data-ttu-id="d81c9-113">Visualizzare report DLP che indicano i contenuti corrispondenti ai criteri DLP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-113">View DLP reports showing content that matches your organization’s DLP policies.</span></span>

<span data-ttu-id="d81c9-114">Per ulteriori informazioni, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span><span class="sxs-lookup"><span data-stu-id="d81c9-114">For more information, see [Overview of data loss prevention policies](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span></span>

![Opzioni per la creazione del criterio DLP](Media/Apply-protection-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="d81c9-116">L'illustrazione seguente mostra le opzioni per la creazione di un criterio DLP:</span><span class="sxs-lookup"><span data-stu-id="d81c9-116">This illustration shows the options for creating a DLP policy:</span></span>

-   <span data-ttu-id="d81c9-p103">Scegliere la protezione da applicare. La protezione può includere:</span><span class="sxs-lookup"><span data-stu-id="d81c9-p103">Choose the protection to apply. Protection can include:</span></span>

    -   <span data-ttu-id="d81c9-119">Suggerimenti per i criteri per gli utenti</span><span class="sxs-lookup"><span data-stu-id="d81c9-119">Policy tips for users</span></span>

    -   <span data-ttu-id="d81c9-120">Report di posta elettronica per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="d81c9-120">Email report for admins</span></span>

    -   <span data-ttu-id="d81c9-121">Impedire la condivisione esternamente, internamente o entrambe</span><span class="sxs-lookup"><span data-stu-id="d81c9-121">Prevent sharing externally, internally, or both</span></span>

-   <span data-ttu-id="d81c9-p104">Scegliere i criteri per l'applicazione della protezione. Applicare la protezione ai documenti con questo tipo di contenuto: è possibile configurare il criterio per utilizzare tipi e/o etichette di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p104">Choose the criteria for applying the protection. Apply the protection to documents with this type of content: you can configure the policy to use sensitive information types and/or labels.</span></span>

### <a name="using-dlp-for-gdpr-compliance"></a><span data-ttu-id="d81c9-124">Usare DLP per la conformità con l'RGPD</span><span class="sxs-lookup"><span data-stu-id="d81c9-124">Using DLP for GDPR compliance</span></span>

<span data-ttu-id="d81c9-p105">Uno dei principali utilizzi di DLP di Office 365 è quello di identificare dati personali correlati a soggetti dei dati europei nell'ambiente di Office 365. DLP di Office 365 è in grado di informare i team della conformità su dove le informazioni personali sono archiviate in SharePoint Online e OneDrive for Business oppure quando gli utenti inviano posta elettronica contenente informazioni personali. DLP è inoltre in grado di fornire suggerimenti per i criteri ai dipendenti quando utilizzano informazioni personali correlate a residenti nell'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p105">One of the primary uses of Office 365 DLP is to identify personal data related to EU data subjects in your Office 365 environment. Office 365 DLP can notify your compliance teams of where personal information is stored in SharePoint Online and OneDrive for Business, or when users send email containing personal information. DLP can also provide policy tips to your employees when working with personal information related to EU residents.</span></span>

<span data-ttu-id="d81c9-p106">Formare e aumentare la consapevolezza di dove sono archiviate le informazioni sui residenti dell'Unione Europea nel proprio ambiente e sulle modalità di trattamento da parte dei dipendenti rappresenta un livello di protezione delle informazioni con DLP di Office 365. Spesso, i dipendenti che hanno già accesso a questo tipo di informazioni richiedono questo accesso per svolgere le proprie attività quotidiane. L'applicazione dei criteri DLP per consentire il rispetto dell'RGPD potrebbe non richiedere la limitazione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p106">Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP. Often, employees who already have access to this type of information require this access to perform their day to day work. Enforcing DLP policies to help comply with GDPR may not require restricting access.</span></span>

<span data-ttu-id="d81c9-p107">Tuttavia, rispettare l'RGPD generalmente presenta una valutazione basata sul rischio dell'organizzazione da una prospettiva di sicurezza delle informazioni e legale, l'identificazione del tipo e di dove sono archiviate le informazioni e se esiste una giustificazione legale per archiviare ed elaborare tali informazioni. In base a questa valutazione, l'implementazione dei criteri per proteggere l'organizzazione e rispettare l'RGPD potrebbe richiedere la rimozione dell'accesso dei dipendenti ai documenti contenenti informazioni personali sui soggetti dei dati europei. Nei casi in cui è richiesta ulteriore protezione, è possibile configurare protezione DLP aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p107">However, complying with GDPR typically involves a risk based assessment of the organization from both a legal and information security perspective, identification of what type and where personal information is stored, as well as if there is a legal justification to store and process that information. Based on this assessment, implementing policies to protect the organization and comply with GDPR might require removing access for employees to documents that contain personal information for EU data subjects. In cases where further protection is required, additional DLP protection can be configured.</span></span>

<span data-ttu-id="d81c9-p108">L'elenco seguente elenca tre configurazioni per aumentare la protezione con DLP. La prima configurazione, le informazioni sulla presenza, può essere usata come punto di partenza e livello minimo di protezione per l'RGPD.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p108">The following table lists three configurations of increasing protection using DLP. The first configuration, awareness, can be used as a starting point and minimum level of protection for GDPR.</span></span>

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a><span data-ttu-id="d81c9-136">Livelli di protezione di esempio possono essere configurati con criteri DLP e usati per la conformità RGPD</span><span class="sxs-lookup"><span data-stu-id="d81c9-136">Example protection levels that can be configured with DLP policies and used for GDPR compliance</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d81c9-137"><strong>Livello di protezione</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-137"><strong>Protection level</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-138"><strong>Configurazione DLP per i documenti con informazioni personali di soggetti di dati dell'Unione Europea</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-138"><strong>DLP configuration for documents with personal information related to EU data subjects</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-139"><strong>Vantaggi e rischi</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-139"><strong>Benefits and risks</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-140">Informazioni sulla presenza</span><span class="sxs-lookup"><span data-stu-id="d81c9-140">Awareness</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-141">Inviare notifiche tramite posta elettronica ai team di conformità quando questi dati vengono individuati nei documenti su SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="d81c9-141">Send email notifications to compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business.</span></span></p>
<p><span data-ttu-id="d81c9-142">Personalizzare e mostrare suggerimenti per i criteri ai dipendenti in SharePoint e OneDrive for Business quando si accede ai documenti contenenti questi dati.</span><span class="sxs-lookup"><span data-stu-id="d81c9-142">Customize and display Policy Tips to employees in SharePoint and OneDrive for Business when accessing documents containing this data.</span></span></p>
<p><span data-ttu-id="d81c9-143">Rilevare e segnalare quando questi dati vengono condivisi.</span><span class="sxs-lookup"><span data-stu-id="d81c9-143">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d81c9-144">Sensibilizzare con il team di conformità e i dipendenti in merito a dove vengono archiviati questi dati.</span><span class="sxs-lookup"><span data-stu-id="d81c9-144">Raise awareness with compliance teams as well as employees regarding where this data is stored.</span></span></p>
<p><span data-ttu-id="d81c9-145">Formare i dipendenti sui criteri aziendali per la gestione dei documenti contenenti questi dati.</span><span class="sxs-lookup"><span data-stu-id="d81c9-145">Educate employees on corporate policy for handling documents containing this data.</span></span></p>
<p><span data-ttu-id="d81c9-146">Non impedire ai dipendenti di condividere questi dati internamente o esternamente.</span><span class="sxs-lookup"><span data-stu-id="d81c9-146">Does not prevent employees from sharing this data internally or externally.</span></span></p>
<p><span data-ttu-id="d81c9-147">È possibile esaminare i report DLP sui dati condivisi e decidere se è necessario aumentare la protezione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-147">You can review DLP reports for shared data and decide if you need to increase the protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-148">Impedire la condivisione esterna</span><span class="sxs-lookup"><span data-stu-id="d81c9-148">Prevent external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-149">Limitare l'accesso ai documenti contenenti questi dati in SharePoint Online e OneDrive for Business quando i contenuti vengono condivisi con gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d81c9-149">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared with external users.</span></span></p>
<p><span data-ttu-id="d81c9-150">Impedire l'invio di messaggi di posta elettronica con documenti contenenti questi dati a destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="d81c9-150">Prevent sending emails with documents that contain this data to external recipients.</span></span></p>
<p><span data-ttu-id="d81c9-151">Rilevare e segnalare quando questi dati vengono condivisi.</span><span class="sxs-lookup"><span data-stu-id="d81c9-151">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d81c9-152">Impedisce la condivisione esterna di questi dati, consentendo ai dipendenti di lavorare a questi dati internamente.</span><span class="sxs-lookup"><span data-stu-id="d81c9-152">Prevents external sharing of this data while allowing for employees to work with this data internally.</span></span></p>
<p><span data-ttu-id="d81c9-153">È possibile esaminare i report DLP sui dati condivisi internamente e decidere se è necessario aumentare la protezione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-153">You can review DLP reports for internally shared data and decide if you need to increase this protection.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-154">Impedire la condivisione interna ed esterna</span><span class="sxs-lookup"><span data-stu-id="d81c9-154">Prevent internal and external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-155">Limitare l'accesso ai documenti contenenti questi dati in SharePoint Online e OneDrive for Business quando i contenuti vengono condivisi internamente o esternamente.</span><span class="sxs-lookup"><span data-stu-id="d81c9-155">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared internally or externally.</span></span></p>
<p><span data-ttu-id="d81c9-156">Impedire l'invio di messaggi di posta elettronica contenente questi dati ai destinatari esterni e interni.</span><span class="sxs-lookup"><span data-stu-id="d81c9-156">Prevent sending emails which contain this data to both internal and external recipients.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d81c9-157">Impedisce la condivisione interna ed esterna di questi dati.</span><span class="sxs-lookup"><span data-stu-id="d81c9-157">Prevents internal and external sharing of this data.</span></span></p>
<p><span data-ttu-id="d81c9-158">I dipendenti potrebbero non essere in grado di completare attività che richiedono di utilizzare questi dati.</span><span class="sxs-lookup"><span data-stu-id="d81c9-158">Employees might not be able to complete tasks that require working with this data.</span></span></p>
<p><span data-ttu-id="d81c9-159">È possibile esaminare i report DLP sui dati condivisi internamente ed esternamente e decidere se è necessario formare l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d81c9-159">You can review DLP reports for internally or externally shared data and decide if end user training is needed.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d81c9-p109">Nota: man mano che aumentano i livelli di protezione, la capacità degli utenti di accedere potrebbe ridursi in alcuni casi e ciò potrebbe influire potenzialmente sulla produttività o sulla capacità di completare le attività quotidiane. L'aumento dei livelli di protezione implementando criteri che hanno un impatto sui dipendenti è generalmente accompagnato dalla formazione dell'utente finale, educando gli utenti sui nuovi criteri di sicurezza e sulle procedure per aiutarli a continuare a essere produttivi in un ambiente più sicuro.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p109">Note: As the levels of protection increase, the ability of users to access information will decrease in some cases, and could potentially impact their productivity or ability to complete day to day tasks. Increasing protection levels by implementing policies that impact employees is typically accompanied by end user training, educating users on new security policies and procedures to help them continue to be productive in a more secure environment.</span></span>

### <a name="example-dlp-policy-for-gdpr--awareness"></a><span data-ttu-id="d81c9-162">Esempio di criterio DLP per RGPD - Informazioni sulla presenza</span><span class="sxs-lookup"><span data-stu-id="d81c9-162">Example DLP policy for GDPR — Awareness</span></span> 

<span data-ttu-id="d81c9-163">Nome: Informazioni sulla presenza di dati personali soggetti all'RGPD</span><span class="sxs-lookup"><span data-stu-id="d81c9-163">Name: Awareness for personal data that is subject to GDPR.</span></span>

<span data-ttu-id="d81c9-164">Descrizione: visualizzare suggerimenti per i criteri ai dipendenti, informare i team di conformità quando questi dati vengono trovati nei documenti su SharePoint Online e OneDrive for Business, rilevare e segnalare quando questi dati vengono condivisi al di fuori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-164">Description: Display policy tips to employees, notify compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business, detect and report when this data is being shared outside your organization.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d81c9-165"><strong>Controllo</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-165"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-166"><strong>Impostazioni</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-166"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-167">Scegliere le informazioni da proteggere</span><span class="sxs-lookup"><span data-stu-id="d81c9-167">Choose information to protect</span></span></td>
<td align="left"><span data-ttu-id="d81c9-168">Selezionare un modello di criteri personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d81c9-168">Select a Custom policy template.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-169">Percorsi</span><span class="sxs-lookup"><span data-stu-id="d81c9-169">Locations</span></span></td>
<td align="left"><span data-ttu-id="d81c9-170">Tutti i percorsi in Office 365</span><span class="sxs-lookup"><span data-stu-id="d81c9-170">All locations in Office 365</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-171">Trovare contenuto contenente</span><span class="sxs-lookup"><span data-stu-id="d81c9-171">Find content that contains</span></span></td>
<td align="left"><span data-ttu-id="d81c9-172">Fare clic su "Modifica" e aggiungere tutti i tipi di informazioni riservate curate per il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="d81c9-172">Click ‘Edit’ and add all the sensitive information types you curated for your environment.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-173">Rilevare quando il contenuto è condiviso</span><span class="sxs-lookup"><span data-stu-id="d81c9-173">Detect when this content is shared</span></span></td>
<td align="left"><span data-ttu-id="d81c9-174">Selezionare questa casella e "con utenti esterni all'organizzazione".</span><span class="sxs-lookup"><span data-stu-id="d81c9-174">Check this box and select ‘with people outside my organization.’</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-175">Comunicare agli utenti quando il contenuto corrisponde alle impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="d81c9-175">Notify users when content matches the policy settings</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-176">Selezionare questa casella ("Mostra suggerimenti per i criteri agli utenti e invia loro una notifica tramite posta elettronica").</span><span class="sxs-lookup"><span data-stu-id="d81c9-176">Check this box (“Show policy tips to users and send them an email notification.”)</span></span></p>
<p><span data-ttu-id="d81c9-p110">Fare clic su "Personalizza suggerimento e messaggio di posta elettronica" e aggiornali per il proprio ambiente. Vedere le notifiche predefinite in questo articolo: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Invio di notifiche tramite posta elettronica e visualizzazione dei suggerimenti per i criteri per i criteri DLP</a>.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p110">Click ‘Customize the tip and email’ and update these for your environment. See the default notifications in this article: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Send email notifications and show policy tips for DLP policies</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-179">Rilevare quando una determinata quantità di informazioni riservata viene condivisa in una sola volta</span><span class="sxs-lookup"><span data-stu-id="d81c9-179">Detect when a specific amount of sensitive info is being shared at one time</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-180">"Rilevare quando il contenuto condiviso contiene: almeno ____ istanze dello stesso tipo di informazioni riservate" — Impostare su 1.</span><span class="sxs-lookup"><span data-stu-id="d81c9-180">‘Detect when content that’s being shared contains: At least ____ instances of the same sensitive info type’ — Set this to 1.</span></span></p>
<p><span data-ttu-id="d81c9-p111">"Invia rapporti operazioni non consentite tramite posta elettronica" — selezionare questa casella di controllo. Fare clic su "Scegli cosa includere nel rapporto e i destinatari". Non dimenticare di aggiungere il team di conformità.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p111">‘Send incident reports in email’ — check this box. Click ‘Choose what to include in the report and who receives it.’ Be sure to add your compliance team.</span></span></p>
<p><span data-ttu-id="d81c9-184">"Limita chi può ricevere il contenuto e sovrascrivi il criterio" — deselezionare questa casella di controllo per ricevere notifiche sulle informazioni riservate senza impedire gli utenti di accedere a tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="d81c9-184">‘Restrict who can access the content and override the policy’ — clear this checkbox to receive notifications about sensitive information without preventing users from access that information.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d81c9-185">Tutti i percorsi includono:</span><span class="sxs-lookup"><span data-stu-id="d81c9-185">All locations includes:</span></span>

-   <span data-ttu-id="d81c9-186">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d81c9-186">SharePoint Online</span></span>

-   <span data-ttu-id="d81c9-187">Account OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d81c9-187">OneDrive for Business accounts</span></span>

-   <span data-ttu-id="d81c9-188">Cassette postali di Exchange</span><span class="sxs-lookup"><span data-stu-id="d81c9-188">Exchange mailboxes</span></span>

<span data-ttu-id="d81c9-189">Poiché Ricerca contenuto al momento non consente di testare tipi di informazioni riservate con la posta elettronica, prendere in considerazione l'idea di creare criteri separati per Exchange con un set secondario di informazioni riservate in ogni criterio, monitorando l'implementazione di questi criteri.</span><span class="sxs-lookup"><span data-stu-id="d81c9-189">Because Content Search doesn’t currently let you test sensitive information types with email,consider creating separate policies for Exchange with a subset of sensitive information types in each policy and monitoring the rollout of these policies.</span></span>

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-office-365"></a><span data-ttu-id="d81c9-190">Ulteriore livello di protezione che è possibile applicare per proteggere i dati personali in Office 365</span><span class="sxs-lookup"><span data-stu-id="d81c9-190">Additional protection you can apply to protect personal data in Office 365</span></span>

<span data-ttu-id="d81c9-p112">I tipi, le etichette e i criteri di protezione della perdita di dati per le informazioni riservate consentono di identificare i documenti contenenti dati specifici e di applicare protezione. Tuttavia, queste protezioni dipendono dalle autorizzazioni appropriate stabilite per l'accesso a dati, utenti con account non danneggiati e dispositivi integri.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p112">Sensitive information types, labels, and data loss protection policies help you identify documents containing specific data and apply protection. However, these protections depend on appropriate permissions being set for access to data, users with accounts that are not compromised, and devices that are healthy.</span></span>

<span data-ttu-id="d81c9-193">La seguente illustrazione mostra l'ulteriore livello di protezione che è possibile applicare per proteggere l'accesso ai dati personali.</span><span class="sxs-lookup"><span data-stu-id="d81c9-193">The following illustration details additional protection you can apply to protect access to personal data.</span></span>

![Ulteriore livello di protezione per proteggere l'accesso ai dati personali](Media/Apply-protection-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="d81c9-195">Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-195">For accessibility, the following table provides the same information in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d81c9-196"><strong>Ambito della protezione</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-196"><strong>Scope of protection</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-197"><strong>Funzionalità</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-197"><strong>Capabilities</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-198">Protezione a livello di posta elettronica e documento (include posta in transito, ma non le cassette postali inattive al momento)</span><span class="sxs-lookup"><span data-stu-id="d81c9-198">Document and email-level protection (includes mail in transit, but not currently mailboxes at rest)</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-199">Tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="d81c9-199">Sensitive information types</span></span></p>
<p><span data-ttu-id="d81c9-200">Etichette di Office</span><span class="sxs-lookup"><span data-stu-id="d81c9-200">Office labels</span></span></p>
<p><span data-ttu-id="d81c9-201">Criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="d81c9-201">Data loss prevention policies</span></span></p>
<p><span data-ttu-id="d81c9-202">Crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="d81c9-202">Office 365 Message Encryption for email</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-203">Protezione a livello di sito e raccolta (include siti di SharePoint Online e OneDrive for Business)</span><span class="sxs-lookup"><span data-stu-id="d81c9-203">Site and library-level protection (includes SharePoint Online and OneDrive for Business sites)</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-204">Autorizzazioni per siti e raccolte di SharePoint Online e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d81c9-204">Permissions for SharePoint Online and OneDrive for Business sites and libraries</span></span></p>
<p><span data-ttu-id="d81c9-205">Criteri di condivisione esterna per SharePoint Online e OneDrive for Business (a livello di sito)</span><span class="sxs-lookup"><span data-stu-id="d81c9-205">External sharing policies for SharePoint Online and OneDrive for Business (site-level)</span></span></p>
<p><span data-ttu-id="d81c9-206">Criteri di accesso al dispositivo a livello di sito</span><span class="sxs-lookup"><span data-stu-id="d81c9-206">Site-level device access policies</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-207">Protezione dell'accesso al servizio (include l'accesso a tutti i servizi in Office 365)</span><span class="sxs-lookup"><span data-stu-id="d81c9-207">Service access protection (includes access to all services in Office 365)</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-208">Protezione dell'accesso a identità e dispositivi nella famiglia di prodotti Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="d81c9-208">Identity and device access protection in Enterprise Mobility + Security (EMS) suite</span></span></p>
<p><span data-ttu-id="d81c9-209">Gestione accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="d81c9-209">Privileged access management</span></span></p>
<p><span data-ttu-id="d81c9-210">Funzionalità di sicurezza di Windows 10</span><span class="sxs-lookup"><span data-stu-id="d81c9-210">Windows 10 security capabilities</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d81c9-211">Il resto di questo articolo fornisce informazioni su ciascuna delle categorie di protezione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-211">The rest of this article provides more information on each of these categories of protection.</span></span>

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a><span data-ttu-id="d81c9-212">Funzionalità che possono essere usate con l'RGPD</span><span class="sxs-lookup"><span data-stu-id="d81c9-212">Capabilities that are OK to use with GDPR</span></span>

<span data-ttu-id="d81c9-p113">È possibile utilizzare le seguenti funzionalità in un ambiente configurato per la conformità RGPD. Queste funzionalità non sono necessarie per la conformità RGPD, ma possono essere utilizzate senza influenzare in modo negativo la capacità di individuare, proteggere, monitorare e segnalare dati in merito alla conformità RGPD.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p113">You can use the following capabilities in an environment configured for GDPR compliance. These capabilities are not necessary for GDPR compliance, but they can be used without adversely affecting your ability to discover, protect, monitor, and report on data related to GDPR compliance.</span></span>

<span data-ttu-id="d81c9-p114">Customer Key - Consente ai clienti di fornire e mantenere il controllo sulle chiavi di crittografia utilizzate per crittografare i dati inattivi in Office 365. Consigliata solo per i clienti con l'esigenza normativa di gestire le proprie chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p114">Customer Key — Allows customers to provide and retain control over the encryption keys that are used to encrypt data at rest within Office 365. Recommended only for customers with a regulatory need to manage their own encryption keys.</span></span>

<span data-ttu-id="d81c9-p115">Customer Lockbox — Customer Lockbox consente di controllare il modo in cui un tecnico del supporto Microsoft accede ai dati, se necessario, per risolvere un problema tecnico caso per caso. È possibile controllare se fornirgli l'accesso ai dati o meno. Per ogni richiesta, è previsto un tempo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p115">Customer Lockbox — Customer lockbox allows you to control how a Microsoft support engineer accesses your data, if needed, to fix a technical issue on a case by case basis. You can control whether to give the support engineer access to your data or not. An expiration time is provided with each request.</span></span>

## <a name="site-and-library-level-protection"></a><span data-ttu-id="d81c9-220">Protezione a livello di sito e raccolta</span><span class="sxs-lookup"><span data-stu-id="d81c9-220">Site and library-level protection</span></span>

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="d81c9-221">Autorizzazioni per raccolte di SharePoint e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d81c9-221">Permissions for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="d81c9-p116">Usare le autorizzazioni in SharePoint per fornire o limitare l'accesso degli utenti al sito o ai suoi contenuti. Aggiungere i singoli utenti o gruppi di Azure Active Directory ai gruppi di SharePoint predefiniti. In alternativa, creare un gruppo personalizzato per un controllo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p116">Use permissions in SharePoint to provide or restrict user access to the site or its contents. Add individual users or Azure Active Directory groups to the default SharePoint groups. Or, create a custom group for finer-grain control.</span></span>

![Livelli di autorizzazione dal controllo completo alla sola visualizzazione](Media/Apply-protection-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="d81c9-p117">L'illustrazione traccia i livelli di autorizzazione da Controllo completo a Solo visualizzazione. Nella seguente tabella sono incluse le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p117">The illustration plots permission levels from Full control to View Only. The following table includes the same information.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d81c9-228"><strong>Controllo completo</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-228"><strong>Full Control</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-229"><strong>Progettazione</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-229"><strong>Design</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-230"><strong>Modifica</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-230"><strong>Edit</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-231"><strong>Collaborazione</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-231"><strong>Contribute</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-232"><strong>Lettura</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-232"><strong>Read</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-233"><strong>Solo visualizzazione</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-233"><strong>View Only</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="d81c9-234">Collaborazione + approvazione e personalizzazione</span><span class="sxs-lookup"><span data-stu-id="d81c9-234">Contribute + approve and customize</span></span></td>
<td align="left"><span data-ttu-id="d81c9-235">Collaborazione + aggiunta, modifica ed eliminazione di elenchi (non solo delle voci degli elenchi)</span><span class="sxs-lookup"><span data-stu-id="d81c9-235">Contribute + add, edit and delete lists (not just list items)</span></span></td>
<td align="left"><span data-ttu-id="d81c9-236">Visualizzazione, aggiunta, aggiornamento, eliminazione dei documenti e delle voci di elenchi</span><span class="sxs-lookup"><span data-stu-id="d81c9-236">View, add, update, delete list items and documents</span></span></td>
<td align="left"><span data-ttu-id="d81c9-237">Visualizzazione e download</span><span class="sxs-lookup"><span data-stu-id="d81c9-237">View and download</span></span></td>
<td align="left"><span data-ttu-id="d81c9-238">Visualizzazione senza download</span><span class="sxs-lookup"><span data-stu-id="d81c9-238">View, no download</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d81c9-239">Ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="d81c9-239">More information:</span></span>

-   [<span data-ttu-id="d81c9-240">Informazioni sui i livelli di autorizzazione in SharePoint</span><span class="sxs-lookup"><span data-stu-id="d81c9-240">Understanding permission levels in SharePoint</span></span>](https://support.office.com/it-IT/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [<span data-ttu-id="d81c9-241">Informazioni sui gruppi di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d81c9-241">Understanding SharePoint groups</span></span>](https://support.office.com/it-IT/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="d81c9-242">Criteri di condivisione esterna per le raccolte di SharePoint Online e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d81c9-242">External sharing policies for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="d81c9-p118">Molte organizzazioni consentono la condivisione esterna per supportare la collaborazione. È necessario capire come sono configurate le impostazioni nel tenant. Quindi rivedere le impostazioni di condivisione esterna per i siti che contengono dati personali.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p118">Many organizations allow external sharing to support collaboration. Find out how your tenant-wide settings are configured. Then review the external sharing settings for sites that contain personal data.</span></span>

<span data-ttu-id="d81c9-246">Un utente esterno è un utente esterno all'organizzazione che viene invitato ad accedere ai siti e documenti di SharePoint Online, ma che non ha la licenza della sottoscrizione di SharePoint Online o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="d81c9-246">An external user is someone outside of your organization who is invited to access your SharePoint Online sites and documents but does not have a license for your SharePoint Online or Microsoft Office 365 subscription.</span></span>

<span data-ttu-id="d81c9-247">Criteri di condivisione esterna per SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="d81c9-247">External sharing policies apply to both SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="d81c9-248">È necessario essere un amministratore di SharePoint Online per configurare i criteri di condivisione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-248">You must be a SharePoint Online admin to configure sharing policies.</span></span>

-   <span data-ttu-id="d81c9-249">È necessario essere il proprietario del sito o avere le autorizzazioni controllo complete per condividere un sito o documento con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d81c9-249">You must be a Site Owner or have full control permissions to share a site or document with external users.</span></span>

<span data-ttu-id="d81c9-250">Nella tabella riportata di seguito vengono riassunti i controlli che è possibile configurare.</span><span class="sxs-lookup"><span data-stu-id="d81c9-250">The following table summarizes the controls you can configure.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d81c9-251"><strong>Categoria di controllo</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-251"><strong>Control category</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-252"><strong>Opzioni</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-252"><strong>Options</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-253">Tipo di condivisione</span><span class="sxs-lookup"><span data-stu-id="d81c9-253">Type of sharing</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-254">Non consentire la condivisione all'esterno dell'organizzazione (può essere impostata per singole raccolte siti)</span><span class="sxs-lookup"><span data-stu-id="d81c9-254">Don’t allow sharing outside your organization (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="d81c9-255">Consentire la condivisione solo con utenti esterni autenticati (consentire nuovo o limitare agli esistenti, può essere impostata per singole raccolte siti)</span><span class="sxs-lookup"><span data-stu-id="d81c9-255">Allow sharing to authenticated external users only (allow new or limit to existing, can be set for individual site collections)\*</span></span></p>
<p><span data-ttu-id="d81c9-256">Consentire la condivisione con utenti esterni con un collegamento per l'accesso anonimo (può essere impostata per singole raccolte siti)</span><span class="sxs-lookup"><span data-stu-id="d81c9-256">Allow sharing to external users with an anonymous access link (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="d81c9-257">Limitare la condivisione esterna tramite i domini (consentire e rifiutare elenchi)</span><span class="sxs-lookup"><span data-stu-id="d81c9-257">Limit external sharing using domains (allow and deny list)</span></span></p>
<p><span data-ttu-id="d81c9-258">Scegliere il tipo di collegamento predefinito (anonimo, condivisibile con l'azienda o limitato)</span><span class="sxs-lookup"><span data-stu-id="d81c9-258">Choose the default link type (anonymous, company shareable, or restricted)</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-259">Cosa possono fare gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="d81c9-259">What external users can do</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-260">Impedire agli utenti esterni di condividere file, cartelle, siti che non possiedono</span><span class="sxs-lookup"><span data-stu-id="d81c9-260">Prevent external users from sharing files, folders, sites they don’t own</span></span></p>
<p><span data-ttu-id="d81c9-261">Richiedere agli utenti esterni di accettare la condivisione degli inviti con lo stesso account a cui è stato inviato l'invio</span><span class="sxs-lookup"><span data-stu-id="d81c9-261">Require external users to accept sharing invitations with the same account the invitation was sent to</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-262">Notifiche</span><span class="sxs-lookup"><span data-stu-id="d81c9-262">Notifications</span></span></td>
<td align="left"><p><span data-ttu-id="d81c9-p119">Attualmente disponibile solo in OneDrive for Business. Inviare una notifica ai proprietari quando:</span><span class="sxs-lookup"><span data-stu-id="d81c9-p119">Currently only available in OneDrive for Business. Notify owners when:</span></span></p>
- <p><span data-ttu-id="d81c9-265">Gli utenti invitano altri utenti esterni ai file condivisi</span><span class="sxs-lookup"><span data-stu-id="d81c9-265">Users invite additional external users to shared files</span></span></p>
- <p><span data-ttu-id="d81c9-266">Gli utenti esterni accettano gli inviti per accedere ai file</span><span class="sxs-lookup"><span data-stu-id="d81c9-266">External users accept invitations to access files</span></span></p>
- <p><span data-ttu-id="d81c9-267">Un collegamento per l'accesso anonimo viene creato o modificato</span><span class="sxs-lookup"><span data-stu-id="d81c9-267">An anonymous access link is created or changed</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d81c9-268">Ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="d81c9-268">More information:</span></span>

-   [<span data-ttu-id="d81c9-269">Gestire la condivisione esterna per l'ambiente di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d81c9-269">Manage external sharing for your SharePoint Online environment</span></span>](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [<span data-ttu-id="d81c9-270">Condividere siti o documenti con utenti esterni alla propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="d81c9-270">Share sites or documents with people outside your organization</span></span>](https://support.office.com/it-IT/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a><span data-ttu-id="d81c9-271">Criteri di accesso al dispositivo a livello di sito</span><span class="sxs-lookup"><span data-stu-id="d81c9-271">Site-level device access policies</span></span>

<span data-ttu-id="d81c9-p120">SharePoint Online e OneDrive for Business consentono di configurare i criteri di accesso dei dispositivi a livello di sito. Ciò consente di configurare una maggiore protezione per i siti con dati riservati.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p120">SharePoint Online and OneDrive for Business let you configure device access policies at the site level. This lets you configure more protection for sites with sensitive data.</span></span>

<span data-ttu-id="d81c9-274">Se si configurano criteri di accesso ai dispositivi a livello di sito, assicurarsi di coordinarli con i criteri a livello di tenant e con i criteri di accesso configurati in Azure Active Directory, Intune e Intune App Management</span><span class="sxs-lookup"><span data-stu-id="d81c9-274">If you configure site-level device access policies, be sure to coordinate these with tenant-level policies and also with access policies that are configured in Azure Active Directory, Intune, and Intune App Management.</span></span>

<span data-ttu-id="d81c9-p121">I criteri di accesso ai dispositivi per SharePoint e OneDrive for Business richiedono criteri di supporto in Azure Active Directory e Microsoft Intune a seconda dello scenario che si sta implementando. Nella tabella seguente vengono riassunti gli obiettivi raggiungibili con i criteri di accesso ai dispositivi e vengono indicati quali prodotti richiedono criteri di supporto.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p121">Device access policies for SharePoint and OneDrive for Business require supporting policies in Azure Active Directory and Microsoft Intune depending on the scenario you are implementing. The following table summarizes objectives you can achieve with device access policies and indicates which products require supporting policies.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="d81c9-277">Consentire l'accesso solo da indirizzi IP specifici</span><span class="sxs-lookup"><span data-stu-id="d81c9-277">Only allow access from specific IP address locations</span></span></th>
<th align="left"><span data-ttu-id="d81c9-278">Impedire agli utenti di scaricare file su dispositivi non aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="d81c9-278">Prevent users from downloading files to non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="d81c9-279">Bloccare l'accesso nei dispositivi non aggiunti al dominio</span><span class="sxs-lookup"><span data-stu-id="d81c9-279">Block access on non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="d81c9-280">Impedire agli utenti di scaricare file nei dispositivi non conformi</span><span class="sxs-lookup"><span data-stu-id="d81c9-280">Prevent users from downloading files to non-compliant devices</span></span></th>
<th align="left"><span data-ttu-id="d81c9-281">Bloccare l'accesso nei dispositivi non conformi</span><span class="sxs-lookup"><span data-stu-id="d81c9-281">Block access on non-compliant devices</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-282">Interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="d81c9-282">SharePoint admin center</span></span></td>
<td align="left"><span data-ttu-id="d81c9-283">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-283">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-284">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-284">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-285">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-285">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-286">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-286">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-287">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-287">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-288">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d81c9-288">Azure Active Directory</span></span></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="d81c9-289">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-289">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-290">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-290">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-291">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-291">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-292">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-292">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-293">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d81c9-293">Microsoft Intune</span></span></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="d81c9-294">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-294">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-295">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-295">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d81c9-296">Altre informazioni: [Interfaccia di amministrazione di SharePoint Online: controllare l'accesso da dispositivi non gestiti](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="d81c9-296">More information: [SharePoint Online admin center: Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="service-access-protection-for-identities-and-devices"></a><span data-ttu-id="d81c9-297">Protezione dell'accesso al servizio per identità e dispositivi</span><span class="sxs-lookup"><span data-stu-id="d81c9-297">Service access protection for identities and devices</span></span>

<span data-ttu-id="d81c9-p122">Microsoft consiglia di configurare la protezione per identità e dispositivi che accedono al servizio. La protezione dell'accesso ai servizi di Office 365 può anche essere usata per proteggere l'accesso ad altri servizi SaaS, PaaS e anche app in altri provider cloud.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p122">Microsoft recommends you configure protection for identities and devices that access the service. The work you put into protecting access to Office 365 services can also be used to protect access to other SaaS services, PaaS services, and even apps in other cloud providers.</span></span>

<span data-ttu-id="d81c9-300">La protezione dell'accesso per identità e dispositivi offre un livello di protezione di base per garantire che le identità non siano compromesse, i dispositivi siano sicuri e i dati dell'organizzazione aperti sui dispositivi siano isolati e protetti.</span><span class="sxs-lookup"><span data-stu-id="d81c9-300">Access protection for identities and devices provides a baseline of protection to ensure that identities are not compromised, devices are safe, and organization data that is accessed on devices is isolated and protected.</span></span>

<span data-ttu-id="d81c9-301">Per suggerimenti iniziali e indicazioni sulla configurazione, vedere [Guida alla sicurezza Microsoft per campagne politiche, organizzazioni no profit e altre organizzazioni Agile](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="d81c9-301">For starting point recommendations and configuration guidance, see [Microsoft security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="d81c9-302">Per ambienti con identità ibride con AD FS, vedere [Configurazioni e criteri di sicurezza consigliati](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="d81c9-302">For hybrid identity environments with AD FS, see [Recommended security policies and configurations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="d81c9-p123">La seguente illustrazione descrive il modo in cui si relazionano i servizi cloud (SaaS, PaaS), i tipi di account (account del dominio tenant vs account B2B) e le funzionalità di accesso al servizio. È importante notare quali funzionalità possono essere usate con gli account B2B.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p123">The following illustration describes how cloud services (SaaS, PaaS), account types (tenant domain accounts vs. B2B accounts) and service access capabilities relate. It’s important to note which capabilities can be used with B2B accounts.</span></span>

![Servizi cloud, tipi di account e funzionalità di accesso](Media/Apply-protection-to-personal-data-in-Office-365-image4.png)

<span data-ttu-id="d81c9-306">Ai fini dell'accessibilità, il resto di questa sezione descrive l'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="d81c9-306">For accessibility, the rest of this section describes this illustration.</span></span>

### <a name="cloud-services"></a><span data-ttu-id="d81c9-307">Servizi cloud</span><span class="sxs-lookup"><span data-stu-id="d81c9-307">Cloud services</span></span>

<span data-ttu-id="d81c9-p124">Azure Active Directory fornisce l'accesso per le identità a qualsiasi servizio cloud, tra cui provider di terze parti non Microsoft come Amazon Web Services. L'illustrazione mostra Office 365, "altre app SaaS" e "app PaaS". Le frecce puntano da Azure Active Directory a ognuno di questi servizi, mostrando che Azure Active Directory può essere usato per l'autenticazione di tutti questi tipi di app.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p124">Azure Active Directory provides identity access to any cloud service, including non-Microsoft providers such as Amazon Web Services. The illustration shows Office 365, “Other SaaS app,” and “PaaS app.” Arrows point from Azure Active Directory to each of these services, showing that Azure Active Directory can be used for authentication to all of these app types.</span></span>

### <a name="types-of-accounts"></a><span data-ttu-id="d81c9-311">Tipi di account</span><span class="sxs-lookup"><span data-stu-id="d81c9-311">Types of accounts</span></span>

<span data-ttu-id="d81c9-p125">Gli account del dominio tenant sono account aggiunti al tenant e gestiti direttamente. Gli account B2B sono account per utenti al di fuori dell'organizzazione invitati a collaborare. Possono essere altri account Office 365, account di altre organizzazioni o account consumer (come Gmail). L'illustrazione mostra entrambi i tipi di account in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p125">Tenant domain accounts are account you add to your tenant and manage directly. B2B accounts are accounts for users outside your organization you invite to collaborate with. These can be other Office 365 accounts, other organization accounts, or consumer accounts (such as Gmail). The illustration shows both account types within Azure Active Directory.</span></span>

### <a name="capabilities"></a><span data-ttu-id="d81c9-316">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="d81c9-316">Capabilities</span></span>

<span data-ttu-id="d81c9-p126">Le funzionalità nella tabella seguente proteggono identità e dispositivi. La tabella indica quali funzionalità possono essere usate con gli account B2B, come l'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="d81c9-p126">The capabilities in the following table protect identities and devices. The table indicates which capabilities can also be used with B2B accounts, similar to the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d81c9-319"><strong>Funzionalità</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-319"><strong>Capability</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-320"><strong>Funziona con gli account del dominio tenant</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-320"><strong>Works with tenant domain accounts</strong></span></span></th>
<th align="left"><span data-ttu-id="d81c9-321"><strong>Funziona con gli account B2B Azure (senza ulteriori licenze)</strong></span><span class="sxs-lookup"><span data-stu-id="d81c9-321"><strong>Works with Azure B2B accounts (without additional licensing)</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-322">Autenticazione a più fattori e accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="d81c9-322">Multi-factor authentication and conditional access</span></span></td>
<td align="left"><span data-ttu-id="d81c9-323">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-323">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-324">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-324">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-325">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d81c9-325">Azure AD Identity Protection</span></span></td>
<td align="left"><span data-ttu-id="d81c9-326">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-326">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-327">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-327">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-328">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="d81c9-328">Azure AD Privileged Identity Management</span></span></td>
<td align="left"><span data-ttu-id="d81c9-329">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-329">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-330">Gestione di applicazioni mobili (MAM)</span><span class="sxs-lookup"><span data-stu-id="d81c9-330">Mobile Application Management (MAM)</span></span></td>
<td align="left"><span data-ttu-id="d81c9-331">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-331">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d81c9-332">Gestione e registrazione del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d81c9-332">Device enrollment and management</span></span></td>
<td align="left"><span data-ttu-id="d81c9-333">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-333">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-334">Solo un'organizzazione può gestire un dispositivo</span><span class="sxs-lookup"><span data-stu-id="d81c9-334">Only one organization can manage a device</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d81c9-335">Funzionalità di sicurezza di Windows 10 (l'accesso condizionale basato sulla conformità dei dispositivi richiede la gestione dei dispositivi)</span><span class="sxs-lookup"><span data-stu-id="d81c9-335">Windows 10 security capabilities (conditional access based on device compliance requires device management)</span></span></td>
<td align="left"><span data-ttu-id="d81c9-336">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-336">Yes</span></span></td>
<td align="left"><span data-ttu-id="d81c9-337">Sì</span><span class="sxs-lookup"><span data-stu-id="d81c9-337">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d81c9-338">È possibile aggiungere licenze ad account B2B per fornire agli utenti funzionalità aggiuntive, se necessario, per proteggere l'accesso ai dati personali nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="d81c9-338">You can add licenses to B2B accounts to give these users additional capabilities, if needed, to protect access to personal data in your environment.</span></span>
