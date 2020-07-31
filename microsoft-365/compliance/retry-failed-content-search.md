---
title: Riprovare una ricerca contenuto per risolvere un errore del percorso del contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Durante un'analisi, è possibile utilizzare il pulsante Riprova per risolvere le ricerche di contenuto che presentano errori di posizione del contenuto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 55ef7ff59bfc58809d0e00ff1f2edf7a8455ba13
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527634"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Riprovare una ricerca contenuto per risolvere un errore del percorso del contenuto

Quando si utilizza la ricerca contenuto nel centro sicurezza e conformità per eseguire ricerche in un numero elevato di cassette postali, è possibile che si verifichino errori di ricerca simili all'errore:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Tali errori (con i codici di errore di CS001-002, CS003-002, CS008-009, CS012-002 e altri errori del modulo CS0XX-0XX) indicano che la ricerca contenuto non è riuscita a individuare percorsi di contenuto specifici. in questo esempio non sono state cercate due cassette postali. Questi errori vengono visualizzati nella pagina del riquadro a comparsa dei dettagli sullo stato della ricerca contenuto.

## <a name="cause-of-content-location-errors"></a>Causa degli errori del percorso del contenuto

Quando si esegue la ricerca di un numero elevato di cassette postali, la ricerca viene distribuita in migliaia di server in un datacenter Microsoft. In una sola volta, i server specifici potrebbero essere nello stato di riavvio o nel processo di failover di copie ridondanti. In entrambi i casi, la richiesta di ricerca del contenuto per il recupero dei dati scadrà. Nell'esempio precedente gli errori relativi alle cassette postali non riuscite sono stati causati dal timeout della ricerca.

## <a name="resolving-content-location-errors"></a>Risoluzione degli errori relativi alla posizione del contenuto

Il riavvio della ricerca spesso comporterà errori simili su server diversi. Invece di riavviare la ricerca, fare clic sul pulsante **Riprova** visualizzato nella parte superiore della pagina dei risultati di ricerca.

![Fare clic sul pulsante Riprova per risolvere gli errori relativi alla posizione del contenuto](../media/retrycontentsearch3.png)

In questo modo, la ricerca verrà ritentata solo per le cassette postali che hanno avuto esito negativo. Quando si ritenta la ricerca, vengono mantenuti gli altri risultati restituiti correttamente.

## <a name="tips-to-avoid-content-location-errors"></a>Suggerimenti per evitare errori di posizione del contenuto

Di seguito sono riportate alcune altre cause degli errori relativi alla posizione del contenuto e alcuni suggerimenti utili per evitarli durante la ricerca di un numero elevato di cassette postali.

- La cassetta postale che si sta cercando potrebbe essere occupata a causa dell'attività dell'utente. In questo caso, il servizio di ricerca potrebbe limitarsi a impedire che la cassetta postale diventi non disponibile. Per evitare questo, provare a eseguire le ricerche durante gli orari non di ufficio.

- La query di ricerca potrebbe recuperare troppo contenuto dalla cassetta postale. Se possibile, provare a restringere l'ambito della ricerca utilizzando parole chiave, intervalli di date e condizioni di ricerca.

- Se si crea una query di ricerca utilizzando l' [elenco delle parole](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)chiave, vengono create troppe parole chiavi o frasi. Quando si esegue una query di ricerca che utilizza l'elenco di parole chiave, il servizio esegue essenzialmente una ricerca distinta per ogni riga dell'elenco di parole chiave in modo che le statistiche possano essere generate. Se si utilizza l'elenco delle parole chiave nelle query di ricerca, ridurre al minimo il numero di righe nell'elenco parole chiave o dividere il numero in elenchi di dimensioni ridotte e creare una ricerca diversa per ogni elenco di parola chiave.

  > [!NOTE]
  > Per contribuire a ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, si è limitato a un massimo di 20 righe nell'elenco delle parole chiave di una query di ricerca.

- Sono state eseguite troppe ricerche contemporaneamente sulla stessa cassetta postale. Se possibile, provare a eseguire una ricerca alla volta su una cassetta postale.

- Ricerca di un numero eccessivo di cassette postali in una singola ricerca. Quando si esegue la ricerca di un numero elevato di cassette postali, aumenta la probabilità che si verifichino errori. Se possibile, provare a eseguire più ricerche in modo che ogni ricerca includa un sottoinsieme di cassette postali nell'organizzazione.

- La manutenzione necessaria viene eseguita sulla cassetta postale. Anche se questa causa si verifica raramente, attendere un po' di tempo dopo aver ricevuto l'errore relativo alla posizione del contenuto e quindi riprovare la ricerca.
