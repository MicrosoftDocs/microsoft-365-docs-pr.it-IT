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
description: Informazioni su come usare la modalità di accessibilità durante la formazione di un modello in SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515149"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Modalità di accessibilità di SharePoint Syntex

In [SharePoint Syntex,](index.md)gli utenti possono attivare la modalità accessibilità in tutte le fasi del training del modello (etichetta, formazione, test) quando si lavora con documenti di esempio. L'uso della modalità di accessibilità può aiutare gli utenti con problemi di vista a semplificare l'accessibilità tramite tastiera mentre si spostano e etichettano gli elementi nel visualizzatore di documenti.

Ciò consente agli utenti di usare le tastiere per spostarsi all'interno del testo nel visualizzatore di documenti e ascoltare un commento audio non solo sui valori selezionati, ma anche sulle azioni (ad esempio l'etichettatura o la rimozione di etichette dal testo selezionato) o sui valori delle etichette previsti durante il training del modello con altri documenti di esempio. 


![Modalità accessibilità](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Requisiti

Per ascoltare l'audio del commento audio, assicurati di attivare [l'app](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) Assistente vocale nelle impostazioni dell'Assistente vocale nel sistema Windows 10.

![Attivare l'Assistente vocale](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Etichettatura per gli utenti della tastiera

Per gli utenti che usano la modalità accessibilità, se stai etichettando il testo in un documento di esempio nel visualizzatore, puoi usare i tasti seguenti:

- Tab: sposta l'utente in avanti e seleziona la parola successiva.
- TAB + MAIUSC: consente di spostarsi all'indietro e selezionare la parola precedente.
- Invio: etichetta o rimuove un'etichetta dalla parola selezionata.
- Freccia destra: consente di spostarsi in avanti tra i singoli caratteri di una parola selezionata.
- Freccia sinistra: consente di spostarsi all'indietro tra i singoli caratteri di una parola selezionata.

> [!NOTE]
> Se si etichettano più parole per una singola etichetta, è necessario etichettare ogni parola.


## <a name="narration"></a>Commenti audio

Per gli utenti dell'Assistente vocale che usano la modalità accessibilità, usa lo stesso spostamento tramite tastiera descritto per consentire agli utenti della tastiera di passare attraverso il documento di esempio nel visualizzatore.

Durante lo spostamento tra i documenti di esempio e i valori delle stringhe delle etichette, l'Assistente vocale offrirà all'utente le istruzioni audio seguenti:

- Quando usi la tastiera per spostarsi all'interno del visualizzatore di documenti, l'audio dell'Assistente vocale segnalerà la stringa selezionata.
- All'interno di una stringa selezionata, l'audio dell'Assistente vocale segnalerà ogni carattere nella stringa durante la selezione usando i tasti di direzione sinistro o destro.
- Se si seleziona una stringa etichettata, l'Assistente vocale indica il valore e quindi "etichetta".  Ad esempio, se il valore dell'etichetta è "Contoso", verrà visualizzato lo stato "Costoso etichettato". 
- Nella scheda formazione, se si seleziona una stringa nel visualizzatore di documenti che è stata solo stimata, l'audio dell'Assistente vocale indica il valore e quindi "previsto". Ciò si verifica quando il training prevede un valore nel file che non corrisponde a quello etichettato dall'utente.
- Nella scheda training, se si seleziona una stringa nel visualizzatore di documenti che è stata etichettata e stimata, l'audio dell'Assistente vocale indica il valore e quindi "etichettato e previsto". Ciò si verifica quando il training ha esito positivo ed esiste una corrispondenza tra un valore previsto e l'etichetta utente.



Dopo l'etichetta di una stringa o la rimozione di un'etichetta nel visualizzatore, l'audio dell'Assistente vocale ti avvisa di salvare le modifiche prima di uscire.

## <a name="see-also"></a>Vedere anche

[Creare un estrattore](create-an-extractor.md)</br>

[Creare un classificatore](create-a-classifier.md)</br>










 


  
  



