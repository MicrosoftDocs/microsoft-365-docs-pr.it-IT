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
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242324"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="af830-103">Gestire le licenze per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="af830-103">Manage licenses for devices</span></span>

<span data-ttu-id="af830-104">Se si dispone di Office 365 ProPlus for Education (Device), è possibile assegnare licenze ai dispositivi mediante i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af830-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="af830-105">Quando un dispositivo dispone di una licenza, tutti gli utenti che utilizzano tale dispositivo possono utilizzare Office 365.</span><span class="sxs-lookup"><span data-stu-id="af830-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="af830-106">Ad esempio, si supponga di disporre di 20 laptop e tablet utilizzati dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="af830-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="af830-107">Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi utilizza Office 365 senza la necessità di disporre di una licenza.</span><span class="sxs-lookup"><span data-stu-id="af830-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af830-108">Office 365 ProPlus for Education (Device) è disponibile solo per i clienti con contratti multilicenza di Education a3 e a5.</span><span class="sxs-lookup"><span data-stu-id="af830-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="af830-109">Per iniziare, è necessario creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="af830-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="af830-110">Per ulteriori informazioni sulle licenze per i dispositivi, compresi i requisiti dei dispositivi, i tipi di gruppi che è possibile utilizzare e come configurare Office 365 ProPlus per l'utilizzo delle licenze per i dispositivi, vedere [device licensing for Office 365 ProPlus for Education Customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="af830-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af830-111">Per completare le attività descritte in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="af830-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="af830-112">Assegnare licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="af830-112">Assign licenses to devices</span></span>

<span data-ttu-id="af830-113">Quando si assegnano le licenze a un gruppo, si assegnano le licenze a tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="af830-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="af830-114">È possibile assegnare una sola sottoscrizione a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="af830-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="af830-115">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina \*\*\*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="af830-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="af830-116">Nella pagina **licenze** scegliere **Office 365 ProPlus for Education (Device)**.</span><span class="sxs-lookup"><span data-stu-id="af830-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="af830-117">Nella pagina **Office 365 ProPlus for Education (Device)** , scegliere un abbonamento, quindi scegliere **assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="af830-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="af830-118">Nel riquadro **assegna licenze a un gruppo** , iniziare a digitare il nome di un gruppo e quindi sceglierlo dai risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="af830-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="af830-119">Scegliere **assegna**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="af830-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="af830-120">Annullamento dell'assegnazione delle licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="af830-120">Unassign licenses from devices</span></span>

<span data-ttu-id="af830-121">Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="af830-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="af830-122">Tutte le app e i dati associati sono quindi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="af830-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="af830-123">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="af830-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="af830-124">Nella pagina **licenze** scegliere **Office 365 ProPlus for Education (Device)**.</span><span class="sxs-lookup"><span data-stu-id="af830-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="af830-125">Nella pagina **Office 365 ProPlus for Education (Device)** , scegliere un abbonamento, scegliere **altre azioni**, quindi fare clic su **Annulla assegnazione licenze**.</span><span class="sxs-lookup"><span data-stu-id="af830-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="af830-126">Nella finestra di dialogo **Annulla assegnazione licenze** scegliere **Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="af830-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>