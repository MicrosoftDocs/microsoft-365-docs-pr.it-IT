---
title: Analizzare gli utenti nel Centro sicurezza Microsoft 365
description: Analizzare gli utenti nel Centro sicurezza Microsoft 365
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, segnalare, identità, dati, dispositivi, app, eventi imprevisti, analizzare, risposta
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939731"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="9b763-104">Analizzare gli utenti nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9b763-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9b763-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9b763-105">**Applies to:**</span></span>

- <span data-ttu-id="9b763-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b763-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9b763-107">Parte dell'analisi degli eventi imprevisti può includere account utente.</span><span class="sxs-lookup"><span data-stu-id="9b763-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="9b763-108">Iniziare con la **scheda Utenti** per un evento imprevisto da **Eventi imprevisti & avvisi >** evento *>* **utenti**.</span><span class="sxs-lookup"><span data-stu-id="9b763-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Esempio di pagina Utenti per un evento imprevisto":::

<span data-ttu-id="9b763-110">Per ottenere un breve riepilogo di un account utente per l'evento imprevisto, selezionare il segno di spunta accanto al nome dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="9b763-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="9b763-111">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="9b763-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Esempio del riquadro di riepilogo dell'account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="9b763-113">Da qui puoi selezionare **Vai alla pagina utente** per visualizzare i dettagli di un account utente.</span><span class="sxs-lookup"><span data-stu-id="9b763-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="9b763-114">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="9b763-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Esempio di pagina dell'account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="9b763-116">Puoi anche visualizzare questa pagina selezionando il nome dell'account utente nell'elenco nella **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="9b763-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="9b763-117">La pagina utente del Centro sicurezza Microsoft 365 combina le informazioni di Microsoft Defender for Endpoint, Microsoft Defender for Identity e Microsoft Cloud App Security (a seconda delle licenze di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="9b763-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="9b763-118">In questa pagina vengono visualizzate informazioni specifiche del rischio per la sicurezza di un account utente.</span><span class="sxs-lookup"><span data-stu-id="9b763-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="9b763-119">Include un punteggio che consente di valutare i rischi e gli eventi e gli avvisi recenti che hanno contribuito al rischio complessivo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9b763-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="9b763-120">Da questa pagina puoi eseguire queste azioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="9b763-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="9b763-121">Contrassegnare l'account utente come compromesso</span><span class="sxs-lookup"><span data-stu-id="9b763-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="9b763-122">Richiedere all'utente di eseguire di nuovo l'accesso</span><span class="sxs-lookup"><span data-stu-id="9b763-122">Require the user to sign in again</span></span>
- <span data-ttu-id="9b763-123">Sospendere l'account utente</span><span class="sxs-lookup"><span data-stu-id="9b763-123">Suspend the user account</span></span>
- <span data-ttu-id="9b763-124">Vedere le impostazioni dell'account utente di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="9b763-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="9b763-125">Visualizzare i file di proprietà dell'account utente</span><span class="sxs-lookup"><span data-stu-id="9b763-125">View the files owned by the user account</span></span>
- <span data-ttu-id="9b763-126">Visualizzare i file condivisi con questo utente.</span><span class="sxs-lookup"><span data-stu-id="9b763-126">View files shared with this user.</span></span> 

<span data-ttu-id="9b763-127">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="9b763-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Esempio di azioni su un account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="9b763-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9b763-129">Related topics</span></span>

- [<span data-ttu-id="9b763-130">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="9b763-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9b763-131">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="9b763-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="9b763-132">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="9b763-132">Manage incidents</span></span>](manage-incidents.md)