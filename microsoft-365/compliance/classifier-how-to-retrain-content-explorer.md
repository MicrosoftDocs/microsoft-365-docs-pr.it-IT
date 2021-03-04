---
title: Come ripetere il training di un classificatore in Esplora contenuto
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come fornire feedback a un classificatore di cui è possibile eseguire il training in Esplora contenuto.
ms.openlocfilehash: fabfe8e4df377c25012b358960d7f7ff7ff994bc
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423263"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Come ripetere il training di un classificatore in Esplora contenuto

Un classificatore formabile di Microsoft 365 è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendogli esempi da esaminare. Una volta preparato, è possibile utilizzarlo per identificare l'elemento per l'applicazione delle etichette di riservatezza di Office, dei criteri di conformità delle comunicazioni e dei criteri delle etichette di conservazione.

Questo articolo illustra come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori pre-preparati fornendo loro un feedback aggiuntivo.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere Informazioni sui classificatori disponibili [per il training.](classifier-learn-about.md)

Guardare questo video per un breve riepilogo del processo di ottimizzazione e riqualificazione. Dovrai comunque leggere questo articolo completo per ottenere i dettagli.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Autorizzazioni

Per accedere ai classificatori nel Centro conformità Microsoft 365:

- Il ruolo di amministratore della conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore

Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:

- Scenario dei criteri di etichetta di conservazione: ruoli Gestione record e Gestione conservazione 

## <a name="overall-workflow"></a>Flusso di lavoro complessivo

> [!IMPORTANT]
> Il feedback viene fornito in Esplora contenuto per l'applicazione automatica dei criteri delle etichette di conservazione agli elementi di Exchange e il classificatore viene utilizzato come condizione. **Se non si dispone di un criterio di conservazione che applica automaticamente un'etichetta di conservazione agli elementi di Exchange e usa un classificatore come condizione, fermarsi qui.**

Quando si utilizzano i classificatori, è possibile aumentare la precisione delle classificazioni che stanno effettuando. A tale scopo, valutare la qualità delle classificazioni effettuate per gli elementi identificati come corrispondenti o meno. Dopo aver fatto 30 valutazioni per un classificatore, richiede quel feedback e si rie classifica automaticamente.

Per ulteriori informazioni sul flusso di lavoro generale di riqualificazione di un classificatore, vedere Flusso di processo per la [riqualificazione di un classificatore.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Un classificatore deve essere già pubblicato e in uso prima di poter essere riesegnato.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Come ripetere il training di un classificatore in Esplora contenuto

1. Accedere al Centro conformità Microsoft 365 con l'accesso al ruolo di amministratore della conformità o amministratore della sicurezza e aprire Esplora contenuto per la classificazione dei dati del Centro conformità **Microsoft 365.**  >    >   
2. **Nell'elenco Filtro in base a etichette, tipi di** informazioni o categorie espandere Classificatori sotto forma di **sottosezioni.**

> [!IMPORTANT]
> La visualizzazione degli elementi aggregati sotto l'intestazione classificatori sotto il training può richiedere fino a otto giorni.

3. Scegliere il classificatore formabile usato nei criteri di etichetta di conservazione applicati automaticamente. Questo è il classificatore su cui è possibile formare il feedback.

> [!NOTE]
> Se un elemento contiene una voce nella colonna **Dell'etichetta** di conservazione, significa che l'elemento è stato classificato come `match` .  Se un elemento non dispone di una voce nella colonna **Dell'etichetta** di conservazione, significa che è stato classificato come `close match` . Puoi migliorare maggiormente la precisione del classificatore fornendo feedback sugli `close match` elementi. 

4. Scegliere un elemento e aprirlo.
 
 > [!TIP]
> Puoi fornire feedback su più elementi contemporaneamente scegliendoli tutti e quindi scegliendo **Migliora classificazione** nella barra dei comandi.

5. Scegliere **Fornisci feedback.**
6. Nel riquadro **Commenti e suggerimenti dettagliati,** se l'elemento è un vero positivo, scegliere **Corrispondenza.**  Se l'elemento è un falso positivo, che è stato incluso in modo errato nella categoria, scegliere **Non corrisponde a.**
7. Se è presente un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci** altri classificatori formabili. In questo modo verrà attivato l'altro classificatore per valutare l'elemento.
8. Scegliere **Invia feedback** per inviare la valutazione dei classificatori, le classificazioni e suggerire altri `match` `not a match` classificatori formabili. Quando hai fornito 30 istanze di feedback a un classificatore, verrà automaticamente riesercita la formazione. La riqualificazione può richiedere da una a quattro ore. I classificatori possono essere addestrati solo due volte al giorno.

> [!IMPORTANT]
> Queste informazioni passano al classificatore nel tenant, **non tornano a Microsoft.**

9. Apri **classificatori di cui è possibile utilizzare il training.**
10. Il classificatore usato nei criteri di conformità delle comunicazioni verrà visualizzato sotto **l'intestazione Ri-formazione.**

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

11. Al termine della riqualificazione, scegli il classificatore per aprire la panoramica della riqualificazione.

![Panoramica dei risultati di riqualificazione dei classificatori](../media/classifier-retraining-overview.png)

12. Esaminare l'azione consigliata e i confronti di previsione delle versioni riesecite e attualmente pubblicate del classificatore.
13. Se si è soddisfatti dei risultati della riqualificazione, scegliere **Riposizioni.**
14. Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriore feedback al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata. 

## <a name="details-on-republishing-recommendations"></a>Dettagli sulla ripubblicazione dei suggerimenti

Ecco un po' di informazioni su come formulare il suggerimento di pubblicare di nuovo un classificatore riqualificato o suggerire un'ulteriore riqualificazione. Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori formabili.

Dopo un nuovo training, valutiamo le prestazioni del classificatore su entrambi gli elementi con feedback, nonché su tutti gli elementi originariamente usati per formare il classificatore. 

- Per i modelli predefiniti, gli elementi usati per eseguire il training del classificatore sono gli elementi usati da Microsoft per creare il modello.
- Per i modelli personalizzati, gli elementi usati nella formazione originale del classificatore sono provenienti dai siti aggiunti per il test e la revisione.

Confrontiamo i numeri delle prestazioni su entrambi i set di elementi per il classificatore rie addestrato e pubblicato per fornire una raccomandazione sulla possibile ripubblicazione di un miglioramento. 

## <a name="see-also"></a>Vedere anche

- [Informazioni sui classificatori sottoponibili a training](classifier-learn-about.md)
- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
