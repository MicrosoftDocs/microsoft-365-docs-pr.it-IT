---
title: Proteggere le app di Office in iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Informazioni su come proteggere le app di Office in iOS con Microsoft 365 Business Premium.
ms.openlocfilehash: 197041a4eb9ada65f4b6046d93f2a856cbdfb40d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422112"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="15d91-103">Proteggere le app di Office in iOS</span><span class="sxs-lookup"><span data-stu-id="15d91-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="15d91-104">Puoi configurare un criterio di accesso utente che richiede agli utenti mobili di immettere un PIN o un'impronta digitale per l'accesso e crittografa anche i file di lavoro archiviati nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="15d91-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="15d91-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="15d91-105">Try it!</span></span>

1. <span data-ttu-id="15d91-106">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15d91-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="15d91-107">In **Criteri** scegliere **Aggiungi criterio.**</span><span class="sxs-lookup"><span data-stu-id="15d91-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="15d91-108">Nel riquadro **Aggiungi criterio** immettere un nome in **Nome** criterio e scegliere il tipo di criterio desiderato in Tipo **di criterio.**</span><span class="sxs-lookup"><span data-stu-id="15d91-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="15d91-109">Attivare Gestisci **il modo in cui gli utenti accedono** ai file di Office nei dispositivi mobili e quindi verificare che le tre impostazioni seguenti siano attivate:</span><span class="sxs-lookup"><span data-stu-id="15d91-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="15d91-110">**Richiedi un PIN o l'impronta digitale per accedere alle app di Office**</span><span class="sxs-lookup"><span data-stu-id="15d91-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="15d91-111">**Proteggere i file di lavoro quando i dispositivi vengono smarriti o rubati**</span><span class="sxs-lookup"><span data-stu-id="15d91-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="15d91-112">**Crittografare i file di lavoro**</span><span class="sxs-lookup"><span data-stu-id="15d91-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="15d91-113">In **File in queste app verranno protetti** selezionare le app di Office che si desidera proteggere nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="15d91-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="15d91-114">In **Chi otterrà queste impostazioni,** tutti gli utenti sono  selezionati per impostazione predefinita, ma è possibile scegliere Cambia per selezionare i gruppi di sicurezza creati.</span><span class="sxs-lookup"><span data-stu-id="15d91-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="15d91-115">Per completare la creazione del criterio, scegliere **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="15d91-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="15d91-116">Nella pagina **Aggiungi criterio** scegliere **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="15d91-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="15d91-117">Nella home page dell'interfaccia di amministrazione verificare  che il nuovo criterio sia stato aggiunto scegliendo Criteri ed esaminando il criterio nella **pagina** Criteri.</span><span class="sxs-lookup"><span data-stu-id="15d91-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>