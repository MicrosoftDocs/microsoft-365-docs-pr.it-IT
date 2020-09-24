---
title: Funzionamento di Collegamenti sicuri ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La funzionalità collegamenti sicuri fornisce il tempo di fare clic sulla verifica dei link ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Leggere questo articolo per informazioni su come funzionano i collegamenti sicuri di ATP.
ms.openlocfilehash: e19d3a1f93d11cd9873e6b5fad9952b018e0a481
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245882"
---
# <a name="how-atp-safe-links-works"></a>Funzionamento di Collegamenti sicuri ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> Per il corretto funzionamento dei collegamenti sicuri di Office 365 ATP, tutti i servizi devono trovarsi nella stessa versione.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Funzionamento dei collegamenti sicuri di ATP con gli URL nella posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 con URL nel messaggio di posta elettronica

A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL nella posta elettronica (ospitati in Office 365, non in locale):
  
1. Gli utenti ricevono messaggi di posta elettronica, alcuni dei quali contengono URL.
    
2. Tutti i messaggi di posta elettronica passano attraverso Exchange Online Protection, dove vengono applicati i filtri Internet (IP) e busta, la protezione antimalware basata sulle firme, i filtri anti-spam e antivirus. 
    
3. La posta elettronica arriva nelle cassette postali degli utenti.
    
4. Un utente accede a Office 365 e passa alla posta in arrivo.
    
5. L'utente apre un messaggio di posta elettronica e fa clic su un URL nel messaggio di posta elettronica.
    
6. La caratteristica collegamenti sicuri ATP verifica immediatamente l'URL prima di aprire il sito Web. L'URL viene identificato come bloccato, dannoso o sicuro.
        
   - Se l'URL è incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-atp.md)dell'organizzazione, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
   - Se l'URL è associato a un sito Web che è stato determinato come dannoso, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
   - Se l'URL passa a un file scaricabile e i criteri per i [collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) dell'organizzazione sono configurati per l'analisi di tali contenuti, il file scaricabile viene controllato. 
    
   - Se l'URL è determinato per la sicurezza, il sito Web verrà aperto.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Funzionamento dei collegamenti sicuri di ATP con gli URL nei documenti di Office

A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL in Microsoft 365 Apps for Enterprise or Business Premium Applications (Current versions of Word, Excel e PowerPoint su Windows, Mac o in un browser, app di Office su dispositivi iOS o Android, Visio su Windows, OneNote in un browser):
  
1. Gli utenti hanno installato Microsoft 365 Apps for Enterprise o Business Premium nel computer, nello smartphone o nel tablet. (Oppure, utilizzano Office nel browser).
    
2. Un utente apre una parola, Excel, PowerPoint, OneNote (nel browser) o Visio (su desktop) e accede a Office 365 Enterprise utilizzando l'account aziendale o dell'Istituto di istruzione. Il documento contiene gli URL.
    
3. Quando l'utente fa clic su un URL del documento, il collegamento è controllato dal servizio collegamenti sicuri di ATP.
    
   - Se l'URL è associato a un sito Web incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-atp.md)dell'organizzazione, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
   - Se l'URL è associato a un sito Web che è stato determinato come dannoso, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
   - Se l'URL passa a un file scaricabile e i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) sono configurati per l'analisi di tali download, viene controllato il file scaricabile. 
    
   - Se l'URL è considerato sicuro, l'utente viene reindirizzato al sito Web.
      
   - Se il controllo URL ha esito negativo, la protezione dei collegamenti sicuri non verrà attivata. Nei client desktop, l'utente verrà avvisato prima di procedere al sito.
      
> [!NOTE]
> All'inizio di ogni sessione potrebbero essere necessari alcuni secondi per verificare che l'utente disponga di collegamenti sicuri di ATP per Office abilitato. 
      
