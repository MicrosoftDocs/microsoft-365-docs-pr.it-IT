---
title: 'Interfaccia di amministrazione di Exchange in Exchange Online Protection '
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: L'Interfaccia di amministrazione di Exchange (EAC) è la console di gestione basata sul Web per Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: a32302c8f18502453ff8cd57f9fc11cc2be4d9e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083527"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Interfaccia di amministrazione di Exchange in Exchange Online Protection 

L'Interfaccia di amministrazione di Exchange (EAC) è la console di gestione basata sul Web per Microsoft Exchange Online Protection (EOP). 
  
Per informazioni sulla versione di Exchange 2013 in questo argomento, vedere [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).
  
Per informazioni sulla versione di Exchange Online in questo argomento, vedere [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).
  
## <a name="accessing-the-eac"></a>Accesso a EAC

Nella maggior parte dei casi, i clienti di EOP accederanno a EAC tramite l'interfaccia di amministrazione di Microsoft 365. È possibile trovare un collegamento a EOP nel menu a discesa nel riquadro **Amministratore**, accanto al riquadro **Io**. Fare clic sul riquadro **Amministratore** e selezionare **Exchange Online Protection** dal menu a discesa per l'esecuzione in EAC. 
  
You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.
  
## <a name="common-user-interface-elements-in-the-eac"></a>Elementi comuni dell'interfaccia utente in EAC

In questa sezione vengono illustrati gli elementi dell'interfaccia utente disponibili in EAC.
  
