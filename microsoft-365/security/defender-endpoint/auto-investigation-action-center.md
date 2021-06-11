---
title: Visitare il centro notifiche per visualizzare le azioni di correzione
description: Usare il centro notifiche per visualizzare i dettagli e i risultati dopo un'indagine automatizzata
keywords: azione, centro, autoir, automatizzato, indagine, risposta, correzione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844911"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="5c30c-104">Visitare il centro notifiche per visualizzare le azioni di correzione</span><span class="sxs-lookup"><span data-stu-id="5c30c-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="5c30c-105">Durante e dopo un'indagine automatizzata, vengono identificate le azioni di correzione per i rilevamenti delle minacce.</span><span class="sxs-lookup"><span data-stu-id="5c30c-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="5c30c-106">A seconda della minaccia specifica e della configurazione di [Microsoft Defender for Endpoint](/windows/security/threat-protection) per l'organizzazione, alcune azioni di correzione vengono eseguite automaticamente e altre richiedono l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="5c30c-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="5c30c-107">Se si fa parte del team delle operazioni di sicurezza dell'organizzazione, è possibile visualizzare le azioni di correzione [in](manage-auto-investigation.md#remediation-actions) sospeso e completate nel **centro notifiche.**</span><span class="sxs-lookup"><span data-stu-id="5c30c-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="5c30c-108">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5c30c-108">**Applies to:**</span></span>
- [<span data-ttu-id="5c30c-109">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5c30c-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c30c-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c30c-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="5c30c-111">(NEW!) Un centro notifiche unificato</span><span class="sxs-lookup"><span data-stu-id="5c30c-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="5c30c-112">Siamo lieti di annunciare un nuovo centro notifiche unificato ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!</span><span class="sxs-lookup"><span data-stu-id="5c30c-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Centro notifiche nel centro Microsoft 365 sicurezza":::

<span data-ttu-id="5c30c-114">Nella tabella seguente viene confrontato il nuovo centro notifiche unificato con il centro notifiche precedente.</span><span class="sxs-lookup"><span data-stu-id="5c30c-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="5c30c-115">Il nuovo centro notifiche unificato</span><span class="sxs-lookup"><span data-stu-id="5c30c-115">The new, unified Action center</span></span>  |<span data-ttu-id="5c30c-116">Centro notifiche precedente</span><span class="sxs-lookup"><span data-stu-id="5c30c-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="5c30c-117">Elenca le azioni in sospeso e completate per i dispositivi e la posta elettronica in un'unica posizione</span><span class="sxs-lookup"><span data-stu-id="5c30c-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="5c30c-118">([Microsoft Defender per Endpoint](microsoft-defender-endpoint.md) più Microsoft Defender per [Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="5c30c-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="5c30c-119">Elenca le azioni in sospeso e completate per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="5c30c-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="5c30c-120">([Solo Microsoft Defender per Endpoint)](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="5c30c-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="5c30c-121">Si trova in:</span><span class="sxs-lookup"><span data-stu-id="5c30c-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="5c30c-122">Si trova in:</span><span class="sxs-lookup"><span data-stu-id="5c30c-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="5c30c-123">Nel centro Microsoft 365 sicurezza scegliere **Centro notifiche.**</span><span class="sxs-lookup"><span data-stu-id="5c30c-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Passaggio al Centro notifiche nel centro sicurezza Microsoft 365 sicurezza"::: | <span data-ttu-id="5c30c-125">Nel riquadro Microsoft Defender Security Center, scegliere **Analisi automatizzate**  >  **Centro notifiche.**</span><span class="sxs-lookup"><span data-stu-id="5c30c-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Spostamento nel centro notifiche dalla Microsoft Defender Security Center":::  |

<span data-ttu-id="5c30c-127">Il centro notifiche unificato riunisce le azioni di correzione in Defender for Endpoint e Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c30c-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="5c30c-128">Definisce un linguaggio comune per tutte le azioni di correzione e offre un'esperienza di indagine unificata.</span><span class="sxs-lookup"><span data-stu-id="5c30c-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="5c30c-129">È possibile utilizzare il centro notifiche unificato se si dispone delle autorizzazioni appropriate e di una o più delle sottoscrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c30c-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="5c30c-130">Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c30c-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="5c30c-131">Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="5c30c-131">Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="5c30c-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c30c-132">Microsoft 365 Defender</span></span>](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="5c30c-133">Per ulteriori informazioni, vedere [Requisiti](/microsoft-365/security/mtp/prerequisites).</span><span class="sxs-lookup"><span data-stu-id="5c30c-133">To learn more, see [Requirements](/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="5c30c-134">Utilizzo del centro notifiche</span><span class="sxs-lookup"><span data-stu-id="5c30c-134">Using the Action center</span></span>

<span data-ttu-id="5c30c-135">Per accedere al centro notifiche unificato nel centro sicurezza Microsoft 365 sicurezza:</span><span class="sxs-lookup"><span data-stu-id="5c30c-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="5c30c-136">Accedere al centro Microsoft 365 sicurezza ( [https://security.microsoft.com](https://security.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5c30c-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="5c30c-137">Nel riquadro di spostamento selezionare **Centro notifiche.**</span><span class="sxs-lookup"><span data-stu-id="5c30c-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="5c30c-138">Quando si visita il centro notifiche, vengono visualizzate due schede: **Azioni in sospeso** e **Cronologia.**</span><span class="sxs-lookup"><span data-stu-id="5c30c-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="5c30c-139">Nella tabella seguente sono riepilogati gli elementi che verranno visualizzati in ogni scheda:</span><span class="sxs-lookup"><span data-stu-id="5c30c-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="5c30c-140">Scheda</span><span class="sxs-lookup"><span data-stu-id="5c30c-140">Tab</span></span>  |<span data-ttu-id="5c30c-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c30c-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5c30c-142">**In sospeso**</span><span class="sxs-lookup"><span data-stu-id="5c30c-142">**Pending**</span></span>     | <span data-ttu-id="5c30c-143">Visualizza un elenco di azioni che richiedono attenzione.</span><span class="sxs-lookup"><span data-stu-id="5c30c-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="5c30c-144">È possibile approvare o rifiutare le azioni una alla volta oppure selezionare più azioni se hanno lo stesso tipo di azione ( ad esempio **File quarantena**).</span><span class="sxs-lookup"><span data-stu-id="5c30c-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="5c30c-145">**SUGGERIMENTO:** verificare e approvare [(o rifiutare)](manage-auto-investigation.md) le azioni in sospeso il prima possibile in modo che le indagini automatizzate possano essere completate in modo rapido.</span><span class="sxs-lookup"><span data-stu-id="5c30c-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="5c30c-146">**Cronologia**</span><span class="sxs-lookup"><span data-stu-id="5c30c-146">**History**</span></span>     | <span data-ttu-id="5c30c-147">Funge da log di controllo per le azioni eseguite, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5c30c-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="5c30c-148">- Azioni correttive intraprese a seguito di indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="5c30c-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="5c30c-149">- Azioni di correzione approvate dal team delle operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5c30c-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="5c30c-150">- Comandi eseguiti e azioni di correzione applicate durante le sessioni di Live Response</span><span class="sxs-lookup"><span data-stu-id="5c30c-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="5c30c-151">- Azioni di correzione eseguite dalle funzionalità di protezione dalle minacce in Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5c30c-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="5c30c-152">Consente di annullare determinate azioni (vedere [Annullare le azioni completate).](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="5c30c-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="5c30c-153">È possibile personalizzare, ordinare, filtrare ed esportare i dati nel centro notifiche.</span><span class="sxs-lookup"><span data-stu-id="5c30c-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Colonne e filtri nel centro notifiche":::

- <span data-ttu-id="5c30c-155">Selezionare un'intestazione di colonna per ordinare gli elementi in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="5c30c-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="5c30c-156">Utilizzare il filtro periodo di tempo per visualizzare i dati relativi al giorno, alla settimana, ai 30 giorni o ai 6 mesi precedenti.</span><span class="sxs-lookup"><span data-stu-id="5c30c-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="5c30c-157">Scegliere le colonne che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="5c30c-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="5c30c-158">Specificare il numero di elementi da includere in ogni pagina di dati.</span><span class="sxs-lookup"><span data-stu-id="5c30c-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="5c30c-159">Utilizzare i filtri per visualizzare solo gli elementi che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="5c30c-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="5c30c-160">Selezionare **Esporta** per esportare i risultati in .csv file.</span><span class="sxs-lookup"><span data-stu-id="5c30c-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="5c30c-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5c30c-161">Next steps</span></span>

- [<span data-ttu-id="5c30c-162">Visualizzare e approvare le azioni correttive</span><span class="sxs-lookup"><span data-stu-id="5c30c-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="5c30c-163">Vedere la guida interattiva: Analizzare e correggere le minacce con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c30c-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="5c30c-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c30c-164">See also</span></span>

- [<span data-ttu-id="5c30c-165">Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c30c-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
