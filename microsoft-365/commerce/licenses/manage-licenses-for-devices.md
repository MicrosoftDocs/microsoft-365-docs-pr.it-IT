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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: ce3c8f7d669f2fe5d19c48d7a1fb1f224aaec7f4
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402871"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="0ddb7-103">Gestire le licenze per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="0ddb7-103">Manage licenses for devices</span></span>

<span data-ttu-id="0ddb7-104">Se si dispone di Microsoft 365 Apps for Enterprise (Device) o Microsoft 365 Apps for Education (Device), è possibile assegnare licenze ai dispositivi mediante i gruppi di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="0ddb7-105">Quando un dispositivo dispone di una licenza, chiunque utilizza tale dispositivo può utilizzare Microsoft 365 Apps for Enterprise (in precedenza denominato Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="0ddb7-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="0ddb7-106">Ad esempio, si supponga di disporre di 20 laptop e tablet utilizzati dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="0ddb7-107">Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi utilizza Microsoft 365 Apps for Enterprise senza che sia necessaria la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ddb7-108">La gestione delle licenze basate su dispositivo per Microsoft 365 Apps for Enterprise è disponibile solo come licenza per i componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="0ddb7-109">Per i clienti commerciali, la licenza è *Microsoft 365 Apps for Enterprise (Device)* ed è disponibile solo tramite la sottoscrizione Enterprise Agreement/Enterprise Agreement.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="0ddb7-110">Per i clienti dell'istruzione, la licenza è *Microsoft 365 Apps for Education (Device)* ed è disponibile solo tramite la registrazione per Education Solutions (SEO).</span><span class="sxs-lookup"><span data-stu-id="0ddb7-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="0ddb7-111">Per ulteriori informazioni, leggere il post di Blog sulla [disponibilità dell'istruzione](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="0ddb7-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="0ddb7-112">Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="0ddb7-113">Per iniziare, è necessario creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="0ddb7-114">Per ulteriori informazioni sulle licenze per dispositivi, inclusi i requisiti per i dispositivi, sui tipi di gruppi che è possibile utilizzare e su come configurare le app Microsoft 365 per Enterprise per l'utilizzo delle licenze per dispositivi, vedere [Device-Based Licensing for Microsoft 365 Apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="0ddb7-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ddb7-115">Per completare le attività descritte in questo articolo, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="0ddb7-116">Assegnare licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="0ddb7-116">Assign licenses to devices</span></span>

<span data-ttu-id="0ddb7-117">Quando si assegnano le licenze a un gruppo, si assegnano le licenze a tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="0ddb7-118">È possibile assegnare una sola sottoscrizione a un singolo gruppo.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="0ddb7-119">Nell'interfaccia di amministrazione di Microsoft 365 passare alla **Billing**  >  pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="0ddb7-120">Nella pagina **licenze** scegliere **Microsoft 365 Apps for Education (Device)** o **Microsoft 365 Apps for Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="0ddb7-121">Nella pagina successiva, scegliere un abbonamento, quindi fare clic su **assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="0ddb7-122">Nel riquadro **assegna licenze a un gruppo** , iniziare a digitare il nome di un gruppo e quindi sceglierlo dai risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="0ddb7-123">Scegliere **assegna**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="0ddb7-124">Annullamento dell'assegnazione delle licenze ai dispositivi</span><span class="sxs-lookup"><span data-stu-id="0ddb7-124">Unassign licenses from devices</span></span>

<span data-ttu-id="0ddb7-125">Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="0ddb7-126">Tutte le app e i dati associati sono quindi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="0ddb7-127">Nell'interfaccia di amministrazione, andare alla **Billing**  >  pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="0ddb7-128">Nella pagina **licenze** scegliere **Microsoft 365 Apps for Education (Device)** o **Microsoft 365 Apps for Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="0ddb7-129">Nella pagina successiva, scegliere un abbonamento, scegliere **altre azioni**, quindi fare clic su **Annulla assegnazione licenze**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="0ddb7-130">Nella finestra di dialogo **Annulla assegnazione licenze** scegliere **Annulla assegnazione**.</span><span class="sxs-lookup"><span data-stu-id="0ddb7-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>