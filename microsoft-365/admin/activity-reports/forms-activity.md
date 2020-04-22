---
title: Microsoft 365 segnalazioni nell'interfaccia di amministrazione-moduli
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Informazioni su come ottenere un report attività di Microsoft Forms utilizzando il Dashboard Microsoft 365 Reports nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 63eb8613879849201876b237c659a4529ce2ca0f
ms.sourcegitcommit: b8a9994b26a6d9865212f5b1871286e719d1608e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43781506"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365 segnalazioni nell'interfaccia di amministrazione-moduli

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di ogni utente concesso in licenza per l'utilizzo di Microsoft Forms esaminando la propria interazione con i moduli. Consente inoltre di comprendere il livello di collaborazione in uso esaminando il numero di moduli creati e i moduli a cui l'utente ha risposto.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Come accedere al report attività moduli

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare **attività** **moduli** \> .

## <a name="interpret-the-forms-activity-report"></a>Interpretare il report attività moduli

È possibile ottenere una visualizzazione nell'attività dei moduli dell'utente esaminando i grafici **attività** e **utenti** . 

![Report attività moduli](../../media/adminformsactivity.png)

|||
|:-----|:-----|
|1.  <br/> |Il rapporto **attività moduli** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 giorni o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).  <br/> |
|2.  <br/> |In genere, i dati di ogni report coprono fino alle ultime 24-48 ore.  <br/> |
|3.  <br/> |La visualizzazione **utenti** consente di conoscere la tendenza nel numero di utenti di moduli attivi. Un utente viene considerato attivo se ha eseguito un'attività attorno a una maschera (creare, modificare, visualizzare e così via) oppure ha risposto a una maschera entro il periodo di tempo specificato.  <br/> |
|4.  <br/> |La visualizzazione **attività** consente di comprendere la tendenza nel numero di utenti attivi. Un utente viene considerato attivo se ha eseguito un'attività sui file, ad esempio salvataggio, sincronizzazione, modifica o condivisione, o ha visitato una pagina in un intervallo di tempo specificato.<br/> Nota: un'attività può verificarsi più volte per una singola maschera, ma conterà solo come una forma attiva. Ad esempio, è possibile creare un modulo e continuare a modificare lo stesso modulo più volte per un periodo di tempo specificato, ma verrà conteggiato solo come una singola maschera. Tuttavia, se un utente ha inviato più risposte per lo stesso modulo, ogni risposta sarebbe comunque una risposta individuale e quindi conteggiata più volte. <br/> |
|5.<br/>|Nel grafico **utenti** l'asse Y rappresenta il numero di utenti univoci. Asse X è la data in cui gli utenti univoci sono attivi. Le legende sono:<br/><br/>I **progettisti** significa che l'utente ha creato o modificato un modulo.<br/>**Risponditori** significa che l'utente ha inviato le risposte a un modulo.<br/> **Totale utenti** significa chiunque nella società che è stato progettista o risponditore.<br/><br/> Nel grafico **attività** , l'asse Y è il numero di moduli o risposte univoci. Asse X è la data in cui si è verificata la maschera o l'attività di risposta. Le legende sono:<br/><br/>**Forms created** è il numero di moduli univoci creati dagli utenti.<br/> **Signed in Responses** il numero di risposte firmate negli utenti dell'organizzazione ricevuti.<br/> **Risposte anonime** è il numero di risposte anonime ricevute dagli utenti dell'organizzazione.<br/><br/>|
|6.<br/>|È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico utenti, selezionare progettisti, risponditori o utenti totali per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella della griglia sottostante.|
|7.<br/>|Nella tabella viene illustrata una ripartizione delle attività a livello di utente. Le legende sono:<br/><br/>**Username** è l'indirizzo di posta elettronica dell'utente che ha eseguito l'attività in Microsoft Forms.<br/>**Data ultima attività (UTC)** è la data più recente in cui l'utente ha eseguito un'attività del modulo per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/><br/>In questo modo la tabella verrà filtrata per visualizzare i dati relativi alle attività dei file solo per gli utenti che hanno eseguito l'attività in quel giorno specifico.<br/><br/>Il **numero di moduli creati** è il numero di moduli creati dall'utente.<br/> Il **numero di moduli risponde** è il numero di moduli a cui l'utente ha inviato le risposte.|
|8.<br/>|Selezionare l'icona **Gestisci colonne** per aggiungere o rimuovere colonne dal report.|
|9.<br/>|È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . In questo modo vengono esportati i dati per tutti gli utenti e è possibile eseguire un'aggregazione semplice, l'ordinamento e il filtraggio per un'ulteriore analisi. Se sono presenti meno di 100 utenti, è possibile ordinarli e filtrarli all'interno della tabella del report stesso. Se si dispone di più di 100 utenti, per filtrare e ordinare i dati dovranno essere esportati.|