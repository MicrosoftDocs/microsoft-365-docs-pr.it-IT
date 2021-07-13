---
title: Microsoft 365 Lighthouse Panoramica della pagina conformità dispositivo
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP) Microsoft 365 Lighthouse, informazioni sulla pagina Conformità dei dispositivi.
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395100"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="d68e0-103">Microsoft 365 Lighthouse Panoramica della pagina conformità dispositivo</span><span class="sxs-lookup"><span data-stu-id="d68e0-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="d68e0-104">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d68e0-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="d68e0-105">Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="d68e0-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="d68e0-106">Microsoft 365 Lighthouse consente di visualizzare informazioni dettagliate e informazioni relative alla conformità dei dispositivi intune per tutti i tenant selezionando **Dispositivi** nel riquadro di spostamento sinistro per aprire la pagina Conformità dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d68e0-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="d68e0-107">Da questa pagina è possibile ottenere una panoramica dello stato di conformità tra i tenant, visualizzare un elenco di dispositivi per ogni tenant e ottenere report sullo stato dei criteri e delle impostazioni di conformità.</span><span class="sxs-lookup"><span data-stu-id="d68e0-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="d68e0-108">Scheda Panoramica</span><span class="sxs-lookup"><span data-stu-id="d68e0-108">Overview tab</span></span>  
  
<span data-ttu-id="d68e0-109">Nella scheda Panoramica puoi visualizzare lo stato di conformità dei dispositivi nei tenant, vedere le tendenze di conformità dei dispositivi mensili e verificare se ai dispositivi sono assegnati criteri di conformità.</span><span class="sxs-lookup"><span data-stu-id="d68e0-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="d68e0-110">È inoltre possibile visualizzare informazioni sulle azioni e sui requisiti di conformità dei dispositivi tenant in base ai criteri di accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="d68e0-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="Screenshot della scheda Panoramica.":::

## <a name="devices-tab"></a><span data-ttu-id="d68e0-112">Scheda Dispositivi</span><span class="sxs-lookup"><span data-stu-id="d68e0-112">Devices tab</span></span>

<span data-ttu-id="d68e0-113">Nella scheda Dispositivi è possibile visualizzare un elenco di tutti i dispositivi tenant e filtrare l'elenco in base ai seguenti stati di conformità: Conforme, Non conforme, In periodo di tolleranza e Non valutato.</span><span class="sxs-lookup"><span data-stu-id="d68e0-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="d68e0-114">Per altre informazioni sui diversi stati di conformità, vedi Monitorare i criteri di conformità dei dispositivi [intune.](/mem/intune/protect/compliance-policy-monitor)</span><span class="sxs-lookup"><span data-stu-id="d68e0-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="d68e0-115">Seleziona qualsiasi dispositivo per visualizzare ulteriori informazioni sul motivo per cui il dispositivo è nello stato di conformità corrente.</span><span class="sxs-lookup"><span data-stu-id="d68e0-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="d68e0-116">Se devi eseguire un'azione sul dispositivo, è disponibile un'opzione per visualizzare il dispositivo in Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="d68e0-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="Screenshot della scheda Dispositivi.":::

## <a name="policies-tab"></a><span data-ttu-id="d68e0-118">Scheda Criteri</span><span class="sxs-lookup"><span data-stu-id="d68e0-118">Policies tab</span></span>

<span data-ttu-id="d68e0-119">Nella scheda Criteri è possibile visualizzare i criteri di conformità nei tenant e confrontare due o tre criteri dello stesso tipo di piattaforma utilizzando la funzionalità Confronta sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="d68e0-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="d68e0-120">È inoltre possibile selezionare qualsiasi criterio per visualizzare ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="d68e0-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="Screenshot della scheda Criteri.":::

## <a name="settings-tab"></a><span data-ttu-id="d68e0-122">Impostazioni scheda</span><span class="sxs-lookup"><span data-stu-id="d68e0-122">Settings tab</span></span>

<span data-ttu-id="d68e0-123">La scheda impostazioni fornisce un report aggregato delle impostazioni non conformi nei dispositivi tenant.</span><span class="sxs-lookup"><span data-stu-id="d68e0-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="d68e0-124">Selezionare una delle righe del report per visualizzare ulteriori informazioni, inclusi i tenant a cui appartengono i dispositivi non conformi.</span><span class="sxs-lookup"><span data-stu-id="d68e0-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Screenshot della scheda Impostazioni.":::

## <a name="related-content"></a><span data-ttu-id="d68e0-126">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d68e0-126">Related content</span></span>

<span data-ttu-id="d68e0-127">[Microsoft 365 Lighthouse panoramica della pagina Utenti](m365-lighthouse-users-page-overview.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="d68e0-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="d68e0-128">[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)</span><span class="sxs-lookup"><span data-stu-id="d68e0-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
