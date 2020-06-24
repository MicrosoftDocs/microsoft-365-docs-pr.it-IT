---
title: Domande frequenti quando si attiva Microsoft Threat Protection
description: Ottenere le risposte alle domande più frequenti sulla gestione delle licenze, delle autorizzazioni, delle impostazioni iniziali e di altri prodotti e servizi correlati all'abilitazione di Microsoft Threat Protection
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845071"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="8f5ea-104">Domande frequenti quando si attiva Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f5ea-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

<span data-ttu-id="8f5ea-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8f5ea-105">**Applies to:**</span></span>
- <span data-ttu-id="8f5ea-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f5ea-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8f5ea-107">Leggere le risposte alle domande più frequenti relative all'attivazione di [Microsoft Threat Protection](microsoft-threat-protection.md), tra cui le licenze e le autorizzazioni necessarie, la distribuzione dei servizi di supporto e le impostazioni iniziali.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="8f5ea-108">Per istruzioni su come abilitare il servizio, [leggere attiva Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ea-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="8f5ea-109">Non si dispone di una licenza Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="8f5ea-110">È ancora possibile utilizzare Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="8f5ea-111">I clienti con le seguenti licenze non E5 possono utilizzare Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="8f5ea-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="8f5ea-112">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f5ea-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="8f5ea-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f5ea-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="8f5ea-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8f5ea-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="8f5ea-115">Protezione avanzata dalle minacce di Office 365 (piano 2)</span><span class="sxs-lookup"><span data-stu-id="8f5ea-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="8f5ea-116">Per un elenco completo delle licenze supportate, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="8f5ea-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="8f5ea-117">È necessario installare o distribuire qualsiasi cosa per iniziare a utilizzare Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="8f5ea-118">No, Microsoft Threat Protection consolida i dati dai servizi di sicurezza di Microsoft 365 che sono già stati distribuiti.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="8f5ea-119">Una volta attivati, gli eventi incidentati, di automazione e di caccia inizieranno a funzionare nell'ambito dei prodotti distribuiti.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="8f5ea-120">Se nessuno di questi prodotti è stato distribuito correttamente, Microsoft Threat Protection non visualizzerà alcun dato e non sarà in grado di intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="8f5ea-121">Per ottimizzare le esperienze di Microsoft Threat Protection, è consigliabile distribuire *tutti i* [prodotti e servizi di sicurezza di Microsoft 365](deploy-supported-services.md)supportati.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="8f5ea-122">Dove viene trattato Microsoft Threat Protection e archiviare i dati personali?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="8f5ea-123">Microsoft Threat Protection seleziona automaticamente una posizione ottimale per il Data Center in cui vengono elaborati e archiviati i dati consolidati.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="8f5ea-124">Se si dispone di Microsoft Defender ATP, seleziona lo stesso percorso utilizzato da Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="8f5ea-125">Microsoft Defender ATP accantona automaticamente i data center dell'Unione europea (EU) quando viene attivato tramite il Centro sicurezza di Azure.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="8f5ea-126">Microsoft Threat Protection provisionerà automaticamente nello stesso data center dell'Unione europea per i clienti che hanno eseguito il provisioning di Microsoft Defender ATP in questo modo.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="8f5ea-127">La posizione del Data Center viene visualizzata prima e dopo il provisioning del servizio nella pagina impostazioni di Microsoft Threat Protection (**impostazioni > Microsoft Threat Protection**).</span><span class="sxs-lookup"><span data-stu-id="8f5ea-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="8f5ea-128">Se si preferisce utilizzare un altro percorso Data Center, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365 per contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="8f5ea-129">Dove è possibile accedere a Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="8f5ea-130">Microsoft Threat Protection è disponibile in Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="8f5ea-131">Per accedere al centro sicurezza, passare all'URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="8f5ea-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="8f5ea-132">Quali autorizzazioni sono necessarie per accedere a Microsoft Threat Protection in Microsoft 365 Security Center?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="8f5ea-133">Gli account assegnati ai seguenti ruoli di Azure Active Directory (AD) possono accedere alle funzionalità e ai dati di Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="8f5ea-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="8f5ea-134">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="8f5ea-134">Global administrator</span></span>
- <span data-ttu-id="8f5ea-135">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="8f5ea-135">Security administrator</span></span>
- <span data-ttu-id="8f5ea-136">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="8f5ea-136">Security Operator</span></span>
- <span data-ttu-id="8f5ea-137">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="8f5ea-137">Global Reader</span></span>
- <span data-ttu-id="8f5ea-138">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="8f5ea-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="8f5ea-139">Le impostazioni del controllo di accesso basato sui ruoli in Microsoft Defender ATP influiscono sull'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="8f5ea-140">Per ulteriori informazioni, vedere [gestione dell'accesso a Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ea-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="8f5ea-141">A quale fuso orario è impostato il valore predefinito di Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="8f5ea-142">Per impostazione predefinita, Microsoft Threat Protection Visualizza le informazioni sull'ora nel fuso orario UTC.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="8f5ea-143">È possibile modificare questa impostazione per utilizzare il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="8f5ea-144">Informazioni su come impostare il fuso orario</span><span class="sxs-lookup"><span data-stu-id="8f5ea-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="8f5ea-145">Come è possibile conoscere le nuove funzionalità di Microsoft Threat Protection e gli aggiornamenti dell'interfaccia utente?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="8f5ea-146">Microsoft fornisce periodicamente informazioni tramite i diversi canali, tra cui:</span><span class="sxs-lookup"><span data-stu-id="8f5ea-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="8f5ea-147">[Centro messaggi](../../admin/manage/message-center.md) nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f5ea-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="8f5ea-148">Blogposts in [Microsoft 365 security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="8f5ea-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="8f5ea-149">Ottenere le ultime esperienze disponibili pubblicamente attivando le [funzionalità di anteprima](preview.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ea-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="8f5ea-150">Microsoft Threat Protection è disponibile per US Government Community Cloud (GCC) o GCC High?</span><span class="sxs-lookup"><span data-stu-id="8f5ea-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="8f5ea-151">Al momento non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="8f5ea-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f5ea-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8f5ea-152">Related topics</span></span>

- [<span data-ttu-id="8f5ea-153">Panoramica di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f5ea-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="8f5ea-154">[Attiva Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="8f5ea-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="8f5ea-155">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8f5ea-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="8f5ea-156">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="8f5ea-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="8f5ea-157">Abilitare le funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="8f5ea-157">Turn on preview features</span></span>](preview.md)