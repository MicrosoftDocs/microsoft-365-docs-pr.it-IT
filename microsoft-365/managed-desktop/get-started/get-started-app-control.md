---
title: Iniziare a utilizzare il controllo app
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170710"
---
# <a name="get-started-with-app-control"></a>Iniziare a utilizzare il controllo app

Prima di abilitare il controllo delle app nel proprio ambiente, controllare e comprendere in che [modo Microsoft Managed Desktop lo implementa](../service-description/app-control.md) e i ruoli e le responsabilità.

Microsoft Managed Desktop semplifica il controllo delle app prendendo in considerazione gli aspetti più impegnativi per ottenere un criterio di base sicuro. Gli amministratori IT devono comunque testare le app nell'anello di testing e controllare i registri per eventuali avvisi o errori. Se un'applicazione ha bisogno di un'esenzione, è possibile archiviare una richiesta o potrebbe essere attiva l'operazione Microsoft Managed Desktop, a seconda di chi lo rileva per primo.

## <a name="initial-deployment-of-apps"></a>Distribuzione iniziale delle app

Quando si distribuisce per la prima volta le app, Microsoft Managed Desktop deve valutare il comportamento corrente. Gli esatti passaggi per l'abilitazione del controllo app dipendono dal fatto che i dispositivi siano già stati distribuiti nell'ambiente in uso.

### <a name="devices-already-in-use"></a>Dispositivi già in uso

Se è già in uso almeno un dispositivo Microsoft Managed Desktop, attenersi alla seguente procedura:

1. Aprire un ticket di servizio con Microsoft Managed Desktop Operations che richiede l'attivazione del controllo app. Le operazioni distribuiranno un [criterio di controllo](../service-description/app-control.md#audit-policy) su tutti i dispositivi.
2. [Testare le applicazioni](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) per verificare se sono state bloccate. Se un'applicazione verrebbe bloccata, aprire una [richiesta del firmatario](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Dopo aver completato il testing (indipendentemente dai risultati), informare le operazioni, rilevando eventuali richieste del firmatario in sospeso. Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo la seguente pianificazione:

|Gruppo di distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|Prima     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Giorno 3       |
|Ampio     | Enforced        |  Giorno 7       |

È sempre possibile aprire un'altra richiesta di servizio per sospendere o ripristinare parte di questa distribuzione in qualsiasi momento durante l'implementazione.

### <a name="devices-not-yet-in-use"></a>Dispositivi non ancora in uso

Se non si dispone ancora di alcun dispositivo in uso, aprire un ticket di servizio con Microsoft Managed Desktop Operations che richiede l'attivazione del controllo app. Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo la seguente pianificazione:

|Gruppo di distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|Prima     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Giorno 3       |
|Ampio     | Enforced        |  Giorno 7       |

È sempre possibile aprire un'altra richiesta di servizio per sospendere o ripristinare parte di questa distribuzione in qualsiasi momento durante l'implementazione.

