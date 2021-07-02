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
ms.openlocfilehash: 50e4e8ef912a8f19f379bba29b328a5a27358b5c
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256904"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="8db1b-103">Usare Microsoft Teams classi con Canvas</span><span class="sxs-lookup"><span data-stu-id="8db1b-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8db1b-104">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="8db1b-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8db1b-105">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="8db1b-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8db1b-106">Microsoft Teams classi è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il Learning Management System (LMS) e il Teams.</span><span class="sxs-lookup"><span data-stu-id="8db1b-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="8db1b-107">Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="8db1b-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="8db1b-108">Microsoft Office 365 Amministratore</span><span class="sxs-lookup"><span data-stu-id="8db1b-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="8db1b-109">Prima di gestire l'integrazione di Microsoft Teams in Instructure Canvas, è importante che l'app **Microsoft-Teams-Sync-for-Canvas** di Canvas di Canvas venga approvata dall'amministratore di Microsoft Office 365 dell'istituto nel tenant di Microsoft Azure prima di completare la configurazione dell'amministratore di Canvas.</span><span class="sxs-lookup"><span data-stu-id="8db1b-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="8db1b-110">Accedi a Canvas.</span><span class="sxs-lookup"><span data-stu-id="8db1b-110">Sign in to Canvas.</span></span>

2. <span data-ttu-id="8db1b-111">Seleziona il **collegamento** Amministratore nella struttura di spostamento globale e quindi seleziona il tuo account.</span><span class="sxs-lookup"><span data-stu-id="8db1b-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="8db1b-112">Nella struttura di spostamento dell'amministratore **seleziona il Impostazioni** e quindi la **scheda** Integrazioni.</span><span class="sxs-lookup"><span data-stu-id="8db1b-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="8db1b-113">Abilita Microsoft Teams sincronizzazione attivando l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="8db1b-113">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="8db1b-115">Immettere il nome del tenant Microsoft e l'attributo di accesso.</span><span class="sxs-lookup"><span data-stu-id="8db1b-115">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="8db1b-116">L'attributo login verrà usato per associare l'utente Canvas a un Azure Active Directory utente.</span><span class="sxs-lookup"><span data-stu-id="8db1b-116">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="8db1b-117">Seleziona **Aggiorna Impostazioni** una volta fatto.</span><span class="sxs-lookup"><span data-stu-id="8db1b-117">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="8db1b-118">Per approvare l'accesso per l'app **Microsoft-Teams-Sync-for-Canvas di** Azure di Canvas, seleziona il collegamento **Concedi accesso tenant.**</span><span class="sxs-lookup"><span data-stu-id="8db1b-118">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="8db1b-119">Sarai reindirizzato all'endpoint di consenso dell'amministratore di Microsoft Identity Platform.</span><span class="sxs-lookup"><span data-stu-id="8db1b-119">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![autorizzazioni](media/permissions.png)

8. <span data-ttu-id="8db1b-121">Selezionare **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="8db1b-121">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="8db1b-122">Amministratore canvas</span><span class="sxs-lookup"><span data-stu-id="8db1b-122">Canvas Admin</span></span>

<span data-ttu-id="8db1b-123">Configurare l'Microsoft Teams LTI 1.3 Integration.</span><span class="sxs-lookup"><span data-stu-id="8db1b-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="8db1b-124">Come amministratore di Canvas, dovrai aggiungere l'app LTI Microsoft Teams classi LTI all'interno del tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="8db1b-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="8db1b-125">Prendere nota dell'ID client LTI per l'app.</span><span class="sxs-lookup"><span data-stu-id="8db1b-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="8db1b-126">Microsoft Teams - 17000000000570</span><span class="sxs-lookup"><span data-stu-id="8db1b-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="8db1b-127">Accedere **alle impostazioni di amministrazione**  >  **App**.</span><span class="sxs-lookup"><span data-stu-id="8db1b-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="8db1b-128">Seleziona **+ App** per aggiungere le app Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="8db1b-128">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="8db1b-130">Selezionare **Per ID client per** tipo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8db1b-130">Select **By Client ID** for configuration type.</span></span>

   ![aggiungere app](media/add-app.png)

4. <span data-ttu-id="8db1b-132">Immetti l'ID client fornito e quindi seleziona **Invia.**</span><span class="sxs-lookup"><span data-stu-id="8db1b-132">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="8db1b-133">Noterai il nome dell'app LTI Microsoft Teams classi LTI per l'ID client per la conferma.</span><span class="sxs-lookup"><span data-stu-id="8db1b-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="8db1b-134">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="8db1b-134">Select **Install**.</span></span>

   <span data-ttu-id="8db1b-135">Le Microsoft Teams app LTI verranno aggiunte all'elenco delle app esterne.</span><span class="sxs-lookup"><span data-stu-id="8db1b-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
