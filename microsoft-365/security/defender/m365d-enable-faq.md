---
title: Domande frequenti sull'attivazione di Microsoft 365 Defender
description: Risposte alle domande più frequenti su licenze, autorizzazioni, impostazioni iniziali e altri prodotti e servizi correlati all'abilitazione di Microsoft 365 Defender
keywords: domande frequenti, domande frequenti, GCC, introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, posizione dei dati, autorizzazioni necessarie, idoneità alla licenza, pagina delle impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7482bf614e7cb3ffad6596f3c5d8bc554d46d912
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068650"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="d9d05-104">Domande frequenti sull'attivazione di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9d05-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d9d05-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d9d05-105">**Applies to:**</span></span>
- <span data-ttu-id="d9d05-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9d05-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d9d05-107">Leggere le risposte alle domande più frequenti sull'attivazione di [Microsoft 365 Defender,](microsoft-365-defender.md)incluse le licenze e le autorizzazioni necessarie, la distribuzione dei servizi di supporto e le impostazioni iniziali.</span><span class="sxs-lookup"><span data-stu-id="d9d05-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="d9d05-108">Per istruzioni su come attivare il servizio, [vedere Attivare Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="d9d05-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="d9d05-109">Non ho una licenza di Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d9d05-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="d9d05-110">Posso ancora usare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d9d05-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="d9d05-111">I clienti con le seguenti licenze non E5 possono usare Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="d9d05-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="d9d05-112">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d9d05-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="d9d05-113">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="d9d05-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="d9d05-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d9d05-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="d9d05-115">Defender per Office 365 (Piano 2)</span><span class="sxs-lookup"><span data-stu-id="d9d05-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="d9d05-116">Per un elenco completo delle licenze supportate, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="d9d05-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="d9d05-117">Devo installare o distribuire qualsiasi elemento per iniziare a usare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d9d05-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="d9d05-118">No, Microsoft 365 Defender consolida i dati dei servizi di sicurezza di Microsoft 365 già distribuiti.</span><span class="sxs-lookup"><span data-stu-id="d9d05-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="d9d05-119">Dopo l'attivazione, le esperienze di evento imprevisto, automazione ed attività di ricerca inizieranno a funzionare nell'ambito dei prodotti distribuiti.</span><span class="sxs-lookup"><span data-stu-id="d9d05-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="d9d05-120">Se nessuno di questi prodotti viene distribuito correttamente, Microsoft 365 Defender non visualizza alcun dato e non è in grado di eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d9d05-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="d9d05-121">Per ottimizzare le esperienze di Microsoft 365 Defender, è consigliabile distribuire tutti i prodotti e i servizi di sicurezza [di Microsoft 365 supportati.](deploy-supported-services.md) </span><span class="sxs-lookup"><span data-stu-id="d9d05-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="d9d05-122">Dove microsoft 365 Defender elabora e archivia i miei dati?</span><span class="sxs-lookup"><span data-stu-id="d9d05-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="d9d05-123">Microsoft 365 Defender seleziona automaticamente una posizione ottimale per il data center in cui vengono elaborati e archiviati i dati consolidati.</span><span class="sxs-lookup"><span data-stu-id="d9d05-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="d9d05-124">Se hai Microsoft Defender per Endpoint, seleziona la stessa posizione usata da Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d9d05-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="d9d05-125">Microsoft Defender for Endpoint effettua automaticamente il provisioning nei data center dell'Unione Europea (UE) quando è attivato tramite Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="d9d05-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="d9d05-126">Microsoft 365 Defender eseguirà automaticamente il provisioning nello stesso data center ue per i clienti che hanno effettuato il provisioning di Microsoft Defender per Endpoint in questo modo.</span><span class="sxs-lookup"><span data-stu-id="d9d05-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="d9d05-127">La posizione del data center viene visualizzata prima e dopo il provisioning del servizio nella pagina delle impostazioni di Microsoft 365 Defender (**Impostazioni > Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="d9d05-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="d9d05-128">Se si preferisce utilizzare un'altra posizione del data center, selezionare Serve **assistenza?** nel Centro sicurezza Microsoft 365 per contattare il supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d9d05-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="d9d05-129">Dove è possibile accedere a Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d9d05-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="d9d05-130">Microsoft 365 Defender è disponibile nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9d05-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="d9d05-131">Per accedere al Centro sicurezza, passare all'URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="d9d05-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="d9d05-132">Quali autorizzazioni sono necessarie per accedere a Microsoft 365 Defender nel Centro sicurezza Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="d9d05-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="d9d05-133">Gli account assegnati ai ruoli di Azure Active Directory (AD) seguenti possono accedere ai dati e alle funzionalità di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="d9d05-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="d9d05-134">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="d9d05-134">Global administrator</span></span>
- <span data-ttu-id="d9d05-135">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d9d05-135">Security administrator</span></span>
- <span data-ttu-id="d9d05-136">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="d9d05-136">Security Operator</span></span>
- <span data-ttu-id="d9d05-137">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="d9d05-137">Global Reader</span></span>
- <span data-ttu-id="d9d05-138">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d9d05-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="d9d05-139">Le impostazioni di controllo dell'accesso basato sui ruoli in Microsoft Defender for Endpoint influiscono sull'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="d9d05-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="d9d05-140">Per ulteriori informazioni, vedere gestione [dell'accesso a Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d9d05-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="d9d05-141">Qual è il fuso orario predefinito di Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="d9d05-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="d9d05-142">Per impostazione predefinita, Microsoft 365 Defender visualizza le informazioni sull'ora nel fuso orario UTC.</span><span class="sxs-lookup"><span data-stu-id="d9d05-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="d9d05-143">Puoi modificare questa impostazione per usare il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="d9d05-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="d9d05-144">Informazioni sull'impostazione del fuso orario</span><span class="sxs-lookup"><span data-stu-id="d9d05-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="d9d05-145">Come posso ottenere informazioni sulle nuove funzionalità di Microsoft 365 Defender e sugli aggiornamenti dell'interfaccia utente?</span><span class="sxs-lookup"><span data-stu-id="d9d05-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="d9d05-146">Microsoft fornisce regolarmente informazioni attraverso i vari canali, tra cui:</span><span class="sxs-lookup"><span data-stu-id="d9d05-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="d9d05-147">Centro [messaggi nell'interfaccia](../../admin/manage/message-center.md) di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9d05-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="d9d05-148">Blogpost nella community tecnica sulla sicurezza di [Microsoft 365 & conformità](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="d9d05-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="d9d05-149">Ottieni le esperienze più recenti disponibili pubblicamente attivando le [funzionalità di anteprima.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="d9d05-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="d9d05-150">Microsoft 365 Defender è disponibile per US Government Community Cloud (GCC) o GCC High?</span><span class="sxs-lookup"><span data-stu-id="d9d05-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="d9d05-151">Al momento non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d9d05-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9d05-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d9d05-152">Related topics</span></span>

- [<span data-ttu-id="d9d05-153">Panoramica di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9d05-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="d9d05-154">[Attivare Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="d9d05-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="d9d05-155">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d9d05-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="d9d05-156">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="d9d05-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="d9d05-157">Attivare funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="d9d05-157">Turn on preview features</span></span>](preview.md)
