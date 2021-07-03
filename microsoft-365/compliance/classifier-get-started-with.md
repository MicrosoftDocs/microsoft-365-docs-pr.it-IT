---
title: Per iniziare con i classificatori sottoponibili a training
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Un Microsoft 365 classificatore è uno strumento che puoi formare per riconoscere diversi tipi di contenuto fornendogli esempi da esaminare. Questo articolo illustra come creare e formare un classificatore personalizzato e come riqualificarli per aumentare l'accuratezza.
ms.openlocfilehash: 3053e5154fb4e1ff39ce7db366ce4679bbb8911d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286634"
---
# <a name="get-started-with-trainable-classifiers"></a>Per iniziare con i classificatori sottoponibili a training

Un Microsoft 365 classificatore di cui è possibile eseguire il training è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendogli esempi da esaminare. Una volta addestrato, è possibile utilizzarlo per identificare l'elemento per l'applicazione di Office di riservatezza, criteri di conformità delle comunicazioni e criteri di etichetta di conservazione.

La creazione di un classificatore sotto forma di training personalizzato comporta innanzitutto la creazione di campioni selezionati dall'utente e che corrispondono in modo positivo alla categoria. Quindi, dopo averli elaborati, puoi testare la capacità dei classificatori di prevedere fornendogli una combinazione di campioni positivi e negativi. Questo articolo illustra come creare e formare un classificatore personalizzato e come migliorare le prestazioni dei classificatori e dei classificatori pre-addestrabili personalizzati nel corso della loro durata tramite la riqualificazione.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere [Learn about trainable classifiers](classifier-learn-about.md).

Guarda questo video per un breve riepilogo della creazione di un classificatore addestrabile. Dovrai comunque leggere questo articolo completo per ottenere i dettagli.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>Prerequisiti

### <a name="licensing-requirements"></a>Requisiti di licenza

I classificatori sono una Microsoft 365 E5 o E5 Compliance. Per utilizzarle, è necessario disporre di una di queste sottoscrizioni.

### <a name="permissions"></a>Autorizzazioni

Per accedere ai classificatori nell'interfaccia utente: 

- l'amministratore globale deve acconsentire esplicitamente al tenant per creare classificatori personalizzati.
- Il ruolo amministratore della conformità è necessario per formare un classificatore.

Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:

- Scenario dei criteri di etichetta di conservazione: ruoli Gestione record e Gestione conservazione 
- Scenario dei criteri delle etichette di riservatezza: Amministratore della sicurezza, Amministratore conformità, Amministratore dati di conformità
- Scenario dei criteri di conformità della comunicazione: Insider Risk Management Admin, Supervisory Review Administrator 

> [!IMPORTANT]
> Per impostazione predefinita, solo l'utente che crea un classificatore personalizzato può eseguire il training e rivedere le previsioni effettuate da tale classificatore.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Preparare un classificatore addestrabile personalizzato 

È utile comprendere cosa comporta la creazione di un classificatore addestrabile personalizzato prima di tuffarsi. 

### <a name="timeline"></a>Sequenza temporale

Questa sequenza temporale riflette una distribuzione di esempio di classificatori sotto forma di training.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Il consenso esplicito è necessario la prima volta per classificatori addestrabili. Per completare una valutazione di Microsoft 365 di base del contenuto dell'organizzazione, sono necessari 12 giorni. Contattare l'amministratore globale per avviare il processo di consenso esplicito.

### <a name="overall-workflow"></a>Flusso di lavoro complessivo

Per ulteriori informazioni sul flusso di lavoro complessivo per la creazione di classificatori addestrabili personalizzati, vedere [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).

### <a name="seed-content"></a>Contenuto seed

Quando si desidera che un classificatore sotto forma di training identifichini in modo indipendente e accurato un elemento in una determinata categoria di contenuto, è innanzitutto necessario presentarlo con molti esempi del tipo di contenuto presente nella categoria. Questa alimentazione di campioni al classificatore trainabile è nota come *seeding.* Il contenuto di seed viene selezionato da un essere umano e viene scelto per rappresentare la categoria di contenuto.

> [!TIP]
> Devi avere almeno 50 campioni positivi e fino a 500. Il classificatore addestrabile eelaborare fino ai 500 esempi creati più di recente (per data e ora di creazione del file). Più esempi fornisci, più accurate saranno le previsioni che il classificatore farà.

### <a name="testing-content"></a>Test del contenuto

Dopo che il classificatore sotto forma di training ha elaborato campioni positivi sufficienti per creare un modello di previsione, è necessario testare le previsioni che effettua per verificare se il classificatore è in grado di distinguere correttamente tra gli elementi che corrispondono alla categoria e gli elementi che non lo soddisfano. A tale scopo, selezionare un altro insieme, si spera più grande, di contenuto raccolto dall'utente costituito da campioni che dovrebbero rientrare nella categoria e campioni che non lo saranno. È consigliabile eseguire il test con dati diversi rispetto ai dati di inizializzazione iniziali forniti per la prima volta. Dopo averli processati, puoi passare manualmente attraverso i risultati e verificare se ogni previsione è corretta, errata o non sei sicuro. Il classificatore addestrabile usa questo feedback per migliorare il modello di previsione.

> [!TIP]
> Per ottenere risultati ottimali, nel set di campioni di test sono presenti almeno 200 elementi con una distribuzione uniforme di corrispondenze positive e negative.

## <a name="how-to-create-a-trainable-classifier"></a>Come creare un classificatore trainabile

