---
title: Integrare Microsoft Teams classi con Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrare Microsoft Teams classi con Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314492"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="c7450-103">Usare Microsoft Teams classi con Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="c7450-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="c7450-104">Il lavoro in team è alla base di ogni organizzazione moderna.</span><span class="sxs-lookup"><span data-stu-id="c7450-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="c7450-105">Promuovendo la collaborazione, è una caratteristica distintiva di ogni istituto di successo.</span><span class="sxs-lookup"><span data-stu-id="c7450-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="c7450-106">Puoi migliorare tutte le funzionalità e le funzionalità di Blackboard Learn Ultra associandole a Microsoft Teams classi.</span><span class="sxs-lookup"><span data-stu-id="c7450-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="c7450-107">Le classi possono includere conversazioni in tempo reale, riunioni video o interazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="c7450-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="c7450-108">Puoi aggiungere esperienze di condivisione e creazione di file per gli studenti, tutte in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="c7450-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="c7450-109">Microsoft Teams con Learn Ultra ridefinire le dinamiche dell'insegnamento e il significato dell'apprendimento efficace.</span><span class="sxs-lookup"><span data-stu-id="c7450-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7450-110">Assicurarsi di aver configurato correttamente il campo E-mail dell'istituto nel sistema sis (Sis) degli studenti `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="c7450-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="c7450-111">L'Microsoft Teams delle classi di autenticazione si basa sul campo di posta elettronica dell'istituto nel SIS per eseguire il mapping al nome dell'entità utente (UPN) del Microsoft Azure Active Directory (AAD) corretto.</span><span class="sxs-lookup"><span data-stu-id="c7450-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="c7450-112">Se non è stato effettuato il provisioning dei messaggi di posta elettronica dell'istituto, per impostazione predefinita verrà utilizzato il messaggio di posta elettronica esistente.</span><span class="sxs-lookup"><span data-stu-id="c7450-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="c7450-113">È consigliabile impostare questo campo per ogni utente per assicurarsi che i dati siano sincronizzati correttamente e che non vi sia alcun conflitto di dati di posta elettronica tra Microsoft AAD e Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="c7450-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="c7450-114">Se questo campo non è stato impostato in modo appropriato nel mapping SIS, l'integrazione continuerà a funzionare, ma gli utenti potrebbero non essere visualizzati nelle classi Teams create e potrebbero verificarsi errori.</span><span class="sxs-lookup"><span data-stu-id="c7450-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="c7450-115">Supporto del mapping dei dati istituzionali - Campo SIS di posta elettronica dell'istituto</span><span class="sxs-lookup"><span data-stu-id="c7450-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="c7450-116">Come parte dell'evoluzione con le integrazioni dei provider  cloud, Blackboard Learn Ultra ha creato un nuovo campo e-mail dell'istituto, sia nell'integrazione di Student Information System Framework che nelle API REST pubbliche, consentendo agli istituti di gestire in modo efficace il processo di sincronizzazione dei dati tra Blackboard Learn Ultra e Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="c7450-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="c7450-117">Cosa significa e cosa supporta l'e-mail dell'istituto?</span><span class="sxs-lookup"><span data-stu-id="c7450-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="c7450-118">Il **campo Institution Email** consente mapping di campi personalizzati tra le origini dati supportate esternamente da un client e Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="c7450-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="c7450-119">Se le origini dati sono provider cloud, ad esempio Microsoft, l'UPN (User Principle Name) è un identificatore univoco primario per ogni utente costituito da un prefisso UPN (il nome dell'account dell'utente) e da un suffisso UPN (un nome di dominio DNS) uniti a un simbolo @.</span><span class="sxs-lookup"><span data-stu-id="c7450-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="c7450-120">In questo modo viene creato un indirizzo di posta elettronica univoco per ogni utente specifico all'interno del Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7450-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="c7450-121">Per garantire che i dati siano accurati e che le registrazioni o le appartenenze tra le classi Blackboard Learn Ultra e Microsoft Teams vengano ottenute correttamente, l'indirizzo di posta elettronica di un utente deve corrispondere tra entrambi i sistemi.</span><span class="sxs-lookup"><span data-stu-id="c7450-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="c7450-122">In Blackboard Learn Ultra, gli utenti possono modificare o sostituire l'indirizzo di posta elettronica esistente nell'interfaccia utente, che potrebbe causare errori di sincronizzazione e l'utente non essere aggiunto correttamente a un team di classe.</span><span class="sxs-lookup"><span data-stu-id="c7450-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="c7450-123">Il mapping del campo **e-mail** dell'istituto garantisce che questo livello di sicurezza e controllo di convalida possa essere gestito correttamente, indipendentemente dal fatto che gli utenti hanno modificato la propria posta elettronica all'interno di Blackboard Learn Ultra o meno.</span><span class="sxs-lookup"><span data-stu-id="c7450-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="c7450-124">Quando due indirizzi di posta elettronica sono diversi:</span><span class="sxs-lookup"><span data-stu-id="c7450-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="c7450-125">È necessario prendere una decisione sull'origine che ha la precedenza e verrà presa sia come messaggio di posta elettronica dell'utente che dell'istituto.</span><span class="sxs-lookup"><span data-stu-id="c7450-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="c7450-126">Oppure</span><span class="sxs-lookup"><span data-stu-id="c7450-126">Or</span></span>
- <span data-ttu-id="c7450-127">Un istituto può impostare un mapping di campo personalizzato nel messaggio di posta elettronica dell'istituto, che può risolvere un potenziale conflitto.</span><span class="sxs-lookup"><span data-stu-id="c7450-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="c7450-128">Il **mapping del campo e-mail** institution è ora disponibile per tutti i tipi di integrazione SIS esistenti in Advanced Configuration **Impostazioni** Users Learn  >  **Object Type** Field  >  **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="c7450-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="c7450-129">È importante notare che, per impostazione  predefinita, l'e-mail dell'istituto è impostata sull'indirizzo di posta elettronica della persona per tutti i formati SIS e deve essere univoco per ogni persona. </span><span class="sxs-lookup"><span data-stu-id="c7450-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="c7450-130">Tutte le integrazioni esistenti che sono state impostate e in esecuzione avranno questo mapping dei dati, in quanto SIS non riuscirà a importare gli utenti se la posta elettronica è duplicata.</span><span class="sxs-lookup"><span data-stu-id="c7450-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="c7450-131">Se un istituto richiede la possibilità di modificare l'indirizzo di posta elettronica dell'istituto **in** **personalizzato,** dovrà gestire questo problema tramite la configurazione avanzata Impostazioni nel SIS.</span><span class="sxs-lookup"><span data-stu-id="c7450-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="c7450-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7450-132">Requirements</span></span>

