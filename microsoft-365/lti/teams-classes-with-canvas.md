---
title: Usare Microsoft Teams classi con Canvas
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
description: Integrare Microsoft Teams classi con Canvas
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821903"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="9e183-103">Usare Microsoft Teams classi con Canvas</span><span class="sxs-lookup"><span data-stu-id="9e183-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e183-104">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="9e183-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9e183-105">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="9e183-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9e183-106">Microsoft Teams è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il sistema di gestione dell'apprendimento (LMS) e il Teams.</span><span class="sxs-lookup"><span data-stu-id="9e183-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="9e183-107">Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="9e183-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="9e183-108">Microsoft Office 365 Amministratore</span><span class="sxs-lookup"><span data-stu-id="9e183-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="9e183-109">Prima di gestire l'integrazione di Microsoft Teams in Instructure Canvas, è importante che l'app **Microsoft-Teams-Sync-for-Canvas** di Canvas di Canvas venga approvata dall'amministratore di Microsoft Office 365 dell'istituto nel tenant di Microsoft Azure prima di completare la configurazione dell'amministratore di Canvas.</span><span class="sxs-lookup"><span data-stu-id="9e183-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="9e183-110">Accedi a Canvas.</span><span class="sxs-lookup"><span data-stu-id="9e183-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="9e183-111">Seleziona il **collegamento** Amministratore nella struttura di spostamento globale e quindi seleziona il tuo account.</span><span class="sxs-lookup"><span data-stu-id="9e183-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="9e183-112">Nella struttura di spostamento dell'amministratore **seleziona il Impostazioni** e quindi la **scheda** Integrazioni.</span><span class="sxs-lookup"><span data-stu-id="9e183-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="9e183-113">Immettere il nome del tenant Microsoft e l'attributo di accesso.</span><span class="sxs-lookup"><span data-stu-id="9e183-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="9e183-114">L'attributo login verrà usato per associare l'utente Canvas a un Azure Active Directory utente.</span><span class="sxs-lookup"><span data-stu-id="9e183-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="9e183-115">Seleziona **Aggiorna Impostazioni** una volta fatto.</span><span class="sxs-lookup"><span data-stu-id="9e183-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="9e183-116">Per approvare l'accesso per l'app **Microsoft-Teams-Sync-for-Canvas di** Azure di Canvas, seleziona il collegamento **Concedi accesso tenant.**</span><span class="sxs-lookup"><span data-stu-id="9e183-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="9e183-117">Sarai reindirizzato all'endpoint di consenso dell'amministratore di Microsoft Identity Platform.</span><span class="sxs-lookup"><span data-stu-id="9e183-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![autorizzazioni](media/permissions.png)

7. <span data-ttu-id="9e183-119">Selezionare **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="9e183-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="9e183-120">Abilita la Microsoft Teams sincronizzazione attivando l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="9e183-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="9e183-122">Amministratore canvas</span><span class="sxs-lookup"><span data-stu-id="9e183-122">Canvas Admin</span></span>

<span data-ttu-id="9e183-123">Configurare l'Microsoft Teams LTI 1.3 Integration.</span><span class="sxs-lookup"><span data-stu-id="9e183-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="9e183-124">Come amministratore di Canvas, dovrai aggiungere l'app LTI Microsoft Teams classi LTI all'interno del tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="9e183-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="9e183-125">Prendere nota dell'ID client LTI per l'app.</span><span class="sxs-lookup"><span data-stu-id="9e183-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="9e183-126">Microsoft Teams - 17000000000570</span><span class="sxs-lookup"><span data-stu-id="9e183-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="9e183-127">Accedere **alle impostazioni di amministrazione**  >  **App**.</span><span class="sxs-lookup"><span data-stu-id="9e183-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="9e183-128">Seleziona **+ App** per aggiungere le app Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="9e183-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="9e183-130">Selezionare **Per ID client per** tipo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9e183-130">Select **By Client ID** for configuration type.</span></span>

   ![aggiungere app](media/add-app.png)

4. <span data-ttu-id="9e183-132">Immetti l'ID client fornito e quindi seleziona **Invia.**</span><span class="sxs-lookup"><span data-stu-id="9e183-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="9e183-133">Noterai il nome dell'app LTI Microsoft Teams classi LTI per l'ID client per la conferma.</span><span class="sxs-lookup"><span data-stu-id="9e183-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="9e183-134">Selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="9e183-134">Select **Install**.</span></span>

   <span data-ttu-id="9e183-135">Le Microsoft Teams app LTI verranno aggiunte all'elenco delle app esterne.</span><span class="sxs-lookup"><span data-stu-id="9e183-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
