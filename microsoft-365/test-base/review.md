---
title: Revisione
description: Esaminare la sezione dopo l'onboarding.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323285"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Passaggio 6: rivedere le selezioni per creare il pacchetto.

1.  In questa scheda, il servizio visualizza i dettagli del test ed esegue un controllo di completezza rapido. 

    Un ```Validation passed``` messaggio o indica se è possibile procedere o meno ai passaggi ```Validation failed``` successivi.

2.  Esaminare i dettagli del test e, se soddisfatti, fare clic sul ```Create``` pulsante. 

![Convalida della visualizzazione](Media/validation.png)

3.  Questo inserirà il pacchetto nell'ambiente di base di test. Se il pacchetto viene creato correttamente, verrà attivato un test automatizzato che verifica se il pacchetto può essere eseguito correttamente in Azure.

![Risultato positivo](Media/successful.png)

> [!Note]
> Si riceverà una notifica dal portale di Azure per notificare l'esito positivo o negativo della verifica del pacchetto. 
>
> Tieni presente che il processo può richiedere fino a 24 ore, quindi è probabile che la tua pagina Web si timeout se non sei attivo su di esso e quindi la notifica non ti informerà del completamento di questa esecuzione su richiesta. 

  - Peradventure, puoi visualizzare lo stato del pacchetto nella ```Manage packages``` scheda.

![Immagine per la gestione dei pacchetti](Media/managepackages.png)

  - Per i test con successo, i risultati possono essere visualizzati tramite e le pagine a intervalli pianificati, spesso a partire da pochi giorni ```Test Summary``` ```Security Updates Results``` dopo il ```Feature Updates Results``` caricamento.
  
  - Durante i test non riusciti, è necessario caricare un nuovo pacchetto. 
  
    È possibile scaricare ```test logs``` l'oggetto per un'ulteriore analisi dalle ```Security update results``` pagine ' e ```Feature updates results``` .

  - Se si verificano errori di test ripetuti, contattare testbasepreview@microsoft.com informazioni dettagliate sull'errore. 

## <a name="next-steps"></a>Passaggi successivi

Scopri le linee guida per i contenuti tramite il collegamento seguente.
> [!div class="nextstepaction"]
> [Passaggio successivo](contentguideline.md)
