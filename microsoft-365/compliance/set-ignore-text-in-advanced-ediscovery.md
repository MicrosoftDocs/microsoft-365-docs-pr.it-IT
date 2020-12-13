---
title: Impostare l'opzione Ignora testo per ANALYZE in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: Informazioni su come definire la regola per ignorare testo specifico quando si utilizzano i moduli Analyze and process in Advanced eDiscovery.
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663471"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a>Opzione set Ignora testo per ANALYZE in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
La funzionalità Ignora testo può essere applicata a tutti o a uno dei seguenti moduli avanzati di eDiscovery: Analyze (near-Duplicates, email Threads, Themes) e pertinenza. Il testo ignorato non verrà visualizzato nei file visualizzati in pertinenza e l'analisi/calcoli ignorerà il testo ignorato.
  
Se la caratteristica Ignora testo era stata definita in precedenza per i moduli già in esecuzione, l'impostazione Ignora testo sarà ora protetta dalla modifica. Tuttavia, la caratteristica Ignora testo per il modulo pertinenza può comunque essere modificata in qualsiasi momento.
  
## <a name="how-ignore-text-filters-are-applied"></a>Modalità di applicazione dei filtri di testo Ignora

Più filtri di testo Ignora vengono applicati nell'ordine in cui sono stati immessi. Per modificare l'ordine in cui vengono applicati, è necessario eliminarlo e riimmetterlo nell'ordine desiderato.
  
Ad esempio, se il contenuto del testo è: "DAVE BOB ALICE CAROL EVE", di seguito sono riportati alcuni esempi di voci di testo Ignora e i risultati ottenuti da queste voci:

|**Ignora voci di testo** <br/> |**Risultati** <br/> |
|:-----|:-----|
|"ALICE", "BOB CAROL"  <br/> |"DAVE EVE"  <br/> |
|"ALICE", "BOB ALICE CAROL"  <br/> |"DAVE BOB CAROL EVE"  <br/> |
   
La seconda voce Ignora testo non viene implementata perché la stringa non viene trovata come tale dopo l'applicazione del primo testo Ignora.
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>Utilizzo di espressioni regolari quando si definisce Ignora testo

Le espressioni regolari sono supportate per l'utilizzo quando si definisce Ignora testo. Di seguito sono riportati alcuni esempi di sintassi e utilizzo di espressioni regolari:
  
- Per rimuovere (ignorare) il testo da inizio fino alla fine di una riga:
    
     `Begin(.*)$`
    
    dove "Begin" è l'occorrenza iniziale di questa stringa nella riga.
    
    Ad esempio, per il testo seguente:
    
    **"Questa è la prima frase e la prima riga**
    
    **Questa è la seconda frase e la seconda riga "**
    
    prima espressione regolare (. \* ) $ provocherà:
    
    **"Questo è**
    
    **Questa è la seconda frase e la seconda riga "**
    
- Per rimuovere le dichiarazioni di non responsabilità e le istruzioni legali inserite automaticamente alla fine dei thread di posta elettronica:
    
     `Begin(.|\s)*End`
    
    dove "Begin" e "end" sono stringhe univoche all'inizio e alla fine di un paragrafo di testo avvolto. 
    
    Ad esempio, l'espressione regolare seguente eliminerà le dichiarazioni di non responsabilità e le istruzioni legali che si trovavano nel thread di posta elettronica tra le stringhe Begin e end:
    
    **Questo messaggio contiene informazioni riservate (. | \s) \* se è richiesta la verifica, richiedere una versione cartacea**
    
- Per rimuovere una dichiarazione di non responsabilità (compresi i caratteri speciali): 
    
    Ad esempio, per il testo seguente (con la dichiarazione di non responsabilità rappresentata qui da x): 
    
    **/\*\ Questo messaggio contiene informazioni riservate. xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx se è richiesta la verifica, richiedere una versione cartacea. /\*\**
    
    l'espressione regolare per rimuovere la dichiarazione di non responsabilità di cui sopra dovrebbe essere la seguente: 
    
    **\/\\*\\ Questo messaggio contiene informazioni riservate \. (. | \s) \* se è richiesta la verifica, richiedere una versione \. cartacea \/\\*\\**
    
- Regole di espressione regolare:
    
  - Tutti i caratteri che non fanno parte dell'alfabeto eccetto per gli spazi, "_" e "-" devono essere preceduti da " \" .
    
  - Il campo eExpression regolare può essere di lunghezza illimitata.
    
> [!TIP]
> Per una spiegazione e una sintassi dettagliata delle espressioni regolari, vedere: [Regular Expression Language-Quick Reference](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx). 
  
## <a name="define-ignore-text-rule"></a>Definire la regola ignora testo

1. Nella sezione **Ignora testo** della scheda **Gestisci \> \> Opzioni di analisi Analyze** fare clic sull' **+** icona per aggiungere una regola. 
    
2. Nella finestra di dialogo **Aggiungi testo Ignora** , nel campo **nome** , digitare un nome per la regola di testo Ignora. 
    
    ![Aggiungi testo ignorato](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. Nella casella di **testo** Digitare il testo da ignorare. Il campo di testo consente un numero illimitato di caratteri. 
    
    > [!TIP]
    > Come mostrato nella finestra sopra, fare clic su **lampadina** per visualizzare le linee guida per la sintassi comune per la regola di testo Ignora. 
  
4. Selezionare la casella di controllo **distinzione tra maiuscole e minuscole** , se necessario. 
    
5. Nell'elenco **applica a** selezionare i moduli avanzati di eDiscovery in cui applicare la definizione. 
    
6. Se si desidera eseguire l'esecuzione di un test nel testo di esempio, digitare il testo di esempio nella casella di testo **input** e fare clic su **test**. I risultati vengono visualizzati nella casella di testo **output** . 
    
7. Fare clic su **OK** per salvare la regola di testo Ignora. Viene visualizzata la regola di testo Ignora definita. 
    
    ![Impostare nome del testo ignorato](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Informazioni sulla somiglianza del documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Impostazione delle opzioni di analisi](set-analyze-options-in-advanced-ediscovery.md)
  
[Impostazione analisi impostazioni avanzate](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Visualizzazione dei risultati dell'analisi](view-analyze-results-in-advanced-ediscovery.md)

