---
title: Come riqualificare un classificatore in Esplora contenuto (anteprima)
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
description: Informazioni su come fornire commenti e suggerimenti a un classificatore addestrabile in Esplora contenuto.
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132326"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a>Come riqualificare un classificatore in Esplora contenuto (anteprima)

Un classificatore addestrabile di Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare. Una volta addestrato, è possibile utilizzarlo per identificare gli elementi per l'applicazione delle etichette di sensibilità di Office, i criteri di conformità delle comunicazioni e i criteri etichette di conservazione.

In questo articolo viene illustrato come migliorare le prestazioni dei classificatori addestrabili personalizzati e di alcuni classificatori preformati fornendo loro commenti e suggerimenti aggiuntivi.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere [informazioni sui classificatori addestrabili (Preview)](classifier-learn-about.md).

## <a name="permissions"></a>Autorizzazioni

Per accedere ai classificatori nel centro conformità di Microsoft 365:

- il ruolo di amministratore conformità o l'amministratore dei dati di conformità è necessario per formare un classificatore

Sono necessari account con queste autorizzazioni per l'utilizzo dei classificatori in questi scenari:

- Scenario dei criteri per l'etichetta di conservazione: ruoli Gestione record e gestione conservazione 

## <a name="overall-workflow"></a>Flusso di lavoro globale

> [!IMPORTANT]
> È possibile fornire commenti e suggerimenti in Esplora contenuto per applicare automaticamente i criteri delle etichette di conservazione per scambiare gli elementi e utilizza il classificatore come condizione. **Se non si dispone di un criterio di conservazione che applica automaticamente un'etichetta di conservazione agli elementi di Exchange e utilizza un classificatore come condizione, interrompere l'applicazione.**

Quando si utilizzano i classificatori, è possibile aumentare la precisione delle classificazioni che stanno facendo. A tale scopo, valutare la qualità delle classificazioni eseguite per gli elementi identificati come una corrispondenza o non una corrispondenza. Dopo aver eseguito 30 valutazioni per un classificatore, è necessario che i commenti e suggerimenti vengano riaddestrati automaticamente.

Per ulteriori informazioni sul flusso di lavoro globale di riqualificazione di un classificatore, vedere [Process Flow for retraining a Classificator](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Un classificatore deve essere già pubblicato e in uso prima che possa essere riaddestrato.

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a>Come riqualificare un classificatore in Esplora contenuto (anteprima)

1. Accedere al centro conformità Microsoft 365 con l'accesso al ruolo amministratore di sicurezza o di amministratore della protezione e aprire **Microsoft 365 Compliance Center**  >  **Data classificazione**  >  **Content Explorer**. 
2. Nell'elenco **filtro su etichette, tipi di informazioni o categorie** , espandere **classificatori addestrabili**.

> [!IMPORTANT]
> È possibile richiedere fino a otto giorni affinché gli elementi aggregati vengano visualizzati nell'intestazione dei classificatori addestrabili.

3. Scegliere il classificatore addestrabile utilizzato nei criteri di etichetta di conservazione applicati automaticamente. Questo è il classificatore addestrabile che fornirà commenti e suggerimenti.

> [!NOTE]
> Se un elemento contiene una voce nella colonna **etichetta di conservazione** , significa che l'elemento è stato classificato come a `match` .  Se un elemento non dispone di una voce nella colonna **etichetta di conservazione** , significa che è stata classificata come a `close match` . È possibile migliorare maggiormente la precisione del classificatore fornendo commenti e suggerimenti sugli `close match` elementi. 

4. Scegliere un elemento e aprirlo.
 
 > [!TIP]
> È possibile fornire commenti e suggerimenti su più elementi contemporaneamente, scegliendo tutti e quindi scegliendo **migliora classificazione** nella barra dei comandi.

5. Scegliere **Fornisci commenti e suggerimenti**.
6. Nel riquadro dei **commenti e suggerimenti dettagliati** , se l'elemento è un valore true positive, scegliere **match**.  Se l'elemento è un falso positivo, ovvero non è stato incluso in modo errato nella categoria, scegliere **non una corrispondenza**.
7. Se è presente un altro classificatore più appropriato per l'elemento, è possibile sceglierlo nell'elenco **Suggerisci altri classificatori addestrabili** . Questo attiverà l'altro classificatore per valutare l'elemento.
8. Scegliere **Invia commenti e suggerimenti** per inviare la valutazione `match` delle `not a match` classificazioni e suggerire altri classificatori addestrabili. Quando sono state fornite 30 istanze di commenti e suggerimenti a un classificatore, la riqualificazione viene automaticamente. La riqualificazione può richiedere da 1 a 4 ore. I classificatori possono essere riaddestrati solo due volte al giorno.

> [!IMPORTANT]
> Queste informazioni passano al classificatore del tenant, **ma non tornano a Microsoft**.

9. Aprire **classificatori addestrabili (anteprima)**.
10. Il classificatore che è stato utilizzato nei criteri di conformità delle comunicazioni verrà visualizzato nell'intestazione **riqualificazione** .

![classificatore nello stato di riqualificazione](../media/classifier-retraining.png)

11. Una volta completata la riqualificazione, scegliere il classificatore per aprire la panoramica sulla riqualificazione.

![Panoramica dei risultati di riqualificazione del classificatore](../media/classifier-retraining-overview.png)

12. Esaminare l'azione consigliata e i confronti di stima delle versioni riqualificate e attualmente pubblicate del classificatore.
13. Se si è soddisfatti dei risultati della riqualificazione, scegliere **ripubblicare**.
14. Se non si è soddisfatti dei risultati della riqualificazione, è possibile scegliere di fornire ulteriori commenti e suggerimenti al classificatore nell'interfaccia di conformità delle comunicazioni e avviare un altro ciclo di riqualificazione o non eseguire alcuna operazione nel qual caso la versione attualmente pubblicata del classificatore continuerà a essere utilizzata. 

## <a name="details-on-republishing-recommendations"></a>Informazioni dettagliate sulla ripubblicazione dei suggerimenti

Ecco alcune informazioni su come formulare la raccomandazione di ripubblicare un classificatore riaddestrato o suggerire ulteriori ricorsi. Ciò richiede una conoscenza più approfondita del funzionamento dei classificatori addestrabili.

Dopo una riqualificazione, vengono valutate le prestazioni del classificatore sia sugli elementi con feedback, sia su tutti gli elementi originariamente utilizzati per formare il classificatore. 

- Per i modelli incorporati, gli elementi utilizzati per la formazione del classificatore sono gli elementi utilizzati da Microsoft per creare il modello.
- Per i modelli personalizzati, gli elementi utilizzati nell'allenamento originale il classificatore è compreso tra i siti aggiunti per il test e la revisione.

Vengono confrontati i numeri di prestazioni su entrambi i set di elementi per il classificatore riaddestrato e pubblicato per fornire una raccomandazione sull'eventuale ripubblicazione del miglioramento. 

## <a name="see-also"></a>Vedere anche

- [Informazioni sui classificatori addestrabili (anteprima)](classifier-learn-about.md)
- [Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
