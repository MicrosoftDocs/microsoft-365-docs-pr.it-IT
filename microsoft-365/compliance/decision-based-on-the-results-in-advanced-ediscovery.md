---
title: Decisione basata sui risultati in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Informazioni su come la scheda decidere in Advanced eDiscovery fornisce dati che consentono di determinare le dimensioni corrette del set di revisione dei file di caso.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0423a21520375f1d9de8e2eaeca142b979ff1883
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759868"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a>Decisione basata sui risultati in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 In Advanced eDiscovery, la scheda decide fornisce informazioni aggiuntive per la visualizzazione e l'utilizzo delle statistiche di supporto decisionale per determinare le dimensioni del set di riesame dei file di caso. 
  
## <a name="using-the-decide-tab"></a>Utilizzo della scheda decide

![Decisione di pertinenza](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
In questa scheda sono inclusi i componenti seguenti:
  
- **Problema**: da qui, è possibile selezionare il problema di interesse dall'elenco. 
    
- **Rapporto Revisione-richiamo**: confronto tra la revisione avanzata di eDiscovery in base ai punteggi di pertinenza. Il punto di taglio nel grafico rappresenta la percentuale di file da esaminare, mappata a un punteggio di pertinenza. Questo valore viene utilizzato nella fase di test di pertinenza e come soglia di esportazione per l'eliminazione. Il punto di taglio predefinito per il numero di file da esaminare è il punto in cui il bilanciamento tra richiamo e precisione è ottimale. Il punto di taglio effettivo dovrebbe essere determinato dall'utente a seconda degli obiettivi e del compromesso dei costi (% revisione) e del rischio (% Recall). Utilizzando il dispositivo di scorrimento, è possibile regolare il punto di taglio e vedere l'effetto sul grafico e sui parametri, quando si modifica la percentuale di file rilevanti da recuperare e prima di convalidare una decisione.
    
- **Parametri**: Review, Recall, Next rilevanti and Total cost Parameters sono statistiche calcolate cumulative relative al set di revisione in relazione alla raccolta per l'intero caso. Le definizioni per questi parametri sono le seguenti:
    
    **Recensione**: percentuale di file da esaminare in base a questo cutoff. 
    
    **Richiamo**: percentuale dei file rilevanti nel set di revisione. 
    
    **Next pertinente**: costo per la revisione e l'identificazione di un ulteriore file pertinente che non è attualmente incluso nel set di revisione. 
    
    **Costo totale**: costo per la revisione di questa percentuale dei file del caso. Le impostazioni dei parametri di costo possono essere impostate dal responsabile del caso.
    
- **Distribuzione per Punteggio di pertinenza**: i file nel display grigio scuro a sinistra sono al di sotto del Punteggio di taglio. Un suggerimento per gli strumenti Visualizza il Punteggio di pertinenza e la percentuale relativa di file nel set di file di revisione in relazione ai file totali.
    
Nel riquadro dettagli espansi vengono visualizzati ulteriori dettagli. I file nelle figure delle raccolte non includono file vuoti o nebulosi. Le figure dei file di famiglia rappresentano i file che non sono caricati in rilevanza, ma vengono comunque conteggiati come parte della famiglia.
  
