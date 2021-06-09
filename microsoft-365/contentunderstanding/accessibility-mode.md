---
title: 'Modalità di accessibilità di SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Scopri come usare la modalità di accessibilità durante il training di un modello in SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515149"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Modalità di accessibilità di SharePoint Syntex

In [SharePoint Syntex,](index.md)gli utenti possono attivare la modalità di accessibilità in tutte le fasi del training del modello (etichetta, training, test) quando si lavora con documenti di esempio. L'uso della modalità di accessibilità può aiutare gli utenti con problemi di vista a semplificare l'accessibilità tramite tastiera man mano che si spostano e etichettano gli elementi nel visualizzatore di documenti.

In questo modo, gli utenti possono usare le tastiere per spostarsi all'interno del testo nel visualizzatore di documenti e ascoltare un commento non solo sui valori selezionati, ma anche sulle azioni (ad esempio l'etichettatura o la rimozione di etichette dal testo selezionato) o sui valori previsti dell'etichetta durante il training del modello con altri documenti di esempio. 


![Modalità accessibilità](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Requisiti

Per ascoltare l'audio del commento audio, assicurati di attivare [l'app Assistente vocale](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) nelle impostazioni Assistente vocale nel sistema Windows 10 audio.

![Attivare Assistente vocale](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Etichettatura per gli utenti della tastiera

Per gli utenti della tastiera che usano la modalità di accessibilità, se stai etichettando il testo in un documento di esempio nel visualizzatore, puoi usare i tasti seguenti:

- Tab: sposta l'utente in avanti e seleziona la parola successiva.
- TAB + MAIUSC: consente di spostarsi all'indietro e selezionare la parola precedente.
- Invio: etichetta o rimuove un'etichetta dalla parola selezionata.
- Freccia destra: consente di spostarsi in avanti tra i singoli caratteri di una parola selezionata.
- Freccia sinistra: consente di spostarsi all'indietro tra i singoli caratteri di una parola selezionata.

> [!NOTE]
> Se si stanno etichettando più parole per una singola etichetta, è necessario etichettare ogni parola.


## <a name="narration"></a>Commento audio

Per Assistente vocale utenti che usano la modalità di accessibilità, usa la stessa navigazione da tastiera descritta per gli utenti con tastiera per passare attraverso il documento di esempio nel visualizzatore.

Durante lo spostamento tra i documenti di esempio e i valori delle stringhe di etichetta, Assistente vocale all'utente verranno visualizzate le istruzioni audio seguenti:

- Quando usi la tastiera per spostarsi nel visualizzatore di documenti, Assistente vocale'audio segnalerà la stringa selezionata.
- All'interno di una stringa selezionata, Assistente vocale audio segnalerà ogni carattere nella stringa mentre li si seleziona utilizzando i tasti freccia sinistra o destra.
- Se si seleziona una stringa etichettata, Assistente vocale il valore e quindi "etichettato".  Ad esempio, se il valore dell'etichetta è "Contoso", verrà visualizzato "Costoso etichettato". 
- Nella scheda training, se si seleziona una stringa nel visualizzatore di documenti che è stata solo stimata, Assistente vocale audio indica il valore e quindi "previsto". Ciò si verifica quando il training prevede un valore nel file che non corrisponde a quello etichettato dall'utente.
- Nella scheda training, se si seleziona una stringa nel visualizzatore di documenti che è stata etichettata e stimata, Assistente vocale audio verrà specificato il valore e quindi "etichettato e previsto". Ciò si verifica quando la formazione ha esito positivo e esiste una corrispondenza tra un valore previsto e l'etichetta utente.



Dopo l'etichetta di una stringa o la rimozione di un'etichetta nel visualizzatore, l Assistente vocale audio ti avvisa di salvare le modifiche prima di uscire.

## <a name="see-also"></a>Vedere anche

[Creare un estrattore](create-an-extractor.md)</br>

[Creare un classificatore](create-a-classifier.md)</br>










 


  
  



