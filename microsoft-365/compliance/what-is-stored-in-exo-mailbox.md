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
ROBOTS: NOINDEX, NOFOLLOW
description: I dati prodotti da app basate su cloud in Microsoft 365 vengono archiviati o associati alla cassetta postale di Exchange Online di un utente.
ms.openlocfilehash: f7bd5b00e8219f382078eb2d4f8aa25bd4c54d69
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750747"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Contenuto archiviato nelle cassette postali di Exchange Online

Una cassetta postale in Exchange Online viene utilizzata principalmente per archiviare elementi correlati alla posta elettronica quali messaggi, elementi del calendario, attività e note. Tuttavia, ciò sta cambiando perché più app basate sul cloud archiviano anche i dati nella cassetta postale di un utente. Uno dei vantaggi dell'archiviazione dei dati in una cassetta postale è che è possibile utilizzare gli strumenti di ricerca nella ricerca di contenuto, Core eDiscovery, Advanced eDiscovery per trovare, visualizzare ed esportare i dati da queste app basate su cloud. I dati di alcune di queste app sono archiviati in cartelle nascoste che si trovano in un sottoalbero dei messaggi non interpersonali (non IPM) nella cassetta postale. I dati di altre app basate  su cloud potrebbero non  essere archiviati nella cassetta postale, ma sono associati alla cassetta postale e vengono restituiti nelle ricerche (se i dati corrispondono alla query di ricerca). Indipendentemente dal fatto che i dati basati sul cloud siano archiviati o associati a una cassetta postale utente, i dati in genere non sono visibili in un client di posta elettronica quando un utente apre la propria cassetta postale.

Nella tabella seguente sono elencate le app che archiviano o associano i dati a una cassetta postale basata su cloud. La tabella descrive anche il tipo di contenuto prodotto da ogni app.

|App Di Microsoft 365|Descrizione|
|:---------|:---------|
|Forms|I moduli e le risposte a un modulo vengono archiviati in file allegati ai messaggi di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato il modulo. I moduli creati prima di aprile 2020 vengono archiviati come file PDF. I moduli creati dopo la versione 2020 vengono archiviati come file JSON.  Le risposte a un modulo vengono archiviate in un file CSV. Quando si esporta contenuto da Forms in un file PST, questi dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il seguente GUID univoco globale : **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Gruppi di Microsoft 365|I messaggi di posta elettronica, gli elementi del calendario, i contatti (Persone), le note e le attività vengono archiviati nella cassetta postale associata a un gruppo di Microsoft 365.|
|Outlook/Exchange Online|I messaggi di posta elettronica, gli elementi del calendario, i contatti (Persone), le note e le attività vengono archiviati nella cassetta postale di un utente.|
|Persone|I contatti nell'app Contatti (che sono gli stessi contatti accessibili in Outlook) vengono archiviati nella cassetta postale di un utente.|
|Pianificazione della classe|I piani creati in Pianificazione classi vengono archiviati nella cassetta postale del gruppo di Microsoft 365 corrispondente di cui viene eseguito il provisioning quando viene creato un nuovo piano. L'alias per la cassetta postale del gruppo è il nome del piano.|
|Skype for Business|Le conversazioni in Skype for Business vengono archiviate nella cartella Cronologia conversazioni nella cassetta postale di un utente. Se la cassetta postale di un partecipante a una riunione Skype viene messa in conservazione per controversia legale o assegnata a un criterio di conservazione, i file allegati a una riunione vengono conservati nella cassetta postale dei partecipanti.|
|Sway|Gli sway vengono archiviati come file HTML allegati a un messaggio di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato lo sway. Quando si esporta contenuto da Sway in un file PST, questi dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il GUID **seguente: 905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**.|
|Tasks|Le attività nell'app Attività (che sono le stesse di quelle accessibili in Outlook) vengono archiviate nella cassetta postale di un utente.|
|Teams|Le conversazioni che fanno parte di un canale di Teams sono associate alla cassetta postale di Teams. Le conversazioni che fanno parte dell'elenco chat in Teams (denominate anche *1 x N chat)* sono associate alla cassetta postale degli utenti che partecipano alla chat. Inoltre, le informazioni di riepilogo per le riunioni e le chiamate in un canale di Teams sono associate alle cassette postali degli utenti che hanno composto la riunione o la chiamata. Pertanto, quando si cerca contenuto di Teams, è necessario cercare nella cassetta postale di Teams il contenuto nelle conversazioni del canale e cercare il contenuto nelle cassette postali degli utenti in 1 x N chat.| 
|To-Do|Le attività *(chiamate cose da fare,* che vengono salvate in elenchi di attività) nell'app To-Do vengono archiviate nella cassetta postale di un utente.|
|Yammer|Le conversazioni e i commenti all'interno di una community di Yammer sono associati alla cassetta postale del gruppo di Microsoft 365, nonché alla cassetta postale utente dell'autore e a tutti i destinatari denominati (utenti @mentioned o cc'ed). I messaggi privati inviati all'esterno di una community di Yammer vengono archiviati nella cassetta postale degli utenti che partecipano al messaggio privato.|  
||||

> [!NOTE]
> Al momento, se un blocco viene posto su una cassetta postale (utilizzando i blocchi in casi di eDiscovery e Advanced eDiscovery), il contenuto di Forms e Sway non verrà conservato dal blocco. 