<span data-ttu-id="c7450-133">L Microsoft Teams di integrazione delle classi di corsi è disponibile solo per i corsi **Di visualizzazione corso Ultra.**</span><span class="sxs-lookup"><span data-stu-id="c7450-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="c7450-134">L'istituto deve completare questi requisiti per usarlo:</span><span class="sxs-lookup"><span data-stu-id="c7450-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="c7450-135">Avere Blackboard Learn Ultra Learn SaaS con l'opzione Di spostamento di base ultra abilitata</span><span class="sxs-lookup"><span data-stu-id="c7450-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="c7450-136">Abilita LTI per l'uso nei corsi.</span><span class="sxs-lookup"><span data-stu-id="c7450-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="c7450-137">a.</span><span class="sxs-lookup"><span data-stu-id="c7450-137">a.</span></span> <span data-ttu-id="c7450-138">Passare al pannello **di amministrazione** Provider di  >  **strumenti LTI** Gestisci proprietà  >  **globali**.</span><span class="sxs-lookup"><span data-stu-id="c7450-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="c7450-139">b.</span><span class="sxs-lookup"><span data-stu-id="c7450-139">b.</span></span> <span data-ttu-id="c7450-140">Selezionare **LTI Enabled in Courses** e, facoltativamente, selezionare Enabled in **Organizations**.</span><span class="sxs-lookup"><span data-stu-id="c7450-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="c7450-141">c.</span><span class="sxs-lookup"><span data-stu-id="c7450-141">c.</span></span> <span data-ttu-id="c7450-142">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7450-142">Select **Submit**.</span></span>

