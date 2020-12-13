---
title: Impostare le opzioni di analisi in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: Esaminare i passaggi per configurare le opzioni per il processo di analisi in Advanced eDiscovery, inclusi i quasi duplicati, i thread di posta elettronica e i temi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ff51402cd79f2966730677a982fa5173b7e9b98
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663501"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a>Impostare le opzioni di ANALYZE in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In Advanced eDiscovery, impostare le opzioni Analyze prima di eseguire ANALYZE.
  
## <a name="set-analyze-options"></a>Impostazione delle opzioni di analisi

Aprire **prepara \> analisi** di \> **installazione**. Viene visualizzata la finestra seguente.
  
![Impostare opzioni di analisi](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **Quasi duplicati e thread di posta elettronica** Selezionare questa casella di controllo se si desidera eseguire l'analisi. Questa opzione è selezionata per impostazione predefinita. 
  
 **Somiglianza del documento** Immettere il valore soglia quasi duplicati oppure accettare l'impostazione predefinita 65%. 
  
 **Temi** Selezionare questa casella per elaborare tutti i file e assegnargli i temi. Per impostazione predefinita, questa casella di controllo non è selezionata. Se si desidera eseguire l'elaborazione dei temi, immettere le opzioni seguenti.
  
- **Numero massimo di temi** Immettere o selezionare un valore per il numero di temi da creare. Il valore predefinito è 200. 
    
    > [!NOTE]
    > L'aumento del numero di temi influenza le prestazioni e la possibilità di generalizzare un tema. Maggiore è il numero di temi, maggiore è il livello di granularità. Ad esempio, se un insieme di temi 50 include un tema come "basket, Spurs, Clippers, Lakers"; 300 temi possono includere temi distinti: "Spurs", "Clippers", "Lakers". Se non si ha consapevolezza del tema "basket" e si utilizza questa funzionalità per ECA, è possibile utilizzare il tema "basket". Tuttavia, se l'elaborazione ha avuto troppi temi, potrebbe non essere possibile visualizzare la parola "basket" e potrebbe non essere in grado di riconoscere che gli Spurs e i Clippers sono buoni temi di basket da rivedere, anziché elementi che vengono utilizzati per i capelli. 
  
- **Temi consigliati** È possibile suggerire parole tematiche per controllare l'elaborazione dei temi. Advanced eDiscovery si concentrerà su queste parole suggerite e cercherà di creare uno o più temi rilevanti, in base alle impostazioni "numero massimo di temi". 
    
    Ad esempio, se la parola suggerita è "computer" e si specifica "2" come "numero massimo di temi", Advanced eDiscovery proverà a generare due temi correlati alla parola "computer". I due temi potrebbero essere, ad esempio, "software per computer" e "hardware del computer". 
    
    ![Aggiungi tema suggerito](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. Per visualizzare, aggiungere o modificare i temi suggeriti, fare clic su **modifica**.
    
2. Nel riquadro **temi consigliati** fare clic sull'icona **Aggiungi** ![ icona ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere un tema. Nel riquadro **Aggiungi tema suggerito** aggiungere le parole separate da virgole. 
    
3. In **numero di temi** selezionare un valore per determinare il numero di temi avanzati che eDiscovery tenterà di generare per queste parole (l'impostazione predefinita è 1 tema).
    
4. Fare clic su **Salva** e quindi chiudere la finestra di dialogo. 
    
    > [!NOTE]
    > Il numero totale di temi include i temi suggeriti. I temi totali suggeriti non possono superare i temi totali. Se sono presenti molti temi suggeriti rispetto ai temi totali, solo alcuni temi "novelli" verranno rilevati dal sistema perché la maggior parte dei temi sarà dedicata ai temi suggeriti. 
  
- **Modalità** Nell'elenco a discesa selezionare un'opzione **temi** : 
    
  - **Create and Apply Model**: calcola i temi in base ai modelli da un segmento dei file e quindi distribuisce i file tra di essi.
    
  - **Create Model**: consente di calcolare un modello di temi da un segmento dei file. Il processo di applicazione della divisione dei file viene effettuato separatamente in un altro momento.
    
  - **Applicazione modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non è stato ancora applicato. In questo modo i file verranno divisi in base ai temi.
    
È inoltre possibile [impostare Ignora testo](set-ignore-text-in-advanced-ediscovery.md) e [set Analyze Advanced Settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze. 
  
Dopo aver impostato queste opzioni, fare clic su **analizza** per l'esecuzione. [Visualizzare i risultati dell'analisi](view-analyze-results-in-advanced-ediscovery.md) . 
  
## <a name="related-topics"></a>Argomenti correlati

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Informazioni sulla somiglianza del documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Imposta Ignora testo ](set-ignore-text-in-advanced-ediscovery.md)
  
[Impostazioni avanzate per l'analisi](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Visualizzare i risultati dell'analisi](view-analyze-results-in-advanced-ediscovery.md)

