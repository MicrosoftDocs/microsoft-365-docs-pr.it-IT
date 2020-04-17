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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541108"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="00aad-104">Che cosa viene in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="00aad-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="00aad-105">Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="00aad-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="00aad-106">Il Punteggio e il punteggio massimo possono variare.</span><span class="sxs-lookup"><span data-stu-id="00aad-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="00aad-107">Tuttavia, ciò non implica una modifica della posizione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="00aad-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="00aad-108">Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="00aad-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="00aad-109">21 aprile 2020</span><span class="sxs-lookup"><span data-stu-id="00aad-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="00aad-110">Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili o che non forniscono una rappresentazione utile della posizione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="00aad-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="00aad-111">Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="00aad-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="00aad-112">Applicare la protezione IRM ai documenti</span><span class="sxs-lookup"><span data-stu-id="00aad-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="00aad-113">Applicare i criteri di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="00aad-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="00aad-114">Aggiunta dell'azione di miglioramento di Azure AD nella versione di anteprima</span><span class="sxs-lookup"><span data-stu-id="00aad-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="00aad-115">Non consentire agli utenti di concedere il consenso alle applicazioni non gestite (attualmente disponibili nella versione rilasciata)</span><span class="sxs-lookup"><span data-stu-id="00aad-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="00aad-116">Aggiunta delle azioni di miglioramento di Azure ATP nella versione di anteprima</span><span class="sxs-lookup"><span data-stu-id="00aad-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="00aad-117">Disabilitare il servizio spooler di stampa nei controller di dominio</span><span class="sxs-lookup"><span data-stu-id="00aad-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="00aad-118">Modificare le deleghe Kerberos non sicure per impedire la rappresentazione</span><span class="sxs-lookup"><span data-stu-id="00aad-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="00aad-119">Proteggere e gestire le password di amministratore locale con i giri Microsoft</span><span class="sxs-lookup"><span data-stu-id="00aad-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="00aad-120">Ridurre il rischio del percorso laterale per le entità sensibili</span><span class="sxs-lookup"><span data-stu-id="00aad-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="00aad-121">Rimuovere gli account dormienti dai gruppi sensibili</span><span class="sxs-lookup"><span data-stu-id="00aad-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="00aad-122">Rimuovere gli attributi di cronologia SID non sicuri dalle entità</span><span class="sxs-lookup"><span data-stu-id="00aad-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="00aad-123">Risolvere gli attributi degli account non sicuri</span><span class="sxs-lookup"><span data-stu-id="00aad-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="00aad-124">Interrompere l'esposizione delle credenziali del testo</span><span class="sxs-lookup"><span data-stu-id="00aad-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="00aad-125">Interrompere la comunicazione con i protocolli legacy</span><span class="sxs-lookup"><span data-stu-id="00aad-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="00aad-126">Interrompere l'utilizzo di crittografia debole</span><span class="sxs-lookup"><span data-stu-id="00aad-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="00aad-127">Supporto per i suggerimenti per la sicurezza di Microsoft Defender ATP Threat & vulnerabilità (TVM) nella versione di anteprima</span><span class="sxs-lookup"><span data-stu-id="00aad-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="00aad-128">Tutti i suggerimenti per la sicurezza rilasciati forniti da TVM saranno ora disponibili anche in Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="00aad-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
