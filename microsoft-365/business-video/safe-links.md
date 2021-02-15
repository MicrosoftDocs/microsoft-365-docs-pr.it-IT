---
title: Gestire collegamenti sicuri
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come gestire collegamenti sicuri per proteggere l'azienda da siti dannosi.
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928019"
---
# <a name="manage-safe-links"></a><span data-ttu-id="477dc-103">Gestire collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="477dc-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="477dc-104">Microsoft Defender per Office 365, in precedenza denominato Microsoft 365 ATP o Advanced Threat Protection, consente di proteggere l'azienda da siti dannosi quando gli utenti selezionano collegamenti nelle app di Office.</span><span class="sxs-lookup"><span data-stu-id="477dc-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="477dc-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="477dc-105">Try it!</span></span>

1. <span data-ttu-id="477dc-106">Accedere [all'interfaccia di amministrazione](https://admin.microsoft.com)e selezionare **Installazione.**</span><span class="sxs-lookup"><span data-stu-id="477dc-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="477dc-107">Scorrere verso il basso **fino ad aumentare la protezione dalle minacce avanzate.**</span><span class="sxs-lookup"><span data-stu-id="477dc-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="477dc-108">Selezionare **Visualizza,** **Gestisci** e quindi **Collegamenti sicuri ATP.**</span><span class="sxs-lookup"><span data-stu-id="477dc-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="477dc-109">In **Criteri applicabili all'intera organizzazione** scegliere il criterio predefinito e quindi selezionare l'icona Modifica.  </span><span class="sxs-lookup"><span data-stu-id="477dc-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="477dc-110">Immettere un URL che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="477dc-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="477dc-111">Selezionare **Usa collegamenti sicuri nelle app di Office, Office per iOS e Android;** selezionare **Non tenere traccia quando gli utenti fanno clic su collegamenti sicuri;** e selezionare **Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale.**</span><span class="sxs-lookup"><span data-stu-id="477dc-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="477dc-112">Questi criteri potrebbero essere già selezionati se si configura il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="477dc-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="477dc-113">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="477dc-113">Select **Save**.</span></span>
1. <span data-ttu-id="477dc-114">In **Criteri applicabili a destinatari specifici** scegliere Regola collegamenti sicuri **consigliati** e quindi selezionare l'icona Modifica. </span><span class="sxs-lookup"><span data-stu-id="477dc-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="477dc-115">Selezionare **le** impostazioni, scorrere verso il basso, immettere l'URL che non si desidera controllare e quindi selezionare **l'icona** Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="477dc-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="477dc-116">Selezionare **applicato a** e quindi selezionare il nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="477dc-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="477dc-117">Selezionare eventuali domini aggiuntivi a cui si desidera applicare la regola.</span><span class="sxs-lookup"><span data-stu-id="477dc-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="477dc-118">Selezionare **Aggiungi**, **OK** e quindi **Salva.**</span><span class="sxs-lookup"><span data-stu-id="477dc-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="477dc-119">I collegamenti sicuri di ATP sono ora configurati.</span><span class="sxs-lookup"><span data-stu-id="477dc-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="477dc-120">Consentire fino a 30 minuti per l'applicazione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="477dc-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="477dc-121">Quando un utente riceve un messaggio di posta elettronica con collegamenti, i collegamenti vengono analizzati.</span><span class="sxs-lookup"><span data-stu-id="477dc-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="477dc-122">Se i collegamenti sono considerati sicuri, saranno selezionabili.</span><span class="sxs-lookup"><span data-stu-id="477dc-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="477dc-123">Tuttavia, se il collegamento si trova nell'elenco dei contatti bloccati, gli utenti visualizzano un messaggio che indica che è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="477dc-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>