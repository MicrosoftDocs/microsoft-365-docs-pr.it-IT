---
title: Usare identità, dispositivo e protezione dalle minacce per la normativa sulla privacy dei dati
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Impedire violazioni dei dati personali con i servizi di protezione dalle minacce, dei dispositivi e dell'identità di Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199466"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="1254f-103">Usare identità, dispositivo e protezione dalle minacce per la normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="1254f-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="1254f-104">Microsoft 365 offre diverse funzionalità di protezione da identità, dispositivi e minacce che le organizzazioni possono utilizzare per garantire la conformità alle normative di conformità relative alla privacy dei dati.</span><span class="sxs-lookup"><span data-stu-id="1254f-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="1254f-105">In questo articolo vengono descritti i requisiti delle normative sulla privacy dei dati in queste aree e viene fornito un elenco delle funzionalità e dei servizi di Microsoft 365 correlati con collegamenti a ulteriori informazioni utili per soddisfare i requisiti di implementazione.</span><span class="sxs-lookup"><span data-stu-id="1254f-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="1254f-106">Relazione tra identità, dispositivo e protezione dalle minacce con la normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="1254f-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="1254f-107">Anche se le normative sulla privacy dei dati variano in base alla loro specificità, l'essenza di ciò che chiamano è incorporata nell'articolo 5(1)(f) del GDPR, che afferma che:</span><span class="sxs-lookup"><span data-stu-id="1254f-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="1254f-108">I dati personali devono essere trattati in modo da garantire una sicurezza adeguata dei dati personali, compresa la protezione contro il trattamento non autorizzato o illecito e contro la perdita accidentale, la distruzione o il danneggiamento, utilizzando misure tecniche o organizzative appropriate ("integrità e riservatezza").</span><span class="sxs-lookup"><span data-stu-id="1254f-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="1254f-109">Poiché le violazioni dei dati personali sono spesso causate da compromissione dell'account amministrativo o dell'utente finale e dall'accesso al sistema dannoso.</span><span class="sxs-lookup"><span data-stu-id="1254f-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="1254f-110">Ad esempio, una violazione dell'account amministratore può comportare l'esfiltrazione dei numeri di carta di credito del cliente o altre informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="1254f-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="1254f-111">Tutte le identità, i dispositivi e la protezione dalle minacce generalmente consigliabili disponibili con Microsoft 365 potenzialmente dovrebbero essere implementate, che verranno riflesse nel punteggio di conformità, disponibile in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="1254f-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="1254f-112">Utilizzo dei risultati del lavoro di valutazione e di Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="1254f-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="1254f-113">Compliance Manager include identità, dispositivo e protezione dalle minacce usando queste categorie:</span><span class="sxs-lookup"><span data-stu-id="1254f-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="1254f-114">L'identità corrisponde alla **categoria Controllo accesso**</span><span class="sxs-lookup"><span data-stu-id="1254f-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="1254f-115">Il dispositivo corrisponde alla **categoria Gestisci** dispositivi</span><span class="sxs-lookup"><span data-stu-id="1254f-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="1254f-116">Protezione dalle minacce corrisponde alla **categoria Protezione dalle** minacce</span><span class="sxs-lookup"><span data-stu-id="1254f-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="1254f-117">Se queste sono selezionate nell'insieme di esempio di quattro principali normative sulla privacy dei dati, Compliance Manager specifica 90 azioni di miglioramento, la maggior parte delle quali ha un punteggio "27".</span><span class="sxs-lookup"><span data-stu-id="1254f-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="1254f-118">Dal momento che un numero così elevato viene chiamato da Compliance Manager per queste categorie, alcune delle più comuni sono elencate qui, per riferimento.</span><span class="sxs-lookup"><span data-stu-id="1254f-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="1254f-119">Usare [Azure Active Directory (Azure AD) per](https://azure.microsoft.com/services/active-directory/) l'identità e la categoria Controllo **accesso,** con cui è possibile:</span><span class="sxs-lookup"><span data-stu-id="1254f-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="1254f-120">Implementare l'autenticazione resistente alla riesecuzione (per impedire attacchi "Man in the middle")</span><span class="sxs-lookup"><span data-stu-id="1254f-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="1254f-121">Bloccare l'autenticazione legacy.</span><span class="sxs-lookup"><span data-stu-id="1254f-121">Block legacy authentication.</span></span>
- <span data-ttu-id="1254f-122">Configurare i criteri di rischio di accesso degli utenti e dei rischi per l'accesso degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1254f-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="1254f-123">Abilitare l'accesso condizionale e l'autenticazione a più fattori (MFA) per amministratori e non amministratori.</span><span class="sxs-lookup"><span data-stu-id="1254f-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="1254f-124">Configurare e applicare criteri password.</span><span class="sxs-lookup"><span data-stu-id="1254f-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="1254f-125">Limitare l'accesso agli account con privilegi con Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="1254f-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="1254f-126">Disabilitare l'accesso al termine.</span><span class="sxs-lookup"><span data-stu-id="1254f-126">Disable access upon termination.</span></span>
- <span data-ttu-id="1254f-127">Controllare gli account utente e le modifiche di stato.</span><span class="sxs-lookup"><span data-stu-id="1254f-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="1254f-128">Esaminare le modifiche amministrative e del gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="1254f-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="1254f-129">Usa [Microsoft Endpoint Manager per](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) i dispositivi e la categoria **Gestisci** dispositivi, con cui puoi:</span><span class="sxs-lookup"><span data-stu-id="1254f-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="1254f-130">Bloccare i dispositivi mobili interrotti e rooted.</span><span class="sxs-lookup"><span data-stu-id="1254f-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="1254f-131">Configurare Intune per la gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="1254f-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="1254f-132">Creare criteri di conformità per dispositivi Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="1254f-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="1254f-133">Crea un profilo di configurazione del dispositivo per dispositivi Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="1254f-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="1254f-134">Creare criteri di protezione delle app per iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="1254f-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="1254f-135">Nascondere le informazioni con la schermata di blocco.</span><span class="sxs-lookup"><span data-stu-id="1254f-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="1254f-136">Implementare criteri password per i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="1254f-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="1254f-137">Richiedi ai dispositivi mobili di bloccarsi in caso di inattività.</span><span class="sxs-lookup"><span data-stu-id="1254f-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="1254f-138">Richiedere ai dispositivi mobili di cancellare i dati in caso di più errori di accesso.</span><span class="sxs-lookup"><span data-stu-id="1254f-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="1254f-139">Usare [Exchange Online Protection e Microsoft Defender per Office 365](../security/office-365-security/defender-for-office-365.md) per la categoria **Protezione** dalle minacce, con cui è possibile:</span><span class="sxs-lookup"><span data-stu-id="1254f-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="1254f-140">Abilitare l'autenticazione mittente (SPF, DMARC e DKIM).</span><span class="sxs-lookup"><span data-stu-id="1254f-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="1254f-141">Configurare i criteri anti-phishing di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="1254f-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="1254f-142">Implementare allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="1254f-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="1254f-143">Implementare collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="1254f-143">Implement Safe Links.</span></span>
- <span data-ttu-id="1254f-144">Implementare i criteri di rilevamento e risposta di malware.</span><span class="sxs-lookup"><span data-stu-id="1254f-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="1254f-145">Implementare i criteri di posta indesiderata in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="1254f-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="1254f-146">Riferimenti:</span><span class="sxs-lookup"><span data-stu-id="1254f-146">References:</span></span>

- [<span data-ttu-id="1254f-147">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="1254f-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="1254f-148">Proteggere dalle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="1254f-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="1254f-149">Allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="1254f-149">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)
- [<span data-ttu-id="1254f-150">Collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="1254f-150">Safe Links</span></span>](../security/office-365-security/safe-links.md)
- [<span data-ttu-id="1254f-151">Sicurezza documenti</span><span class="sxs-lookup"><span data-stu-id="1254f-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
