---
title: Utilizzare l'analisi Express in Advanced eDiscovery
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Informazioni su come eseguire la modalità di analisi Express di Advanced eDiscovery
ms.openlocfilehash: 32e1087d33b9e9a6c0e4935bd3488a6b464d06a2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626412"
---
# <a name="use-express-analysis-in-advanced-ediscovery-classic"></a>Utilizzare l'analisi Express in Advanced eDiscovery (Classic) 

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
È possibile utilizzare l' **analisi Express** per analizzare rapidamente un caso ed esportare i risultati. 
  
È possibile utilizzare l'analisi Express per calcolare quasi duplicati e thread di posta elettronica e calcolare i temi. È inoltre possibile impostare alcuni parametri per i temi, la somiglianza dei documenti e i file di esportazione nelle [Impostazioni avanzate per l'analisi espressa](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).
  
## <a name="run-express-analysis"></a>Eseguire l'analisi Express

1. Nella scheda **Express Analysis** (1) selezionare un contenitore per abilitare i pulsanti * * Express Analysis * * (2) e **Advanced Settings** . 
    
    ![Schermata della pagina di analisi rapida](../media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. In **Analyze Parameters**:
    
  - Selezionare **Calcola quasi duplicati e thread di posta elettronica** se si desidera eseguire l'analisi. Questa opzione è selezionata per impostazione predefinita. 
    
  - Controllare il **calcolo dei temi** per elaborare tutti i file e assegnargli i temi. Questa opzione è selezionata per impostazione predefinita. 
    
3. In **destinazione esportazione**:
    
  - Controllare il download del computer **locale** per il download nel sistema locale. 
    
  - Se si seleziona **Esporta in Azure BLOB definito dall'utente** , è anche possibile specificare un URL del contenitore e un token SAS. 
    
    > [!NOTE]
    > Dopo l'archiviazione di un pacchetto di esportazione nell'oggetto BLOB di Azure definito dall'utente, i dati non vengono più gestiti da Advanced eDiscovery. viene gestito dal BLOB di Azure. Questo significa che, se si elimina il caso, i file esportati rimarranno sempre sul BLOB di Azure. 
  
  - **Save SAS token for future Export Session**: se selezionata, il token SAS verrà crittografato nel database interno di Advanced eDiscovery per un utilizzo futuro.
    
    > [!NOTE]
    > Attualmente il token SAS scade dopo un mese. Se si tenta di eseguire il download dopo più di un mese, è necessario annullare l'ultima sessione e quindi riesportarla. 
  
4. Per avviare l'analisi Express con le impostazioni predefinite, scegliere **analisi espressa**e la pagina **stato attività** verrà visualizzata 
    
    Nella pagina **stato attività** è possibile espandere le schede **Process**, **Analyze** and **Export** per visualizzare i dettagli relativi all'esecuzione espressa. 
    
    ![Schermata della pagina di stato attività di analisi avanzata di eDiscovery Express](../media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. Scegliere la pagina **Riepilogo analisi Express** per elencare informazioni dettagliate sull'esecuzione. 
    
    Nella parte inferiore della pagina **Riepilogo analisi rapida** scegliere **Scarica ultima sessione** per scaricare i file di analisi TP del computer locale. Per prima cosa è necessario scaricare lo strumento di esportazione di eDiscovery e incollare la chiave Export per lo strumento di esportazione di eDiscovery. 
    
## <a name="advanced-settings-for-express-analysis"></a>Impostazioni avanzate per l'analisi espressa
<a name="BK_AdvancedSettings"> </a>

Facoltativamente, è possibile impostare **Impostazioni avanzate** per modificare i parametri di analisi Express predefiniti. 
  
1. Nella sezione **Analyze** : 
    
  - Nelle **quasi duplicati e nei thread di posta elettronica**, immettere il valore di **somiglianza del documento** oppure accettare l'impostazione predefinita 65%. 
    
  - Nel **numero massimo di temi** immettere o selezionare un valore per il numero di temi da creare. Il valore predefinito è 200. 
    
    > [!NOTE]
    > L'aumento del numero di temi influenza le prestazioni e la possibilità di generalizzare un tema. Maggiore è il numero di temi, maggiore è il livello di granularità. Ad esempio, se un insieme di temi 50 include un tema come "basket, Spurs, Clippers, Lakers"; 300 temi possono includere temi distinti: "Spurs", "Clippers", "Lakers". Se non si ha consapevolezza del tema "basket" e si utilizza questa funzionalità per ECA, è possibile utilizzare il tema "basket". Tuttavia, se l'elaborazione ha avuto troppi temi, potrebbe non essere possibile visualizzare la parola "basket" e potrebbe non essere in grado di riconoscere che gli Spurs e i Clippers sono buoni temi di basket da rivedere, anziché elementi che vengono utilizzati per i capelli. 
  
  - Nei **temi suggeriti** scegliere **modifica** per suggerire le parole del tema per controllare l'elaborazione dei temi. Advanced eDiscovery si concentrerà su queste parole suggerite e cercherà di creare uno o più temi rilevanti, in base alle impostazioni "numero massimo di temi". 
    
    Ad esempio, se la parola suggerita è "computer" e si specifica "2" come "numero massimo di temi", Advanced eDiscovery proverà a generare due temi correlati alla parola "computer". I due temi potrebbero essere, ad esempio, "software per computer" e "hardware del computer".
    
    ![Aggiungi tema suggerito](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - **Modalità** Nell'elenco a discesa selezionare un'opzione **temi** : 
    
  - **Create and Apply Model**: calcola i temi in base ai modelli da un segmento dei file e quindi distribuisce i file tra di essi.
    
  - **Create Model**: consente di calcolare un modello di temi da un segmento dei file. Il processo di applicazione della divisione dei file viene effettuato separatamente in un altro momento.
    
  - **Applicazione modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non è stato ancora applicato. In questo modo i file verranno divisi in base ai temi.
    
2. Nella sezione **Export** : 
    
1. Nel **batch di esportazione selezionare**:
    
  - Nell'elenco **Esporta batch** selezionare il nome del batch o esportare i risultati in batch di esportazione 01 (il batch predefinito). 
    
  - Per esportare i risultati per i nuovi file aggiunti a un caso esistente, continuare con il batch corrente. Per creare una sessione nel batch, selezionare lo stesso numero di batch e fare clic su **Crea sessione di esportazione** è possibile utilizzare questa opzione per esportare gli stessi parametri del batch precedente, in modo incrementale. 
    
  - Per esportare in un nuovo batch, fare **Add** ![clic su Aggiungi](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icona e immettere un nuovo nome in **batch Name** (o accettare il valore predefinito) e una descrizione in **batch Description**. Fare clic su **OK**.
    
  - Per modificare un nome o una descrizione in batch, selezionare il nome in **batch di esportazione**, fare](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)clic su **modifica** ![icona modifica e quindi modificare i campi.
    
    > [!NOTE]
    > Dopo aver eseguito le sessioni per un batch di esportazione, non è possibile eliminarle. Inoltre, solo alcuni parametri possono essere modificati dopo l'esecuzione della prima sessione. 
  
  - Per creare un batch di esportazione duplicato, scegliere **Duplica esportazione batch** ![creare un'icona](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) del batch di esportazione duplicata e immettere un nome e una descrizione per il batch duplicato nel pannello. 
    
  - Per eliminare un batch di esportazione, scegliere **Delete** ![Delete an export batch](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)Icon.
    
  - Per visualizzare la cronologia di un batch, fare clic su cronologia **batch** ![Visualizza](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)cronologia.
    
2. In define p **opulation:** selezionare **Includi solo i file sopra il Punteggio di rilevanza** e/o il **batch di esportazione** se si desidera ottimizzare le impostazioni per il batch di esportazione. Se si seleziona **Includi solo i file sopra il Punteggio di rilevanza**, il **problema** è abilitato e se il Punteggio di pertinenza del file è superiore al Punteggio di taglio del problema selezionato, il file viene esportato. Il file verrà esportato a meno che non sia stato escluso dal filtro **per la revisione** . Se si seleziona **affina esportazione batch**, i pulsanti di opzione **deduplica** e **Filtra in base a' per la revisione '** sono abilitati. Se si sceglie **deduplicazione**, i file duplicati verranno filtrati in base al criterio definito: [livello case (impostazione predefinita): da ogni set di file duplicati nell'intero caso, tutti tranne un file verranno deselezionati. Livello di custode: da ogni serie di file duplicati dello stesso custode, tutti tranne un file verranno deduplicati. Un record di tutti i file duplicati è disponibile nell'output di esportazione. Se si sceglie **Filtra per campo ' per la revisione '** , selezionare **modifica in metadati** per immettere le impostazioni del campo **' per la revisione '**. Selezionare **Includi file di input**per includere i file di origine nel contenuto del pacchetto. È possibile cancellare questa opzione per velocizzare il processo di esportazione. Si noti che i file nativi verranno esportati in tutti i casi.
    
3. In **Definisci metadati**selezionare una delle opzioni seguenti nell'elenco **modello di esportazione** (una volta per sessione). 
    
  - **Standard**: set di elementi di dati, metadati e proprietà di base. Utilizzare questa opzione quando i dati di importazione sono già stati elaborati in Advanced eDiscovery e i dati di esportazione vengono caricati in un sistema che già contiene i file. Per impostazione predefinita, le colonne dei modelli di esportazione vengono create e riempite.
    
  - **All**: set completo di metadati standard, inclusi tutti i dati di elaborazione, nonché analisi e punteggi di pertinenza. Questo modello è necessario quando Advanced eDiscovery esegue l'elaborazione e i dati dei file vengono caricati su un sistema esterno per la prima volta.
    
  - **Problemi**: selezionare **tutti i problemi** o selezionare un particolare problema creato. 
    
Scegliere **OK**per salvare le impostazioni avanzate, **ripristinare** i valori predefiniti per l'utilizzo del valore predefinito oppure **Annulla** per annullare l'impostazione delle impostazioni avanzate. 
  
## <a name="see-also"></a>Vedere anche
<a name="BK_AdvancedSettings"> </a>

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)

