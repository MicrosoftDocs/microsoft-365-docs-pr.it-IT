---
title: Protezione anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle funzionalità di protezione anti-phishing in Exchange Online Protection (EOP) e Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 5594c4e7033ab70a622403bca7759cd4b89f111a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827446"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="f5dad-103">Protezione anti-phishing in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5dad-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="f5dad-104">Il *phishing* è un attacco di posta elettronica che cerca di rubare informazioni riservate nei messaggi che sembrano provenire da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="f5dad-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="f5dad-105">Esistono categorie specifiche di phishing.</span><span class="sxs-lookup"><span data-stu-id="f5dad-105">There are specific categories of phishing.</span></span> <span data-ttu-id="f5dad-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f5dad-106">For example:</span></span>

- <span data-ttu-id="f5dad-107">**Spear phishing** utilizza contenuto molto concentrato e personalizzato appositamente adattato ai destinatari mirati (in genere dopo la ricognizione dei destinatari da parte dell'utente malintenzionato).</span><span class="sxs-lookup"><span data-stu-id="f5dad-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="f5dad-108">La **caccia alle balene** è rivolta ai dirigenti o ad altri obiettivi di alto valore all'interno di un'organizzazione per ottenere il massimo effetto.</span><span class="sxs-lookup"><span data-stu-id="f5dad-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="f5dad-109">**Business email compromess (BEC)** utilizza i mittenti attendibili falsificati (responsabili finanziari, clienti, partner attendibili e così via) nel tentativo di ingannare il destinatario nell'approvazione dei pagamenti, nel trasferimento di fondi o nella divulgazione dei dati del cliente.</span><span class="sxs-lookup"><span data-stu-id="f5dad-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="f5dad-110">**Ransomware** che crittografa i dati e richiede il pagamento per decrittografarlo inizia quasi sempre nei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="f5dad-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="f5dad-111">La protezione anti-phishing non consente di decrittografare i file crittografati, ma può contribuire a rilevare i messaggi di phishing iniziali associati alla campagna ransomware.</span><span class="sxs-lookup"><span data-stu-id="f5dad-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="f5dad-112">Per ulteriori informazioni sul ripristino da un attacco ransomware, vedere [Recover from a ransomware Attack in Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="f5dad-113">Con la crescente complessità degli attacchi, è persino difficile per gli utenti addestrati identificare messaggi di phishing sofisticati.</span><span class="sxs-lookup"><span data-stu-id="f5dad-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="f5dad-114">Fortunatamente, Exchange Online Protection (EOP) e le funzionalità aggiuntive di Office 365 Advanced Threat Protection (Office 365 ATP) possono essere di aiuto.</span><span class="sxs-lookup"><span data-stu-id="f5dad-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="f5dad-115">Protezione anti-phishing in EOP</span><span class="sxs-lookup"><span data-stu-id="f5dad-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="f5dad-116">EOP (ovvero le organizzazioni Microsoft 365 senza ATP) contiene funzionalità che consentono di proteggere l'organizzazione da minacce di phishing:</span><span class="sxs-lookup"><span data-stu-id="f5dad-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="f5dad-117">**Spoof Intelligence**: per esaminare i messaggi falsificati inviati da mittenti in domini interni ed esterni e consentire o bloccare tali mittenti.</span><span class="sxs-lookup"><span data-stu-id="f5dad-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="f5dad-118">Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="f5dad-119">**Criteri di anti-phishing in EOP**: attivazione o disattivazione dell'intelligence di spoofing, attivazione o disabilitazione dell'identificazione dei mittenti non autenticati in Outlook e specifica dell'azione per i mittenti bloccati falsificati (passare alla cartella posta indesiderata o alla quarantena).</span><span class="sxs-lookup"><span data-stu-id="f5dad-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="f5dad-120">Per ulteriori informazioni, vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="f5dad-121">**Autenticazione della posta elettronica implicita**: EOP migliora i controlli di autenticazione della posta elettronica standard per la posta elettronica in ingresso ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) con la reputazione mittente, la cronologia del mittente, la cronologia dei destinatari, l'analisi comportamentale e altre tecniche avanzate che consentono di identificare i mittenti contraffatti.</span><span class="sxs-lookup"><span data-stu-id="f5dad-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="f5dad-122">Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="f5dad-123">Ulteriore protezione anti-phishing in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f5dad-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="f5dad-124">Office 365 ATP contiene funzionalità di anti-phishing aggiuntive e avanzate:</span><span class="sxs-lookup"><span data-stu-id="f5dad-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="f5dad-125">**Criteri di anti-phishing ATP**: creare nuovi criteri personalizzati, configurare le impostazioni di antirappresentazione (proteggere utenti e domini dalla rappresentazione), le impostazioni di intelligence delle cassette postali e le soglie di phishing avanzate regolabili.</span><span class="sxs-lookup"><span data-stu-id="f5dad-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="f5dad-126">Per ulteriori informazioni, vedere [configurare i criteri di anti-phishing ATP in Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="f5dad-127">Per ulteriori informazioni sulle differenze tra i criteri anti-phishing e i criteri di anti-phishing ATP, vedere [anti-phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="f5dad-128">**Visualizzazioni della campagna**: l'apprendimento automatico e altre euristiche identificano e analizzano i messaggi coinvolti negli attacchi di phishing coordinati per l'intero servizio e per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5dad-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="f5dad-129">Per ulteriori informazioni, vedere [Campaign views in Office 365 ATP](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="f5dad-130">**Simulatore di attacco**: gli amministratori possono creare falsi messaggi di phishing e inviarli agli utenti interni come strumenti didattici.</span><span class="sxs-lookup"><span data-stu-id="f5dad-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="f5dad-131">Per ulteriori informazioni, vedere [Attack Simulator in Office 365 ATP](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="f5dad-132">Altre risorse anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f5dad-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="f5dad-133">Per gli utenti finali: [proteggersi da schemi di phishing e altre forme di frode online](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span><span class="sxs-lookup"><span data-stu-id="f5dad-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="f5dad-134">[In che modo Microsoft 365 convalida l'indirizzo del mittente per impedire il phishing](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="f5dad-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
