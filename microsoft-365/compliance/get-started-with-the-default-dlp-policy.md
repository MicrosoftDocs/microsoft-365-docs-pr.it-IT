---
title: Introduzione ai criteri di prevenzione della perdita dei dati predefiniti
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
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
description: Informazioni su come utilizzare il report per perfezionare i criteri di prevenzione della perdita dei dati (DLP) predefiniti dell'organizzazione.
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817615"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introduzione ai criteri di prevenzione della perdita dei dati predefiniti

Prima di creare il primo criterio di prevenzione della perdita di dati (DLP), DLP contribuisce a proteggere le informazioni riservate con un criterio predefinito. Questo criterio predefinito e il relativo consiglio (mostrato di seguito) consentono di proteggere i contenuti sensibili inviando una notifica quando messaggi di posta elettronica o documenti contenenti un numero di carta di credito sono stati condivisi con un utente esterno all'organizzazione. You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center. 
  
È possibile utilizzare questo widget per visualizzare rapidamente quando e quante informazioni riservate sono stati condivisi e quindi perfezionare il criterio DLP predefinito in uno o due clic. È inoltre possibile modificare il criterio DLP predefinito in qualsiasi momento perché è completamente personalizzabile. Tieni presente che se il suggerimento non è visualizzato in un primo momento, prova a fare clic su **+Altro** nella parte inferiore della sezione Consigliata **per te.** 
  
![Widget denominato Proteggere ulteriormente il contenuto condiviso](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Visualizzare il report e perfezionare il criterio DLP predefinito

Quando il widget mostra che gli utenti hanno condiviso informazioni riservate con persone esterne all'organizzazione, scegliere **Criteri di** prevenzione della perdita dei dati nella parte inferiore. 
  
Il report dettagliato mostra quando e quanti contenuti contenenti numeri di carta di credito sono stati condivisi negli ultimi 30 giorni. Si noti che la visualizzazione delle corrispondenze delle regole nel widget può richiedere fino a 48 ore.
  
Per proteggere le informazioni riservate, il criterio DLP predefinito:
  
- Rileva quando il contenuto in Exchange, SharePoint e OneDrive che contiene almeno un numero di carta di credito viene condiviso con persone esterne all'organizzazione.
    
- Mostra un suggerimento per i criteri e invia una notifica tramite posta elettronica agli utenti quando tentano di condividere queste informazioni riservate con persone esterne all'organizzazione. Per ulteriori informazioni su queste opzioni, vedere Inviare notifiche [tramite posta elettronica e visualizzare i suggerimenti per i criteri DLP.](use-notifications-and-policy-tips.md)
    
- Genera report attività dettagliati in modo da poter tenere traccia di elementi come chi ha condiviso il contenuto con persone esterne all'organizzazione e quando lo ha fatto. È possibile utilizzare i report [DLP e](view-the-dlp-reports.md) i [dati del log di](search-the-audit-log-in-security-and-compliance.md) controllo (dove **Prevenzione** della perdita dei dati attività ) per visualizzare  =  queste informazioni.
    
Per perfezionare rapidamente il criterio DLP predefinito, è possibile scegliere di farlo:
  
- Inviare un messaggio di posta elettronica di report operazioni non consentite quando gli utenti condividono queste informazioni riservate con persone esterne all'organizzazione.
    
- Aggiungere altri utenti al rapporto operazioni non consentite tramite posta elettronica.
    
- Bloccare l'accesso al contenuto contenente le informazioni riservate, ma consentire all'utente di eseguire l'override e condividere o inviare, se necessario.
    
Per ulteriori informazioni sui report operazioni non consentite o sulla limitazione dell'accesso, vedere [Panoramica dei criteri di prevenzione della perdita di dati.](data-loss-prevention-policies.md)
  
Se si desidera modificare queste opzioni in un secondo momento, è possibile modificare il criterio DLP predefinito in qualsiasi momento - vedere la sezione successiva.
  
![Impostazioni per il widget denominato Proteggere ulteriormente il contenuto condiviso](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Modificare il criterio DLP predefinito

Questo criterio è denominato **criterio DLP predefinito** e viene visualizzato in Prevenzione **della** perdita dei dati nella **pagina** Criteri del Centro sicurezza &amp; e conformità. 
  
Questo criterio è completamente personalizzabile, come qualsiasi criterio DLP creato da zero. È inoltre possibile disattivare o eliminare il criterio, in modo che gli utenti non ricevano più suggerimenti per i criteri o notifiche tramite posta elettronica.
  
![Criterio DLP denominato Criterio DLP predefinito](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando il widget non viene visualizzato o non viene visualizzato

Il widget denominato **Protezione ulteriore contenuto condiviso** viene visualizzato nella sezione **Consigliata** per l'utente della **home** page del Centro sicurezza &amp; e conformità. 
  
Questo widget viene visualizzato solo quando:
  
- Non sono disponibili criteri di prevenzione della perdita dei dati nel Centro sicurezza &amp; e conformità o nell'interfaccia di amministrazione di Exchange. Questo widget ha lo scopo di aiutare a iniziare a usare DLP, quindi non viene visualizzato se si dispone già di criteri DLP.
    
- Il contenuto contenente almeno una carta di credito è stato condiviso con un utente esterno all'organizzazione negli ultimi 30 giorni.
    
Si noti che le corrispondenze delle regole possono richiedere fino a 48 ore per essere disponibili per il widget, quindi, dopo aver rilevato le informazioni riservate condivise esternamente, potrebbero essere necessarie fino a due giorni prima che il suggerimento venga visualizzato.
  
Infine, dopo aver utilizzato il widget per perfezionare il criterio DLP predefinito, il widget scompare dalla **home** page. 
  

