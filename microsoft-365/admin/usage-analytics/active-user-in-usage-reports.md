---
title: Utente attivo nei report di utilizzo di Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Informazioni su un utente attivo di analisi di utilizzo di Microsoft 365, report attività e metriche di adozioni.
ms.openlocfilehash: 0e2f5f5112593c142b4a7829977221c5542adf49
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243503"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Utente attivo nei report di utilizzo di Microsoft 365

## <a name="active-user-in-usage-reports"></a>Utente attivo nei report di utilizzo

Un utente attivo di prodotti Microsoft 365 per l' [analisi dell'utilizzo di microsoft 365](usage-analytics.md) e i [rapporti attività nell'](../activity-reports/activity-reports.md) interfaccia di amministrazione è definito come segue. 
  
|**Prodotto**|**Definizione di utente attivo**|**Note**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Qualsiasi utente che abbia letto o inviato un messaggio di posta elettronica.  <br/> |Nessuna informazione del calendario è rappresentata, verranno aggiunte in un aggiornamento imminente.  <br/> |
|SharePoint Online  <br/> |Qualsiasi utente che abbia interagito con un file mediante la creazione, modifica, visualizzazione, eliminazione, condivisione interna o esterna o sincronizzazione con i client in tutti i siti o visualizzato una pagina in qualsiasi sito.  <br/> |La metrica dell'utente attivo per SharePoint Online nell'app modello di analisi di utilizzo di Microsoft 365 riflette solo gli utenti che hanno eseguito attività sui file in un sito del team di SharePoint o in un sito del gruppo. L'app modello verrà aggiornata per sincronizzare la definizione in modo che sia presente nei report sull'utilizzo nell'interfaccia di amministrazione.  <br/> |
|OneDrive for Business  <br/> |Qualsiasi utente che abbia interagito con un file mediante la creazione, modifica, visualizzazione, eliminazione, condivisione interna o esterna o sincronizzazione con i client.  <br/> ||
|Yammer  <br/> |Qualsiasi utente che abbia letto, pubblicato o espresso apprezzamento per un messaggio in Yammer.  <br/> ||
|Skype for Business  <br/> |Qualsiasi utente che abbia partecipato a una sessione peer-to-peer (inclusi messaggistica istantanea, chiamate audio e video, condivisione delle applicazioni e trasferimento di file) che abbia organizzato o partecipato a una conferenza.  <br/> ||
|Office  <br/> |Qualsiasi utente che abbia attivato la sottoscrizione Microsoft 365 Pro Plus, Visio Pro o Project Pro su almeno un dispositivo.  <br/> ||
|Microsoft 365 gruppi  <br/> |Qualsiasi membro del gruppo con attività relative alle cassette postali (se è stato inviato un messaggio al gruppo)  <br/> |Questa definizione verrà migliorata con attività dei file di sito di gruppo e attività del gruppo Yammer (attività dei file nel sito del gruppo e messaggio inviato al gruppo di Yammer associato al gruppo). Questi dati non sono attualmente disponibili nell'app modello di analisi di utilizzo di Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Qualsiasi utente che abbia partecipato a messaggi di chat, messaggi di chat privati, chiamate, riunioni o altre attività. Altre attività sono definite come il numero di altre attività del team da parte dell'utente, alcune delle quali includono, e non solo, i messaggi, le app, i file, le ricerche, i gruppi di lavoro e il canale e la loro preferenza.  <br/> ||
   
## <a name="adoption-metrics"></a>Metriche di adozione

L' [analisi di utilizzo di Microsoft 365](usage-analytics.md) contiene metriche di adozione aggiuntive relative agli utenti attivi per mostrare l'adozione dei prodotti nel tempo. Queste metriche sono valide per il mese, l'anno e il prodotto selezionato e sono definite come segue. 
  
|**Metrica**|**Descrizione**|
|:-----|:-----|
|EnabledUsers  <br/> |Numero di utenti abilitati all'utilizzo del prodotto nel mese.  <br/> |
|ActiveUsers  <br/> |Numero di utenti attivi nel mese.  <br/> |
|MoMReturningUsers  <br/> |Numero di utenti attivi nel mese che sono stati attivi anche nel mese precedente.  <br/> |
|FirstTimeUsers  <br/> |Numero di utenti attivi nel mese che non hanno mai utilizzato il servizio prima.  <br/> |
|CumulativeActiveUsers  <br/> |Numero di utenti attivi nel mese più qualsiasi mese precedente.  <br/> |
|ActiveUsers (%)  <br/> |Percentuale di utenti, arrotondati al decimo più vicino, attivi nel mese rispetto al numero di utenti abilitati in quel mese.  <br/> |
|MoMReturningUsers (%)  <br/> |Percentuale di utenti, arrotondati al decimo più vicino, attivi nel mese che sono stati attivi anche nel mese precedente rispetto al numero di utenti attivi.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers sono stati reimpostati a partire dal 1 ° gennaio 2018 con l'inclusione di Microsoft teams.
  