- <span data-ttu-id="c7450-143">Deve essere configurato LTI</span><span class="sxs-lookup"><span data-stu-id="c7450-143">Must have LTI configured</span></span>

- <span data-ttu-id="c7450-144">Aggiungere Blackboard Learn Ultra Teams Classes LTI Integration</span><span class="sxs-lookup"><span data-stu-id="c7450-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="c7450-145">Aggiungere Microsoft Teams classi LTI 1.3 Tool</span><span class="sxs-lookup"><span data-stu-id="c7450-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="c7450-146">Aggiungere lo strumento API REST e condivisione di risorse tra origini</span><span class="sxs-lookup"><span data-stu-id="c7450-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="c7450-147">Configurare e approvare classi Microsoft Teams integrazione</span><span class="sxs-lookup"><span data-stu-id="c7450-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="c7450-148">Aggiungere lo strumento Blackboard Learn Ultra Teams Classes LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="c7450-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="c7450-149">Nel Pannello **di amministrazione** selezionare Provider di **strumenti LTI.**</span><span class="sxs-lookup"><span data-stu-id="c7450-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="c7450-150">Selezionare **register LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="c7450-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="c7450-151">Nel campo **ID client** digitare oppure copiare e incollare questo ID:</span><span class="sxs-lookup"><span data-stu-id="c7450-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="c7450-152">Esaminare tutte le impostazioni pre-popolate e in **Stato strumento** e quindi selezionare **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="c7450-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="c7450-153">In **Criteri dell'istituto** selezionare **Ruolo in Corso, Nome** e Indirizzo di posta **elettronica,** quindi selezionare **Sì** per entrambi.</span><span class="sxs-lookup"><span data-stu-id="c7450-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="c7450-154">Selezionare **Consenti accesso al servizio di livello** e Consenti accesso al servizio di **appartenenza**.</span><span class="sxs-lookup"><span data-stu-id="c7450-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="c7450-155">Aggiungere lo strumento Microsoft Teams Classes LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="c7450-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="c7450-156">Nel Pannello **di amministrazione** selezionare Provider di **strumenti LTI.**</span><span class="sxs-lookup"><span data-stu-id="c7450-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="c7450-157">Selezionare **register LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="c7450-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="c7450-158">Nel campo **ID client** digitare oppure copiare e incollare questo ID:</span><span class="sxs-lookup"><span data-stu-id="c7450-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="c7450-159">Esaminare tutte le impostazioni pre-popolate e in *Stato strumento e* selezionare *Abilitato.*</span><span class="sxs-lookup"><span data-stu-id="c7450-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="c7450-160">In **Criteri dell'istituto** selezionare **Ruolo in Corso, Nome e** Indirizzo di posta **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="c7450-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="c7450-161">Selezionare **Sì** per entrambi.</span><span class="sxs-lookup"><span data-stu-id="c7450-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="c7450-162">Selezionare **Consenti accesso al servizio di livello** e Consenti accesso al servizio di **appartenenza**.</span><span class="sxs-lookup"><span data-stu-id="c7450-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="c7450-163">Aggiungere lo strumento API REST</span><span class="sxs-lookup"><span data-stu-id="c7450-163">Add the REST API tool</span></span>

