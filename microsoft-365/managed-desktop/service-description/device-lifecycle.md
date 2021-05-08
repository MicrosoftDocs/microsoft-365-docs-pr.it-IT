---
title: Microsoft Managed Desktop ciclo di vita del prodotto
description: In questo articolo sono elencate le specifiche del dispositivo usate in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a8b8abc58b82d08d004d204396cfd8e381c6303a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245313"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop ciclo di vita del prodotto

Microsoft Managed Desktop gli utenti assicurano di usare sempre dispositivi che offrono le migliori funzionalità di prestazioni, affidabilità, progettazione e sicurezza (ad esempio il supporto per funzionalità come Windows Hello). A tale scopo, Microsoft Managed Desktop un breve catalogo di dispositivi approvati continuamente aggiornati. Puoi visualizzare i dispositivi approvati filtrando le Microsoft Managed Desktop nel sito [Shop Windows 10 Pro dispositivi](https://www.microsoft.com/windowsforbusiness/view-all-devices) aziendali.
 
Questo articolo descrive in dettaglio il ciclo di vita dei dispositivi quando vengono aggiunti e rimossi dal catalogo approvato. 

> [!NOTE]
> In questo argomento verrà fatta una distinzione tra un "dispositivo" e un "prodotto". Per "dispositivo" si intende un singolo computer specifico. Ad esempio, "Numero di serie 1234", "Portatile di Bill", "Macchina virtuale condivisa XYZ" fanno riferimento a dispositivi specifici. Un "prodotto", tuttavia, fa riferimento a una raccolta o a una famiglia di dispositivi. Ad esempio, "Fabrikam Laptop", "Adatum ZX450 Laptop" e così via. Questo è importante perché i prodotti vengono aggiunti all'elenco approvato o al catalogo e i dispositivi vengono registrati in Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Ciclo di vita del prodotto

 In genere, i prodotti passano attraverso queste fasi del ciclo di vita:

- [Rilascio e valutazione del prodotto](#product-release-and-evaluation)
- [Periodo di disponibilità principale del prodotto](#product-primary-availability-period)
- [Periodo di tolleranza del prodotto](#product-grace-period)
- [Ritiro del prodotto](#product-retirement)


Questa figura mostra l'intera sequenza:

![Sequenza temporale del ciclo di vita: a partire dalla disponibilità generale del prodotto, la "disponibilità principale" dura due anni. Durante questo periodo di tempo la finestra di certificazione termina e a un certo punto il dispositivo viene onboarded. Al termine della disponibilità principale, il prodotto viene archiviato e inizia il "periodo di tolleranza" di tre anni. A partire dall'onboarded, il dispositivo ha un periodo di utilizzo di 3 anni fino a quando non viene rimosso dalla gestione. Al termine del periodo di tolleranza, il prodotto viene rimosso dal catalogo.](../../media/non-dark1-edits.PNG)

I prodotti rimangono nel catalogo fino a <em></em> 24 mesi, ma i dispositivi rimangono in gestione per tre anni in base alle date di registrazione individuali. In effetti, ogni prodotto ha tre date importanti, ma ogni dispositivo ne ha solo una. Per i prodotti, tutte e tre <em></em>queste date vengono calcolate in base alla data di approvazione e pertanto tali date vengono pubblicate dopo l'approvazione, in modo da poter sempre guardare avanti e pianificare in modo appropriato per l'intero ciclo di vita del prodotto.

Questa tabella mostra le date di esempio per un prodotto teorico:


|Prodotto  |Data approvazione  |Fine della disponibilità principale  |Fine dell'idoneità  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

Questa tabella mostra le date di esempio per i dispositivi *teorici:*


|ID dispositivo  |Data di registrazione  |Data di ritiro  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Desktop #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Rilascio e valutazione del prodotto

Il ciclo di vita del prodotto inizia quando un produttore rilascia pubblicamente il prodotto:

![Sequenza temporale del ciclo di vita che mostra il periodo di rilascio e valutazione](../../media/non-dark3-edits.PNG)

Durante questa fase, il team di Microsoft Managed Desktop esegue la valutazione e la certificazione di un prodotto. Il team valuta aspetti quali affidabilità e prestazioni con Windows, conformità a una linea di base hardware, valutazione del mercato e disponibilità dell'inventario e del canale, tra le altre cose. Questo processo in genere richiede circa sei settimane.
  
Microsoft Managed Desktop valuta solo i dispositivi per la certificazione entro i primi sei mesi di disponibilità. Questo criterio garantisce che i nostri sforzi siano sempre incentrati sull'ultima generazione di hardware.
 
Al termine di questa fase, Microsoft Managed Desktop il prodotto all'elenco [approvato,](device-list.md)rilasciando in modo efficace il prodotto per le registrazioni dei clienti. Indipendentemente dalla data di certificazione di  un dispositivo, la data di approvazione è datata alla data di disponibilità generale del prodotto. 


## <a name="product-primary-availability-period"></a>Periodo di disponibilità principale del prodotto

Questo periodo è il fulcro della disponibilità del prodotto:

![Sequenza temporale del ciclo di vita che mostra la disponibilità principale](../../media/non-dark4-edits.PNG)

Qualsiasi dispositivo registrato durante questo periodo riceve il supporto completo di tre anni da Microsoft Managed Desktop (come mostrato dalla sequenza temporale blu). Questo periodo dura fino a una data di fine impostata su 24 mesi dalla data di disponibilità generale.

È possibile pensare a questo periodo come effettivamente "registrazione aperta", quindi per ottimizzare il valore di Microsoft Managed Desktop, è consigliabile scegliere come destinazione i modelli di approvvigionamento e i prodotti selezionati per rientrare in questo periodo. Come piccolo esempio, è consigliabile evitare di impostare un periodo di implementazione di due anni utilizzando un prodotto che si trova nell'ultimo mese di [](#product-grace-period) disponibilità principale: la maggior parte di questi dispositivi non riceverà i tre anni completi di gestione di Microsoft Managed Desktop (vedere periodo di tolleranza per ulteriori informazioni).  

## <a name="product-grace-period"></a>Periodo di tolleranza del prodotto

Il periodo di tolleranza del prodotto è di tre anni dopo la disponibilità principale. Questa fase consente di registrare i dispositivi che sono di una famiglia di prodotti supportata, ma continuano a mantenere le promesse di Microsoft Managed Desktop per quanto riguarda le prestazioni moderne di hardware e dispositivi. Questa fase è ideale per i clienti che hanno preso decisioni di approvvigionamento prima di conoscere Microsoft Managed Desktop. 

Se hai acquistato di recente dispositivi approvati prima della registrazione con Microsoft Managed Desktop, puoi comunque registrarli, ma non riceverai tre anni di gestione completi. Al contrario, non saranno conformi alla data di ritiro, indipendentemente dal momento in cui sono stati registrati. Dietro le quinte, Microsoft Managed Desktop questi dispositivi verranno trattati come se fossero registrati l'ultimo giorno di disponibilità principale. In questa figura, è possibile vedere questo scenario notando che il dispositivo blu e verde terminano nello stesso giorno, nonostante la differenza di un anno nella registrazione:


![Sequenza temporale del ciclo di vita che mostra il periodo di tolleranza](../../media/non-dark2-edits.PNG)

Nell'esempio fabrikam laptop della tabella precedente viene illustrata questa situazione: 

|Prodotto  |Data approvazione  |Fine della disponibilità principale  |Fine dell'idoneità  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Come cliente, è possibile registrare i portatili Fabrikam fino al 1/6/2022, ma verranno tutti considerati come se fossero stati registrati il 1/6/2019. Se si registra un portatile Fabrikam il 1/6/2021, si otterrà solo un anno di gestione. Questo criterio consente di estrarre cicli di vita parziali da prodotti precedentemente supportati, anziché dover procurare nuovi dispositivi in modo prematuro. 

Infine, durante questa fase il dispositivo viene rimosso dall'elenco [dei dispositivi](device-list.md) e spostato nell'elenco dei [dispositivi archiviati.](archived-device-list.md)


## <a name="product-retirement"></a>Ritiro del prodotto

Il ritiro dei prodotti è la fase finale del ciclo di vita. In questa fase, non è possibile registrare nuovi dispositivi di quel tipo di prodotto in Microsoft Managed Desktop e, per definizione, tutti i dispositivi esistenti sono ora al di fuori del periodo di tre anni consentito. Durante questo periodo, Microsoft Managed Desktop il dispositivo verrà rimosso completamente dall'elenco pubblico. È anche in questa fase in cui, se non sono già state procurate sostituzioni, inizierai a vedere i servizi diminuiti quando Microsoft Managed Desktop inizia a calare nei dispositivi che non sono conformi. 

## <a name="devices-that-are-out-of-compliance"></a>Dispositivi non conformi

Un dispositivo non è conforme quando è trascorsa la finestra consentita Microsoft Managed Desktop gestione dei dispositivi. Questa situazione si verifica quando il dispositivo ha raggiunto tre anni di gestione o quando quel tipo di prodotto viene rimosso dal catalogo dei dispositivi, a seconda di quale sia il primo problema. Devi sempre impostare come destinazione i cicli di approvvigionamento in modo che i nuovi dispositivi siano distribuiti prima che i dispositivi correnti non siano conformi.

Il Microsoft Managed Desktop team sa che i cicli di approvvigionamento sono lunghi e pianificati in base ai budget a esecuzione lunga. Per essere sempre a conoscenza dello stato della popolazione dei [](https://aka.ms/mmdportal) dispositivi, forniamo un sito Web in cui sono elencati tutti i dispositivi in gestione, l'età e uno stato che ne indica la conformità. Il sito Web consente di avere sempre le informazioni più aggiornate sull'età del dispositivo e di utilizzare il report in qualsiasi ciclo di pianificazione degli appalti. 







