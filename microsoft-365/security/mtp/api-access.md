---
title: Accedere alle API di Microsoft 365 Defender
description: Informazioni su come accedere alle API di Microsoft 365 Defender
keywords: accesso, API, contesto dell'applicazione, contesto utente, applicazione AAD, token di accesso
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845019"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Accedere alle API di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche. Tali API consentiranno di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di Microsoft 365 Defender. L'accesso API richiede l'autenticazione OAuth 2.0. Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


In generale, è necessario eseguire la procedura seguente per utilizzare le API:
- Creare un'applicazione AAD
- Ottenere un token di accesso tramite questa applicazione
- Utilizzare il token per accedere a Microsoft 365 Defender API


È possibile accedere a Microsoft 365 Defender API con contesto dell' **applicazione** o **contesto utente**.

- **Contesto dell'applicazione: (scelta consigliata)** <br>
    Utilizzato dalle app eseguite senza un utente connesso. ad esempio, le app che vengono eseguite come servizi in background o demoni.

    Passaggi che è necessario eseguire per accedere a Microsoft 365 Defender API con contesto dell'applicazione:

  1. Creare un'applicazione Web AAD.
  2. Assegnare l'autorizzazione desiderata all'esempio applicationFor, **Incident. Read. All** , **AdvancedHunting. Read. All**. 
  3. Creare una chiave per l'applicazione.
  4. Ottenere il token utilizzando l'applicazione con la relativa chiave.
  5. Utilizzare il token per accedere a Microsoft 365 Defender API

     Per ulteriori informazioni, vedere [Get Access with Application context](api-create-app-web.md).


- **Contesto utente:** <br>
    Utilizzato per eseguire azioni nell'API per conto di un utente.

    Passaggi che è necessario eseguire per accedere a Microsoft 365 Defender API con contesto dell'applicazione:
  1. Creare un'applicazione nativa AAD.
  2. Assegnare l'autorizzazione desiderata per l'applicazione. Ad esempio, **Incident. Read** , **AdvancedHunting. Read**.
  3. Ottenere il token utilizzando l'applicazione con le credenziali utente.
  4. Utilizzare il token per accedere a Microsoft 365 Defender API

     Per ulteriori informazioni, vedere [ottenere l'accesso con il contesto utente](api-create-app-user-context.md).


## <a name="related-topics"></a>Argomenti correlati
- [API Microsoft 365 Defender](api-supported.md)
- [Accedere a Microsoft 365 Defender con contesto dell'applicazione](api-create-app-web.md)
- [Accedere a Microsoft 365 Defender con contesto utente](api-create-app-user-context.md)
