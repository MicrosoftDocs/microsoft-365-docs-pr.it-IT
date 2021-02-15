---
title: Dati analitici sugli aggiornamenti della sicurezza di Windows
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941442"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="c0c25-103">Dati analitici sugli aggiornamenti della sicurezza di Windows</span><span class="sxs-lookup"><span data-stu-id="c0c25-103">Windows security update insights</span></span>
<span data-ttu-id="c0c25-104">Questa visualizzazione offre una panoramica dello stato degli aggiornamenti della sicurezza per i dispositivi Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c0c25-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="c0c25-105">Per visualizzare i dati di utilizzo, selezionare la <strong>scheda Aggiornamenti della sicurezza di Windows.</strong></span><span class="sxs-lookup"><span data-stu-id="c0c25-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Riquadro degli aggiornamenti della sicurezza di Windows: grafici a barre dello stato del dispositivo e della versione di aggiornamento nella colonna sinistra, avanzamento della distribuzione degli aggiornamenti nel tempo nella colonna centrale e percentuale di dispositivi attivi in base al gruppo di distribuzione, nonché numero di giorni necessari per raggiungere la destinazione di distribuzione del 95% nella colonna destra.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="c0c25-107">Stato del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c0c25-107">Device status</span></span>

<span data-ttu-id="c0c25-108">Per poter essere aggiornati da Windows Update, i dispositivi devono essere connessi a Internet e non ibernazione per un minimo di sei ore, due dei quali devono essere continui.</span><span class="sxs-lookup"><span data-stu-id="c0c25-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="c0c25-109">Anche se è possibile che un dispositivo che non soddisfa questi requisiti venga aggiornato, i dispositivi che soddisfano tali requisiti hanno la massima probabilità di essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="c0c25-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="c0c25-110">Categorizziamo l'attività dei dispositivi nel contesto di Windows Update con questi termini:</span><span class="sxs-lookup"><span data-stu-id="c0c25-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="c0c25-111"><strong>Attivo:</strong> Dispositivi che hanno soddisfatto i criteri di attività minimi (sei ore, due continui) per la versione più recente dell'aggiornamento della sicurezza e che hanno archiviato con Microsoft Intune almeno ogni cinque giorni</span><span class="sxs-lookup"><span data-stu-id="c0c25-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="c0c25-112"><strong>Sincronizzato:</strong> Dispositivi che hanno archiviato con Intune negli ultimi 28 giorni</span><span class="sxs-lookup"><span data-stu-id="c0c25-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="c0c25-113"><strong>Non sincronizzato:</strong> Dispositivi che <i>non hanno</i> archiviato con Intune negli ultimi 28 giorni</span><span class="sxs-lookup"><span data-stu-id="c0c25-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="c0c25-114">Aggiornare lo stato della versione</span><span class="sxs-lookup"><span data-stu-id="c0c25-114">Update version status</span></span>

