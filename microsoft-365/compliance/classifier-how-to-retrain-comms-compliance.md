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
description: Informazioni su come fornire feedback a un classificatore addestrabile in Conformità comunicazioni.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918147"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Come ripetere il training di un classificatore in Conformità alle comunicazioni

Un classificatore di Microsoft 365 addestrabile è uno strumento che è possibile addestrare a riconoscere vari tipi di contenuto fornendogli esempi da esaminare. Una volta addestrato, è possibile utilizzarlo per identificare l'elemento per l'applicazione delle etichette di riservatezza di Office, dei criteri di conformità delle comunicazioni e dei criteri delle etichette di conservazione.

Questo articolo illustra come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori pre-addestrati fornendo loro un feedback aggiuntivo.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere [Learn about trainable classifiers](classifier-learn-about.md).

## <a name="permissions"></a>Autorizzazioni

Per accedere ai classificatori nel Centro conformità Microsoft 365:

- il ruolo di amministratore della conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore

Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:

- Scenario dei criteri di conformità della comunicazione: Insider Risk Management Admin, Supervisory Review Administrator 

## <a name="overall-workflow"></a>Flusso di lavoro complessivo

> [!IMPORTANT]
> Fornisci feedback nella soluzione di conformità che usa il classificatore come condizione. **Se non si dispone di un criterio di conformità delle comunicazioni che usa un classificatore come condizione, arrestarsi qui.**

Quando usi i classificatori, potresti voler aumentare la precisione delle classificazioni che stanno effettuando. A tale scopo, valutare la qualità delle classificazioni effettuate per gli elementi identificati come corrispondenti o meno. Dopo aver fatto 30 valutazioni per un classificatore, è necessario ricevere tale feedback e riqualificare automaticamente se stesso.

Per ulteriori informazioni sul flusso di lavoro complessivo di riqualificazione di un classificatore, vedere [Process flow for retraining a classifier.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Un classificatore deve essere già pubblicato e in uso prima di poter essere nuovamente addestrato.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>Come riqualificare un classificatore nei criteri di conformità delle comunicazioni

1. Aprire i criteri di conformità di comunicazione che utilizzano un classificatore come condizione e scegliere uno degli elementi identificati **nell'elenco In** sospeso.
2. Scegliere i puntini di sospensione e **Migliorare la classificazione.**
3. Nel riquadro **Feedback dettagliato,** se l'elemento è un vero positivo, scegliere **Corrispondenza**.  Se l'elemento è un falso positivo, che è stato incluso in modo errato nella categoria, scegliere **Non corrisponde.**
4. Se esiste un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci** altri classificatori trainabili. Questo attiverà l'altro classificatore per valutare l'elemento.

> [!TIP]
> È possibile fornire commenti e suggerimenti su più elementi contemporaneamente scegliendoli tutti e quindi scegliendo Fornire **commenti e suggerimenti dettagliati** nella barra dei comandi.

5. Scegliere **Invia feedback** per inviare la valutazione di , `match` `not a match` classificazioni e suggerire altri classificatori addestrabili. Quando hai fornito 30 istanze di feedback a un classificatore, verrà automaticamente riqualificato. La riqualificazione può richiedere da 1 a 4 ore. I classificatori possono essere addestrati solo due volte al giorno.

> [!IMPORTANT]
> Queste informazioni passano al classificatore nel tenant, **non tornano a Microsoft**.

6.  Aprire la **pagina Classificazione dati** nel Centro conformità Microsoft **365.**
7. Aprire **Classificatori trainabili**.
8. Il classificatore utilizzato nei criteri di conformità comunicazioni verrà visualizzato sotto **l'intestazione Ri-formazione.**

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

9. Al termine della riqualificazione, scegli il classificatore per aprire la panoramica della riqualificazione.

![Panoramica dei risultati di riqualificazione classificatore](../media/classifier-retraining-overview.png)

10. Esaminare l'azione consigliata e i confronti di previsione delle versioni di cui è stato eseguito il training e attualmente pubblicate del classificatore.
11. Se si è soddisfatti dei risultati della riqualificazione, scegliere **Ri publish**.
12. Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriore feedback al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata. 

## <a name="details-on-republishing-recommendations"></a>Dettagli sulla ripubblicazione dei suggerimenti

Ecco un po' di informazioni su come formulare il suggerimento per pubblicare di nuovo un classificatore riqualificato o suggerire un'ulteriore riqualificazione. Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori addestrabili.

Dopo una riqualificazione, valutiamo le prestazioni del classificatore sia sugli elementi con feedback che su tutti gli elementi originariamente usati per formare il classificatore. 

- Per i modelli predefiniti, gli elementi usati per eseguire il training del classificatore sono gli elementi usati da Microsoft per creare il modello.
- Per i modelli personalizzati, gli elementi utilizzati nel training originale del classificatore derivano dai siti aggiunti per il test e la revisione.

Confrontiamo i numeri delle prestazioni su entrambi i set di elementi per il classificatore rie addestrato e pubblicato per fornire un suggerimento sull'eventuale miglioramento della ripubblicazione. 

## <a name="see-also"></a>Vedere anche

- [Informazioni sui classificatori sottoponibili a training](classifier-learn-about.md)
- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)