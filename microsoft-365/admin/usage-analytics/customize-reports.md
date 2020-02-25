---
title: Personalizzare i report nell'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Informazioni su come personalizzare i report nel desktop del browser e Power BI.
ms.openlocfilehash: 5fc3b399638b2f1e9b1b2726fbf58e22eda33e01
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244217"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Personalizzare i report nell'analisi dell'utilizzo di Microsoft 365

Microsoft 365 Usage Analytics fornisce un dashboard in Power BI che offre informazioni su come gli utenti adottano e utilizzano Microsoft 365. Il dashboard è solo un punto di partenza per interagire con i dati di utilizzo. Le informazioni contenute nei report possono essere personalizzate.
  
È anche possibile usare Power BI Desktop per personalizzare ulteriormente i report collegandoli ad altre origini dati per ricavare informazioni utili e più complete sull'attività aziendale.
  
## <a name="customizing-reports-in-the-browser"></a>Personalizzazione dei report nel browser

I due esempi seguenti illustrano come modificare un oggetto visivo esistente e come creare un nuovo oggetto visivo.
  
### <a name="modify-an-existing-visual"></a>Modificare un oggetto visivo esistente

In questo esempio viene illustrato come modificare la scheda **attivazione** all'interno del rapporto di **attivazione/gestione licenze** . 
  
1. All'interno del rapporto di **attivazione/gestione delle licenze** , fare clic sulla scheda **attivazione** .
    
