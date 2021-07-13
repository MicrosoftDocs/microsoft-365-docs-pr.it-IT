---
title: Usare Microsoft Teams riunioni con Canvas
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
description: Integrare Microsoft Teams riunioni con Canvas
ms.openlocfilehash: 7e13052cb029fef369f6386c2039785e40acc4ff
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409093"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="bf5d4-103">Usare Microsoft Teams riunioni con Canvas</span><span class="sxs-lookup"><span data-stu-id="bf5d4-103">Use Microsoft Teams meetings with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf5d4-104">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bf5d4-105">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="bf5d4-106">Microsoft Teams riunioni è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il sistema di gestione di Learning (LMS) e il Teams.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-106">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="bf5d4-107">Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="bf5d4-108">Microsoft Office 365 Amministratore</span><span class="sxs-lookup"><span data-stu-id="bf5d4-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="bf5d4-109">Prima di gestire l'integrazione di Microsoft Teams in Instructure Canvas, è importante che l'app **Microsoft-Teams-Sync-for-Canvas** di Canvas di Canvas venga approvata dall'amministratore di Microsoft Office 365 dell'istituto nel tenant di Microsoft Azure prima di completare la configurazione dell'amministratore di Canvas.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="bf5d4-110">Accedi a Canvas.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-110">Sign in to Canvas.</span></span>

2. <span data-ttu-id="bf5d4-111">Seleziona il **collegamento** Amministratore nella struttura di spostamento globale e quindi seleziona il tuo account.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="bf5d4-112">Nella struttura di spostamento dell'amministratore **seleziona il Impostazioni** e quindi la **scheda** Integrazioni.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="bf5d4-113">Immettere il nome del tenant Microsoft e l'attributo di accesso.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-113">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="bf5d4-114">L'attributo login verrà usato per associare l'utente Canvas a un Azure Active Directory utente.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="bf5d4-115">Seleziona **Aggiorna Impostazioni** una volta fatto.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="bf5d4-116">Per approvare l'accesso per l'app **Microsoft-Teams-Sync-for-Canvas di** Azure di Canvas, seleziona il collegamento **Concedi accesso tenant.**</span><span class="sxs-lookup"><span data-stu-id="bf5d4-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="bf5d4-117">Sarai reindirizzato all'endpoint di consenso dell'amministratore di Microsoft Identity Platform.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![autorizzazioni](media/permissions.png)

7. <span data-ttu-id="bf5d4-119">Selezionare **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-119">Select **Accept**.</span></span>

8. <span data-ttu-id="bf5d4-120">Abilita la Microsoft Teams sincronizzazione attivando l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="bf5d4-122">Amministratore canvas</span><span class="sxs-lookup"><span data-stu-id="bf5d4-122">Canvas Admin</span></span>

<span data-ttu-id="bf5d4-123">Configurare l'Microsoft Teams LTI 1.3 Integration.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="bf5d4-124">Come amministratore di Canvas, dovrai aggiungere l'app LTI per Microsoft Teams riunioni all'interno dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-124">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="bf5d4-125">Prendere nota dell'ID client LTI per l'app.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="bf5d4-126">Microsoft Teams riunioni - 17000000000703</span><span class="sxs-lookup"><span data-stu-id="bf5d4-126">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="bf5d4-127">Accedere **alle impostazioni di amministrazione**  >  **App**.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="bf5d4-128">Seleziona **+ App** per aggiungere le app Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-128">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="bf5d4-130">Selezionare **Per ID client per** tipo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-130">Select **By Client ID** for configuration type.</span></span>

   ![aggiungere app](media/add-app.png)

4. <span data-ttu-id="bf5d4-132">Immetti l'ID client fornito e quindi seleziona **Invia.**</span><span class="sxs-lookup"><span data-stu-id="bf5d4-132">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="bf5d4-133">Noterai il nome dell'app LTI Microsoft Teams riunioni per l'ID client per la conferma.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-133">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="bf5d4-134">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-134">Select **Install**.</span></span>

   <span data-ttu-id="bf5d4-135">L Microsoft Teams l'app LTI per le riunioni verrà aggiunta all'elenco delle app esterne.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-135">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="bf5d4-136">Abilita per i corsi Canvas</span><span class="sxs-lookup"><span data-stu-id="bf5d4-136">Enable for Canvas Courses</span></span>

<span data-ttu-id="bf5d4-137">Per usare l'LTI all'interno di un corso, un istruttore del corso Canvas deve abilitare la sincronizzazione delle integrazioni. Ogni corso deve essere abilitato da un docente per creare un Teams corrispondente; non esiste alcun meccanismo globale per la Teams creazione.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-137">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="bf5d4-138">Questo è progettato per evitare la creazione di Teams indesiderati.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-138">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="bf5d4-139">Fai riferimento agli istruttori alla [documentazione per i docenti](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) per abilitare l'LTI per ogni corso e completare la configurazione dell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="bf5d4-139">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
