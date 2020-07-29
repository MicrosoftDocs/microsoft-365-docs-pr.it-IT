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
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430448"
---
# <a name="work-with-app-control"></a>Usare il controllo delle applicazioni

Una volta che il controllo app è stato distribuito nell'ambiente in uso, sia le operazioni di Microsoft Managed Desktop che quelle gestite hanno responsabilità continuative. Ad esempio, è possibile aggiungere una nuova app nell'ambiente o aggiungere (o rimuovere) un firmatario attendibile. Per migliorare la sicurezza, tutte le app devono essere firmate con codice prima di rilasciarle agli utenti finali. I dettagli dell'editore di un'app includono informazioni sul firmatario.


## <a name="add-a-new-app"></a>Aggiungere una nuova app

Per aggiungere una nuova app, eseguire la procedura seguente:

1. Aggiungere l'app a [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).
2. Distribuire l'app a qualsiasi dispositivo nell'anello di test. 
3. Testare l'app in base ai processi aziendali standard. 
4. Controllare il Visualizzatore eventi in **Logs\Microsoft\Windows\AppLocker di applicazioni e servizi**, cercando qualsiasi evento **8003** o **8006** . Questi eventi indicano che l'applicazione verrebbe bloccata. Per ulteriori informazioni su tutti gli eventi degli armadietti delle app e sui relativi significati, vedere [using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Se si trova uno qualsiasi di questi eventi, aprire una richiesta di firmatario con le operazioni di Microsoft Managed Desktop.

## <a name="add-or-remove-a-trusted-signer"></a>Aggiungere (o rimuovere) un firmatario attendibile

Quando si apre una richiesta del firmatario, è necessario prima fornire alcuni dettagli importanti dell'editore. Eseguire quindi la procedura seguente:

1. [Raccogliere i dettagli dell'editore](#gather-publisher-details).
2. Aprire un ticket con le operazioni di Microsoft Managed Desktop per richiedere la regola del firmatario e includere i dettagli seguenti:  
    - Nome applicazione 
    - Versione dell'applicazione 
    - Descrizione 
    - Tipo di modifica ("Aggiungi" o "Rimuovi")  
    - Dettagli editore (ad esempio: "O = <publisher name> , L = <location> , S = stato, C = paese") 

> [!NOTE]
> Per rimuovere la relazione di trust per un'app, eseguire gli stessi passaggi, ma impostare **tipo di modifica** da *rimuovere*.

Le operazioni distribuiranno progressivamente i criteri ai gruppi di distribuzione seguendo la seguente pianificazione:


|Guida alla distribuzione  |Tipo di criterio  |Tempistiche  |
|---------|---------|---------|
|Test     |  Audit       |  Giorno 0       |
|Prima     | Enforced        | Giorno 1        |
|Veloce     | Enforced        |  Giorno 2       |
|Ampio     | Enforced        |  Giorno 3       |


È possibile sospendere o eseguire il rollback della distribuzione in qualsiasi momento durante l'implementazione. A tale scopo, aprire un'altra richiesta di servizio con le operazioni.

> [!NOTE]
> Se si sospende la liberazione di una regola del firmatario, è necessario eseguire il rollback o il completamento di una regola prima che sia possibile avviare un'altra implementazione.

## <a name="gather-publisher-details"></a>Raccogliere i dettagli dell'editore

Per accedere ai dati del server di pubblicazione per un'app, eseguire la procedura seguente:

1. Individuare un dispositivo Microsoft Managed Desktop nell'anello di testing in cui è stato applicato un criterio modalità di controllo. 
2. Tentativo di installazione dell'app nel dispositivo.
3. Aprire il Visualizzatore eventi su quel dispositivo. 
4. In Visualizzatore eventi passare a **Logs\Microsoft\Windows applicazione e servizi**, quindi selezionare **AppLocker**. 
5. Individuare qualsiasi evento **8003** o **8006** e quindi copiare le informazioni dall'evento: 
    - Nome applicazione 
    - Versione dell'applicazione 
    - Descrizione 
    - Dettagli editore (ad esempio: "O = <publisher name> , L = <location> , S = stato, C = paese") 
