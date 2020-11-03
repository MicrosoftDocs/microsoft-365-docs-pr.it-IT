---
title: Domande frequenti quando si attiva Microsoft 365 Defender
description: Ottenere le risposte alle domande più frequenti sulla gestione delle licenze, delle autorizzazioni, delle impostazioni iniziali e di altri prodotti e servizi correlati all'abilitazione di Microsoft 365 Defender
keywords: domande frequenti, FAQ, GCC, introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, percorso dati, autorizzazioni necessarie, idoneità licenza, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842417"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="f44a7-104">Domande frequenti quando si attiva Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f44a7-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f44a7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f44a7-105">**Applies to:**</span></span>
- <span data-ttu-id="f44a7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f44a7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f44a7-107">Leggere le risposte alle domande più frequenti relative all'attivazione di [Microsoft 365 Defender](microsoft-threat-protection.md), tra cui le licenze e le autorizzazioni necessarie, la distribuzione dei servizi di supporto e le impostazioni iniziali.</span><span class="sxs-lookup"><span data-stu-id="f44a7-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="f44a7-108">Per istruzioni su come abilitare il servizio, [leggere attiva Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f44a7-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="f44a7-109">Non si dispone di una licenza Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f44a7-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="f44a7-110">È ancora possibile utilizzare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f44a7-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="f44a7-111">I clienti con le seguenti licenze non E5 possono utilizzare Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f44a7-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="f44a7-112">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f44a7-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f44a7-113">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="f44a7-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="f44a7-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f44a7-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f44a7-115">Difensore per Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="f44a7-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="f44a7-116">Per un elenco completo delle licenze supportate, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f44a7-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="f44a7-117">È necessario installare o distribuire qualsiasi cosa per iniziare a utilizzare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f44a7-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="f44a7-118">No, Microsoft 365 Defender consolida i dati dai servizi di sicurezza di Microsoft 365 che sono già stati distribuiti.</span><span class="sxs-lookup"><span data-stu-id="f44a7-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="f44a7-119">Una volta attivati, gli eventi incidentati, di automazione e di caccia inizieranno a funzionare nell'ambito dei prodotti distribuiti.</span><span class="sxs-lookup"><span data-stu-id="f44a7-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="f44a7-120">Se nessuno di questi prodotti è stato distribuito correttamente, Microsoft 365 Defender non visualizzerà alcun dato e non sarà in grado di intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="f44a7-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="f44a7-121">Per ottimizzare le esperienze di Microsoft 365 Defender, è consigliabile distribuire *tutti i* [prodotti e servizi di sicurezza di Microsoft 365](deploy-supported-services.md)supportati.</span><span class="sxs-lookup"><span data-stu-id="f44a7-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="f44a7-122">Dove Microsoft 365 Defender elabora e archivia i dati personali?</span><span class="sxs-lookup"><span data-stu-id="f44a7-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="f44a7-123">Microsoft 365 Defender seleziona automaticamente una posizione ottimale per il Data Center in cui vengono elaborati e archiviati i dati consolidati.</span><span class="sxs-lookup"><span data-stu-id="f44a7-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="f44a7-124">Se si dispone di Microsoft Defender per endpoint, viene selezionato lo stesso percorso utilizzato da Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="f44a7-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="f44a7-125">Microsoft Defender per endpoint si riattiva automaticamente nei data center dell'Unione europea (EU) quando viene attivato tramite Azure Defender \*.</span><span class="sxs-lookup"><span data-stu-id="f44a7-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender\*.</span></span> <span data-ttu-id="f44a7-126">Microsoft 365 Defender provvederà alla provisioning automatico nello stesso data center EU per i clienti che hanno sottoposto a Microsoft Defender per endpoint in questo modo.</span><span class="sxs-lookup"><span data-stu-id="f44a7-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="f44a7-127">La posizione del Data Center viene visualizzata prima e dopo il provisioning del servizio nella pagina impostazioni di Microsoft 365 Defender ( **impostazioni > microsoft 365 Defender** ).</span><span class="sxs-lookup"><span data-stu-id="f44a7-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="f44a7-128">Se si preferisce utilizzare un altro percorso Data Center, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365 per contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f44a7-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="f44a7-129">Dove è possibile accedere a Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f44a7-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="f44a7-130">Microsoft 365 Defender è disponibile in Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="f44a7-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="f44a7-131">Per accedere al centro sicurezza, passare all'URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="f44a7-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="f44a7-132">Quali autorizzazioni sono necessarie per accedere a Microsoft 365 Defender in Microsoft 365 Security Center?</span><span class="sxs-lookup"><span data-stu-id="f44a7-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="f44a7-133">Gli account assegnati ai seguenti ruoli di Azure Active Directory (AD) possono accedere alla funzionalità e ai dati di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f44a7-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="f44a7-134">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="f44a7-134">Global administrator</span></span>
- <span data-ttu-id="f44a7-135">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f44a7-135">Security administrator</span></span>
- <span data-ttu-id="f44a7-136">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f44a7-136">Security Operator</span></span>
- <span data-ttu-id="f44a7-137">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="f44a7-137">Global Reader</span></span>
- <span data-ttu-id="f44a7-138">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="f44a7-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="f44a7-139">Le impostazioni del controllo di accesso basato sui ruoli in Microsoft Defender per endpoint influiscono sull'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="f44a7-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="f44a7-140">Per ulteriori informazioni, vedere [Managing Access to Microsoft 365 Defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f44a7-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="f44a7-141">A quale fuso orario è impostato il valore predefinito di Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f44a7-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="f44a7-142">Per impostazione predefinita, Microsoft 365 Defender Visualizza le informazioni sull'ora nel fuso orario UTC.</span><span class="sxs-lookup"><span data-stu-id="f44a7-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="f44a7-143">È possibile modificare questa impostazione per utilizzare il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="f44a7-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="f44a7-144">Informazioni su come impostare il fuso orario</span><span class="sxs-lookup"><span data-stu-id="f44a7-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="f44a7-145">Come è possibile conoscere le nuove funzionalità di Microsoft 365 Defender e gli aggiornamenti dell'interfaccia utente?</span><span class="sxs-lookup"><span data-stu-id="f44a7-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="f44a7-146">Microsoft fornisce periodicamente informazioni tramite i diversi canali, tra cui:</span><span class="sxs-lookup"><span data-stu-id="f44a7-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="f44a7-147">[Centro messaggi](../../admin/manage/message-center.md) nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f44a7-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="f44a7-148">Blogposts in [Microsoft 365 security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="f44a7-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="f44a7-149">Ottenere le ultime esperienze disponibili pubblicamente attivando le [funzionalità di anteprima](preview.md).</span><span class="sxs-lookup"><span data-stu-id="f44a7-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="f44a7-150">Microsoft 365 Defender è disponibile per US Government community Cloud (GCC) o GCC High?</span><span class="sxs-lookup"><span data-stu-id="f44a7-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="f44a7-151">Al momento non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f44a7-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f44a7-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f44a7-152">Related topics</span></span>

- [<span data-ttu-id="f44a7-153">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f44a7-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="f44a7-154">[Attiva Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f44a7-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="f44a7-155">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f44a7-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="f44a7-156">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="f44a7-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="f44a7-157">Attivare funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="f44a7-157">Turn on preview features</span></span>](preview.md)