1. Raccogliere tra 50 e 500 elementi di contenuto di seed. Questi devono essere solo esempi che rappresentano in modo forte il tipo di contenuto che il classificatore sotto forma di training deve identificare in modo positivo nella categoria di classificazione. Per i tipi di file supportati, vedere Default [crawled file name extensions and parsed file types in SharePoint Server.](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

   > [!IMPORTANT]
   > Gli elementi di esempio di seed e test non devono essere crittografati e devono essere in inglese.

   > [!IMPORTANT]
   > Assicurati che gli elementi nel set di seed siano **esempi** specifici della categoria. Il classificatore di cui è possibile eseguire il training inizialmente crea il modello in base al valore di inizializzazione. Il classificatore presuppone che tutti i campioni di seme siano positivi forti e non abbia modo di sapere se un campione è una corrispondenza debole o negativa alla categoria.

2. Inserire il contenuto del seed in una SharePoint online dedicata solo al *contenuto del seed.* Prendere nota dell'URL del sito, della raccolta e della cartella.

   > [!TIP]
   > Se si crea un nuovo sito e una nuova cartella per i dati di seed, consentire l'indicizzazione di almeno un'ora per tale posizione prima di creare il classificatore trainabile che utilizzerà i dati di seed.

3. Accedi a Centro conformità Microsoft 365 con l'accesso al ruolo amministratore della conformità o amministratore della sicurezza e **apri** Centro conformità Microsoft 365 o **Microsoft 365 del** centro sicurezza  >  **Classificazione dati**.

4. Scegliere la **scheda Classificatori trainabili.**

5. Scegliere **Crea classificatore trainabile.**

6. Compilare i valori appropriati per i campi e della categoria di elementi che si desidera identificare da `Name` `Description` questo classificatore sotto forma di training.

7. Selezionare il SharePoint, la raccolta e l'URL della cartella di SharePoint online per il sito di contenuto seed dal passaggio 2. Scegliere `Add` .

8. Rivedere le impostazioni e scegliere `Create trainable classifier` .

9. Entro 24 ore il classificatore addestrabile eelaborare i dati di seed e creare un modello di previsione. Lo stato del classificatore `In progress` è durante l'elaborazione dei dati di seed. Quando il classificatore ha terminato l'elaborazione dei dati di seed, lo stato viene modificato in `Need test items` .

10. È ora possibile visualizzare la pagina dei dettagli scegliendo il classificatore.

    > [!div class="mx-imgBorder"]
    > ![Classificatore addestrabile pronto per il test](../media/classifier-trainable-ready-to-test-detail.png)

11. Raccogliere almeno 200 elementi di contenuto di test (10.000 max) per ottenere risultati ottimali. Questi dovrebbero essere una combinazione di elementi che sono positivi forti, negativi forti e alcuni che sono un po ' meno evidenti nella loro natura. Per i tipi di file supportati, vedere Default [crawled file name extensions and parsed file types in SharePoint Server.](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

    > [!IMPORTANT]
    > Gli elementi di esempio non devono essere crittografati e devono essere in inglese.

12. Inserire il contenuto di test in una SharePoint online dedicata solo al contenuto *di test.* Prendere nota dell'URL SharePoint sito, raccolta e cartella di SharePoint Online.

    > [!TIP]
    > Se si creano un nuovo sito e una nuova cartella per i dati di test, è necessario indicizzare almeno un'ora per tale posizione prima di creare il classificatore di cui è possibile eseguire il training che utilizzerà i dati di seed.

13. Scegliere `Add items to test` .

14. Selezionare l SharePoint, la raccolta e l'URL della cartella per il sito di contenuto di test dal passaggio 12. Scegliere `Add` .

15. Completare la procedura guidata scegliendo `Done` . Il classificatore di cui è possibile eseguire il training può richiedere fino a un'ora per elaborare i file di test.

16. Quando il classificatore addestrabile ha finito di elaborare i file di test, lo stato nella pagina dei dettagli cambierà in `Ready to review` . Se devi aumentare le dimensioni del campione di test, scegli e consenti al `Add items to test` classificatore addestrabile di elaborare gli elementi aggiuntivi.

    > [!div class="mx-imgBorder"]
    > ![screenshot pronto per la revisione](../media/classifier-trainable-ready-to-review-detail.png)

17. Scegliere `Tested items to review` la scheda per esaminare gli elementi.

18. Microsoft 365 presenta 30 elementi alla volta. Esaminarli e nella `We predict this item is "Relevant". Do you agree?` casella scegliere uno o `Yes` `No` `Not sure, skip to next item` . L'accuratezza del modello viene aggiornata automaticamente dopo ogni 30 elementi.

    > [!div class="mx-imgBorder"]
    > ![casella rivedi elementi](../media/classifier-trainable-review-detail.png)

19. Esaminare *almeno* 200 elementi. Una volta stabilizzato il punteggio di accuratezza, **l'opzione di** pubblicazione diventerà disponibile e lo stato del classificatore dirà `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![punteggio di accuratezza e pronto per la pubblicazione](../media/classifier-trainable-review-ready-to-publish.png)

20. Pubblicare il classificatore.

21. Dopo la pubblicazione, il classificatore sarà disponibile come condizione in Office [auto-etichettatura](apply-sensitivity-label-automatically.md)con etichette di [riservatezza,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) applicare automaticamente i criteri delle etichette di conservazione in base a una condizione e in [Conformità alle comunicazioni.](communication-compliance.md)
