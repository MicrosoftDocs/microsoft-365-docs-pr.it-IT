---
title: Personalizzare il tema di Office 365 per l'organizzazione
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
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
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: "Informazioni su come modificare il tema predefinito di Office 365 e personalizzarlo in modo che corrisponda al logo o al colore dell'azienda. "
ms.openlocfilehash: 9d83abb919cfb9f6ea3c804d9c5d934614f35285
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42360637"
---
# <a name="customize-the-office-365-theme-for-your-organization"></a>Personalizzare il tema di Office 365 per l'organizzazione

Informazioni su come personalizzare il tema nell'interfaccia di amministrazione di Microsoft 365. In qualità di amministratore dell'abbonamento a Office 365 per le aziende, è possibile cambiare il tema predefinito visualizzato nella barra di spostamento superiore per tutti gli utenti dell'organizzazione. È possibile aggiungere il logo dell'azienda e modificare i colori in modo che corrispondano al resto del brand. È anche possibile aggiungere un collegamento di destinazione per gli utenti a cui passare quando selezionano il logo. È possibile visualizzare qui il tema predefinito e il risultato del tema personalizzato in Office 365.
  
![Tema predefinito di Office 365 e Theme Office 365 personalizzato](../../media/e2cbc922-b424-4683-8c5c-fdbcbd0ce844.png)
  
## <a name="customize-your-theme-in-the-admin-center"></a>Personalizzare il tema nell'interfaccia di amministrazione

1. Nell'interfaccia di amministrazione passare **alle impostazioni**delle **Impostazioni** \> e quindi scegliere la scheda **profilo organizzazione** .

2. Nella scheda **profilo organizzazione** scegliere **temi personalizzati**.

3. Nel riquadro **temi doganali** modificare gli elementi del tema desiderati per l'organizzazione:
    
  - **Utilizzare un'immagine personalizzata del logo**: scegliere se utilizzare un'immagine da un URL o caricare un'immagine. Se si utilizza un URL, assicurarsi che l'URL utilizzi HTTPS e che sia 200 x 30 pixel di qualsiasi formato di qualsiasi dimensione. È possibile caricare un logo inferiore a 10 KB che è 200 x 30 pixel in formato JPG, PNG, GIF o SVG.

    > [!NOTE]
    > Affinché il logo venga visualizzato nell'app per dispositivi mobili di SharePoint, utilizzare solo immagini SVG. Le immagini caricate in qualsiasi altro formato non vengono visualizzate nell'app. I loghi non possono essere cliccabili nell'app per dispositivi mobili di SharePoint.
    
  - **Fare clic su logo**: è possibile utilizzare il logo nella barra di spostamento come collegamento a qualsiasi risorsa dell'azienda. È possibile immettere l'URL per il logo qui, iniziando con http://o https://. Passaggio facoltativo.
    
  - **Selezionare immagine di sfondo**: selezionare l'immagine e caricare il proprio jpg, PNG o gif con una risoluzione di 1366 x 50 pixel, non superiore a 15 KB. L'immagine di sfondo viene visualizzata nella barra di spostamento superiore di ogni pagina.
    
    > [!NOTE]
    > Le immagini che contengono testo potrebbero non essere visualizzate come previsto. Gli elementi incorporati che vengono visualizzati a sinistra e a destra della barra di spostamento possono variare in base ai servizi e il testo può essere nascosto da questi elementi. A causa della natura dinamica della barra di spostamento, al momento non è possibile fornire indicazioni per la spaziatura interna immagine per ottenere un’esperienza coerente. 
    
  - **Colore barra di spostamento**: selezionare un colore da usare per lo sfondo della barra di spostamento. Viene visualizzato nella parte superiore di ogni pagina.
    
  - **Testo e icone**: Selezionare un colore da usare per il testo e le icone sulla barra di spostamento superiore.
    
  - **Colore accento**: selezionare un colore da usare per il pulsante della barra di spostamento e gli accenti di pagina come pulsanti e testo su determinate applicazioni.

   - **Impedire agli utenti di eseguire l'override di Theme**: capovolgere questo interruttore per impedire agli utenti di scegliere il proprio tema dalla selezione del tema. Questo non impedisce agli utenti di essere in grado di impostare un tema a contrasto elevato.
      
  - **Visualizza il nome utente**: scegliere se mostrare il nome completo di un utente al punto di ingresso per l'account Manager nell'angolo in alto a destra della pagina quando l'utente ha eseguito l'accesso. Per impostazione predefinita, gli utenti visualizzeranno la foto o le iniziali se una foto non è stata caricata.
    
