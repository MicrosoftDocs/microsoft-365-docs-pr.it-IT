---
title: Ciclo di vita del prodotto Microsoft Managed Desktop
description: Questo articolo elenca le specifiche dei dispositivi usate in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841200"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Ciclo di vita del prodotto Microsoft Managed Desktop

Microsoft Managed Desktop offre vantaggi agli utenti assicurando che usano sempre dispositivi che offrono le migliori funzionalità di prestazioni, affidabilità, progettazione e sicurezza (ad esempio il supporto per funzionalità come Windows Hello). A tale scopo, Microsoft Managed Desktop gestisce un breve catalogo di dispositivi approvati [continuamente aggiornati.](device-list.md) 
 
Questo articolo descrive in dettaglio il ciclo di vita dei dispositivi che vengono aggiunti e rimossi dal catalogo approvato. 

> [!NOTE]
> In questo argomento verrà fatta una distinzione tra un "dispositivo" e un "prodotto". Per "dispositivo" si intende un singolo computer specifico. Ad esempio, "Numero di serie 1234", "Portatile di Bill", "Macchina virtuale condivisa XYZ" fanno riferimento a dispositivi specifici. Un "prodotto", tuttavia, fa riferimento a una raccolta o a una famiglia di dispositivi. Ad esempio, "Fabrikam Laptop", "Adatum ZX450 Laptop" e così via. Questo è importante perché i prodotti vengono aggiunti all'elenco [approvato](device-list.md)o al catalogo e i dispositivi vengono registrati in Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Ciclo di vita del prodotto

 In genere, i prodotti passano attraverso queste fasi del ciclo di vita:

