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
ms.openlocfilehash: 2fd9b958cdbdaf22346f8171c789f2ca9a8336d1
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957608"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="11dfb-104">Analizzare gli utenti nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11dfb-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="11dfb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="11dfb-105">**Applies to:**</span></span>

- <span data-ttu-id="11dfb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11dfb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="11dfb-107">Parte dell'analisi degli eventi imprevisti può includere account utente.</span><span class="sxs-lookup"><span data-stu-id="11dfb-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="11dfb-108">Iniziare con la **scheda Utenti** per un evento imprevisto da **Eventi imprevisti & avvisi >** evento *>* **utenti**.</span><span class="sxs-lookup"><span data-stu-id="11dfb-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Esempio di pagina Utenti per un evento imprevisto":::

<span data-ttu-id="11dfb-110">Per ottenere un breve riepilogo di un account utente per l'evento imprevisto, selezionare il segno di spunta accanto al nome dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="11dfb-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="11dfb-111">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="11dfb-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Esempio del riquadro di riepilogo dell'account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::

> [!NOTE]
> <span data-ttu-id="11dfb-113">La pagina Utente mostra l'organizzazione di Azure Active Directory (AD) e i gruppi, consentendoti di comprendere i gruppi e le autorizzazioni associati a un utente.</span><span class="sxs-lookup"><span data-stu-id="11dfb-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="11dfb-114">In questa pagina a comparsa è possibile esaminare le informazioni sulle minacce degli utenti, inclusi eventuali eventi imprevisti correnti, avvisi attivi e livello di rischio, nonché l'esposizione degli utenti, gli account, i dispositivi e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="11dfb-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="11dfb-115">Inoltre, è possibile intervenire direttamente nel Centro sicurezza Microsoft 365 per risolvere un utente compromesso, confermando che l'utente è compromesso o richiedendo loro di accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="11dfb-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="11dfb-116">Da qui puoi selezionare **Vai alla pagina utente** per visualizzare i dettagli di un account utente.</span><span class="sxs-lookup"><span data-stu-id="11dfb-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="11dfb-117">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="11dfb-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Esempio di pagina dell'account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="11dfb-119">Puoi anche visualizzare questa pagina selezionando il nome dell'account utente nell'elenco nella **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="11dfb-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="11dfb-120">La pagina utente del Centro sicurezza Microsoft 365 combina le informazioni di Microsoft Defender for Endpoint, Microsoft Defender for Identity e Microsoft Cloud App Security (a seconda delle licenze di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="11dfb-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="11dfb-121">In questa pagina vengono visualizzate informazioni specifiche del rischio per la sicurezza di un account utente.</span><span class="sxs-lookup"><span data-stu-id="11dfb-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="11dfb-122">Include un punteggio che consente di valutare i rischi e gli eventi e gli avvisi recenti che hanno contribuito al rischio complessivo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="11dfb-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="11dfb-123">Da questa pagina puoi eseguire queste azioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="11dfb-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="11dfb-124">Contrassegnare l'account utente come compromesso</span><span class="sxs-lookup"><span data-stu-id="11dfb-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="11dfb-125">Richiedere all'utente di eseguire di nuovo l'accesso</span><span class="sxs-lookup"><span data-stu-id="11dfb-125">Require the user to sign in again</span></span>
- <span data-ttu-id="11dfb-126">Sospendere l'account utente</span><span class="sxs-lookup"><span data-stu-id="11dfb-126">Suspend the user account</span></span>
- <span data-ttu-id="11dfb-127">Vedere le impostazioni dell'account utente di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="11dfb-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="11dfb-128">Visualizzare i file di proprietà dell'account utente</span><span class="sxs-lookup"><span data-stu-id="11dfb-128">View the files owned by the user account</span></span>
- <span data-ttu-id="11dfb-129">Visualizzare i file condivisi con questo utente.</span><span class="sxs-lookup"><span data-stu-id="11dfb-129">View files shared with this user.</span></span> 

<span data-ttu-id="11dfb-130">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="11dfb-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Esempio di azioni su un account utente per un evento imprevisto nel Centro sicurezza Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="11dfb-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="11dfb-132">Related topics</span></span>

- [<span data-ttu-id="11dfb-133">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="11dfb-133">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="11dfb-134">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="11dfb-134">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="11dfb-135">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="11dfb-135">Manage incidents</span></span>](manage-incidents.md)