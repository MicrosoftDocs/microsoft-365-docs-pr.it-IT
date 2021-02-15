---
title: Lavorare con Microsoft Consulting Services
description: preparazione e passaggi da seguire per lavorare con MCS per creare un pacchetto delle app
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, MCS, creazione di pacchetti
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841424"
---
# <a name="working-with-microsoft-consulting-services"></a>Lavorare con Microsoft Consulting Services

Puoi interagire con Microsoft Consulting Services (MCS) per creare pacchetti di app da usare con Microsoft Managed Desktop. Per dettagli precisi, contatta il rappresentante dell'account per contattare MCS e impostare l'ambito del progetto di creazione di pacchetti dell'app specifico.

## <a name="roles-and-responsibilities"></a>Ruoli e responsabilità

Per usare il pacchetto dell'app MCS, **devi fornire questi elementi:**

- I file del programma di installazione di origine (ad esempio, setup.exe o msi).
- Istruzioni per l'installazione, che specificano i dettagli sull'aspetto dell'installazione finale. Ad esempio, dovrebbe esserci un collegamento sul desktop all'app? Che cosa deve essere la visibilità dell'app? L'app deve connettersi a un server e, in tal caso, quale? Per informazioni dettagliate, vedi il modello di richiesta [di creazione di pacchetti dell'applicazione.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)
- Devi eseguire test di accettazione personalizzati per verificare che l'app funzioni come necessario nell'ambiente.

**MCS si occuperà di queste azioni:**

- Verifica se l'app è proibita o limitata nell'ambiente Microsoft Managed Desktop.
- Test di installazione, avvio e disinstallazione dell'app per garantire la compatibilità con Windows 10. Se MCS rileva un problema di compatibilità, l'app verrà consegnata al programma [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) per la correzione.
- Creare il pacchetto dell'app per la specifica e quindi testare la distribuzione dell'app tramite Microsoft Intune.

## <a name="app-delivery-schedule"></a>Pianificazione recapito app

Avvia il processo di creazione del pacchetto caricando le informazioni sull'app nel portale Microsoft Managed Desktop. Il team di creazione di pacchetti rivede i nuovi invii ogni giovedì. Dopo la revisione e la creazione del pacchetto, le app in pacchetto vengono recapitate il venerdì seguente. L'avvio può contenere fino a cinque app a settimana, ma il servizio può essere ridimensionato in base alle tue esigenze.

![calendario che mostra il flusso in entrata dell'app il giovedì (il 21 in questo esempio), convalida multimediale il giorno successivo, creazione di pacchetti il lunedì successivo (il 25) e recapito dell'app il venerdì successivo (il 29)](../../media/MCS-cal.png)

Una volta recapitata l'app, ti verrà notificata. A questo punto, hai 21 giorni per eseguire il test di accettazione e approvare il lavoro nel portale Microsoft Managed Desktop. Se si verificano problemi con l'app durante il test di accettazione, rifiutare l'app nel portale Microsoft Managed Desktop e si verrà connessi tramite posta elettronica con uno strumento per la creazione di pacchetti MCS per comprendere e risolvere il problema.

## <a name="testing-accounts-and-environment"></a>Test di account e ambiente

Per consentire al team di creazione pacchetti di completare la migrazione a Microsoft Intune, è consigliabile fornire alcune autorizzazioni:
 
-   Accesso alle funzionalità di distribuzione di app di Microsoft Intune per l'aggiunta e l'assegnazione dell'app da parte dello strumento di creazione pacchetti 
-   Gruppi di test, account utente e licenze per i packager per poter testare le app

MCS utilizzerà tali autorizzazioni per eseguire le azioni seguenti:
 
-   Verifica del funzionamento dell'app nella macchina virtuale configurata per Microsoft Managed Desktop
-   Caricamento dell'app in Microsoft Intune per la distribuzione agli utenti

Senza queste autorizzazioni, è possibile che MCS si sposti in avanti, ma non sarà in grado di caricare le applicazioni nell'ambiente.