- [Rilascio e valutazione del prodotto](#product-release-and-evaluation)
- [Periodo di disponibilità principale del prodotto](#product-primary-availability-period)
- [Periodo di tolleranza del prodotto](#product-grace-period)
- [Ritiro del prodotto](#product-retirement)


Questa figura mostra l'intera sequenza:

![Sequenza temporale del ciclo di vita: a partire dalla disponibilità generale del prodotto, la "disponibilità principale" dura due anni. Durante questo periodo di tempo la finestra di certificazione termina e a un certo punto il dispositivo viene onboarded. Al termine della disponibilità principale, il prodotto viene archiviato e inizia il "periodo di tolleranza" di tre anni. A partire dall'onboarded, il dispositivo ha un periodo di utilizzo di 3 anni fino a quando non viene rimosso dalla gestione. Al termine del periodo di tolleranza, il prodotto viene rimosso dal catalogo.](../../media/non-dark1-edits.PNG)

I prodotti rimangono nel catalogo per un <em></em> massimo di 24 mesi, ma i dispositivi rimangono sotto gestione per tre anni in base alle date di registrazione individuale. In effetti, ogni prodotto ha tre date importanti, ma ogni dispositivo ne ha solo una. Per i prodotti, tutte e tre <em></em>queste date vengono calcolate in base alla data di approvazione e pertanto tali date vengono pubblicate dopo l'approvazione, in modo da poter sempre guardare avanti e pianificare in modo appropriato l'intero ciclo di vita del prodotto.

Questa tabella mostra le date di esempio per un prodotto teorico:


|Prodotto  |Data approvazione  |Fine della disponibilità principale  |Fine dell'idoneità  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Portatile Adatum   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

Questa tabella mostra le date di esempio per i dispositivi *teorici:*


|ID dispositivo  |Data di registrazione  |Data di ritiro  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Desktop #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Rilascio e valutazione del prodotto

Il ciclo di vita del prodotto inizia quando un produttore rilascia pubblicamente il prodotto:

![Sequenza temporale del ciclo di vita che mostra il periodo di rilascio e valutazione](../../media/non-dark3-edits.PNG)

Durante questa fase, il team di progettazione di Microsoft Managed Desktop esegue la valutazione e la certificazione di un prodotto. Il team valuta aspetti come affidabilità e prestazioni con Windows, conformità a una linea di base hardware, valutazione del mercato e preparazione dell'inventario e del canale, tra le altre cose. Questo processo in genere richiede circa sei settimane.
  
Microsoft Managed Desktop valuterà i dispositivi per la certificazione solo entro i primi sei mesi di disponibilità. Questo criterio garantisce che il nostro impegno sia sempre focalizzato sull'ultima generazione di hardware.
 
Al termine di questa fase, Microsoft Managed Desktop aggiunge il prodotto all'elenco [approvato,](device-list.md)rilasciando in modo efficace il prodotto per le registrazioni dei clienti. Indipendentemente dalla data in cui un  dispositivo viene certificato, la data approvata è datata alla data di disponibilità generale del prodotto. 


## <a name="product-primary-availability-period"></a>Periodo di disponibilità principale del prodotto

Questo periodo è il fulcro della disponibilità del prodotto:

![Sequenza temporale del ciclo di vita che mostra la disponibilità principale](../../media/non-dark4-edits.PNG)

Tutti i dispositivi registrati durante questo periodo ricevono il supporto completo di tre anni da Microsoft Managed Desktop (come mostrato dalla sequenza temporale blu). Questo periodo dura fino a una data di fine impostata su 24 mesi dalla data di disponibilità generale.

È possibile pensare a questo periodo come a una "registrazione aperta", quindi per ottimizzare il valore di Microsoft Managed Desktop, è consigliabile che i modelli di approvvigionamento e i prodotti selezionati cadano entro questo periodo. Come piccolo esempio, è consigliabile evitare di impostare un periodo di implementazione di due anni utilizzando un prodotto che si trova nell'ultimo mese [](#product-grace-period) di disponibilità primaria: la maggior parte di questi dispositivi non riceverà i tre anni completi di gestione di Microsoft Managed Desktop (vedere il periodo di tolleranza per ulteriori informazioni).  

## <a name="product-grace-period"></a>Periodo di tolleranza del prodotto

Il periodo di tolleranza del prodotto è un periodo di tre anni dopo la disponibilità principale. Questa fase consente di registrare i dispositivi di una famiglia di prodotti supportata, ma di mantenere le promesse di Microsoft Managed Desktop per quanto riguarda le prestazioni moderne di hardware e dispositivi. Questa fase è ideale per i clienti che hanno preso decisioni di approvvigionamento prima di conoscere Microsoft Managed Desktop. 

Se di recente hai acquistato dispositivi approvati prima della registrazione a Microsoft Managed Desktop, puoi comunque registrarli, ma non riceverai un intero periodo di gestione di tre anni. Al contrario, non saranno conformi alla data di ritiro, indipendentemente dal momento in cui sono stati registrati. Dietro le quinte, Microsoft Managed Desktop tratterà questi dispositivi come se fossero registrati l'ultimo giorno di disponibilità principale. In questa figura puoi vedere questo scenario notando che il dispositivo blu e il dispositivo verde terminano nello stesso giorno, nonostante la differenza di un anno nella registrazione:


![Sequenza temporale del ciclo di vita che mostra il periodo di tolleranza](../../media/non-dark2-edits.PNG)

Nell'esempio fabrikam laptop della tabella precedente viene illustrata questa situazione: 

|Prodotto  |Data approvazione  |Fine della disponibilità principale  |Fine dell'idoneità  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

I clienti possono registrare i laptop Fabrikam fino al 1/6/2022, ma verranno tutti considerati come se fossero stati registrati il 1/6/2019. Se si registra un portatile Fabrikam il 1/6/2021, si otterrà un solo anno di gestione. Questo criterio consente di estrarre cicli di vita parziali da prodotti che in precedenza erano supportati, invece di dover procurarsi nuovi dispositivi in modo prematurio. 

Infine, durante questa fase il dispositivo viene rimosso dall'elenco dei dispositivi [e](device-list.md) spostato nell'elenco [dei dispositivi archiviati.](archived-device-list.md)


## <a name="product-retirement"></a>Ritiro del prodotto

Il ritiro del prodotto è la fase finale del ciclo di vita. In questa fase, non è possibile registrare nuovi dispositivi di quel tipo di prodotto in Microsoft Managed Desktop e, per definizione, tutti i dispositivi esistenti sono ora al di fuori del periodo di tre anni consentito. Durante questo periodo, Microsoft Managed Desktop rimuoverà completamente il dispositivo dall'elenco pubblico. È anche in questa fase in cui, se non sono state già procurate sostituzioni, si inizierà a vedere i servizi diminuiti quando Microsoft Managed Desktop inizia a dilagare nei dispositivi che non sono conformi. 

## <a name="devices-that-are-out-of-compliance"></a>Dispositivi non conformi

Un dispositivo non è conforme al termine della finestra consentita per la gestione di Microsoft Managed Desktop. Questa situazione si verifica quando il dispositivo ha raggiunto tre anni di gestione o quando il tipo di prodotto viene rimosso dal catalogo dei dispositivi, a seconda di quale si verifica per primo. È consigliabile fare sempre in modo che i cicli di approvvigionamento siano mirati in modo che i nuovi dispositivi siano distribuiti prima che i dispositivi correnti non siano conformi.

Il team Microsoft Managed Desktop sa che i cicli di approvvigionamento sono lunghi e pianificati in base a budget di lunga durata. Per essere sempre a conoscenza dello stato della popolazione di [](https://aka.ms/mmdportal) dispositivi, forniamo un sito Web in cui sono elencati tutti i dispositivi in fase di gestione, la relativa età e uno stato che ne indica la conformità. Il sito Web consente di avere sempre le informazioni più aggiornate sull'età del dispositivo e di utilizzare il report in qualsiasi ciclo di pianificazione dell'approvvigionamento. 







