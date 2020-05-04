---
title: Gestire le licenze per i dispositivi
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Informazioni su come assegnare licenze ai gruppi per l'utilizzo con i dispositivi.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: 1a525117c25a2471ad696ef1447fd7e4ccb6bed0
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011186"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="7a514-103">Gestire le licenze per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="7a514-103">Manage licenses for devices</span></span>

<span data-ttu-id="7a514-104">Se si dispone di Microsoft 365 Apps for Enterprise (Device) o Microsoft 365 Apps for Education (Device), è possibile assegnare licenze ai dispositivi mediante i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7a514-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="7a514-105">Quando un dispositivo dispone di una licenza, chiunque utilizza tale dispositivo può utilizzare Microsoft 365 Apps for Enterprise (in precedenza denominato Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="7a514-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="7a514-106">Ad esempio, si supponga di disporre di 20 laptop e tablet utilizzati dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7a514-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="7a514-107">Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi utilizza Microsoft 365 Apps for Enterprise senza che sia necessaria la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="7a514-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a514-108">La gestione delle licenze basate su dispositivo per Microsoft 365 Apps for Enterprise è disponibile solo come licenza per i componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="7a514-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="7a514-109">Per i clienti commerciali, la licenza è *Microsoft 365 Apps for Enterprise (Device)* ed è disponibile solo tramite la sottoscrizione Enterprise Agreement/Enterprise Agreement.</span><span class="sxs-lookup"><span data-stu-id="7a514-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="7a514-110">Per i clienti dell'istruzione, la licenza è *Microsoft 365 Apps for Education (Device)* ed è disponibile solo tramite la registrazione per Education Solutions (SEO).</span><span class="sxs-lookup"><span data-stu-id="7a514-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="7a514-111">Per ulteriori informazioni, leggere il post di Blog sulla [disponibilità dell'istruzione](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="7a514-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="7a514-112">Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a514-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="7a514-113">Per iniziare, è necessario creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="7a514-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="7a514-114">Per ulteriori informazioni sulle licenze per dispositivi, inclusi i requisiti per i dispositivi, sui tipi di gruppi che è possibile utilizzare e su come configurare le app Microsoft 365 per Enterprise per l'utilizzo delle licenze per dispositivi, vedere [Device-Based Licensing for Microsoft 365 Apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="7a514-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a514-115">Per completare le attività descritte in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="7a514-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="7a514-116">Assegnare licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="7a514-116">Assign licenses to devices</span></span>

<span data-ttu-id="7a514-117">Quando si assegnano le licenze a un gruppo, si assegnano le licenze a tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="7a514-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="7a514-118">È possibile assegnare una sola sottoscrizione a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="7a514-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="7a514-119">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="7a514-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="7a514-120">Nella pagina **licenze** scegliere **Microsoft 365 Apps for Education (Device)** o **Microsoft 365 Apps for Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="7a514-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="7a514-121">Nella pagina successiva, scegliere un abbonamento, quindi fare clic su **assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="7a514-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="7a514-122">Nel riquadro **assegna licenze a un gruppo** , iniziare a digitare il nome di un gruppo e quindi sceglierlo dai risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a514-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="7a514-123">Scegliere **assegna**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7a514-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="7a514-124">Annullamento dell'assegnazione delle licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="7a514-124">Unassign licenses from devices</span></span>

<span data-ttu-id="7a514-125">Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="7a514-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="7a514-126">Tutte le app e i dati associati sono quindi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="7a514-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="7a514-127">Nell'interfaccia di amministrazione, andare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="7a514-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="7a514-128">Nella pagina **licenze** scegliere **Microsoft 365 Apps for Education (Device)** o **Microsoft 365 Apps for Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="7a514-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="7a514-129">Nella pagina successiva, scegliere un abbonamento, scegliere **altre azioni**, quindi fare clic su **Annulla assegnazione licenze**.</span><span class="sxs-lookup"><span data-stu-id="7a514-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="7a514-130">Nella finestra di dialogo **Annulla assegnazione licenze** scegliere **Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="7a514-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>