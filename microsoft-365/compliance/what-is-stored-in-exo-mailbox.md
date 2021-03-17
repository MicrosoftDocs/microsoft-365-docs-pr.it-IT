---
title: Contenuto archiviato nelle cassette postali di Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: Il contenuto prodotto da app basate su cloud in Microsoft 365 viene archiviato o associato alla cassetta postale di Exchange Online di un utente. Questo contenuto può essere cercato utilizzando gli strumenti di Microsoft eDiscovery.
ms.openlocfilehash: 872e618486c273e07e8dcf98d61bbbb7d8f95051
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838614"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>Contenuto archiviato nelle cassette postali di Exchange Online per eDiscovery

Una cassetta postale in Exchange Online viene utilizzata principalmente per archiviare elementi correlati alla posta elettronica, ad esempio messaggi, elementi del calendario, attività e note. Tuttavia, ciò sta cambiando poiché un maggior numero di app basate sul cloud archivia anche i propri dati nella cassetta postale di un utente. Uno dei vantaggi dell'archiviazione dei dati in una cassetta postale è che è possibile utilizzare gli strumenti di ricerca in ricerca contenuto, Core eDiscovery ed Advanced eDiscovery per trovare, visualizzare ed esportare i dati da queste app basate su cloud. I dati di alcune di queste app sono archiviati in cartelle nascoste che si trovano in un sottoalbero di messaggi non interpersonali (non IPM) nella cassetta postale. I dati di altre app basate  sul cloud potrebbero non  essere archiviati nella cassetta postale, ma sono associati alla cassetta postale e vengono restituiti nelle ricerche (se i dati corrispondono alla query di ricerca). Indipendentemente dal fatto che i dati basati sul cloud siano archiviati o associati a una cassetta postale utente, i dati in genere non sono visibili in un client di posta elettronica quando un utente apre la propria cassetta postale.

Nella tabella seguente sono elencate le app che archiviano o associano dati a una cassetta postale basata su cloud. La tabella descrive anche il tipo di contenuto prodotto da ogni app.

|App Microsoft 365|Descrizione|
|:---------|:---------|
|Moduli|I moduli e le risposte a un modulo vengono archiviati in file allegati ai messaggi di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato il modulo. I moduli creati prima di aprile 2020 vengono archiviati come file PDF. I moduli creati dopo la versione 2020 vengono archiviati come file JSON.  Le risposte a un modulo vengono archiviate in un file CSV. Quando si esporta contenuto da Moduli in un file PST, questi dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il guid (Globally Unique Identified) seguente: **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**. |
|Gruppi di Microsoft 365|I messaggi di posta elettronica, gli elementi del calendario, i contatti (Persone), le note e le attività vengono archiviati nella cassetta postale associata a un gruppo di Microsoft 365.|
|Outlook/Exchange Online|I messaggi di posta elettronica, gli elementi del calendario, i contatti (Persone), le note e le attività vengono archiviati nella cassetta postale di un utente.|
|Persone|I contatti nell'app Contatti (che sono gli stessi contatti accessibili in Outlook) vengono archiviati nella cassetta postale di un utente.|
|Pianificazione della classe|I piani creati in Pianificazione classi vengono archiviati nella cassetta postale del gruppo di Microsoft 365 corrispondente di cui viene eseguito il provisioning quando viene creato un nuovo piano. L'alias per la cassetta postale del gruppo è il nome del piano.|
|Skype for Business|Le conversazioni in Skype for Business vengono archiviate nella cartella Cronologia conversazioni nella cassetta postale di un utente. Se la cassetta postale di un partecipante a una riunione Skype viene messa in conservazione per controversia legale o assegnata a un criterio di conservazione, i file allegati a una riunione vengono conservati nella cassetta postale dei partecipanti.|
|Sway|Gli sway vengono archiviati come file HTML allegato a un messaggio di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato lo sway. Quando si esporta contenuto da Sway in un file PST, questi dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il GUID  **seguente: 905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Tasks|Le attività nell'app Attività (che sono le stesse di quelle accessibili in Outlook) vengono archiviate nella cassetta postale di un utente.|
|Teams|Le conversazioni che fanno parte di un canale teams sono associate alla cassetta postale di Teams. Le conversazioni che fanno parte dell'elenco Chat in Teams (denominate anche *chat 1 x N)* sono associate alla cassetta postale degli utenti che partecipano alla chat. Inoltre, le informazioni di riepilogo per le riunioni e le chiamate in un canale di Teams sono associate alle cassette postali degli utenti che hanno chiamato la riunione o la chiamata. Pertanto, quando si cerca il contenuto di Teams, è necessario cercare nella cassetta postale di Teams il contenuto nelle conversazioni del canale e cercare il contenuto nelle cassette postali degli utenti in 1 x N chat.|
|To-Do|Le attività *(denominate cose da* fare, che vengono salvate in elenchi di attività) nell'app To-Do vengono archiviate nella cassetta postale di un utente.|
|Yammer|Le conversazioni e i commenti all'interno di una community di Yammer sono associati alla cassetta postale del gruppo di Microsoft 365, nonché alla cassetta postale dell'utente dell'autore e a tutti i destinatari denominati (@ menzionati o utenti Cc'ed). I messaggi privati inviati all'esterno di una community yammer vengono archiviati nella cassetta postale degli utenti che partecipano al messaggio privato.|  
||||

> [!NOTE]
> In questo momento, se viene effettuato un blocco su una cassetta postale (utilizzando i blocchi nei casi di Core eDiscovery e Advanced eDiscovery), il contenuto di Forms e Sway non verrà conservato dal blocco.