2. Immettere la modalità di modifica facendo clic sul pulsante **modifica** nella parte superiore tramite ![il pulsante altro pagina nel pulsante Power](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) bi. 
    
    ![Click Edit report on the top right navigation](../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. In alto a destra, fare clic su **Duplica questa pagina**.
    
    ![Choose Duplicate this page](../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. In basso a destra, fare clic su uno dei grafici a barre che mostra il numero di utenti che si attivano in base al sistema operativo, ad esempio Android, iOS, Mac e così via.
    
5. Nell'area **visualizzazioni** a destra, per rimuovere **Mac count** dall'elemento visivo, fare clic sulla **X** accanto ad essa.

    ![Rimuovi conteggio Mac](../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Creare un nuovo oggetto visivo

L'esempio seguente illustra come creare un nuovo oggetto visivo per tenere traccia di nuovi utenti di Yammer su base mensile.
  
1. Accedere al report **sull'utilizzo del prodotto** usando il NAV sinistro e fare clic sulla scheda **Yammer** .
    
2. Passare alla modalità di modifica facendo clic ![sul pulsante altro pagina in Power bi](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) e **modifica**. 
    
3. Nella parte inferiore della pagina, fare clic su ![Pulsante Aggiungi pagina in Power BI](../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) per creare una nuova pagina.
  
4. Nell'area **visualizzazioni** a destra fare clic sul **grafico a barre in pila** (riga superiore, primo da sinistra).

    ![Seleziona grafico a barre](../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Fare clic sull'angolo inferiore destro della visualizzazione e trascinarla per ingrandirla.

6. Nell'area **campi** a destra espandere la tabella **Calendario** .

7. Trascinare **MonthName** nell'area campi, direttamente sotto l'intestazione **Asse** nell'area **Visualizzazioni**.
 
    ![Nome del mese di trascinamento](../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. Nell'area **Campi** a destra espandere la tabella **TenantProductUsage**.

9. Trascinare **FirstTimeUsers** nell'area campi, direttamente sotto l'intestazione **Valore**.

10. Trascinare **Prodotto** nell'area **Filtri**, direttamente sotto l'intestazione **Filtri a livello di oggetto visivo**.

11. Nell'area **Tipo di filtro** che viene visualizzata, selezionare la casella di controllo **Yammer**.

    ![Selezionare la casella di controllo Yammer](../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Appena sotto l'elenco delle visualizzazioni, fare clic sull' **icona formato formato icona** ![in Power bi Visualizaions](../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).

13. Espandere Titolo e cambiare il valore **Testo titolo** in **Nuovi utenti di Yammer per mese**.
    
14. Cambiare il valore **Dimensione testo** in **12**.
    
15. Modificare il titolo della nuova pagina modificando il nome della pagina in basso a destra.

16.  Salvare il rapporto facendo clic sulla **visualizzazione lettura** in alto e quindi su **Salva**.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Personalizzazione dei report in Power BI Desktop

Per la maggior parte dei clienti è sufficiente modificare i report e gli oggetti visivi grafico in Power BI sul Web. Per alcuni, tuttavia, potrebbe essere necessario unire questi dati con altre origini dati per ricavare informazioni utili e più complete relative al contesto della propria azienda, nel qual caso è possibile personalizzare e creare report aggiuntivi con Power BI Desktop. È possibile scaricare [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) gratis. 
  
### <a name="use-the-reporting-apis"></a>Usare le API Reporting

È possibile iniziare collegandosi direttamente alle API di Reporting ODATA da Microsoft 365 che alimentano questi rapporti.
  
1. Passare a **Recupera dati** \> **Altro** \> **Feed OData** \> **Connetti**.
    
2. Nella finestra URL immettere "https://<i></i>Reports.Office.com/PBI/V1.0/\<TenantId"\>
    
    **Nota:** Le API dei report sono in anteprima e sono soggette a modifiche fino a quando non entrano in produzione. 
  
    ![OData feed URL for Power BI desktop](../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Immettere le credenziali di amministratore di Microsoft 365 (organizzazione o scuola) per l'autenticazione a Microsoft 365 quando richiesto.
    
    Per ulteriori informazioni su chi è autorizzato ad accedere ai report delle app modello di adozione di Microsoft 365, vedere le [domande frequenti](usage-analytics.md#faq) . 
    
4. Dopo aver autorizzato la connessione, viene visualizzata la finestra Strumento di navigazione che mostra i set di dati disponibili a cui connettersi.
    
    Selezionare tutto e fare clic su **Carica**.
    
    I dati verranno in Power BI Desktop. Salvare questo file per iniziare a creare i report necessari.
    
    ![Valori ODATA disponibili nell'API dei report](../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Utilizzare il modello di analisi dei dati di utilizzo di Microsoft 365

È inoltre possibile utilizzare il file del modello Power BI che corrisponde ai report di analisi di utilizzo di Microsoft 365 come punto di partenza per la connessione ai dati. Il vantaggio di usare il file PBIT è che ha la stringa di connessione già stabilita. È anche possibile sfruttare tutte le misure personalizzate create, oltre ai dati che lo schema di base restituisce, usandole come base di sviluppo.
  
È possibile scaricare il file del modello Power BI dall'area download Microsoft dall' [area download](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). Dopo aver scaricato il file del modello di Power BI seguire questa procedura per iniziare:
  
1. Aprire il file PBIT.
    
2. Immettere il valore dell'ID tenant nella finestra di dialogo.
    
    ![Enter your tenant ID to open the pbit file](../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Quando richiesto, immettere le credenziali di amministratore per eseguire l'autenticazione a Microsoft 365.
    
     Per ulteriori informazioni su chi è autorizzato ad accedere ai report di analisi di utilizzo di Microsoft 365. 
    
    Una volta ottenuta l'autorizzazione, i dati verranno aggiornati nel file di Power BI.
    
    Il caricamento dei dati può richiedere del tempo, ma al termine è possibile salvare il file PBIX e continuare a personalizzare i report o importare un'origine dati aggiuntiva nel report.
    
4. Per comprendere come creare i report, pubblicarli nel servizio Power BI e condividerli con l'organizzazione, vedere [Introduzione a Power BI](https://go.microsoft.com/fwlink/?linkid=849802). Se si segue questo percorso per la personalizzazione e la condivisione potrebbero essere necessarie altre licenze di Power BI. Per altre informazioni vedere le [indicazioni sulle licenze](https://go.microsoft.com/fwlink/p/?linkid=849803). 
    

