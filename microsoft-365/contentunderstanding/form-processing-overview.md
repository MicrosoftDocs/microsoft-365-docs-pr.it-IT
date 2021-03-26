---
title: Panoramica dell'elaborazione di moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informazioni sull'elaborazione di moduli in Microsoft SharePoint Syntex
ms.openlocfilehash: e3cf8298a2db9383e5b88dde737efc84e75c7f19
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222258"
---
# <a name="form-processing-overview"></a>Panoramica dell'elaborazione di moduli

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex usa l’elaborazione di moduli di [AI Builder](/ai-builder/overview) in Microsoft PowerApps per creare modelli all'interno delle raccolte documenti di SharePoint.

È possibile usare l'elaborazione dei moduli di AI Builder per creare modelli di intelligenza artificiale che usano la tecnologia di apprendimento automatico per identificare ed estrarre coppie chiave-valore e dati tabella da documenti strutturati o semi strutturati, ad esempio moduli e fatture.

Spesso le organizzazioni ricevono un gran numero di fatture da diverse origini, ad esempio via posta, fax, posta elettronica e così via. L'elaborazione di tali documenti e la loro immissione manuale in un database possono richiedere una considerevole quantità di tempo. Tramite l’uso dell’intelligenza artificiale, l'elaborazione dei moduli automatizza il processo di estrazione del testo, le coppie chiave-valore e le tabelle dai documenti. 

> [!NOTE]
> Per altri esempi di scenari di elaborazione dei moduli, vedere[Adozione di SharePoint Syntex: guida introduttiva](./adoption-getstarted.md).

Ad esempio, è possibile creare un modello di elaborazione moduli che identifichi tutti i documenti relativi agli ordini di acquisto caricati nella raccolta documenti. Da ogni ordine di acquisto è quindi possibile estrarre e visualizzare dati specifici importanti per l'utente, come il *numero ordine d’acquisto*, la *data* o l’*ammontare totale*.

![Visualizzazione della raccolta documenti](../media/content-understanding/doc-lib-done.png)</br>  

L’utente usa i file di esempio per eseguire il training del modello e definire le informazioni da estrarre dal modulo. Il layout del documento viene acquisito eseguendo il training del modello. Per iniziare, sono necessari solo cinque moduli. AI Builder analizza i file di esempio per individuare le coppie chiave-valore e l’utente può identificare manualmente quelli che non sono stati rilevati.  AI Builder consente di testare l’accuratezza del modello nei file di esempio.

Dopo aver eseguito il training del modello e averlo pubblicato, quest’ultimo crea un [flusso di Power Automate](/power-automate/getting-started). Il flusso viene eseguito quando un file è caricato nella raccolta documenti di SharePoint ed estrarrà i dati che sono stati identificati nel modello. I dati estratti saranno visualizzati nelle colonne di visualizzazione della raccolta documenti del modello.

Gli amministratori di Office 365 devono [abilitare l'elaborazione del modulo](./set-up-content-understanding.md) per la raccolta documenti di SharePoint in modo che gli utenti possano [creare un modello di elaborazione moduli](create-a-form-processing-model.md) in essa. È possibile selezionare i siti durante l'installazione o dopo la configurazione nelle impostazioni di gestione.

### <a name="file-limitations"></a>Limitazioni relative ai file

Quando si usano modelli di elaborazione dei moduli, assicurarsi di prendere nota dei [requisiti e delle limitazioni per l'utilizzo dei file](/ai-builder/form-processing-model-requirements).

### <a name="multi-geo-environments"></a>Ambienti multi-geografici

Quando si configura SharePoint Syntex in un [ambiente Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md), è possibile configurarlo solo per usare l'elaborazione dei moduli nella posizione centrale. Se si vuole usare l'elaborazione dei moduli in una località satellitare, contattare il supporto Microsoft.






## <a name="see-also"></a>Vedere anche
  
[Documentazione di Power Automate](/power-automate/)

[Creare un modello di elaborazione moduli](create-a-form-processing-model.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)

[Formazione: migliorare le prestazioni aziendali con AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)