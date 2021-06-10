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
description: Utilizzare i report DLP in Office 365 per visualizzare il numero di corrispondenze, sostituzioni o falsi positivi dei criteri DLP e vedere se stanno andando verso l'alto o verso il basso nel tempo.
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928390"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Visualizzare i report di prevenzione della perdita di dati

Dopo aver creato i criteri di prevenzione della perdita dei dati (DLP), è necessario verificare che funzionino come previsto e per mantenere la conformità. Con i report DLP nel Centro &amp; sicurezza e conformità, è possibile visualizzare rapidamente:
  
- **Corrispondenze dei criteri DLP** Questo report mostra il conteggio delle corrispondenze dei criteri DLP nel tempo. È possibile filtrare i report per data, percorso, criterio o azione. È possibile usare questo report per: 
    
  - Ottimizzare o perfezionare i criteri di prevenzione della perdita dei dati durante la loro esecuzione in modalità test. È possibile visualizzare la regola specifica per la quale è stata trovata una corrispondenza al contenuto.
    
  - Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.
    
  - Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.
    
  - Comprendere ogni impatto aziendale dei criteri di prevenzione della perdita dei dati visualizzando quali azioni sono state applicate al contenuto.
    
  - Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.
    
  - Visualizzare un elenco degli utenti principali e ripetere gli utenti che contribuiscono agli incidenti dell'organizzazione.
    
  - Visualizzare un elenco dei principali tipi di informazioni riservate nell'organizzazione.
    
- **Eventi imprevisti DLP** Questo report mostra anche le corrispondenze dei criteri nel tempo, come il rapporto corrispondenze dei criteri. Tuttavia, il rapporto corrispondenze dei criteri mostra le corrispondenze a livello di regola. Ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto corrisponde ai criteri mostra tre voci diverse. Al contrario, il report degli eventi imprevisti mostra le corrispondenze a livello di elemento. Ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto eventi imprevisti mostra una singola riga per tale elemento di contenuto. 
    
  Poiché i conteggi dei report vengono aggregati in modo diverso, il rapporto corrispondenze dei criteri è migliore per identificare le corrispondenze con regole specifiche e ottimizzare i criteri DLP. Il report relativo agli incidenti è più utile per identificare i tipi di contenuto specifici che risultano essere problematici per i propri criteri di prevenzione della perdita dei dati.
    
- **Falsi positivi e sostituzioni DLP** Se il criterio DLP consente agli utenti di ignorarlo o segnalare un falso positivo, questo report mostra un conteggio di tali istanze nel tempo. È possibile filtrare i report per data, percorso o criterio. È possibile usare questo report per: 
    
  - Ottimizzare o perfezionare i criteri di prevenzione della perdita dei dati rilevando i criteri che causano un numero elevato di falsi positivi.
    
  - Visualizzare le giustificazioni inviate dagli utenti quando risolvono un suggerimento per i criteri ignorando il criterio.
    
  - Scoprire dove i criteri di prevenzione della perdita dei dati sono in conflitto con processi aziendali validi incorrendo in un numero elevato di override degli utenti.
    
Tutti i report di prevenzione della perdita dei dati possono mostrare i dati relativi a un periodo di tempo di quattro mesi precedenti. I dati più recenti possono richiedere fino a 24 ore per essere visualizzati nei report.
  
Questi report sono disponibili nel dashboard dei report del Centro sicurezza e &amp; \>  \> **conformità.**
  
![Report corrispondenze criteri DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Visualizzare la giustificazione inviata da un utente per una sostituzione

Se i criteri di prevenzione della perdita dei dati dell'organizzazione consentono agli utenti di ignorarli, è possibile utilizzare il report sui criteri falsi positivi e ignorati per visualizzare il testo inviato dagli utenti nei suggerimenti per i criteri.
  
![Campo Giustificazione nei dettagli del report dlp falso positivo e sostituzione](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Eseguire azioni su informazioni dettagliate e suggerimenti

I report possono mostrare informazioni dettagliate e suggerimenti in cui è possibile fare clic sull'icona di avviso rossa per visualizzare i dettagli sui potenziali problemi e intraprendere possibili azioni correttive.
  
![Fare clic su un'icona informazioni dettagliate per visualizzare i dettagli e le azioni da eseguire](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Autorizzazioni per i report DLP

Per visualizzare i report DLP nel Centro sicurezza & conformità, è necessario disporre delle autorizzazioni seguenti:

- **Ruolo Lettore** di sicurezza nell'Exchange di amministrazione. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Lettore sicurezza nell'Exchange di amministrazione.

- **Ruolo Gestione conformità DLP di sola** visualizzazione nel Centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Amministratore conformità, Gestione organizzazione, Amministratore sicurezza e Lettore sicurezza nel Centro sicurezza & conformità.

- **Ruolo Destinatari di sola** visualizzazione nell'Exchange di amministrazione. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità, Gestione organizzazione e Gestione organizzazione View-Only nell'interfaccia Exchange di amministrazione.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Trovare i cmdlet per i report DLP

Per usare la maggior parte dei cmdlet per il Centro sicurezza e conformità, è necessario:
  
1. [Connessione al Centro sicurezza &amp; e conformità tramite PowerShell remoto](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. Utilizzare uno di questi [cmdlet del Centro sicurezza e &amp; conformità](/powershell/exchange/exchange-online-powershell)
    
I report dei criteri di prevenzione della perdita dei dati devono tuttavia estrarre i dati da Office 365, incluso Exchange Online. Per questo motivo, i cmdlet per i report DLP sono disponibili in Exchange Online PowerShell, non in PowerShell del Centro &amp; sicurezza e conformità. Per usare i cmdlet per i report dei criteri di prevenzione della perdita dei dati, è quindi necessario:
  
1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. Usare uno di questi cmdlet per i report dei criteri di prevenzione della perdita dei dati:
    
      - [Get-DlpDetectionsReport](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [Get-DlpDetailReport](/powershell/module/exchange/get-dlpdetailreport)
