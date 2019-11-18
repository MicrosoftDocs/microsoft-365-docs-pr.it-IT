---
title: Creare un classificatore addestrabile (anteprima)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Utilizzare classificatori addestrabili quando uno dei classificatori di caselle pronti per l'uso non soddisfa le proprie esigenze. Un classificatore Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare. In questo argomento viene illustrato come creare un classificatore personalizzato.
ms.openlocfilehash: 1d62b70d821593ff7d8d3889c0da0e0b5cc9809f
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38690639"
---
# <a name="creating-a-trainable-classifier-preview"></a>Creazione di un classificatore addestrabile (anteprima)

Utilizzare i classificatori addestrabili quando uno dei classificatori fuori campo non soddisfa le proprie esigenze. Un classificatore Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare. Formazione il classificatore implica la prima assegnazione di campioni che sono selezionati in modo umano e corrispondono positivamente alla categoria. Successivamente, dopo averli elaborati, si verificano le stime conferendole una combinazione di esempi positivi e negativi.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere [Guida introduttiva ai classificatori addestrabili (anteprima)](classifier-getting-started-with.md)

Questa sequenza temporale riflette una distribuzione di esempio.

![addestrare-classificatore-sequenza temporale](media/trainable-classifier-deployment-timeline_border.png)

## <a name="seed-content"></a>Contenuto del seeding

Quando si desidera che un classificatore addestrabile sia in grado di identificare in modo indipendente e accurato un elemento come in particolare la categoria di contenuto, è necessario innanzitutto presentarlo con numerosi esempi del tipo di contenuto nella categoria. L'alimentazione dei campioni al classificatore addestrabile è nota come *seeding*. Il contenuto del seeding viene selezionato da un essere umano e viene giudicato per rappresentare la categoria di contenuto.

> [!TIP]
> È necessario avere almeno 50 campioni positivi e ben 500. Il classificatore addestrativo elaborerà fino a 500 campioni creati più recenti (per data e timestamp creati dal file). Più esempi vengono forniti, maggiore è la precisione delle stime che verranno apportate dal classificatore.

## <a name="testing-content"></a>Test del contenuto

Dopo che il classificatore addestratore ha elaborato campioni positivi sufficienti per creare un modello di stima, è necessario verificare le stime che consente di verificare se il classificatore può distinguere correttamente tra gli elementi che corrispondono alla categoria e gli elementi che non lo sono. A tale scopo, è necessario nutrirlo con un altro, che si spera più grande, insieme di contenuto umano raccolto che è costituito da campioni che devono rientrare nella categoria e campioni che non lo faranno. Dopo averli elaborati, si procederà manualmente ai risultati e si verificherà se ogni previsione è corretta, non corretta o non si è certi. Il classificatore addestrabile utilizza questi commenti e suggerimenti per migliorare il modello di stima.

> [!TIP]
> Per ottenere risultati ottimali, avere 10.000 elementi nel set di campioni di test con una distribuzione uniforme di corrispondenze positive e negative.

> [!TIP]
> L'opzione opt-in è necessaria per la prima volta per i classificatori addestrabili. Per completare una valutazione di base del contenuto delle organizzazioni, sono necessari dodici giorni per Microsoft 365.

## <a name="how-to-create-a-trainable-classifier"></a>Come creare un classificatore addestrabile

1. Raccogliere tra gli elementi di contenuto di 50-500 Seed. Questi devono essere solo campioni che rappresentano fortemente il tipo di contenuto che si desidera che il classificatore addestrabile identifichi positivamente come nella Categoria classificazione. Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .

> [!IMPORTANT]
> Gli elementi di esempio Seed e test non devono essere crittografati e devono essere in inglese.

> [!IMPORTANT]
> Verificare che gli elementi del set di Seed siano esempi **forti** della categoria. Il classificatore addestrabile crea inizialmente il modello in base alle operazioni con cui viene eseguito il seeding. Il classificatore presuppone che tutti gli esempi di sementi siano forti positivi e che non sia possibile sapere se un campione è una corrispondenza debole o negativa per la categoria.

2. Inserire il contenuto di inizializzazione in una cartella di SharePoint Online dedicata a contenere *solo il contenuto del seeding*. Prendere nota dell'URL del sito, della raccolta e della cartella.

