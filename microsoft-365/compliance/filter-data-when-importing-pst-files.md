---
title: Filtrare i dati durante l'importazione di file PST in Office 365
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
search.appverid: MOE150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: 'Utilizzare la nuova caratteristica Intelligent Import nel servizio di importazione di Office 365 per filtrare gli elementi che vengono effettivamente importati nelle cassette postali di destinazione. Intelligent Import consente di decidere in modo proattivo quali dati importare e cosa lasciarsi alle spalle. Intelligent Import fornisce anche informazioni dettagliate sui dati che si stanno importando in Office 365. '
ms.openlocfilehash: 0ac3b23443c42a53efc94faccc99991f608185b5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594567"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a>Filtrare i dati durante l'importazione di file PST in Office 365

Utilizzare la nuova caratteristica Intelligent Import nel servizio di importazione di Office 365 per filtrare gli elementi nei file PST che vengono effettivamente importati nelle cassette postali di destinazione. Tenere presente quanto segue:
  
- Dopo aver creato e inviato un processo di importazione PST, i file PST vengono caricati in un'area di archiviazione di Azure nel cloud Microsoft.
    
- Office 365 analizza i dati nei file PST, in modo sicuro e sicuro, identificando l'età degli elementi della cassetta postale e i diversi tipi di messaggi inclusi nei file PST.
    
- Al termine dell'analisi e i dati sono pronti per l'importazione, è possibile importare tutti i dati nei file PST come è o tagliare i dati importati impostando filtri che consentono di controllare i dati che vengono importati. Ad esempio, è possibile scegliere di:
    
  - Importare solo gli elementi di un determinato periodo di tempo.
    
  - Importare i tipi di messaggio selezionati.
    
  - Escludere i messaggi inviati o ricevuti da persone specifiche.
    
- Dopo aver configurato le impostazioni del filtro, Office 365 importa solo i dati che soddisfano i criteri di filtro alle cassette postali di destinazione specificate nel processo di importazione.
    
Nell'immagine seguente viene illustrato il processo di importazione intelligente e vengono evidenziate le attività eseguite e le attività svolte da Office 365.
  
