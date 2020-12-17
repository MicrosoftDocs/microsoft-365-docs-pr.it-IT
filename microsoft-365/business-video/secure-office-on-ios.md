---
title: Proteggere le app di Office su iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Informazioni su come proteggere le app di Office su iOS con Microsoft 365 Business Premium.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702061"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="38429-103">Proteggere le app di Office su iOS</span><span class="sxs-lookup"><span data-stu-id="38429-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="38429-104">È possibile configurare un criterio di accesso utente che richiede agli utenti di dispositivi mobili di immettere un PIN o un'impronta digitale per accedere e crittografare i file di lavoro archiviati nei propri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="38429-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="38429-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="38429-105">Try it!</span></span>

1. <span data-ttu-id="38429-106">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38429-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="38429-107">In **criteri** scegliere **Aggiungi criterio**.</span><span class="sxs-lookup"><span data-stu-id="38429-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="38429-108">Nel riquadro **Aggiungi criterio** , immettere un nome in **Nome criterio** e scegliere il tipo di criteri desiderato in **tipo** di criterio.</span><span class="sxs-lookup"><span data-stu-id="38429-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="38429-109">Attiva **gestire la modalità di accesso degli utenti ai file di Office nei dispositivi mobili** e quindi verificare che siano attivate le tre impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38429-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="38429-110">**Richiedi un PIN o l'impronta digitale per accedere alle app di Office**</span><span class="sxs-lookup"><span data-stu-id="38429-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="38429-111">**Proteggere i file di lavoro quando i dispositivi vengono persi o rubati**</span><span class="sxs-lookup"><span data-stu-id="38429-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="38429-112">**Crittografare i file di lavoro**</span><span class="sxs-lookup"><span data-stu-id="38429-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="38429-113">In **file in queste applicazioni verrà protetto**, selezionare le app di Office che si desidera proteggere nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="38429-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="38429-114">In **chi otterrà queste impostazioni?**, tutti gli utenti sono selezionati per impostazione predefinita, ma è possibile scegliere **Cambia** per selezionare i gruppi di sicurezza creati.</span><span class="sxs-lookup"><span data-stu-id="38429-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="38429-115">Per completare la creazione del criterio, scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="38429-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="38429-116">Nella pagina **Aggiungi criterio** scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="38429-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="38429-117">Nella Home page dell'interfaccia di amministrazione, verificare che il nuovo criterio sia stato aggiunto scegliendo **criteri** e rivedendo i criteri nella pagina **criteri** .</span><span class="sxs-lookup"><span data-stu-id="38429-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>