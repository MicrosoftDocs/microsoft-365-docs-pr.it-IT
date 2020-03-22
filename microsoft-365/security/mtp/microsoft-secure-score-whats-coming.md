---
title: Che cosa viene in Microsoft Secure Score?
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, in che modo vengono calcolati i dettagli e quali amministratori della sicurezza possono aspettarsi.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895442"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="0398c-104">Che cosa viene in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="0398c-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="0398c-105">Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="0398c-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="0398c-106">Il Punteggio e il punteggio massimo possono variare.</span><span class="sxs-lookup"><span data-stu-id="0398c-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="0398c-107">Tuttavia, ciò non implica una modifica della posizione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0398c-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="0398c-108">Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="0398c-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="0398c-109">21 aprile 2020</span><span class="sxs-lookup"><span data-stu-id="0398c-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="0398c-110">Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili o che non forniscono una rappresentazione utile della posizione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0398c-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="0398c-111">Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0398c-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="0398c-112">Eliminare/bloccare gli account non utilizzati negli ultimi 30 giorni</span><span class="sxs-lookup"><span data-stu-id="0398c-112">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="0398c-113">Designare meno di 5 amministratori globali</span><span class="sxs-lookup"><span data-stu-id="0398c-113">Designate fewer than 5 global admins</span></span>
- <span data-ttu-id="0398c-114">Applicare la protezione IRM ai documenti</span><span class="sxs-lookup"><span data-stu-id="0398c-114">Apply IRM protections to documents</span></span>
- <span data-ttu-id="0398c-115">Applicare i criteri di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="0398c-115">Apply Data Loss Prevention policies</span></span>

### <a name="adding-additional-control-support-in-the-preview-version"></a><span data-ttu-id="0398c-116">Aggiunta di un ulteriore supporto di controllo nella versione di anteprima</span><span class="sxs-lookup"><span data-stu-id="0398c-116">Adding additional control support in the preview version</span></span>
- <span data-ttu-id="0398c-117">Non consentire agli utenti di concedere il consenso alle applicazioni non gestite (attualmente disponibili nella versione rilasciata)</span><span class="sxs-lookup"><span data-stu-id="0398c-117">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a><span data-ttu-id="0398c-118">Supporto per altre azioni di miglioramento della sicurezza delle app di Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="0398c-118">Support for additional Microsoft Cloud App Security improvement actions</span></span>
- <span data-ttu-id="0398c-119">Disabilitare il servizio spooler di stampa nei controller di dominio</span><span class="sxs-lookup"><span data-stu-id="0398c-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="0398c-120">Modificare le deleghe Kerberos non sicure per impedire la rappresentazione</span><span class="sxs-lookup"><span data-stu-id="0398c-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="0398c-121">Proteggere e gestire le password di amministratore locale con i giri Microsoft</span><span class="sxs-lookup"><span data-stu-id="0398c-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="0398c-122">Ridurre il rischio del percorso laterale per le entità sensibili</span><span class="sxs-lookup"><span data-stu-id="0398c-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="0398c-123">Rimuovere gli account dormienti dai gruppi sensibili</span><span class="sxs-lookup"><span data-stu-id="0398c-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="0398c-124">Rimuovere gli attributi di cronologia SID non sicuri dalle entità</span><span class="sxs-lookup"><span data-stu-id="0398c-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="0398c-125">Risolvere gli attributi degli account non sicuri</span><span class="sxs-lookup"><span data-stu-id="0398c-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="0398c-126">Interrompere l'esposizione delle credenziali del testo</span><span class="sxs-lookup"><span data-stu-id="0398c-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="0398c-127">Interrompere la comunicazione con i protocolli legacy</span><span class="sxs-lookup"><span data-stu-id="0398c-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="0398c-128">Interrompere l'utilizzo di crittografia debole</span><span class="sxs-lookup"><span data-stu-id="0398c-128">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="0398c-129">Supporto per i suggerimenti per la sicurezza di Microsoft Defender ATP Threat & vulnerabilità (TVM)</span><span class="sxs-lookup"><span data-stu-id="0398c-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>
- <span data-ttu-id="0398c-130">Tutti i suggerimenti per la sicurezza rilasciati forniti da TVM saranno ora disponibili anche in Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="0398c-130">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
