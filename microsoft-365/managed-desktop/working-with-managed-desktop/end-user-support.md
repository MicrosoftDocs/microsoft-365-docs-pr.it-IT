---
title: Ottenere supporto per gli utenti per Microsoft Managed Desktop
description: Come gli utenti possono ottenere assistenza con il servizio e i dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362607"
---
# <a name="getting-help-for-users"></a>Ottenere assistenza per gli utenti

Se hai raggiunto il punto [](../service-description/user-support.md) del flusso di lavoro in cui devi richiedere l'accesso al dispositivo con privilegi elevati o l'escalation a Microsoft, segui questi passaggi:
 
>[!NOTE]
>Queste opzioni di supporto non sono disponibili per i dispositivi nel gruppo Test.

## <a name="elevation-requests"></a>Richieste di elevazione

Prima di richiedere l'accesso con privilegi elevati a un dispositivo, è meglio esaminare le azioni più adatte.

- **Le azioni tipiche** sono l'obiettivo di questo processo e vengono eseguite di routine durante la risoluzione dei problemi Microsoft Managed Desktop dispositivi. Alcuni esempi:
    - Elevazione degli strumenti di risoluzione dei problemi di sistema incorporati, del prompt dei comandi o Windows PowerShell
    - Risoluzione dei problemi delle applicazioni line-of-business
    - Uso di una soluzione alternativa per correggere un elemento che dovrebbe funzionare in base alla progettazione (ad esempio l'attivazione di BitLocker o l'ora di sistema non aggiornata)
    - Elevazione di Gestione dispositivi per eseguire operazioni quali l'aggiornamento dei driver, la disinstallazione di un dispositivo o la ricerca di nuove modifiche

- **Le azioni non consigliate includono:**
    - Installazione di software o browser
    - Installazione di driver al di fuori delle Windows, incluse quelle per le periferiche
    - Installazione di .msi o .exe file
    - Installazione di Windows funzionalità

- **Le azioni non supportate includono:**
    - Installazione di software o funzionalità in conflitto con Microsoft Managed Desktop di sicurezza o gestione o operazioni
    - Disabilitazione di Windows funzionalità necessaria per Microsoft Managed Desktop, ad esempio BitLocker
    - Modifica delle impostazioni gestite dall'organizzazione

### <a name="to-request-elevation"></a>Per richiedere l'elevazione

1. Accedere al portale [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) all'indirizzo e accedere con le credenziali Azure Active Directory utente.
2. Selezionare **Nuova richiesta di elevazione**.
3. Fornire questi dettagli:
    - **ID ticket di** supporto dal proprio sistema di ticket di supporto.
    - **Nome dispositivo:** immetti il numero di serie del dispositivo e quindi seleziona il dispositivo dal menu.
    - **Categoria**: selezionare la categoria più adatta al problema. Se nessuna opzione sembra chiusa, seleziona **Altro** e fornisci altre informazioni nei campi **Titolo** **e Piano di** azione. È meglio selezionare una categoria, se possibile.
    - **Sottocategoria:** selezionare quella più adatta al problema. Se nessuna opzione sembra chiusa, seleziona **Altro** e fornisci una breve descrizione in **Titolo.** In **Plan of action** fornire i passaggi per la risoluzione dei problemi che si prevede di eseguire dopo aver concesso l'elevazione.
4. Selezionare **Invia**.


## <a name="escalation-requests"></a>Richieste di escalation


Se è necessario [inoltrare un](../service-description/user-support.md#escalation-portal) problema a Microsoft, attenersi alla seguente procedura:

1. Accedere al portale [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) all'indirizzo e accedere con le credenziali Azure Active Directory utente.
2. Selezionare **Richieste di escalation** e quindi Nuova richiesta di **escalation.**
3. Fornire questi dettagli:
    - **Categoria**: selezionare la categoria più adatta al problema.
    - **Title**: Fornire una breve descrizione.
    - **Descrizione:** aggiungere ulteriori dettagli che potrebbero aiutare il team a comprendere il problema. Se è necessario allegare file, è possibile farlo tornando alla richiesta dopo l'invio.
    - **Informazioni di contatto principali:** fornire informazioni su come contattare la persona principale responsabile della collaborazione con il team.
4. Selezionare **Invia**.
5. Rivedere il ticket nello stesso portale per interagire con il team.

> [!NOTE]
> Solo i problemi di gravità C possono essere inoltrati attraverso questo percorso. Per altri problemi, contattare l'amministratore IT per file la richiesta tramite il portale di amministrazione.