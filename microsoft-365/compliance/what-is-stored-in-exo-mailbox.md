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
description: I dati prodotti dalle app basate su cloud in Office 365 sono archiviati o associati a una cassetta postale di Exchange Online dell'utente.
ms.openlocfilehash: 88cd2bf459ed7a50c06194b22f2ae6a999380d51
ms.sourcegitcommit: 9a4084ce2b80bac883412e0ec956b6c0cc18d0f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "42400983"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Contenuto archiviato nelle cassette postali di Exchange Online

Una cassetta postale in Exchange Online viene utilizzata principalmente per archiviare gli elementi relativi alla posta elettronica, ad esempio messaggi, elementi del calendario, attività e note. Tuttavia, la modifica del numero di app di Office 365 basate su cloud memorizza anche i dati nella cassetta postale di un utente. Uno dei vantaggi dell'archiviazione dei dati in una cassetta postale è che è possibile utilizzare gli strumenti di ricerca nelle ricerche di contenuto, eDiscovery di base, eDiscovery avanzate e indagini sui dati per individuare, visualizzare ed esportare i dati da queste app basate su cloud. I dati di alcune di queste app sono archiviati in cartelle nascoste che si trovano in una sottostruttura di messaggi non interpersonali (non IPM) nella cassetta postale. I dati provenienti da altre app basate su cloud potrebbero non essere archiviati _nella_ cassetta postale, ma sono _associati_ alla cassetta postale e vengono restituiti nelle ricerche (se tali dati corrispondono alla query di ricerca). Indipendentemente dal fatto che i dati basati sul cloud siano archiviati o associati a una cassetta postale dell'utente, i dati in genere non sono visibili in un client di posta elettronica quando un utente apre la propria cassetta postale.

Nella tabella seguente sono elencate le app di Office 365 che archiviano o associa i dati a una cassetta postale basata su cloud. La tabella descrive anche il tipo di contenuto che ogni app produce.

|App di Office 365|Descrizione|
|:---------|:---------|
|Forms|I moduli (archiviati come file PDF) e le risposte a un modulo (archiviati in un file CSV) sono allegati ai messaggi di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato il modulo. Quando si esporta contenuto da moduli in un file PST, questi dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il GUID seguente: **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Gruppi di Office 365|I messaggi di posta elettronica, gli elementi del calendario, i contatti (persone), le note e le attività vengono archiviati nella cassetta postale associata a un gruppo di Office 365.|
|Outlook/Exchange Online|I messaggi di posta elettronica, gli elementi del calendario, i contatti (persone), le note e le attività vengono archiviati nella cassetta postale di un utente.|
|Persone|I contatti nell'app utenti (che sono gli stessi contatti di quelli accessibili in Outlook) vengono archiviati nella cassetta postale di un utente.|
|Pianificazione delle classi|I piani creati nella pianificazione delle classi vengono archiviati nella cassetta postale del gruppo di Office 365 corrispondente di cui viene effettuato il provisioning quando viene creato un nuovo piano. L'alias della cassetta postale del gruppo è il nome del piano.|
|Skype for Business|Le conversazioni in Skype for business sono archiviate nella cartella Cronologia conversazioni della cassetta postale di un utente. Se la cassetta postale di un partecipante a una riunione Skype viene mantenuta per controversia legale o assegnata a un criterio di conservazione, i file allegati a una riunione vengono conservati nella cassetta postale dei partecipanti.|
|Sway|Gli Sway sono archiviati come file HTML collegato a un messaggio di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato il dominio. Quando si esporta contenuto da Sway in un file PST, i dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il GUID seguente **905fcf26-4EB7-48A0-9ff0-8dcc7194b5ba**.|
|Tasks|Le attività nell'app attività (che sono le stesse attività di quelle accessibili in Outlook) vengono memorizzate nella cassetta postale di un utente.|
|Teams|Le conversazioni che fanno parte di un canale teams sono associate alla cassetta postale teams. Le conversazioni che fanno parte dell'elenco chat in teams (chiamate anche *1 x N chat*) sono associate alla cassetta postale degli utenti che partecipano alla chat. Inoltre, le informazioni di riepilogo per le riunioni e le chiamate in un canale team sono associate alle cassette postali degli utenti che hanno effettuato l'accesso alla riunione o alla chiamata. In questo modo, quando si cerca il contenuto del team, è necessario cercare nella cassetta postale teams per il contenuto nelle conversazioni di canale e nelle cassette postali degli utenti di ricerca per il contenuto in chat di 1 x| 
|To-Do|Le attività (chiamate *da DOS*, che vengono salvate negli elenchi di cose da fare) nell'app da fare sono archiviate nella cassetta postale di un utente.|
||||

> [!NOTE]
> A questo punto, se una conservazione viene posizionata su una cassetta postale (utilizzando le esenzioni in eDiscovery e nei casi avanzati di eDiscovery), il contenuto proveniente da maschere e Sway non verrà mantenuto dall'esenzione. 