<span data-ttu-id="c0c25-115">Microsoft rilascia gli aggiornamenti della sicurezza ogni secondo martedì del mese.</span><span class="sxs-lookup"><span data-stu-id="c0c25-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="c0c25-116">Ogni versione aggiunge aggiornamenti importanti per le vulnerabilità di sicurezza note.</span><span class="sxs-lookup"><span data-stu-id="c0c25-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="c0c25-117">Microsoft Managed Desktop garantisce che il 95% dei dispositivi gestiti sia aggiornato con l'aggiornamento della sicurezza più recente disponibile ogni mese.</span><span class="sxs-lookup"><span data-stu-id="c0c25-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="c0c25-118">Gli aggiornamenti della sicurezza vengono talvolta rilasciati in altri momenti per affrontare con urgenza nuove minacce.</span><span class="sxs-lookup"><span data-stu-id="c0c25-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="c0c25-119">Microsoft Managed Desktop distribuisce questi aggiornamenti in modo simile.</span><span class="sxs-lookup"><span data-stu-id="c0c25-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="c0c25-120">Lo stato delle versioni degli aggiornamenti della sicurezza viene classificato con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0c25-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="c0c25-121"><strong>Corrente:</strong> Dispositivi che eseguono l'aggiornamento rilasciato nel mese corrente</span><span class="sxs-lookup"><span data-stu-id="c0c25-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="c0c25-122"><strong>Precedente:</strong> Dispositivi che eseguono l'aggiornamento rilasciato nel mese precedente</span><span class="sxs-lookup"><span data-stu-id="c0c25-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="c0c25-123"><strong>Meno recente:</strong> Dispositivi che eseguono qualsiasi aggiornamento della sicurezza rilasciato prima del mese precedente</span><span class="sxs-lookup"><span data-stu-id="c0c25-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="c0c25-124">Dovrebbero essere visualizzati pochi <strong></strong> dispositivi nella categoria Meno recente. Una popolazione di grandi dimensioni o in crescita probabilmente indica un problema sistemico che è necessario segnalare a Microsoft Managed Desktop in modo da poter analizzare.</span><span class="sxs-lookup"><span data-stu-id="c0c25-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="c0c25-125">Avanzamento della distribuzione</span><span class="sxs-lookup"><span data-stu-id="c0c25-125">Deployment progress</span></span>

<span data-ttu-id="c0c25-126">All'inizio di ogni ciclo di rilascio degli aggiornamenti della sicurezza, Microsoft Managed Desktop prende uno snapshot della popolazione di dispositivi e imposta l'obiettivo di distribuzione sul 95% della popolazione.</span><span class="sxs-lookup"><span data-stu-id="c0c25-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="c0c25-127"><strong>L'area di avanzamento</strong> della distribuzione mostra una tendenza cronologica aggiornata ogni giorno, verificando la frequenza con cui la distribuzione dell'aggiornamento soddisfa questo obiettivo per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="c0c25-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="c0c25-128">Questo grafico mostra solo i dispositivi con stato Attivo.</span><span class="sxs-lookup"><span data-stu-id="c0c25-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="c0c25-129">Puoi visualizzare questi dati per i cicli di aggiornamento precedenti usando il menu a discesa in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="c0c25-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="c0c25-130">Il periodo selezionato in questo menu si applica a tutte le informazioni nell'intera pagina.</span><span class="sxs-lookup"><span data-stu-id="c0c25-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="c0c25-131"><strong>L'area Dispositivi attivi aggiornati in</strong> base al gruppo di distribuzione offre una visualizzazione diversa mostrando l'avanzamento dell'installazione dell'aggiornamento per ogni gruppo di distribuzione di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c0c25-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="c0c25-132"><strong>Nell'area Giorni per raggiungere</strong> l'area di destinazione viene visualizzato il tempo impiegato per il 95% del numero totale di dispositivi da aggiornare con l'aggiornamento della sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="c0c25-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="c0c25-133">Mentre è in corso la distribuzione, in quest'area viene visualizzato l'opzione Ancora <strong>aggiornamento</strong> fino a quando non viene raggiunta la destinazione del 95% per l'aggiornamento selezionato.</span><span class="sxs-lookup"><span data-stu-id="c0c25-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="c0c25-134">Area dettagli dispositivo</span><span class="sxs-lookup"><span data-stu-id="c0c25-134">Device details area</span></span>

<span data-ttu-id="c0c25-135">Nella parte inferiore del dashboard è disponibile una tabella che mostra informazioni dettagliate per i dispositivi, tra cui lo stato del [dispositivo](#device-status) e [lo stato della versione di aggiornamento.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="c0c25-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="c0c25-136">È possibile cercare questo elenco o filtrarlo in base a qualsiasi valore elencato.</span><span class="sxs-lookup"><span data-stu-id="c0c25-136">You can search this list or filter it by any listed value.</span></span>


![Tabella dettagli dispositivo che mostra le colonne relative al nome del dispositivo, all'utente assegnato, allo stato del dispositivo, alla versione di aggiornamento, alla versione del sistema operativo e alla data dell'ultima sincronizzazione del dispositivo.](../../media/security-update-insights-device-table-sterile.png)
