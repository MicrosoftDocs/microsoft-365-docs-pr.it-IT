---
title: Utilizzo dell'identità, del dispositivo e della protezione dalle minacce per la normativa sulla privacy dei dati
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
description: Impedire violazioni dei dati personali con i servizi Identity, Device e Threat Protection di Microsoft 365.
ms.openlocfilehash: 681ff807b734430ae864334b409fe11397f3089e
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377058"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="8b0e1-103">Utilizzo dell'identità, del dispositivo e della protezione dalle minacce per la normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="8b0e1-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="8b0e1-104">Microsoft 365 fornisce una serie di funzionalità di protezione dell'identità, dei dispositivi e delle minacce che le organizzazioni possono utilizzare per contribuire a conformarsi alle normative sulla conformità relative alla privacy dei dati.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="8b0e1-105">In questo articolo vengono descritte le normative sulla privacy dei dati richieste in queste aree e viene fornito un elenco delle funzionalità e dei servizi relativi a Microsoft 365 con collegamenti a ulteriori informazioni che consentono di soddisfare i requisiti di implementazione.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="8b0e1-106">Come identità, dispositivo e protezione dalle minacce riguardano la normativa sulla privacy dei dati</span><span class="sxs-lookup"><span data-stu-id="8b0e1-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="8b0e1-107">Anche se le normative sulla privacy dei dati variano in base alla loro specificità, l'essenza del loro appello è incarnata nell'articolo 5 (1) (f) dell'GDPR, in cui si afferma che:</span><span class="sxs-lookup"><span data-stu-id="8b0e1-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="8b0e1-108">I dati personali devono essere elaborati in modo da garantire una sicurezza adeguata dei dati personali, inclusa la protezione contro l'elaborazione non autorizzata o illecita e contro la perdita accidentale, la distruzione o il danneggiamento, usando misure tecniche o organizzative appropriate ("integrità e riservatezza").</span><span class="sxs-lookup"><span data-stu-id="8b0e1-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="8b0e1-109">Poiché le violazioni dei dati personali sono spesso causate da un compromesso dell'account amministrativo o dell'utente finale e da un accesso dannoso del sistema.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="8b0e1-110">Ad esempio, un hack dell'account di amministratore può comportare la exfiltration dei numeri di carta di credito del cliente o di altre informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="8b0e1-111">Tutti gli identificatori, i dispositivi e la protezione delle minacce generalmente consigliati disponibili con Microsoft 365 potrebbero essere implementati, che verranno riflessi nel punteggio di conformità, individuati in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="8b0e1-112">Utilizzo dei risultati del lavoro di valutazione e del Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="8b0e1-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="8b0e1-113">Compliance Manager include identità, dispositivo e protezione dalle minacce utilizzando queste categorie:</span><span class="sxs-lookup"><span data-stu-id="8b0e1-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="8b0e1-114">Identity corrisponde alla categoria di **accesso ai controlli**</span><span class="sxs-lookup"><span data-stu-id="8b0e1-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="8b0e1-115">Dispositivo corrispondente alla categoria **Gestisci dispositivi**</span><span class="sxs-lookup"><span data-stu-id="8b0e1-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="8b0e1-116">La protezione dalle minacce corrisponde alla categoria **Proteggi contro i pericoli**</span><span class="sxs-lookup"><span data-stu-id="8b0e1-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="8b0e1-117">Se queste sono selezionate nel set di quattro principali normative sulla privacy dei dati, Compliance Manager specifica 90 azioni di miglioramento, la maggior parte delle quali ha un punteggio di "27".</span><span class="sxs-lookup"><span data-stu-id="8b0e1-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="8b0e1-118">Poiché un numero così elevato viene chiamato da Compliance Manager per queste categorie, alcuni dei più comuni sono elencati qui, per riferimento.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="8b0e1-119">Utilizzare [Azure Active Directory (Azure ad)](https://azure.microsoft.com/services/active-directory/) per l'identità e la categoria di **accesso ai controlli** , con cui è possibile:</span><span class="sxs-lookup"><span data-stu-id="8b0e1-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="8b0e1-120">Implementazione dell'autenticazione resistente ai rigiocamenti (per impedire attacchi di tipo "Man in the Middle")</span><span class="sxs-lookup"><span data-stu-id="8b0e1-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="8b0e1-121">Bloccare l'autenticazione legacy.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-121">Block legacy authentication.</span></span>
- <span data-ttu-id="8b0e1-122">Configurare i rischi per gli utenti e i criteri di accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="8b0e1-123">Abilitare l'accesso condizionale e l'autenticazione a più fattori (AMF) per gli amministratori e gli utenti non amministratori.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="8b0e1-124">Configurare e applicare i criteri per le password.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="8b0e1-125">Limitare l'accesso a account privilegiati con Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="8b0e1-126">Disabilitare l'accesso alla terminazione.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-126">Disable access upon termination.</span></span>
- <span data-ttu-id="8b0e1-127">Controllare gli account utente e le modifiche dello stato.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="8b0e1-128">Esaminare il gruppo di ruoli e le modifiche amministrative.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="8b0e1-129">Utilizzare [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) per i dispositivi e la categoria **Gestisci dispositivi** , con cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b0e1-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="8b0e1-130">Blocca i dispositivi mobili bloccati e sradicati del Jail.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="8b0e1-131">Configurare Intune per la gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="8b0e1-132">Creare criteri di conformità per i dispositivi Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="8b0e1-133">Creare un profilo di configurazione del dispositivo per i dispositivi Android, iOS, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="8b0e1-134">Creare criteri di protezione delle app per iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="8b0e1-135">Nascondere le informazioni con la schermata di blocco.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="8b0e1-136">Implementare criteri password per i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="8b0e1-137">Richiedere ai dispositivi mobili di bloccarsi su inattività.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="8b0e1-138">Richiedere ai dispositivi mobili di cancellare gli errori di accesso multipli.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="8b0e1-139">Utilizzare [Exchange Online Protection e Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) per la categoria **protezione dalle minacce** , con cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b0e1-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="8b0e1-140">Abilitare l'autenticazione del mittente (SPF, DMARC e DKIM).</span><span class="sxs-lookup"><span data-stu-id="8b0e1-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="8b0e1-141">Impostare i criteri di anti-phishing di Office 365 Advanced Threat Protection (ATP).</span><span class="sxs-lookup"><span data-stu-id="8b0e1-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="8b0e1-142">Implementare gli allegati sicuri di ATP.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="8b0e1-143">Implementare collegamenti sicuri di ATP.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="8b0e1-144">Implementare criteri di rilevamento e risposta malware.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="8b0e1-145">Implementare i criteri di posta indesiderata in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="8b0e1-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="8b0e1-146">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="8b0e1-146">References:</span></span>

- [<span data-ttu-id="8b0e1-147">Criteri comuni di identità e accesso dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="8b0e1-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="8b0e1-148">Protezione dalle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="8b0e1-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="8b0e1-149">Allegati sicuri di ATP</span><span class="sxs-lookup"><span data-stu-id="8b0e1-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="8b0e1-150">Collegamenti sicuri di ATP</span><span class="sxs-lookup"><span data-stu-id="8b0e1-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="8b0e1-151">Sicurezza documenti ATP</span><span class="sxs-lookup"><span data-stu-id="8b0e1-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
