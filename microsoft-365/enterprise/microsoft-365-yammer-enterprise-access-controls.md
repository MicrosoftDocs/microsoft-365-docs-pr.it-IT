---
title: Controlli di accesso di Microsoft 365 Yammer Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo è incluso un breve riepilogo sui controlli di accesso di Yammer Enterprise nell'ambiente di produzione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332665"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="5923f-103">Controlli di accesso di Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="5923f-103">Yammer enterprise access controls</span></span> 

<span data-ttu-id="5923f-104">L'accesso fisico e logico all'ambiente di produzione di Yammer è limitato a un piccolo gruppo di utenti (Infrastructure and Operations).</span><span class="sxs-lookup"><span data-stu-id="5923f-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="5923f-105">Come per gli altri ingegneri di Microsoft 365, gli ingegneri di Yammer hanno accesso a zero diritti ai dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="5923f-105">As with other Microsoft 365 engineers, Yammer engineers have zero standing access to customer data.</span></span> <span data-ttu-id="5923f-106">L'accesso deve essere richiesto utilizzando un sistema di controllo dell'accesso basato su approvazione analogo all'archivio protetto con un numero limitato di responsabili approvazione.</span><span class="sxs-lookup"><span data-stu-id="5923f-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="5923f-107">I responsabili approvazione verificano la richiesta (ad esempio, verificano se la richiesta è legittima in base alle esigenze, al caso aziendale, al tempo e così via) e quindi approva o rifiuta la richiesta.</span><span class="sxs-lookup"><span data-stu-id="5923f-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="5923f-108">Se la richiesta viene approvata, l'accesso JIT viene concesso per un periodo di tempo definito e limitato.</span><span class="sxs-lookup"><span data-stu-id="5923f-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="5923f-109">Dopo aver superato il tempo di accesso, l'accesso scade automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5923f-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="5923f-110">Come per gli altri servizi Microsoft 365, tutti gli accessi all'ambiente di produzione di Yammer utilizzano l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="5923f-110">As with other Microsoft 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="5923f-111">Tutti gli accessi e la cronologia dei comandi vengono assegnati a un utente e registrati e recensiti regolarmente dal team di sicurezza di Yammer.</span><span class="sxs-lookup"><span data-stu-id="5923f-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="5923f-112">Per ulteriori informazioni sull'amministrazione e la gestione di Yammer, vedere la Guida di amministrazione di [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page).</span><span class="sxs-lookup"><span data-stu-id="5923f-112">For more information about Yammer administration and management, see [Yammer admin help](https://docs.microsoft.com/yammer/yammer-landing-page).</span></span>