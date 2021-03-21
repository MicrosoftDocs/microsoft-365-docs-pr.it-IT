---
title: Esaminare gli utenti nel Centro sicurezza Microsoft 365
description: analizzare gli utenti nel Centro sicurezza Microsoft 365
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, segnalare, identità, dati, dispositivi, app
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 32c496a212e038d649fdc9880c8ac829ee4a5337
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927236"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="d1be4-104">Esaminare gli utenti nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1be4-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="d1be4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d1be4-105">**Applies to:**</span></span>

- <span data-ttu-id="d1be4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1be4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d1be4-107">Nell'ambito dell'indagine, è possibile che un utente sia stato compromesso.</span><span class="sxs-lookup"><span data-stu-id="d1be4-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="d1be4-108">La pagina utente del Centro sicurezza Microsoft 365 combina le informazioni di Microsoft Defender for Endpoint, Microsoft Defender for Identity e Microsoft Cloud App Security (a seconda delle licenze di cui si dispone).</span><span class="sxs-lookup"><span data-stu-id="d1be4-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="d1be4-109">Questa pagina è il punto di partenza ideale per l'analisi degli utenti e dei potenziali incidenti.</span><span class="sxs-lookup"><span data-stu-id="d1be4-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="d1be4-110">![Pagina utente](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="d1be4-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="d1be4-111">Questa pagina mostra informazioni specifiche del rischio per la sicurezza di un utente.</span><span class="sxs-lookup"><span data-stu-id="d1be4-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="d1be4-112">Questo include un punteggio che consente di valutare i rischi, gli eventi recenti e gli avvisi che hanno contribuito al rischio complessivo dell'utente e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="d1be4-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="d1be4-113">È possibile accedere a questa pagina da più aree del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1be4-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="d1be4-114">È possibile accedere a questa pagina da un evento imprevisto specifico nella **scheda** Utenti. Alcuni avvisi potrebbero includere gli utenti come risorsa interessata specifica.</span><span class="sxs-lookup"><span data-stu-id="d1be4-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="d1be4-115">È inoltre possibile cercare utenti.</span><span class="sxs-lookup"><span data-stu-id="d1be4-115">You can also search for users.</span></span>  

<span data-ttu-id="d1be4-116">Altre informazioni su come analizzare gli utenti e i potenziali rischi [in questa esercitazione su Cloud App Security.](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)</span><span class="sxs-lookup"><span data-stu-id="d1be4-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1be4-117">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d1be4-117">Related topics</span></span>

- [<span data-ttu-id="d1be4-118">Panoramica sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="d1be4-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d1be4-119">Assegnare priorità agli incidenti</span><span class="sxs-lookup"><span data-stu-id="d1be4-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="d1be4-120">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="d1be4-120">Manage incidents</span></span>](manage-incidents.md)