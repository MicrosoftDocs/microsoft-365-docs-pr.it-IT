---
title: Introduzione al controllo delle applicazioni
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
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

Prima di abilitare il controllo delle app nell'ambiente, assicurati di esaminare e comprendere in che modo Microsoft Managed Desktop [implementarlo](../service-description/app-control.md) e i ruoli e le responsabilità.

Microsoft Managed Desktop semplifica il controllo delle app prendendosi cura degli aspetti più impegnativi di ottenere un criterio di base sicuro. Gli amministratori IT devono comunque testare le app nell'anello test ed esaminare i registri per eventuali avvisi o errori. Se un'app necessita di un'esenzione, puoi determinare se è possibile determinare Microsoft Managed Desktop richiesta, a seconda di chi la rileva per prima.

## <a name="initial-deployment-of-apps"></a>Distribuzione iniziale delle app

Quando distribuisci le app per la Microsoft Managed Desktop, devi valutarne il comportamento corrente. I passaggi esatti per abilitare il controllo delle app dipendono dal fatto che i dispositivi siano già stati distribuiti nell'ambiente.

### <a name="devices-not-yet-in-use"></a>Dispositivi non ancora in uso

Se non hai ancora dispositivi in uso, apri un ticket di servizio con Microsoft Managed Desktop Operations che richiede di attivare il controllo dell'app. Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:

|Guida alla distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|First     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Giorno 2       |
|Broad     | Enforced        |  Giorno 3       |

È sempre possibile aprire un'altra richiesta di servizio per sospendere o eseguire il rollback di parte della distribuzione in qualsiasi momento durante l'implementazione.

### <a name="devices-already-in-use"></a>Dispositivi già in uso

Se è già in uso almeno Microsoft Managed Desktop dispositivo, eseguire la procedura seguente:

1. Apri un ticket di servizio con Microsoft Managed Desktop Operations che richiede di attivare il controllo dell'app. Le operazioni [distribuiranno un criterio di](../service-description/app-control.md#audit-policy) controllo in tutti i dispositivi.
2. [Testare le applicazioni](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) per verificare se ne verrebbero bloccate. Se un'applicazione viene bloccata, aprire una [richiesta di firmatario.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer) 
3. Dopo aver completato il test (indipendentemente dai risultati), invia una notifica alle operazioni, segnalando eventuali richieste di firmatario in sospeso. Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:

|Guida alla distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|First     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  In pausa, implementazione su richiesta       |
|Broad     | Enforced        |  In pausa, implementazione su richiesta       |

È sempre possibile aprire un'altra richiesta di servizio per sospendere o eseguire il rollback di parte della distribuzione in qualsiasi momento durante l'implementazione.



