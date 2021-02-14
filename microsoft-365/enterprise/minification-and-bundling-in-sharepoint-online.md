---
title: Minimizzazione e creazione di bundle in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Informazioni su come usare tecniche di minificazione e creazione di aggregazione con Web Essentials per ridurre le richieste HTTP e il tempo necessario per caricare le pagine in SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690991"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Minimizzazione e creazione di bundle in SharePoint Online

In questo articolo viene descritto come utilizzare tecniche di minificazione e creazione di aggregazione con Web Essentials per ridurre il numero di richieste HTTP e ridurre il tempo necessario per caricare le pagine in SharePoint Online.
  
Quando si personalizza il sito Web è possibile aggiungere un numero elevato di file aggiuntivi al server per supportare la personalizzazione. L'aggiunta di ulteriori immagini, CSS e JavaScript aumenta il numero di richieste HTTP al server che a sua volta aumenta il tempo necessario per visualizzare una pagina Web. Se si dispone di più file dello stesso tipo, è possibile creare dei bundle di questi file per accelerarne il download.
  
Per i file JavaScript e CSS, puoi anche usare un approccio denominato minificazione, in cui puoi ridurre le dimensioni totali dei file rimuovendo gli spazi vuoti e altri caratteri non necessari.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Minimizzazione e creazione di bundle di file JavaScript e CSS tramite Web Essentials

È possibile utilizzare software di terze parti, ad esempio Web Essentials, per raggruppare i file CSS e JavaScript.
  
> [!IMPORTANT]
> Web Essentials è un progetto di terze parti, open source e basato sulla community. Il software è un'estensione di Visual Studio 2012 e Visual Studio 2013 e non è supportato da Microsoft. Per scaricare Web Essentials, visitare il sito Web all'indirizzo [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
Web Essentials offre due forme di creazione di bundle:
  
- .bundle: per i file CSS e JavaScript
    
- .sprite: per le immagini (disponibile solo in Visual Studio 2013)
    
È possibile utilizzare Web Essentials se si dispone di una funzionalità esistente con alcuni elementi di personalizzazione cui viene fatto riferimento all'interno di una pagina master personalizzata, ad esempio:
  
![Schermata dell'elemento del marchio nella pagina master personalizzata](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Per creare un bundle TE000127218 e CSS in Web Essentials**
  
1. In Visual Studio, in Esplora risorse selezionare i file che si desidera includere nel bundle.
    
2. Fai clic con il pulsante destro del mouse sui file selezionati e quindi scegli **Web Essentials** \> **Create JavaScript bundle file** dal menu di scelta rapida. Ad esempio: 
    
    ![Schermata che mostra le opzioni del menu di Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Visualizzazione dei risultati della creazione di bundle di file JavaScript e CSS

Quando si crea un bundle di JavaScript e CSS, Web Essentials crea un file XML, denominato file recipe, che identifica i file JavaScript e CSS nonché altre informazioni sulla configurazione: 
  
![Schermata di file recipe JavaScript e CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Inoltre, se il flag minify è impostato su true nei file recipe aggregati, i file vengono ridimensionati e collegati tra loro. Ciò significa che le nuove versioni minimizzate dei file JavaScript sono state create ed è possibile farvi riferimento nella pagina master.
  
![Schermata del flag minify impostato su true](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Quando si carica una pagina dal sito Web, è possibile utilizzare gli strumenti di sviluppo dal browser, come Internet Explorer 11, per visualizzare il numero di richieste inviate al server e il tempo impiegato da ciascun file per il caricamento.
  
La figura seguente mostra il risultato del caricamento di file JavaScript e CSS prima della minimizzazione.
  
![Schermata che mostra il download di 80 elementi](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
In seguito all'aggregazione dei file CSS e JavaScript, il numero di richieste viene interrotto a 74 e ogni file impiega un tempo leggermente più lungo dei file originali per ogni singolo download:
  
![Schermata che mostra il download di 74 elementi](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Dopo l'aggregazione, il file di bundle JavaScript viene ridotto in modo significativo da 815 KB a 365 KB:
  
![Schermata che mostra dimensioni di download ridotte](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Aggregazione di immagini tramite la creazione di un'immagine sprite

Analogamente all'aggregazione di file CSS e JavaScript, è possibile combinare molte piccole icone e altre immagini comuni in un foglio sprite più grande e quindi utilizzare CSS per visualizzare le singole immagini. Invece di scaricare ogni singola immagine, il Web browser dell'utente scarica il foglio sprite una sola volta e quindi lo memorizza nella cache del computer locale. Ciò migliora le prestazioni di caricamento della pagina riducendo il numero di download e sequenze di andata e ritorno al server Web.
  
 **Per creare un'immagine sprite in Web Essentials**
  
1. In Visual Studio, in Esplora risorse selezionare i file che si desidera includere nel bundle.
    
2. Fai clic con il pulsante destro del mouse sui file selezionati e quindi scegli **Web Essentials** \> **Create image sprite** dal menu di scelta rapida. Ad esempio: 
    
    ![Schermata che illustra come creare un'immagine sprite](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Selezionare il percorso in cui salvare il file sprite. Il file .sprite è un file XML che descrive le impostazioni e i file nello sprite. Le figure seguenti mostrano un esempio di file PNG sprite e il file XML .sprite corrispondente.
    
    ![Schermata di un file sprite](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Schermata del file XML sprite](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

