---
title: Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di moduli Pro
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Informazioni su come ottenere un report di attività di Microsoft Forms Pro utilizzando il Dashboard Microsoft 365 Reports nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: df03f3f0300dcd923f43987ee786981b1653b1ce
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387706"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-pro-activity"></a>Rapporti Microsoft 365 nell'interfaccia di amministrazione-attività di moduli Pro

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di ogni utente concesso in licenza per l'utilizzo di Microsoft Forms Pro analizzando le interazioni con i moduli Pro. Consente inoltre di comprendere il livello di collaborazione che si sta verificando analizzando il numero di sondaggi Pro creati e le indagini Pro a cui gli utenti hanno risposto. 
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Come accedere al report attività moduli Pro

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare attività **moduli Pro** \> **activity**.

## <a name="interpret-the-forms-activity-report"></a>Interpretare il report attività moduli

È possibile ottenere una visualizzazione nell'attività Forms Pro dell'utente esaminando i grafici **attività** e **utenti** . 

![Report attività moduli](../../media/formsproactivity.png)

|||
|:-----|:-----|
|1.  <br/> |Il report attività **moduli Pro** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 giorni o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) visualizzerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).   <br/> |
|2.  <br/> |I dati di ogni report sono in genere recenti come le ultime 48 ore.  <br/> |
|3.  <br/> |La visualizzazione **utenti** consente di conoscere la tendenza nel numero di utenti di moduli attivi Pro. Un utente viene considerato attivo se ha eseguito un'attività attorno a un sondaggio Pro (creare, modificare, visualizzare e così via) entro il periodo di tempo specifico.  <br/> |
|4.  <br/> |La visualizzazione **attività** consente di comprendere la tendenza nel numero di utenti attivi. Un utente viene considerato attivo se ha eseguito un'attività sui file, ad esempio salvataggio, sincronizzazione, modifica o condivisione, o ha visitato una pagina in un intervallo di tempo specificato.<br/> Nota: un'attività può verificarsi più volte per un singolo sondaggio, ma conterà solo come un sondaggio attivo. Ad esempio, è possibile creare un sondaggio Pro e continuare a modificare lo stesso sondaggio più volte nel corso di un periodo di tempo specificato, conterà solo come un singolo sondaggio. <br>|
|5.<br/>|Nel grafico **utenti** l'asse Y rappresenta il numero di utenti univoci. Asse X è la data in cui gli utenti univoci sono attivi. Le legende sono:<br/><br/>I **progettisti** significa che l'utente ha creato o modificato un sondaggio moduli Pro.<br><br>Nel grafico **attività** , l'asse Y è il numero di risposte Pro dei moduli per sondaggio. Asse X è la data in cui si è verificata l'attività di rilevamento o di risposta. Le legende sono:<br/><br/>I **sondaggi creati** sono il numero di sondaggi specifici per i moduli Pro creati dagli utenti<br>**Responses** è il numero di risposte anonime o non anonime che gli utenti che hanno ricevuto il sondaggio sono stati inviati. |
|6.<br/>|È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico utenti, selezionare progettisti, risponditori o utenti totali per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella della griglia sottostante.|
|7.<br/>|Nella tabella viene illustrata una ripartizione delle attività a livello di utente. Le legende sono:<br/><br/>**Username** è l'indirizzo di posta elettronica dell'utente che ha eseguito l'attività in Microsoft Forms.<br/>**Data ultima attività (UTC)** è la data più recente in cui l'utente ha eseguito un'attività del modulo per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/>In questo modo la tabella verrà filtrata per visualizzare i dati relativi alle attività dei file solo per gli utenti che hanno eseguito l'attività in quel giorno specifico.<br/><br/>**Numero di sondaggi creati** è il numero di sondaggi creati dall'utente.<br/> Il **numero di risposte di sondaggio** è il numero di risposte provenienti da risponditori a cui è stato distribuito il sondaggio.|
|8.<br/>|Selezionare l'icona **Gestisci colonne** per aggiungere o rimuovere colonne dal report.|
|9.<br/>|È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . In questo modo vengono esportati i dati per tutti gli utenti e è possibile eseguire un'aggregazione semplice, l'ordinamento e il filtraggio per un'ulteriore analisi. Se sono presenti meno di 100 utenti, è possibile ordinarli e filtrarli all'interno della tabella del report stesso. Se si dispone di più di 100 utenti, per filtrare e ordinare i dati dovranno essere esportati.|