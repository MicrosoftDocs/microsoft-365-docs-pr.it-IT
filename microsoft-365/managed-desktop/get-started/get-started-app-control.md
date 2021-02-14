---
title: Introduzione al controllo delle applicazioni
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430460"
---
# <a name="get-started-with-app-control"></a>Introduzione al controllo delle applicazioni

Prima di abilitare il controllo delle app nel tuo ambiente, assicurati di esaminare e comprendere in che modo [Microsoft Managed Desktop](../service-description/app-control.md) lo implementa e i tuoi ruoli e responsabilità.

Microsoft Managed Desktop semplifica il controllo delle app prendendosi cura degli aspetti più impegnativi di ottenere un criterio di base sicuro. Gli amministratori IT devono comunque testare le app nell'anello Test ed esaminare i log per verificare la presenza di avvisi o errori. Se un'app necessita di un'esenzione, puoi richiedere una richiesta o Microsoft Managed Desktop Operation potrebbe, a seconda di chi la rileva per prima.

## <a name="initial-deployment-of-apps"></a>Distribuzione iniziale delle app

Quando distribuisci per la prima volta le app, Microsoft Managed Desktop deve valutarne il comportamento corrente. I passaggi esatti per abilitare il controllo delle app dipendono dal fatto che i dispositivi siano già stati distribuiti nel tuo ambiente.

### <a name="devices-not-yet-in-use"></a>Dispositivi non ancora in uso

Se non hai ancora dispositivi in uso, apri un ticket di servizio con Microsoft Managed Desktop Operations che richiede di attivare il controllo delle app. Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:

|Guida alla distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|First     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Giorno 2       |
|Generale     | Enforced        |  Giorno 3       |

È sempre possibile aprire un'altra richiesta di servizio per sospendere o eseguire il rollback di parte di questa distribuzione in qualsiasi momento durante l'implementazione.

### <a name="devices-already-in-use"></a>Dispositivi già in uso

Se è già in uso almeno un dispositivo Microsoft Managed Desktop, procedere come segue:

1. Apri un ticket di servizio con Microsoft Managed Desktop Operations che richiede di attivare il controllo dell'app. Le operazioni distribuiranno [un criterio di](../service-description/app-control.md#audit-policy) controllo a tutti i dispositivi.
2. [Testare le applicazioni](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) per verificare se ne verrebbero bloccate. Se un'applicazione viene bloccata, aprire una [richiesta del firmatario.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer) 
3. Dopo aver completato il test (indipendentemente dai risultati), notifica operazioni, segnalando eventuali richieste di firmatario in sospeso. Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:

|Guida alla distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|First     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Sospesa, implementazione su richiesta       |
|Generale     | Enforced        |  Sospesa, implementazione su richiesta       |

È sempre possibile aprire un'altra richiesta di servizio per sospendere o eseguire il rollback di parte di questa distribuzione in qualsiasi momento durante l'implementazione.



