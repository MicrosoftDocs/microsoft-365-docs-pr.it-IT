---
title: 'Passaggio 4: pianificare modifiche apportate agli indirizzi IP e URL'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 44990dcfd09e5cc2a44666da43fdeeaffd59da7d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868269"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="ca9af-102">Passaggio 4: pianificare modifiche apportate agli indirizzi IP e URL</span><span class="sxs-lookup"><span data-stu-id="ca9af-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="ca9af-103">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ca9af-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="ca9af-p101">Questo passaggio richiede di aver completato il [passaggio 3](networking-configure-proxies-firewalls.md). Se non è stato completato il passaggio 3, andare al [passaggio 5](networking-optimize-tcp-performance.md).</span><span class="sxs-lookup"><span data-stu-id="ca9af-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="ca9af-p102">Gli URL e gli indirizzi IP usati dalla rete globale di Microsoft 365 cambiano nel tempo, è quindi importante pianificare gli aggiornamenti a questi endpoint. Ad esempio, potrebbe essere necessario configurare di nuovo i dispositivi di sicurezza nella rete perimetrale con:</span><span class="sxs-lookup"><span data-stu-id="ca9af-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="ca9af-108">Nuovi URL per nuovi servizi che richiedono l'elaborazione senza intoppi</span><span class="sxs-lookup"><span data-stu-id="ca9af-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="ca9af-109">Rimozione di URL per servizi non più disponibili</span><span class="sxs-lookup"><span data-stu-id="ca9af-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="ca9af-110">Nuovi intervalli di indirizzi IP per nuovi percorsi di rete e server Microsoft su Internet</span><span class="sxs-lookup"><span data-stu-id="ca9af-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="ca9af-111">Modifiche agli intervalli di indirizzi IP per i diversi servizi</span><span class="sxs-lookup"><span data-stu-id="ca9af-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="ca9af-112">Per ulteriori informazioni sulla creazione di un piano di implementazione delle modifiche agli endpoint, comprensivo di notifiche di tali modifiche, vedere [Gestione degli endpoint di Office 365 - Integrazione](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) e [Gestione degli endpoint di Office 365 - Proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span><span class="sxs-lookup"><span data-stu-id="ca9af-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="ca9af-113">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step4) di questa fase.</span><span class="sxs-lookup"><span data-stu-id="ca9af-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ca9af-114">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ca9af-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="ca9af-115">Ottimizzare prestazioni di client e del servizio di Office 365</span><span class="sxs-lookup"><span data-stu-id="ca9af-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
