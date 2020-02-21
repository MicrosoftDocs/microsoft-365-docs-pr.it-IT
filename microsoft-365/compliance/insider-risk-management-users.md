---
title: Utenti di gestione dei rischi Insider
description: Informazioni sugli utenti di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 322cd0aa8b72ea2c81792b36614e87d97db87d7c
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179107"
---
# <a name="insider-risk-management-users"></a><span data-ttu-id="cd81f-104">Utenti di gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="cd81f-104">Insider risk management users</span></span>

<span data-ttu-id="cd81f-105">Gli utenti di gestione dei rischi Insider sono impiegati nell'organizzazione che sono inclusi in uno o più criteri di gestione dei rischi Insider.</span><span class="sxs-lookup"><span data-stu-id="cd81f-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="cd81f-106">Utilizzare il **Dashboard utenti** per esaminare rapidamente le informazioni sui rischi per i dipendenti e per aggiungere un dipendente a un criterio di gestione dei rischi Insider esistente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="cd81f-107">Ogni utente incluso in un criterio di gestione dei rischi Insider contiene le seguenti informazioni visualizzate nel **dashboard degli utenti**:</span><span class="sxs-lookup"><span data-stu-id="cd81f-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="cd81f-108">**Utenti**: il nome utente di un utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-108">**Users**: The username for a user.</span></span>
- <span data-ttu-id="cd81f-109">**Livello di rischio**: il livello di rischio calcolato corrente dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-109">**Risk level**: The current calculated risk level of the user.</span></span> <span data-ttu-id="cd81f-110">Questo punteggio viene calcolato ogni 24 ore e utilizza i punteggi dei rischi di avviso provenienti da tutti gli avvisi attivi associati all'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-110">This score is calculated every 24 hours and uses the alert risk scores from all active alerts associated to the user.</span></span>
- <span data-ttu-id="cd81f-111">**Avvisi attivi**: il numero di avvisi attivi per tutti i criteri.</span><span class="sxs-lookup"><span data-stu-id="cd81f-111">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="cd81f-112">**Violazioni confermate**: il numero di casi risolti come *violazioni dei criteri confermate* per l'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-112">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="cd81f-113">**Caso**: il caso attivo corrente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-113">**Case**: The current active case for the user.</span></span>

![Dashboard degli utenti di gestione dei rischi Insider](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="cd81f-115">Visualizzare i dettagli dell'utente</span><span class="sxs-lookup"><span data-stu-id="cd81f-115">View user details</span></span>

<span data-ttu-id="cd81f-116">Per visualizzare ulteriori dettagli sull'attività di rischio per un utente, aprire il riquadro dei dettagli dell'utente facendo doppio clic su un utente nel **Dashboard utenti**.</span><span class="sxs-lookup"><span data-stu-id="cd81f-116">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="cd81f-117">Nel riquadro dei dettagli, è possibile visualizzare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd81f-117">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="cd81f-118">Scheda **profilo utente**</span><span class="sxs-lookup"><span data-stu-id="cd81f-118">**User profile** tab</span></span>
    - <span data-ttu-id="cd81f-119">**Nome e titolo**: il nome e il titolo della posizione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-119">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="cd81f-120">**Messaggio**di posta elettronica dell'utente: l'indirizzo di posta elettronica per l'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-120">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="cd81f-121">**Alias**: l'alias di rete per l'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-121">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="cd81f-122">**Organizzazione o reparto**: organizzazione o reparto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-122">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="cd81f-123">Scheda **attività utente**</span><span class="sxs-lookup"><span data-stu-id="cd81f-123">**User activity** tab</span></span>
    - <span data-ttu-id="cd81f-124">**Cronologia delle attività degli utenti recenti**: elenca sia gli eventi di attivazione dei criteri sia gli indicatori di rischio per le attività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="cd81f-124">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="cd81f-125">Un evento di attivazione può essere l'accettazione di una data di dimissioni o l'ultima data di lavoro pianificata per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-125">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="cd81f-126">Gli indicatori di rischio sono attività determinate per avere un elemento di rischio e che corrispondono a criteri in base ai quali l'utente è incluso.</span><span class="sxs-lookup"><span data-stu-id="cd81f-126">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="cd81f-127">Gli eventi e le attività di rischio sono elencati con l'elemento più recente elencato per primo.</span><span class="sxs-lookup"><span data-stu-id="cd81f-127">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="cd81f-128">Aggiungere un utente a un criterio</span><span class="sxs-lookup"><span data-stu-id="cd81f-128">Add a user to a policy</span></span>

<span data-ttu-id="cd81f-129">Per aggiungere un utente a un criterio di gestione dei rischi Insider, è possibile utilizzare la procedura guidata nuovo criterio o la scheda **utenti** nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd81f-129">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="cd81f-130">Completare la procedura seguente per aggiungere un utente a un criterio di rischio Insider esistente:</span><span class="sxs-lookup"><span data-stu-id="cd81f-130">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="cd81f-131">Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **utenti** .</span><span class="sxs-lookup"><span data-stu-id="cd81f-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="cd81f-132">Selezionare **Aggiungi un utente a un criterio** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="cd81f-132">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="cd81f-133">Nella finestra di dialogo **Aggiungi nuovo utente** , iniziare a digitare un nome utente nel campo **utente** .</span><span class="sxs-lookup"><span data-stu-id="cd81f-133">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="cd81f-134">Selezionare l'utente che si desidera aggiungere a un criterio.</span><span class="sxs-lookup"><span data-stu-id="cd81f-134">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="cd81f-135">Selezionare la freccia a discesa del campo **criterio** per visualizzare i criteri di gestione dei rischi Insider configurati.</span><span class="sxs-lookup"><span data-stu-id="cd81f-135">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="cd81f-136">Selezionare il criterio a cui aggiungere l'utente.</span><span class="sxs-lookup"><span data-stu-id="cd81f-136">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="cd81f-137">Utilizzare il controllo del dispositivo di scorrimento della **finestra di attivazione** per definire la durata del criterio attivo per l'utente e viene attivato quando l'utente esegue la prima attività corrispondente al criterio.</span><span class="sxs-lookup"><span data-stu-id="cd81f-137">Use the **Activation window** slider control to define how long the policy is active for this user and is triggered when the user performs the first activity matching the policy.</span></span> <span data-ttu-id="cd81f-138">L'intervallo per la finestra di monitoraggio è compreso tra 5 e 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="cd81f-138">The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="cd81f-139">Selezionare **Aggiungi** e quindi **conferma** per aggiungere l'utente al criterio.</span><span class="sxs-lookup"><span data-stu-id="cd81f-139">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
