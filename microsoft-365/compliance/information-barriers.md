---
title: Informazioni sulle barriere informative
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare le barriere informative per garantire la conformità della comunicazione tramite Microsoft teams all'interno dell'organizzazione.
ms.openlocfilehash: f063a18dcadf5de74b43b2efeba3910f65e40102
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153498"
---
# <a name="information-barriers"></a><span data-ttu-id="654e1-103">Barriere informative</span><span class="sxs-lookup"><span data-stu-id="654e1-103">Information barriers</span></span>

## <a name="overview"></a><span data-ttu-id="654e1-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="654e1-104">Overview</span></span>

<!--

# Information barriers (click-through test)

## Overview



 [![Click-Through for Information Barriers](./media/information-barriers/clickthrough-information-barriers-thumbnail.png)](./media/information-barriers/clickthrough-information-barriers.pdf)


Click through an overview of Information Barriers: [PDF](./media/information-barriers/clickthrough-information-barriers.pdf) | [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/Clickthrough-Information-Barriers.pptx)

OLD: Move comment field here

 [![Click-Through for Information Barriers](./media/information-barriers/Clickthrough_InformationBarriers_Thumbnail.png)](./media/information-barriers/Clickthrough_InformationBarriers.pdf)

For the PowerPoint slide of this Click-Through, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/InfoBarriersExample.pptx).

>[!Tip]
>Try this new [Click-Through on information barriers](media/information-barriers/Clickthrough_InformationBarriers.pdf) for a quick overview of the essential facts.
>

--> 


<span data-ttu-id="654e1-105">I servizi cloud Microsoft includono potenti funzionalità di comunicazione e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="654e1-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="654e1-106">Tuttavia, si supponga di voler limitare le comunicazioni tra due gruppi per evitare che si verifichi un conflitto di interessi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="654e1-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="654e1-107">In alternativa, è possibile limitare le comunicazioni tra alcune persone all'interno dell'organizzazione per salvaguardare le informazioni interne.</span><span class="sxs-lookup"><span data-stu-id="654e1-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="654e1-108">Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni, quindi è possibile limitare le comunicazioni tra i gruppi di utenti specifici, se necessario.</span><span class="sxs-lookup"><span data-stu-id="654e1-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="654e1-109">Con barriere informative, è possibile!</span><span class="sxs-lookup"><span data-stu-id="654e1-109">With information barriers, you can!</span></span> 

