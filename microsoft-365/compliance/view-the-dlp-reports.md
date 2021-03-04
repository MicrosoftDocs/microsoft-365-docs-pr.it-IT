---
title: Visualizzare i report di prevenzione della perdita di dati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Usare i report DLP in Office 365 per visualizzare il numero di corrispondenze, sostituzioni o falsi positivi dei criteri DLP e vedere se stanno andando verso l'alto o verso il basso nel tempo.
ms.openlocfilehash: eb281f4d912a9e21716d7f9859564a02f9c23401
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423829"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Visualizzare i report di prevenzione della perdita di dati

Dopo aver creato i criteri di prevenzione della perdita dei dati (DLP), è necessario verificare che funzionino come previsto e mantenere la conformità. Con i report DLP nel Centro sicurezza &amp; e conformità, è possibile visualizzare rapidamente:
  
- **Corrispondenze ai criteri DLP** Questo report mostra il conteggio delle corrispondenze dei criteri DLP nel tempo. È possibile filtrare il report in base a data, posizione, criterio o azione. È possibile utilizzare questo report per: 
    
  - Ottimizzare o perfezionare i criteri DLP durante l'esecuzione in modalità test. È possibile visualizzare la regola specifica corrispondente al contenuto.
    
  - Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.
    
  - Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.
    
  - Comprendere l'impatto aziendale dei criteri DLP per vedere quali azioni vengono applicate al contenuto.
    
  - Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.
    
  - Visualizzare un elenco degli utenti principali e ripetere gli utenti che contribuiscono a eventi imprevisti nell'organizzazione.
    
  - Visualizzare un elenco dei principali tipi di informazioni riservate nell'organizzazione.
    
- **Eventi imprevisti dlp** Questo report mostra anche le corrispondenze dei criteri nel tempo, come il report corrispondenze dei criteri. Tuttavia, il rapporto corrispondenze dei criteri mostra le corrispondenze a livello di regola; Ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto corrispondenze dei criteri mostra tre voci diverse. Al contrario, il report degli eventi imprevisti mostra le corrispondenze a livello di elemento; Ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il report degli eventi imprevisti mostra una singola voce per tale parte di contenuto. 
    
  Poiché i conteggi dei report vengono aggregati in modo diverso, il rapporto corrispondenze dei criteri è migliore per identificare le corrispondenze con regole specifiche e ottimizzare i criteri DLP. Il rapporto operazioni non consentite è migliore per identificare parti specifiche di contenuto problematico per i criteri DLP.
    
- **Falsi positivi e sostituzioni DLP** Se il criterio DLP consente agli utenti di ignorarlo o segnalare un falso positivo, questo report mostra un conteggio di tali istanze nel tempo. È possibile filtrare il report in base a data, posizione o criterio. È possibile utilizzare questo report per: 
    
  - Ottimizzare o perfezionare i criteri DLP per vedere quali criteri comportano un numero elevato di falsi positivi.
    
  - Visualizzare le giustificazioni inviate dagli utenti quando risolvono un suggerimento per i criteri ignorando il criterio.
    
  - Individuare i casi in cui i criteri DLP sono in conflitto con i processi aziendali validi in caso di un numero elevato di sostituzioni utente.
    
Tutti i report DLP possono mostrare i dati del periodo di quattro mesi più recente. La visualizzazione dei dati più recenti nei report può richiedere fino a 24 ore.
  
Questi report sono disponibili nel dashboard dei report &amp; del Centro sicurezza e \>  \> **conformità.**
  
![Report corrispondenze dei criteri DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Visualizzare la giustificazione inviata da un utente per una sostituzione

Se il criterio DLP consente agli utenti di ignorarlo, è possibile utilizzare il rapporto falsi positivi e override per visualizzare il testo inviato dagli utenti nel suggerimento per i criteri.
  
![Campo Giustificazione nei dettagli del report di falsi positivi e override dlp](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Eseguire azioni su informazioni dettagliate e suggerimenti

I report possono mostrare informazioni dettagliate e suggerimenti in cui è possibile fare clic sull'icona di avviso rossa per visualizzare i dettagli sui potenziali problemi e intraprendere possibili azioni correttive.
  
![Fare clic sull'icona di informazioni dettagliate per visualizzare i dettagli e le azioni da eseguire](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Autorizzazioni per i report DLP

Per visualizzare i report DLP nel Centro sicurezza & conformità, è necessario disporre delle autorizzazioni seguenti:

- **Ruolo Lettore** di sicurezza nell'interfaccia di amministrazione di Exchange. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Lettore sicurezza nell'interfaccia di amministrazione di Exchange.

- **Ruolo Gestione conformità DLP di sola** visualizzazione nel Centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Amministratore conformità, Gestione organizzazione, Amministratore sicurezza e Lettore sicurezza nel Centro sicurezza & conformità.

- **Ruolo Destinatari di sola** visualizzazione nell'interfaccia di amministrazione di Exchange. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità, Gestione organizzazione e View-Only Gestione organizzazione nell'interfaccia di amministrazione di Exchange.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Trovare i cmdlet per i report DLP

Per usare la maggior parte dei cmdlet per il Centro sicurezza e conformità, è necessario:
  
1. [Connettersi al Centro &amp; sicurezza e conformità tramite Remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. Utilizzare uno di questi [cmdlet del Centro sicurezza e &amp; conformità](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
I report dei criteri di prevenzione della perdita dei dati devono tuttavia estrarre i dati da Office 365, incluso Exchange Online. Per questo motivo, i cmdlet per i report DLP sono disponibili in PowerShell di Exchange Online e non in PowerShell per Centro sicurezza &amp; e conformità. Per usare i cmdlet per i report dei criteri di prevenzione della perdita dei dati, è quindi necessario:
  
1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Usare uno di questi cmdlet per i report dei criteri di prevenzione della perdita dei dati:
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