4. Selezionare **Salva modifiche**.
    
Il nuovo tema verrà visualizzato immediatamente nell'interfaccia di amministrazione e dopo un breve periodo di tempo, verrà visualizzato in tutta la pagina di Office 365, incluse le pagine di Outlook e di SharePoint. È possibile rimuovere l'icona o i colori personalizzati in qualsiasi momento. Basta tornare alla pagina del tema e selezionare **Rimuovi tema personalizzato**.
  
## <a name="best-practices"></a>Procedure consigliate

Quando si sceglie un' **immagine del logo**, è consigliabile utilizzare un tipo di file SVG, laddove possibile, in modo che il logo abbia un aspetto ad alta risoluzione su tutti gli schermi e su tutti i livelli di zoom.

Quando si scelgono colori personalizzati, scegliere un **colore di sfondo della barra** di spostamento con un rapporto di contrasto elevato con l'immagine del **logo** selezionata. Scegliere anche un colore del **testo e delle icone** con un rapporto di contrasto elevato rispetto al **colore di sfondo della barra** di spostamento per garantire che tutto il testo e le icone siano facilmente visibili.

Quando si scelgono colori personalizzati, scegliere un **colore di accento** che si ripresenta bene su uno sfondo bianco o chiaro. Il **colore dell'accento** viene utilizzato per colorare alcuni collegamenti e pulsanti visualizzati su uno sfondo bianco o chiaro. Ad esempio, il **colore dell'accento** viene utilizzato per colorare gli elementi nella cartella posta in arrivo di un utente e nella relativa pagina del portale di Office.com. 
  
Il rapporto di contrasto consigliato tra testo, icona o colore del pulsante e il colore di sfondo è 4,5:1.

Di seguito è illustrato un semplice diagramma di flusso che consente di ottenere rapidamente una configurazione con un tema personalizzato di Office 365 visivamente accattivante per l'organizzazione:
  - Si desidera utilizzare una versione colorata del logo.
    - Si consiglia di eseguire le seguenti impostazioni:
      - **Immagine del logo**: logo colorato dell'organizzazione.
      - **Colore barra di spostamento**: un colore neutro. È consigliabile #FAF9F7 per un colore chiaro e #252423 per un colore scuro.
      - **Colore del testo e dell'icona**: un colore per contrastare il **colore della barra di spostamento**. È consigliabile #FAF9F7 per un colore chiaro e #252423 per un colore scuro.
      - **Colore accento**: colore del marchio scuro. Con alcune applicazioni, questo colore deve essere visibile su uno sfondo chiaro.
  - Vorrei utilizzare una versione neutrale del logo e rappresentare il colore nella barra di spostamento.
    - Si consiglia di eseguire le seguenti impostazioni:
      - **Immagine del logo**: logo neutro dell'organizzazione.
      - **Colore della barra di spostamento**: un colore del marchio che contrasta con il logo.
      - **Colore del testo e dell'icona**: scegliere un colore che contrasta con il colore del marchio scelto per il **colore della barra di spostamento**. È consigliabile #252423 per un colore scuro e #FAF9F7 per un colore chiaro.
      - **Colore accento**: colore del marchio scuro. Con alcune applicazioni, questo colore deve essere visibile su uno sfondo chiaro.
  
## <a name="related-articles"></a>Articoli correlati

[Aggiungere riquadri personalizzati alla pagina Mie app e all'icona di avvio delle app](../manage/customize-the-app-launcher.md)
  
  

