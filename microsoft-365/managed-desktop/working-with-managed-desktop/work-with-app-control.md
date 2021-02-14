---
title: Usare il controllo delle applicazioni
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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289460"
---
# <a name="work-with-app-control"></a>Usare il controllo delle applicazioni

Dopo la distribuzione del controllo delle app nell'ambiente, sia l'utente che Microsoft Managed Desktop Operations hanno responsabilità continue. Ad esempio, potresti voler aggiungere una nuova app nell'ambiente o aggiungere (o rimuovere) un firmatario attendibile. Per migliorare la sicurezza, tutte le app devono essere firmate con codice prima di rilasciarle agli utenti. I dettagli dell'autore di un'app includono informazioni sul firmatario.


## <a name="add-a-new-app"></a>Aggiungere una nuova app

Per aggiungere una nuova app, segui questi passaggi:

1. Aggiungere l'app a [Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)
2. Distribuisci l'app in qualsiasi dispositivo nell'anello Test. 
3. Testa la tua app in base ai processi aziendali standard. 
4. Controlla Visualizzatore eventi in **Registri applicazioni e servizi\Microsoft\Windows\AppLocker,** cercando eventuali eventi **8003** **o 8006.** Questi eventi indicano che l'app verrebbe bloccata. Per altre informazioni su tutti gli eventi di App Locker e sul relativo significato, vedi [Uso del Visualizzatore eventi con AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)
5. Se si trova uno di questi eventi, aprire una richiesta di firmatario con Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Aggiungere (o rimuovere) un firmatario attendibile

Quando apri una richiesta di firmatario, devi prima fornire alcuni dettagli importanti sull'autore. Eseguire quindi la procedura seguente:

1. [Raccogliere i dettagli dell'autore.](#gather-publisher-details)
2. Aprire un ticket con Microsoft Managed Desktop Operations per richiedere la regola firmatario e includere i dettagli seguenti:  
    - Nome applicazione 
    - Versione dell'applicazione 
    - Descrizione 
    - Tipo di modifica ("aggiungi" o "rimuovi")  
    - Dettagli dell'autore (ad esempio: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Per rimuovere l'attendibilità per un'app, segui gli stessi passaggi, ma imposta **Modifica tipo** per *rimuovere*.

Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:


|Guida alla distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|First     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Giorno 2       |
|Generale     | Enforced        |  Giorno 3       |


È possibile sospendere o eseguire il rollback della distribuzione in qualsiasi momento durante l'implementazione. A tale scopo, aprire un'altra richiesta di servizio con Operazioni.

> [!NOTE]
> Se si sospende il rilascio di una regola firmatario, è necessario eseguire il rollback o il completamento di tale regola prima di avviare un'altra implementazione.

## <a name="gather-publisher-details"></a>Raccogliere i dettagli dell'autore

Per accedere ai dati dell'autore per un'app, segui questi passaggi:

1. Trova un dispositivo Microsoft Managed Desktop nell'anello Test a cui è applicato un criterio modalità di controllo. 
2. Tenta di installare l'app nel dispositivo.
3. Aprire il Visualizzatore eventi in tale dispositivo. 
4. Nel Visualizzatore eventi passa a **Registri applicazioni e servizi\Microsoft\Windows** e quindi seleziona **AppLocker.** 
5. Trovare qualsiasi **evento 8003** **o 8006** e quindi copiare le informazioni dall'evento: 
    - Nome applicazione 
    - Versione dell'applicazione 
    - Descrizione 
    - Dettagli dell'autore (ad esempio: "O= <publisher name> , L= <location> , S=State, C=Country") 
