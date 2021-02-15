---
title: Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di Dynamics 365 Customer Voice
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
description: Informazioni su come ottenere un report attività di Microsoft Dynamics 365 Customer Voice usando il dashboard report di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: de03067197c80634f02318b35a79eb84e33c4b86
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988553"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Report di Microsoft 365 nell'interfaccia di amministrazione - Attività di Dynamics 365 Customer Voice

Il **dashboard** report di Microsoft 365 mostra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento introduttivo sui report](activity-reports.md).
  
Ad esempio, è possibile comprendere l'attività di ogni utente con licenza per l'uso di Microsoft Dynamics 365 Customer Voice esaminando le interazioni con Dynamics 365 Customer Voice. Consente inoltre di comprendere il livello di collaborazione in corso esaminando il numero di sondaggi pro creati e di sondaggi pro a cui gli utenti hanno risposto. 
  
> [!NOTE]
> Per visualizzare i report, è necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, Teams Service, Teams Communications o Skype for Business. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Come accedere al report attività di Forms Pro

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. **Nell'elenco a discesa Selezionare un report** selezionare Attività di Dynamics **365 Customer** \> **Voice.**

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretare il report attività di Dynamics 365 Customer Voice

È possibile visualizzare l'attività di Dynamics 365 Customer Voice dell'utente esaminando i grafici **Attività** **e Utenti.** 

![Report attività moduli](../../media/formsproactivity.png)

|Elemento|Descrizione|
|:-----|:-----|
|1.  <br/> |Il report attività di **Dynamics 365 Customer Voice** può essere visualizzato per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella (7) mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report).   <br/> |
|2.  <br/> |I dati in ogni report sono in genere recenti come le ultime 48 ore.  <br/> |
|3.  <br/> |La **visualizzazione** Utenti consente di comprendere la tendenza nel numero di utenti attivi di Dynamics 365 Customer Voice. Un utente viene considerato attivo se ha eseguito un'attività attorno a un sondaggio pro (creazione, modifica, visualizzazione e così via) entro il periodo di tempo specifico.  <br/> |
|4.  <br/> |La **visualizzazione** Attività consente di comprendere la tendenza del numero di utenti attivi. Un utente viene considerato attivo se ha eseguito un'attività sui file, ad esempio salvataggio, sincronizzazione, modifica o condivisione, o ha visitato una pagina in un intervallo di tempo specificato.<br/> NOTA: un'attività può verificarsi più volte per un singolo sondaggio, ma verrà conteggiato come un solo sondaggio attivo. Ad esempio, è possibile creare un sondaggio pro e continuare a modificare lo stesso sondaggio più volte in un periodo di tempo specificato, verrà conteggiato come un solo sondaggio. <br>|
|5.<br/>|Nel grafico **Utenti** l'asse Y è il numero di utenti univoci. L'asse X è la data in cui sono attivi gli utenti univoci. Le legende sono:<br/><br/>**I progettisti** significano che l'utente ha creato o modificato un sondaggio Di Dynamics 365 Customer Voice.<br><br>Nel grafico **Attività,** l'asse Y è il conteggio delle risposte di Dynamics 365 Customer Voice per sondaggio. L'asse X è la data in cui si è verificata l'attività di sondaggio o risposta. Le legende sono:<br/><br/>**Sondaggi creati è** il conteggio dei sondaggi univoci di Dynamics 365 Customer Voice creati dagli utenti<br>**Risposte è** il numero di risposte anonime o non anonime inviate dagli utenti che hanno ricevuto il sondaggio. |
|6.<br/>|È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Nel grafico Utenti, ad esempio, selezionare progettisti, risponditori o utenti totali per visualizzare solo le informazioni correlate a ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella della griglia sottostante.|
|7.<br/>|La tabella mostra un'analisi delle attività a livello di singolo utente. Le legende sono:<br/><br/>**Il** nome utente è l'indirizzo di posta elettronica dell'utente che ha eseguito l'attività in Microsoft Forms.<br/>**Data ultima attività (UTC)** è la data più recente in cui un'attività del modulo è stata eseguita dall'utente per l'intervallo di date selezionato. Per visualizzare l'attività relativa a una data specifica, selezionare la data direttamente nel grafico.<br/>In questo modo la tabella verrà filtrata in modo da visualizzare i dati sulle attività dei file solo per gli utenti che hanno eseguito l'attività in tale giorno specifico.<br/><br/>**Il numero di sondaggi creati** è il numero di sondaggi creati dall'utente.<br/> **Il numero di risposte al sondaggio** è il numero di risposte dei risponditori a cui è stato distribuito il sondaggio.|
|8.<br/>|Selezionare **l'icona Gestisci** colonne per aggiungere o rimuovere colonne dal report.|
|9.<br/>|È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il **collegamento Esporta.** In questo modo vengono esportati i dati per tutti gli utenti e è possibile eseguire semplici operazioni di aggregazione, ordinamento e filtro per un'ulteriore analisi. Se sono presenti meno di 100 utenti, è possibile ordinare e filtrare all'interno della tabella del report stesso. Se sono presenti più di 100 utenti, per filtrare e ordinare, sarà necessario esportare i dati.|