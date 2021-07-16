---
title: Usare Microsoft Teams classi con Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrare Microsoft Teams classi con Canvas
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454686"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="79911-103">Usare Microsoft Teams classi con Canvas</span><span class="sxs-lookup"><span data-stu-id="79911-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="79911-104">Microsoft Teams classi è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il Learning Management System (LMS) e il Teams.</span><span class="sxs-lookup"><span data-stu-id="79911-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="79911-105">Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="79911-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="79911-106">Prerequisiti prima della distribuzione</span><span class="sxs-lookup"><span data-stu-id="79911-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="79911-107">L'oggetto Class Teams LTI supporta solo la sincronizzazione degli utenti Canvas con Microsoft Azure Active Directory (AAD) in un ambito limitato.</span><span class="sxs-lookup"><span data-stu-id="79911-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="79911-108">Il tenant deve avere una corrispondenza esatta tra un campo Canvas (e-mail, ID utente o ID SIS) e l'UPN in Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="79911-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="79911-109">Stiamo lavorando per espandere la flessibilità della funzionalità di sincronizzazione, ma nel frattempo, tutti gli utenti in Canvas non corrispondenti a un UPN in AAD non verranno aggiunti alla classe Teams sincronizzata con Canvas.</span><span class="sxs-lookup"><span data-stu-id="79911-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="79911-110">Solo un singolo tenant Microsoft può essere usato per il mapping degli utenti tra Canvas e Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79911-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="79911-111">Sarà necessario disattivare SDS prima di usare la classe Teams LTI per evitare la duplicazione dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="79911-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="79911-112">Microsoft Office 365 Amministratore</span><span class="sxs-lookup"><span data-stu-id="79911-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="79911-113">Prima di gestire l'integrazione di Microsoft Teams in Instructure Canvas, è importante che l'app **Microsoft-Teams-Sync-for-Canvas** di Canvas di Canvas venga approvata dall'amministratore di Microsoft Office 365 dell'istituto nel tenant di Microsoft Azure prima di completare la configurazione dell'amministratore di Canvas.</span><span class="sxs-lookup"><span data-stu-id="79911-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="79911-114">Accedi a Canvas.</span><span class="sxs-lookup"><span data-stu-id="79911-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="79911-115">Seleziona il **collegamento** Amministratore nella struttura di spostamento globale e quindi seleziona il tuo account.</span><span class="sxs-lookup"><span data-stu-id="79911-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="79911-116">Nella struttura di spostamento dell'amministratore **seleziona il Impostazioni** e quindi la **scheda** Integrazioni.</span><span class="sxs-lookup"><span data-stu-id="79911-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="79911-117">Abilita Microsoft Teams sincronizzazione attivando l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="79911-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="79911-119">Immettere il nome del tenant Microsoft e l'attributo di accesso.</span><span class="sxs-lookup"><span data-stu-id="79911-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="79911-120">L'attributo login verrà usato per associare l'utente Canvas a un Azure Active Directory utente.</span><span class="sxs-lookup"><span data-stu-id="79911-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="79911-121">Seleziona **Aggiorna Impostazioni** una volta fatto.</span><span class="sxs-lookup"><span data-stu-id="79911-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="79911-122">Per approvare l'accesso per l'app **Microsoft-Teams-Sync-for-Canvas di** Azure di Canvas, seleziona il collegamento **Concedi accesso tenant.**</span><span class="sxs-lookup"><span data-stu-id="79911-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="79911-123">Sarai reindirizzato all'endpoint di consenso dell'amministratore di Microsoft Identity Platform.</span><span class="sxs-lookup"><span data-stu-id="79911-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![autorizzazioni](media/permissions.png)

8. <span data-ttu-id="79911-125">Selezionare **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="79911-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="79911-126">Amministratore canvas</span><span class="sxs-lookup"><span data-stu-id="79911-126">Canvas Admin</span></span>

<span data-ttu-id="79911-127">Configurare l'Microsoft Teams LTI 1.3 Integration.</span><span class="sxs-lookup"><span data-stu-id="79911-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="79911-128">Come amministratore di Canvas, dovrai aggiungere l'app LTI Microsoft Teams classi LTI all'interno del tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="79911-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="79911-129">Prendere nota dell'ID client LTI per l'app.</span><span class="sxs-lookup"><span data-stu-id="79911-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="79911-130">Microsoft Teams - 17000000000570</span><span class="sxs-lookup"><span data-stu-id="79911-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="79911-131">Accedere **alle impostazioni di amministrazione**  >  **App**.</span><span class="sxs-lookup"><span data-stu-id="79911-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="79911-132">Seleziona **+ App** per aggiungere le app Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="79911-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="79911-134">Selezionare **Per ID client per** tipo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="79911-134">Select **By Client ID** for configuration type.</span></span>

   ![aggiungere app](media/add-app.png)

4. <span data-ttu-id="79911-136">Immetti l'ID client fornito e quindi seleziona **Invia.**</span><span class="sxs-lookup"><span data-stu-id="79911-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="79911-137">Noterai il nome dell'app LTI Microsoft Teams classi LTI per l'ID client per la conferma.</span><span class="sxs-lookup"><span data-stu-id="79911-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="79911-138">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="79911-138">Select **Install**.</span></span>

   <span data-ttu-id="79911-139">Le Microsoft Teams app LTI verranno aggiunte all'elenco delle app esterne.</span><span class="sxs-lookup"><span data-stu-id="79911-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="79911-140">Abilitazione dell'app LTI per i corsi Canvas</span><span class="sxs-lookup"><span data-stu-id="79911-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="79911-141">Per usare l'app LTI all'interno di un corso, un istruttore del corso Canvas deve abilitare la sincronizzazione delle integrazioni. Ogni corso deve essere abilitato da un docente per creare un team corrispondente; non esiste un meccanismo globale per la creazione di team.</span><span class="sxs-lookup"><span data-stu-id="79911-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="79911-142">Questo è progettato come misura precauzionale per impedire la creazione di team indesiderati.</span><span class="sxs-lookup"><span data-stu-id="79911-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="79911-143">Per abilitare l'app LTI per ogni corso e completare [la](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) configurazione dell'integrazione, fare riferimento agli istruttori alla documentazione per i docenti.</span><span class="sxs-lookup"><span data-stu-id="79911-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
