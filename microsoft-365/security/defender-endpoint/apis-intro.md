---
title: Accedere a API di Microsoft Defender per endpoint .
ms.reviewer: ''
description: Informazioni su come usare le API per automatizzare i flussi di lavoro e innovare in base alle funzionalità di Microsoft Defender for Endpoint
keywords: API, API, wdatp, API aperta, Microsoft Defender per API endpoint, Microsoft Defender Atp, API pubblica, API supportate, avvisi, dispositivo, utente, dominio, IP, file, caccia avanzata, query
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
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571830"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Accedere a API di Microsoft Defender per endpoint . 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Si applica a:** 
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriviti per una prova gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint espone gran parte dei dati e delle azioni tramite un set di API a livello di programmazione. Tali API consentono di automatizzare i flussi di lavoro e innovare in base alle funzionalità di Defender for Endpoint. L'accesso all'API richiede l'autenticazione OAuth2.0. Per ulteriori informazioni, vedere [Codice di autorizzazione OAuth 2.0 Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Guarda questo video per una rapida panoramica delle API di Defender for Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

In generale, dovrai adottare i passaggi seguenti per usare le API:
- Creare [un'applicazione AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Ottenere un token di accesso utilizzando questa applicazione
- Utilizzare il token per accedere all'API Defender for Endpoint


È possibile accedere a Defender per l'API endpoint con **contesto applicazione** **o contesto utente**.

- **Contesto applicazione: (scelta consigliata)** <br>
    Usato dalle app eseguite senza un utente con accesso presente. ad esempio, app eseguite come servizi in background o daemon.

    Passaggi da adottare per accedere all'API Defender for Endpoint con il contesto dell'applicazione:

  1. Creare un'applicazione Web AAD.
  2. Assegnare l'autorizzazione desiderata all'applicazione, ad esempio 'Leggi avvisi', 'Isola computer'. 
  3. Creare una chiave per questa applicazione.
  4. Ottenere il token utilizzando l'applicazione con la sua chiave.
  5. Utilizzare il token per accedere all'API di Microsoft Defender for Endpoint

     Per ulteriori informazioni, vedere Ottenere [l'accesso con il contesto dell'applicazione](exposed-apis-create-app-webapp.md).


- **Contesto utente:** <br>
    Utilizzato per eseguire azioni nell'API per conto di un utente.

    Passaggi da adottare per accedere all'API Defender for Endpoint con il contesto dell'applicazione:

  1. Creare un'applicazione nativa AAD.
  2. Assegnare l'autorizzazione desiderata all'applicazione, ad esempio "Leggi avvisi", "Isola macchine" e così via. 
  3. Ottenere il token utilizzando l'applicazione con le credenziali utente.
  4. Utilizzare il token per accedere all'API di Microsoft Defender for Endpoint

     Per ulteriori informazioni, vedere [Ottenere l'accesso con il contesto utente](exposed-apis-create-app-nativeapp.md).


## <a name="related-topics"></a>Argomenti correlati
- [Microsoft Defender per API endpoint](exposed-apis-list.md)
- [Accedere a Microsoft Defender per endpoint con contesto dell'applicazione](exposed-apis-create-app-webapp.md)
- [Accedere a Microsoft Defender per endpoint con contesto utente](exposed-apis-create-app-nativeapp.md)
