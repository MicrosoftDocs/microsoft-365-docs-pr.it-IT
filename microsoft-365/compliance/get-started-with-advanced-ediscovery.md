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
- m365solution-ediscovery
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come configurare Advanced eDiscovery per iniziare a creare e gestire i casi. Vengono inoltre descritte le sottoscrizioni e le licenze Microsoft necessarie. Dopo aver completato alcuni passaggi rapidi, lo strumento Advanced eDiscovery è pronto per l'uso.
ms.openlocfilehash: 29a220f36a55a04d1c1a24add03b2e013a5c60ba
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727411"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurare Microsoft 365 Advanced eDiscovery

Advanced eDiscovery in Microsoft 365 offre un flusso di lavoro [end-to-end](overview-ediscovery-20.md#advanced-ediscovery-workflow) per conservare, raccogliere, esaminare, analizzare ed esportare i dati in grado di rispondere alle indagini interne ed esterne dell'organizzazione. Non è necessario distribuire Advanced eDiscovery, ma esistono alcune attività preliminari che un amministratore IT e un manager di eDiscovery devono completare prima che l'organizzazione possa iniziare a creare e utilizzare casi di eDiscovery avanzati per gestire le indagini.

In questo articolo vengono illustrati i passaggi necessari per configurare Advanced eDiscovery. Ciò include la garanzia delle licenze appropriate necessarie per accedere a Advanced eDiscovery e aggiungere i custodi ai casi e l'assegnazione delle autorizzazioni al team legale e di indagine in modo che possano accedere e gestire i casi.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Passaggio 1: Verificare e assegnare licenze appropriate

Le licenze per Advanced eDiscovery richiedono l'abbonamento all'organizzazione appropriato e le licenze per utente.

- **Sottoscrizione organizzazione:** Per accedere a Advanced eDiscovery nel Centro conformità Microsoft 365 o nel Centro sicurezza e conformità &, l'organizzazione deve disporre di uno degli elementi seguenti:

  - Abbonamento a Microsoft 365 E5 o a Office 365 E5
  
  - Abbonamento a Microsoft 365 E3 con il componente aggiuntivo E5 Compliance

  - Abbonamento a Microsoft 365 E3 con il componente aggiuntivo eDiscovery e controllo di E5

  Se non si dispone di un piano Microsoft 365 E5 esistente e si desidera provare Advanced eDiscovery, è possibile aggiungere [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 E5.

- **Licenze per utente:** Per aggiungere un utente come responsabile in un caso di Advance eDiscovery, a tale utente deve essere assegnata una delle licenze seguenti, a seconda dell'abbonamento all'organizzazione:

  - Microsoft 365: agli utenti deve essere assegnata una licenza di Microsoft 365 E5, una licenza del componente aggiuntivo Conformità E5 o una licenza del componente aggiuntivo E5 eDiscovery e controllo.

  - Office 365: agli utenti deve essere assegnata una licenza di Office 365 E5.

   Per informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> Gli utenti necessitano solo di una licenza E5 (o della licenza del componente aggiuntivo appropriata) da aggiungere come custodi a un caso advanced eDiscovery. Gli amministratori IT, i responsabili di eDiscovery, gli avvocati, i paralegali o gli investigatori che utilizzano Advanced eDiscovery per gestire i casi e rivedere i dati dei casi non necessitano di una licenza E5 o di un componente aggiuntivo.

## <a name="step-2-assign-ediscovery-permissions"></a>Passaggio 2: Assegnare le autorizzazioni di eDiscovery

Per accedere a Advanced eDiscovery o essere stato aggiunto come membro di un caso advanced eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In particolare, un utente deve essere aggiunto come membro del gruppo di ruoli Manager eDiscovery nel Centro sicurezza & conformità. I membri di questo gruppo di ruoli possono creare e gestire i casi di Advanced eDiscovery. Possono aggiungere e rimuovere membri, mettere in attesa i custodi e i percorsi di contenuto, gestire le notifiche di blocco legale, creare e modificare le ricerche associate in un caso, aggiungere risultati di ricerca a un set di recensioni, analizzare i dati in un set di recensioni ed esportare e scaricare da un caso advanced eDiscovery.

Completare la procedura seguente per aggiungere utenti al gruppo di ruoli Manager eDiscovery:

1. Accedere a e accedere utilizzando le credenziali per [https://protection.office.com/permissions](https://protection.office.com/permissions) un account amministratore nell'organizzazione di Microsoft 365.

2. Nella pagina **Autorizzazioni** selezionare il gruppo di ruoli **Manager eDiscovery.**

3. Nella pagina a comparsa Gestione eDiscovery fare clic su **Modifica** accanto alla sezione **Gestione eDiscovery.**

4. Nella pagina **Choose eDiscovery Manager** della procedura guidata edit role group fare clic **su Choose eDiscovery Manager.**

5. Fare **clic su** Aggiungi, quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Fare **clic su** Aggiungi per aggiungere gli utenti selezionati e quindi fare clic su **Fine.**

7. Fare **clic** su Salva per aggiungere gli utenti al gruppo di ruoli, quindi fare clic su **Chiudi** per completare il passaggio.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Ulteriori informazioni sul gruppo di ruoli Manager eDiscovery

Esistono due sottogruppi nel gruppo di ruoli Manager eDiscovery. La differenza tra questi sottogruppi dipende dall'ambito.

- **eDiscovery Manager:** Può visualizzare e gestire i casi di Advanced eDiscovery creati o di cui sono membri. Se un altro responsabile di eDiscovery crea un caso ma non aggiunge un secondo responsabile di eDiscovery come membro di tale caso, il secondo gestore di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina Advanced eDiscovery nel Centro conformità. In generale, la maggior parte degli utenti dell'organizzazione può essere aggiunta al sottogruppo Manager di eDiscovery.

- **Amministratore di eDiscovery:** Può eseguire tutte le attività di gestione dei casi che possono essere eseguite da un responsabile di eDiscovery. Inoltre, un amministratore di eDiscovery è in grado di:

  - Visualizzare tutti i casi elencati nella pagina Advanced eDiscovery.
  
  - Gestire qualsiasi caso nell'organizzazione dopo essersi aggiunti come membri del caso.

  - Accedere ed esportare i dati del caso per qualsiasi caso nell'organizzazione.

  A causa dell'ampio ambito di accesso, un'organizzazione deve avere solo pochi amministratori membri del sottogruppo Amministratori di eDiscovery.

Per ulteriori informazioni sulle autorizzazioni di eDiscovery e una descrizione di ogni ruolo assegnato al gruppo di ruoli Manager eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Passaggio 3: Configurare le impostazioni globali per Advanced eDiscovery

L'ultimo passaggio da completare prima che gli utenti dell'organizzazione inizino a creare e utilizzare i casi consiste nel configurare le impostazioni globali applicabili a tutti i casi dell'organizzazione. In questo momento, l'unica impostazione globale è il rilevamento dei privilegi *avvocato-client* (altre impostazioni globali saranno disponibili in futuro). Questa impostazione consente l'esecuzione del modello di privilegio avvocato-client quando si analizzano i dati in un set di revisione. Il modello usa l'apprendimento automatico per determinare la probabilità che un documento contenga contenuto di natura legale. Confronta inoltre i partecipanti ai documenti con un elenco di avvocati (inviato durante la configurazione del modello) per determinare se un documento ha almeno un partecipante che è un avvocato.

Per ulteriori informazioni sulla configurazione e sull'utilizzo del modello di rilevamento dei privilegi [avvocato-client, vedere Set up attorney-client privilege detection in Advanced eDiscovery.](attorney-privilege-detection.md)

> [!NOTE]
> Si tratta di un passaggio facoltativo che è possibile eseguire in qualsiasi momento. La non implementazione del modello di rilevamento dei privilegi avvocato-client non impedisce la creazione e l'utilizzo di casi di Advanced eDiscovery.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver configurato Advanced eDiscovery, è possibile [creare un caso.](create-and-manage-advanced-ediscoveryv2-case.md)
