---
title: Filtrare i dati durante l'importazione dei file PST
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
ms.custom: seo-marvel-apr2020
description: Informazioni su come filtrare i dati usando la funzionalità di importazione intelligente nel servizio di importazione di Office 365 quando si importano file PST in Office 365.
ms.openlocfilehash: d511c1277104a27076116fafcb4b71bc851baaca
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817725"
---
# <a name="filter-data-when-importing-pst-files"></a>Filtrare i dati durante l'importazione dei file PST

Usare la nuova funzionalità di importazione intelligente nel servizio di importazione di Office 365 per filtrare gli elementi nei file PST che vengono effettivamente importati nelle cassette postali di destinazione. Tenere presente quanto segue:
  
- Dopo aver creato e inviato un processo di importazione PST, i file PST vengono caricati in un'area di archiviazione di Azure nel cloud Microsoft.
    
- Microsoft 365 analizza i dati nei file PST, in modo sicuro, identificando l'età degli elementi della cassetta postale e i diversi tipi di messaggio inclusi nei file PST.
    
- Quando l'analisi è completa e i dati sono pronti per l'importazione, è possibile importare tutti i dati nei file PST così come sono o tagliare i dati importati impostando filtri che controllano i dati importati. Ad esempio, è possibile scegliere di:
    
  - Importa solo gli elementi di una determinata età.
    
  - Importa i tipi di messaggio selezionati.
    
  - Escludere i messaggi inviati o ricevuti da utenti specifici.
    
- Dopo aver configurato le impostazioni del filtro, Microsoft 365 importa solo i dati che soddisfano i criteri di filtro nelle cassette postali di destinazione specificate nel processo di importazione.
    
Nella figura seguente viene illustrato il processo di importazione intelligente e vengono evidenziate le attività eseguite e le attività eseguite da Office 365.
  
