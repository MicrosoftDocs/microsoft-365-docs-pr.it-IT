---
title: Integrazione di Cortana con Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: "Informazioni su come utilizzare Cortana, quando è integrato con Office 365. È possibile disattivare Cortana nell'interfaccia di amministrazione per limitare l'accesso ai dati dell'organizzazione. "
ms.openlocfilehash: 8f20c9b96ee57dcdf5da99dc08ffeb72465bc515
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361437"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="207f5-104">Cortana in Office 365</span><span class="sxs-lookup"><span data-stu-id="207f5-104">Cortana in Office 365</span></span>

<span data-ttu-id="207f5-105">Cortana è un assistente digitale basato sul cloud e il servizio Microsoft 365 e Office 365 che funziona su tutti i dispositivi e i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="207f5-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="207f5-106">Cortana è in grado di utilizzare le informazioni archiviate in Microsoft 365 e Office 365 per consentire agli utenti dell'organizzazione di rimanere sempre aggiornati e di ottenere approfondimenti, attività consigliate e assistenza per le riunioni, i documenti e i contatti.</span><span class="sxs-lookup"><span data-stu-id="207f5-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="207f5-107">Info per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="207f5-107">Info for admins</span></span>

<span data-ttu-id="207f5-108">La conformità è un impegno che Microsoft apporta ai clienti aziendali.</span><span class="sxs-lookup"><span data-stu-id="207f5-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="207f5-109">Per ulteriori informazioni, vedere Microsoft Compliance Framework.</span><span class="sxs-lookup"><span data-stu-id="207f5-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="207f5-110">Compatibilmente con gli altri servizi Microsoft 365 e Office 365, le funzionalità Cortana conformi sono protette e assicurate, soggette alle condizioni dei servizi online che includono una serie di promesse che coinvolgono la protezione dei dati degli utenti da perdite accidentali, alterazioni, Disclosure o accessi non autorizzati o distruzione illecita.</span><span class="sxs-lookup"><span data-stu-id="207f5-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="207f5-111">Tutte le altre funzionalità di Cortana (ad esempio, i servizi connessi opzionali di Cortana) sono soggette al [contratto dei servizi Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=2109174) e all' [informativa sulla privacy di Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span><span class="sxs-lookup"><span data-stu-id="207f5-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="207f5-112">I servizi di Cortana sono suddivisi in due categorie di dati, **conformi** e **servizi connessi facoltativi**, che è possibile controllare.</span><span class="sxs-lookup"><span data-stu-id="207f5-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="207f5-113">Disattiva servizi connessi opzionali di Cortana</span><span class="sxs-lookup"><span data-stu-id="207f5-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="207f5-114">Cortana i servizi connessi opzionali possono essere disattivati per i dipendenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="207f5-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="207f5-115">In questo modo vengono disabilitati i servizi connessi opzionali di Cortana in Cortana in Windows e l'app per dispositivi mobili di Cortana.</span><span class="sxs-lookup"><span data-stu-id="207f5-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="207f5-116">Questo include i promemoria, gli elenchi, le attività e altre caratteristiche di Cortana.</span><span class="sxs-lookup"><span data-stu-id="207f5-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="207f5-117">I servizi nella categoria conforme (ad esempio, Cortana OST experiences), come la posta elettronica del briefing di Cortana e la riproduzione dei messaggi di posta elettronica in Outlook Mobile, rimarranno attivi.</span><span class="sxs-lookup"><span data-stu-id="207f5-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="207f5-118">Nell' > **interfaccia di amministrazione** di Microsoft 365, **selezionare impostazioni impostazioni e**selezionare **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="207f5-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="207f5-119">Selezionare la casella di controllo per **consentire l'utilizzo delle esperienze di connessione facoltativa di Cortana per utilizzare i dati ospitati di Microsoft nell'organizzazione** per abilitare o disabilitare le esperienze collegate a Cortana</span><span class="sxs-lookup"><span data-stu-id="207f5-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="207f5-120">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="207f5-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="207f5-121">Disattiva le esperienze di Cortana OST</span><span class="sxs-lookup"><span data-stu-id="207f5-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="207f5-122">I dipendenti dell'organizzazione possono scegliere singolarmente le esperienze di Cortana OST attenendosi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="207f5-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="207f5-123">Aprire Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="207f5-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="207f5-124">Passare a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="207f5-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="207f5-125">Selezionare **Ascolta i miei messaggi di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="207f5-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="207f5-126">Spostare l'interruttore su disattivato negli account che si desidera disabilitare.</span><span class="sxs-lookup"><span data-stu-id="207f5-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="207f5-127">Informazioni di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="207f5-127">Briefing email</span></span>

<span data-ttu-id="207f5-128">La disattivazione di Cortana sulla barra delle applicazioni non disattiverà la posta elettronica del briefing di Cortana.</span><span class="sxs-lookup"><span data-stu-id="207f5-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="207f5-129">I dipendenti devono annullare la sottoscrizione singolarmente.</span><span class="sxs-lookup"><span data-stu-id="207f5-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="207f5-130">Gli utenti dell'organizzazione possono rifiutare la posta elettronica del briefing di Cortana selezionando **Annulla sottoscrizione** nel piè di pagina del messaggio.</span><span class="sxs-lookup"><span data-stu-id="207f5-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>
