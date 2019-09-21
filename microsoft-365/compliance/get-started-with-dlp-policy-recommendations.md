---
title: Introduzione alle raccomandazioni per i criteri di prevenzione della perdita dei dati
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: Questa raccomandazione basata su Insight aiuta l'organizzazione a mantenere i contenuti riservati sicuri quando viene archiviato e condiviso in Office 365 informando quando si verifica una possibile lacuna nella copertura dei criteri DLP. Questo suggerimento viene visualizzato nella Home page del Centro sicurezza &amp; e conformità, se i documenti contengono uno dei primi cinque tipi più comuni di informazioni riservate ma non sono protetti da un criterio DLP.
ms.openlocfilehash: 37292d1496fb9217b2c3d77fadff18ae002e14d7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083593"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>Introduzione alle raccomandazioni per i criteri di prevenzione della perdita dei dati

Questa raccomandazione basata su Insight aiuta l'organizzazione a mantenere i contenuti riservati sicuri quando viene archiviato e condiviso in Office 365 informando quando si verifica una possibile lacuna nella copertura dei criteri DLP. Questo suggerimento viene visualizzato nella **Home** page del Centro sicurezza &amp; e conformità, se i documenti contengono uno dei primi cinque tipi più comuni di informazioni riservate, ma non sono protetti da un criterio di prevenzione della perdita di dati (DLP). 
  
È possibile utilizzare questo widget per creare rapidamente un criterio DLP personalizzato con un solo clic o due e, dopo aver creato questo criterio DLP, è completamente personalizzabile. Si noti che, se la raccomandazione non viene visualizzata all'inizio, provare a fare clic su **+ altro** nella parte inferiore della sezione **consigliata per l'utente** . 
  
![Widget denominato informazioni riservate non protette](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>Creare il criterio DLP consigliato

Quando il widget Visualizza informazioni riservate non protette, scegliere **inizia** in basso per creare rapidamente un criterio DLP. 
  
Per proteggere le informazioni riservate, questo criterio DLP:
  
- Rileva quando il contenuto in Exchange, SharePoint e OneDrive che contiene uno dei tipi non protetti di informazioni riservate viene condiviso con persone esterne all'organizzazione.
    
- Genera report di attività dettagliati in modo che sia possibile tenere conto di elementi quali la condivisione dei contenuti con persone esterne all'organizzazione e quando sono state eseguite. È possibile utilizzare i [report DLP](view-the-dlp-reports.md) e i [dati del log di controllo](search-the-audit-log-in-security-and-compliance.md) (dove **attività** = **DLP**) per visualizzare queste informazioni.
    
È inoltre possibile scegliere di disporre del criterio DLP:
  
- Inviare un messaggio di posta indesiderata quando gli utenti condividono molte delle informazioni riservate con persone esterne all'organizzazione.
    
- Aggiungere altri utenti al rapporto sugli incidenti di posta elettronica.
    
- Mostrare un suggerimento per i criteri e inviare una notifica tramite posta elettronica agli utenti quando tentano di condividere queste informazioni riservate con persone esterne all'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [inviare notifiche tramite posta elettronica e Mostra suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md).
    
Se si desidera modificare queste opzioni in un secondo momento, è possibile modificare il criterio DLP dopo che è stato creato. Ad esempio, è possibile rendere il criterio più restrittivo persino bloccando la condivisione di contenuti che contengono informazioni riservate in primo luogo, vedere la sezione successiva.
  
![Impostazioni del widget denominate informazioni riservate non protette](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>Modificare il criterio DLP consigliato

Dopo aver utilizzato il widget per creare un criterio DLP, il criterio viene visualizzato in **prevenzione della perdita di dati** nella pagina **criteri** del &amp; Centro sicurezza e conformità. 
  
Per impostazione predefinita, il criterio è denominato **criterio consigliato dal sistema per la condivisione di informazioni riservate**. Questo criterio è completamente personalizzabile, lo stesso di qualsiasi criterio DLP creato da zero. Ad esempio, se si è deciso di non abilitare i rapporti sugli incidenti e i suggerimenti per i criteri quando è stato utilizzato il widget, è sempre possibile modificare il criterio e attivarle in qualsiasi momento.
  
![Criteri consigliati per la condivisione di informazioni riservate](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando il widget fa e non viene visualizzato

Il widget denominato **informazioni riservate non protette** viene visualizzato nella sezione **consigliata** della **Home** page del Centro sicurezza &amp; e conformità. 
  
Questo widget viene visualizzato solo quando:
  
- I nuovi documenti contenenti uno dei cinque tipi più comuni di informazioni riservate sono stati rilevati in SharePoint o OneDrive negli ultimi 30 giorni.
    
- Le informazioni riservate non sono già protette da un criterio DLP esistente.
    
A differenza dei criteri DLP che analizzano costantemente i dati, questa raccomandazione consente di analizzare gli spazi vuoti nella copertura del criterio DLP all'incirca ogni 48 ore, quindi dopo che è stato caricato il nuovo contenuto, potrebbero essere necessari fino a due giorni prima che venga visualizzata la raccomandazione.
  
Infine, dopo aver utilizzato il widget per creare un criterio DLP consigliato, il widget scompare dalla **Home** page. 
  

