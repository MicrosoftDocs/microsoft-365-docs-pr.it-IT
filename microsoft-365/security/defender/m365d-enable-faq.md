---
title: Domande frequenti quando si accende Microsoft 365 Defender
description: Risposte alle domande più frequenti su licenze, autorizzazioni, impostazioni iniziali e altri prodotti e servizi relativi all'abilitazione di Microsoft 365 Defender
keywords: domande frequenti, domande frequenti, GCC, iniziare, abilitare Microsoft 365 Defender, Microsoft 365 Defender, M365, sicurezza, posizione dei dati, autorizzazioni richieste, idoneità alla licenza, pagina delle impostazioni
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572766"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="68970-104">Domande frequenti quando si accende Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68970-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="68970-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="68970-105">**Applies to:**</span></span>
- <span data-ttu-id="68970-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68970-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="68970-107">Leggere le risposte alle domande più frequenti sull'attivazione di [Microsoft 365 Defender](microsoft-365-defender.md), incluse le licenze e le autorizzazioni necessarie, la distribuzione dei servizi di supporto e le impostazioni iniziali.</span><span class="sxs-lookup"><span data-stu-id="68970-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="68970-108">Per istruzioni su come attivare il servizio, [vedere Attivare Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="68970-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="68970-109">Non ho una licenza Microsoft 365 E5 licenza.</span><span class="sxs-lookup"><span data-stu-id="68970-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="68970-110">Posso ancora usare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="68970-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="68970-111">I clienti con le seguenti licenze non E5 possono utilizzare Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="68970-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="68970-112">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="68970-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="68970-113">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="68970-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="68970-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="68970-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="68970-115">Defender per Office 365 (Piano 2)</span><span class="sxs-lookup"><span data-stu-id="68970-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="68970-116">Per un elenco completo delle licenze supportate, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="68970-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="68970-117">Devo installare o distribuire qualcosa per iniziare a usare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="68970-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="68970-118">No, Microsoft 365 Defender consolida i dati Microsoft 365 servizi di sicurezza che hai già distribuito.</span><span class="sxs-lookup"><span data-stu-id="68970-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="68970-119">Una volta attivata, le esperienze di incidente, automazione e caccia inizieranno a funzionare nell'ambito dei prodotti distribuiti.</span><span class="sxs-lookup"><span data-stu-id="68970-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="68970-120">Se nessuno di questi prodotti è distribuito correttamente, Microsoft 365 Defender non visualizza dati e non è in grado di intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="68970-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="68970-121">Per ottimizzare le esperienze Microsoft 365 Defender, è consigliabile distribuire tutti i *prodotti e* i servizi [Microsoft 365 sicurezza supportati.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="68970-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="68970-122">Dove Microsoft 365 Defender e memorizza i miei dati?</span><span class="sxs-lookup"><span data-stu-id="68970-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="68970-123">Microsoft 365 Defender seleziona automaticamente una posizione ottimale per il data center in cui vengono elaborati e archiviati i dati consolidati.</span><span class="sxs-lookup"><span data-stu-id="68970-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="68970-124">Se si dispone di Microsoft Defender for Endpoint, viene selezionata la stessa posizione utilizzata da Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="68970-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="68970-125">Microsoft Defender for Endpoint viene automaticamente azuree nei data center dell'Unione Europea (UE) quando viene attivato tramite Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="68970-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="68970-126">Microsoft 365 Defender verrà es provisioning automatico nello stesso data center UE per i clienti che hanno e provisioning di Microsoft Defender per Endpoint in questo modo.</span><span class="sxs-lookup"><span data-stu-id="68970-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="68970-127">La posizione del data center viene visualizzata prima e dopo il provisioning del servizio nella pagina delle impostazioni per Microsoft 365 Defender (**Impostazioni > Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="68970-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="68970-128">Se si preferisce usare un'altra posizione del data center, **selezionare Serve assistenza nel** centro Microsoft 365 sicurezza per contattare il supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68970-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="68970-129">Dove posso accedere a Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="68970-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="68970-130">Microsoft 365 Defender è disponibile nel Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="68970-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="68970-131">Per passare al Centro sicurezza, passare all'URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="68970-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="68970-132">Quali autorizzazioni sono necessarie per accedere a Defender Microsoft 365 nel centro Microsoft 365 sicurezza?</span><span class="sxs-lookup"><span data-stu-id="68970-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="68970-133">Gli account assegnati ai ruoli Azure Active Directory di controllo (Azure AD) possono accedere Microsoft 365 funzionalità e ai dati di Defender:</span><span class="sxs-lookup"><span data-stu-id="68970-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="68970-134">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="68970-134">Global administrator</span></span>
- <span data-ttu-id="68970-135">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="68970-135">Security administrator</span></span>
- <span data-ttu-id="68970-136">Operatore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="68970-136">Security Operator</span></span>
- <span data-ttu-id="68970-137">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="68970-137">Global Reader</span></span>
- <span data-ttu-id="68970-138">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="68970-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="68970-139">Le impostazioni di controllo degli accessi basate sui ruoli in Microsoft Defender for Endpoint influenzano l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="68970-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="68970-140">Per ulteriori informazioni, vedere Managing [Access to Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="68970-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="68970-141">A quale fuso orario Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="68970-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="68970-142">Per impostazione predefinita, Microsoft 365 Defender visualizza le informazioni sull'ora nel fuso orario UTC.</span><span class="sxs-lookup"><span data-stu-id="68970-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="68970-143">È possibile modificare questa impostazione per utilizzare il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="68970-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="68970-144">Informazioni sull'impostazione del fuso orario</span><span class="sxs-lookup"><span data-stu-id="68970-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="68970-145">Come posso conoscere i nuovi aggiornamenti delle funzionalità Microsoft 365 Defender e dell'interfaccia utente?</span><span class="sxs-lookup"><span data-stu-id="68970-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="68970-146">Microsoft fornisce regolarmente informazioni attraverso i vari canali, tra cui:</span><span class="sxs-lookup"><span data-stu-id="68970-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="68970-147">Centro [messaggi nell'Microsoft 365](../../admin/manage/message-center.md) di amministrazione</span><span class="sxs-lookup"><span data-stu-id="68970-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="68970-148">Blogpost nella community tecnologica [Microsoft 365 sicurezza & conformità](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="68970-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="68970-149">Ottieni le esperienze più recenti disponibili pubblicamente attivando le funzionalità [di anteprima](preview.md).</span><span class="sxs-lookup"><span data-stu-id="68970-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="68970-150">Microsoft 365 Defender è disponibile per i Government Community Cloud (GCC) o GCC High?</span><span class="sxs-lookup"><span data-stu-id="68970-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="68970-151">Al momento non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="68970-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="68970-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="68970-152">Related topics</span></span>

- [<span data-ttu-id="68970-153">Microsoft 365 Panoramica di Defender</span><span class="sxs-lookup"><span data-stu-id="68970-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="68970-154">[Attivare Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="68970-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="68970-155">Requisiti relativi alle licenze e altri prerequisiti</span><span class="sxs-lookup"><span data-stu-id="68970-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="68970-156">Distribuire i servizi supportati</span><span class="sxs-lookup"><span data-stu-id="68970-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="68970-157">Attivare funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="68970-157">Turn on preview features</span></span>](preview.md)
