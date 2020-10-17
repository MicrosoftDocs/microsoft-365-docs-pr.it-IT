---
title: Panoramica dell'elaborazione di moduli
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni sull'elaborazione di moduli in Microsoft SharePoint Syntex
ms.openlocfilehash: 7340e0c78db71fbb0acc05c2985b60f6bafbba80
ms.sourcegitcommit: 705915f8bf9b7c082d12a009523d8aa0670a74a1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48493674"
---
# <a name="form-processing-overview"></a>Panoramica dell'elaborazione di moduli

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex usa l’elaborazione di moduli di [AI Builder](https://docs.microsoft.com/ai-builder/overview) in Microsoft PowerApps per creare modelli all'interno delle raccolte documenti di SharePoint.

È possibile usare l'elaborazione dei moduli di AI Builder per creare modelli di intelligenza artificiale che usano la tecnologia di apprendimento automatico per identificare ed estrarre coppie chiave-valore e dati tabella da documenti strutturati o semi strutturati, ad esempio moduli e fatture.

Spesso le organizzazioni ricevono un gran numero di fatture da diverse origini, ad esempio via posta, fax, posta elettronica e così via. L'elaborazione di tali documenti e la loro immissione manuale in un database possono richiedere una considerevole quantità di tempo. Tramite l’uso dell’intelligenza artificiale, l'elaborazione dei moduli automatizza il processo di estrazione del testo, le coppie chiave-valore e le tabelle dai documenti. 

> [!NOTE]
> Per altri esempi di scenari di elaborazione dei moduli, vedere[Adozione di SharePoint Syntex: guida introduttiva](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).

Ad esempio, è possibile creare un modello di elaborazione moduli che identifichi tutti i documenti relativi agli ordini di acquisto caricati nella raccolta documenti. Da ogni ordine di acquisto è quindi possibile estrarre e visualizzare dati specifici importanti per l'utente, come il*numero ordine d’acquisto*, la *data* o l’*ammontare totale*.

![Visualizzazione della raccolta documenti](../media/content-understanding/doc-lib-done.png)</br>  

L’utente usa i file di esempio per eseguire il training del modello e definire le informazioni da estrarre dal modulo. Il layout del documento viene acquisito eseguendo il training del modello. Per iniziare, sono necessari solo cinque moduli. AI Builder analizza i file di esempio per individuare le coppie chiave-valore e l’utente può identificare manualmente quelli che non sono stati rilevati.  AI Builder consente di testare l’accuratezza del modello nei file di esempio.

Per iniziare, sono necessari almeno cinque moduli. AI Builder analizza i file di esempio per individuare le coppie chiave-valore e poi identifica manualmente quelli che non sono stati rilevati.  AI Builder consente di testare l’accuratezza del modello nei file di esempio.

Dopo aver eseguito il training del modello e averlo pubblicato, quest’ultimo crea un [flusso di Power Automate](https://docs.microsoft.com/power-automate/getting-started). Il flusso viene eseguito quando un file è caricato nella raccolta documenti di SharePoint ed estrarrà i dati che sono stati identificati nel modello. I dati estratti saranno visualizzati nelle colonne di visualizzazione della raccolta documenti del modello.

Gli amministratori di Office 365 devono [abilitare l'elaborazione del modulo](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) per la raccolta documenti di SharePoint in modo che gli utenti possano [creare un modello di elaborazione moduli](create-a-form-processing-model.md) in essa. È possibile selezionare i siti durante l'installazione o dopo la configurazione nelle impostazioni di gestione.



## <a name="see-also"></a>Vedere anche
  
[Documentazione di Power Automate](https://docs.microsoft.com/power-automate/)

[Creare un modello di elaborazione moduli](create-a-form-processing-model.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)

[Formazione: migliorare le prestazioni aziendali con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
