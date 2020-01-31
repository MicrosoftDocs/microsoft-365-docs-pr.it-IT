---
title: Utenti di gestione dei rischi Insider (anteprima)
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
ms.openlocfilehash: f79fcebf220f1aee98ba97c537ff80b65b6e3881
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582855"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="b96dd-104">Utenti di gestione dei rischi Insider (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b96dd-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="b96dd-105">Gli utenti di gestione dei rischi Insider sono impiegati nell'organizzazione che sono inclusi in uno o più criteri di gestione dei rischi Insider.</span><span class="sxs-lookup"><span data-stu-id="b96dd-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="b96dd-106">Utilizzare il **Dashboard utenti** per esaminare rapidamente le informazioni sui rischi per i dipendenti e per aggiungere un dipendente a un criterio di gestione dei rischi Insider esistente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="b96dd-107">Ogni utente incluso in un criterio di gestione dei rischi Insider contiene le seguenti informazioni visualizzate nel **dashboard degli utenti**:</span><span class="sxs-lookup"><span data-stu-id="b96dd-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="b96dd-108">**Users: il**nome utente di un utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="b96dd-109">**Livello di rischio**:</span><span class="sxs-lookup"><span data-stu-id="b96dd-109">**Risk level**:</span></span> 
- <span data-ttu-id="b96dd-110">**Avvisi attivi**: il numero di avvisi attivi per tutti i criteri.</span><span class="sxs-lookup"><span data-stu-id="b96dd-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="b96dd-111">**Violazioni confermate**: il numero di casi risolti come *violazioni dei criteri confermate* per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="b96dd-112">**Caso**: il caso attivo corrente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-112">**Case**: The current active case for the user.</span></span>

![Dashboard degli utenti di gestione dei rischi Insider](media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="b96dd-114">Visualizzare i dettagli dell'utente</span><span class="sxs-lookup"><span data-stu-id="b96dd-114">View user details</span></span>

<span data-ttu-id="b96dd-115">Per visualizzare ulteriori dettagli sull'attività di rischio per un utente, aprire il riquadro dei dettagli dell'utente facendo doppio clic su un utente nel **Dashboard utenti**.</span><span class="sxs-lookup"><span data-stu-id="b96dd-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="b96dd-116">Nel riquadro dei dettagli, è possibile visualizzare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b96dd-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="b96dd-117">Scheda **profilo utente**</span><span class="sxs-lookup"><span data-stu-id="b96dd-117">**User profile** tab</span></span>
    - <span data-ttu-id="b96dd-118">**Nome e titolo**: il nome e il titolo della posizione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="b96dd-119">**Messaggio**di posta elettronica dell'utente: l'indirizzo di posta elettronica per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="b96dd-120">**Alias**: l'alias di rete per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="b96dd-121">**Organizzazione o reparto**: organizzazione o reparto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="b96dd-122">Scheda **attività utente**</span><span class="sxs-lookup"><span data-stu-id="b96dd-122">**User activity** tab</span></span>
    - <span data-ttu-id="b96dd-123">**Cronologia delle attività degli utenti recenti**: elenca sia gli eventi di attivazione dei criteri sia gli indicatori di rischio per le attività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="b96dd-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="b96dd-124">Un evento di attivazione può essere l'accettazione di una data di dimissioni o l'ultima data di lavoro pianificata per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="b96dd-125">Gli indicatori di rischio sono attività determinate per avere un elemento di rischio e che corrispondono a criteri in base ai quali l'utente è incluso.</span><span class="sxs-lookup"><span data-stu-id="b96dd-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="b96dd-126">Gli eventi e le attività di rischio sono elencati con l'elemento più recente elencato per primo.</span><span class="sxs-lookup"><span data-stu-id="b96dd-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="b96dd-127">Aggiungere un utente a un criterio</span><span class="sxs-lookup"><span data-stu-id="b96dd-127">Add a user to a policy</span></span>

<span data-ttu-id="b96dd-128">Per aggiungere un utente a un criterio di gestione dei rischi Insider, è possibile utilizzare la procedura guidata nuovo criterio o la scheda **utenti** nella soluzione di **gestione dei rischi Insider** nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b96dd-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="b96dd-129">Completare la procedura seguente per aggiungere un utente a un criterio di rischio Insider esistente:</span><span class="sxs-lookup"><span data-stu-id="b96dd-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="b96dd-130">Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **utenti** .</span><span class="sxs-lookup"><span data-stu-id="b96dd-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="b96dd-131">Selezionare **Aggiungi un utente a un criterio** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="b96dd-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="b96dd-132">Nella finestra di dialogo **Aggiungi nuovo utente** , iniziare a digitare un nome utente nel campo **utente** .</span><span class="sxs-lookup"><span data-stu-id="b96dd-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="b96dd-133">Selezionare l'utente che si desidera aggiungere a un criterio.</span><span class="sxs-lookup"><span data-stu-id="b96dd-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="b96dd-134">Selezionare la freccia a discesa del campo **criterio** per visualizzare i criteri di gestione dei rischi Insider configurati.</span><span class="sxs-lookup"><span data-stu-id="b96dd-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="b96dd-135">Selezionare il criterio a cui aggiungere l'utente.</span><span class="sxs-lookup"><span data-stu-id="b96dd-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="b96dd-136">Utilizzare il controllo del dispositivo di scorrimento della **finestra di monitoraggio** per definire il...... L'intervallo per la finestra di monitoraggio è compreso tra 5 e 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b96dd-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="b96dd-137">Selezionare **Aggiungi** e quindi **conferma** per aggiungere l'utente al criterio.</span><span class="sxs-lookup"><span data-stu-id="b96dd-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
