---
title: Utente attivo nei report sull'utilizzo di Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Informazioni su un utente attivo dell'analisi di utilizzo di Microsoft 365, dei report attività e delle metriche di adozione.
ms.openlocfilehash: 7b8d15a88568c9af8b11a157dad2ec5f76ace6d3
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603973"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Utente attivo nei report sull'utilizzo di Microsoft 365

## <a name="active-user-in-usage-reports"></a>Utente attivo nei report di utilizzo

Un utente attivo dei prodotti Microsoft 365 per l'analisi dell'utilizzo di [Microsoft 365](usage-analytics.md) e dei report attività nell'interfaccia di amministrazione è definito come segue. [](../activity-reports/activity-reports.md) 
  
|**Prodotto**|**Definizione di utente attivo**|**Note**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Qualsiasi utente che abbia eseguito una delle azioni seguenti: Segna come già letto, invia messaggi, crea appuntamenti, invia convocazioni di riunione, accetta (come provvisorio) o rifiuta le convocazioni di riunione, annulla le riunioni.  <br/> |Nessuna informazione del calendario è rappresentata, verranno aggiunte in un aggiornamento imminente.  <br/> |
|SharePoint Online  <br/> |Qualsiasi utente che abbia interagito con un file mediante la creazione, modifica, visualizzazione, eliminazione, condivisione interna o esterna o sincronizzazione con i client in tutti i siti o visualizzato una pagina in qualsiasi sito.  <br/> |La metrica utente attiva per SharePoint Online nell'app modello Analisi di utilizzo di Microsoft 365 riflette solo gli utenti che hanno fatto attività di file in un sito del team di SharePoint o in un sito di gruppo. L'app modello verrà aggiornata per sincronizzare la definizione con quella presente nei report sull'utilizzo nell'interfaccia di amministrazione.  <br/> |
|OneDrive for Business  <br/> |Qualsiasi utente che abbia interagito con un file mediante la creazione, modifica, visualizzazione, eliminazione, condivisione interna o esterna o sincronizzazione con i client.  <br/> ||
|Yammer  <br/> |Qualsiasi utente che abbia letto, pubblicato o espresso apprezzamento per un messaggio in Yammer.  <br/> ||
|Skype for Business  <br/> |Qualsiasi utente che abbia partecipato a una sessione peer-to-peer (inclusi messaggistica istantanea, chiamate audio e video, condivisione delle applicazioni e trasferimento di file) che abbia organizzato o partecipato a una conferenza.  <br/> ||
|Office  <br/> |Qualsiasi utente che ha attivato l'abbonamento a Microsoft 365 Pro Plus, Visio Pro o Project Pro in almeno un dispositivo.  <br/> ||
|Gruppi di Microsoft 365  <br/> |Qualsiasi membro del gruppo con attività relative alle cassette postali (se è stato inviato un messaggio al gruppo)  <br/> |Questa definizione verrà migliorata con l'attività dei file del sito del gruppo e l'attività del gruppo di Yammer (attività sui file nel sito del gruppo e il messaggio pubblicato nel gruppo di Yammer associato al gruppo). Questi dati non sono attualmente disponibili nell'app modello Analisi di utilizzo di Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Qualsiasi utente che abbia partecipato a messaggi di chat, messaggi di chat privati, chiamate, riunioni o altre attività. Altre attività sono definite come il numero di altre attività del team da parte dell'utente, alcune delle quali includono, e non solo, messaggi di gradimento, app, lavoro sui file, ricerca, seguire team e canali e favorirli.  <br/> ||
   
## <a name="adoption-metrics"></a>Metriche di adozione

[L'analisi dell'utilizzo di Microsoft 365](usage-analytics.md) contiene ulteriori metriche di adozione relative agli utenti attivi per mostrare l'adozione dei prodotti nel tempo. Queste metriche sono valide per il mese, l'anno e il prodotto selezionato e sono definite come segue. 
  
|**Metrica**|**Descrizione**|
|:-----|:-----|
|EnabledUsers  <br/> |Numero di utenti abilitati per l'utilizzo del prodotto nel mese.  <br/> |
|ActiveUsers  <br/> |Numero di utenti attivi nel mese.  <br/> |
|MoMReturningUsers  <br/> |Numero di utenti attivi nel mese che erano attivi anche nel mese precedente.  <br/> |
|FirstTimeUsers  <br/> |Numero di utenti attivi nel mese che non hanno mai utilizzato il servizio prima.  <br/> |
|CumulativeActiveUsers  <br/> |Numero di utenti attivi nel mese più qualsiasi mese precedente.  <br/> |
|ActiveUsers(%)  <br/> |Percentuale di utenti, arrotondata al decimo più vicino, attiva nel mese rispetto al numero di utenti abilitati in tale mese.  <br/> |
|MoMReturningUsers(%)  <br/> |Percentuale di utenti, arrotondata al decimo più vicino, attivo nel mese che erano attivi anche nel mese precedente rispetto al numero di utenti attivi.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, CumulativeActiveUsers sono stati reimpostati a partire dal &amp; 1° gennaio 2018 con l'inclusione di Microsoft Teams.
  
