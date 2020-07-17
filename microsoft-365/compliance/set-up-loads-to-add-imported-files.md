---
title: Impostare i carichi per aggiungere i file importati in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: Esaminare i passaggi per aggiungere i file importati all'ultimo carico definito, o batch, di file prima di eseguire la formazione di pertinenza in Advanced eDiscovery.
ms.openlocfilehash: fc05111d9193a935158b4b00a14717877ae148a7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936817"
---
# <a name="set-up-loads-to-add-imported-files-in-advanced-ediscovery-classic"></a>Impostare i carichi per aggiungere i file importati in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In Advanced eDiscovery, un carico è un nuovo batch di file aggiunto a un caso. Per impostazione predefinita, viene definito un carico e vengono aggiunti tutti i file importati. Prima di eseguire la formazione di pertinenza, i file importati devono essere aggiunti al carico. 
  
Si considerino gli scenari seguenti:
  
- I nuovi file sono noti per essere simili ai file precedenti caricati nel database del caso oppure il carico precedente di file era un set casuale della raccolta file. In questa istanza, aggiungere i file importati al caricamento del file corrente.
    
- I nuovi file sono diversi da quelli precedenti (ad esempio, da un'origine diversa) oppure non sono presenti informazioni precedenti che sono simili o diversi ai carichi precedenti. In questo scenario, aggiungere i file importati a un nuovo caricamento del file. Advanced eDiscovery riconosce questo come uno scenario dei carichi di rotolamento, richiama un processo di aggiornamento, blocca la formazione di pertinenza e i calcoli in batch fino al completamento del recupero e il nuovo carico è integrato e addestrato. 
    
## <a name="adding-imported-files-to-the-current-load"></a>Aggiunta di file importati al carico corrente

Tutti i file importati devono essere aggiunti a un carico da elaborare in Advanced eDiscovery. I file importati vengono aggiunti all'ultimo carico definito. Se si importano ulteriori file in un secondo momento, è necessario aggiungerli anche al carico.
  
1. Nella scheda ** \> configurazione** pertinenza pertinenza selezionare **carica**.
    
    ![Scheda dei caricamenti per la configurazione di pertinenza](../media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. **Includi file**: selezionare un'opzione per i file da includere. Per impostazione predefinita, l'aggiunta di file al carico corrente si basa sulla popolazione "tutti i file".
    
    > [!TIP]
    > Caricare tutti i file abbattuti disponibili in pertinenza. Se si prevede di caricare solo un sottoinsieme dei file disponibili, consultare prima di tutto il supporto, in quanto i sottoinsiemi di caricamento possono influire negativamente sulla formazione per pertinenza. 
  
3. In **gestione carichi**selezionare un carico.
    
4. Fare clic su **Aggiungi file**. I file vengono aggiunti al carico e viene visualizzato un messaggio di conferma. 
    
5. Fare clic su **OK**.
    
I file possono ora essere elaborati in una pertinenza eDiscovery avanzata per la formazione dei file.
  
## <a name="editing-a-load-name-within-a-case"></a>Modifica di un nome di carico all'interno di un caso

Se si modifica il nome del carico, è consigliabile utilizzare un nome significativo per il caso.
  
1. Nella scheda ** \> configurazione** pertinenza pertinenza selezionare **carica**.
    
2. Nell'elenco **gestione carichi** selezionare un carico e fare clic sull'icona **modifica** . Viene visualizzata la finestra modifica caricamento. 
    
3. Immettere le modifiche e quindi fare clic su **OK**.
    
## <a name="adding-imported-files-to-a-new-load"></a>Aggiunta di file importati a un nuovo carico

Dopo aver avviato la formazione di pertinenza o aver eseguito il calcolo in batch, è possibile che si desideri importare ed elaborare un ulteriore set di file. 
  
Durante il recupero, è possibile creare, contrassegnare e analizzare il set di catch-up. Advanced eDiscovery confronta la valutazione dei file rilevanti e non rilevanti nel nuovo carico con quelli presenti nei carichi precedenti. In base ai risultati, viene richiesto di prendere decisioni di catch-up, se necessario, e Advanced eDiscovery fornisce consigli in base alle informazioni sulla pertinenza accumulate. 
  
I carichi di rotolamento e la funzionalità di catch-up variano come indicato di seguito: 
  
- Quando si importa un nuovo caricamento di file dopo il calcolo del batch, Advanced eDiscovery determina in che misura i file rientrano in una delle categorie seguenti:
    
  - Analogo (omogeneo): non è necessario un nuovo ciclo personalizzato di formazione per la pertinenza e le conoscenze accumulate dal carico precedente possono essere applicate "così com'è" al nuovo carico. 
    
  - Distinct (eterogeneo): è necessario un nuovo ciclo personalizzato di formazione per la pertinenza e non è possibile applicare le informazioni accumulate dal carico precedente. 
    
    Tali termini si riferiscono al livello di somiglianza dei file tra i carichi e non all'interno dei carichi. 
    
- Quando si importa un nuovo carico di file durante la formazione di pertinenza (prima del calcolo del batch), il recupero consente di continuare la formazione sulla pertinenza del set di file Uniti. Advanced eDiscovery non calcola se il nuovo carico è simile o distinto rispetto al carico precedente. Raccoglie semplicemente informazioni sul nuovo carico e consente la formazione della pertinenza per continuare con i nuovi e precedenti insiemi di file. 
    
- Quando sono presenti più problemi relativi alla formazione sulla pertinenza e ai problemi dopo il calcolo del batch, il processo di recupero viene eseguito una volta per tutti i problemi e i risultati vengono calcolati e visualizzati per ogni problema.
    
> [!NOTE]
> Le dimensioni dell'esempio di catch-up possono variare. Dipende dalle dimensioni del nuovo carico rispetto ai carichi precedenti e dal numero di esempi completati prima di aggiungere il nuovo carico. L'esempio di catch-up è in genere un set di 200 a 2.000 file dal nuovo carico. 
  
> [!TIP]
> Catch-up interrompe tutte le altre attività e richiede il tagging e la revisione dei singoli file. Pertanto, è possibile ridurre il sovraccarico quando si aggiungono nuovi file in batch di grandi dimensioni. 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a>Aggiunta di un nuovo caricamento dei file con i carichi di catch-up e Rolling

1. Nella scheda ** \> configurazione** pertinenza pertinenza selezionare **carica**.
    
2. In **gestione carichi**fare clic sull' **+** icona per aggiungere un carico. Viene visualizzato un messaggio di conferma. 
    
3. Fare clic su **Sì** per continuare. Viene visualizzata la finestra di dialogo **Aggiungi nuovo caricamento** . 
    
    > [!NOTE]
    > È possibile aggiungere un nuovo carico solo se le azioni sono state eseguite al carico precedente. 
  
4. Nella finestra di dialogo **Aggiungi nuovo carico** , digitare informazioni in nome e **Descrizione** del **caricamento** e quindi fare clic su **OK**. Advanced eDiscovery aggiunge un nuovo carico.
    
5. Per importare il nuovo file di caricamento, fare clic su **Aggiungi file**. Tutti i nuovi file vengono aggiunti a questo carico. Dopo che Advanced eDiscovery importa i file, riconosce lo scenario dei carichi di rotolamento e indica il passaggio successivo.
    
6. Fare clic su **catch-up** nella parte inferiore della finestra di dialogo per eseguire lo scenario. 
    
    Viene creato un singolo set di catch-up, che in genere contiene 200 a 2.000 file dal nuovo carico, per tutti i problemi per consentire il tagging dei file simultanei.
    
    Vengono forniti informazioni dettagliate sul fatto che i carichi siano simili o distinti, se Advanced eDiscovery ha unito o diviso i carichi automaticamente e le informazioni relative all'elaborazione nel passaggio successivo.
    
    È quindi possibile contrassegnare i file ed eseguire un'operazione di calcolo. Il tagging attiva la pertinenza per determinare se i carichi sono simili o distinti e consente di continuare a lavorare sul nuovo set di file.
    
7. Dopo la revisione del set di catch-up, visualizzare la verifica della **pertinenza \> ** per i risultati di catch-up. 
    
1. Se il nuovo caricamento file è stato aggiunto durante la formazione di pertinenza (ovvero, il problema non è stato ancora superato tramite calcolo batch), **continuare l'allenamento** è il passaggio successivo, indipendentemente dai risultati di catch-up. 
    
    I carichi nuovi e precedenti vengono elaborati con un carico e una formazione di pertinenza continua sul set Unito. Dopo aver completato questa procedura, è possibile continuare la formazione sulla pertinenza. 
    
2. Se il nuovo carico è stato aggiunto dopo il calcolo batch, procedere con i passaggi seguenti.
    
8. Per i nuovi carichi aggiunti dopo il calcolo in batch, Advanced eDiscovery determina se il nuovo carico è simile o diverso dai carichi precedenti, come indicato di seguito:
    
1. Se i carichi sono stati trovati come simili: non è necessaria alcuna formazione supplementare sulla pertinenza. Il dashboard indica che il passaggio successivo consigliato consiste nell'eseguire * * il calcolo batch * * di nuovo per calcolare i punteggi di pertinenza per il nuovo carico. I carichi sono stati trovati come simili, quindi è possibile eseguire l'analisi di classificazione precedente nei nuovi file. 
    
2. Se i carichi sono stati individuati come distinti: è necessaria una formazione più pertinente e il passaggio successivo è la decisione di catch-up. Selezionare una decisione di catch-up come indicato di seguito:
    
    Se si seleziona **Unisci carichi**, Advanced eDiscovery unisce i carichi precedenti e nuovi per il set di training. Anche se il primo carico ha superato il calcolo in batch, è necessario un numero maggiore di formazione. Continuare a formare carichi nuovi e precedenti insieme. Il calcolo batch verrà quindi eseguito di nuovo e i punteggi del calcolo batch precedenti devono essere ignorati. Scegliere questa selezione quando i punteggi di rilevanza per i carichi esistenti possono essere ricalcolati, ad esempio quando la revisione dei carichi di file esistenti non è stata avviata.
    
    Se si seleziona **Suddividi carichi**, continuare la formazione sulla pertinenza solo sul nuovo carico. In questo caso, i punteggi del calcolo batch precedenti rimarranno così come sono. Scegliere questa opzione se non è possibile ricalcolare i punteggi di pertinenza esistenti per i carichi esistenti, ad esempio se è già stata avviata la revisione dei carichi esistenti. I punteggi relativi alla pertinenza sono gestiti separatamente da questo punto e non possono essere Uniti.
    
3. Fare clic su **continua formazione**.
    
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Definire i problemi e assegnare gli utenti](define-issues-and-assign-users.md)
  
[Definire parole chiave evidenziate e opzioni avanzate](define-highlighted-keywords-and-advanced-options.md)