![EOP-AdminCenter](../media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a>Riquadro delle funzionalità

È il primo livello di esplorazione per la maggior parte delle attività da eseguire in EAC. Il riquadro delle funzionalità è organizzato in aree funzionali.
  
1. **Destinatari** Consente di visualizzare gli utenti interni e i contatti esterni. 
    
2. **Autorizzazioni** Consente di gestire i ruoli di amministratore. 
    
3. **Gestione della conformità** Consente di individuare i registri di controllo e i rapporti, ad esempio il rapporto di un gruppo di ruoli amministratore. 
    
4. **Protezione** Consente di gestire la protezione anti-malware e dalla posta indesiderata per l'organizzazione e consente di gestire i messaggi in quarantena. 
    
5. **Flusso di posta** Consente di gestire regole, domini accettati e connettori e di eseguire l'analisi dei messaggi. 
    
### <a name="tabs"></a>Schede

Le schede rappresentano il secondo livello di esplorazione. Ciascuna area funzionale contiene varie schede, ognuna delle quali rappresenta una funzionalità.
  
### <a name="toolbar"></a>Barra degli strumenti

La selezione della maggior parte delle schede consente di visualizzare una barra degli strumenti. che include icone che eseguono un'azione specifica. Nella tabella seguente sono descritte le icone e le loro azioni.
  
|**Icona**|**Nome**|**Azione**|
|:-----|:-----|:-----|
|![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif)           <br/> |Aggiungi, Nuovo  <br/> |Utilizzare questa icona per creare un nuovo oggetto. Ad alcune icone è associata una freccia in giù sulla quale si può fare clic per mostrare ulteriori oggetti da creare.  <br/> |
|![Icona Modifica](../media/ITPro-EAC-EditIcon.gif)           <br/> |Modifica  <br/> |Utilizzare questa icona per modificare un oggetto.  <br/> |
|![Icona Elimina](../media/ITPro-EAC-DeleteIcon.gif)           <br/> |Elimina  <br/> |Utilizzare questa icona per eliminare un oggetto. Ad alcune icone Elimina è associata una freccia in giù su cui si può fare clic per mostrare altre opzioni.  <br/> |
|![icona Cerca](../media/ITPro-EAC-.gif)           <br/> |Cerca  <br/> |Utilizzare questa icona per aprire una casella di ricerca in cui digitare la frase di ricerca per l'oggetto che si desidera trovare.  <br/> |
|![Icona Aggiorna](../media/ITPro-EAC-RefreshIcon.gif)           <br/> |Aggiorna  <br/> |Utilizzare questa icona per aggiornare la visualizzazione elenco.  <br/> |
|![Icona Ulteriori opzioni](../media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |Altre opzioni  <br/> |Utilizzare questa icona per visualizzare le altre azioni da eseguire per gli oggetti della scheda. Ad esempio in **Destinatari \> Utenti**, facendo clic sull'icona, viene visualizzata l'opzione per eseguire una **Ricerca avanzata**.  <br/> |
|![Icona Freccia in su](../media/ITPro-EAC-UpArrowIcon.gif)![Icona Freccia in giù](../media/ITPro-EAC-DownArrowIcon.gif)           <br/> |Freccia su e freccia giù  <br/> |Utilizzare queste icone per spostare la priorità di un oggetto verso l'alto o verso il basso.  <br/> |
|![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.gif)           <br/> |Rimuovi  <br/> |Questa icona consente di rimuovere gli oggetti da un elenco.  <br/> |
   
### <a name="list-view"></a>Visualizzazione elenco

Selezionando una scheda, nella maggior parte dei casi viene attivata una visualizzazione elenco. Il limite visualizzabile con l'elenco EAC è di circa 10.000 oggetti. È inoltre inclusa la funzione di paging che consente di scorrere fino ai risultati.
  
### <a name="details-pane"></a>Riquadro dei dettagli

Quando si seleziona un oggetto dalla visualizzazione elenco, nel riquadro dei dettagli vengono visualizzate le informazioni relative all'oggetto in questione. In alcuni casi il riquadro dei dettagli include attività di gestione.
  
### <a name="me-tile-and-help"></a>Riquadro Io e Guida

Il riquadro **Io** consente di disconnettersi da EAC e accedere come altro utente. Dal menu a discesa **Guida**![Icona Guida](../media/ITPro-EAC-HelpIcon.gif), è possibile eseguire le seguenti operazioni: 
  
1. **Guida** Fare clic su ![Icona Guida](../media/ITPro-EAC-HelpIcon.gif) per visualizzare il contenuto della Guida. 
    
2. **Disabilita finestra della Guida** La finestra della Guida visualizza una guida contestuale per i campi relativi alla creazione o alla modifica di un oggetto. È possibile disabilitare la finestra della Guida o riattivarla se era stata disabilitata. 
    
3. **Copyright** Fare clic su questo collegamento per leggere le informazioni sul copyright per Exchange Online Protection. 
    
4. **Privacy** Fare clic per leggere l'informativa sulla privacy per Exchange Online Protection. 
    
## <a name="supported-browsers"></a>Browser supportati

Per la migliore esperienza nell'utilizzo di EAC, si consiglia di utilizzare sempre i browser più recenti, i client e le app di Office. Si consiglia inoltre di installare gli aggiornamenti software quando disponibili. Per ulteriori informazioni sui browser supportati e requisiti di sistema per il servizio, vedere [Requisiti di sistema per Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699). 
  
## <a name="supported-languages-in-eop"></a>Lingue supportate in EOP

Per Exchange Online Protection sono disponibili e supportate le seguenti lingue server:
  
- Amharico
    
- Arabo
    
- Basco (Province basche)
    
- Bengali (India)
    
- Bulgaro
    
- Catalano
    
- Cinese (semplificato)
    
- Cinese (tradizionale)
    
- Croato
    
- Ceco
    
- Danese
    
- Olandese
    
- Olandese
    
- Inglese
    
- Estone
    
- Filippino (Filippine)
    
- Finlandese
    
- Francese
    
- Gallego
    
- Tedesco
    
- Greco
    
- Gujarati
    
- Ebraico
    
- Hindi
    
- Ungherese
    
- Islandese
    
- Indonesiano
    
- Italiano
    
- Giapponese
    
- Kannada
    
- Kazaco
    
- Kiswahili
    
- Coreano
    
- Lettone
    
- Lituano
    
- Malese (Brunei Darussalam)
    
- Malese (Malesia)
    
- Malayalam
    
- Marathi
    
- Norvegese (Bokmål)
    
- Norvegese (Nynorsk)
    
- Oriya
    
- Persiano
    
- Polacco
    
- Portoghese (Brasile)
    
- Portoghese (Portogallo)
    
- Rumeno
    
- Russo
    
- Serbo (alfabeto cirillico)
    
- Serbo (alfabeto latino)
    
- Slovacco
    
- Sloveno
    
- Spagnolo
    
- Svedese
    
- Tamil
    
- Telugu
    
- Tailandese
    
- Turco
    
- Ucraino
    
- Urdu
    
- Vietnamita
    
- Gallese
    

