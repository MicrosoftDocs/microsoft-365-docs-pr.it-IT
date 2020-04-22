---
title: Collegamenti sicuri ATP per Team, safelinks, collegamenti sicuri, blocca collegamenti dannosi, Office 365 ATP, collegamenti sicuri per i team, impedire agli utenti di fare clic su collegamenti non validi, collegamenti dannosi
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: I team avranno ora accesso ai collegamenti sicuri al momento del clic. Se si utilizzano chat 1-su-1 chat, tra gruppi o in canali e tabulazioni, se si dispone di un abbonamento a Office 365 ATP, si avrà la possibilità di abilitare e utilizzare questa funzionalità di sicurezza.
ms.openlocfilehash: 88fe9756188eb16a2347d3c0cd4a98b4003ff457
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635999"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="cd184-104">Collegamenti sicuri in Teams</span><span class="sxs-lookup"><span data-stu-id="cd184-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd184-105">Questa funzionalità è in **anteprima pubblica** per i clienti del Microsoft teams Technology Adoption Program (TAP) del 28 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="cd184-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="cd184-106">Questa nota verrà rimossa dall'articolo quando i collegamenti sicuri per i team sono più diffusi.</span><span class="sxs-lookup"><span data-stu-id="cd184-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="cd184-107">Microsoft teams, un'applicazione basata sul cloud Microsoft per la gestione del lavoro, utilizza già gli allegati sicuri (per Office 365), ma ora avrà accesso ai collegamenti sicuri al momento del clic.</span><span class="sxs-lookup"><span data-stu-id="cd184-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="cd184-108">Se si utilizzano chat 1-su-1 chat, tra gruppi o in canali e tabulazioni, se si dispone di un abbonamento a Office 365 ATP, si avrà la possibilità di abilitare e utilizzare questa misura di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cd184-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="cd184-109">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cd184-109">Here's how it works:</span></span> 

1. <span data-ttu-id="cd184-110">Quando si avvia l'applicazione teams, Microsoft 365 controllerà per assicurarsi che l'utente appartenga a un'organizzazione con Office 365 ATP e che l'utente faccia parte di un criterio di collegamenti sicuri attivo con la protezione abilitata per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="cd184-110">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="cd184-111">Se il valore di cui sopra è vero, gli URL verranno convalidati al momento del clic su chat, chat di gruppo, canali e in schede per tale utente.</span><span class="sxs-lookup"><span data-stu-id="cd184-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="cd184-112">Che cosa useranno gli utenti?</span><span class="sxs-lookup"><span data-stu-id="cd184-112">What will users experience?</span></span> 

<span data-ttu-id="cd184-113">Tutti gli utenti protetti avranno questa esperienza con gli URL pericolosi:</span><span class="sxs-lookup"><span data-stu-id="cd184-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="cd184-114">Se il collegamento è stato selezionato da una conversazione di Team, da una chat di gruppo o da un canale, verrà eseguito il rendering di una pagina nel browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="cd184-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="cd184-115">Se il collegamento è stato selezionato da una scheda bloccata, la pagina verrà visualizzata nella GUI teams all'interno di tale scheda e l'opzione per l'apertura nel browser verrà disabilitata per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cd184-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="cd184-116">Questo utente verrà bloccato dal procedere al sito dell'URL.</span><span class="sxs-lookup"><span data-stu-id="cd184-116">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="cd184-117">Se l'utente che ha inviato il collegamento non è protetto da Office 365 ATP, è libero di fare clic sull'URL nel computer in uso e di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="cd184-117">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="cd184-118">Questo rende doppiamente importante per gli amministratori di essere a conoscenza di chi sono gli utenti protetti e devono essere.</span><span class="sxs-lookup"><span data-stu-id="cd184-118">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Una pagina collegamenti sicuri per i team che segnalano un collegamento dannoso e bloccano il transito alla pagina.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="cd184-120">Se si fa clic sul pulsante *Torna indietro* in questa pagina, il team verrà chiuso (o potrebbe risultare che gli utenti di una pagina vuota possano chiudere).</span><span class="sxs-lookup"><span data-stu-id="cd184-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="cd184-121">Tuttavia, facendo clic nuovamente sul collegamento si otterrà una rivalutazione della reputazione del sito in modo che questa pagina ricompaia.</span><span class="sxs-lookup"><span data-stu-id="cd184-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="cd184-122">Alcuni amministratori di Microsoft 365 consentiranno la **prosecuzione** del messaggio nella pagina di blocco.</span><span class="sxs-lookup"><span data-stu-id="cd184-122">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="cd184-123">Tuttavia, se i collegamenti sicuri misurano la reputazione di un sito e lo trovano privo, non è necessario eseguire ulteriori clic.</span><span class="sxs-lookup"><span data-stu-id="cd184-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="cd184-124">Non è consigliabile ignorare le misure di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cd184-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="cd184-125">Si prega di pesare questo nelle considerazioni prima di continuare comunque.</span><span class="sxs-lookup"><span data-stu-id="cd184-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