> [!TIP]
> Se si crea un nuovo sito e una nuova cartella per i dati di seeding, è possibile eseguire l'indicizzazione di almeno un'ora affinché tale percorso venga indicizzato prima di creare il classificatore addestrabile che utilizzerà tali dati.

3. Accedere a Microsoft 365 Compliance Center with Compliance admin or Security admin Role Access e Open **Microsoft 365 Compliance Center** or **Microsoft 365 Security Center** > **Data Classification**

4. Scegliere la scheda **classificatori addestrabili** .

5. Scegliere **Crea classificatore addestrabile**.

6. Inserire i valori adeguati per `Name`i campi `Description` e la categoria di elementi che si desidera vengano identificati dal classificatore addestrabile.

7. Immettere il sito, la raccolta e l'URL della cartella di SharePoint Online esatti per il sito di contenuto Seed del passaggio 2. Scegliere `Add`.

8. Rivedere le impostazioni e scegliere `Create trainable classifier`.

9. Entro 24 ore, il classificatore addestrativo elaborerà i dati di seeding e realizzerà un modello di stima. Lo stato del classificatore `In progress` è durante l'elaborazione dei dati di seeding. Quando il classificatore ha terminato di elaborare i dati di seeding, lo `Need test items`stato cambia in.

10. È ora possibile visualizzare la pagina dei dettagli scegliendo il classificatore.


![classificatore addestrabile pronto per il testing](media/classifier-trainable-ready-to-test-detail.png)

11. Raccogliere almeno 200 elementi di contenuto di test. Microsoft consiglia 10.000 per ottenere risultati ottimali. Queste devono essere una combinazione di elementi che sono forti positivi, negativi forti e alcuni che sono un po' meno evidenti nella loro natura. Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .

> [!IMPORTANT]
> Gli elementi di esempio non devono essere crittografati e devono essere in inglese.

12. Inserire il contenuto del test in una cartella di SharePoint Online dedicata alla conservazione *del solo contenuto del test*. Prendere nota del sito, della raccolta e dell'URL della cartella di SharePoint Online.

> [!TIP]
> Se si crea un nuovo sito e una nuova cartella per i dati di test, è possibile che la posizione venga indicizzata per almeno un'ora prima di creare il classificatore addestrabile che utilizzerà tali dati.

13. Scegliere `Add items to test`.

14. Immettere il sito di SharePoint Online, la raccolta e l'URL della cartella esatti per il sito di contenuto di test del passaggio 12. Scegliere `Add`.

15. Completare la procedura guidata scegliendo `Done`. Il classificatore addestrabile richiederà fino a un'ora per l'elaborazione dei file di test.

16. Quando si esegue l'elaborazione dei file di test da `Ready to review`parte del classificatore addestrabile, lo stato nella pagina dei dettagli cambia. Se è necessario aumentare le dimensioni del campione di test, `Add items to test` scegliere e consentire al classificatore addestrabile di elaborare gli elementi aggiuntivi.

![pronto per la revisione dello screenshot](media/classifier-trainable-ready-to-review-detail.png)

17. Scegliere `Tested items to review` la scheda per esaminare gli elementi.

18. Microsoft 365 presenterà 30 elementi alla volta. Verificarli e nella casella `We predict this item is "Relevant". Do you agree?` scegliere uno `Yes` o `No` più o `Not sure, skip to next item`. L'accuratezza del modello viene aggiornata automaticamente dopo ogni 30 elementi.

![casella di controllo elementi](media/classifier-trainable-review-detail.png)

19. Esaminare *almeno 200 elementi* .

20. Continuare a esaminare fino a quando l'accuratezza raggiunge almeno il 70 `Publish the classifier` % e `Ready to use`lo stato è.

![accuratezza e pronto per la pubblicazione](media/classifier-trainable-review-ready-to-publish.png)

21. Pubblicare il classificatore.

22. Una volta pubblicato, il classificatore sarà disponibile come condizione nel criterio di etichetta di conservazione per l' [applicazione automatica in base a una condizione](labels.md#applying-a-retention-label-automatically-based-on-conditions) e in [conformità alla comunicazione](communication-compliance.md).

> [!CAUTION]
> Dopo la pubblicazione di un classificatore, non è possibile eseguire ulteriori corsi di formazione, quindi accertarsi di aver testato e Recensito il maggior numero possibile di elementi per garantire la massima accuratezza possibile.

## <a name="see-also"></a>Vedere anche

- [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md)
- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