<span data-ttu-id="654e1-110">Gli ostacoli alle informazioni stanno per essere implementati ora, a partire da Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="654e1-110">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="654e1-111">Presupponendo che la [sottoscrizione](#required-licenses-and-permissions) includa barriere informative, un amministratore di conformità o un amministratore delle informazioni barriere può definire criteri per consentire o impedire le comunicazioni tra gruppi di utenti in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="654e1-111">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="654e1-112">I criteri di barriera delle informazioni possono essere utilizzati per situazioni come queste:</span><span class="sxs-lookup"><span data-stu-id="654e1-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="654e1-113">L'utente del gruppo trader diurno non deve comunicare con il team di marketing</span><span class="sxs-lookup"><span data-stu-id="654e1-113">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="654e1-114">Il personale finanziario che lavora su informazioni aziendali riservate non deve comunicare con alcuni gruppi all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="654e1-114">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="654e1-115">Un team interno con materiale segreto commerciale non deve chiamare o chattare online con persone di alcuni gruppi all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="654e1-115">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="654e1-116">Un team di ricerca deve chiamare o chattare online solo con un team di sviluppo del prodotto</span><span class="sxs-lookup"><span data-stu-id="654e1-116">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="654e1-117">Barriere informative ***supportano solo*** due restrizioni di modalità.</span><span class="sxs-lookup"><span data-stu-id="654e1-117">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="654e1-118">Restrizioni a un modo, come il marketing può comunicare con i commercianti diurni, ma i trader diurni non possono comunicare con il marketing ***non è supportato***.</span><span class="sxs-lookup"><span data-stu-id="654e1-118">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="654e1-119">Per tutti questi scenari di esempio e altro ancora, è possibile definire i criteri di barriera delle informazioni per impedire o consentire le comunicazioni in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="654e1-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="654e1-120">Tali criteri possono impedire agli utenti di effettuare chiamate o chattare con coloro che non devono o consentire agli utenti di comunicare solo con gruppi specifici in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="654e1-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="654e1-121">Con i criteri di protezione delle informazioni in vigore, quando gli utenti interessati da tali criteri tentano di comunicare con altri membri di Microsoft teams, vengono eseguiti i controlli per impedire (o consentire) la comunicazione (come definito dai criteri di barriera delle informazioni).</span><span class="sxs-lookup"><span data-stu-id="654e1-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="654e1-122">Per ulteriori informazioni sull'esperienza utente con barriere informative, vedere [barriere informative in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="654e1-122">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="654e1-123">Attualmente, le barriere informative non si applicano alle comunicazioni di posta elettronica o alla condivisione di file tramite SharePoint Online o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="654e1-123">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="654e1-124">Inoltre, le barriere informative sono indipendenti dai [limiti di conformità](set-up-compliance-boundaries.md).</span><span class="sxs-lookup"><span data-stu-id="654e1-124">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="654e1-125">Prima di definire e applicare i criteri di barriera delle informazioni, assicurarsi che l'organizzazione non disponga di [Criteri rubrica di Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in vigore.</span><span class="sxs-lookup"><span data-stu-id="654e1-125">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="654e1-126">(Le barriere informative si basano sui criteri della rubrica).</span><span class="sxs-lookup"><span data-stu-id="654e1-126">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="654e1-127">Cosa accade con barriere informative</span><span class="sxs-lookup"><span data-stu-id="654e1-127">What happens with information barriers</span></span>

<span data-ttu-id="654e1-128">Quando vengono attivati i criteri di protezione delle informazioni, gli utenti che non devono comunicare con altri utenti specifici non saranno in grado di trovare, selezionare, chattare o chiamare tali utente.</span><span class="sxs-lookup"><span data-stu-id="654e1-128">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="654e1-129">Con barriere informative, sono disponibili controlli che impediscono la comunicazione non autorizzata.</span><span class="sxs-lookup"><span data-stu-id="654e1-129">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="654e1-130">Inizialmente, gli ostacoli alle informazioni si applicano solo alle chat e ai canali di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="654e1-130">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="654e1-131">In Microsoft teams, i criteri barriera di informazioni determinano e impediscono i seguenti tipi di comunicazioni non autorizzate:</span><span class="sxs-lookup"><span data-stu-id="654e1-131">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="654e1-132">Ricerca di un utente</span><span class="sxs-lookup"><span data-stu-id="654e1-132">Searching for a user</span></span>
- <span data-ttu-id="654e1-133">Aggiunta di un membro a un team</span><span class="sxs-lookup"><span data-stu-id="654e1-133">Adding a member to a team</span></span>
- <span data-ttu-id="654e1-134">Avvio di una sessione di chat con un utente</span><span class="sxs-lookup"><span data-stu-id="654e1-134">Starting a chat session with someone</span></span>
- <span data-ttu-id="654e1-135">Avvio di una chat di gruppo</span><span class="sxs-lookup"><span data-stu-id="654e1-135">Starting a group chat</span></span>
- <span data-ttu-id="654e1-136">Invitare un utente a partecipare a una riunione</span><span class="sxs-lookup"><span data-stu-id="654e1-136">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="654e1-137">Condivisione di una schermata</span><span class="sxs-lookup"><span data-stu-id="654e1-137">Sharing a screen</span></span>
- <span data-ttu-id="654e1-138">Effettuazione di una chiamata</span><span class="sxs-lookup"><span data-stu-id="654e1-138">Placing a call</span></span> 

<span data-ttu-id="654e1-139">Se le persone coinvolte sono incluse in un criterio barriera informativo per impedire l'attività, non saranno in grado di procedere.</span><span class="sxs-lookup"><span data-stu-id="654e1-139">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="654e1-140">Inoltre, potenzialmente, tutti gli elementi inclusi in un criterio barriera informativo possono essere bloccati dalla comunicazione con altri utenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="654e1-140">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="654e1-141">Quando le persone coinvolte nei criteri di barriera delle informazioni fanno parte dello stesso team o chat di gruppo, potrebbero essere rimosse dalle sessioni di chat e potrebbe non essere consentita un'ulteriore comunicazione con il gruppo.</span><span class="sxs-lookup"><span data-stu-id="654e1-141">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="654e1-142">Per ulteriori informazioni sull'esperienza utente con barriere informative, vedere [barriere informative in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="654e1-142">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="654e1-143">Licenze e autorizzazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="654e1-143">Required licenses and permissions</span></span>

<span data-ttu-id="654e1-144">Gli ostacoli alle informazioni stanno per essere implementati e sono inclusi negli abbonamenti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="654e1-144">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="654e1-145">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="654e1-145">Microsoft 365 E5</span></span>
- <span data-ttu-id="654e1-146">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="654e1-146">Office 365 E5</span></span>
- <span data-ttu-id="654e1-147">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="654e1-147">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="654e1-148">Microsoft 365 E5 Information Protection and Compliance</span><span class="sxs-lookup"><span data-stu-id="654e1-148">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="654e1-149">Per ulteriori informazioni, vedere [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span><span class="sxs-lookup"><span data-stu-id="654e1-149">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="654e1-150">Per [definire o modificare criteri di barriera delle informazioni](information-barriers-policies.md), è necessario essere assegnati a uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="654e1-150">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="654e1-151">Microsoft 365 amministratore globale</span><span class="sxs-lookup"><span data-stu-id="654e1-151">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="654e1-152">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="654e1-152">Office 365 global administrator</span></span>
- <span data-ttu-id="654e1-153">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="654e1-153">Compliance administrator</span></span>
- <span data-ttu-id="654e1-154">IB Compliance Management (questo è un nuovo ruolo)</span><span class="sxs-lookup"><span data-stu-id="654e1-154">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="654e1-155">Per ulteriori informazioni sui ruoli e le autorizzazioni, vedere [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="654e1-155">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="654e1-156">È necessario avere familiarità con i cmdlet di PowerShell per definire, convalidare o modificare i criteri di barriera delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="654e1-156">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="654e1-157">Anche se vengono forniti diversi esempi di cmdlet di PowerShell nell' [articolo How-to](information-barriers-policies.md), è necessario conoscere ulteriori dettagli, ad esempio i parametri, per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="654e1-157">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="654e1-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="654e1-158">Next steps</span></span>

- [<span data-ttu-id="654e1-159">Per ulteriori informazioni, vedere barriere informative in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="654e1-159">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="654e1-160">Visualizzare gli attributi che è possibile utilizzare per i criteri di barriera delle informazioni</span><span class="sxs-lookup"><span data-stu-id="654e1-160">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="654e1-161">Definire i criteri per le barriere informative</span><span class="sxs-lookup"><span data-stu-id="654e1-161">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="654e1-162">Modificare (o rimuovere) i criteri di barriera delle informazioni</span><span class="sxs-lookup"><span data-stu-id="654e1-162">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 
