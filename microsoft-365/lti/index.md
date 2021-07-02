---
title: Panoramica sulle app LTI
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman, sovaish
ms.date: 06/15/2021
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- M365-modern-desktop
localization_priority: None
description: Informazioni sulle app Office Learning Tools Interoperability (LTI) in M365 e su come aiuteranno i docenti nell'integrazione delle app di Office nel sistema di gestione di Learning (LMS).
ms.openlocfilehash: 4fd7b25b6463eec4f681e3090bb65db8b00351a8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256679"
---
# <a name="integrating-microsoft-products-with-your-learning-management-system-lms"></a><span data-ttu-id="b058f-103">Integrazione dei prodotti Microsoft con Learning Management System (LMS)</span><span class="sxs-lookup"><span data-stu-id="b058f-103">Integrating Microsoft products with your Learning Management System (LMS)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b058f-104">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="b058f-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b058f-105">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="b058f-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

- [<span data-ttu-id="b058f-106">OneDrive LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="b058f-106">OneDrive LTI with Canvas</span></span>](#onedrive-lti-with-canvas)
- [<span data-ttu-id="b058f-107">Teams Riunioni LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="b058f-107">Teams Meetings LTI with Canvas</span></span>](#teams-meetings-lti-with-canvas)
- [<span data-ttu-id="b058f-108">Teams Classi LTI</span><span class="sxs-lookup"><span data-stu-id="b058f-108">Teams Classes LTI</span></span>](#teams-classes-lti)

<span data-ttu-id="b058f-109">Microsoft Education e i partner di terze parti comprendono che il flusso di insegnamento e apprendimento supera invariabilmente i limiti della soluzione.</span><span class="sxs-lookup"><span data-stu-id="b058f-109">Microsoft Education and our third-party partners understand that the flow of teaching and learning invariably crosses solution boundaries.</span></span> <span data-ttu-id="b058f-110">Stiamo lavorando per offrire esperienze più semplici, mantenendo docenti e studenti concentrati sui loro obiettivi, invece di dover giocoleggiare gli strumenti.</span><span class="sxs-lookup"><span data-stu-id="b058f-110">We're working on providing more seamless experiences, keeping educators and learners focused on their goals, rather than having to juggle tools.</span></span> <span data-ttu-id="b058f-111">Stiamo integrando i prodotti Microsoft ovunque si verifichi l'insegnamento e l'apprendimento, anche all'interno e insieme a Learning Management Systems (LMS).</span><span class="sxs-lookup"><span data-stu-id="b058f-111">We're integrating Microsoft products wherever teaching and learning occurs, including within and alongside Learning Management Systems (LMS).</span></span> <span data-ttu-id="b058f-112">Abbiamo collaborato con i nostri partner LMS per creare una famiglia di strumenti utilizzando lo [standard LTI (Learning Tools Interoperability)](https://www.imsglobal.org/activity/learning-tools-interoperability) che offre il meglio di Microsoft direttamente nel sistema LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-112">We've worked with our LMS partners to create a suite of tools using the [Learning Tools Interoperability (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) that brings the best of Microsoft directly into your LMS.</span></span>

<span data-ttu-id="b058f-113">Questi strumenti includono una nuova app OneDrive LTI, una nuova app Teams Meetings LTI e una nuova app Class Teams LTI.</span><span class="sxs-lookup"><span data-stu-id="b058f-113">These tools include a new OneDrive LTI app, a new Teams Meetings LTI app, and a new Class Teams LTI app.</span></span> <span data-ttu-id="b058f-114">Questi nuovi strumenti sono altamente sicuri e completamente compatibili con gli standard LTI 1.3 e LTI Advantage.</span><span class="sxs-lookup"><span data-stu-id="b058f-114">These new tools are highly secure and fully compatible with LTI 1.3 and LTI Advantage standards.</span></span> <span data-ttu-id="b058f-115">L OneDrive app LTI consente a docenti e studenti di portare OneDrive archiviazione cloud e file Office 365 direttamente nei flussi di lavoro di assegnazione e creazione di contenuto all'interno di un sistema LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-115">The OneDrive LTI app allows educators and students to bring OneDrive cloud storage and Office 365 files directly into assignment and content creation workflows within an LMS.</span></span> <span data-ttu-id="b058f-116">L Teams Meeting LTI consente a docenti e studenti di gestire, pianificare e accedere alle riunioni Teams da un hub riunioni nel proprio sistema LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-116">The Teams Meetings LTI app allows educators and students to manage, schedule, and access their Teams Meetings from within a meetings hub in their LMS.</span></span> <span data-ttu-id="b058f-117">L'app Class Teams LTI consente ai docenti di creare un team per il loro corso all'interno del loro sistema LMS usando l'elenco dei corsi LMS con gli aggiornamenti giornalieri dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b058f-117">The Class Teams LTI app allows educators to create a team for their course within their LMS using the LMS course roster with daily roster updates.</span></span> <span data-ttu-id="b058f-118">Gli studenti possono quindi accedere al team direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-118">Students can then access the team right from within the LMS.</span></span> <span data-ttu-id="b058f-119">Siamo felici di portare questi nuovi strumenti ai clienti e continuare a migliorare le nostre soluzioni in base al tuo feedback.</span><span class="sxs-lookup"><span data-stu-id="b058f-119">We are excited to bring these new tools to customers and continue to improve our solutions according to your feedback.</span></span>

## <a name="onedrive-lti-with-canvas"></a><span data-ttu-id="b058f-120">OneDrive LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="b058f-120">OneDrive LTI with Canvas</span></span>

<span data-ttu-id="b058f-121">Altre informazioni sull'Microsoft OneDrive con il Learning Management System (LMS).</span><span class="sxs-lookup"><span data-stu-id="b058f-121">Learn more about using Microsoft OneDrive with your Learning Management System (LMS).</span></span>

- <span data-ttu-id="b058f-122">**Consente Microsoft Office 365 direttamente nei flussi di lavoro**</span><span class="sxs-lookup"><span data-stu-id="b058f-122">**Brings Microsoft Office 365 directly into your workflows**</span></span>

<span data-ttu-id="b058f-123">L Microsoft OneDrive'app LTI si integra con il sistema LMS per Microsoft OneDrive e Microsoft Office 365 direttamente nei flussi di lavoro più importanti che includono:</span><span class="sxs-lookup"><span data-stu-id="b058f-123">The Microsoft OneDrive LTI app integrates with your LMS to bring Microsoft OneDrive and Microsoft Office 365 directly into your most important workflows that include:</span></span>

- <span data-ttu-id="b058f-124">Allegare risorse e organizzare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b058f-124">Attaching resources and organizing content.</span></span>
- <span data-ttu-id="b058f-125">Avvio di documenti di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="b058f-125">Starting collaborative documents.</span></span>
- <span data-ttu-id="b058f-126">Creazione e classificazione delle assegnazioni.</span><span class="sxs-lookup"><span data-stu-id="b058f-126">Creating and grading assignments.</span></span>

- <span data-ttu-id="b058f-127">**Sicuro e completamente conforme agli standard LTI più recenti**</span><span class="sxs-lookup"><span data-stu-id="b058f-127">**Secure and fully compliant with latest LTI standards**</span></span>

<span data-ttu-id="b058f-128">L Microsoft OneDrive app LTI è compatibile con LTI 1.3 e LTI Advantage.</span><span class="sxs-lookup"><span data-stu-id="b058f-128">The Microsoft OneDrive LTI App is compatible with LTI 1.3 and LTI Advantage.</span></span> <span data-ttu-id="b058f-129">Questo vantaggio consente un'esperienza utente altamente sicura e strettamente integrata.</span><span class="sxs-lookup"><span data-stu-id="b058f-129">This advantage allows for a highly secure and tightly integrated user experience.</span></span>

- <span data-ttu-id="b058f-130">**Esperienza utente moderna e ricca**</span><span class="sxs-lookup"><span data-stu-id="b058f-130">**Modern and Rich User Experience**</span></span>

<span data-ttu-id="b058f-131">L Microsoft OneDrive app LTI offre il meglio di Microsoft direttamente nell'esperienza LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-131">The Microsoft OneDrive LTI App brings the best of Microsoft right into your LMS experience.</span></span> <span data-ttu-id="b058f-132">Stiamo migliorando l'integrazione di Office 365 esistente nel sistema LMS offrendo un'esperienza utente più moderna, completa di una selezione file Microsoft OneDrive nuova ed estesa e di esperienze di modifica più complete per i file Office.</span><span class="sxs-lookup"><span data-stu-id="b058f-132">We're improving upon the existing Office 365 integration in your LMS by delivering a more modern user experience, complete with a new and expanded Microsoft OneDrive file picker and richer editing experiences for Office files.</span></span> <span data-ttu-id="b058f-133">Microsoft sarà anche completamente proprietaria dell'Microsoft OneDrive LTI App in futuro, il che significa che potrai sempre ottenere automaticamente le versioni più recenti e più recenti di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b058f-133">Microsoft will also fully own the Microsoft OneDrive LTI App going forward, which means you’ll always get the latest and greatest from Microsoft automatically.</span></span>

<span data-ttu-id="b058f-134">L Microsoft OneDrive app LTI consente di:</span><span class="sxs-lookup"><span data-stu-id="b058f-134">The Microsoft OneDrive LTI App allows you to:</span></span>

- <span data-ttu-id="b058f-135">Allegare Office 365 file di Word, inclusi documenti di Word, PowerPoint presentazioni e Excel dall'Editor contenuto rtf.</span><span class="sxs-lookup"><span data-stu-id="b058f-135">Attach Office 365 files including Word documents, PowerPoint presentations, and Excel from the Rich Content Editor.</span></span>
- <span data-ttu-id="b058f-136">Distribuire Office 365 assegnazioni cloud.</span><span class="sxs-lookup"><span data-stu-id="b058f-136">Distribute Office 365 cloud assignments.</span></span>
- <span data-ttu-id="b058f-137">Visualizzare e organizzare i file personali e Microsoft OneDrive corso.</span><span class="sxs-lookup"><span data-stu-id="b058f-137">View and organize your personal and course Microsoft OneDrive files.</span></span>
- <span data-ttu-id="b058f-138">Creare collaborazioni in cui i membri del corso possono collaborare a documenti condivisi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="b058f-138">Create collaborations where course members can work together on shared documents in real time.</span></span>
- <span data-ttu-id="b058f-139">Accedere a più Microsoft OneDrive, inclusi gli account personali e dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="b058f-139">Access multiple Microsoft OneDrive accounts, including personal and school accounts.</span></span>
- <span data-ttu-id="b058f-140">Integrare Office 365 file con i moduli del corso.</span><span class="sxs-lookup"><span data-stu-id="b058f-140">Integrate Office 365 files with your course modules.</span></span>
- <span data-ttu-id="b058f-141">Usa il tuo account Microsoft per l'accesso Single #A0 con il sistema LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-141">Use your Microsoft account for single sign-on with your LMS.</span></span>

<span data-ttu-id="b058f-142">Per la procedura di configurazione, vedi [Usare Microsoft OneDrive LTI con Canvas.](use-onedrive-with-lms.md)</span><span class="sxs-lookup"><span data-stu-id="b058f-142">For configuration steps, see [Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md).</span></span>

## <a name="teams-lti-apps"></a><span data-ttu-id="b058f-143">Teams App LTI</span><span class="sxs-lookup"><span data-stu-id="b058f-143">Teams LTI apps</span></span>

### <a name="teams-meetings-lti-with-canvas"></a><span data-ttu-id="b058f-144">Teams Riunioni LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="b058f-144">Teams Meetings LTI with Canvas</span></span>

<span data-ttu-id="b058f-145">Microsoft Teams riunioni LTI consente agli amministratori di incorporare Teams riunioni nel corso LMS dell'istituto didattico.</span><span class="sxs-lookup"><span data-stu-id="b058f-145">Microsoft Teams meetings LTI app helps admins incorporate Teams meetings into their educational institution's LMS course.</span></span> <span data-ttu-id="b058f-146">I docenti e gli studenti possono visualizzare le riunioni passate e future, pianificare riunioni individuali o ricorrenti e partecipare alle riunioni del team relative al corso, tutte all'interno del proprio sistema LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-146">Educators and students can view past and upcoming meetings, schedule individual or recurring meetings, and join team meetings related to the course, all from within their LMS.</span></span>

<span data-ttu-id="b058f-147">Per la procedura di configurazione, vedi [Usare Microsoft Teams riunioni con Canvas.](teams-meetings-with-canvas.md)</span><span class="sxs-lookup"><span data-stu-id="b058f-147">For configuration steps, see [Use Microsoft Teams meetings with Canvas](teams-meetings-with-canvas.md).</span></span>

### <a name="teams-classes-lti"></a><span data-ttu-id="b058f-148">Teams Classi LTI</span><span class="sxs-lookup"><span data-stu-id="b058f-148">Teams Classes LTI</span></span>

<span data-ttu-id="b058f-149">L Microsoft Teams l'app LTI aiuta docenti e studenti a spostarsi tra il sistema LMS e Teams.</span><span class="sxs-lookup"><span data-stu-id="b058f-149">The Microsoft Teams classes LTI app helps educators and students navigate between their LMS and Teams.</span></span> <span data-ttu-id="b058f-150">Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.</span><span class="sxs-lookup"><span data-stu-id="b058f-150">Users can access their class teams associated with their course directly from within their LMS.</span></span> <span data-ttu-id="b058f-151">Di seguito sono riportati i passaggi di configurazione:</span><span class="sxs-lookup"><span data-stu-id="b058f-151">You can find configuration steps below:</span></span>

- <span data-ttu-id="b058f-152">**Teams classi LTI con Canvas Usare** [Microsoft Teams classi con Canvas](teams-classes-with-canvas.md).</span><span class="sxs-lookup"><span data-stu-id="b058f-152">**Teams Classes LTI with Canvas** [Use Microsoft Teams classes with Canvas](teams-classes-with-canvas.md).</span></span>
