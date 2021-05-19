---
title: Analizzare gli utenti in Microsoft 365 Defender
description: Analizzare gli utenti per individuare un incidente nel centro Microsoft 365 sicurezza.
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
ms.openlocfilehash: 7084b9370a0dd83265b37ff1d152e2164fe32813
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539132"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="b64b5-104">Analizzare gli utenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b64b5-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b64b5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b64b5-105">**Applies to:**</span></span>

- <span data-ttu-id="b64b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b64b5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b64b5-107">Parte dell'indagine degli eventi imprevisti può includere account utente.</span><span class="sxs-lookup"><span data-stu-id="b64b5-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="b64b5-108">Iniziare con la **scheda Utenti** per un evento imprevisto da **Eventi imprevisti & avvisi >** evento *>* **utenti**.</span><span class="sxs-lookup"><span data-stu-id="b64b5-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Esempio di pagina Utenti per un evento imprevisto":::

<span data-ttu-id="b64b5-110">Per ottenere un breve riepilogo di un account utente per l'evento imprevisto, selezionare il segno di spunta accanto al nome dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="b64b5-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="b64b5-111">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="b64b5-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Esempio del riquadro di riepilogo dell'account utente per un evento imprevisto nel centro Microsoft 365 sicurezza":::

> [!NOTE]
> <span data-ttu-id="b64b5-113">La pagina Utente mostra Azure Active Directory(AD) e i gruppi, consentendoti di comprendere i gruppi e le autorizzazioni associati a un utente.</span><span class="sxs-lookup"><span data-stu-id="b64b5-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="b64b5-114">In questa pagina a comparsa è possibile esaminare le informazioni sulle minacce degli utenti, inclusi eventuali eventi imprevisti correnti, avvisi attivi e livello di rischio, nonché l'esposizione degli utenti, gli account, i dispositivi e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="b64b5-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="b64b5-115">Inoltre, è possibile eseguire un'azione direttamente nel centro sicurezza Microsoft 365 per risolvere un utente compromesso, confermando che l'utente è compromesso o richiedendo loro di accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b64b5-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="b64b5-116">Da qui puoi selezionare **Vai alla pagina utente** per visualizzare i dettagli di un account utente.</span><span class="sxs-lookup"><span data-stu-id="b64b5-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="b64b5-117">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="b64b5-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Esempio di pagina dell'account utente per un evento imprevisto nel centro sicurezza Microsoft 365 sicurezza":::

<span data-ttu-id="b64b5-119">Puoi anche visualizzare questa pagina selezionando il nome dell'account utente nell'elenco nella **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="b64b5-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="b64b5-120">La Microsoft 365 utente del Centro sicurezza e sicurezza combina le informazioni di Microsoft Defender per Endpoint, Microsoft Defender per l'identità e Microsoft Cloud App Security (a seconda delle licenze di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="b64b5-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="b64b5-121">In questa pagina vengono visualizzate informazioni specifiche del rischio per la sicurezza di un account utente.</span><span class="sxs-lookup"><span data-stu-id="b64b5-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="b64b5-122">Include un punteggio che consente di valutare i rischi e gli eventi e gli avvisi recenti che hanno contribuito al rischio complessivo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b64b5-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="b64b5-123">Da questa pagina puoi eseguire queste azioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="b64b5-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="b64b5-124">Contrassegnare l'account utente come compromesso</span><span class="sxs-lookup"><span data-stu-id="b64b5-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="b64b5-125">Richiedere all'utente di eseguire di nuovo l'accesso</span><span class="sxs-lookup"><span data-stu-id="b64b5-125">Require the user to sign in again</span></span>
- <span data-ttu-id="b64b5-126">Sospendere l'account utente</span><span class="sxs-lookup"><span data-stu-id="b64b5-126">Suspend the user account</span></span>
- <span data-ttu-id="b64b5-127">Vedere le impostazioni Azure Active Directory (Azure AD) dell'account utente</span><span class="sxs-lookup"><span data-stu-id="b64b5-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="b64b5-128">Visualizzare i file di proprietà dell'account utente</span><span class="sxs-lookup"><span data-stu-id="b64b5-128">View the files owned by the user account</span></span>
- <span data-ttu-id="b64b5-129">Visualizzare i file condivisi con questo utente.</span><span class="sxs-lookup"><span data-stu-id="b64b5-129">View files shared with this user.</span></span> 

<span data-ttu-id="b64b5-130">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="b64b5-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Esempio di azioni su un account utente per un evento imprevisto nel centro sicurezza Microsoft 365 sicurezza":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="b64b5-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b64b5-132">Next steps</span></span>

<span data-ttu-id="b64b5-133">In base alle esigenze per gli eventi imprevisti in-process, continuare [l'indagine.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="b64b5-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b64b5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b64b5-134">See also</span></span>

- [<span data-ttu-id="b64b5-135">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="b64b5-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b64b5-136">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="b64b5-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="b64b5-137">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="b64b5-137">Manage incidents</span></span>](manage-incidents.md)