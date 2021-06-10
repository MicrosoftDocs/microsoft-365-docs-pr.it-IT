---
title: Proteggere le app di Office in iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Scopri come proteggere le app Office in iOS con Microsoft 365 Business Premium.
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580463"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="f9dad-103">Proteggere le app di Office in iOS</span><span class="sxs-lookup"><span data-stu-id="f9dad-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="f9dad-104">Puoi configurare criteri di accesso utente che richiedono agli utenti mobili di immettere un PIN o un'impronta digitale per l'accesso e crittografare anche i file di lavoro archiviati nei propri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f9dad-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="f9dad-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="f9dad-105">Try it!</span></span>

1. <span data-ttu-id="f9dad-106">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9dad-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="f9dad-107">In **Criteri** scegliere **Aggiungi criterio.**</span><span class="sxs-lookup"><span data-stu-id="f9dad-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="f9dad-108">Nel riquadro **Aggiungi** criterio immettere un nome **in** Nome criterio e scegliere il tipo di criterio desiderato in Tipo di **criterio.**</span><span class="sxs-lookup"><span data-stu-id="f9dad-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="f9dad-109">Attiva Gestisci il modo in cui **gli utenti Office accedere** ai file nei dispositivi mobili e quindi assicurati che le tre impostazioni seguenti siano attivate:</span><span class="sxs-lookup"><span data-stu-id="f9dad-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="f9dad-110">**Richiedi un PIN o l'impronta digitale per accedere alle app di Office**</span><span class="sxs-lookup"><span data-stu-id="f9dad-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="f9dad-111">**Proteggere i file di lavoro quando i dispositivi vengono smarriti o rubati**</span><span class="sxs-lookup"><span data-stu-id="f9dad-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="f9dad-112">**Crittografare i file di lavoro**</span><span class="sxs-lookup"><span data-stu-id="f9dad-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="f9dad-113">In **I file in queste app saranno protetti** selezionare Office che si desidera proteggere nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="f9dad-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="f9dad-114">In **Who queste impostazioni?**, tutti gli utenti sono selezionati per  impostazione predefinita, ma è possibile scegliere Cambia per selezionare i gruppi di sicurezza creati.</span><span class="sxs-lookup"><span data-stu-id="f9dad-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="f9dad-115">Per completare la creazione del criterio, scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f9dad-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="f9dad-116">Nella pagina **Aggiungi criterio** scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f9dad-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="f9dad-117">Nella home page dell'interfaccia di amministrazione verificare  che il nuovo criterio sia stato aggiunto scegliendo Criteri ed esaminando i criteri nella **pagina** Criteri.</span><span class="sxs-lookup"><span data-stu-id="f9dad-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>