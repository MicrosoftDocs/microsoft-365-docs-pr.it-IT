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
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826280"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="5fe3c-103">Gestire le licenze per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="5fe3c-103">Manage licenses for devices</span></span>

<span data-ttu-id="5fe3c-104">Se si dispone di Office 365 ProPlus (Device) o Office 365 ProPlus for Education (Device), è possibile assegnare licenze ai dispositivi mediante i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-104">If you have Office 365 ProPlus (device) or Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="5fe3c-105">Quando un dispositivo dispone di una licenza, tutti gli utenti che utilizzano tale dispositivo possono utilizzare Office 365.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="5fe3c-106">Ad esempio, si supponga di disporre di 20 laptop e tablet utilizzati dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="5fe3c-107">Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi utilizza Office 365 senza la necessità di disporre di una licenza.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fe3c-108">La gestione delle licenze basate su dispositivo per Office 365 ProPlus è disponibile solo come licenza per i componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-108">Device-based licensing for Office 365 ProPlus is available only as an add-on license for some commerical customers and some education customers.</span></span> <span data-ttu-id="5fe3c-109">Per i clienti commerciali, la licenza è *Office 365 ProPlus (dispositivo)* ed è disponibile solo tramite sottoscrizione Enterprise Agreement/Enterprise Agreement.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-109">For commercial customers, the license is *Office 365 ProPlus (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="5fe3c-110">Per i clienti dell'istruzione, la licenza è *Office 365 ProPlus for Education (Device)* ed è disponibile solo tramite la registrazione per Education Solutions (SEO).</span><span class="sxs-lookup"><span data-stu-id="5fe3c-110">For education customers, the license is *Office 365 ProPlus for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="5fe3c-111">Per ulteriori informazioni, leggere il post di Blog sulla [disponibilità dell'istruzione](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="5fe3c-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="5fe3c-112">Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="5fe3c-113">Per iniziare, è necessario creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="5fe3c-114">Per ulteriori informazioni sulle licenze per dispositivi, inclusi i requisiti dei dispositivi, sui tipi di gruppi che è possibile utilizzare e su come configurare Office 365 ProPlus per l'utilizzo delle licenze per i dispositivi, vedere [Device-Based Licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="5fe3c-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device-based licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fe3c-115">Per completare le attività descritte in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="5fe3c-116">Assegnare licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="5fe3c-116">Assign licenses to devices</span></span>

<span data-ttu-id="5fe3c-117">Quando si assegnano le licenze a un gruppo, si assegnano le licenze a tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="5fe3c-118">È possibile assegnare una sola sottoscrizione a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="5fe3c-119">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="5fe3c-120">Nella pagina **licenze** scegliere **Office 365 ProPlus per Education (Device)** o **Office ProPlus (Device)**.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-120">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="5fe3c-121">Nella pagina successiva, scegliere un abbonamento, quindi fare clic su **assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="5fe3c-122">Nel riquadro **assegna licenze a un gruppo** , iniziare a digitare il nome di un gruppo e quindi sceglierlo dai risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="5fe3c-123">Scegliere **assegna**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="5fe3c-124">Annullamento dell'assegnazione delle licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="5fe3c-124">Unassign licenses from devices</span></span>

<span data-ttu-id="5fe3c-125">Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="5fe3c-126">Tutte le app e i dati associati sono quindi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="5fe3c-127">Nell'interfaccia di amministrazione, andare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="5fe3c-128">Nella pagina **licenze** scegliere **Office 365 ProPlus per Education (Device)** o **Office ProPlus (Device)**.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-128">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="5fe3c-129">Nella pagina successiva, scegliere un abbonamento, scegliere **altre azioni**, quindi fare clic su **Annulla assegnazione licenze**.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="5fe3c-130">Nella finestra di dialogo **Annulla assegnazione licenze** scegliere **Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe3c-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>