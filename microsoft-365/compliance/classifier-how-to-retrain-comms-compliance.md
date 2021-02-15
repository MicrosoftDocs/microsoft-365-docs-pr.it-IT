---
title: Come ripetere il training di un classificatore in Conformità alle comunicazioni
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
description: Informazioni su come fornire feedback a un classificatore formabile nella conformità delle comunicazioni.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752650"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Come ripetere il training di un classificatore in Conformità alle comunicazioni

Un classificatore formabile di Microsoft 365 è uno strumento che è possibile formare per riconoscere vari tipi di contenuto fornendogli esempi da esaminare. Una volta preparato, è possibile utilizzarlo per identificare l'elemento per l'applicazione delle etichette di riservatezza di Office, dei criteri di conformità delle comunicazioni e dei criteri delle etichette di conservazione.

In questo articolo viene illustrato come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori pre-addestrati fornendo loro un feedback aggiuntivo.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere Informazioni sui classificatori disponibili [per il training.](classifier-learn-about.md)

## <a name="permissions"></a>Autorizzazioni

Per accedere ai classificatori nel Centro conformità Microsoft 365:

- Il ruolo di amministratore della conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore

Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:

- Scenario dei criteri di conformità delle comunicazioni: Insider Risk Management Admin, Supervisory Review Administrator 

## <a name="overall-workflow"></a>Flusso di lavoro complessivo

> [!IMPORTANT]
> Fornire feedback nella soluzione di conformità che usa il classificatore come condizione. **Se non si dispone di un criterio di conformità delle comunicazioni che usa un classificatore come condizione, fermarsi qui.**

Quando si utilizzano i classificatori, è possibile aumentare la precisione delle classificazioni che stanno effettuando. A tale scopo, valutare la qualità delle classificazioni effettuate per gli elementi identificati come corrispondenti o meno. Dopo aver evaso 30 valutazioni per un classificatore, questo feedback viene ricevuto e rieserci automaticamente la formazione.

Per ulteriori informazioni sul flusso di lavoro generale di riqualificazione di un classificatore, vedere Flusso di processo per la [riqualificazione di un classificatore.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Un classificatore deve essere già pubblicato e in uso prima di poter essere riesegnato.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>Come riqualificare un classificatore nei criteri di conformità delle comunicazioni

1. Aprire i criteri di conformità delle comunicazioni che utilizzano un classificatore come condizione e scegliere uno degli elementi identificati dall'elenco **In** sospeso.
2. Scegliere i puntini di sospensione e migliorare **la classificazione.**
3. Nel riquadro **Commenti e suggerimenti dettagliati,** se l'elemento è un vero positivo, scegliere **Corrispondenza.**  Se l'elemento è un falso positivo, che è stato incluso in modo errato nella categoria, scegliere **Non corrisponde a.**
4. Se è presente un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci** altri classificatori formabili. In questo modo verrà attivato l'altro classificatore per valutare l'elemento.

> [!TIP]
> Puoi fornire feedback su più elementi contemporaneamente scegliendoli tutti e quindi scegliendo Fornire **feedback dettagliato** nella barra dei comandi.

5. Scegliere **Invia feedback** per inviare la valutazione dei classificatori , le classificazioni e suggerire altri `match` `not a match` classificatori formabili. Quando hai fornito 30 istanze di feedback a un classificatore, verrà automaticamente riesercita la formazione. La riqualificazione può richiedere da 1 a 4 ore. I classificatori possono essere addestrati solo due volte al giorno.

> [!IMPORTANT]
> Queste informazioni passano al classificatore nel tenant, **non tornano a Microsoft.**

6.  Aprire la **pagina Classificazione dati** nel Centro conformità Microsoft **365.**
7. Apri **classificatori che possono essere addestrati.**
8. Il classificatore usato nei criteri di conformità delle comunicazioni verrà visualizzato sotto **l'intestazione Ri-formazione.**

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

9. Al termine della riqualificazione, scegli il classificatore per aprire la panoramica della riqualificazione.

![Panoramica dei risultati di riqualificazione dei classificatori](../media/classifier-retraining-overview.png)

10. Esaminare l'azione consigliata e i confronti di previsione delle versioni riesecite e attualmente pubblicate del classificatore.
11. Se si è soddisfatti dei risultati della riqualificazione, scegliere **Ri publish.**
12. Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriore feedback al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata. 

## <a name="details-on-republishing-recommendations"></a>Dettagli sulla ripubblicazione dei suggerimenti

Ecco un po' di informazioni su come formulare il suggerimento di pubblicare di nuovo un classificatore riqualificato o suggerire un'ulteriore riqualificazione. Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori formabili.

Dopo un nuovo training, valutiamo le prestazioni del classificatore su entrambi gli elementi con feedback, nonché su tutti gli elementi originariamente usati per formare il classificatore. 

- Per i modelli predefiniti, gli elementi usati per formare il classificatore sono gli elementi usati da Microsoft per creare il modello.
- Per i modelli personalizzati, gli elementi usati nel training originale del classificatore sono provenienti dai siti aggiunti per il test e la revisione.

Confrontiamo i numeri delle prestazioni su entrambi i set di elementi per il classificatore rie addestrato e pubblicato per fornire una raccomandazione sull'eventuale miglioramento della ripubblicazione. 

## <a name="see-also"></a>Vedere anche

- [Informazioni sui classificatori sottoponibili a training](classifier-learn-about.md)
- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
