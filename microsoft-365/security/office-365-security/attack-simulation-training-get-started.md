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
description: Gli amministratori possono imparare a usare la formazione sulla simulazione degli attacchi per eseguire attacchi simulati di phishing e password nelle organizzazioni Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a33c212f7d0fd6b0617a8059b03ac90de03fba16
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407477"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="f20c8-103">Introduzione alla formazione sull’uso di Simulatore di attacchi</span><span class="sxs-lookup"><span data-stu-id="f20c8-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f20c8-104">Se l'organizzazione dispone di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi e risposta alle [minacce,](office-365-ti.md)è possibile usare la formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f20c8-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="f20c8-105">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sui tuoi utili.</span><span class="sxs-lookup"><span data-stu-id="f20c8-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="f20c8-106">Leggi questo articolo per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="f20c8-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="f20c8-107">La formazione per la simulazione degli attacchi sostituisce la vecchia esperienza simulatore di attacchi v1 descritta in Simulatore di attacchi [in Microsoft Defender per Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="f20c8-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f20c8-108">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="f20c8-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f20c8-109">Per aprire il Centro sicurezza Microsoft, passare a <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="f20c8-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="f20c8-110">La formazione sulla simulazione degli attacchi è disponibile nella **formazione sulla simulazione** degli attacchi tramite posta elettronica \> **e collaborazione.**</span><span class="sxs-lookup"><span data-stu-id="f20c8-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="f20c8-111">Per passare direttamente al training di simulazione degli attacchi, aprire <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="f20c8-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="f20c8-112">Per ulteriori informazioni sulla disponibilità della formazione sulla simulazione degli attacchi tra diversi abbonamenti a Microsoft 365, vedere Descrizione del servizio [Microsoft Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="f20c8-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="f20c8-113">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni nel Centro sicurezza & conformità o in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f20c8-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="f20c8-114">In particolare, è necessario essere membri di **Gestione** organizzazione, **Amministratore sicurezza** o uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f20c8-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="f20c8-115">**Amministratori simulatore di attacco:** creare e gestire tutti gli aspetti delle campagne di simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="f20c8-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="f20c8-116">**Autori di payload del simulatore di** attacchi: creare payload di attacco che un amministratore può avviare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f20c8-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="f20c8-117">Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md) o Informazioni sui ruoli di [amministratore.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f20c8-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="f20c8-118">Non sono disponibili cmdlet di PowerShell corrispondenti per la formazione sulla simulazione degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="f20c8-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="f20c8-119">I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f20c8-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="f20c8-120">Per altre informazioni, vedere [Percorsi dei dati di Microsoft 365.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="f20c8-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="f20c8-121">La simulazione degli attacchi è disponibile nelle aree geografiche seguenti: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN e KOR.</span><span class="sxs-lookup"><span data-stu-id="f20c8-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="f20c8-122">Simulazioni</span><span class="sxs-lookup"><span data-stu-id="f20c8-122">Simulations</span></span>

<span data-ttu-id="f20c8-123">*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="f20c8-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="f20c8-124">*Il* phishing fa parte di un sottoinsieme di tecniche classificate come _ingegneria sociale._</span><span class="sxs-lookup"><span data-stu-id="f20c8-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="f20c8-125">Nella formazione sulla simulazione degli attacchi sono disponibili diversi tipi di tecniche di social engineering:</span><span class="sxs-lookup"><span data-stu-id="f20c8-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="f20c8-126">**Raccolta credenziali:** un utente malintenzionato invia al destinatario un messaggio contenente un URL.</span><span class="sxs-lookup"><span data-stu-id="f20c8-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="f20c8-127">Quando il destinatario fa clic sull'URL, viene visualizzato un sito Web che in genere mostra una finestra di dialogo che richiede all'utente nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="f20c8-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="f20c8-128">In genere, la pagina di destinazione è a cui viene fatto il nome per rappresentare un sito Web noto per creare una relazione di trust con l'utente.</span><span class="sxs-lookup"><span data-stu-id="f20c8-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="f20c8-129">**Allegato malware:** un utente malintenzionato invia al destinatario un messaggio contenente un allegato.</span><span class="sxs-lookup"><span data-stu-id="f20c8-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="f20c8-130">Quando il destinatario apre l'allegato, nel dispositivo dell'utente viene eseguito codice arbitrario (ad esempio una macro) per consentire all'autore dell'attacco di installare codice aggiuntivo o consolidare ulteriormente se stesso.</span><span class="sxs-lookup"><span data-stu-id="f20c8-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="f20c8-131">**Collegamento nell'allegato:** si tratta di un ibrido di un raccolto di credenziali.</span><span class="sxs-lookup"><span data-stu-id="f20c8-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="f20c8-132">Un utente malintenzionato invia al destinatario un messaggio contenente un URL all'interno di un allegato.</span><span class="sxs-lookup"><span data-stu-id="f20c8-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="f20c8-133">Quando il destinatario apre l'allegato e fa clic sull'URL, viene visualizzato un sito Web che in genere mostra una finestra di dialogo che richiede all'utente nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="f20c8-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="f20c8-134">In genere, la pagina di destinazione è a cui viene fatto il nome per rappresentare un sito Web noto per creare una relazione di trust con l'utente.</span><span class="sxs-lookup"><span data-stu-id="f20c8-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="f20c8-135">**Collegamento al malware:** un utente malintenzionato invia al destinatario un messaggio contenente un collegamento a un allegato in un sito noto di condivisione file (ad esempio, SharePoint Online o Dropbox).</span><span class="sxs-lookup"><span data-stu-id="f20c8-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="f20c8-136">Quando il destinatario fa clic sull'URL, l'allegato viene aperto e nel dispositivo dell'utente viene eseguito codice arbitrario, ad esempio una macro, per consentire all'autore dell'attacco di installare codice aggiuntivo o consolidare ulteriormente se stesso.</span><span class="sxs-lookup"><span data-stu-id="f20c8-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="f20c8-137">**Unità per url: un** utente malintenzionato invia al destinatario un messaggio contenente un URL.</span><span class="sxs-lookup"><span data-stu-id="f20c8-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="f20c8-138">Quando il destinatario fa clic sull'URL, viene visualizzato un sito Web che tenta di eseguire il codice in background.</span><span class="sxs-lookup"><span data-stu-id="f20c8-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="f20c8-139">Questo codice in background tenta di raccogliere informazioni sul destinatario o di distribuire codice arbitrario nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f20c8-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="f20c8-140">In genere, il sito Web di destinazione è un sito Web noto che è stato compromesso o un clone di un sito Web noto.</span><span class="sxs-lookup"><span data-stu-id="f20c8-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="f20c8-141">La familiarità con il sito Web consente di convincere l'utente che il collegamento è sicuro da fare clic.</span><span class="sxs-lookup"><span data-stu-id="f20c8-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="f20c8-142">Questa tecnica è nota anche come attacco _al foro di innaffiamento._</span><span class="sxs-lookup"><span data-stu-id="f20c8-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="f20c8-143">Verificare la disponibilità dell'URL di phishing simulato nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="f20c8-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="f20c8-144">Anche se lavoriamo con molti fornitori di reputazione URL per consentire sempre questi URL di simulazione, non sempre abbiamo una copertura completa (ad esempio, Esplorazione sicura di Google).</span><span class="sxs-lookup"><span data-stu-id="f20c8-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="f20c8-145">La maggior parte dei fornitori fornisce indicazioni che consentono di consentire sempre URL specifici , ad esempio <https://support.google.com/chrome/a/answer/7532419> .</span><span class="sxs-lookup"><span data-stu-id="f20c8-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="f20c8-146">Gli URL utilizzati dal training di simulazione degli attacchi sono descritti nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="f20c8-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="f20c8-147">Creare una simulazione</span><span class="sxs-lookup"><span data-stu-id="f20c8-147">Create a simulation</span></span>

<span data-ttu-id="f20c8-148">Per istruzioni dettagliate su come creare e inviare una nuova [simulazione, vedere Simulare un attacco di phishing.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="f20c8-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="f20c8-149">Creare un payload</span><span class="sxs-lookup"><span data-stu-id="f20c8-149">Create a payload</span></span>

<span data-ttu-id="f20c8-150">Per istruzioni dettagliate su come creare un payload da usare all'interno di una simulazione, vedi Creare un payload personalizzato per il training della simulazione [di attacco.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="f20c8-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="f20c8-151">Ottenere informazioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="f20c8-151">Gaining insights</span></span>

<span data-ttu-id="f20c8-152">Per istruzioni dettagliate su come ottenere informazioni dettagliate con la creazione di report, vedere Acquisire informazioni [dettagliate tramite la formazione sulla simulazione degli attacchi.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="f20c8-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
