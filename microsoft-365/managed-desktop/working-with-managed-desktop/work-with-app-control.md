---
title: Usare il controllo delle applicazioni
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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917641"
---
# <a name="work-with-app-control"></a>Usare il controllo delle applicazioni

Dopo la distribuzione del controllo dell'app nell'ambiente, sia tu che Microsoft Managed Desktop Operations avete responsabilità continue. Ad esempio, potresti voler aggiungere una nuova app nell'ambiente o aggiungere (o rimuovere) un firmatario attendibile. Per migliorare la sicurezza, tutte le app devono essere firmate con codice prima di rilasciarle agli utenti. I dettagli dell'autore di un'app includono informazioni sul firmatario.


## <a name="add-a-new-app"></a>Aggiungere una nuova app

Per aggiungere una nuova app, segui questi passaggi:

1. Aggiungere l'app a [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).
2. Distribuisci l'app in qualsiasi dispositivo nell'anello Test. 
3. Testa la tua app in base ai processi aziendali standard. 
4. Controlla Visualizzatore eventi in Registri applicazioni e **servizi\Microsoft\Windows\AppLocker,** cercando eventuali eventi **8003** o **8006.** Questi eventi indicano che l'app verrà bloccata. Per altre informazioni su tutti gli eventi di App Locker e sui relativi significati, vedi [Uso del Visualizzatore eventi con AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)
5. Se si trova uno di questi eventi, aprire una richiesta di firmatario con Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Aggiungere (o rimuovere) un firmatario attendibile

Quando si apre una richiesta di firmatario, è necessario fornire prima alcuni dettagli importanti sull'autore. Eseguire quindi la procedura seguente:

1. [Raccogliere i dettagli dell'autore](#gather-publisher-details).
2. Aprire un ticket con Microsoft Managed Desktop Operations per richiedere la regola del firmatario e includere i dettagli seguenti:  
    - Nome applicazione 
    - Versione dell'applicazione 
    - Descrizione 
    - Tipo di modifica ("aggiungi" o "rimuovi")  
    - Dettagli dell'autore (ad esempio: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Per rimuovere l'attendibilità per un'app, segui gli stessi passaggi, ma imposta **Cambia tipo** su *rimuovi*.

Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo questa pianificazione:


|Guida alla distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|First     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Giorno 2       |
|Broad     | Enforced        |  Giorno 3       |


È possibile sospendere o eseguire il rollback della distribuzione in qualsiasi momento durante l'implementazione. A tale scopo, aprire un'altra richiesta di servizio con Operations.

> [!NOTE]
> Se si sospende il rilascio di una regola del firmatario, è necessario eseguire il rollback o il completamento della regola prima di avviare un'altra implementazione.

## <a name="gather-publisher-details"></a>Raccogliere i dettagli dell'autore

Per accedere ai dati dell'autore per un'app, segui questi passaggi:

1. Trova un dispositivo Microsoft Managed Desktop nell'anello test a cui è applicato un criterio modalità di controllo. 
2. Prova a installare l'app nel dispositivo.
3. Apri visualizzatore eventi in tale dispositivo. 
4. Nel Visualizzatore eventi passare a Registri applicazioni e **servizi\Microsoft\Windows** e quindi selezionare **AppLocker.** 
5. Trova qualsiasi **evento 8003** o **8006** e quindi copia le informazioni dall'evento: 
    - Nome applicazione 
    - Versione dell'applicazione 
    - Descrizione 
    - Dettagli dell'autore (ad esempio: "O= <publisher name> , L= <location> , S=State, C=Country")