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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372004"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="62b4e-104">Che cosa viene in Microsoft Secure Score?</span><span class="sxs-lookup"><span data-stu-id="62b4e-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="62b4e-105">Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="62b4e-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="62b4e-106">Il Punteggio e il punteggio massimo possono variare.</span><span class="sxs-lookup"><span data-stu-id="62b4e-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="62b4e-107">Tuttavia, ciò non implica una modifica della posizione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="62b4e-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="62b4e-108">Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="62b4e-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="62b4e-109">16 marzo 2020</span><span class="sxs-lookup"><span data-stu-id="62b4e-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="62b4e-110">Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili o che non forniscono una rappresentazione utile della posizione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="62b4e-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="62b4e-111">Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="62b4e-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="62b4e-112">Archiviare i documenti degli utenti in OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="62b4e-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="62b4e-113">Impostare i criteri degli allegati sicuri di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="62b4e-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="62b4e-114">Configurare i collegamenti sicuri di Office 365 per verificare gli URL</span><span class="sxs-lookup"><span data-stu-id="62b4e-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="62b4e-115">Non consentire la delega delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="62b4e-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="62b4e-116">Consenti collegamenti di condivisione guest anonimi per siti e documenti</span><span class="sxs-lookup"><span data-stu-id="62b4e-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="62b4e-117">Abilitare la console di protezione delle app Cloud</span><span class="sxs-lookup"><span data-stu-id="62b4e-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="62b4e-118">Configurare la data di scadenza per i collegamenti di condivisione esterna</span><span class="sxs-lookup"><span data-stu-id="62b4e-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="62b4e-119">Supporto delle impostazioni predefinite per la sicurezza per le azioni di miglioramento di Azure AD</span><span class="sxs-lookup"><span data-stu-id="62b4e-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="62b4e-120">Microsoft Secure Score aggiornerà le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza di Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.</span><span class="sxs-lookup"><span data-stu-id="62b4e-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="62b4e-121">Influenzerà le operazioni di miglioramento seguenti:</span><span class="sxs-lookup"><span data-stu-id="62b4e-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="62b4e-122">Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro</span><span class="sxs-lookup"><span data-stu-id="62b4e-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="62b4e-123">Richiedere l'AMF per i ruoli amministrativi</span><span class="sxs-lookup"><span data-stu-id="62b4e-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="62b4e-124">Abilitazione del criterio per bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="62b4e-124">Enable policy to block legacy authentication</span></span>
