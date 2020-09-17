---
title: Panoramica dell'elaborazione dei moduli (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sull'elaborazione dei moduli in Project Cortex.
ms.openlocfilehash: de8e0ed546380059cc1b7b209eeec71f1eb779f9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950025"
---
# <a name="form-processing-overview-preview"></a>Panoramica dell'elaborazione dei moduli (anteprima)
> [!Note]
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).

Project Cortex utilizza l'elaborazione dei moduli di Microsoft PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview) per creare modelli all'interno delle raccolte documenti di SharePoint.
È possibile utilizzare l'elaborazione dei moduli di AI Builder per creare modelli AI che utilizzano la tecnologia di apprendimento automatico per identificare ed estrarre coppie di valori chiave e dati di tabella da documenti strutturati o semistrutturati, come maschere e fatture.

Le aziende spesso ricevono fatture in grandi quantità e da una vasta gamma di fonti, come posta elettronica, fax, posta elettronica o di persona. L'elaborazione di questi documenti e l'immissione manuale nel database può richiedere molto tempo. Utilizzando Ia per estrarre le coppie testo, chiave/valore e le tabelle dei documenti, l'elaborazione dei moduli automatizza questo processo. 

Ad esempio, è possibile creare un modello di elaborazione dei moduli che identifichi tutti i documenti degli ordini di acquisto caricati nella raccolta documenti. E da ogni ordine di acquisto è possibile estrarre e visualizzare dati specifici che sono importanti per l'utente, ad esempio il *numero di po*, la *Data*o il *costo totale*.

È possibile utilizzare file di esempio per formare il modello e definire le informazioni da estrarre dal modulo. Il layout del documento viene imparato mediante la formazione del modello. Per iniziare, sono necessari solo cinque documenti del modulo. AI Builder verranno analizzati i file di esempio per le coppie chiave-valore ed è inoltre possibile identificare manualmente quelli che potrebbero non essere stati rilevati.  AI Builder è possibile testare l'accuratezza del modello nei file di esempio.

Dopo aver eseguito la formazione e la pubblicazione del modello, per utilizzarlo è possibile creare un [flusso di automatizzazione Power](https://docs.microsoft.com/power-automate/getting-started). Il flusso viene eseguito quando un file viene caricato nella raccolta documenti di SharePoint e verranno estratti i dati identificati nel modello. I dati estratti verranno visualizzati nelle colonne della visualizzazione raccolta documenti del modello.

Un amministratore di Office 365 deve [abilitare l'elaborazione dei moduli](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) per la raccolta documenti di SharePoint affinché gli utenti siano in grado di [creare un modello di elaborazione dei moduli](create-a-form-processing-model.md) .



## <a name="see-also"></a>Vedere anche
  
[Documentazione su Power automatizzate](https://docs.microsoft.com/power-automate/)</br>
[Creare un modello di elaborazione dei moduli](create-a-form-processing-model.md)</br>
[Panoramica della comprensione del documento](document-understanding-overview.md)</br>
[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




