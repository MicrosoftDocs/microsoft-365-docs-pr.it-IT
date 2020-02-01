---
title: Configurazione delle notifiche di posta indesiderata dell'utente finale in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: È possibile configurare le notifiche di posta indesiderata dell'utente finale per il criterio di filtro della posta indesiderata a livello di società predefinito o per i criteri di filtro antispam applicati ai domini.
ms.openlocfilehash: 3fc2d78e06d0b33793cab0fac3ba038720662f8a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599623"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Configurazione delle notifiche di posta indesiderata dell'utente finale in Exchange Online

> [!IMPORTANT]
> Questo argomento è destinato ai clienti di Exchange Online che proteggono le loro cassette postali ospitate su cloud. I clienti autonomi di Exchange Online Protection (EOP) che proteggono le cassette postali locali dovrebbero invece leggere l'argomento seguente: [configurare le notifiche di posta indesiderata dell'utente finale in EOP](configure-end-user-spam-notifications-in-eop.md). 
  
È possibile configurare le notifiche di posta indesiderata dell'utente finale per i criteri di filtro della posta indesiderata a livello di società o per i criteri di filtro antispam personalizzati L'abilitazione dei messaggi di notifica di posta indesiderata dell'utente finale consente agli utenti di gestire i propri messaggi in quarantena. 
  
Le notifiche di posta indesiderata dell'utente finale contengono un elenco di tutti i messaggi di posta indesiderata messi in quarantena ricevuti dall'utente finale durante un periodo di tempo configurato. È possibile specificare un valore compreso tra 1 e 15 giorni. È inoltre possibile configurare la lingua in cui è scritto il messaggio di notifica.
  
Dopo la ricezione di un messaggio di notifica, gli utenti finali possono scegliere tra le seguenti opzioni:

**Blocca mittente** se si desidera che in Office 365 venga aggiunto il mittente all'elenco dei mittenti bloccati.

**Rilascia** se il messaggio non è posta indesiderata e si desidera che Office 365 invii il messaggio alla cassetta postale.

**Revisione** per passare al portale di quarantena all'interno del centro sicurezza & Compliance, se si desidera eseguire altre operazioni, ad esempio l'anteprima o il rilascio.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento: 2 minuti
  
Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) . 
  
Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per la configurazione delle notifiche di posta indesiderata

1. In Interfaccia di amministrazione di Exchange, accedere a **Protezione** \> **Filtro posta indesiderata**.
    
2. Selezionare il criterio di filtro della posta indesiderata per il quale si desidera abilitare le notifiche di posta indesiderata dell'utente finale (disabilitato per impostazione predefinita).
    
3. Nel riquadro di destra, in cui sono contenute informazioni di riepilogo sul criterio, fare clic sul collegamento **Configura notifiche spam utente finale**. 
    
4. Nella finestra di dialogo successiva è possibile configurare le seguenti opzioni:
    
   - **Abilita le notifiche di spam all'utente finale** Selezionare questa casella di controllo per abilitare le notifiche di posta indesiderata dell'utente finale per questo criterio. Viceversa, se questo criterio è abilitato, è possibile deselezionare la casella di controllo per disabilitare le notifiche di posta indesiderata dell'utente finale per tale criterio. 
    
   - **Invia notifiche di spam agli utenti finali ogni (giorni)** Consente di specificare la frequenza di invio delle notifiche di posta indesiderata dell'utente finale. Il valore predefinito è 3 giorni. È possibile specificare un valore compreso tra 1 e 15 giorni. Se, ad esempio, si specifica 7 giorni, la notifica includerà l'elenco di tutti i messaggi che negli ultimi 7 giorni erano diretti all'utente ma che sono stati invece inviati alla quarantena della posta indesiderata. 
    
   - **Lingua delle notifiche** Utilizzando l'elenco a discesa, selezionare la lingua in cui scrivere le notifiche di posta indesiderata dell'utente finale per il criterio in questione. 
    
   - Fare clic su **Salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri di filtro della posta indesiderata, incluse le impostazioni di notifica di posta indesiderata dell'utente finale.
    
> [!NOTE]
>  Le notifiche di posta indesiderata dell'utente finale saranno funzionali solo per i criteri di filtro della posta indesiderata abilitati. >  Le notifiche di posta indesiderata dell'utente finale vengono inviate solo una volta al giorno. Non è possibile garantire l'ora di recapito della notifica per alcun utente specifico e non è possibile configurarla. 
  
 **Suggerimento:** Se si desidera testare le notifiche di posta indesiderata dell'utente finale inviando un gruppo limitato di utenti prima di implementarle completamente, creare un criterio di filtro di posta indesiderata personalizzato che consenta le notifiche di posta indesiderata dell'utente finale per i domini in cui risiedono gli utenti. Successivamente, nell'interfaccia di amministrazione di Exchange, in **regole del flusso \> di posta**, creare una regola del flusso di posta (nota anche come regola di trasporto) per bloccare i messaggi da Quarantine@messaging.microsoft.com (l'indirizzo di posta elettronica che invia le notifiche) con le eccezioni per gli utenti che si desiderano ricevere le notifiche. La figura seguente descrive un esempio relativo alla creazione di un'eccezione per due utenti (SaraD e AlexD) dal dominio Contoso.com: 
  
![Regola di trasporto per verificare le notifiche di posta indesiderata dell'utente finale](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a>Utilizzo di SCC per configurare le notifiche di posta indesiderata dell'utente finale

È inoltre possibile utilizzare il Centro sicurezza e conformità (SCC) per configurare le notifiche di posta indesiderata dell'utente finale. Eseguire la procedura seguente:

1. Aprire il Centro sicurezza e conformità, accedere a **** \> **criteri** \> di gestione della **posta indesiderata** o utilizzare il https://protection.office.com/antispamcollegamento diretto.

2. Fare clic sulla freccia in giù accanto al criterio di filtro posta indesiderata per il quale si vogliono abilitare le notifiche di posta indesiderata dell'utente finale.

3. Fare clic sul collegamento **Configura notifiche di posta indesiderata dell'utente finale** .

4. Nella finestra di dialogo successiva è possibile configurare le seguenti opzioni:
    
   - **Abilita le notifiche di spam all'utente finale** Selezionare questa casella di controllo per abilitare le notifiche di posta indesiderata dell'utente finale per questo criterio. Viceversa, se questo criterio è abilitato, è possibile deselezionare la casella di controllo per disabilitare le notifiche di posta indesiderata dell'utente finale per tale criterio. 
    
   - **Invia notifiche di spam agli utenti finali ogni (giorni)** Consente di specificare la frequenza di invio delle notifiche di posta indesiderata dell'utente finale. Il valore predefinito è 3 giorni. È possibile specificare un valore compreso tra 1 e 15 giorni. Se, ad esempio, si specifica 7 giorni, la notifica includerà l'elenco di tutti i messaggi che negli ultimi 7 giorni erano diretti all'utente ma che sono stati invece inviati alla quarantena della posta indesiderata. 
    
   - **Lingua delle notifiche** Utilizzando l'elenco a discesa, selezionare la lingua in cui scrivere le notifiche di posta indesiderata dell'utente finale per il criterio in questione. 
    
   - Fare clic su **Salva**. Nel riquadro viene visualizzato un riepilogo delle impostazioni dei criteri di filtro della posta indesiderata, incluse le impostazioni di notifica di posta indesiderata dell'utente finale.

## <a name="for-more-information"></a>Ulteriori informazioni

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
