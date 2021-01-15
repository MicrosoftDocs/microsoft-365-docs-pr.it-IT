---
title: Iniziare a usare la formazione di simulazione di attacco
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare la formazione di simulazione di attacco per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 piano 2.
ms.openlocfilehash: 9d97816edf7d59c002658fc8bb3f39e72dbc2430
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871245"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="6ba7e-103">Iniziare a usare la formazione di simulazione di attacco</span><span class="sxs-lookup"><span data-stu-id="6ba7e-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6ba7e-104">Se l'organizzazione dispone di Microsoft 365 E5 o Microsoft Defender per Office 365 piano 2, che include le [funzionalità di ricerca e di risposta alle minacce](office-365-ti.md), è possibile utilizzare la formazione di simulazione di attacco nel centro protezione Microsoft per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="6ba7e-105">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="6ba7e-106">Leggere questo articolo per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="6ba7e-107">L'allenamento di simulazione di attacco sostituisce la vecchia esperienza di attacco simulatore v1 descritta in [Attack Simulator in Microsoft Defender per Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6ba7e-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6ba7e-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6ba7e-109">Per aprire il Centro sicurezza Microsoft, andare a <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="6ba7e-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="6ba7e-110">La formazione sulla simulazione degli attacchi è disponibile all'addestramento per la simulazione di attacchi di **posta elettronica e collaborazione** \> .</span><span class="sxs-lookup"><span data-stu-id="6ba7e-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="6ba7e-111">Per accedere direttamente all'addestramento di simulazione di attacco, Apri <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="6ba7e-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="6ba7e-112">Per ulteriori informazioni sulla disponibilità della formazione sulla simulazione degli attacchi tra diverse sottoscrizioni di Microsoft 365, vedere [Descrizione del servizio Microsoft Defender per Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="6ba7e-113">Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni nel centro sicurezza & Compliance o in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="6ba7e-114">In particolare, è necessario essere membri della **gestione dell'organizzazione**, dell' **amministratore della sicurezza** o di uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ba7e-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="6ba7e-115">**Amministratori di simulatori di attacco**: creare e gestire tutti gli aspetti delle campagne di simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="6ba7e-116">**Autori di payload Attack Simulator**: creare payload di attacco che un amministratore può avviare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="6ba7e-117">Per ulteriori informazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) o [About admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="6ba7e-118">Non sono disponibili i cmdlet di PowerShell corrispondenti per la formazione sulla simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="6ba7e-119">I dati relativi alla simulazione e all'addestramento degli attacchi vengono archiviati con altri dati dei clienti per i servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="6ba7e-120">Per ulteriori informazioni, vedere [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="6ba7e-121">La simulazione di attacco non è attualmente disponibile nelle seguenti aree: PSC, NOR, UAE, ZAF, GER, BRA e che.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="6ba7e-122">Simulazioni</span><span class="sxs-lookup"><span data-stu-id="6ba7e-122">Simulations</span></span>

<span data-ttu-id="6ba7e-123">Il *phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni sensibili nei messaggi che sembrano provenire da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="6ba7e-124">Il *phishing* è parte di un sottoinsieme di tecniche che vengono classificate come _Social Engineering_.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="6ba7e-125">Nell'esercitazione sulla simulazione degli attacchi sono disponibili più tipi di tecniche di social engineering:</span><span class="sxs-lookup"><span data-stu-id="6ba7e-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="6ba7e-126">**Raccolta credenziali**: un utente malintenzionato invia al destinatario un messaggio che contiene un URL.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="6ba7e-127">Quando il destinatario fa clic sull'URL, vengono indirizzati a un sito Web che in genere viene visualizzata una finestra di dialogo in cui viene richiesto all'utente il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="6ba7e-128">La pagina di destinazione, in genere, è rappresentata da un sito Web noto per poter creare la fiducia nell'utente.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="6ba7e-129">**Allegato di malware**: un utente malintenzionato invia al destinatario un messaggio che contiene un allegato.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="6ba7e-130">Quando il destinatario apre l'allegato, il codice arbitrario (ad esempio, una macro) viene eseguito sul dispositivo dell'utente per consentire all'aggressore di installare ulteriore codice o ulteriori radicare stessi.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="6ba7e-131">**Collegamento in allegato**: questo è un ibrido di un raccolto di credenziali.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="6ba7e-132">Un utente malintenzionato invia al destinatario un messaggio che contiene un URL all'interno di un allegato.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="6ba7e-133">Quando il destinatario apre l'allegato e fa clic sull'URL, viene visualizzato in un sito Web che in genere viene visualizzata una finestra di dialogo in cui viene richiesto all'utente il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="6ba7e-134">La pagina di destinazione, in genere, è rappresentata da un sito Web noto per poter creare la fiducia nell'utente.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="6ba7e-135">**Collegamento a malware**: un utente malintenzionato invia al destinatario un messaggio che contiene un collegamento a un allegato in un sito di condivisione file conosciuto (ad esempio, SharePoint Online o Dropbox).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="6ba7e-136">Quando il destinatario fa clic sull'URL, viene aperto l'allegato e viene eseguito codice arbitrario, ad esempio una macro, sul dispositivo dell'utente per consentire all'aggressore di installare ulteriore codice o ulteriori radicare.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="6ba7e-137">**Drive-by-URL**: un utente malintenzionato invia al destinatario un messaggio che contiene un URL.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="6ba7e-138">Quando il destinatario fa clic sull'URL, vengono indirizzati a un sito Web che tenta di eseguire il codice di sfondo.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="6ba7e-139">Questo codice di sfondo tenta di raccogliere informazioni sul destinatario o di distribuire codice arbitrario nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="6ba7e-140">In genere, il sito Web di destinazione è un sito Web noto che è stato compromesso o un clone di un sito Web noto.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="6ba7e-141">La familiarità con il sito Web consente di convincere l'utente che il collegamento è sicuro fare clic su.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="6ba7e-142">Questa tecnica è nota anche come _attacco del foro di irrigazione_.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="6ba7e-143">Controllare la disponibilità dell'URL di phishing simulato nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="6ba7e-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="6ba7e-144">Mentre lavoriamo con molti fornitori di reputazione URL per consentire sempre questi URL di simulazione, non sempre abbiamo una copertura completa (ad esempio, esplorazione sicura di Google).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="6ba7e-145">La maggior parte dei fornitori fornisce indicazioni che consentono di abilitare sempre URL specifici (ad esempio, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="6ba7e-146">Gli URL utilizzati dall'addestramento di simulazione di attacco sono descritti nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="6ba7e-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="6ba7e-147">Creare una simulazione</span><span class="sxs-lookup"><span data-stu-id="6ba7e-147">Create a simulation</span></span>

<span data-ttu-id="6ba7e-148">Per istruzioni dettagliate su come creare e inviare una nuova simulazione, vedere [simulare un attacco di phishing](attack-simulation-training.md).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="6ba7e-149">Creare un payload</span><span class="sxs-lookup"><span data-stu-id="6ba7e-149">Create a payload</span></span>

<span data-ttu-id="6ba7e-150">Per istruzioni dettagliate su come creare un payload per l'utilizzo all'interno di una simulazione, vedere [creare un payload personalizzato per la formazione di simulazione di attacco](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="6ba7e-151">Acquisizione di informazioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="6ba7e-151">Gaining insights</span></span>

<span data-ttu-id="6ba7e-152">Per istruzioni dettagliate su come acquisire informazioni sulla creazione di report, vedere [Gain Insights through Attack Simulation Training](attack-simulation-training-insights.md).</span><span class="sxs-lookup"><span data-stu-id="6ba7e-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
