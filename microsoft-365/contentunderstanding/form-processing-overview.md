---
title: Panoramica dell'elaborazione dei moduli
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sull'elaborazione dei moduli in Microsoft SharePoint Syntex
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295177"
---
# <a name="form-processing-overview-preview"></a>Panoramica dell'elaborazione dei moduli (anteprima)

Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

Project Cortex utilizza l'elaborazione dei moduli di Microsoft PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview) per creare modelli all'interno delle raccolte documenti di SharePoint.

È possibile utilizzare l'elaborazione dei moduli di AI Builder per creare modelli AI che utilizzano la tecnologia di apprendimento automatico per identificare ed estrarre coppie di valori chiave e dati di tabella da documenti strutturati o semistrutturati, come maschere e fatture.

Utilizzare l'elaborazione dei moduli di AI Builder per creare modelli AI che utilizzano la tecnologia di apprendimento automatico (ML) per identificare ed estrarre le coppie chiave/valore e i dati di tabella da documenti strutturati o semistrutturati, ad esempio la maschera e le fatture.

Le organizzazioni spesso ricevono fatture in grandi quantità da diverse fonti, ad esempio posta elettronica, fax, posta elettronica e così via. L'elaborazione di questi documenti e l'immissione manuale in un database può richiedere molto tempo. Utilizzando Ia per estrarre le coppie testo, chiave/valore e le tabelle dei documenti, la maschera di elaborazione automatizza questo processo. 

Ad esempio, è possibile creare un modello di elaborazione dei moduli che identifichi tutti i documenti degli ordini di acquisto caricati nella raccolta documenti. Da ogni ordine di acquisto è quindi possibile estrarre e visualizzare dati specifici che sono importanti per l'utente, ad esempio il *numero di po*, la *Data*o il *costo totale*.

È inoltre possibile utilizzare i file di esempio per formare il modello e definire le informazioni da estrarre dal modulo. Il layout del documento viene imparato mediante la formazione del modello. Per iniziare, è necessario un minimo di cinque documenti del modulo. L'edificio AI analizza i file di esempio per le coppie chiave-valore e quindi identifica manualmente quelli che potrebbero non essere stati rilevati.  AI Builder è possibile testare l'accuratezza del modello nei file di esempio.

Dopo aver eseguito la formazione e la pubblicazione del modello, utilizzarlo per creare un [flusso automatico di alimentazione automatizzato](https://docs.microsoft.com/power-automate/getting-started) in esecuzione dopo il caricamento di un file nella raccolta documenti di SharePoint. Vengono quindi estratti i dati identificati nel modello. I dati estratti verranno visualizzati nelle colonne della visualizzazione raccolta documenti del modello.

È possibile utilizzare i file di esempio per formare il modello e definire le informazioni da estrarre dal modulo. Il layout del documento viene imparato mediante la formazione del modello. Per iniziare, sono necessari solo cinque documenti del modulo. AI Builder verranno analizzati i file di esempio per le coppie chiave-valore ed è inoltre possibile identificare manualmente quelli che potrebbero non essere stati rilevati.  AI Builder è possibile testare l'accuratezza del modello nei file di esempio.

Dopo aver eseguito la formazione e la pubblicazione del modello, per utilizzarlo è possibile creare un [flusso di automatizzazione Power](https://docs.microsoft.com/power-automate/getting-started). Il flusso viene eseguito quando un file viene caricato nella raccolta documenti di SharePoint e verranno estratti i dati identificati nel modello. I dati estratti verranno visualizzati nelle colonne della visualizzazione raccolta documenti del modello.

Un amministratore di Office 365 deve [abilitare l'elaborazione dei moduli](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) per la raccolta documenti di SharePoint affinché gli utenti siano in grado di [creare un modello di elaborazione dei moduli](create-a-form-processing-model.md) .

## <a name="see-also"></a>Vedere anche
  
[Documentazione su Power automatizzate](https://docs.microsoft.com/power-automate/)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</br>
[Panoramica della comprensione del documento](document-understanding-overview.md)</br>
[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