![Processo di importazione intelligente in Office 365](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a>Prima di iniziare

- Nella procedura descritta in questo argomento si presuppone che sia stato creato un processo di importazione PST nel servizio di importazione di Office 365 tramite caricamento di rete o unità di trasporto. Per istruzioni dettagliate, vedere uno degli argomenti seguenti:
    
  - [Usare il caricamento tramite rete per importare file PST in Office 365](use-network-upload-to-import-pst-files.md)
    
  - [Usare la spedizione unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- Dopo aver creato un processo di importazione tramite il caricamento di rete, lo stato del processo di importazione nella pagina Importa nel centro sicurezza & conformità è impostato su **analisi in corso**, il che significa che Office 365 analizza i dati nei file PST caricati. ![Fare **clic su Aggiorna aggiornamento**](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) per aggiornare lo stato del processo di importazione. 
    
- Per i processi di importazione delle unità di trasporto, i dati verranno analizzati da Office 365 dopo che il personale del Data Center di Microsoft riceverà il disco rigido e caricherà i file PST nell'area di archiviazione di Azure per l'organizzazione.
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>Filtrare i dati che vengono importati nelle cassette postali

Dopo aver creato un processo di importazione PST, attenersi alla procedura seguente per filtrare i dati prima di importarli in Office 365.
  
1. Passare a [https://protection.office.com/](https://protection.office.com/) e accedere con le credenziali di un account amministratore dell'organizzazione di Office 365. 
    
2. Fare clic su **informazioni sulla governance** \> **Import** \> **Import PST files**.
    
    I processi di importazione per l'organizzazione sono elencati nella pagina **importazione file PST** . Si noti che il valore **analisi completata** nella colonna **stato** indica i processi di importazione analizzati da Office 365 e che sono pronti per l'importazione. 
    
    ![Lo stato del completamento dell'analisi indica che Office 365 ha analizzato i dati nei file PST](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. Fare clic su **pronto per l'importazione in Office 365** per il processo di importazione che si desidera completare. 
    
    Viene visualizzata una pagina a comparsa con informazioni sui file PST e sul processo di importazione.
    
4. Fare clic su **Importa in Office 365**.
    
    Viene visualizzata la pagina **Filtrare i dati**. Contiene informazioni approfondite sui dati nei file PST per il processo di importazione, incluse quelle relative all'età dei dati. 
    
    ![La pagina dei dati del filtro Visualizza informazioni dettagliate sui file PST per il processo di importazione](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. In base al fatto che si desideri o meno tagliare i dati importati in Office 365, eseguire una delle operazioni seguenti per **filtrare i dati**:
    
    a. Fare clic su **Sì, si desidera filtrarlo prima** di eseguire l'importazione per tagliare i dati importati e quindi fare clic su **Avanti**.
    
    La pagina **Import data to Office 365** page viene visualizzata con informazioni dettagliate sull'analisi eseguita da Office 365. 
    
    ![Office 365 Visualizza informazioni dettagliate sulla sua analisi dei file PST](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    Il grafico in questa pagina Visualizza la quantità di dati che verranno importati. Le informazioni su ogni tipo di messaggio trovato nei file PST vengono visualizzate nel grafico. È possibile posizionare il puntatore del mouse su ogni barra per visualizzare informazioni specifiche sul tipo di messaggio. È inoltre presente un elenco a discesa con valori di età diversi in base all'analisi dei file PST. Quando si seleziona un'età nell'elenco a discesa, il grafico viene aggiornato per visualizzare la quantità di dati che verranno importati per l'età selezionata. 
    
    b. Per configurare i filtri di addizione per ridurre la quantità di dati importati, fare clic su **altre opzioni di filtro**.
    
    ![Configurare i filtri nella pagina altre opzioni per tagliare i dati importati](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    È possibile configurare questi filtri:
    
      - **Age** -selezionare un'età in modo che vengano importati solo gli elementi più recenti di quelli specificati. Vedere la sezione [ulteriori informazioni](#more-information) per una descrizione del modo in cui Office 365 determina i bucket di validità del filtro di **età** . 
    
      - **Tipo** : in questa sezione vengono illustrati tutti i tipi di messaggi trovati nei file PST per il processo di importazione. È possibile deselezionare una casella accanto a un tipo di messaggio che si desidera escludere. Si noti che non è possibile escludere l'altro tipo di messaggio. Per un elenco degli elementi delle cassette postali inclusi nell'altra categoria, vedere la sezione [ulteriori informazioni](#more-information) . 
    
      - **Utenti** : è possibile escludere i messaggi inviati o ricevuti da persone specifiche. Per escludere le persone che vengono visualizzate nel campo da: campo, a: oppure il campo CC: dei messaggi, fare clic su **Escludi utenti** accanto a quel tipo di destinatario. Digitare l'indirizzo di posta elettronica (indirizzo SMTP) della persona, ****![fare clic su](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) Aggiungi nuova icona per aggiungerli all'elenco di utenti esclusi per tale tipo di destinatario e quindi fare clic su **Salva** per salvare l'elenco di utenti esclusi. 
    
        > [!NOTE]
        > Office 365 non Visualizza informazioni dettagliate risultante dall'impostazione del filtro **persone** . Tuttavia, se si imposta questo filtro per escludere i messaggi inviati o ricevuti da persone specifiche, tali messaggi verranno esclusi durante il processo di importazione effettivo. 
  
    c. Fare clic su **applica** nella pagina **altre opzioni di filtro** per salvare le impostazioni del filtro. 
    
    Le informazioni dettagliate sulla pagina **Importa dati in Office 365** vengono aggiornate in base alle impostazioni del filtro, inclusa la quantità totale di dati che verranno importati in base alle impostazioni del filtro. Si noti che è anche visualizzato un riepilogo delle impostazioni del filtro. È possibile fare clic su **modifica** accanto a un filtro per modificare l'impostazione, se necessario. 
    
    ![Gli Insight dei dati vengono aggiornati in base alle impostazioni del filtro](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d. Fare clic su **Avanti**.
    
    Viene visualizzata una pagina di stato per visualizzare le impostazioni del filtro. Anche in questo caso, è possibile modificare le impostazioni del filtro.
    
    e. Fare clic su **Importa dati** per avviare l'importazione. Si noti che la quantità totale di dati che verranno importati viene visualizzata. 
    
    Oppure
    
    a. Fare clic su **No, si desidera importare tutto** per importare tutti i dati nei file PST in Office 365 e quindi fare clic su **Avanti**.
    
    b. Nella pagina **Importa dati in Office 365** fare clic su **Importa dati** per avviare l'importazione. Si noti che la quantità totale di dati che verranno importati viene visualizzata. 
    
6. Nella pagina **importazione file PST** **fare clic su Aggiorna** ![aggiornamento](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png). Lo stato del processo di importazione viene visualizzato nella colonna **stato** . 
    
7. Fare clic sul pulsante Importa il processo per visualizzare informazioni più dettagliate, ad esempio lo stato di ogni file PST e le impostazioni di filtro configurate.

  
## <a name="more-information"></a>Ulteriori informazioni

- In che modo Office 365 determina gli incrementi del filtro di validità? Quando Office 365 analizza un file PST, viene visualizzato l'indicatore di data e ora di invio di ogni elemento (se un elemento ha un timestamp sia inviato che ricevuto, la più vecchia è selezionata). Successivamente, Office 365 esamina il valore dell'anno per tale timestamp e lo confronta con la data corrente per determinare l'età dell'elemento. Tali ere vengono quindi utilizzate come valori nell'elenco a discesa del filtro di **validità** . Ad esempio, se un file PST contiene messaggi provenienti da 2016, 2015 e 2014, i valori del filtro di **validità** sarebbero **1 anno**, **2 anni**e **3 anni**.
    
- Nella tabella seguente sono elencati i tipi di messaggio inclusi nell' **altra** categoria del filtro **tipo** nella pagina altre **Opzioni** di volo (vedere il passaggio 5b nella procedura precedente). Attualmente, non è possibile escludere gli elementi nella categoria "altro" quando si importa PST in Office 365. 
    
    |**ID classe messaggio**|**Elementi della cassetta postale che utilizzano questa classe messaggio**|
    |:-----|:-----|
    |IPM. Attività  <br/> |Voci del diario  <br/> |
    |IPM. Documento  <br/> |Documenti e file (non allegati a un messaggio di posta elettronica)  <br/> |
    |IPM. File  <br/> |(uguale a IPM. Documento  <br/> |
    |IPM. Note. IMC. Notification  <br/> |Report inviati da Internet mail Connect, che è il gateway di Exchange Server per Internet  <br/> |
    |IPM. Note. Microsoft. fax  <br/> |Messaggi fax  <br/> |
    |IPM. Note. Rules. OOF. template. Microsoft  <br/> |Messaggi di risposta automatica fuori sede  <br/> |
    |IPM. Note. Rules. ReplyTemplate. Microsoft  <br/> |Risposte inviate da una regola di posta in arrivo  <br/> |
    |IPM. OLE. Classe  <br/> |Eccezioni per una serie ricorrente  <br/> |
    |IPM. Recall. report  <br/> |Rapporti Richiamo messaggio  <br/> |
    |IPM. Remoto  <br/> |Messaggi di posta elettronica remoti  <br/> |
    |IPM. Report  <br/> |Report sullo stato degli elementi  <br/> |
