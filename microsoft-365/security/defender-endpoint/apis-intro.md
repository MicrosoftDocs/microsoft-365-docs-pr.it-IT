---
title: Accedere a API di Microsoft Defender per endpoint .
ms.reviewer: ''
description: Informazioni su come usare le API per automatizzare i flussi di lavoro e innovare in base alle funzionalità di Microsoft Defender for Endpoint
keywords: api, api, Microsoft Defender for Endpoint, api aperte, Api Microsoft Defender for Endpoint, api pubbliche, api supportate, avvisi, dispositivo, utente, dominio, ip, file, ricerca avanzata, query
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 87dce8ff4fde505eb8d4e458c8d9fb56556f4d78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935107"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Accedere a API di Microsoft Defender per endpoint . 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Si applica a:** 
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint espone gran parte dei dati e delle azioni tramite un set di API programmatiche. Queste API ti consentiranno di automatizzare i flussi di lavoro e innovare in base alle funzionalità di Defender for Endpoint. L'accesso API richiede l'autenticazione OAuth2.0. Per ulteriori informazioni, vedere Flusso del codice di autorizzazione [OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Guarda questo video per una breve panoramica delle API di Defender for Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

In generale, dovrai eseguire la procedura seguente per usare le API:
- Creare un'applicazione AAD
- Ottenere un token di accesso con questa applicazione
- Usare il token per accedere all'API di Defender for Endpoint


Puoi accedere all'API defender per endpoint con **il contesto dell'applicazione** **o il contesto utente.**

- **Contesto applicazione: (scelta consigliata)** <br>
    Usato dalle app eseguite senza un utente connesso. ad esempio app eseguite come servizi in background o daemon.

    Passaggi da eseguire per accedere all'API defender per endpoint con il contesto dell'applicazione:

  1. Creare un'applicazione Web AAD.
  2. Assegnare l'autorizzazione desiderata all'applicazione, ad esempio "Avvisi di lettura", "Isola computer". 
  3. Crea una chiave per l'applicazione.
  4. Ottenere il token usando l'applicazione con la relativa chiave.
  5. Usare il token per accedere all'API di Microsoft Defender for Endpoint

     Per ulteriori informazioni, vedere [Ottenere l'accesso con il contesto dell'applicazione.](exposed-apis-create-app-webapp.md)


- **Contesto utente:** <br>
    Usato per eseguire azioni nell'API per conto di un utente.

    Passaggi da eseguire per accedere all'API defender per endpoint con il contesto dell'applicazione:

  1. Creare un'applicazione nativa di AAD.
  2. Assegnare l'autorizzazione desiderata all'applicazione, ad esempio "Avvisi di lettura", "Isola computer" e così via. 
  3. Ottenere il token usando l'applicazione con le credenziali utente.
  4. Usare il token per accedere all'API di Microsoft Defender for Endpoint

     Per ulteriori informazioni, vedere [Ottenere l'accesso con il contesto utente.](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Argomenti correlati
- [API di Microsoft Defender per endpoint](exposed-apis-list.md)
- [Accedere a Microsoft Defender for Endpoint con il contesto dell'applicazione](exposed-apis-create-app-webapp.md)
- [Accedere a Microsoft Defender per Endpoint con contesto utente](exposed-apis-create-app-nativeapp.md)
