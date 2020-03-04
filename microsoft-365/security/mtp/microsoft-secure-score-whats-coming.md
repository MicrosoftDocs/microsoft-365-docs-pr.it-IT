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
# <a name="whats-coming-in-microsoft-secure-score"></a>Che cosa viene in Microsoft Secure Score?

Per rendere Microsoft Secure Score un migliore rappresentante della posizione di sicurezza e migliorare l'usabilità, vengono apportate alcune modifiche nel prossimo futuro. Il Punteggio e il punteggio massimo possono variare. Tuttavia, ciò non implica una modifica della posizione di sicurezza.

Per informazioni sulle modifiche recenti, vedere [What ' s New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>16 marzo 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Rimozione di azioni di miglioramento che non soddisfano le aspettative per misure affidabili o che non forniscono una rappresentazione utile della posizione di sicurezza

Per assicurarsi che il Punteggio Microsoft Secure sia significativo e che ogni azione di miglioramento sia misurabile e affidabile, vengono eliminate le azioni di miglioramento riportate di seguito.

- Archiviare i documenti degli utenti in OneDrive for business
- Impostare i criteri degli allegati sicuri di Office 365 ATP
- Configurare i collegamenti sicuri di Office 365 per verificare gli URL
- Non consentire la delega delle cassette postali
- Consenti collegamenti di condivisione guest anonimi per siti e documenti
- Abilitare la console di protezione delle app Cloud
- Configurare la data di scadenza per i collegamenti di condivisione esterna

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Supporto delle impostazioni predefinite per la sicurezza per le azioni di miglioramento di Azure AD

Microsoft Secure Score aggiornerà le azioni di miglioramento per supportare le impostazioni predefinite per la [sicurezza di Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), che facilitano la protezione dell'organizzazione con quelle preconfigurate per gli attacchi più comuni.

Influenzerà le operazioni di miglioramento seguenti:

- Garantire che tutti gli utenti possano completare l'autenticazione a più fattori per l'accesso sicuro
- Richiedere l'AMF per i ruoli amministrativi
- Abilitazione del criterio per bloccare l'autenticazione legacy
