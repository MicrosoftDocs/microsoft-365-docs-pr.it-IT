---
title: Eccezioni al piano di servizio
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9dca53ac9e99fd9bc68ee42f78de6a2bc009e42c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636185"
---
# <a name="exceptions-to-the-service-plan"></a>Eccezioni al piano di servizio

Microsoft Managed Desktop fornisce un elenco di dispositivi a cura, [impostazioni del dispositivo standard](device-policies.md), requisiti per le applicazioni e determinate [impostazioni configurabili](../working-with-managed-desktop/config-setting-overview.md), tutte progettate per offrire un'esperienza sicura, produttiva e piacevole per gli utenti finali. È consigliabile rimanere sempre con il servizio fornito. Tuttavia, si riconosce che alcuni dettagli del servizio potrebbero non corrispondere esattamente alle esigenze dell'organizzazione. Se si ritiene che sia necessario modificare il servizio in qualche modo, è importante seguire i processi seguenti per richiedere tali modifiche.
 
## <a name="types-of-exceptions"></a>Tipi di eccezioni

Un'eccezione è una o più modifiche apportate alla configurazione di base di Microsoft Managed Desktop; gli esempi variano dalla configurazione delle porte USB alla distribuzione di un nuovo driver di dispositivo. Raggruppare diverse eccezioni nel modo seguente:

|Tipo  |Descrizione  |
|---------|---------|
|Software per la produttività     |  Software di primo piano necessari per gli utenti finali, limitato dai [requisiti dell'applicazione](mmd-app-requirements.md)       |
|Agenti di sicurezza & VPN     |  Software utilizzato per proteggere, monitorare o modificare il comportamento del dispositivo o della rete       |
|Monitoraggio dell'esperienza digitale     |  Software utilizzato per registrare i dati del dispositivo di un utente per segnalarli       |
|Driver hardware o software     |   Driver di dispositivo, limitati dai [requisiti dell'applicazione](mmd-app-requirements.md)      |
|Generali     | App di Windows 10 o Microsoft 365 per le impostazioni dell'organizzazione su un dispositivo gestito        |
|Dispositivi     | Dispositivi che non sono presenti nell' [elenco](device-list.md) dispositivi di Microsoft Managed Desktop        |
|Altro     |  Tutto ciò che non rientra nelle altre aree       |
 
## <a name="request-an-exception"></a>Richiedere un'eccezione

Inviare richieste tramite il portale di amministrazione di Microsoft Managed Desktop mediante la creazione di una richiesta di modifica. Assicurarsi di includere i dettagli seguenti:

-   Tipo di esenzione: quale categoria di eccezione è? (vedere la tabella precedente)
-   Requisito: qual è il requisito aziendale specifico per l'eccezione?
-   Proposta: qual è la soluzione che richiede la propria azienda?
-   Sequenza temporale: per quanto tempo si desidera che l'eccezione venga ultimata? 

## <a name="how-we-assess-an-exception-request"></a>Come viene valutata una richiesta di eccezione

Quando si esaminano le richieste di eccezione, vengono valutati questi fattori nell'ordine indicato:
 
1.  Alcune applicazioni e criteri che Microsoft Managed Desktop distribuisce a tutti i dispositivi non sono negoziabili, quindi la richiesta non deve influire su queste. Per ulteriori informazioni, vedere [configurazione dei dispositivi](device-policies.md) .
2.  È probabile che il software di produttività limitato richiesto da un utente finale sia approvato. 
3.  Se si è in grado di rispondere ai propri requisiti utilizzando la tecnologia Microsoft, è probabile che la richiesta venga approvata per un periodo di migrazione delle eccezioni compreso tra tre e dodici mesi (a seconda dell'ambito del progetto).
4.  Se non si riesce a rispettare i requisiti utilizzando la tecnologia Microsoft, è probabile che la richiesta venga approvata a meno che non venga violata una delle condizioni seguenti.  

Questi principi assicurano che Microsoft Managed Desktop sia sempre in grado di soddisfare le proprie esigenze tenendo traccia delle deviazioni dal modello standard. 

## <a name="key-conditions"></a>Condizioni chiave

Vengono esaminate le eccezioni per garantire che non violino nessuna di queste condizioni:

-   Un'eccezione non deve influire negativamente sulla sicurezza del sistema. 
-   La gestione dell'eccezione non deve comportare un costo significativo per le operazioni o il supporto di Microsoft Managed Desktop.
-   Un'eccezione non deve influire sulla stabilità del sistema, ad esempio causando arresti anomali o blocchi della modalità kernel.
-   La modifica non deve limitare l'utilizzo del servizio o il conflitto con la tecnologia di base di Microsoft Managed Desktop.

Queste condizioni potrebbero cambiare in futuro. Se si apportano tali modifiche, verrà fornita una notifica di 30 giorni prima che le condizioni vengano applicate.  Se Microsoft Managed Desktop fornisce un modo alternativo per rispondere a un'eccezione approvata, Microsoft Managed Desktop notificherà al cliente che Microsoft Managed Desktop può modificare il modo in cui viene supportato l'eccezione. 

## <a name="revoking-approval-for-an-exception"></a>Revoca dell'approvazione per un'eccezione

Dopo l'approvazione e la distribuzione di un'eccezione richiesta, è possibile che si verifichino problemi che violano le condizioni chiave non evidenti quando è stata approvata la modifica in primo luogo. In questo caso, potrebbe essere necessario revocare l'approvazione per l'eccezione.
 
In tal caso, verrà notificato tramite il portale di amministrazione di Microsoft Managed Desktop. Dal primo momento in cui viene effettuata la notifica, sono disponibili 90 giorni per rimuovere l'eccezione prima che i dispositivi con l'eccezione non siano più associati ai contratti di servizio Microsoft Managed Desktop. Verranno inviate diverse notifiche in base a una sequenza temporale rigorosa, tuttavia, un grave incidente o una minaccia potrebbe richiedere di modificare la sequenza temporale o le decisioni relative a un'eccezione. Non verrà *rimossa* un'eccezione senza il consenso, ma qualsiasi dispositivo con un'eccezione revocata non sarà più associato al contratto di servizio. Ecco la cronologia delle notifiche che verranno inviate:

- **Primo avviso:** Viene fornita la prima notifica della decisione di revocare l'approvazione, incluse le informazioni sul motivo per cui è stata revocata, le azioni che si consiglia di eseguire, la data di scadenza per tali azioni e i passaggi da seguire se si vuole fare appello alla decisione. Questo è di 90 giorni prima che l'eccezione debba essere rimossa da tutti i dispositivi. 
- **Secondo avviso (30 giorni dopo):** Viene fornita una seconda notifica, incluse le stesse informazioni fornite nel primo avviso. 
- **Terza notifica (60 giorni dopo il primo avviso):** Viene fornita una terza notifica, incluse le stesse informazioni fornite nel primo avviso. 
- **Avviso finale (1 settimana prima della scadenza di 90 giorni):** Viene fornito un quarto avviso, incluse le stesse informazioni fornite nel primo avviso.
- **90 giorni dopo il primo avviso:** I contratti di servizio Microsoft Managed Desktop Level non si applicano più ai dispositivi con l'eccezione revocata. In qualsiasi momento, è possibile contestare la decisione e fornire ulteriori informazioni per considerazione, tra cui l'aggiornamento, le modifiche alla configurazione o la modifica del software. 


