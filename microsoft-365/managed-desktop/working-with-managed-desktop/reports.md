---
title: Usare i report
description: I vari report disponibili in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729969"
---
# <a name="work-with-reports"></a><span data-ttu-id="5619a-104">Usare i report</span><span class="sxs-lookup"><span data-stu-id="5619a-104">Work with reports</span></span>

<span data-ttu-id="5619a-105">Microsoft Managed Desktop fornisce diversi report e dashboard che gli amministratori IT dell'organizzazione possono usare per comprendere diversi aspetti della popolazione di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5619a-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="5619a-106">I report sono disponibili in due posizioni: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) e nell'Microsoft 365 [admin center.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)</span><span class="sxs-lookup"><span data-stu-id="5619a-106"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="5619a-107">Report in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5619a-107">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="5619a-108">La Microsoft Endpoint Manager console riunisce i report di diversi prodotti in un'unica posizione per monitorare e analizzare i problemi relativi alla configurazione e ai dispositivi dell'organizzazione di Azure AD ("tenant").</span><span class="sxs-lookup"><span data-stu-id="5619a-108">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="5619a-109">Microsoft Managed desktop include  una sezione in Report nel menu principale in cui è possibile trovare report specifici per la gestione dei dispositivi registrati da Microsoft Managed Desktop di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5619a-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="5619a-110">Questi report includono:</span><span class="sxs-lookup"><span data-stu-id="5619a-110">These reports include:</span></span>
- <span data-ttu-id="5619a-111">**Dispositivi gestiti**  >  **Aggiornamenti delle funzionalità**: questa visualizzazione mostra lo stato complessivo degli aggiornamenti delle funzionalità nei dispositivi Microsoft Managed Desktop dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5619a-111">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="5619a-112">**Dispositivi gestiti**  >  **Office aggiornamenti**: questa visualizzazione mostra lo stato complessivo degli aggiornamenti Office nei dispositivi Microsoft Managed Desktop dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5619a-112">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="5619a-113">Inoltre, in diverse posizioni in Microsoft Endpoint Manager è possibile filtrare i report di altri gruppi di prodotti per includere o escludere in modo specifico i dispositivi gestiti da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5619a-113">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="5619a-114">Questi report hanno integrato questa funzionalità di filtro:</span><span class="sxs-lookup"><span data-stu-id="5619a-114">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="5619a-115">Tutti i dispositivi</span><span class="sxs-lookup"><span data-stu-id="5619a-115">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="5619a-116">Conformità dispositivo</span><span class="sxs-lookup"><span data-stu-id="5619a-116">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="5619a-117">Dispositivi non conformi</span><span class="sxs-lookup"><span data-stu-id="5619a-117">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="5619a-118">I Microsoft Managed Desktop personalizzati garantiscono l'accesso solo ai Microsoft Managed Desktop report.</span><span class="sxs-lookup"><span data-stu-id="5619a-118">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="5619a-119">Per accedere ad altre parti di Microsoft Endpoint Manager, ad esempio **Tutti** i dispositivi, vedi Controllo dell'accesso basato sui ruoli [con](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="5619a-119">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 


 ## <a name="inventory-data"></a><span data-ttu-id="5619a-120">Dati di inventario</span><span class="sxs-lookup"><span data-stu-id="5619a-120">Inventory data</span></span>

<span data-ttu-id="5619a-121">Oltre agli altri report, puoi esportare informazioni sui dispositivi gestiti da Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5619a-121">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="5619a-122">Nella visualizzazione **Dispositivi** dell'area **Dispositivi** di Microsoft Endpoint Manager,  usa la scheda Esporta tutto per [scaricare un report inventario dettagliato.](device-inventory-report.md)</span><span class="sxs-lookup"><span data-stu-id="5619a-122">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>