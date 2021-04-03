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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle funzionalità di protezione anti-phishing in Exchange Online Protection (EOP) e Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a100e28ddee1629b2fe35e28742a43b891d13e57
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570613"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="882ec-103">Protezione anti-phishing in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="882ec-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="882ec-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="882ec-104">**Applies to**</span></span>
- [<span data-ttu-id="882ec-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="882ec-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="882ec-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="882ec-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="882ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="882ec-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="882ec-108">*Il phishing* è un attacco tramite posta elettronica che tenta di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="882ec-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="882ec-109">Esistono categorie specifiche di phishing.</span><span class="sxs-lookup"><span data-stu-id="882ec-109">There are specific categories of phishing.</span></span> <span data-ttu-id="882ec-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="882ec-110">For example:</span></span>

- <span data-ttu-id="882ec-111">**Il spear phishing** usa contenuto mirato e personalizzato specifico per i destinatari di destinazione (in genere, dopo la ricognizione dei destinatari da parte dell'autore dell'attacco).</span><span class="sxs-lookup"><span data-stu-id="882ec-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="882ec-112">**La caccia alle baleni** è rivolta ai dirigenti o ad altri obiettivi di alto valore all'interno di un'organizzazione per il massimo effetto.</span><span class="sxs-lookup"><span data-stu-id="882ec-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="882ec-113">La compromissione della posta elettronica aziendale **(BEC)** utilizza mittenti attendibili contraffatti (responsabili finanziari, clienti, partner attendibili e così via) per indurre i destinatari ad approvare pagamenti, trasferire fondi o rivelare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="882ec-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span> <span data-ttu-id="882ec-114">Per ulteriori informazioni, guardare [questo video.](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)</span><span class="sxs-lookup"><span data-stu-id="882ec-114">Learn more by watching [this video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).</span></span>

- <span data-ttu-id="882ec-115">**Ransomware** che crittografa i dati e richiede il pagamento per decrittografarlo quasi sempre inizia nei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="882ec-115">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="882ec-116">La protezione anti-phishing non può aiutarti a decrittografare i file crittografati, ma può aiutare a rilevare i messaggi di phishing iniziali associati alla campagna ransomware.</span><span class="sxs-lookup"><span data-stu-id="882ec-116">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="882ec-117">Per ulteriori informazioni sul ripristino da un attacco ransomware, vedere [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="882ec-117">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="882ec-118">Con la crescente complessità degli attacchi, è anche difficile per gli utenti addestrati identificare i messaggi di phishing sofisticati.</span><span class="sxs-lookup"><span data-stu-id="882ec-118">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="882ec-119">Fortunatamente, Exchange Online Protection (EOP) e le funzionalità aggiuntive in Microsoft Defender per Office 365 possono essere utili.</span><span class="sxs-lookup"><span data-stu-id="882ec-119">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="882ec-120">Protezione anti-phishing in EOP</span><span class="sxs-lookup"><span data-stu-id="882ec-120">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="882ec-121">EOP (ovvero, le organizzazioni di Microsoft 365 senza Microsoft Defender per Office 365) contiene funzionalità che consentono di proteggere l'organizzazione dalle minacce di phishing:</span><span class="sxs-lookup"><span data-stu-id="882ec-121">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="882ec-122">**Spoof Intelligence**: per esaminare i messaggi falsificati inviati da mittenti in domini interni ed esterni e consentire o bloccare tali mittenti.</span><span class="sxs-lookup"><span data-stu-id="882ec-122">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="882ec-123">Per ulteriori informazioni, vedere [Configure spoof intelligence in EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="882ec-123">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="882ec-124">Criteri **anti-phishing in EOP:** attivare o disattivare l'intelligence di spoofing, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e specificare l'azione per i mittenti falsificati bloccati (passare alla cartella Posta indesiderata o alla quarantena).</span><span class="sxs-lookup"><span data-stu-id="882ec-124">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="882ec-125">Per ulteriori informazioni, vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="882ec-125">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="882ec-126">Autenticazione implicita della posta elettronica **:** EOP migliora i controlli di autenticazione della posta elettronica standard per la posta elettronica in ingresso ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC)](use-dmarc-to-validate-email.md)con reputazione mittente, cronologia mittente, cronologia dei destinatari, analisi comportamentali e altre tecniche avanzate per identificare i mittenti contraffatti.</span><span class="sxs-lookup"><span data-stu-id="882ec-126">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="882ec-127">Per altre informazioni, vedere [Autenticazione di posta elettronica in Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="882ec-127">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="882ec-128">Protezione anti-phishing aggiuntiva in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="882ec-128">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="882ec-129">Microsoft Defender per Office 365 contiene funzionalità anti-phishing aggiuntive e più avanzate:</span><span class="sxs-lookup"><span data-stu-id="882ec-129">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="882ec-130">Criteri **anti-phishing in Microsoft Defender per Office 365:** creare nuovi criteri personalizzati, configurare le impostazioni di anti-rappresentazione (proteggere utenti e domini dalla rappresentazione), impostazioni di intelligence delle cassette postali e soglie di phishing avanzate regolabili.</span><span class="sxs-lookup"><span data-stu-id="882ec-130">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="882ec-131">Per ulteriori informazioni, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="882ec-131">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="882ec-132">Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in EOP e i criteri anti-phishing in Defender per Office 365, vedere [Criteri anti-phishing in Microsoft 365.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="882ec-132">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="882ec-133">**Visualizzazioni campagna**: Machine learning e altre euristiche identificano e analizzano i messaggi coinvolti in attacchi di phishing coordinati contro l'intero servizio e l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="882ec-133">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="882ec-134">Per ulteriori informazioni, vedere [Visualizzazioni campagna in Microsoft Defender per Office 365.](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="882ec-134">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="882ec-135">**Simulatore di** attacco: gli amministratori possono creare messaggi di phishing falsi e inviarli agli utenti interni come strumento didattico.</span><span class="sxs-lookup"><span data-stu-id="882ec-135">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="882ec-136">Per ulteriori informazioni, vedere [Simulatore di attacco in Microsoft Defender per Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="882ec-136">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="882ec-137">Altre risorse anti-phishing</span><span class="sxs-lookup"><span data-stu-id="882ec-137">Other anti-phishing resources</span></span>

- <span data-ttu-id="882ec-138">Per gli utenti finali: [proteggersi dagli schemi di phishing e altre forme di frode online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="882ec-138">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="882ec-139">[In che modo Microsoft 365 convalida l'indirizzo From per impedire il phishing.](how-office-365-validates-the-from-address.md)</span><span class="sxs-lookup"><span data-stu-id="882ec-139">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
