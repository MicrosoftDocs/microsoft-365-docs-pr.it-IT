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
description: Scopri come fornire feedback a un classificatore addestrabile in Esplora contenuto.
ms.openlocfilehash: d61437634dcad7f01a6737947b0f32f42de2818e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918102"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Come ripetere il training di un classificatore in Esplora contenuto

Un classificatore di Microsoft 365 addestrabile è uno strumento che è possibile addestrare a riconoscere vari tipi di contenuto fornendogli esempi da esaminare. Una volta addestrato, è possibile utilizzarlo per identificare l'elemento per l'applicazione delle etichette di riservatezza di Office, dei criteri di conformità delle comunicazioni e dei criteri delle etichette di conservazione.

Questo articolo illustra come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori pre-addestrati fornendo loro un feedback aggiuntivo.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere [Learn about trainable classifiers](classifier-learn-about.md).

Guarda questo video per un breve riepilogo del processo di ottimizzazione e riqualificazione. Dovrai comunque leggere questo articolo completo per ottenere i dettagli.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Autorizzazioni

Per accedere ai classificatori nel Centro conformità Microsoft 365:

- il ruolo di amministratore della conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore

Per usare i classificatori in questi scenari, sono necessari account con queste autorizzazioni:

- Scenario dei criteri di etichetta di conservazione: ruoli Gestione record e Gestione conservazione 

## <a name="overall-workflow"></a>Flusso di lavoro complessivo

> [!IMPORTANT]
> È possibile fornire commenti e suggerimenti in Esplora contenuto per applicare automaticamente i criteri delle etichette di conservazione agli elementi di Exchange e utilizzare il classificatore come condizione. **Se non si dispone di un criterio di conservazione che applica automaticamente un'etichetta di conservazione agli elementi di Exchange e utilizza un classificatore come condizione, arrestarsi qui.**

Quando usi i classificatori, potresti voler aumentare la precisione delle classificazioni che stanno effettuando. A tale scopo, valutare la qualità delle classificazioni effettuate per gli elementi identificati come corrispondenti o meno. Dopo aver fatto 30 valutazioni per un classificatore, è necessario ricevere tale feedback e riqualificare automaticamente se stesso.

Per ulteriori informazioni sul flusso di lavoro complessivo di riqualificazione di un classificatore, vedere [Process flow for retraining a classifier.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Un classificatore deve essere già pubblicato e in uso prima di poter essere nuovamente addestrato.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Come ripetere il training di un classificatore in Esplora contenuto

1. Accedere al Centro conformità Microsoft 365 con l'accesso al ruolo amministratore della conformità o amministratore della sicurezza e aprire Microsoft **365 Compliance Center**  >  **Data classification Content**  >  **explorer**. 
2. **Nell'elenco Filtra in base a etichette, tipi** di informazioni o categorie espandi **Classificatori sotto forma di classificatori.**

> [!IMPORTANT]
> La visualizzazione degli elementi aggregati sotto l'intestazione classificatori sotto il training può richiedere fino a otto giorni.

3. Scegliere il classificatore addestrabile usato per applicare automaticamente i criteri delle etichette di conservazione. Questo è il classificatore formabile su cui darai feedback.

> [!NOTE]
> Se un elemento include una voce nella **colonna Etichetta di** conservazione, significa che l'elemento è stato classificato come `match` .  Se un elemento non dispone di una voce nella colonna **Etichetta** di conservazione, significa che è stato classificato come `close match` . Puoi migliorare al massimo la precisione del classificatore fornendo feedback sugli `close match` elementi. 

4. Scegliere un elemento e aprirlo.
 
 > [!TIP]
> È possibile fornire commenti e suggerimenti su più elementi contemporaneamente scegliendoli tutti e quindi scegliendo **Migliora classificazione** nella barra dei comandi.

5. Scegliere **Fornisci feedback.**
6. Nel riquadro **Feedback dettagliato,** se l'elemento è un vero positivo, scegliere **Corrispondenza**.  Se l'elemento è un falso positivo, che è stato incluso in modo errato nella categoria, scegliere **Non corrisponde.**
7. Se esiste un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci** altri classificatori trainabili. Questo attiverà l'altro classificatore per valutare l'elemento.
8. Scegliere **Invia feedback** per inviare la valutazione di , `match` `not a match` classificazioni e suggerire altri classificatori addestrabili. Quando hai fornito 30 istanze di feedback a un classificatore, verrà automaticamente riqualificato. La riqualificazione può richiedere da una a quattro ore. I classificatori possono essere addestrati solo due volte al giorno.

> [!IMPORTANT]
> Queste informazioni passano al classificatore nel tenant, **non tornano a Microsoft**.

9. Aprire **Classificatori trainabili**.
10. Il classificatore utilizzato nei criteri di conformità comunicazioni verrà visualizzato sotto **l'intestazione Ri-formazione.**

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

11. Al termine della riqualificazione, scegli il classificatore per aprire la panoramica della riqualificazione.

![Panoramica dei risultati di riqualificazione classificatore](../media/classifier-retraining-overview.png)

12. Esaminare l'azione consigliata e i confronti di previsione delle versioni di cui è stato eseguito il training e attualmente pubblicate del classificatore.
13. Se si è soddisfatti dei risultati della riqualificazione, scegliere **Ri publish**.
14. Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriore feedback al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata. 

## <a name="details-on-republishing-recommendations"></a>Dettagli sulla ripubblicazione dei suggerimenti

Ecco un po' di informazioni su come formulare il suggerimento per pubblicare di nuovo un classificatore riqualificato o suggerire un'ulteriore riqualificazione. Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori addestrabili.

Dopo una riqualificazione, valutiamo le prestazioni del classificatore sia sugli elementi con feedback che su tutti gli elementi originariamente usati per formare il classificatore. 

- Per i modelli predefiniti, gli elementi usati per eseguire il training del classificatore sono gli elementi usati da Microsoft per creare il modello.
- Per i modelli personalizzati, gli elementi utilizzati nel training originale del classificatore derivano dai siti aggiunti per il test e la revisione.

Confrontiamo i numeri delle prestazioni su entrambi i set di elementi per il classificatore rie addestrato e pubblicato per fornire un suggerimento sull'eventuale miglioramento della ripubblicazione. 

## <a name="see-also"></a>Vedere anche

- [Informazioni sui classificatori sottoponibili a training](classifier-learn-about.md)
- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)