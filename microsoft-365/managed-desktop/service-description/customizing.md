---
title: Eccezioni al piano di servizio
description: Come richiedere eccezioni al piano di servizio standard
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 97fe3fe1734908c46dcfff4acd76ce9ae5b8b1a5
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841268"
---
# <a name="exceptions-to-the-service-plan"></a>Eccezioni al piano di servizio

Microsoft Managed Desktop offre un elenco di dispositivi curato, impostazioni dei dispositivi [standard,](device-policies.md)requisiti delle applicazioni e alcune impostazioni [configurabili,](../working-with-managed-desktop/config-setting-overview.md)tutte progettate per offrire un'esperienza sicura, produttiva e piacevole per gli utenti. È meglio rimanere sempre con il servizio come indicato. Tuttavia, ci rendiamo conto che alcuni dettagli del servizio potrebbero non adattarsi esattamente alle esigenze dell'organizzazione. Se si sente la necessità di modificare il servizio in qualche modo, è importante seguire i processi seguenti per richiedere tali modifiche.
 
## <a name="types-of-exceptions"></a>Tipi di eccezioni

Un'eccezione è qualsiasi aggiunta o modifica alla configurazione di base di Microsoft Managed Desktop; Alcuni esempi vanno dalla configurazione delle porte USB alla distribuzione di un nuovo driver di dispositivo. Le varie eccezioni vengono raggruppate nel modo seguente:

|Tipo  |Descrizione  |
|---------|---------|
|Software di produttività     |  Software in primo piano necessario per gli utenti, limitato dai requisiti [dell'applicazione](mmd-app-requirements.md)       |
|Agenti di sicurezza & VPN     |  Software utilizzato per proteggere, monitorare o modificare il comportamento del dispositivo o della rete       |
|Monitoraggio dell'esperienza digitale     |  Software usato per tenere traccia dei dati nel dispositivo di un utente da segnalare all'IT       |
|Driver hardware o software     |   Driver di dispositivo, limitati dai requisiti [dell'applicazione](mmd-app-requirements.md)      |
|Criteri     | Impostazioni di Windows 10 o Microsoft 365 Apps for enterprise in un dispositivo gestito        |
|Dispositivi     | Dispositivi non presenti nell'elenco dei dispositivi Microsoft Managed [Desktop](device-list.md)        |
|Altro     |  Tutto ciò che non è coperto dalle altre aree       |
 
## <a name="request-an-exception"></a>Richiedere un'eccezione

Inviare richieste tramite il portale di amministrazione di Microsoft Managed Desktop creando una richiesta di modifica. Assicurati di includere questi dettagli:

-   Tipo di esenzione: qual è la categoria di eccezione? (vedere la tabella precedente)
-   Requisito: qual è il requisito aziendale specifico per l'eccezione?
-   Proposta: quale soluzione richiede l'azienda?
-   Sequenza temporale: per quanto tempo si desidera che l'eccezione dura? 

## <a name="how-we-assess-an-exception-request"></a>Come valutiamo una richiesta di eccezione

Quando rivediamo le richieste di eccezione, valutiamo questi fattori nell'ordine seguente:
 
1.  Alcune applicazioni e criteri distribuiti da Microsoft Managed Desktop in tutti i dispositivi non sono negoziabili, pertanto la richiesta non deve influire su tali applicazioni. Per [altre informazioni, vedi](device-policies.md) Configurazione del dispositivo.
2.  È probabile che il software di produttività limitato richiesto da un utente per eseguire il proprio lavoro sia approvato. 
3.  Se possiamo soddisfare il tuo requisito usando la tecnologia Microsoft, probabilmente approveremo la richiesta di un periodo di migrazione di eccezione da tre a 12 mesi (a seconda dell'ambito del progetto).
4.  Se non possiamo soddisfare il tuo requisito usando la tecnologia Microsoft, probabilmente approveremo la tua richiesta a meno che non violi una delle condizioni seguenti.  

Questi principi garantiscono che Microsoft Managed Desktop sia sempre in grado di soddisfare le proprie esigenze tenendo traccia delle deviazioni dal modello standard. 

## <a name="key-conditions"></a>Condizioni chiave

Microsoft esamina le eccezioni per assicurarsi che non violino nessuna di queste condizioni:

-   Un'eccezione non deve influire negativamente sulla sicurezza del sistema. 
-   La gestione dell'eccezione non deve incorrere in costi significativi per le operazioni di Microsoft Managed Desktop o per il supporto.
-   Un'eccezione non deve influire sulla stabilità del sistema, ad esempio causando arresti anomali o blocchi della modalità kernel.
-   La modifica non deve impedirci di utilizzare il servizio o di essere in conflitto con la tecnologia Microsoft Managed Desktop di base.

Queste condizioni potrebbero cambiare in futuro. In caso di modifiche di questo tipo, forniremo un preavviso di 30 giorni prima dell'applicazione di tali condizioni.  Se Microsoft Managed Desktop offre un modo alternativo per soddisfare un'eccezione approvata, Microsoft Managed Desktop informerà il cliente se Microsoft Managed Desktop altera il modo in cui supporta l'eccezione. 

## <a name="revoking-approval-for-an-exception"></a>Revoca dell'approvazione per un'eccezione

Dopo l'approvazione e la distribuzione di un'eccezione richiesta, è possibile individuare problemi che violano le condizioni chiave che non erano evidenti quando è stata approvata la modifica. In questo caso, potrebbe essere necessario revocare l'approvazione per l'eccezione.
 
In questo caso, ti invieremo una notifica tramite il portale di amministrazione di Microsoft Managed Desktop. Dalla prima notifica, hai 90 giorni di tempo per rimuovere l'eccezione prima che i dispositivi con l'eccezione non siano più vincolati dai contratti di servizio di Microsoft Managed Desktop. Invieremo diverse notifiche in base a una sequenza temporale rigida, tuttavia un grave incidente o una minaccia potrebbe richiedere la modifica della sequenza temporale o le decisioni relative a un'eccezione. Microsoft non *rimuoverà* un'eccezione senza il consenso dell'utente, ma qualsiasi dispositivo con un'eccezione revocata non sarà più vincolato dal contratto di servizio. Ecco la sequenza temporale delle notifiche che ti invieremo:

- **Primo avviso:** Forniamo il primo avviso della nostra decisione di revocare l'approvazione, incluse le informazioni sul motivo per cui la revoca, le azioni che ti consigliamo di intraprendere, la scadenza per tali azioni e i passaggi da seguire se vuoi appellarti alla decisione. Questo avviso si verifica con 90 giorni di anticipo prima che l'eccezione venga rimossa da tutti i dispositivi. 
- **Secondo avviso (30 giorni dopo):** Forniamo un secondo avviso, incluse le stesse informazioni fornite nel primo avviso. 
- **Terzo avviso (60 giorni dopo il primo avviso):** Forniamo un terzo avviso, incluse le stesse informazioni fornite nel primo avviso. 
- **Avviso finale (una settimana prima della scadenza di 90 giorni):** Forniamo un quarto avviso, incluse le stesse informazioni fornite nel primo avviso.
- **90 giorni dopo il primo avviso:** I contratti di servizio di Microsoft Managed Desktop non si applicano più ai dispositivi con l'eccezione revocata. In qualsiasi momento, è possibile contestarne la decisione e fornire ulteriori informazioni da prendere in considerazione, tra cui l'aggiornamento, le modifiche alla configurazione o la modifica del software. 


