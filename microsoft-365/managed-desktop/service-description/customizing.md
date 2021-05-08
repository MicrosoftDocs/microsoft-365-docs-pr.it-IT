---
title: Eccezioni al piano di servizio
description: Come richiedere eccezioni al piano di servizio standard
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245517"
---
# <a name="exceptions-to-the-service-plan"></a>Eccezioni al piano di servizio

Microsoft Managed Desktop fornisce un elenco di dispositivi curato, impostazioni dei dispositivi [standard,](device-policies.md)requisiti delle applicazioni e alcune impostazioni [configurabili,](../working-with-managed-desktop/config-setting-overview.md)tutte progettate per offrire agli utenti un'esperienza sicura, produttiva e piacevole. È meglio rimanere sempre con il servizio come fornito. Tuttavia, microsoft riconosce che alcuni dettagli del servizio potrebbero non corrispondere esattamente alle esigenze dell'organizzazione. Se si sente la necessità di modificare il servizio in qualche modo, è importante seguire i processi seguenti per richiedere tali modifiche.
 
## <a name="types-of-exceptions"></a>Tipi di eccezioni

Un'eccezione è qualsiasi aggiunta o modifica alla Microsoft Managed Desktop di base. gli esempi vanno dalla configurazione delle porte USB alla distribuzione di un nuovo driver di dispositivo. Vengono raggruppate diverse eccezioni nel modo seguente:

|Tipo  |Descrizione  |
|---------|---------|
|Software di produttività     |  Software in primo piano necessario agli utenti, limitato dai requisiti [dell'applicazione](mmd-app-requirements.md)       |
|Agenti di sicurezza & VPN     |  Software utilizzato per proteggere, monitorare o modificare il comportamento del dispositivo o della rete       |
|Monitoraggio dell'esperienza digitale     |  Software usato per tenere traccia dei dati nel dispositivo di un utente per segnalare all'IT       |
|Driver hardware o software     |   Driver di dispositivo, limitati dai requisiti [dell'applicazione](mmd-app-requirements.md)      |
|Criteri     | Windows 10 o Microsoft 365 Apps for enterprise in un dispositivo gestito        |
|Dispositivi     | Dispositivi non presenti nell'Microsoft Managed Desktop [dei dispositivi](device-list.md)        |
|Altro     |  Tutto ciò che non è coperto dalle altre aree       |
 
## <a name="request-an-exception"></a>Richiedere un'eccezione

Inviare richieste tramite il Microsoft Managed Desktop di amministrazione creando una richiesta di modifica. Assicurati di includere questi dettagli:

- Tipo di esenzione: qual è la categoria di eccezione? (vedere la tabella precedente)
- Requisito: qual è il requisito aziendale specifico per l'eccezione?
- Proposta: quale soluzione richiede l'azienda?
- Sequenza temporale: per quanto tempo vuoi che l'eccezione durerà? 

## <a name="how-we-assess-an-exception-request"></a>Modalità di valutazione di una richiesta di eccezione

Quando rivediamo le richieste di eccezione, valutiamo questi fattori nell'ordine seguente:
 
1. Alcune applicazioni e criteri Microsoft Managed Desktop distribuiti in tutti i dispositivi non sono negoziabili, quindi la richiesta non deve influire su tali applicazioni. Per [altre informazioni, vedi](device-policies.md) Configurazione del dispositivo.
2. Il software di produttività limitato richiesto da un utente per eseguire il proprio lavoro sarà probabilmente approvato. 
3. Se possiamo soddisfare il tuo requisito usando la tecnologia Microsoft, probabilmente approveremo la tua richiesta per un periodo di migrazione di eccezione da tre a 12 mesi (a seconda dell'ambito del progetto).
4. Se non è possibile soddisfare i requisiti dell'utente utilizzando la tecnologia Microsoft, è probabile che la richiesta venga approvata a meno che non violi una delle condizioni seguenti.  

Questi principi assicurano che Microsoft Managed Desktop sempre in grado di soddisfare le tue esigenze tenendo traccia delle deviazioni dal nostro modello standard. 

## <a name="key-conditions"></a>Condizioni chiave

Microsoft esamina le eccezioni per assicurarsi che non violino nessuna di queste condizioni:

- Un'eccezione non deve influire negativamente sulla sicurezza del sistema. 
- La gestione dell'eccezione non deve comportare costi significativi per le Microsoft Managed Desktop o il supporto tecnico.
- Un'eccezione non deve influire sulla stabilità del sistema, ad esempio causando arresti anomali o blocchi della modalità kernel.
- La modifica non deve impedirci di utilizzare il servizio o essere in conflitto con la tecnologia Microsoft Managed Desktop core.

Queste condizioni potrebbero cambiare in futuro. Se apportare tali modifiche, forniremo un avviso di 30 giorni prima dell'applicazione di tali condizioni.  Se Microsoft Managed Desktop un modo alternativo per soddisfare un'eccezione approvata, Microsoft Managed Desktop il cliente dovrà Microsoft Managed Desktop modificare il modo in cui supporta l'eccezione. 

## <a name="revoking-approval-for-an-exception"></a>Revoca dell'approvazione per un'eccezione

Dopo l'approvazione e la distribuzione di un'eccezione richiesta, è possibile che si potrebbero individuare problemi che violano le condizioni chiave che non erano evidenti quando è stata approvata la modifica. In questo caso, potrebbe essere necessario revocare l'approvazione per l'eccezione.
 
In questo caso, ti invieremo una notifica usando il portale di Microsoft Managed Desktop di amministrazione. Dalla prima notifica, hai 90 giorni per rimuovere l'eccezione prima che i dispositivi con l'eccezione non siano più associati Microsoft Managed Desktop contratti di servizio. Ti invieremo diverse notifiche in base a una sequenza temporale rigida. Tuttavia, un grave incidente o una minaccia potrebbe richiedere di modificare la sequenza temporale o le nostre decisioni su un'eccezione. Non rimuoveremo *un'eccezione* senza il tuo consenso, ma qualsiasi dispositivo con un'eccezione revocata non sarà più vincolato dal nostro contratto di servizio. Ecco la sequenza temporale delle notifiche che ti invieremo:

- **Primo avviso:** Forniamo il primo avviso della nostra decisione di revocare l'approvazione, incluse le informazioni sul motivo per cui la stiamo revocando, le azioni che consigliamo di intraprendere, la scadenza per tali azioni e i passaggi da seguire se vuoi appellarti alla decisione. Questo avviso si verifica 90 giorni prima che l'eccezione venga rimossa da tutti i dispositivi. 
- **Secondo avviso (30 giorni dopo):** Forniamo un secondo avviso, incluse le stesse informazioni fornite nel primo avviso. 
- **Terzo avviso (60 giorni dopo il primo avviso):** Forniamo un terzo avviso, incluse le stesse informazioni fornite nel primo avviso. 
- **Avviso finale (una settimana prima della scadenza di 90 giorni):** Forniamo un quarto avviso, incluse le stesse informazioni fornite nel primo avviso.
- **90 giorni dopo il primo avviso: Microsoft Managed Desktop** contratti di servizio non si applicano più ai dispositivi con l'eccezione revocata. In qualsiasi momento, è possibile contestarne la decisione e fornire ulteriori informazioni da prendere in considerazione, tra cui l'aggiornamento, le modifiche alla configurazione o la modifica del software. 