1. <span data-ttu-id="c7450-164">Nel Pannello **di amministrazione** passa a **Integrazioni e** seleziona **Integrazioni API Rest.**</span><span class="sxs-lookup"><span data-stu-id="c7450-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="c7450-165">Selezionare **Crea integrazione**.</span><span class="sxs-lookup"><span data-stu-id="c7450-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="c7450-166">Nel campo **ID applicazione** digitare oppure copiare e incollare questo ID:</span><span class="sxs-lookup"><span data-stu-id="c7450-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="c7450-167">Digitare un utente per questa integrazione.</span><span class="sxs-lookup"><span data-stu-id="c7450-167">Type a user for this integration.</span></span>

   <span data-ttu-id="c7450-168">Questo utente sarà quello con accesso all'API principale da cui è associata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7450-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="c7450-169">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7450-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="c7450-170">Aggiungere la condivisione di risorse tra origini</span><span class="sxs-lookup"><span data-stu-id="c7450-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="c7450-171">Nel pannello **Amministratore,** accedere a **Integrazioni e** selezionare \**Condivisione risorse tra origini*.</span><span class="sxs-lookup"><span data-stu-id="c7450-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="c7450-172">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="c7450-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="c7450-173">Nel campo **Origine** digitare copiare e incollare l'URL:</span><span class="sxs-lookup"><span data-stu-id="c7450-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="c7450-174">Nel campo **Intestazioni consentite** digitare **Autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="c7450-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="c7450-175">Impostare **Disponibile** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c7450-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="c7450-176">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7450-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="c7450-177">Configurare e approvare le classi Microsoft Teams integrazione</span><span class="sxs-lookup"><span data-stu-id="c7450-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="c7450-178">Per integrare correttamente l'istanza di Blackboard Learn Ultra con le classi Microsoft Teams, devi assicurarti che l'applicazione Blackboard Learn Ultra sia approvata per l'accesso all'interno del tenant Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="c7450-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="c7450-179">Si tratta di un processo che dovrà essere completato dall'amministratore globale dell'Microsoft 365 dell'istituto.</span><span class="sxs-lookup"><span data-stu-id="c7450-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="c7450-180">Questo processo può essere eseguito prima o dopo aver configurato le applicazioni LTI nella blackboard Learn Ultra Instance.</span><span class="sxs-lookup"><span data-stu-id="c7450-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="c7450-181">Prima di configurare le applicazioni LTI</span><span class="sxs-lookup"><span data-stu-id="c7450-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="c7450-182">Se si sceglie di approvare l'app Azure Learn Ultra Teams Classes di Blackboard prima di configurare le integrazioni LTI, sarà necessario reindirizzare all'endpoint di consenso dell'amministratore di **Microsoft Identity Platform.**</span><span class="sxs-lookup"><span data-stu-id="c7450-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="c7450-183">L'URL viene visualizzato:</span><span class="sxs-lookup"><span data-stu-id="c7450-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="c7450-184">Devi sostituire **{Tenant} con il** tuo ID tenant Microsoft Azure istituzionale specifico.</span><span class="sxs-lookup"><span data-stu-id="c7450-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="c7450-185">Dopo aver configurato le applicazioni LTI</span><span class="sxs-lookup"><span data-stu-id="c7450-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="c7450-186">Nel Pannello **di amministrazione,** accedere a **Strumenti e utilità** e selezionare Microsoft Teams Amministratore **integrazione.**</span><span class="sxs-lookup"><span data-stu-id="c7450-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="c7450-187">Selezionare **Abilita Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="c7450-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="c7450-188">Aggiungi il **tuo ID tenant Microsoft** nel campo di testo disponibile.</span><span class="sxs-lookup"><span data-stu-id="c7450-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="c7450-189">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7450-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="c7450-190">Se l'app ha il pre-consenso, mostrerà un piccolo segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="c7450-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="c7450-191">Se viene visualizzato il segno di spunta, selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7450-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="c7450-192">Se il consenso non è stato approvato, seguire la procedura descritta per generare l'URL per il consenso e inviarlo all'amministratore globale Microsoft 365 per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="c7450-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="c7450-193">Dopo aver confermato l'approvazione, selezionare **Riprova** per confermare e quindi selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="c7450-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>
