---
title: Visualizzazione report di Microsoft Defender per Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono scoprire come trovare e usare Defender per Office 365 report disponibili nel portale Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8bb03202139137adf55c4c10230b1c4e99253ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454722"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="ba2ad-103">Visualizzare i report di Defender Office 365 nel Microsoft 365 Defender portale</span><span class="sxs-lookup"><span data-stu-id="ba2ad-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ba2ad-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-104">**Applies to**</span></span>
- [<span data-ttu-id="ba2ad-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="ba2ad-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ba2ad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba2ad-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ba2ad-107">Microsoft Defender per le organizzazioni Office 365 (ad esempio, abbonamenti Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 1 o componenti aggiuntivi Microsoft Defender per Office 365 Piano 2) contengono una serie di report relativi alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="ba2ad-108">Se si dispone [delle](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)autorizzazioni necessarie, è possibile visualizzare questi  report nel portale di Microsoft 365 Defender andando a Rapporti e-mail & \> **collaborazione** \> **E-mail**& rapporti di collaborazione .</span><span class="sxs-lookup"><span data-stu-id="ba2ad-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ba2ad-109">Per passare direttamente alla pagina Rapporti di **collaborazione &** e-mail, aprire <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="ba2ad-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina dei & di collaborazione tramite posta elettronica nel portale Microsoft 365 Defender posta elettronica](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="ba2ad-111">I report di sicurezza della posta elettronica che non richiedono Defender per Office 365 sono descritti in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="ba2ad-112">I report correlati al flusso di posta sono ora disponibili nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="ba2ad-113">Per ulteriori informazioni su questi report, vedere [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="ba2ad-114">Cassaforte Report Tipi di file allegati</span><span class="sxs-lookup"><span data-stu-id="ba2ad-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="ba2ad-115">Il **Cassaforte dei tipi di file allegati** alla fine andrà via.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="ba2ad-116">Le stesse informazioni sono disponibili nella relazione [sullo stato di Threat Protection.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ba2ad-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="ba2ad-117">Cassaforte Rapporto eliminazione messaggi allegati</span><span class="sxs-lookup"><span data-stu-id="ba2ad-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="ba2ad-118">Il **Cassaforte di eliminazione dei messaggi** allegati alla fine andrà via.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="ba2ad-119">Le stesse informazioni sono disponibili nella relazione [sullo stato di Threat Protection.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ba2ad-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="ba2ad-120">Rapporto latenza della posta</span><span class="sxs-lookup"><span data-stu-id="ba2ad-120">Mail latency report</span></span>

<span data-ttu-id="ba2ad-121">Il **report Latenza della posta** mostra una visualizzazione aggregata della latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="ba2ad-122">I tempi di recapito della posta nel servizio sono influenzati da una serie di fattori e il tempo di recapito assoluto in secondi spesso non è un buon indicatore di esito positivo o di un problema.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="ba2ad-123">Un tempo di recapito lento in un giorno può essere considerato un tempo medio di recapito in un altro giorno o viceversa.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="ba2ad-124">In questo modo si tenta di qualificare il recapito dei messaggi in base ai dati statistici relativi ai tempi di recapito osservati di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="ba2ad-125">Il lato client e la latenza di rete non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="ba2ad-126">Per visualizzare il report, aprire il portale [Microsoft 365 Defender,](https://security.microsoft.com)passare **a** Report e-mail & \> **collaborazione** \> **E-mail & collaborazione.**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ba2ad-127">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Rapporto **latenza posta** e quindi fare clic su Visualizza **dettagli.**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="ba2ad-128">Per passare direttamente al report, aprire <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="ba2ad-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![Widget report di latenza della posta nella pagina Report & e-mail](../../media/mail-latency-report-widget.png)

<span data-ttu-id="ba2ad-130">Nella pagina **Rapporto latenza posta** sono disponibili le schede seguenti nella pagina **Rapporto latenza posta:**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="ba2ad-131">**50° percentile**: indica i tempi di recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="ba2ad-132">È possibile considerare questo valore come un tempo medio di recapito.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="ba2ad-133">Questa scheda è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-133">This tab is selected by default.</span></span>
- <span data-ttu-id="ba2ad-134">**90° percentile**: indica un'elevata latenza per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="ba2ad-135">Solo il 10% dei messaggi ha impiegato più tempo di questo valore per il recapito.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="ba2ad-136">**99° percentile:** indica la latenza massima per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="ba2ad-137">Indipendentemente dalla scheda selezionata, il grafico mostra i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="ba2ad-138">**Latenza recapito posta**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="ba2ad-139">**Detonazioni**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-139">**Detonations**</span></span>

<span data-ttu-id="ba2ad-140">Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare una suddivisione della latenza in ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![50° percentile del rapporto latenza della posta](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="ba2ad-142">Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dei dettagli in base ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="ba2ad-143">**Data (UTC)**: **Data inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ba2ad-144">**Visualizzazione messaggio:** uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="ba2ad-145">**Tutti i messaggi**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-145">**All messages**</span></span>
  - <span data-ttu-id="ba2ad-146">**Messaggi che contengono allegati o URL**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="ba2ad-147">**Messaggi detonati**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-147">**Detonated messages**</span></span>

<span data-ttu-id="ba2ad-148">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ba2ad-149">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ba2ad-150">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-150">**Date (UTC)**</span></span>
- <span data-ttu-id="ba2ad-151">**Percentili**: **50,** **90** o **99**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="ba2ad-152">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-152">**Message count**</span></span>
- <span data-ttu-id="ba2ad-153">**Latenza complessiva**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ba2ad-154">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ba2ad-154">Threat protection status report</span></span>

<span data-ttu-id="ba2ad-155">Il **rapporto sullo stato di** Protezione dalle minacce è un'unica visualizzazione che riunisce informazioni sul contenuto dannoso e sulla posta elettronica dannosa rilevata e bloccata da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ba2ad-156">Per ulteriori informazioni, vedere [Rapporto sullo stato di Protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="ba2ad-157">Report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="ba2ad-157">URL threat protection report</span></span>

<span data-ttu-id="ba2ad-158">Il **report di protezione dalle minacce URL** fornisce visualizzazioni di riepilogo e tendenze per le minacce rilevate e le azioni eseguite sui clic sugli URL nell'ambito Cassaforte [collegamenti.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="ba2ad-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="ba2ad-159">In questo report non saranno disponibili dati sui clic degli utenti a cui è stato applicato il criterio collegamenti Cassaforte clic utente è selezionata l'opzione Non tenere traccia **dei** clic degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="ba2ad-160">Per visualizzare il report, aprire il portale [Microsoft 365 Defender,](https://security.microsoft.com)passare **a** Report e-mail & \> **collaborazione** \> **E-mail & collaborazione.**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ba2ad-161">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare la pagina Protezione **URL** e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="ba2ad-162">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="ba2ad-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![Widget report protezione URL nella pagina Report di collaborazione & e-mail](../../media/url-protection-report-widget.png)

<span data-ttu-id="ba2ad-164">Le visualizzazioni disponibili nella pagina **del report di protezione** dalle minacce URL sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="ba2ad-165">Si tratta di un *report sulle tendenze di protezione,* ovvero i dati rappresentano le tendenze in un set di dati più grande.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="ba2ad-166">Di conseguenza, i dati nei grafici non sono disponibili in tempo reale qui, ma i dati nella tabella dei dettagli sono, quindi potresti vedere una leggera discrepanza tra i due.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="ba2ad-167">I grafici vengono aggiornati una volta ogni quattro ore e contengono dati per gli ultimi 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="ba2ad-168">Visualizzare i dati in base all'azione di protezione del clic dell'URL</span><span class="sxs-lookup"><span data-stu-id="ba2ad-168">View data by URL click protection action</span></span>

![Url Click Protection action view in the URL threat protection report](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="ba2ad-170">La visualizzazione azione Visualizza dati in base **all'URL** consente di visualizzare il numero di clic sull'URL da parte degli utenti nell'organizzazione e i risultati del clic:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="ba2ad-171">**Consentito**: all'utente è stato consentito passare all'URL.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="ba2ad-172">**Bloccato:** all'utente è stato impedito di passare all'URL.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="ba2ad-173">**Bloccato e su cui è stato fatto clic:** l'utente ha scelto di continuare a passare all'URL.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="ba2ad-174">**Fatto clic durante l'analisi**: l'utente ha fatto clic sul collegamento prima del completamento dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="ba2ad-175">Un clic indica che l'utente ha fatto clic attraverso la pagina di blocco al sito Web dannoso (gli amministratori possono disabilitare il click-through nei Cassaforte dei collegamenti).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="ba2ad-176">Se si fa **clic su Filtri**, è possibile modificare il report e la tabella dei dettagli selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="ba2ad-177">**Data (UTC)**: **Data inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ba2ad-178">**Rilevamento**:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-178">**Detection**:</span></span>
  - <span data-ttu-id="ba2ad-179">**Consentito**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-179">**Allowed**</span></span>
  - <span data-ttu-id="ba2ad-180">**Bloccato**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-180">**Blocked**</span></span>
  - <span data-ttu-id="ba2ad-181">**Bloccato e su cui è stato fatto clic**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="ba2ad-182">**Fatto clic durante l'analisi**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="ba2ad-183">**Domini**: domini URL elencati nei risultati del report.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="ba2ad-184">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-184">**Recipients**</span></span>

<span data-ttu-id="ba2ad-185">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ba2ad-186">La tabella dei dettagli sotto il grafico fornisce la seguente visualizzazione quasi in tempo reale di tutti i clic che si sono verificato nell'organizzazione negli ultimi 7 giorni:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="ba2ad-187">**Ora clic**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-187">**Click time**</span></span>
- <span data-ttu-id="ba2ad-188">**Utente**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-188">**User**</span></span>
- <span data-ttu-id="ba2ad-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-189">**URL**</span></span>
- <span data-ttu-id="ba2ad-190">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-190">**Action**</span></span>
- <span data-ttu-id="ba2ad-191">**App**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="ba2ad-192">Visualizzare i dati in base all'URL facendo clic per applicazione</span><span class="sxs-lookup"><span data-stu-id="ba2ad-192">View data by URL click by application</span></span>

![Url click by application view in the URL threat protection report](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="ba2ad-194">La **visualizzazione Visualizza dati in base all'URL** in base all'applicazione mostra il numero di clic sull'URL da parte delle app che supportano Cassaforte collegamenti:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="ba2ad-195">**Client di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-195">**Email client**</span></span>
- <span data-ttu-id="ba2ad-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-196">**PowerPoint**</span></span>
- <span data-ttu-id="ba2ad-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-197">**Word**</span></span>
- <span data-ttu-id="ba2ad-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-198">**Excel**</span></span>
- <span data-ttu-id="ba2ad-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-199">**OneNote**</span></span>
- <span data-ttu-id="ba2ad-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-200">**Visio**</span></span>
- <span data-ttu-id="ba2ad-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-201">**Teams**</span></span>
- <span data-ttu-id="ba2ad-202">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-202">**Others**</span></span>

<span data-ttu-id="ba2ad-203">Se si fa **clic su Filtri**, è possibile modificare il report e la tabella dei dettagli selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="ba2ad-204">**Data (UTC)**: **Data inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ba2ad-205">**Rilevamento:** app disponibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="ba2ad-206">**Domini**: domini URL elencati nei risultati del report.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="ba2ad-207">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-207">**Recipients**</span></span>

<span data-ttu-id="ba2ad-208">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ba2ad-209">La tabella dei dettagli sotto il grafico fornisce la seguente visualizzazione quasi in tempo reale di tutti i clic che si sono verificato nell'organizzazione negli ultimi 7 giorni:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="ba2ad-210">**Ora clic**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-210">**Click time**</span></span>
- <span data-ttu-id="ba2ad-211">**Utente**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-211">**User**</span></span>
- <span data-ttu-id="ba2ad-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-212">**URL**</span></span>
- <span data-ttu-id="ba2ad-213">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-213">**Action**</span></span>
- <span data-ttu-id="ba2ad-214">**App**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="ba2ad-215">Report aggiuntivi da visualizzare</span><span class="sxs-lookup"><span data-stu-id="ba2ad-215">Additional reports to view</span></span>

<span data-ttu-id="ba2ad-216">Oltre ai report descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="ba2ad-217">Report</span><span class="sxs-lookup"><span data-stu-id="ba2ad-217">Report</span></span>|<span data-ttu-id="ba2ad-218">Argomento</span><span class="sxs-lookup"><span data-stu-id="ba2ad-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="ba2ad-219">**Explorer** (Microsoft Defender per Office 365 Piano 2) o rilevamenti in tempo reale **(Microsoft** Defender per Office 365 Piano 1)</span><span class="sxs-lookup"><span data-stu-id="ba2ad-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="ba2ad-220">Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="ba2ad-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="ba2ad-221">Rapporti di sicurezza della posta elettronica che non richiedono Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="ba2ad-221">Email security reports that don't require Defender for Office 365</span></span>|[<span data-ttu-id="ba2ad-222">Visualizzare i report di sicurezza della posta elettronica nel portale Microsoft 365 Defender posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ba2ad-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="ba2ad-223">Rapporti del flusso di posta nell Exchange ac (EAC)</span><span class="sxs-lookup"><span data-stu-id="ba2ad-223">Mail flow reports in the Exchange admin center (EAC)</span></span>|[<span data-ttu-id="ba2ad-224">Rapporti del flusso di posta nella nuova Exchange di amministrazione</span><span class="sxs-lookup"><span data-stu-id="ba2ad-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|

<span data-ttu-id="ba2ad-225">Cmdlet per la creazione di report di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-225">PowerShell reporting cmdlets:</span></span>

<br>

****

|<span data-ttu-id="ba2ad-226">Report</span><span class="sxs-lookup"><span data-stu-id="ba2ad-226">Report</span></span>|<span data-ttu-id="ba2ad-227">Argomento</span><span class="sxs-lookup"><span data-stu-id="ba2ad-227">Topic</span></span>|
|---|---|
|<span data-ttu-id="ba2ad-228">Destinatari e mittenti principali</span><span class="sxs-lookup"><span data-stu-id="ba2ad-228">Top senders and recipients</span></span>|[<span data-ttu-id="ba2ad-229">Get-MailTrafficTopReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-229">Get-MailTrafficTopReport</span></span>](/powershell/module/exchange/get-mailtraffictopreport) <p> [<span data-ttu-id="ba2ad-230">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-230">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="ba2ad-231">Malware principale</span><span class="sxs-lookup"><span data-stu-id="ba2ad-231">Top malware</span></span>|[<span data-ttu-id="ba2ad-232">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-232">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="ba2ad-233">Traffico di posta</span><span class="sxs-lookup"><span data-stu-id="ba2ad-233">Mail traffic</span></span>|[<span data-ttu-id="ba2ad-234">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-234">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport) <p> [<span data-ttu-id="ba2ad-235">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-235">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|<span data-ttu-id="ba2ad-236">Collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="ba2ad-236">Safe Links</span></span>|[<span data-ttu-id="ba2ad-237">Get-SafeLinksAggregateReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-237">Get-SafeLinksAggregateReport</span></span>](/powershell/module/exchange/get-safelinksaggregatereport) <p> [<span data-ttu-id="ba2ad-238">Get-SafeLinksDetailReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-238">Get-SafeLinksDetailReport</span></span>](/powershell/module/exchange/get-safelinksdetailreport)|
|<span data-ttu-id="ba2ad-239">Utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="ba2ad-239">Compromised users</span></span>|[<span data-ttu-id="ba2ad-240">Get-CompromisedUserAggregateReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-240">Get-CompromisedUserAggregateReport</span></span>](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [<span data-ttu-id="ba2ad-241">Get-CompromisedUserDetailReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-241">Get-CompromisedUserDetailReport</span></span>](/powershell/module/exchange/get-compromiseduserdetailreport)|
|<span data-ttu-id="ba2ad-242">Stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="ba2ad-242">Mail flow status</span></span>|[<span data-ttu-id="ba2ad-243">Get-MailflowStatusReport</span><span class="sxs-lookup"><span data-stu-id="ba2ad-243">Get-MailflowStatusReport</span></span>](/powershell/module/exchange/get-mailflowstatusreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="ba2ad-244">Quali autorizzazioni sono necessarie per visualizzare defender per Office 365 report?</span><span class="sxs-lookup"><span data-stu-id="ba2ad-244">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="ba2ad-245">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel portale di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="ba2ad-245">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="ba2ad-246">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-246">**Organization Management**</span></span>
- <span data-ttu-id="ba2ad-247">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-247">**Security Administrator**</span></span>
- <span data-ttu-id="ba2ad-248">**Ruolo con autorizzazioni di lettura per la sicurezza**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-248">**Security Reader**</span></span>
- <span data-ttu-id="ba2ad-249">**Ruolo con autorizzazioni di lettura globali**</span><span class="sxs-lookup"><span data-stu-id="ba2ad-249">**Global Reader**</span></span>

<span data-ttu-id="ba2ad-250">Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-250">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="ba2ad-251">**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-251">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ba2ad-252">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-252">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ba2ad-253">Cosa succede se i report non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="ba2ad-253">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ba2ad-254">Se non vedi i dati nel tuo Defender per i Office 365, verifica che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-254">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ba2ad-255">L'organizzazione deve [disporre Cassaforte](set-up-safe-links-policies.md) dei collegamenti e [Cassaforte dei](set-up-safe-attachments-policies.md) criteri allegati per poter disporre di Defender Office 365 protezione.</span><span class="sxs-lookup"><span data-stu-id="ba2ad-255">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="ba2ad-256">Vedere anche [Protezione da posta indesiderata e antimalware](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ba2ad-256">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba2ad-257">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ba2ad-257">Related topics</span></span>

[<span data-ttu-id="ba2ad-258">Report e informazioni dettagliate intelligenti nel portale Microsoft 365 Defender dati</span><span class="sxs-lookup"><span data-stu-id="ba2ad-258">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="ba2ad-259">Autorizzazioni ruolo (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ba2ad-259">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
