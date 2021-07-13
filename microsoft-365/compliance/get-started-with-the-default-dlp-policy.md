---
title: Introduzione ai criteri di prevenzione della perdita dei dati predefiniti
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come utilizzare il report per affinare i criteri di prevenzione della perdita dei dati predefiniti dell'organizzazione.
ms.openlocfilehash: 98f2a95d66860695034fa958969d1c195e9d58be
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408961"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introduzione ai criteri di prevenzione della perdita dei dati predefiniti

Prima di creare il primo criterio di prevenzione della perdita dei dati (DLP), DLP contribuisce a proteggere le informazioni riservate con un criterio predefinito. Questo criterio predefinito e il relativo suggerimento (mostrato di seguito) consentono di proteggere i contenuti sensibili inviando una notifica quando i messaggi di posta elettronica o i documenti contenenti un numero di carta di credito sono stati condivisi con un utente esterno all'organizzazione. Questo suggerimento verrà visualizzato nella **home** page del Centro &amp; sicurezza e conformità. 
  
Puoi usare questo widget per visualizzare rapidamente quando e quanti dati sensibili sono stati condivisi e quindi perfezionare il criterio DLP predefinito con uno o due clic. È inoltre possibile modificare il criterio DLP predefinito in qualsiasi momento perché è completamente personalizzabile. Tieni presente che se non vedi il suggerimento in un primo momento, prova a fare clic **su +Altro** nella parte inferiore della **sezione Consigliato per te.** 
  
![Widget denominato Proteggere ulteriormente il contenuto condiviso](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Visualizzare il report e perfezionare il criterio DLP predefinito

Quando il widget mostra che gli utenti hanno condiviso informazioni riservate con persone esterne all'organizzazione, scegliere **Affina** criterio DLP nella parte inferiore. 
  
Il report dettagliato mostra quando e quanti contenuti contenenti numeri di carta di credito sono stati condivisi negli ultimi 30 giorni. Tieni presente che le corrispondenze delle regole possono richiedere fino a 48 ore per essere mostrate nel widget.
  
Per proteggere le informazioni riservate, il criterio DLP predefinito:
  
- Rileva quando il contenuto in Exchange, SharePoint e OneDrive che contiene almeno un numero di carta di credito viene condiviso con persone esterne all'organizzazione.
    
- Mostra un suggerimento per i criteri e invia una notifica tramite posta elettronica agli utenti quando tentano di condividere queste informazioni riservate con persone esterne all'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [Send email notifications and show policy tips for DLP policies.](use-notifications-and-policy-tips.md)
    
- Genera report dettagliati sulle attività in modo da poter tenere traccia di elementi come chi ha condiviso il contenuto con persone esterne all'organizzazione e quando lo ha fatto. È possibile utilizzare i report [DLP e](view-the-dlp-reports.md) i [dati del registro di](search-the-audit-log-in-security-and-compliance.md) controllo (dove **DLP**  =  **attività**) per visualizzare queste informazioni.
    
Per affinare rapidamente il criterio DLP predefinito, è possibile scegliere di farlo:
  
- Inviare un messaggio di posta elettronica di segnalazione degli eventi imprevisti quando gli utenti condividono queste informazioni riservate con persone esterne all'organizzazione.
    
- Aggiungere altri utenti al rapporto operazioni non consentite tramite posta elettronica.
    
- Blocca l'accesso al contenuto contenente le informazioni riservate, ma consenti all'utente di eseguire l'override e condividere o inviare, se necessario.
    
Per ulteriori informazioni sui report degli eventi imprevisti o sulla limitazione dell'accesso, vedere [Informazioni di riferimento sulla prevenzione della perdita di dati.](data-loss-prevention-policies.md)
  
Se si desidera modificare queste opzioni in un secondo momento, è possibile modificare il criterio DLP predefinito in qualsiasi momento- vedere la sezione successiva.
  
![Impostazioni per il widget denominato Proteggere ulteriormente il contenuto condiviso](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Modificare il criterio DLP predefinito

Questo criterio è denominato **Criterio DLP predefinito** e viene visualizzato in Prevenzione della **perdita** dei dati nella **pagina** Criteri del Centro sicurezza &amp; e conformità. 
  
Questo criterio è completamente personalizzabile, come qualsiasi criterio DLP creato da zero. Puoi anche disattivare o eliminare il criterio, in modo che gli utenti non ricevano più suggerimenti per i criteri o notifiche tramite posta elettronica.
  
![Criterio DLP denominato Criterio DLP predefinito](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando il widget viene visualizzato e non viene visualizzato

Il widget denominato **Protezione ulteriore contenuto condiviso** viene visualizzato nella sezione Consigliato per **l'utente** della **home** page del Centro sicurezza &amp; e conformità. 
  
Questo widget viene visualizzato solo quando:
  
- Non esistono criteri di prevenzione della perdita di dati nel Centro sicurezza e conformità &amp; o nell Exchange intervanza di amministrazione. Questo widget ha lo scopo di aiutarti a iniziare a usare DLP, in modo che non venga visualizzato se hai già criteri DLP.
    
- Il contenuto contenente almeno una carta di credito è stato condiviso con un utente esterno all'organizzazione negli ultimi 30 giorni.
    
Tieni presente che le corrispondenze delle regole possono richiedere fino a 48 ore per essere disponibili per il widget, quindi dopo aver rilevato le informazioni riservate condivise esternamente, potrebbero essere necessarie fino a due giorni per la visualizzazione del suggerimento.
  
Infine, dopo aver utilizzato il widget per affinare il criterio DLP predefinito, il widget scompare dalla **home** page. 
  

