---
title: Accedere alle API di Microsoft Threat Protection
description: Informazioni su come accedere alle API di Microsoft Threat Protection
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
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650386"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>Accedere alle API di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Microsoft Threat Protection espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche. Tali API consentiranno di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di protezione dalle minacce di Microsoft. L'accesso API richiede l'autenticazione OAuth 2.0. Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


In generale, è necessario eseguire la procedura seguente per utilizzare le API:
- Creare un'applicazione AAD
- Ottenere un token di accesso tramite questa applicazione
- Utilizzare il token per accedere all'API di Microsoft Threat Protection


È possibile accedere all'API Microsoft Threat Protection con contesto dell' **applicazione** o **contesto utente**.

- **Contesto dell'applicazione: (scelta consigliata)** <br>
    Utilizzato dalle app eseguite senza un utente connesso. ad esempio, le app che vengono eseguite come servizi in background o demoni.

    Passaggi da eseguire per accedere all'API di Microsoft Threat Protection con il contesto dell'applicazione:

  1. Creare un'applicazione Web AAD.
  2. Assegnare l'autorizzazione desiderata all'esempio applicationFor, **Incident. Read. All**, **AdvancedHunting. Read. All**. 
  3. Creare una chiave per l'applicazione.
  4. Ottenere il token utilizzando l'applicazione con la relativa chiave.
  5. Utilizzare il token per accedere all'API di Microsoft Threat Protection

     Per ulteriori informazioni, vedere [Get Access with Application context](api-create-app-web.md).


- **Contesto utente:** <br>
    Utilizzato per eseguire azioni nell'API per conto di un utente.

    Passaggi da eseguire per accedere all'API di Microsoft Threat Protection con il contesto dell'applicazione:
  1. Creare un'applicazione nativa AAD.
  2. Assegnare l'autorizzazione desiderata per l'applicazione. Ad esempio, **Incident. Read**, **AdvancedHunting. Read**.
  3. Ottenere il token utilizzando l'applicazione con le credenziali utente.
  4. Utilizzare il token per accedere all'API di Microsoft Threat Protection

     Per ulteriori informazioni, vedere [ottenere l'accesso con il contesto utente](api-create-app-user-context.md).


## <a name="related-topics"></a>Argomenti correlati
- [API di Microsoft Threat Protection](api-supported.md)
- [Accedere a Microsoft Threat Protection con il contesto dell'applicazione](api-create-app-web.md)
- [Accedere a Microsoft Threat Protection con contesto utente](api-create-app-user-context.md)
