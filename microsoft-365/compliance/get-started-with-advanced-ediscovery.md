---
title: Configurare Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come configurare Advanced eDiscovery per iniziare a creare e gestire i casi. Vengono inoltre descritte le sottoscrizioni e le licenze Microsoft necessarie. Dopo aver completato alcuni passaggi rapidi, lo strumento Advanced eDiscovery è pronto per l'uso.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919747"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurare Microsoft 365 Advanced eDiscovery

Advanced eDiscovery in Microsoft 365 fornisce un flusso di lavoro end-to-end per conservare, raccogliere, esaminare, analizzare ed esportare i dati in grado di rispondere alle indagini interne ed esterne dell'organizzazione. Non è necessario distribuire Advanced eDiscovery, ma esistono alcune attività preliminari che un amministratore IT e un responsabile di eDiscovery devono completare prima che l'organizzazione possa iniziare Advanced eDiscovery creare e usare casi di Advanced eDiscovery per gestire le indagini.

In questo articolo vengono illustrati i passaggi seguenti necessari per configurare Advanced eDiscovery.

![Passaggi per la configurazione Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

Ciò include la garanzia delle licenze appropriate necessarie per accedere Advanced eDiscovery e aggiungere i custodi ai casi e l'assegnazione delle autorizzazioni al team legale e di indagine in modo che possano accedere e gestire i casi.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Passaggio 1: Verificare e assegnare licenze appropriate

Le licenze per Advanced eDiscovery richiedono l'abbonamento all'organizzazione appropriato e le licenze per utente. Per un elenco dei requisiti di licenza per Advanced eDiscovery, vedere [Sottoscrizioni e licenze.](overview-ediscovery-20.md#subscriptions-and-licensing)

## <a name="step-2-assign-ediscovery-permissions"></a>Passaggio 2: Assegnare le autorizzazioni di eDiscovery

Per accedere Advanced eDiscovery o aggiunto come membro di un caso Advanced eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In particolare, un utente deve essere aggiunto come membro del gruppo di ruoli Manager eDiscovery nel Centro sicurezza & conformità. I membri di questo gruppo di ruoli possono creare e gestire Advanced eDiscovery casi. Possono aggiungere e rimuovere membri, mettere i custodi e i percorsi di contenuto in attesa, gestire le notifiche di blocco legale, creare e modificare le ricerche associate in un caso, aggiungere risultati di ricerca a un set di recensioni, analizzare i dati in un set di recensioni ed esportare e scaricare da un caso di Advanced eDiscovery.

Completare la procedura seguente per aggiungere utenti al gruppo di ruoli Manager eDiscovery:

1. Accedere a e accedere utilizzando le credenziali per <https://protection.office.com/permissions> un account amministratore nell'Microsoft 365 aziendale.

2. Nella pagina **Autorizzazioni** selezionare il gruppo di ruoli **Manager eDiscovery.**

3. Nella pagina a comparsa Gestione eDiscovery fare clic su **Modifica** accanto alla sezione **Gestione eDiscovery.**

4. Nella pagina **Choose eDiscovery Manager** della procedura guidata edit role group fare clic **su Choose eDiscovery Manager.**

5. Fare **clic su** Aggiungi, quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Fare **clic su** Aggiungi per aggiungere gli utenti selezionati e quindi fare clic su **Fine.**

7. Fare **clic** su Salva per aggiungere gli utenti al gruppo di ruoli, quindi fare clic su **Chiudi** per completare il passaggio.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Ulteriori informazioni sul gruppo di ruoli Manager eDiscovery

Esistono due sottogruppi nel gruppo di ruoli Manager eDiscovery. La differenza tra questi sottogruppi dipende dall'ambito.

- **eDiscovery Manager:** può visualizzare e gestire i Advanced eDiscovery che creano o di cui sono membri. Se un altro responsabile di eDiscovery crea un caso ma non aggiunge un secondo responsabile di eDiscovery come membro di tale caso, il secondo gestore di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina Advanced eDiscovery del Centro conformità. In generale, la maggior parte degli utenti dell'organizzazione può essere aggiunta al sottogruppo Manager di eDiscovery.

- **Amministratore di eDiscovery:** può eseguire tutte le attività di gestione dei casi che possono essere eseguite da un responsabile di eDiscovery. Inoltre, un amministratore di eDiscovery è in grado di:

  - Visualizzare tutti i casi elencati nella pagina Advanced eDiscovery.
  
  - Gestire i casi nell'organizzazione dopo essersi aggiunto come membro del caso.

  - Accedere ai dati dei casi ed esportarli per qualsiasi caso nell'organizzazione.

  Dato l'ampio ambito di accesso, un'organizzazione deve avere solo alcuni amministratori che sono membri del sottogruppo Amministratori di eDiscovery.

Per ulteriori informazioni sulle autorizzazioni di eDiscovery e una descrizione di ogni ruolo assegnato al gruppo di ruoli Manager eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Passaggio 3: Configurare le impostazioni globali per Advanced eDiscovery

L'ultimo passaggio da completare prima che gli utenti dell'organizzazione inizino a creare e utilizzare i casi consiste nel configurare le impostazioni globali applicabili a tutti i casi dell'organizzazione. In questo momento, l'unica impostazione globale è il rilevamento dei privilegi *avvocato-client* (altre impostazioni globali saranno disponibili in futuro). Questa impostazione consente l'esecuzione del modello di privilegio avvocato-client quando si analizzano i dati in un set di revisione. Il modello usa l'apprendimento automatico per determinare la probabilità che un documento contenga contenuto di natura legale. Confronta inoltre i partecipanti ai documenti con un elenco di avvocati (inviato durante la configurazione del modello) per determinare se un documento ha almeno un partecipante che è un avvocato.

Per ulteriori informazioni sulla configurazione e sull'utilizzo del modello di rilevamento dei privilegi avvocato-client, vedere [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).

> [!NOTE]
> Si tratta di un passaggio facoltativo che è possibile eseguire in qualsiasi momento. La non implementazione del modello di rilevamento dei privilegi avvocato-client non impedisce all'utente di creare e Advanced eDiscovery casi.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver configurato Advanced eDiscovery, sei pronto per [creare un caso.](create-and-manage-advanced-ediscoveryv2-case.md)