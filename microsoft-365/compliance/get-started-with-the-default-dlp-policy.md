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
description: Informazioni su come utilizzare il report per affinare i criteri di prevenzione della perdita di dati (DLP) predefiniti dell'organizzazione.
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817615"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introduzione ai criteri di prevenzione della perdita dei dati predefiniti

Prima di creare anche il primo criterio di prevenzione della perdita di dati (DLP), DLP contribuisce a proteggere le informazioni riservate con un criterio predefinito. Questo criterio predefinito e il relativo suggerimento (illustrato di seguito) consentono di mantenere la sicurezza del contenuto riservato notificando quando la posta elettronica o i documenti contenenti un numero di carta di credito sono stati condivisi con un utente esterno all'organizzazione. Questo suggerimento viene visualizzato nella **Home** page del Centro sicurezza e &amp; conformità. 
  
È possibile utilizzare questo widget per visualizzare rapidamente la condivisione e la quantità di informazioni riservate, quindi affinare il criterio DLP predefinito in un solo clic o due. È inoltre possibile modificare il criterio DLP predefinito in qualsiasi momento perché è completamente personalizzabile. Si noti che, se la raccomandazione non viene visualizzata all'inizio, provare a fare clic su **+ altro** nella parte inferiore della sezione **consigliata per l'utente** . 
  
![Widget denominato ulteriore protezione del contenuto condiviso](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Visualizzazione del report e affinamento del criterio DLP predefinito

Quando il widget indica che gli utenti hanno condiviso informazioni riservate con persone esterne all'organizzazione, scegliere **affina i criteri DLP** nella parte inferiore. 
  
Il rapporto dettagliato indica quando e quanto contenuto contenente i numeri di carta di credito è stato condiviso negli ultimi 30 giorni. Si noti che le corrispondenze delle regole possono richiedere fino a 48 ore per essere visualizzate nel widget.
  
Per proteggere le informazioni riservate, il criterio DLP predefinito:
  
- Rileva quando il contenuto in Exchange, SharePoint e OneDrive che contiene almeno un numero di carta di credito viene condiviso con persone esterne all'organizzazione.
    
- Visualizza un suggerimento per i criteri e invia una notifica tramite posta elettronica agli utenti quando tentano di condividere queste informazioni riservate con persone esterne all'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [inviare notifiche tramite posta elettronica e Mostra suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md).
    
- Genera report di attività dettagliati in modo che sia possibile tenere conto di elementi quali la condivisione dei contenuti con persone esterne all'organizzazione e quando sono state eseguite. È possibile utilizzare i [report DLP](view-the-dlp-reports.md) e i [dati del log di controllo](search-the-audit-log-in-security-and-compliance.md) (dove **attività**  =  **DLP**) per visualizzare queste informazioni.
    
Per affinare rapidamente il criterio DLP predefinito, è possibile sceglierlo:
  
- Inviare un messaggio di posta indesiderata quando gli utenti condividono queste informazioni riservate con persone esterne all'organizzazione.
    
- Aggiungere altri utenti al rapporto sugli incidenti di posta elettronica.
    
- Blocca l'accesso al contenuto contenente le informazioni riservate, ma Consenti all'utente di eseguire l'override e la condivisione o l'invio, se necessario.
    
Per ulteriori informazioni sui rapporti sugli incidenti o la limitazione dell'accesso, vedere [Panoramica dei criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md).
  
Se si desidera modificare queste opzioni in un secondo momento, è possibile modificare il criterio DLP predefinito in qualsiasi ora, vedere la sezione successiva.
  
![Impostazioni per widget denominato ulteriore protezione del contenuto condiviso](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Modificare il criterio DLP predefinito

Questo criterio è denominato **criterio DLP predefinito** e viene visualizzato in **prevenzione della perdita di dati** nella pagina **criteri** del Centro sicurezza e &amp; conformità. 
  
Questo criterio è completamente personalizzabile, lo stesso di qualsiasi criterio DLP creato da zero. È anche possibile disattivare o eliminare il criterio, in modo che gli utenti non ricevano più suggerimenti per i criteri o notifiche tramite posta elettronica.
  
![Criterio DLP denominato criterio DLP predefinito](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando il widget fa e non viene visualizzato

Il widget denominato **ulteriore protezione contenuto condiviso** viene visualizzato nella sezione **consigliata per l'utente** della **Home** page del Centro sicurezza e &amp; conformità. 
  
Questo widget viene visualizzato solo quando:
  
- Non esistono criteri di prevenzione della perdita di dati nel centro sicurezza o nell'interfaccia di &amp; amministrazione di Exchange. Questo widget ha lo scopo di iniziare a utilizzare DLP, in modo che non venga visualizzato se si dispone già di criteri DLP.
    
- I contenuti contenenti almeno una carta di credito sono stati condivisi con un utente esterno all'organizzazione negli ultimi 30 giorni.
    
Si noti che le corrispondenze delle regole possono richiedere fino a 48 ore per essere disponibili per il widget, quindi dopo che le informazioni riservate condivise esternamente vengono rilevate, potrebbero essere necessari fino a due giorni affinché venga visualizzata la raccomandazione.
  
Infine, dopo aver utilizzato il widget per affinare il criterio DLP predefinito, il widget scompare dalla **Home** page. 
  

