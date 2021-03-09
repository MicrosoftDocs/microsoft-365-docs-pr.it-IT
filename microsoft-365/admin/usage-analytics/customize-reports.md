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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Informazioni su come personalizzare i report nel browser e in Power BI Desktop.
ms.openlocfilehash: 3c662dfa91939c68f0aa0a85c19a1fab003064bf
ms.sourcegitcommit: d3c1b08b3a8af29ef19ffe77da063920f28fe290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50572651"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Personalizzare i report nell'analisi dell'utilizzo di Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

L'analisi dell'utilizzo di Microsoft 365 fornisce un dashboard in Power BI che offre informazioni dettagliate su come gli utenti adottano e usano Microsoft 365. Il dashboard è solo un punto di partenza per interagire con i dati di utilizzo. Le informazioni contenute nei report possono essere personalizzate.
  
È anche possibile usare Power BI Desktop per personalizzare ulteriormente i report collegandoli ad altre origini dati per ricavare informazioni utili e più complete sull'attività aziendale.
  
## <a name="customizing-reports-in-the-browser"></a>Personalizzazione dei report nel browser

I due esempi seguenti illustrano come modificare un oggetto visivo esistente e come creare un nuovo oggetto visivo.
  
### <a name="modify-an-existing-visual"></a>Modificare un oggetto visivo esistente

Questo esempio mostra come modificare la scheda **Attivazione** all'interno del report **attivazione/licenza.** 
  
1. Nel report **Attivazione/Licenze** seleziona la **scheda Attivazione.**
    
2. Per passare alla modalità di modifica, scegliere il **pulsante** Modifica nella parte superiore del pulsante Altro ![ pagina in Power ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI. 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. In alto a destra scegliere **Duplica questa pagina.**
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. In basso a destra scegli uno dei grafici a barre che mostrano il numero di utenti che si attivano in base al sistema operativo, ad esempio Android, iOS, Mac e così via.
    
5. Nell'area **Visualizzazioni** a destra, per rimuovere Mac **Count** dall'oggetto visivo, seleziona la **X** accanto.

    ![Rimuovi conteggio Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Creare un nuovo oggetto visivo

L'esempio seguente illustra come creare un nuovo oggetto visivo per tenere traccia di nuovi utenti di Yammer su base mensile.
  
1. Passare al **report Utilizzo prodotti usando** il riquadro di spostamento sinistro e selezionare la scheda **Yammer.**
    
2. Passare alla modalità di modifica scegliendo ![ il pulsante Altro pagina in Power BI e ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **Modifica.** 
    
3. Nella parte inferiore della pagina, selezionare il pulsante ![Pulsante Aggiungi pagina in Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) per creare una nuova pagina.
  
4. Nell'area **Visualizzazioni** a destra scegliere il grafico a **barre** in pila (riga superiore, prima da sinistra).

    ![Seleziona grafico a barre](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Selezionare la visualizzazione in basso a destra e trascinarla per ingrandirla.

6. **Nell'area Campi** a destra espandere la **tabella** Calendario.

7. Trascinare **MonthName** nell'area campi, direttamente sotto l'intestazione **Asse** nell'area **Visualizzazioni**.
 
    ![Trascinare il nome del mese](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. Nell'area **Campi** a destra espandere la tabella **TenantProductUsage**.

9. Trascinare **FirstTimeUsers** nell'area campi, direttamente sotto l'intestazione **Valore**.

10. Trascinare **Prodotto** nell'area **Filtri**, direttamente sotto l'intestazione **Filtri a livello di oggetto visivo**.

11. Nell'area **Tipo di filtro** che viene visualizzata, selezionare la casella di controllo **Yammer**.

    ![Seleziona la casella di controllo di Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Appena sotto l'elenco delle visualizzazioni, scegliere **l'icona** ![ Formato icona Formato in Power BI Visualizaions. ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)

13. Espandere Titolo e cambiare il valore **Testo titolo** in **Nuovi utenti di Yammer per mese**.
    
14. Cambiare il valore **Dimensione testo** in **12**.
    
15. Modificare il titolo della nuova pagina modificando il nome della pagina in basso a destra.

16.  Salvare il report facendo clic su **Visualizzazione lettura** nella parte superiore e quindi **su Salva.**
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Personalizzazione dei report in Power BI Desktop

Per la maggior parte dei clienti è sufficiente modificare i report e gli oggetti visivi grafico in Power BI sul Web. Per alcuni, tuttavia, potrebbe essere necessario unire questi dati con altre origini dati per ricavare informazioni utili e più complete relative al contesto della propria azienda, nel qual caso è possibile personalizzare e creare report aggiuntivi con Power BI Desktop. È possibile scaricare [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) gratis. 
  
### <a name="use-the-reporting-apis"></a>Usare le API Reporting

È possibile iniziare connettendosi direttamente alle API di report ODATA di Microsoft 365 che generano questi report.
  
1. Passare a **Recupera dati** \> **Altro** \> **Feed OData** \> **Connetti**.
    
2. Nella finestra dell'URL immettere "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"
    
    **NOTA:** Le API per i report sono in anteprima e sono soggette a modifiche fino a quando non vengono in produzione. 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Quando richiesto, immettere le credenziali di amministratore di Microsoft 365 (organizzazione o istituto di istruzione) per l'autenticazione in Microsoft 365.
    
    Per altre [informazioni sugli](usage-analytics.md#faq) utenti autorizzati ad accedere ai report dell'app modello Microsoft 365 Adoption, vedere le domande frequenti. 
    
4. Dopo aver autorizzato la connessione, viene visualizzata la finestra Strumento di navigazione che mostra i set di dati disponibili a cui connettersi.
    
    Selezionare tutto e scegliere **Carica.**
    
    I dati verranno in Power BI Desktop. Salvare questo file per iniziare a creare i report necessari.
    
    ![Valori ODATA disponibili nell'API per i report](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Usare il modello di analisi dell'utilizzo di Microsoft 365

È anche possibile usare il file modello di Power BI che corrisponde ai report di analisi di utilizzo di Microsoft 365 come punto di partenza per connettersi ai dati. Il vantaggio di usare il file PBIT è che ha la stringa di connessione già stabilita. È anche possibile sfruttare tutte le misure personalizzate create, oltre ai dati che lo schema di base restituisce, usandole come base di sviluppo.
  
È possibile scaricare il file modello di Power BI [dall'Area download Microsoft.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) Dopo aver scaricato il file modello di Power BI, eseguire la procedura seguente per iniziare:
  
1. Aprire il file PBIT.
    
2. Immettere il valore dell'ID tenant nella finestra di dialogo.
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Immettere le credenziali di amministratore per l'autenticazione in Microsoft 365 quando richiesto.
    
     per altre informazioni sugli utenti autorizzati ad accedere ai report di analisi dell'utilizzo di Microsoft 365. 
    
    Una volta ottenuta l'autorizzazione, i dati verranno aggiornati nel file di Power BI.
    
    Il caricamento dei dati può richiedere del tempo, ma al termine è possibile salvare il file PBIX e continuare a personalizzare i report o importare un'origine dati aggiuntiva nel report.
    
4. Per comprendere come creare i report, pubblicarli nel servizio Power BI e condividerli con l'organizzazione, vedere [Introduzione a Power BI](https://go.microsoft.com/fwlink/?linkid=849802). Se si segue questo percorso per la personalizzazione e la condivisione potrebbero essere necessarie altre licenze di Power BI. Per altre informazioni vedere le [indicazioni sulle licenze](https://go.microsoft.com/fwlink/p/?linkid=849803). 
    