![Processo di importazione intelligente in Office 365](../media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="create-a-pst-import-job"></a>Creare un processo di importazione PST

- I passaggi descritti in questo argomento presuppongono che sia stato creato un processo di importazione PST nel servizio di importazione di Office 365 tramite il caricamento di rete o la spedizione delle unità. Per istruzioni dettagliate, vedere uno degli argomenti seguenti:
    
  - [Usare il caricamento tramite rete per importare file PST in Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Usare la spedizione unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Dopo aver creato un processo di importazione utilizzando il caricamento di rete, lo stato del processo di importazione nella pagina Importa nel Centro sicurezza & conformità è impostato su Analisi **in** corso, il che significa che Microsoft 365 sta analizzando i dati nei file PST caricati. Fare **clic su** Aggiorna per aggiornare lo stato del processo di ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) importazione. 
    
- Per i processi di importazione della spedizione unità, i dati verranno analizzati da Microsoft 365 dopo che il personale del datacenter Microsoft riceverà l'unità disco rigido e carica i file PST nell'area di archiviazione di Azure per l'organizzazione.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtrare i dati importati nelle cassette postali

Dopo aver creato un processo di importazione PST, seguire questa procedura per filtrare i dati prima di importarlo in Office 365.
  
1. Passare a [https://protection.office.com/](https://protection.office.com/) e accedere con le credenziali di un account amministratore dell'organizzazione. 
    
2. Fare **clic su Governance** delle informazioni \> **Importa** file \> **PST.**
    
    I processi di importazione per l'organizzazione sono elencati nella **pagina Importa file PST.** Si noti **che** il  valore Analisi completata nella colonna Stato indica i processi di importazione che sono stati analizzati da Microsoft 365 e sono pronti per l'importazione. 
    
    ![Lo stato di completamento dell'analisi indica che Microsoft 365 ha analizzato i dati nei file PST](../media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Fare **clic su Pronto per eseguire l'importazione in Office 365** per il processo di importazione che si desidera completare. 
    
    Viene visualizzata una pagina a comparsa con informazioni sui file PST e sul processo di importazione.
    
4. Fare **clic su Importa in Office 365.**
    
    Viene visualizzata la pagina **Filtrare i dati**. Contiene informazioni dettagliate sui dati nei file PST per il processo di importazione, incluse informazioni sull'età dei dati. 
    
    ![La pagina Filtro dati mostra informazioni dettagliate sui dati dei file PST per il processo di importazione](../media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. A seconda che si desideri o meno tagliare i dati importati in Microsoft 365, in Si desidera filtrare i **dati?** eseguire una delle operazioni seguenti:
    
    a. Fare **clic su Sì, si desidera filtrarlo prima dell'importazione** per tagliare i dati importati e quindi fare clic su **Avanti.**
    
    La **pagina Importa dati in Office 365** viene visualizzata con informazioni dettagliate sull'analisi eseguita da Microsoft 365. 
    
    ![Microsoft 365 visualizza informazioni dettagliate sui dati dall'analisi dei file PST](../media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    Il grafico in questa pagina mostra la quantità di dati che verranno importati. Le informazioni su ogni tipo di messaggio trovato nei file PST vengono visualizzate nel grafico. È possibile posizionare il cursore su ogni barra per visualizzare informazioni specifiche sul tipo di messaggio. È inoltre disponibile un elenco a discesa con valori di età diversi in base all'analisi dei file PST. Quando si seleziona un periodo di validità nell'elenco a discesa, il grafico viene aggiornato per mostrare la quantità di dati che verranno importati per la fascia d'età selezionata. 
    
    b. Per configurare filtri aggiuntivi per ridurre la quantità di dati importati, fare clic su **Altre opzioni di filtro.**
    
    ![Configurare i filtri nella pagina Altre opzioni per tagliare i dati importati](../media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    È possibile configurare questi filtri:
    
      - **Fascia** d'età: selezionare un periodo di validità in modo che verranno importati solo gli elementi più nuovi della fascia d'età specificata. Vedere la [sezione Ulteriori informazioni](#more-information) per una descrizione del modo in cui Microsoft 365 determina i bucket di validità per il filtro Fascia **d'età.** 
    
      - **Tipo:** questa sezione mostra tutti i tipi di messaggio trovati nei file PST per il processo di importazione. È possibile deselezionare una casella accanto a un tipo di messaggio che si desidera escludere. Si noti che non è possibile escludere il tipo di messaggio Altro. Per un [elenco degli elementi](#more-information) della cassetta postale inclusi nella categoria Altro, vedere la sezione Ulteriori informazioni. 
    
      - **Utenti:** è possibile escludere i messaggi inviati o ricevuti da utenti specifici. Per escludere le persone visualizzate nel campo Da:, A: o Cc: dei messaggi, fare clic su Escludi utenti accanto a quel tipo di destinatario.  Digitare l'indirizzo di posta elettronica (indirizzo SMTP) della persona, fare clic sull'icona Aggiungi nuovo per aggiungerli all'elenco degli utenti esclusi per quel tipo di destinatario e quindi fare clic su Salva per salvare l'elenco degli utenti  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) esclusi.  
    
        > [!NOTE]
        > Microsoft 365 non mostra informazioni dettagliate sui dati risultate dall'impostazione del **filtro** Persone. Tuttavia, se si imposta questo filtro per escludere i messaggi inviati o ricevuti da utenti specifici, tali messaggi verranno esclusi durante il processo di importazione effettivo. 
  
    c. Fare **clic su** Applica nella pagina a comparsa Altre **opzioni** di filtro per salvare le impostazioni del filtro. 
    
    Le informazioni dettagliate sui dati nella pagina Importa dati in **Office 365** vengono aggiornate in base alle impostazioni del filtro, inclusa la quantità totale di dati che verranno importati in base alle impostazioni del filtro. Si noti che viene visualizzato anche un riepilogo delle impostazioni del filtro. È possibile fare **clic su** Modifica accanto a un filtro per modificare l'impostazione, se necessario. 
    
    ![Le informazioni dettagliate sui dati vengono aggiornate in base alle impostazioni del filtro](../media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Fare clic su **Avanti**.
    
    Viene visualizzata una pagina di stato che mostra le impostazioni del filtro. Anche in questo caso, è possibile modificare qualsiasi impostazione del filtro.
    
    e. Fare **clic su Importa dati** per avviare l'importazione. Si noti che viene visualizzata la quantità totale di dati che verranno importati. 
    
    Oppure
    
    a. Fare **clic su No, si** desidera importare tutti i dati nei file PST in Office 365 e quindi fare clic su **Avanti.**
    
    b. Nella pagina **Importa dati in Office 365** fare clic su Importa **dati** per avviare l'importazione. Si noti che viene visualizzata la quantità totale di dati che verranno importati. 
    
6. Nella pagina **Importa file PST** fare clic su **Aggiorna** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) aggiornamento. Lo stato del processo di importazione viene visualizzato nella **colonna** Stato. 
    
7. Fare clic sul processo di importazione per visualizzare informazioni più dettagliate, ad esempio lo stato di ogni file PST e le impostazioni di filtro configurate.

  
## <a name="more-information"></a>Altre informazioni

- In che modo Microsoft 365 determina gli incrementi per il filtro per fascia d'età? Quando Microsoft 365 analizza un file PST, esamina l'indicatore di data e ora inviato o ricevuto di ogni elemento (se un elemento ha un timestamp inviato e ricevuto, viene selezionata la data meno recente). Microsoft 365 esamina quindi il valore dell'anno per tale timestamp e lo confronta con la data corrente per determinare l'età dell'elemento. Queste età vengono quindi utilizzate come valori nell'elenco a discesa per **il** filtro Fascia d'età. Ad esempio, se un file PST contiene messaggi dal 2016, 2015 e  2014, i valori nel filtro Età saranno **1 anno,** **2 anni** e **3 anni.**
    
- Nella tabella seguente sono elencati i tipi di  messaggio inclusi  nella categoria Altro nel filtro Tipo nella pagina a comparsa Altre opzioni (vedere il passaggio 5b nella procedura precedente).  Attualmente, non è possibile escludere gli elementi nella categoria "Altro" quando si importano file PST in Office 365. 
    
    |**ID classe messaggio**|**Elementi della cassetta postale che utilizzano questa classe messaggio**|
    |:-----|:-----|
    |IPM. Attività  <br/> |Voci del diario  <br/> |
    |IPM.Document  <br/> |Documenti e file (non allegati a un messaggio di posta elettronica)  <br/> |
    |IPM. File  <br/> |(uguale a IPM.Document)  <br/> |
    |IPM. Note.IMC.Notification  <br/> |Report inviati da Internet Mail Connect, ovvero il gateway Exchange Server a Internet  <br/> |
    |IPM. Note.Microsoft.Fax  <br/> |Messaggi fax  <br/> |
    |IPM. Note.Rules.Oof.Template.Microsoft  <br/> |Messaggi di risposta automatica fuori sede  <br/> |
    |IPM. Note.Rules.ReplyTemplate.Microsoft  <br/> |Risposte inviate da una regola di Posta in arrivo  <br/> |
    |IPM. OLE. Classe  <br/> |Eccezioni per una serie ricorrente  <br/> |
    |IPM. Recall.Report  <br/> |Rapporti Richiamo messaggio  <br/> |
    |IPM. Remoto  <br/> |Messaggi di posta remota  <br/> |
    |IPM. Report  <br/> |Relazioni sullo stato degli elementi  <br/> |
