---
title: Office 365 ATP Safe Links for teams, safelinks, safe Links, Block maligne Links, Office 365 ATP, teams Safe Links, impedire agli utenti di fare clic su collegamenti non validi, collegamenti dannosi
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
ms.openlocfilehash: 864b211a1f007a0f6bde83da12b61362b53bf041
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030142"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="c0d0e-104">Collegamenti sicuri di Office 365 in teams</span><span class="sxs-lookup"><span data-stu-id="c0d0e-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0d0e-105">Questa funzionalità è in **anteprima pubblica** per i clienti del Microsoft teams Technology Adoption Program (TAP) del 28 febbraio 2020.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="c0d0e-106">Questa nota verrà rimossa dall'articolo quando i collegamenti sicuri per i team sono più diffusi.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="c0d0e-107">Microsoft teams, un'applicazione basata sul cloud di Office 365 per la gestione del lavoro, utilizza già gli allegati sicuri (per Office 365), ma ora avrà accesso ai collegamenti sicuri al momento del clic.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="c0d0e-108">Se si utilizzano chat 1-su-1 chat, tra gruppi o in canali e tabulazioni, se si dispone di un abbonamento a Office 365 ATP, si avrà la possibilità di abilitare e utilizzare questa misura di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="c0d0e-109">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c0d0e-109">Here's how it works:</span></span> 

1. <span data-ttu-id="c0d0e-110">Quando si avvia l'applicazione teams, Office 365 verifica che l'utente appartenga a un'organizzazione con Office 365 ATP e che l'utente faccia parte di un criterio di collegamenti sicuri attivo con la relativa protezione abilitata per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="c0d0e-111">Se il valore di cui sopra è vero, gli URL verranno convalidati al momento del clic su chat, chat di gruppo, canali e in schede per tale utente.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="c0d0e-112">Che cosa useranno gli utenti?</span><span class="sxs-lookup"><span data-stu-id="c0d0e-112">What will users experience?</span></span> 

<span data-ttu-id="c0d0e-113">Tutti gli utenti protetti avranno questa esperienza con gli URL pericolosi:</span><span class="sxs-lookup"><span data-stu-id="c0d0e-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="c0d0e-114">Se il collegamento è stato selezionato da una conversazione di Team, da una chat di gruppo o da un canale, verrà eseguito il rendering di una pagina nel browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="c0d0e-115">Se il collegamento è stato selezionato da una scheda bloccata, la pagina verrà visualizzata nella GUI teams all'interno di tale scheda e l'opzione per l'apertura nel browser verrà disabilitata per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="c0d0e-116">Questo utente verrà bloccato dal procedere al sito dell'URL.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-116">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="c0d0e-117">Se l'utente che ha inviato il collegamento non è protetto da Office 365 ATP, è libero di fare clic sull'URL nel computer in uso e di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-117">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="c0d0e-118">In questo modo è doppiamente importante che gli amministratori di Office 365 siano a conoscenza di chi sono e dovrebbero essere gli utenti protetti.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-118">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![Una pagina collegamenti sicuri per i team che segnalano un collegamento dannoso e bloccano il transito alla pagina.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="c0d0e-120">Se si fa clic sul pulsante *Torna indietro* in questa pagina, il team verrà chiuso (o potrebbe risultare che gli utenti di una pagina vuota possano chiudere).</span><span class="sxs-lookup"><span data-stu-id="c0d0e-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="c0d0e-121">Tuttavia, facendo clic nuovamente sul collegamento si otterrà una rivalutazione della reputazione del sito in modo che questa pagina ricompaia.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="c0d0e-122">Alcuni amministratori di Office 365 consentiranno la **prosecuzione** del messaggio nella pagina di blocco.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-122">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="c0d0e-123">Tuttavia, se i collegamenti sicuri misurano la reputazione di un sito e lo trovano privo, non è necessario eseguire ulteriori clic.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="c0d0e-124">Non è consigliabile ignorare le misure di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="c0d0e-125">Si prega di pesare questo nelle considerazioni prima di continuare comunque.</span><span class="sxs-lookup"><span data-stu-id="c0d0e-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

