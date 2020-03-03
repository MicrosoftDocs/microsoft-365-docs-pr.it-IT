---
title: Report di Microsoft 365 nell'interfaccia di amministrazione-report sull'utilizzo di dispositivi Yammer
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
ms.assetid: b793ffdd-effa-43d0-849a-b1ca2e899f38
description: "Ottenere il report sull'utilizzo di dispositivi di Yammer per conoscere i dispositivi su cui gli utenti utilizzano Yammer. "
ms.openlocfilehash: 42fc4b1f9a4d782c50eabd892f6a49d1c474be01
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353377"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>Report di Microsoft 365 nell'interfaccia di amministrazione-report sull'utilizzo di dispositivi Yammer

Il Dashboard Microsoft 365 **Reports** illustra la panoramica delle attività tra i prodotti dell'organizzazione. Consente di eseguire il drill-down fino a visualizzare report a livello di singolo prodotto, per ottenere informazioni più dettagliate sulle attività in ogni prodotto. Vedere l' [argomento di panoramica sui report](activity-reports.md).
  
I report sull'utilizzo di dispositivi Yammer forniscono informazioni sui dispositivi su cui gli utenti usano Yammer. È possibile visualizzare il numero di utenti giornalieri per tipo di dispositivo e il numero di utenti per il tipo di dispositivo in un periodo di tempo selezionato. È anche possibile visualizzare i dettagli per ogni utente.
  
> [!NOTE]
> È necessario essere un amministratore globale, un lettore globale o un lettore di report in Microsoft 365 o un amministratore di Exchange, SharePoint o Skype for business per visualizzare i report. 
  
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>Come si ottiene il report sull'utilizzo di dispositivi Yammer?

1. Nell'interfaccia di amministrazione passare alla pagina **Report** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Utilizzo</a>.

    
2. Nell'elenco **a discesa selezionare un report** selezionare **Yammer** \> **Device Usage**.
  
## <a name="interpret-the-yammer-activity-report"></a>Interpretare il report Attività in Yammer

Per avere una visuale dell'utilizzo di dispositivi Yammer da parte degli utenti è possibile esaminare le visualizzazioni **Utenti** e **Distribuzione**. 
  
Il report sull'utilizzo di dispositivi contiene le informazioni seguenti.
  
- Utilizzare le schede giorno per visualizzare le tendenze del rapporto attività di **utilizzo dei dispositivi Yammer** negli ultimi 7 giorni, 30 giorni, 90 giorni o 180 giorni. Tuttavia, se si seleziona un giorno specifico nel report, la tabella mostrerà i dati per un massimo di 28 giorni dalla data corrente (non la data in cui è stato generato il report). 
    
- Ogni report include la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività.
    
- Il grafico **Utenti** mostra il numero di utenti giornalieri per tipo di dispositivo.<br/>![Visualizzazione degli utenti nel grafico di utilizzo dei dispositivi Yammer](../../media/ecfba1ec-fbea-4491-88da-1fb19b4d5629.png)<br/>![Report sull'utilizzo del dispositivo di Yammer che mostra la visualizzazione utenti](../../media/f396865a-ad6e-4f8b-a145-cc3865b352f4.png)
  
- Il grafico **Distribuzione** mostra il numero di utenti per tipo di dispositivo.<br/>![Visualizzazione distribuzione nel report sull'utilizzo dei dispositivi di Yammer](../../media/7a0b152e-2d2b-4d23-8dc2-046be53b724f.png)<br/>![Report utilizzo di dispositivi Yammer](../../media/780c351d-7a1d-451d-8c16-4c454ef58aa8.png)
  
- La tabella **Dettagli** sotto il grafico mostra un'analisi dell'utilizzo di dispositivi Yammer a livello di utente. 
    
    È anche possibile aggiungere e rimuovere le colonne. Le colonne disponibili sono:
    
  - **Nome utente** è l'indirizzo di posta elettronica dell'utente. È possibile visualizzare l'indirizzo di posta elettronica effettivo o rendere questo campo anonimo. 
    
    Questa griglia consente di visualizzare gli utenti che hanno effettuato l'accesso a Yammer utilizzando l'account Microsoft 365 o che hanno effettuato l'accesso alla rete tramite Single Sign-on.
    
  - **Nome visualizzato** è il nome completo dell'utente. È possibile visualizzare il nome effettivo o rendere questo campo anonimo. 
    
  - **Stato utente** corrisponde a uno di questi tre valori: Attivo, Eliminato o Sospeso. 
    
    Questi report mostrano i dati relativi agli utenti attivi, sospesi ed eliminati. Gli utenti in sospeso sono esclusi, in quanto non possono pubblicare, leggere o aggiungere Mi piace a un messaggio.
    
  - **Web** indica se l'utente ha usato Yammer sul web. 
    
  - **Telefono Windows** indica se l'utente ha usato Yammer in un telefono Windows. 
    
  - **Telefono Android** indica se l'utente ha usato Yammer in un telefono Android. 
    
  - **iPhone** indicates if the user has used Yammer on an iPhone. 
    
  - **iPad** indica se l'utente ha usato Yammer in un iPad. 
    
  - **Altro** indica se l'utente ha usato Yammer in un altro dispositivo non elencato in precedenza. 
    
    Se i criteri dell'organizzazione impediscono la visualizzazione dei report in cui le informazioni degli utenti sono identificabili, è possibile modificare l'impostazione della privacy per tutti questi report. Vedere la sezione **come nascondere i dettagli a livello di utente** nei [rapporti attività nell'interfaccia di amministrazione di Microsoft 365](activity-reports.md).
    
- È inoltre possibile esportare i dati del report in un file CSV di Excel selezionando il collegamento **Esporta** . Vengono esportati i dati di tutti gli utenti, che possono poi essere ordinati e filtrati per ulteriore analisi. Se gli utenti sono meno di 2000, è possibile ordinarli e filtrarli direttamente nella tabella del report. Se invece gli utenti sono più di 2000, per ordinarli e filtrarli occorre esportare i dati. 
    

