---
title: Introduzione alla formazione sull’uso di Simulatore di attacchi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare la formazione di simulazione degli attacchi per eseguire attacchi simulati di phishing e password nelle organizzazioni Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5d4b77204f207c31f2014df797f6209b92c9ccb
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822335"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="b6e16-103">Introduzione alla formazione sull’uso di Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="b6e16-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b6e16-104">Se l'organizzazione dispone di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi delle minacce e [risposta,](office-365-ti.md)è possibile utilizzare la formazione sulla simulazione di attacchi nel Centro sicurezza Microsoft per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6e16-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="b6e16-105">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sulla linea di fondo.</span><span class="sxs-lookup"><span data-stu-id="b6e16-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="b6e16-106">Leggi questo articolo per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="b6e16-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="b6e16-107">Il training della simulazione di attacco sostituisce la vecchia esperienza di Simulatore di attacco v1 descritta in [Simulatore](attack-simulator.md)di attacco in Microsoft Defender per Office 365 .</span><span class="sxs-lookup"><span data-stu-id="b6e16-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b6e16-108">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="b6e16-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b6e16-109">Per aprire il Centro sicurezza Microsoft, passare a <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="b6e16-109">To open the Microsoft Security Center, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="b6e16-110">Formazione sulla simulazione di attacchi è disponibile in **Formazione sulla simulazione di attacchi tramite posta elettronica e** \> **collaborazione.**</span><span class="sxs-lookup"><span data-stu-id="b6e16-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="b6e16-111">Per passare direttamente alla formazione sulla simulazione di attacco, aprire <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="b6e16-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="b6e16-112">Per ulteriori informazioni sulla disponibilità del training di simulazione degli attacchi tra diverse sottoscrizioni Microsoft 365, vedi [Microsoft Defender per](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)la descrizione Office 365 servizio .</span><span class="sxs-lookup"><span data-stu-id="b6e16-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="b6e16-113">È necessario disporre delle autorizzazioni nel Centro sicurezza & conformità o in Azure Active Directory prima di eseguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6e16-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="b6e16-114">In particolare, è necessario essere membri di **Gestione** organizzazione, **Amministratore sicurezza** o uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6e16-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="b6e16-115">**Amministratori simulatore di attacco**: creare e gestire tutti gli aspetti delle campagne di simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="b6e16-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="b6e16-116">**Autori payload simulatore di** attacco : creare payload di attacco che un amministratore può avviare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="b6e16-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="b6e16-117">Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md) o Informazioni sui ruoli di [amministratore.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="b6e16-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="b6e16-118">Non sono disponibili cmdlet di PowerShell corrispondenti per il training della simulazione di attacco.</span><span class="sxs-lookup"><span data-stu-id="b6e16-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="b6e16-119">I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti Microsoft 365 servizi.</span><span class="sxs-lookup"><span data-stu-id="b6e16-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="b6e16-120">Per ulteriori informazioni, [vedere Microsoft 365 di dati](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="b6e16-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="b6e16-121">La simulazione di attacco è disponibile nelle seguenti aree geografiche: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN e KOR.</span><span class="sxs-lookup"><span data-stu-id="b6e16-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

- <span data-ttu-id="b6e16-122">A partire dal 15 giugno 2021, il training di simulazione degli attacchi è disponibile in GCC.</span><span class="sxs-lookup"><span data-stu-id="b6e16-122">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="b6e16-123">Se l'organizzazione ha Office 365 G5 GCC o Microsoft Defender for Office 365 (Piano 2) per enti pubblici, è possibile utilizzare la formazione sulla simulazione di attacchi nel Centro sicurezza Microsoft per eseguire scenari di attacco realistici nell'organizzazione, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6e16-123">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="b6e16-124">Il training della simulazione di attacchi non è ancora disponibile in GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="b6e16-124">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="b6e16-125">La formazione sulla simulazione di attacchi offre un sottoinsieme di funzionalità ai clienti E3 come versione di prova.</span><span class="sxs-lookup"><span data-stu-id="b6e16-125">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="b6e16-126">L'offerta di valutazione contiene la possibilità di usare un payload di raccolta delle credenziali e la possibilità di selezionare esperienze di formazione "PHISHING ISA" o "Phishing di massa sul mercato".</span><span class="sxs-lookup"><span data-stu-id="b6e16-126">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="b6e16-127">Nessuna altra funzionalità fa parte dell'offerta di valutazione E3.</span><span class="sxs-lookup"><span data-stu-id="b6e16-127">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="b6e16-128">Simulazioni</span><span class="sxs-lookup"><span data-stu-id="b6e16-128">Simulations</span></span>

<span data-ttu-id="b6e16-129">*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="b6e16-129">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="b6e16-130">*Il phishing* fa parte di un sottoinsieme di tecniche classificate come _social engineering._</span><span class="sxs-lookup"><span data-stu-id="b6e16-130">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="b6e16-131">Nella formazione sulla simulazione di attacchi sono disponibili diversi tipi di tecniche di social engineering:</span><span class="sxs-lookup"><span data-stu-id="b6e16-131">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="b6e16-132">**Raccolta credenziali:** un utente malintenzionato invia al destinatario un messaggio contenente un URL.</span><span class="sxs-lookup"><span data-stu-id="b6e16-132">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="b6e16-133">Quando il destinatario fa clic sull'URL, viene visualizzato un sito Web che in genere visualizza una finestra di dialogo che richiede all'utente nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="b6e16-133">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="b6e16-134">In genere, la pagina di destinazione è a base di un'applicazione che rappresenta un sito Web noto per creare una relazione di trust con l'utente.</span><span class="sxs-lookup"><span data-stu-id="b6e16-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="b6e16-135">**Allegato malware:** un utente malintenzionato invia al destinatario un messaggio contenente un allegato.</span><span class="sxs-lookup"><span data-stu-id="b6e16-135">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="b6e16-136">Quando il destinatario apre l'allegato, viene eseguito codice arbitrario (ad esempio una macro) nel dispositivo dell'utente per consentire all'autore dell'attacco di installare codice aggiuntivo o consolidare ulteriormente se stessi.</span><span class="sxs-lookup"><span data-stu-id="b6e16-136">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="b6e16-137">**Collegamento nell'allegato:** si tratta di un ibrido di un raccolto di credenziali.</span><span class="sxs-lookup"><span data-stu-id="b6e16-137">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="b6e16-138">Un utente malintenzionato invia al destinatario un messaggio contenente un URL all'interno di un allegato.</span><span class="sxs-lookup"><span data-stu-id="b6e16-138">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="b6e16-139">Quando il destinatario apre l'allegato e fa clic sull'URL, viene visualizzato un sito Web in cui in genere viene visualizzata una finestra di dialogo che richiede all'utente nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="b6e16-139">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="b6e16-140">In genere, la pagina di destinazione è a base di un'applicazione che rappresenta un sito Web noto per creare una relazione di trust con l'utente.</span><span class="sxs-lookup"><span data-stu-id="b6e16-140">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="b6e16-141">**Collegamento al malware**: un utente malintenzionato invia al destinatario un messaggio contenente un collegamento a un allegato in un sito noto per la condivisione di file (ad esempio, SharePoint Online o Dropbox).</span><span class="sxs-lookup"><span data-stu-id="b6e16-141">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="b6e16-142">Quando il destinatario fa clic sull'URL, l'allegato si apre e sul dispositivo dell'utente viene eseguito codice arbitrario (ad esempio una macro) per consentire all'autore dell'attacco di installare codice aggiuntivo o consolidare ulteriormente se stessi.</span><span class="sxs-lookup"><span data-stu-id="b6e16-142">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="b6e16-143">**Unità per url**: un utente malintenzionato invia al destinatario un messaggio contenente un URL.</span><span class="sxs-lookup"><span data-stu-id="b6e16-143">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="b6e16-144">Quando il destinatario fa clic sull'URL, viene visualizzato un sito Web che tenta di eseguire codice in background.</span><span class="sxs-lookup"><span data-stu-id="b6e16-144">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="b6e16-145">Questo codice in background tenta di raccogliere informazioni sul destinatario o di distribuire codice arbitrario nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6e16-145">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="b6e16-146">In genere, il sito Web di destinazione è un sito Web noto compromesso o un clone di un sito Web noto.</span><span class="sxs-lookup"><span data-stu-id="b6e16-146">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="b6e16-147">La familiarità con il sito Web consente di convincere l'utente che il collegamento è sicuro da fare clic.</span><span class="sxs-lookup"><span data-stu-id="b6e16-147">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="b6e16-148">Questa tecnica è nota anche come _attacco del foro di annaffiatura._</span><span class="sxs-lookup"><span data-stu-id="b6e16-148">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="b6e16-149">Verificare la disponibilità dell'URL di phishing simulato nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="b6e16-149">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="b6e16-150">Anche se lavoriamo con molti fornitori di reputazione URL per consentire sempre questi URL di simulazione, non sempre abbiamo una copertura completa (ad esempio, Google Safe Browsing).</span><span class="sxs-lookup"><span data-stu-id="b6e16-150">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="b6e16-151">La maggior parte dei fornitori fornisce indicazioni che consentono di consentire sempre URL specifici (ad esempio, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="b6e16-151">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="b6e16-152">Gli URL utilizzati dal training di simulazione degli attacchi sono descritti nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="b6e16-152">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="b6e16-153">Creare una simulazione</span><span class="sxs-lookup"><span data-stu-id="b6e16-153">Create a simulation</span></span>

<span data-ttu-id="b6e16-154">Per istruzioni dettagliate su come creare e inviare una nuova [simulazione,](attack-simulation-training.md)vedere Simulate a phishing attack .</span><span class="sxs-lookup"><span data-stu-id="b6e16-154">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="b6e16-155">Creare un payload</span><span class="sxs-lookup"><span data-stu-id="b6e16-155">Create a payload</span></span>

<span data-ttu-id="b6e16-156">Per istruzioni dettagliate su come creare un payload da usare all'interno di una simulazione, vedi Creare un payload personalizzato per [il training della simulazione di attacco.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="b6e16-156">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="b6e16-157">Ottenere informazioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="b6e16-157">Gaining insights</span></span>

<span data-ttu-id="b6e16-158">Per istruzioni dettagliate su come ottenere informazioni dettagliate con la creazione di report, vedi Acquisire informazioni dettagliate tramite la formazione [sulla simulazione di attacchi.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="b6e16-158">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b6e16-159">Attack Simulator usa Collegamenti sicuri in Defender per Office 365 per tenere traccia in modo sicuro dei dati dei clic per  l'URL nel messaggio payload inviato ai destinatari mirati di una campagna di phishing, anche se l'impostazione Non tenere traccia dei clic degli utenti nei criteri Collegamenti sicuri è attivata.</span><span class="sxs-lookup"><span data-stu-id="b6e16-159">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
