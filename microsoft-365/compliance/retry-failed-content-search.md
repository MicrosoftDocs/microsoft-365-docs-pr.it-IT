---
title: Ritentare una ricerca di contenuto per risolvere un errore di percorso del contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Durante un'indagine, è possibile utilizzare il pulsante Riprova per risolvere le ricerche di contenuto con errori relativi alla posizione del contenuto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311821"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Ritentare una ricerca di contenuto per risolvere un errore di percorso del contenuto

Quando si utilizza Ricerca contenuto nel Centro sicurezza e conformità per cercare un numero elevato di cassette postali, è possibile che si otterrà errori di ricerca simili all'errore:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Questi errori (con codici di errore CS001-002, CS003-002, CS008-009, CS012-002 e altri errori nel formato CS0XX-0XX) indicano che ricerca contenuto non è riuscita a cercare percorsi di contenuto specifici. in questo esempio, non è stata ricercata due cassette postali. Questi errori vengono visualizzati nella pagina a comparsa dei dettagli sullo stato della ricerca contenuto.

## <a name="cause-of-content-location-errors"></a>Causa degli errori relativi al percorso del contenuto

Quando si esegue una ricerca in un numero elevato di cassette postali, la ricerca viene distribuita su migliaia di server in un datacenter Microsoft. In qualsiasi momento, server specifici potrebbero essere in stato di riavvio o in fase di failover in copie ridondanti. In uno di questi casi, il timeout della richiesta di recupero dei dati da parte della ricerca di contenuto. Nell'esempio precedente, gli errori per le cassette postali non riuscite erano il risultato del timeout della ricerca.

## <a name="resolving-content-location-errors"></a>Risoluzione degli errori relativi alla posizione del contenuto

Il riavvio della ricerca spesso genererà errori simili in server diversi. Anziché riavviare la ricerca, fare clic sul pulsante **Riprova** visualizzato nella parte superiore della pagina dei risultati della ricerca.

![Fare clic sul pulsante Riprova per risolvere gli errori relativi alla posizione del contenuto](../media/retrycontentsearch3.png)

In questo modo verrà eseguito un nuovo tentativo di ricerca solo per le cassette postali non riuscite. Quando si ritenta la ricerca, gli altri risultati restituiti correttamente vengono mantenuti.

## <a name="tips-to-avoid-content-location-errors"></a>Suggerimenti evitare errori relativi al percorso del contenuto

Ecco alcune cause aggiuntive degli errori relativi alla posizione del contenuto e alcuni suggerimenti per evitarli durante la ricerca di un numero elevato di cassette postali.

- La cassetta postale da cercare potrebbe essere occupata a causa dell'attività dell'utente. In questo caso, il servizio di ricerca potrebbe essere limitato per evitare che la cassetta postale diventi non disponibile. Per evitare questo problema, provare a eseguire ricerche durante l'orario non di ufficio.

- La query di ricerca potrebbe recuperare troppo contenuto dalla cassetta postale. Se possibile, provare a restringere l'ambito della ricerca utilizzando parole chiave, intervalli di date e condizioni di ricerca.

- Troppe parole chiave o frasi di parole chiave quando si crea una query di ricerca utilizzando [l'elenco di parole chiave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches). Quando si esegue una query di ricerca che utilizza l'elenco di parole chiave, il servizio esegue essenzialmente una ricerca separata per ogni riga dell'elenco di parole chiave in modo da poter generare statistiche. Se si utilizza l'elenco di parole chiave nelle query di ricerca, ridurre al minimo il numero di righe nell'elenco di parole chiave o dividere le parole chiave del numero in elenchi più piccoli e creare una ricerca diversa per ogni elenco di parole chiave.

  > [!NOTE]
  > Per ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, ora si è limitati a un massimo di 20 righe nell'elenco di parole chiave di una query di ricerca.

- Troppe ricerche vengono eseguite contemporaneamente sulla stessa cassetta postale. Se possibile, provare a eseguire una ricerca alla volta in una cassetta postale.

- Ricerca di troppe cassette postali in una singola ricerca. La probabilità di errori del percorso del contenuto aumenta durante la ricerca in un numero elevato di cassette postali. Se possibile, provare a eseguire più ricerche in modo che ogni ricerca includa un sottoinsieme di cassette postali nell'organizzazione.

- È in corso la manutenzione necessaria per la cassetta postale. Anche se questa causa probabilmente si verifica raramente, attendere un po' dopo aver ricevuto l'errore del percorso del contenuto e quindi ritentare la ricerca.
