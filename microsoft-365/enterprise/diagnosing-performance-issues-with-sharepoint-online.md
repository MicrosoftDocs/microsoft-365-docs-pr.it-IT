---
title: Diagnosi dei problemi delle prestazioni con SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: In questo articolo viene illustrato come è possibile diagnosticare problemi comuni con il sito di SharePoint Online utilizzando gli strumenti di sviluppo di Internet Explorer.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691182"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Diagnosi dei problemi delle prestazioni con SharePoint Online

In questo articolo viene illustrato come è possibile diagnosticare problemi comuni con il sito di SharePoint Online utilizzando gli strumenti di sviluppo di Internet Explorer.
  
Esistono tre modi per identificare che una pagina in un sito di SharePoint Online presenta di un problema di prestazioni con le personalizzazioni.
  
- Il network monitor della barra degli strumenti F12

- Confronto di una linea di base non personalizzata

- Metrica dell'intestazione delle risposte di SharePoint Online

In questo argomento viene descritto come utilizzare ciascuno di questi metodi per diagnosticare problemi di prestazioni. Dopo aver individuato la causa del problema, è possibile lavorare per una soluzione utilizzando gli articoli relativi al miglioramento delle prestazioni di SharePoint che è possibile trovare su https://aka.ms/tune .
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>Utilizzo della barra degli strumenti F12 per diagnosticare le prestazioni in SharePoint Online
<a name="F12ToolInfo"> </a>

In questo articolo si utilizza Internet Explorer 11. Le versioni degli strumenti di sviluppo F12 su altri browser dispongono di caratteristiche simili, anche se potrebbero apparire leggermente diversi. Per informazioni sugli strumenti di sviluppo F12, vedere:
  
- [Novità degli strumenti F12](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [Utilizzo degli strumenti di sviluppo F12](https://go.microsoft.com/fwlink/p/?LinkId=522546)

Per visualizzare gli strumenti di sviluppo premere **F12**, quindi fare clic sull'icona Wi-Fi:
  
![Schermata dell'icona Wi-Fi di Strumenti di sviluppo F12](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
Nella scheda **Rete**, premere il pulsante verde di riproduzione per caricare la pagina. Lo strumento restituisce tutti i file che il browser richiede per ottenere la pagina richiesta dall'utente. La schermata seguente mostra un elenco di questo tipo.
  
![Schermata dell'elenco di file restituito con una richiesta di pagina.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
È inoltre possibile visualizzare i tempi di download dei file sul lato destro, come illustrato in questa schermata.
  
![Diagramma che mostra il tempo necessario per il caricamento delle pagine richieste da SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
In questo modo, si ottiene una rappresentazione visiva del tempo impiegato per caricare il file. La linea verde segnala quando la pagina è pronta per il rendering del browser. Ciò può fornire una visualizzazione rapida dei file diversi che possono rallentare i caricamenti delle pagine sul sito.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Impostazione di una linea di base non personalizzata per SharePoint Online
<a name="F12ToolInfo"> </a>

Il modo migliore per determinare i punti deboli delle prestazioni del sito consiste nell'impostare una raccolta siti completamente fuori dalla casella in SharePoint Online. In questo modo è possibile confrontare tutti i vari aspetti del proprio sito con quello che si otterrebbe senza nessuna personalizzazione della pagina. L'home page di OneDrive for Business è un buon esempio di una raccolta siti separata che di solito non dispone di personalizzazioni.
  
## <a name="viewing-sharepoint-response-header-information"></a>Visualizzazione delle informazioni di intestazione della risposta di SharePoint
<a name="F12ToolInfo"> </a>

In SharePoint Online, è possibile accedere alle informazioni restituite al browser nell'intestazione della risposta per ogni file. Il valore più utile per la diagnosi dei problemi di prestazioni è **SPRequestDuration**, che consente di visualizzare l'intervallo di tempo in cui la richiesta ha eseguito il server per l'elaborazione. Ciò consente di determinare se la richiesta è molto pesante e richiede un utilizzo intensivo delle risorse. Questa è la migliore conoscenza disponibile relativa all'attività del server per visualizzare la pagina.

### <a name="to-view-sharepoint-response-header-information"></a>Per visualizzare le informazioni di intestazione della risposta di SharePoint
  
1. Verificare di avere installato gli strumenti F12. Per ulteriori informazioni sul download e sull'installazione di questi strumenti, vedere [What ' s New in F12 Tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).

2. Negli strumenti F12,nella scheda **Rete**, premere il pulsante verde di riproduzione per caricare la pagina.

3. Fare clic sui file .aspx restituiti dagli strumenti, quindi fare clic su **DETTAGLI**.

    ![Mostra i dettagli dell'intestazione della risposta](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Fare clic su **Intestazioni di risposta**.

    ![Diagramma che mostra l'URL dell'intestazione della risposta](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>Qual è la causa dei problemi delle prestazioni in SharePoint Online?
<a name="F12ToolInfo"> </a>

Nell'articolo [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) viene illustrato un esempio dell'utilizzo del valore SPRequestDuration per determinare che la navigazione strutturale complicata causava che la pagina richiedeva molto tempo per l'elaborazione sul server. Adottando un valore per un sito di base (senza personalizzazione), è possibile determinare se un determinato file richieda molto tempo per il caricamento. Nell'esempio utilizzato in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) è il file .aspx principale. Tale file contiene la maggior parte del codice ASP.NET che viene eseguito per il caricamento della pagina. A seconda del modello di sito utilizzato, potrebbe trattarsi di start.aspx, home.aspx, default.aspx o di un altro nome se si personalizza la home page. Se questo numero è notevolmente superiore al sito di base, è molto probabile che sia in corso qualcosa di complesso nella pagina che causa problemi delle prestazioni.
  
Dopo aver chiarito che si tratta di un problema specifico del sito, il metodo consigliato per individuare la causa della riduzione delle prestazioni è l'eliminazione di tutte le possibili cause, come le personalizzazioni della pagina, per poi riaggiungerle al sito una alla volta. Dopo aver rimosso sufficienti personalizzazioni soddisfacenti della pagina, sarà quindi possibile riaggiungere le personalizzazioni specifiche una alla volta.
  
Ad esempio, se si dispone di una struttura di spostamento molto complessa provare a modificare tale struttura per non visualizzare siti secondari, quindi controllare gli strumenti di sviluppo per vedere se ci sono differenze. In alternativa, se si dispone di una grande quantità di contenuti di aggiornamenti cumulativi provare a rimuoverli dalla pagina e vedere se si ottengono miglioramenti. Se si eliminano tutte le possibili cause e si aggiungono nuovamente una alla volta, è possibile identificare facilmente quali funzionalità sono il problema principale, per poi lavorare a una soluzione.
