---
title: Visualizzare i report di prevenzione della perdita di dati
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
description: Con i report DLP in Office 365, è possibile visualizzare rapidamente il numero di corrispondenze di criteri DLP, sostituzioni o falsi positivi. controllare se si sta facendo una tendenza verso l'alto o verso il basso nel tempo; filtrare il report in modi diversi; e visualizzare ulteriori dettagli selezionando un punto su una linea del grafico.
ms.openlocfilehash: f3161854a19f9f9a04390eec508ae43e92119f96
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084255"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Visualizzare i report di prevenzione della perdita di dati

Dopo aver creato i criteri di prevenzione della perdita di dati (DLP), è necessario verificare che funzionino come previsto e che vi aiuti a rimanere conformi. Con i report DLP nel centro sicurezza &amp; e conformità di Office 365, è possibile visualizzare rapidamente:
  
- **Corrispondenze di criteri DLP** Questo rapporto Visualizza il numero di corrispondenze di criteri DLP nel tempo. È possibile filtrare il report per data, percorso, criterio o azione. È possibile utilizzare questo report per: 
    
  - Ottimizzare o affinare i criteri DLP quando vengono eseguiti in modalità test. È possibile visualizzare la regola specifica corrispondente al contenuto.
    
  - Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.
    
  - Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.
    
  - Comprendere qualsiasi impatto aziendale dei criteri DLP vedendo quali azioni vengono applicate al contenuto.
    
  - Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.
    
  - Consente di visualizzare un elenco di utenti principali e di ripetere gli utenti che contribuiscono a incidenti nell'organizzazione.
    
  - Visualizzare un elenco dei tipi principali di informazioni riservate nell'organizzazione.
    
- **Incidenti DLP** Questo rapporto Visualizza anche le corrispondenze di criteri nel tempo, come il rapporto criteri di corrispondenza. Tuttavia, il rapporto dei criteri corrisponde alle corrispondenze a livello di regola; ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto criteri corrisponde a tre diversi elementi pubblicitari. Al contrario, il rapporto sugli incidenti Visualizza le corrispondenze a livello di elemento. ad esempio, se un messaggio di posta elettronica corrisponde a tre regole diverse, il rapporto eventi non consentiti Visualizza un singolo elemento di riga per il contenuto. 
    
  Poiché i conteggi dei rapporti vengono aggregati in modo diverso, il rapporto criteri di ricerca è migliore per identificare le corrispondenze con regole specifiche e criteri DLP di ottimizzazione. Il rapporto sugli incidenti è migliore per identificare parti di contenuto specifiche che sono problematiche per i criteri DLP.
    
- **False positive e sostituzioni DLP** Se il criterio DLP consente agli utenti di eseguire l'override o di segnalare un falso positivo, questo rapporto Visualizza il numero di istanze nel tempo. È possibile filtrare il report per data, percorso o criterio. È possibile utilizzare questo report per: 
    
  - Ottimizzare o affinare i criteri DLP vedendo quali criteri incorrono in un numero elevato di falsi positivi.
    
  - Visualizzare le giustificazioni inviate dagli utenti quando si risolve un suggerimento per i criteri eseguendo l'override del criterio.
    
  - Individuare la posizione in cui i criteri DLP sono in conflitto con processi aziendali validi incorrendo in un numero elevato di sostituzioni degli utenti.
    
Tutti i report DLP sono in grado di visualizzare i dati del periodo di quattro mesi più recente. I dati più recenti possono richiedere fino a 24 ore per essere visualizzati nei rapporti.
  
Questi rapporti sono disponibili &amp; nel **Dashboard**dei **report** \> del centro \> sicurezza e conformità.
  
![Rapporto delle corrispondenze dei criteri DLP](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Visualizzare la giustificazione inviata da un utente per una sostituzione

Se il criterio DLP consente agli utenti di sostituirlo, è possibile utilizzare il rapporto false positive e Sostituisci per visualizzare il testo inviato dagli utenti nel suggerimento per i criteri.
  
![Campo giustificazione nei dettagli del rapporto di sostituzione e false](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Intervenire su informazioni e suggerimenti

I report possono mostrare spunti e suggerimenti in cui è possibile fare clic sull'icona di avviso rossa per visualizzare i dettagli relativi a potenziali problemi e intraprendere possibili interventi correttivi.
  
![Fare clic su un'icona Insights per visualizzare i dettagli e le azioni da intraprendere](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Autorizzazioni per i report DLP

Per visualizzare i report DLP nel centro sicurezza & Compliance, è necessario assegnare il seguente:

- Ruolo **lettore di sicurezza** nell'interfaccia di amministrazione di Exchange. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e lettore di sicurezza nell'interfaccia di amministrazione di Exchange.

- Ruolo di **gestione della conformità DLP di sola visualizzazione** nel centro sicurezza & Compliance. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli amministratore di conformità, Gestione organizzazione, amministratore della sicurezza e lettore di sicurezza nel centro sicurezza & conformità.

- Ruolo **destinatari di sola visualizzazione** nell'interfaccia di amministrazione di Exchange. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità, Gestione organizzazione e organizzazione di sola visualizzazione nell'interfaccia di amministrazione di Exchange.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Individuare i cmdlet per i report DLP

Per utilizzare la maggior parte dei cmdlet per il centro &amp; sicurezza e conformità, è necessario:
  
1. [Connettersi al Centro sicurezza e conformità Office 365 utilizzando sessione remota di PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409).
    
2. Utilizzare uno di questi [cmdlet del centro &amp; sicurezza e conformità di Office 365](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
Tuttavia, i report DLP devono estrarre dati dall'intera sede di Office 365, incluso Exchange Online. Per questo motivo, i cmdlet per i report DLP sono disponibili in PowerShell di Exchange Online, non in PowerShell &amp; per il Centro sicurezza e conformità. Pertanto, per utilizzare i cmdlet per i report DLP, è necessario eseguire le operazioni seguenti:
  
1. [Connettersi a Exchange Online usando una sessione remota di PowerShell](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Utilizzare uno di questi cmdlet per i report DLP:
    
      - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

