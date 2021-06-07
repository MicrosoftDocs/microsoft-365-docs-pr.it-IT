---
title: Esplora API in Microsoft Defender per endpoint
ms.reviewer: ''
description: Usare Esplora API per creare ed eseguire query API, testare e inviare richieste per qualsiasi API disponibile
keywords: api, explorer, inviare, richiedere, ottenere, pubblicare,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769798"
---
# <a name="api-explorer"></a>Esplora API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)


Microsoft Defender for Endpoint API Explorer è uno strumento che consente di esplorare in modo interattivo diverse API di Defender for Endpoint. 

Esplora API semplifica la creazione e l'esecuzione di query API, test e invio di richieste per qualsiasi endpoint API Defender for Endpoint disponibile. Usa Esplora API per eseguire azioni o trovare dati che potrebbero non essere ancora disponibili tramite l'interfaccia utente.

Lo strumento è utile durante lo sviluppo di app. Consente di eseguire query API che rispettino le impostazioni di accesso degli utenti, riducendo la necessità di generare token di accesso.

È inoltre possibile utilizzare lo strumento per esplorare la raccolta di query di esempio, copiare esempi di codice dei risultati e generare informazioni di debug.

Con Esplora API puoi:

- Eseguire richieste per qualsiasi metodo e visualizzare le risposte in tempo reale
- Sfoglia rapidamente gli esempi di API e scopri quali parametri supportano
- Effettuare chiamate API con facilità; non è necessario eseguire l'autenticazione oltre l'accesso al portale di gestione

## <a name="access-api-explorer"></a>Esplora API di Access

Nel menu di spostamento a sinistra seleziona **Partner & API**  >  **Explorer.**

## <a name="supported-apis"></a>API supportate

Esplora API supporta tutte le API offerte da Defender per Endpoint.
  
L'elenco delle API supportate è disponibile nella documentazione [relativa alle API.](apis-intro.md) 

## <a name="get-started-with-the-api-explorer"></a>Introduzione a Esplora API

1. Nel riquadro sinistro è disponibile un elenco di richieste di esempio che è possibile utilizzare. 
2. Seguire i collegamenti e fare clic **su Esegui query**. 

Per alcuni esempi potrebbe essere necessario specificare un parametro nell'URL, ad esempio {machine- ID}.

## <a name="faq"></a>Domande frequenti

**Devo avere un token API per usare Esplora API?** <br>
Le credenziali per accedere a un'API non sono necessarie. Esplora API usa il token defender per il portale di gestione degli endpoint ogni volta che effettua una richiesta.

La credenziale di autenticazione utente con accesso viene usata per verificare che Esplora API sia autorizzato ad accedere ai dati per tuo conto.

Le richieste API specifiche sono limitate in base ai privilegi RBAC. Ad esempio, una richiesta di "indicatore di invio" è limitata al ruolo di amministratore della sicurezza. 
