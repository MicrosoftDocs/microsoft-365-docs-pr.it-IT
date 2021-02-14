---
title: Ritardo caricamento immagini e JavaScript in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
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
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: Informazioni su come ridurre il tempo di caricamento per le pagine di SharePoint Online utilizzando JavaScript per ritardare il caricamento di immagini e JavaScript non essenziali.
ms.openlocfilehash: ee86ae0813c11fbfd836d7d38ea124c1e3f277d0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691323"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Ritardo caricamento immagini e JavaScript in SharePoint Online

In questo articolo viene descritto come è possibile ridurre il tempo di caricamento per le pagine di SharePoint Online utilizzando JavaScript per ritardare il caricamento delle immagini e anche attendendo di caricare JavaScript non essenziale fino al caricamento della pagina.
  
Le immagini possono influenzare negativamente la velocità di caricamento della pagina in SharePoint Online. Per impostazione predefinita, i browser Internet più moderni pre-recuperano immagini durante il caricamento di una pagina HTML. Ciò può far sì che la pagina si carichi lentamente senza motivo se le immagini non sono visibili sullo schermo fino a quando l'utente scorre verso il basso. Le immagini possono impedire al browser di caricare la parte visibile della pagina. Per risolvere questo problema, è possibile utilizzare JavaScript per ignorare prima il caricamento delle immagini. Inoltre, il caricamento di JavaScript non essenziale può rallentare i tempi di download anche nelle pagine di SharePoint. In questo argomento vengono descritti alcuni metodi utilizzabili per migliorare i tempi di caricamento delle pagine con JavaScript in SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Migliorare i tempi di caricamento delle immagini nelle pagine caricando le pagine di SharePoint Online tramite JavaScript

È possibile utilizzare JavaScript per impedire a un browser Web di pre-recuperare le immagini. Ciò consente di velocizzare il rendering complessivo del documento. A tale scopo, rimuovere il valore dell'attributo src dal tag e sostituirlo con il percorso di un file in un attributo di dati, ad \<img\> esempio: data-src. Ad esempio:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Utilizzando questo metodo, il browser non scarica immediatamente le immagini. Se l'immagine è già nel riquadro di visualizzazione, JavaScript indica al browser di recuperare l'URL dall'attributo dati e di inserirlo come valore per l'attributo src. L'immagine viene caricata solo quando l'utente scorre e arriva all'immagine.
  
Per fare in modo che tutto ciò accada, dovrai usare JavaScript.
  
In un file di testo, definire la funzione **isElementInViewport()** per controllare se un elemento fa o meno parte del browser visibile all'utente.
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

Utilizzare quindi **isElementInViewport()** nella funzione **loadItemsInView()**. La funzione **loadItemsInView()** caricherà tutte le immagini con un valore per l'attributo dati-src se fanno parte del browser visibile all'utente. Aggiungere la seguente funzione al file di testo:
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

Infine, chiamare **loadItemsInView()** da **window.onscroll()** come illustrato nell'esempio seguente. In questo modo tutte le immagini presenti nel riquadro di visualizzazione sono caricate quando ne ha bisogno l'utente, ma non prima. Aggiungere quanto segue al file di testo:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Per SharePoint Online, è necessario associare la funzione seguente all'evento scroll nel \<div\> tag #s4-workspace. Questo perché gli eventi della finestra vengono ignorati per garantire che la barra multifunzione rimanga collegata alla parte superiore della pagina.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Salvare il file di testo come un file JavaScript con estensione js, ad esempio delayLoadImages.js.
  
Dopo aver completato la scrittura delayLoadImages.js, è possibile aggiungere il contenuto del file a una pagina master in SharePoint Online. È possibile farlo aggiungendo un link di script all'intestazione nella pagina master. Una volta in una pagina master, JavaScript verrà applicato a tutte le pagine del sito di SharePoint Online che usano tale layout di pagina master. In alternativa, se si prevede di utilizzarlo solo in una pagina del sito, è possibile utilizzare l'editor di script Web Part per incorporare JavaScript nella pagina. Per ulteriori informazioni, vedere i seguenti argomenti:
  
- [Procedura: Applicare una pagina master a un sito in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [Procedura: Create a page layout in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Esempio: Fare riferimento al file JavaScript delayLoadImages.js da una pagina master in SharePoint Online
  
Affinché funzioni, è necessario fare riferimento a jQuery nella pagina master. Nell'esempio seguente, è possibile visualizzare il caricamento della pagina iniziale dove viene caricata solo un'immagine, ma ce ne sono molte altre nella pagina.
  
![Schermata che mostra un'immagine caricata nella pagina](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
Lo screenshot seguente mostra il resto delle immagini che vengono scaricate dopo lo scorrimento nella visualizzazione.
  
![Schermata che mostra varie immagini caricate nella pagina](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Ritardare il caricamento delle immagini tramite JavaScript può essere una tecnica efficace per aumentare le prestazioni. Tuttavia, se la tecnica viene applicata a un sito Web pubblico, allora i motori di ricerca non sono in grado di eseguire ricerche per indicizzazione delle immagini nello stesso modo in cui si farebbe una ricerca per indicizzazione di un'immagine regolarmente formata. Questo può influire sulla classificazione nei motori di ricerca perché i metadati dell'immagine stessa non sono realmente presenti fino a quando non viene caricata la pagina. I crawler dei motori di ricerca leggono solo il codice HTML e pertanto non vedranno le immagini come contenuto nella pagina. Le immagini sono uno dei fattori utilizzati per classificare le pagine nei risultati della ricerca. Un modo per risolvere il problema consiste nell'utilizzare testo introduttivo per le immagini.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Esempio di codice GitHub: inserimento di JavaScript per migliorare le prestazioni

Non perdere l'articolo e l'esempio di codice [sull'inserimento in JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) fornito su GitHub.
  
## <a name="see-also"></a>Vedere anche

[Browser supportati in Office 2013 e Microsoft 365 Apps for enterprise](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Procedura: Applicare una pagina master a un sito in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[Procedura: Create a page layout in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)
