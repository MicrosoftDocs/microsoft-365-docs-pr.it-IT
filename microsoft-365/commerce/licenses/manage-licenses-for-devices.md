---
title: Gestire le licenze per i dispositivi
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Scopri come assegnare licenze ai gruppi per l'uso con i dispositivi.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911483"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="bd73e-103">Gestire le licenze per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd73e-103">Manage licenses for devices</span></span>

<span data-ttu-id="bd73e-104">Se hai Microsoft 365 Apps for enterprise (dispositivo) o Microsoft 365 Apps for Education (dispositivo), puoi assegnare licenze ai dispositivi usando i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bd73e-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="bd73e-105">Quando un dispositivo ha una licenza, chiunque lo usi può usare Microsoft 365 Apps for enterprise (in precedenza denominato Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="bd73e-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="bd73e-106">Si supponga, ad esempio, di disporre di 20 portatili e tablet utilizzati dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd73e-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="bd73e-107">Quando assegni una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi usa Microsoft 365 Apps for enterprise senza la necessità della propria licenza.</span><span class="sxs-lookup"><span data-stu-id="bd73e-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd73e-108">Le licenze basate su dispositivi per Microsoft 365 Apps for enterprise sono disponibili solo come licenza per componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="bd73e-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="bd73e-109">Per i clienti commerciali, la licenza è *Microsoft 365 Apps for enterprise (dispositivo)* ed è disponibile solo tramite Contratto Enterprise/Contratto Enterprise Subscription.</span><span class="sxs-lookup"><span data-stu-id="bd73e-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="bd73e-110">Per i clienti education, la licenza è *Microsoft 365 Apps for Education (dispositivo)* ed è disponibile solo tramite Enrollment for Education Solutions (EES).</span><span class="sxs-lookup"><span data-stu-id="bd73e-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="bd73e-111">Per ulteriori informazioni, leggere il post di blog sulla [disponibilità dell'istruzione.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)</span><span class="sxs-lookup"><span data-stu-id="bd73e-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="bd73e-112">Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd73e-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="bd73e-113">Per iniziare, creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd73e-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="bd73e-114">Per altre informazioni sulle licenze dei dispositivi, inclusi i requisiti dei dispositivi, i tipi di gruppi che puoi usare e come configurare Microsoft 365 Apps for enterprise per l'uso delle licenze per dispositivi, vedi Licenze basate su dispositivi per [Microsoft 365 Apps for enterprise.](/deployoffice/device-based-licensing)</span><span class="sxs-lookup"><span data-stu-id="bd73e-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd73e-115">Per completare le attività in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="bd73e-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="bd73e-116">Assegnare licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd73e-116">Assign licenses to devices</span></span>

<span data-ttu-id="bd73e-117">Quando assegni licenze a un gruppo, assegna le licenze a tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd73e-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="bd73e-118">È possibile assegnare una sola sottoscrizione a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd73e-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="bd73e-119">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione.</span><span class="sxs-lookup"><span data-stu-id="bd73e-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="bd73e-120">Nella pagina **Licenze** scegliere **Microsoft 365 Apps for Education (dispositivo)** o **Microsoft 365 Apps for enterprise (dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="bd73e-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="bd73e-121">Nella pagina successiva scegliere un abbonamento e quindi **Assegnare licenze.**</span><span class="sxs-lookup"><span data-stu-id="bd73e-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="bd73e-122">Nel riquadro **Assegna licenze a un gruppo** inizia a digitare un nome di gruppo e quindi sceglilo dai risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd73e-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="bd73e-123">Scegliere **Assegna**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bd73e-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="bd73e-124">Annullare l'assegnazione delle licenze dai dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd73e-124">Unassign licenses from devices</span></span>

<span data-ttu-id="bd73e-125">Quando rimuovi le licenze da un gruppo, rimuovi le licenze da tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd73e-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="bd73e-126">Tutte le app e i dati associati sono quindi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="bd73e-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="bd73e-127">Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione.</span><span class="sxs-lookup"><span data-stu-id="bd73e-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="bd73e-128">Nella pagina **Licenze** scegliere **Microsoft 365 Apps for Education (dispositivo)** o **Microsoft 365 Apps for enterprise (dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="bd73e-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="bd73e-129">Nella pagina successiva scegli una sottoscrizione, scegli **Altre azioni,** quindi scegli **Annulla assegnazione licenze.**</span><span class="sxs-lookup"><span data-stu-id="bd73e-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="bd73e-130">Nella finestra **di dialogo** Annulla assegnazione licenze scegliere **Annulla assegnazione.**</span><span class="sxs-lookup"><span data-stu-id="bd73e-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>