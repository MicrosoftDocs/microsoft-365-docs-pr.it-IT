---
title: Proteggere i dati dell'organizzazione con il controllo del dispositivo
description: Monitorare la sicurezza dei dati dell'organizzazione tramite i report di controllo dei dispositivi.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772366"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="647eb-103">Proteggere i dati dell'organizzazione con il controllo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="647eb-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="647eb-104">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="647eb-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="647eb-105">Il controllo dei dispositivi Microsoft Defender for Endpoint protegge dalla perdita di dati, monitorando e controllando l'uso dei supporti da parte dei dispositivi dell'organizzazione, ad esempio l'uso di dispositivi di archiviazione rimovibili e unità USB.</span><span class="sxs-lookup"><span data-stu-id="647eb-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="647eb-106">Con il report di controllo del dispositivo puoi visualizzare gli eventi correlati all'utilizzo dei supporti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="647eb-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="647eb-107">**Eventi di controllo:** Indica il numero di eventi di controllo che si verificano quando è connesso un supporto esterno.</span><span class="sxs-lookup"><span data-stu-id="647eb-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="647eb-108">**Eventi dei criteri:** Mostra il numero di eventi dei criteri che si verificano quando viene attivato un criterio di controllo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="647eb-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="647eb-109">L'evento di controllo per tenere traccia dell'utilizzo dei contenuti multimediali è abilitato per impostazione predefinita per i dispositivi onboarded in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="647eb-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="647eb-110">Informazioni sugli eventi di controllo</span><span class="sxs-lookup"><span data-stu-id="647eb-110">Understanding the audit events</span></span>

<span data-ttu-id="647eb-111">Gli eventi di controllo includono:</span><span class="sxs-lookup"><span data-stu-id="647eb-111">The audit events include:</span></span>

- <span data-ttu-id="647eb-112">**Montaggio e smontare unità USB:** Eventi di controllo generati quando un'unità USB viene montata o disinstallata.</span><span class="sxs-lookup"><span data-stu-id="647eb-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="647eb-113">**PnP:** Gli eventi di controllo Plug and Play vengono generati quando viene connessa un'archiviazione rimovibile, una stampante o Bluetooth supporto.</span><span class="sxs-lookup"><span data-stu-id="647eb-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="647eb-114">Monitorare la sicurezza del controllo dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="647eb-114">Monitor device control security</span></span>

<span data-ttu-id="647eb-115">Il controllo dei dispositivi in Microsoft Defender for Endpoint offre agli amministratori della sicurezza strumenti che consentono loro di tenere traccia della sicurezza del controllo dei dispositivi dell'organizzazione tramite i report.</span><span class="sxs-lookup"><span data-stu-id="647eb-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="647eb-116">Puoi trovare il report di controllo del dispositivo nel centro sicurezza Microsoft 365 sicurezza andando a **Report > Protezione del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="647eb-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="647eb-117">La scheda Protezione dispositivo nel dashboard **Report** mostra il numero di eventi di controllo generati dal tipo di supporto negli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="647eb-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="647eb-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="647eb-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="647eb-119">Il **pulsante Visualizza dettagli** mostra più dati di utilizzo multimediale nella pagina del report del controllo **dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="647eb-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="647eb-120">La pagina fornisce un dashboard con un numero aggregato di eventi per tipo e un elenco di eventi.</span><span class="sxs-lookup"><span data-stu-id="647eb-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="647eb-121">Gli amministratori possono filtrare l'intervallo di tempo, il nome della classe multimediale e l'ID dispositivo.</span><span class="sxs-lookup"><span data-stu-id="647eb-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="647eb-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="647eb-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="647eb-123">Quando si seleziona un evento, viene visualizzato un riquadro a comparsa che mostra ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="647eb-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="647eb-124">**Dettagli generali:** Data, modalità azione e i criteri di questo evento.</span><span class="sxs-lookup"><span data-stu-id="647eb-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="647eb-125">**Informazioni multimediali:** Le informazioni multimediali includono Nome supporto, Nome classe, GUID classe, ID dispositivo, ID fornitore, Volume, Numero di serie e Tipo di bus.</span><span class="sxs-lookup"><span data-stu-id="647eb-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="647eb-126">**Dettagli percorso:** Nome del dispositivo e MDATP dispositivo.</span><span class="sxs-lookup"><span data-stu-id="647eb-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="647eb-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="647eb-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="647eb-128">Per visualizzare le attività in tempo reale per questi elementi multimediali nell'organizzazione, selezionare il **pulsante Apri ricerca** avanzata.</span><span class="sxs-lookup"><span data-stu-id="647eb-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="647eb-129">Include una query incorporata predefinita.</span><span class="sxs-lookup"><span data-stu-id="647eb-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="647eb-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="647eb-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="647eb-131">Per visualizzare la sicurezza del dispositivo, seleziona il **pulsante Apri** pagina dispositivo nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="647eb-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="647eb-132">Questo pulsante apre la pagina dell'entità dispositivo.</span><span class="sxs-lookup"><span data-stu-id="647eb-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="647eb-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="647eb-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="647eb-134">Segnalazione di ritardi</span><span class="sxs-lookup"><span data-stu-id="647eb-134">Reporting delays</span></span>

<span data-ttu-id="647eb-135">Il report di controllo del dispositivo può avere un ritardo di 12 ore dal momento in cui si verifica una connessione multimediale al momento in cui l'evento si riflette nella scheda o nell'elenco dei domini.</span><span class="sxs-lookup"><span data-stu-id="647eb-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
