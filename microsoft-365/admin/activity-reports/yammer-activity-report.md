---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-report attività di Yammer
f1.keywords:
- NOCSH
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
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a
description: Ottenere il report attività di Yammer e sapere di più sul numero di utenti che utilizzano Yammer per inviare, come, o leggere un messaggio.
ms.openlocfilehash: bd128e17b8d435b8d5c6b06f16ff37fea11a6ce3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43618957"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-report attività di Yammer

Come amministratore Microsoft 365, nel dashboard **report** sono riportati i dati relativi all'utilizzo dei prodotti all'interno dell'organizzazione. Estrarre [i report attività nell'interfaccia di amministrazione](activity-reports.md). Il **report Attività su Yammer** consente di capire il livello di utilizzo di Yammer nell'organizzazione calcolando il numero di utenti che usano Yammer per pubblicare, aggiungere Mi piace o leggere un messaggio e la quantità di attività generata nell'intera organizzazione. 
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint, teams, Communications o Skype for business per visualizzare i report. 
 
## <a name="how-to-get-to-the-yammer-activity-report"></a>Come accedere al report attività su Yammer

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare **attività**di **Yammer** \> .
  
## <a name="interpret-the-yammer-activity-report"></a>Interpretare il report Attività in Yammer

Per avere una visuale delle attività degli utenti in Yammer, è possibile osservare i grafici Attività e Utenti.
  
![Report attività di Yammer](../../media/92e8b2c6-166a-4154-9824-3fb6bbedf0db.JPG)
  
Il report attività contiene le informazioni seguenti.
  
- Usare le schede dei giorni per visualizzare il report **Attività in Yammer** per le tendenze degli ultimi 7, 30, 90 o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report). 
    
- Ogni report include la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività.
    
- Il grafico **Attività** consente di interpretare la tendenza delle attività in Yammer all'interno dell'organizzazione, suddividendo i messaggi pubblicati, letti o a cui è stato aggiunto Mi piace. 
    
    ![Visualizzazione attività nel report attività di Yammer](../../media/76983516-2c5f-43a1-a5e3-c414e9f17638.JPG)
  
  - Nel grafico **Attività** l'asse Y indica il numero delle attività di pubblicazione, lettura e aggiunta di Mi piace ai messaggi. 
    
- Il grafico **Utenti** consente di interpretare la tendenza degli utenti che generano le attività in Yammer, esaminando gli utenti che pubblicano, leggono a aggiungono Mi piace ai messaggi in Yammer. 
    
    ![Visualizzazione degli utenti nel report attività di Yammer](../../media/b1098162-7b79-430f-bfe4-9d3957d56885.JPG)
  
  - Nel grafico **Utenti** l'asse Y indica l'utente che pubblica, legge o aggiunge Mi piace ai messaggi in Yammer. 
    
  - L'asse X in entrambi i grafici rappresenta l'intervallo di date selezionato per il report specifico.
    
- È possibile filtrare la serie visualizzata nel grafico selezionando un elemento nella legenda. Ad esempio, nel grafico **attività** selezionare **postato**, **letto**o **apprezzato** per visualizzare solo le informazioni relative a ognuna di esse. 
    
    ![Opzioni registrate, lette e apprezzate](../../media/8b832afc-415c-409b-816f-cb02b7a71e69.png)
  
    La modifica di questa selezione non cambia le informazioni nella tabella della griglia.
    
- La tabella sotto il grafico mostra un'analisi delle attività in Yammer a livello di utente.
    
    È possibile usare il menu per filtrare e ordinare i dati.
    
    ![Opzioni di menu per i report di Yammer](../../media/9d32240c-f1ff-400b-9c4e-a21b48651530.JPG)
  
    È anche possibile aggiungere e rimuovere le colonne. Le colonne disponibili sono:
    
  - **Nome utente** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere questo campo anonimo. 
    
    Questa griglia consente di visualizzare gli utenti che hanno effettuato l'accesso a Yammer utilizzando l'account Microsoft 365 o che hanno effettuato l'accesso alla rete tramite Single Sign-on.
    
  - **Nome visualizzato** è il nome completo dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo. 
    
  - **Stato utente** corrisponde a uno di questi tre valori: Attivato, Eliminato o Sospeso. 
    
    Questi report mostrano i dati relativi agli utenti attivi, sospesi ed eliminati. Gli utenti in sospeso sono esclusi, in quanto non possono pubblicare, leggere o aggiungere Mi piace a un messaggio.
    
  - **Data del cambio di stato (UTC)** è la data in cui lo stato dell'utente è stato cambiato in Yammer. 
    
  - **Data ultima attività (UTC)** è la data più recente in cui l'utente ha pubblicato, letto o aggiunto Mi piace a un messaggio. 
    
  - **Pubblicati** è il numero di messaggi che l'utente ha pubblicato nel periodo specificato. 
    
  - **Letti** è il numero di conversazioni che l'utente ha letto nel periodo specificato. 
    
  - **Apprezzati** è il numero di messaggi univoci a cui l'utente ha aggiunto Mi piace nel periodo specificato. 
    
  - **Prodotto assegnato** sono i prodotti assegnati a questo utente. 
    
    Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **come nascondere i dettagli a livello di utente** in [rapporti attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).
    
- È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
    
## <a name="what-data-is-in-these-reports"></a>Quali dati contengono questi report?

- **Tutti i clienti** Questi report riuniscono i dati di tutti i clienti, inclusi quelli che usano Yammer in un browser o in un'app iOS o Android. 
    
- **Nessun dato di reti esterne** I dati di reti esterne non sono inclusi in questi report. 
    
- **Reti attivate** Questi report mostrano i dati per la rete Yammer che fa parte dell'abbonamento a Microsoft 365. Il grafico aggrega l'utilizzo di tutti gli utenti che hanno effettuato l'accesso alla rete Yammer, indipendentemente dal fatto che abbiano utilizzato Microsoft 365 o Yammer per eseguire l'accesso. 
    

