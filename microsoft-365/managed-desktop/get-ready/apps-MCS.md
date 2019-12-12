---
title: Lavorare con Microsoft Consulting Services
description: preparazione e passaggi da seguire per lavorare con MCS per il pacchetto delle app
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, Apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4491504616eb4bb447f12d08dddb12c73c2a88ac
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962623"
---
# <a name="working-with-microsoft-consulting-services"></a>Lavorare con Microsoft Consulting Services

È possibile collaborare con Microsoft Consulting Services (MCS) per ottenere le app in pacchetti per l'utilizzo con Microsoft Managed Desktop. Per i dettagli esatti, collaborare con il proprio account Representative per contattare MCS e l'ambito del progetto di packaging app specifico.

## <a name="roles-and-responsibilities"></a>Ruoli e responsabilità

Per utilizzare la confezione dell'app MCS, **è necessario fornire questi elementi**:

- File del programma di installazione di origine (ad esempio, Setup. exe o. msi).
- Istruzioni di installazione, specificando i dettagli sul modo in cui deve essere consentita l'installazione finale. Ad esempio, se è presente un collegamento sul desktop per l'app? Che cosa dovrebbe essere la visibilità dell'app? Se l'app si connette a un server e, in caso affermativo, quale? Per informazioni dettagliate, vedere il [modello di richiesta di pacchettizzazione dell'applicazione](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- È necessario eseguire un test di accettazione personalizzato per verificare che l'app funzioni come necessario nell'ambiente in uso.

**MCS si occuperà di queste azioni:**

- Controllare se l'app è vietata o limitata nell'ambiente Microsoft Managed Desktop.
- Verifica dell'installazione, dell'avvio e della disinstallazione dell'app per garantire la compatibilità con Windows 10. Se MCS individua un problema di compatibilità, disinvierà l'app al programma [app desktop assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) per la correzione.
- L'applicazione viene configurata per la specifica e quindi viene testata la distribuzione delle app tramite Microsoft Intune.

## <a name="app-delivery-schedule"></a>Pianificazione del recapito delle app

Avviare il processo di creazione del pacchetto caricando le informazioni sull'app nel portale Microsoft Managed Desktop. Il team di packaging esamina i nuovi invii ogni Giovedi. Dopo la revisione e la confezione, le app in pacchetti vengono recapitate il venerdì seguente. È possibile creare pacchetti fino a cinque app alla settimana, ma il servizio può essere ridimensionato per soddisfare le proprie esigenze.

![calendario che mostra l'afflusso di app su un Giovedi (il 21 in questo esempio), la convalida dei contenuti multimediali il giorno successivo, la confezione del lunedì seguente (il venticinquesimo) e il recapito delle app il venerdì successivo (29)](images/MCS-cal.png)

Una volta che l'app è stata recapitata, verrà inviata una notifica. A questo punto, sono necessari 21 giorni per eseguire il test di accettazione e disconnettersi sul lavoro nel portale Microsoft Managed Desktop. Se si scopre qualche problema con l'app durante il test di accettazione, rifiutare l'applicazione nel portale Microsoft Managed Desktop e si sarà connessi tramite posta elettronica con un Packager MCS per comprendere e risolvere il problema.

## <a name="testing-accounts-and-environment"></a>Verifica degli account e dell'ambiente

Affinché il team di packaging completi la migrazione a Microsoft Intune, è consigliabile fornire determinate autorizzazioni:
 
-   Accesso alle funzionalità di distribuzione delle app di Microsoft Intune per il Packager per aggiungere e assegnare l'app 
-   Gruppi di test, account utente e licenze per i Packager per poter testare le app

MCS utilizzerà le autorizzazioni necessarie per eseguire le azioni seguenti:
 
-   Garantire che l'app funzioni su una macchina virtuale configurata per Microsoft Managed Desktop
-   Caricamento dell'app in Microsoft Intune per la distribuzione agli utenti

Se non si dispone di queste autorizzazioni, è possibile che MCS venga spostato in avanti, ma non sarà in grado di caricare le applicazioni nell'ambiente in uso.


