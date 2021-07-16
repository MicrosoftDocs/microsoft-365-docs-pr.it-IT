---
title: Visualizzare le app
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Visualizzare le app.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420131"
---
# <a name="view-your-apps"></a><span data-ttu-id="e0699-103">Visualizzare le app</span><span class="sxs-lookup"><span data-stu-id="e0699-103">View your apps</span></span>

><span data-ttu-id="e0699-104">*[Indicazioni sulle licenze di Microsoft 365 per la sicurezza e la conformità](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="e0699-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e0699-105">La governance delle app Microsoft consente di ottenere rapidamente dati analitici approfonditi sulle app Microsoft 365 nel tenant.</span><span class="sxs-lookup"><span data-stu-id="e0699-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="e0699-106">Ad esempio, è possibile visualizzare:</span><span class="sxs-lookup"><span data-stu-id="e0699-106">For example, you can see:</span></span>

- <span data-ttu-id="e0699-107">Un elenco di app nel tenant abilitate per OAuth che usano l'API Microsoft Graph, oltre ai relativi metadati e dati di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e0699-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="e0699-108">I dettagli delle app con dati analitici e informazioni approfondite selezionando un'app nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e0699-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="e0699-109">Ottenere un elenco di tutte le app del tenant</span><span class="sxs-lookup"><span data-stu-id="e0699-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="e0699-110">Per un riepilogo delle app nel tenant, passare a **Centro conformità Microsoft 365 > Protezione e governance delle app > App**.</span><span class="sxs-lookup"><span data-stu-id="e0699-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![Pagina di riepilogo dell'app MAPG nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="e0699-112">L'account di accesso deve disporre di uno di [questi ruoli](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance delle app.</span><span class="sxs-lookup"><span data-stu-id="e0699-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="e0699-113">Verrà visualizzato un elenco di app e le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0699-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="e0699-114">Nome dell’app</span><span class="sxs-lookup"><span data-stu-id="e0699-114">App Name</span></span>
- <span data-ttu-id="e0699-115">Autore</span><span class="sxs-lookup"><span data-stu-id="e0699-115">Publisher</span></span>
- <span data-ttu-id="e0699-116">Certificazione delle app</span><span class="sxs-lookup"><span data-stu-id="e0699-116">App certification</span></span>

  <span data-ttu-id="e0699-117">Indica se l'app è compatibile con le tecnologie Microsoft, conforme alle procedure consigliate per la sicurezza delle app cloud e supportata da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0699-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="e0699-118">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="e0699-118">Last modified</span></span>

  <span data-ttu-id="e0699-119">Mostra la data in cui la governance dell'app è stata installata nel client e se tale data è più recente della data dell'ultima modifica dell'app.</span><span class="sxs-lookup"><span data-stu-id="e0699-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="e0699-120">Data di installazione</span><span class="sxs-lookup"><span data-stu-id="e0699-120">Date installed</span></span>
- <span data-ttu-id="e0699-121">Livello di privilegio</span><span class="sxs-lookup"><span data-stu-id="e0699-121">Privilege level</span></span>
- <span data-ttu-id="e0699-122">Numero di utenti</span><span class="sxs-lookup"><span data-stu-id="e0699-122">Number of users</span></span>
- <span data-ttu-id="e0699-123">Accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="e0699-123">Data access</span></span>

  <span data-ttu-id="e0699-124">Somma dei dati dell'app caricati e scaricati nel tenant nell'ultimo giorno, oltre alla modifica nel giorno precedente.</span><span class="sxs-lookup"><span data-stu-id="e0699-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="e0699-125">La governance delle app ordina l'elenco delle app in base al **nome dell'app** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e0699-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="e0699-126">Per ordinare l'elenco in base a un altro attributo dell'app, selezionare il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="e0699-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="e0699-127">È anche possibile selezionare **Cerca** per cercare un'app in base al nome.</span><span class="sxs-lookup"><span data-stu-id="e0699-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="e0699-128">Ottenere informazioni dettagliate su un'app</span><span class="sxs-lookup"><span data-stu-id="e0699-128">Getting detailed information on an app</span></span>

<span data-ttu-id="e0699-129">Per ottenere informazioni dettagliate su un'app specifica nel tenant, passare a \*\*Centro conformità Microsoft 365 > Governance delle app >Pagina app > \*nome app\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="e0699-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Riquadro dei dettagli dell'app di governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="e0699-131">Il riquadro dei dettagli dell'app fornisce informazioni aggiuntive nelle schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0699-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="e0699-132">Nome scheda</span><span class="sxs-lookup"><span data-stu-id="e0699-132">Tab name</span></span> | <span data-ttu-id="e0699-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0699-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="e0699-134">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e0699-134">Details</span></span> | <span data-ttu-id="e0699-135">È possibile visualizzare dati aggiuntivi sull'app, ad esempio la data del primo consenso e l'ID dell'app.</span><span class="sxs-lookup"><span data-stu-id="e0699-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="e0699-136">Per visualizzare le proprietà dell'app registrate in Azure AD, selezionare **Visualizza app in Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="e0699-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="e0699-137">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="e0699-137">Usage</span></span> | <span data-ttu-id="e0699-138">È possibile visualizzare i dati a cui accede l'app nel tenant, tracciare l'utilizzo dei dati e mostrare l'utilizzo da parte degli \<x> utenti principali e degli utenti con [account prioritari](/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="e0699-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="e0699-139">Utenti</span><span class="sxs-lookup"><span data-stu-id="e0699-139">Users</span></span> | <span data-ttu-id="e0699-140">È possibile visualizzare un elenco di utenti che usano l'app, se dispongono di un account prioritario e la quantità dei dati scaricati e caricati.</span><span class="sxs-lookup"><span data-stu-id="e0699-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="e0699-141">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e0699-141">Permissions</span></span> | <span data-ttu-id="e0699-142">È possibile visualizzare un riepilogo delle autorizzazioni concesse e usate dall'app, nonché l'elenco delle autorizzazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="e0699-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="e0699-143">Per altre informazioni, vedere i [riferimenti delle autorizzazioni di Microsoft Graph](/graph/permissions-reference).</span><span class="sxs-lookup"><span data-stu-id="e0699-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="e0699-144">Per un'app abilitata, è disponibile anche un controllo **Disabilita app** per disabilitare l'uso dell'app selezionata e un controllo **Abilita app** per abilitare l'uso dell'app disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e0699-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="e0699-145">Queste azioni seguenti richiedono i seguenti [ruoli di amministratore](app-governance-get-started.md#administrator-roles):</span><span class="sxs-lookup"><span data-stu-id="e0699-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="e0699-146">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="e0699-146">Compliance Administrator</span></span>
- <span data-ttu-id="e0699-147">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e0699-147">Global Administrator</span></span>
- <span data-ttu-id="e0699-148">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e0699-148">Security Administrator</span></span>
- <span data-ttu-id="e0699-149">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e0699-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="e0699-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e0699-150">Next step</span></span>

<span data-ttu-id="e0699-151">[Determinare la postura di conformità generale dell'app](app-governance-visibility-insights-compliance-posture.md).</span><span class="sxs-lookup"><span data-stu-id="e0699-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
